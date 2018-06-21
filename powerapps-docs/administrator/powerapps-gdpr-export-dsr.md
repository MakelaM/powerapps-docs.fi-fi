---
title: PowerApps-asiakastietojen vientiin liittyviin DSR-pyyntöihin vastaaminen | Microsoft Docs
description: Ohjeet PowerApps-asiakastietojen vientiin liittyviin DSR-pyyntöihin vastaamiseen.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 000f15ea7b1fa4e11cbe49b44e57017daf973a89
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34552963"
---
# <a name="responding-to-data-subject-rights-dsr-requests-to-export-powerapps-customer-data"></a>PowerApps-asiakastietojen vientiin liittyviin DSR-pyyntöihin vastaaminen
Oikeus tietojen siirtämiseen antaa rekisteröidylle oikeuden pyytää kopiota henkilötiedoistaan sähköisessä muodossa (yleensä tämä on jäsennelty, yleisesti käytetty, koneluettava ja yhteentoimiva muoto), jossa tiedot voidaan siirtää toiselle rekisterinpitäjälle:

* Sivustot: [PowerApps-portaali](https://web.powerapps.com), [PowerApps-hallintakeskus](https://admin.powerapps.com/) ja [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)

* PowerShellin käyttö: PowerApps [Sovelluksen luojan cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871448), [Järjestelmänvalvojan cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804) ja [Paikalliset yhdyskäytävän cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=872238)

Alla on yhteenveto henkilötietojen tyypeistä, jotka PowerApps voi tallentaa tietylle käyttäjälle ja joiden avulla tiedot voi hakea ja viedä.

Henkilötietoja sisältävät resurssit | Sivuston käyttö |   PowerShellin käyttö
--- | --- | --
Ympäristö | PowerApps-hallintakeskus |  PowerAppsin cmdlet-komennot
Ympäristön oikeudet**   | PowerApps-hallintakeskus    | PowerAppsin cmdlet-komennot
Kaaviosovellus  | PowerApps-hallintakeskus <br> PowerApps-portaali |    PowerAppsin cmdlet-komennot
Kaaviosovellusten oikeudet  | PowerApps-hallintakeskus <br> PowerApps-portaali  | PowerAppsin cmdlet-komennot
Yhdyskäytävä | PowerApps-portaali***   | Paikalliset yhdyskäytävän cmdlet-komennot
Yhdyskäytävien oikeudet | PowerApps-portaali***   |
Mukautettu yhdistin | |    Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä
Mukautettujen yhdistimien oikeudet | |    Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä
Yhteys | | Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä
Yhteyksien oikeudet  | | Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä
PowerAppsin käyttäjäasetukset, käyttäjäsovelluksen asetukset ja ilmoitukset | | Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä

> ** Kun Common Data Service (CDS) for Apps on käytössä ja tietokanta luodaan ympäristöön, ympäristön käyttöoikeudet ja mallipohjaisten sovellusten käyttöoikeudet tallennetaan tietueina CDS for Apps -tietokannan esiintymään. Saat lisätietoja CDC for Appsia käyttävien käyttäjien DSR-pyyntöihin vastaamisesta ohjeartikkelista [DSR:ien suorittaminen CDC for Appsin asiakastiedoille](common-data-service-gdpr-dsr-guide.md).

> *** Järjestelmänvalvoja voi käyttää näitä resursseja [PowerApps-portaalista](https://web.powerapps.com) vain, jos resurssin omistaja on myöntänyt eksplisiittisesti hänelle käyttöoikeuden. Jos näin ei ole, järjestelmänvalvojan on hyödynnettävä [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentoja](https://go.microsoft.com/fwlink/?linkid=871804).

## <a name="prerequisites"></a>Edellytykset

### <a name="for-users"></a>Käyttäjille
Käyttäjät, joilla on kelvollinen PowerApps-käyttöoikeus, voivat suorittaa tässä asiakirjassa kuvattuja toimenpiteitä käyttämällä [PowerApps-portaalia](https://web.powerapps.com) tai [sovelluksen luojien cmdlet-komentoja](https://go.microsoft.com/fwlink/?linkid=871448).

### <a name="for-admins"></a>Järjestelmänvalvojille
Tässä asiakirjassa mainittujen hallintatoimintojen suorittaminen PowerAppsin hallintakeskuksen, Microsoft Flow -hallintakeskuksen tai [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) avulla edellyttää seuraavia käyttöoikeuksia:

* Maksullisen PowerApps-palvelupaketin 2 käyttöoikeus tai PowerApps-palvelupaketin 2 kokeiluversion käyttöoikeus. Voit rekisteröityä 30 päivän maksuttoman kokeiluversion käyttäjäksi osoitteessa [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Kokeiluversion käyttöoikeudet voi uusia, jos ne ovat vanhentuneet.

* [Office 365:n yleisen järjestelmänvalvojan](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleisen järjestelmänvalvojan](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) oikeudet ovat myös pakollisia, jos haluat tehdä hakuja toisen käyttäjän resursseihin. (Huomioi, että ympäristön järjestelmänvalvojilla on pääsy vain niihin ympäristöihin ja ympäristön resursseihin, joihin heillä on oikeudet.)

## <a name="step-1-export-personal-data-contained-within-environments-created-by-the-user"></a>Vaihe 1: vie käyttäjän luomiin ympäristöihin sisältyvät henkilötiedot

### <a name="powerapps-admin-center"></a>PowerApps-hallintakeskus
Järjestelmänvalvojat voivat viedä kaikki tietyn käyttäjän luomat ympäristöt [PowerApps-hallintakeskuksesta](https://admin.powerapps.com/) seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi.

    ![Hallintakeskuksen saapumissivu](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Jos ympäristön on luonut DSR-pyynnön lähettänyt käyttäjä, siirry **Tiedot**-sivulle, kopioi tiedot ja liitä ne tiedostojen muokkausohjelmaan, kuten Microsoft Wordiin.

    ![Ympäristön tiedot](./media/powerapps-gdpr-export-dsr/environment-details.png)

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjät voivat viedä ympäristöt, joihin heillä on käyttöoikeus PowerAppsissa, käyttämällä [PowerAppsin sovelluksen luojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871448) **Get-PowerAppsEnvironment**-funktiota:

~~~~
Add-PowerAppsAccount
Get-PowerAppsEnvironment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä kaikki käyttäjän luomat ympäristöt [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminEnvironment**-funktiolla:

~~~~
Add-PowerAppsAccount
$userId = "7557f390-5f70-4c93-8bc4-8c2faabd2ca0"
Get-AdminEnvironment -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-2-export-the-users-environment-permissions"></a>Vaihe 2: vie käyttäjän ympäristöjen oikeudet
Käyttäjille voidaan määrittää ympäristössä oikeuksia (kuten ympäristön järjestelmänvalvoja ja ympäristön tekijä), jotka tallennetaan PowerApps-palveluun *roolimäärityksenä*. Kun CDS for Apps on käytössä ja tietokanta luodaan ympäristöön, nämä roolimääritykset tallennetaan tietueina CDS for Apps -tietokannan esiintymään. Lisätietoja on [PowerAppsin ympäristöjen hallinta](environments-administration.md) -osiossa.

### <a name="for-environments-without-a-cds-for-apps-database"></a>Ympäristöt, joissa ei ole Sovellusten CDS -tietokantaa

#### <a name="powerapps-admin-center"></a>PowerApps-hallintakeskus
Järjestelmänvalvojat voivat viedä käyttäjän ympäristöjen oikeudet [PowerApps-hallintakeskuksesta](https://admin.powerapps.com/) seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi. Sinun on oltava [Office 365:n yleinen järjestelmänvalvoja](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleinen järjestelmänvalvoja](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), jotta voit tarkastella kaikkia ympäristöjä, jotka on luotu organisaatiosi sisällä.

    ![Hallintakeskuksen saapumissivu](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Valitse **Suojaus**.

    Jos ympäristössäsi ei ole Sovellusten CDS -tietokantaa, näkyviin tulee osa, jossa ovat **Ympäristön roolit.**

3. Valitse **Ympäristön järjestelmänvalvoja** ja **Ympäristön tekijä** erikseen ja hae käyttäjän nimi etsintäpalkin kautta.

    ![Ympäristön roolit -sivu](./media/powerapps-gdpr-export-dsr/admin-environment-role-share-page.png)

4. Jos käyttäjällä on jommankumman roolin käyttöoikeus, siirry **Käyttäjät**-sivulle, kopioi tiedot ja liitä ne tiedostojen muokkausohjelmaan, kuten Microsoft Wordiin.

#### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä kaikki käyttäjän ympäristön roolimääritykset kaikissa ympäristöissä ilman Sovellusten CDS -tietokantaa käyttämällä [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminEnvironmentRoleAssignment**-funktiota:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminEnvironmentRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

> [!IMPORTANT]
>  Tämä funktio toimii vain ympäristöissä, joissa ei ole Sovellusten CDS -tietokannan esiintymää.
>
>

### <a name="for-environments-with-a-cds-for-apps-database"></a>Ympäristöt, joissa on CDS for Apps -tietokanta
Kun Sovellusten CDS on käytössä, jos tietokanta luodaan ympäristöön, roolimääritykset tallennetaan tietueina Sovellusten CDS -tietokannan esiintymään. Katso lisätietoja henkilötietojen poistamisesta Sovellusten CDS -tietokannan esiintymästä kohdasta [Common Data Service -käyttäjän henkilötietojen poistaminen](https://go.microsoft.com/fwlink/?linkid=871886).
 
## <a name="step-3-export-personal-data-contained-within-canvas-apps-created-by-the-user"></a>Vaihe 3: vie käyttäjän luomiin kaaviosovelluksiin sisältyvät henkilötiedot

### <a name="powerapps-portal"></a>PowerApps-portaali
Käyttäjä voi viedä sovelluksen [PowerApps-portaalista](https://web.powerapps.com). Katso vaiheittaiset ohjeet sovelluksen viemiseen kohdasta [Sovelluksen vieminen](environment-and-tenant-migration.md#exporting-an-app).

### <a name="powerapps-admin-center"></a>PowerApps-hallintakeskus
Järjestelmänvalvoja voi viedä käyttäjän luomat sovellukset [PowerApps-hallintakeskuksesta](https://admin.powerapps.com/) seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi. Sinun on oltava [Office 365:n yleinen järjestelmänvalvoja](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleinen järjestelmänvalvoja](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), jotta voit tarkastella kaikkia ympäristöjä, jotka on luotu organisaatiosi sisällä.

    ![Hallintakeskuksen saapumissivu](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Valitse **Resurssit** ja sitten **Sovellukset**.

3. Hae etsintäpalkin avulla käyttäjän nimi, jolla saadaan näkyviin sovellukset, jotka kyseinen käyttäjä on luonut tähän ympäristöön:

    ![Hae sovelluksia](./media/powerapps-gdpr-export-dsr/search-apps.png)

4. Valitse kaikkien kyseisen käyttäjän luomien sovellusten kohdalla **Jaa** ja anna itsellesi sovelluksen **Voi muokata** -käyttöoikeus:

    ![Valitse sovelluksen jakaminen](./media/powerapps-gdpr-export-dsr/select-share.png)

    ![Anna käyttäjälle käyttöoikeus](./media/powerapps-gdpr-export-dsr/grant-access.png)

5. Kun sinulla on käyttöoikeus jokaiseen käyttäjän sovellukseen, voit viedä sovelluksen [PowerApps-portaalista](https://web.powerapps.com). Katso vaiheittaiset ohjeet sovelluksen viemiseen kohdasta [Sovelluksen vieminen](environment-and-tenant-migration.md#exporting-an-app).

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä käyttäjän luomat sovellukset [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminApp**-funktiolla:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminApp -Owner $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-4-export-the-users-permissions-to-canvas-apps"></a>Vaihe 4: vie käyttäjän kaaviosovellusten oikeudet
Aina, kun sovellus on jaettu käyttäjän kanssa, PowerApps tallentaa tietueen nimeltä *roolimääritys*, joka kuvaa käyttäjän oikeuksia (CanEdit tai CanUser) sovellukseen. Lisätietoja saat kohdasta [Sovelluksen jakaminen](../maker/canvas-apps/share-app.md#share-an-app).

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjät voivat viedä kaikkien niiden sovellusten roolimääritykset, joihin heillä on käyttöoikeus, [PowerAppsin sovelluksen luojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871448) **Get-RoleAssignment**-funktiolla:

~~~~
Add-PowerAppsAccount
Get-AppRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powerapps-admin-center"></a>PowerApps-hallintakeskus
Järjestelmänvalvojat voivat viedä käyttäjän sovellusten roolimääritykset [PowerApps-hallintakeskuksesta](https://admin.powerapps.com/) seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi. Sinun on oltava [Office 365:n yleinen järjestelmänvalvoja](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleinen järjestelmänvalvoja](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), jotta voit tarkastella kaikkia ympäristöjä, jotka on luotu organisaatiosi sisällä.

    ![Hallintakeskuksen saapumissivu](./media/powerapps-gdpr-export-dsr/admin-center-landing.png)

2. Valitse kunkin ympäristön kohdalla **Resurssit** ja sitten **Sovellukset**.

3. Valitse **Jaa** kullekin ympäristössä olevalle sovellukselle.

    ![Valitse sovelluksen jakaminen](./media/powerapps-gdpr-export-dsr/select-admin-share-nofilter.png)

4. Jos käyttäjällä on sovelluksen käyttöoikeus, siirry sovelluksen **Jaa**-sivulle, kopioi tiedot ja liitä ne tiedostojen muokkausohjelmaan, kuten Microsoft Wordiin.

    ![Järjestelmänvalvojan sovelluksen jakaminen -sivu](./media/powerapps-gdpr-export-dsr/admin-share-page.png)

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä käyttäjän kaikki sovellusten roolimääritykset vuokraajan kaikista sovelluksista käyttämällä [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminAppRoleAssignment**-funktiota:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminAppRoleAssignment -UserId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-5-export-personal-data-contained-within-connections-created-by-the-user"></a>Vaihe 5: vie käyttäjän luomiin yhteyksiin sisältyvät henkilötiedot
Yhteyksiä käytetään yhdistimien kanssa muodostettaessa yhteyksiä muihin ohjelmointirajapintoihin ja SaaS-järjestelmiin. Yhteyksien sisällä on viittauksia käyttäjään, joka ne on luonut, ja sen vuoksi ne voidaan poistaa, jotta saadaan poistettua mahdolliset viittaukset käyttäjään.

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjät voivat viedä kaikki yhteydet, joihin heillä on käyttöoikeus, [PowerAppsin sovelluksen luojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871448) **Get-Connection**-funktiolla:

~~~~
Add-PowerAppsAccount
Get-Connection | ConvertTo-Json | out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä käyttäjän luomat yhteydet [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminConnection**-funktiolla:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnection -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-6-export-the-users-permissions-to-shared-connections"></a>Vaihe 6: vie käyttäjän jaettujen yhteyksien oikeudet

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjät voivat viedä kaikkien niiden yhteyksien roolimääritykset, joihin heillä on käyttöoikeus, [PowerAppsin sovelluksen luojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871448) **Get-ConnectionRoleAssignment**-funktiolla:

~~~~
Add-PowerAppsAccount
Get-ConnectionRoleAssignment | ConvertTo-Json | Out-file -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä käyttäjän kaikki yhteysroolimääritykset [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminConnectionRoleAssignment**-funktiolla:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectionRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-7-export-personal-data-contained-within-custom-connectors-created-by-the-user"></a>Vaihe 7: vie käyttäjän luomiin mukautettuihin yhdistimiin sisältyvät henkilötiedot
Mukautetut yhdistimet täydentävät valmiina tulevia yhdistimiä ja mahdollistavat yhdistämisen muihin ohjelmointirajapintoihin, SaaS-järjestelmiin ja mukautettuihin järjestelmiin.

### <a name="powerapps-app-creator-powershell-cmdlets"></a>PowerAppsin sovelluksen luojan PowerShell-cmdlet-komennot
Käyttäjät voivat viedä kaikki itse luomansa mukautetut liittimet käyttämällä [PowerAppsin sovelluksen luojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871448) **Get-Connector**-funktiota:

~~~~
Add-PowerAppsAccount  
Get-Connector -FilterNonCustomConnectors | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä kaikki käyttäjän luomat mukautetut liittimet [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminConnector**-funktiolla:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnector -CreatedBy $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

## <a name="step-8-export-the-users-permissions-to-custom-connectors"></a>Vaihe 8: vie käyttäjän mukautettujen yhdistimien oikeudet

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjät voivat viedä kaikkien niiden mukautettujen yhdistimien roolimääritykset, joihin heillä on käyttöoikeus, [PowerAppsin sovelluksen luojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871448) **Get-ConnectorRoleAssignment**-funktiolla:

~~~~
Add-PowerAppsAccount  
Get-ConnectorRoleAssignment | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä kaikki käyttäjän mukautetun liittimen roolimääritykset [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminConnectorRoleAssignment**-funktiolla:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminConnectorRoleAssignment -PrincipalObjectId $userId | ConvertTo-Json | Out-File -FilePath "UserDetails.json"
~~~~
 
## <a name="step-9-export-powerapps-notifications-user-settings-and-user-app-settings"></a>Vaihe 9: vie PowerAppsin ilmoitukset, käyttäjäasetukset ja käyttäjäsovelluksen asetukset
PowerApps lähettää käyttäjille useita erilaisia ilmoituksia, esimerkiksi siitä, kun sovellus jaetaan heidän kanssaan tai kun Sovellusten CDS -vientitoiminto on suoritettu. Käyttäjän ilmoitushistoria näkyy hänelle [PowerApps-portaalissa](https://web.powerapps.com).

PowerApps tallentaa myös useita eri käyttäjäasetuksia ja asetuksia, joiden avulla tarjotaan PowerAppsin suorituspalvelun ja portaalin käyttökokemus, mukaan lukien tiedot siitä, milloin käyttäjä viimeksi avasi sovelluksen, kiinnitti sovelluksen jne.

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjät voivat viedä omat PowerApps-ilmoituksensa, käyttäjäasetuksensa ja käyttäjäsovellusten asetuksensa [PowerAppsin sovelluksen luojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871448) **Get-AdminPowerAppsUserDetails**-funktiolla:

~~~~
Add-PowerAppsAccount  
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json"
~~~~

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvojat voivat viedä PowerApps-ilmoitukset, käyttäjäasetukset ja käyttäjän käyttäjäsovellusten asetukset [PowerAppsin järjestelmänvalvojan PowerShell-cmdlet-komentojen](https://go.microsoft.com/fwlink/?linkid=871804) **Get-AdminPowerAppsUserDetails**-funktiolla:

~~~~
Add-PowerAppsAccount
$userId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
Get-AdminPowerAppsUserDetails -WriteToFile -OutputFilePath "UserDetails.json" -UserPrincipalName foobar@microsoft.com
~~~~

## <a name="step-10-export-personal-data-contained-for-a-user-stored-gateway-or-in-the-users-gateway-permissions"></a>Vaihe 10: vie käyttäjän tallentaman yhdyskäytävän tai käyttäjän yhdyskäytävän oikeuksiin sisältyvät henkilötiedot

### <a name="powerapps-portal"></a>PowerApps-portaali
Käyttäjät voivat viedä yhdyskäytäväpalveluun tallennetut henkilötiedot [PowerApps-portaalista](https://web.powerapps.com) seuraavasti:

1. Valitse [PowerApps-portaalissa](https://web.powerapps.com) vuokraajasi oletusympäristössä **Yhdyskäytävät** ja sitten **Tiedot** kaikkien niiden yhdyskäytävien kohdalla, joihin sinulla on käyttöoikeus.

    ![Yhdyskäytävän saapumissivu](./media/powerapps-gdpr-export-dsr/gateway-select-details.png)

2. Jos **Tiedot**-sivulla yhdyskäytävän tiedoissa on henkilötietoja, kopioi tiedot ja liitä ne tiedostojen muokkausohjelmaan, kuten Microsoft Wordiin.

    ![Yhdyskäytävän tiedot](./media/powerapps-gdpr-export-dsr/gateway-details-drillin.png)

3. Valitse **Jaa**, kopioi sivun sisältö ja liitä se tiedostojen muokkausohjelmaan, kuten Microsoft Wordiin.

    ![Yhdyskäytävän tiedot](./media/powerapps-gdpr-export-dsr/gateway-details-share.png)

### <a name="gateway-powershell-cmdlets"></a>Yhdyskäytävän PowerShell-cmdlet-komennot
On olemassa myös PowerShell-cmdlet-komentoja, joiden avulla voit hakea, hallita ja poistaa henkilökohtaisia yhdyskäytäviäsi. Katso lisätietoja ohjeaiheesta [Paikalliset yhdyskäytävän cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=872238).

### <a name="administrators"></a>Järjestelmänvalvojat
Artikkelin [Tutustu Microsoft PowerAppsin paikallisiin tietoyhdyskäytäviin](https://docs.microsoft.com/powerapps/maker/canvas-apps/gateway-reference#tenant-level-administration) osassa **Vuokraajan hallinta** on ohjeet yhdyskäytävien hallintaan organisaatiossasi.

## <a name="step-11-export-the-users-personal-data-in-microsoft-flow"></a>Vaihe 11: vie käyttäjän henkilötiedot Microsoft Flow -palvelusta
PowerApps-käyttöoikeudet sisältävät aina Microsoft Flow -ominaisuudet. Sen lisäksi, että Microsoft Flow sisältyy PowerAppsin käyttöoikeuksiin, se on saatavilla erillisenä palvelunakin. Saat lisätietoja Microsoft Flow -palvelua käyttäneiden käyttäjien DSR-pyyntöihin vastaamisesta ohjeartikkelista [GPDR DSR:ien suorittaminen Microsoft Flow’n asiakastiedoille](https://go.microsoft.com/fwlink/?linkid=872250).

> [!IMPORTANT]
>  Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjien puolesta.
>
>

## <a name="step-12-export-the-users-personal-data-in-cds-for-apps-instances"></a>Vaihe 12: vie käyttäjän henkilötiedot Sovellusten CDS -esiintymistä
Tietyt PowerAppsin käyttöoikeudet sallivat organisaation käyttäjien luoda Sovellusten CDS -esiintymiä sekä luoda ja rakentaa sovelluksia Sovellusten CDS -palveluun. Tämä on mahdollista esimerkiksi maksuttomalla PowerAppsin yhteisön palvelupaketilla, jolla käyttäjät voivat kokeilla Sovellusten CDS -palvelua erillisessä ympäristössä. Voit tarkastella kuhunkin PowerApps-käyttöoikeuteen sisältyviä Sovellusten CDS -ominaisuuksia [PowerAppsin hinnoittelusivulla](https://powerapps.microsoft.com/pricing).

Saat lisätietoja CDC for Appsia käyttävien käyttäjien DSR-pyyntöihin vastaamisesta ohjeartikkelista [DSR:ien suorittaminen CDC for Appsin asiakastiedoille](common-data-service-gdpr-dsr-guide.md).

> [!IMPORTANT]
>  Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjien puolesta.
>
>
