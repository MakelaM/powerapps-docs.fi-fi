---
title: Asiakastietojen poistamiseen liittyviin DSR-pyyntöihin vastaaminen | Microsoft Docs
description: Ohjeet PowerApps-asiakastietojen poistamiseen liittyviin DSR-pyyntöihin vastaamiseen.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 05/23/2018
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 5f27622e7d2021b095452ed7887fe5e979cbc81d
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42848548"
---
# <a name="responding-to-data-subject-rights-dsr-requests-to-delete-powerapps-customer-data"></a>PowerApps-asiakastietojen poistamiseen liittyviin DSR-pyyntöihin vastaaminen

Käyttäjän oikeus tietojensa poistamiseen organisaation asiakastiedoista on Euroopan Unionin (EU) yleisen tietosuoja-asetuksen (GDPR) keskeisimpiä oikeuksia. Henkilötietojen poistaminen käsittää järjestelmän luomien lokien poistamisen, mutta ei valvontalokitietoja.

PowerApps tarjoaa käyttäjille mahdollisuuden luoda toimialakohtaisia sovelluksia, jotka ovat tärkeä osa organisaation päivittäistä toimintaa. Kun käyttäjä poistuu organisaatiosi palveluksesta, sinun täytyy tarkistaa tiedot manuaalisesti ja päättää, täytyykö tietyt tiedot ja hänen luomansa resurssit poistaa. Muut henkilökohtaiset tiedot poistetaan automaattisesti, kun käyttäjän tili poistetaan Microsoft Azure Active Directorysta.

Tässä on erittely siitä, mitä henkilötietoja poistetaan automaattisesti ja mitkä tiedot vaativat manuaalisen tarkistuksen ja poistamisen:

Edellyttää manuaalisen tarkistuksen ja poistamisen |   Poistetaan automaattisesti, kun käyttäjä poistetaan Azure Active Directorysta
--- | ---
Ympäristö\** | Yhdyskäytävä
Ympäristön käyttöoikeudet\*** | Yhdyskäytävien käyttöoikeudet
Kangas-sovellus\** | PowerApps-ilmoitukset
Kangas-sovelluksen käyttöoikeudet | PowerApps-käyttäjäasetukset
Yhteys\** | PowerApps-käyttäjäsovellusten asetukset
Yhteyksien käyttöoikeudet |
Mukautettu yhdistin\** |
Mukautettujen yhdistimien käyttöoikeudet |  

\** Kukin näistä resursseista sisältää ”tekijä”- ja ”muokannut”-tietueet, jotka sisältävät henkilökohtaisia tietoja. Tietoturvasyistä nämä tietueet säilytetään, kunnes resurssi poistetaan.

\*** Niiden ympäristöjen kohdalla, jotka sisältävät Common Data Servicen (CDS) sovellusten tietokannalle, ympäristön käyttöoikeudet (eli käyttäjät, jotka on määritetty ympäristön tekijän ja järjestelmänvalvojan rooleihin) on tallennettu tietueina kyseiseen tietokantaan. Saat lisätietoja CDC for Appsia käyttäneiden käyttäjien DSR-pyyntöihin vastaamisesta ohjeartikkelista [DSR:ien suorittaminen CDC for Appsin asiakastiedoille](common-data-service-gdpr-dsr-guide.md).

Manuaalista tarkistusta edellyttäviä tietoja ja resursseja varten PowerApps tarjoaa seuraavat ominaisuudet, joiden avulla tietyn käyttäjän henkilökohtaiset tiedot voidaan (tarvittaessa) määrittää uudelleen tai poistaa:

* Sivustot: [PowerApps-sivusto](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), [PowerApps-hallintakeskus](https://admin.powerapps.com/) ja [Office 365 Service Trust Portal](https://servicetrust.microsoft.com/)

* PowerShell: PowerApps-sovellusten cmdlet-komennot [sovelluskehittäjille](https://go.microsoft.com/fwlink/?linkid=871448) sekä [järjestelmänvalvojille](https://go.microsoft.com/fwlink/?linkid=871804) ja [paikallisten yhdyskäytävien](https://go.microsoft.com/fwlink/?linkid=872238) cmdlet-komennot.

Tässä on erittely siitä, mitkä ominaisuudet ovat käytettävissä kunkin tyyppisen resurssin poistamiseen, joka voi sisältää henkilötietoja:

Henkilötietoja sisältävät resurssit | Sivuston käyttö | PowerShellin käyttö
--- | --- | ---
Ympäristö | PowerApps-hallintakeskus |  PowerAppsin cmdlet-komennot
Ympäristön oikeudet**   | PowerApps-hallintakeskus | PowerAppsin cmdlet-komennot
Kangas-sovellus  | PowerApps-hallintakeskus <br> PowerApps| PowerAppsin cmdlet-komennot
Kangas-sovelluksen käyttöoikeudet  | PowerApps-hallintakeskus | PowerAppsin cmdlet-komennot
Yhteys | | Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä
Yhteyksien oikeudet | | Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä
Mukautettu yhdistin | | Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä
Mukautettujen yhdistimien käyttöoikeudet | | Sovelluksen luoja: käytettävissä <br> Järjestelmänvalvoja: käytettävissä

\** Kun Sovellusten CDS käytössä, jos tietokanta luodaan ympäristöön, ympäristön käyttöoikeudet ja mallipohjaisten sovellusten käyttöoikeudet tallennetaan tietueina kyseisen tietokannan esiintymään. Saat lisätietoja CDC for Appsia käyttäneiden käyttäjien DSR-pyyntöihin vastaamisesta ohjeartikkelista [DSR:ien suorittaminen CDC for Appsin asiakastiedoille](common-data-service-gdpr-dsr-guide.md).

## <a name="prerequisites"></a>Edellytykset

### <a name="for-users"></a>Käyttäjille
Käyttäjät, joilla on kelvollinen PowerApps-käyttöoikeus, voivat suorittaa tässä asiakirjassa kuvattuja toimenpiteitä käyttämällä [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) tai [sovelluksen luojien PowerShellin cmdlet-komentoja](https://go.microsoft.com/fwlink/?linkid=871448).

#### <a name="unmanaged-tenant"></a>Muu kuin hallittu vuokraaja
Jos olet [muun kuin hallitun vuokraajan](https://docs.microsoft.com/azure/active-directory/domains-admin-takeover) jäsen, mikä tarkoittaa, ettei Azure AD -vuokraajallasi ei ole yleistä järjestelmänvalvojaa, pystyt edelleen poistamaan henkilökohtaiset tietosi tässä artikkelissa annettujen ohjeiden mukaisesti.  Kuitenkin koska vuokraajallasi ei ole yleistä järjestelmänvalvojaa, sinun on poistettava oma tilisi vuokraajasta alla olevan [Vaiheen 11: Poista käyttäjä Azure Active Directorysta](#step-11-delete-the-user-from-azure-active-directory) ohjeiden mukaisesti.

Voit selvittää, oletko muun kuin hallitun vuokraajan jäsen, toimimalla seuraavasti:

1. Avaa seuraava URL-osoite selaimessa ja muista korvata sähköpostiosoitteesi URL-osoitteessa: https://login.windows.net/common/userrealm/name@contoso.com?api-version=2.1

2. Jos olet **muun kuin hallitun vuokraajan** jäsen, vastauksessa näkyy `"IsViral": true`.
```
{
  ...
  "Login": "name@unmanagedcontoso.com",
  "DomainName": "unmanagedcontoso.com",
  "IsViral": true,
  ...
}
```

3. Muussa tapauksessa kuulut **hallittuun vuokraajaan**.

### <a name="for-administrators"></a>Järjestelmänvalvojille
Mikäli halutaan suorittaa tässä asiakirjassa kuvattuja järjestelmänvalvojan toimenpiteitä käyttämällä [PowerApps-hallintakeskusta](https://admin.powerapps.com/), Microsoft Flow -hallintakeskusta tai [PowerShellin cmdlet-komentoja PowerApps-järjestelmänvalvojille](https://go.microsoft.com/fwlink/?linkid=871804), tarvitaan seuraavat asiat:

* Maksullisen PowerApps-palvelupaketin 2 käyttöoikeus tai PowerApps-palvelupaketin 2 kokeiluversion käyttöoikeus. Voit rekisteröityä 30 päivän maksuttoman kokeiluversion käyttäjäksi osoitteessa [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Kokeiluversion käyttöoikeudet voi uusia, jos ne ovat vanhentuneet.

* [Office 365:n yleisen järjestelmänvalvojan](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleisen järjestelmänvalvojan](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) oikeudet ovat myös pakollisia, jos haluat tehdä hakuja toisen käyttäjän resursseihin. (Huomioi, että ympäristön järjestelmänvalvojilla on pääsy vain niihin ympäristöihin ja ympäristön resursseihin, joihin heillä on oikeudet.)

## <a name="step-1-delete-or-reassign-all-environments-created-by-the-user"></a>Vaihe 1: Poista tai määritä uudelleen kaikki käyttäjän luomat ympäristöt
Järjestelmänvalvojana tehtävänäsi on kaksi päätöstä, kun käsittelet DSR-poistopyyntöä kussakin ympäristössä, jonka käyttäjä on luonut:

1. Jos päätät, että kukaan muu organisaatiossasi ei käytä kyseistä ympäristöä, voit halutessasi poistaa ympäristön.

2. Jos päätät, että ympäristöä tarvitaan edelleen, voit halutessasi säilyttää ympäristön ja lisätä itsesi (tai jonkun toisen käyttäjän organisaatiossasi) ympäristön järjestelmänvalvojaksi.

> [!IMPORTANT]
> Ympäristön poistaminen poistaa pysyvästi kaikki ympäristön resurssit, mukaan lukien kaikki sovellukset, työnkulut, yhteydet jne. Tutustu siis ympäristön sisältöön huolella ennen sen poistamista.

### <a name="give-access-to-a-users-environments-from-the-powerapps-admin-center"></a>Anna käyttöoikeudet käyttäjän ympäristöön PowerAppsin hallintakeskuksesta käsin
Järjestelmänvalvoja voi myöntää järjestelmänvalvojan oikeudet tietyn käyttäjän luomaan ympäristöön [PowerAppsin hallintakeskuksen](https://admin.powerapps.com/) kautta seuraavasti:

1. Valitse [PowerAppsin hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi.

    ![Järjestelmänvalvojan hallintakeskuksen aloitussivu](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Jos ympäristön on luonut DSR-pyynnössä oleva käyttäjä, valitse **Suojaus** ja jatka [Ympäristöjen hallinta](environments-administration.md) -kohdassa annettujen ohjeiden mukaisesti, jotta voit antaa järjestelmänvalvojan oikeudet itsellesi tai toiselle käyttäjälle organisaatiossasi.

    ![Ympäristön suojaus](./media/powerapps-gdpr-delete-dsr/share-environment.png)

### <a name="delete-environments-created-by-a-user-from-the-powerapps-admin-center"></a>Poista käyttäjän luomat ympäristöt PowerAppsin hallintakeskuksesta käsin
Järjestelmänvalvoja voi tarkastella ja poistaa tietyn käyttäjän luomat ympäristöt [PowerAppsin hallintakeskuksesta](https://admin.powerapps.com/) käsin seuraavasti:

1. Valitse [PowerAppsin hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi.

    ![Hallintakeskuksen aloitussivu](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Jos ympäristön on luonut DSR-pyynnössä oleva käyttäjä, valitse **Poista** ja jatka sitten ohjeiden mukaan ympäristön poistamiseksi:

    ![Ympäristön poistaminen](./media/powerapps-gdpr-delete-dsr/delete-environment.png)

### <a name="give-access-to-a-users-environments-using-powershell"></a>Käyttöoikeuden myöntäminen käyttäjän ympäristöihin PowerShellin avulla
Järjestelmänvalvoja voi määrittää itselleen (tai toiselle käyttäjälle organisaatiossaan) käyttöoikeudet kaikkiin käyttäjän luomiin ympäristöihin **Set-AdminEnvironmentRoleAssignment**-toiminnon kautta kohdassa [PowerShellin cmdlet-komennot PowerAppsin järjestelmänvalvojille](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
$myUserId = $global:currentSession.UserId

#Assign yourself as an admin to each environment created by the user
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Set-AdminEnvironmentRoleAssignment -RoleName EnvironmentAdmin -PrincipalType User -PrincipalObjectId $myUserId

#Retrieve the environment role assignments to confirm
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Get-AdminEnvironmentRoleAssignment
```

> [!IMPORTANT]
> Tämä toiminto toimii vain ympäristöissä, joissa ei ole tietokannan esiintymiä Sovellusten CDS:ssä.

### <a name="delete-environments-created-by-a-user-using-powershell"></a>Poista käyttäjän luomia ympäristöjä PowerShellin avulla
 Järjestelmänvalvoja voi poistaa kaikki käyttäjän luomat ympäristöt **Remove-AdminEnvironment**-toiminnon kautta kohdassa [PowerShellin cmdlet-komennot PowerAppsin järjestelmänvalvojille](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

# Retrieve all environments created by the user and then delete them
Get-AdminEnvironment -CreatedBy $deleteDsrUserId | Remove-AdminEnvironment
```

## <a name="step-2-delete-the-users-permissions-to-all-other-environments"></a>Vaihe 2: Poista käyttäjän oikeudet kaikkiin ympäristöihin
Käyttäjille voidaan määrittää käyttöoikeudet (kuten ympäristön järjestelmänvalvojan ja ympäristön tekijän oikeudet) ympäristössä, joka on tallennettu PowerApps-palveluun ”roolimäärityksenä”.
Kun Sovellusten CDS on käytössä, jos tietokanta luodaan ympäristöön, nämä ”roolimääritykset” tallennetaan tietueina kyseisen tietokannan esiintymään.
Lisätietoja on [Ympäristöjen hallinta](environments-administration.md) -kohdassa.

### <a name="for-environments-without-a-cds-for-apps-database"></a>Ympäristöt, joissa ei ole Sovellusten CDS -tietokantaa

#### <a name="powerapps-admin-center"></a>PowerApps-hallintakeskus
Järjestelmänvalvoja voi poistaa käyttäjän ympäristön käyttöoikeudet alkaen [PowerAppsin hallintakeskuksesta](https://admin.powerapps.com/) seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi.

    Sinun on oltava [Office 365:n yleinen järjestelmänvalvoja](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleinen järjestelmänvalvoja](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), jotta voit tarkastella kaikkia ympäristöjä, jotka on luotu organisaation sisällä.

    ![Hallintakeskuksen aloitussivu](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Valitse **Suojaus**.

    Jos ympäristössä ei ole Sovellusten CDS -tietokantaa, näkyviin tulee osa, jossa ovat **Ympäristön roolit.**

3. Valitse **Ympäristön roolit** -kohdassa sekä **Ympäristön järjestelmänvalvoja** että **Ympäristön tekijä** erikseen ja etsi käyttäjän nimi etsintäpalkin avulla.

    ![Ympäristöroolit-sivu](./media/powerapps-gdpr-delete-dsr/admin-environment-role-share-page.png)

5.  Jos käyttäjällä on käyttöoikeus jompaankumpaan rooliin, poista **Käyttäjät**-näytöllä hänen käyttöoikeutensa ja valitse **Tallenna**.

#### <a name="powershell"></a>PowerShell
Järjestelmänvalvoja voi poistaa kaikki käyttäjän ympäristön roolimääritykset kaikissa ympäristöissä ilman Sovellusten CDS -tietokantaa käyttämällä **Remove-AdminEnvironmentRoleAssignment**-toimintoa kohdassa [PowerShellin cmdlet-komennot PowerApps-järjestelmänvalvojille](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all environment role assignments for the user for environments without a CDS for Apps instance and delete them
Get-AdminEnvironmentRoleAssignment -UserId $deleteDsrUserId | Remove-AdminEnvironmentRoleAssignment
```

> [!IMPORTANT]
> Tämä toiminto toimii vain ympäristöissä, joissa ei ole Sovellusten CDS -tietokannan esiintymiä.

### <a name="for-environments-with-a-cds-for-apps-database"></a>Ympäristöt, joissa ON Sovellusten CDS -tietokanta
Kun Sovellusten CDS on käytössä, jos tietokanta luodaan ympäristöön, nämä ”roolimääritykset” tallennetaan tietueina kyseisen tietokannan esiintymään. Katso seuraavasta dokumentaatiosta, miten henkilötiedot poistetaan tietokannan esiintymästä Sovellusten CDS:ssä: Common Data Service -käyttäjän henkilötietojen poistaminen

## <a name="step-3-delete-or-reassign-all-canvas-apps-owned-by-a-user"></a>Vaihe 3: Poista tai siirrä kaikki käyttäjän omistamat Kangas-sovellukset

### <a name="reassign-a-users-canvas-apps-using-the-powerapps-admin-powershell-cmdlets"></a>Uudelleenmääritä käyttäjän kangassovellukset PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komentojen avulla
Jos järjestelmänvalvoja päättää olla poistamatta käyttäjän kangassovelluksia, hän voi uudelleenmäärittää käyttäjän omistamat sovellukset **Set-AdminAppOwner**-toiminnolla kohdassa [PowerAppsin järjestelmänvalvojan PowerShellin cdmlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"
$newAppOwnerUserId = "72c272b8-14c3-4f7a-95f7-a76f65c9ccd8"

#find all apps owned by the DSR user and assigns them a new owner
Get-AdminApp -Owner $deleteDsrUserId | Set-AdminAppOwner -AppOwner $newAppOwnerUserId
```

### <a name="delete-a-users-canvas-app-using-the-powerapps-site"></a>Poista käyttäjän kangassovellus PowerApps-sivuston avulla
Käyttäjä voi poistaa sovelluksen [PowerApps-sivustolta](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Täydelliset ohjeet sovelluksen poistamiseen näet Sovelluksen poistaminen -kohdassa.

### <a name="delete-a-users-canvas-app-using-the-powerapps-admin-center"></a>Poista käyttäjän kangassovellus PowerApps-hallintakeskuksen avulla
Järjestelmänvalvoja voi poistaa käyttäjän luomat sovellukset alkaen [PowerAppsin hallintakeskuksesta](https://admin.powerapps.com/) seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi.

    Sinun on oltava [Office 365:n yleinen järjestelmänvalvoja](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleinen järjestelmänvalvoja](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), jotta voit tarkastella kaikkia ympäristöjä, jotka on luotu organisaation sisällä.

    ![Hallintakeskuksen aloitussivu](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Valitse **Resurssit** > **Sovellukset**.

3. Hae etsintäpalkin avulla käyttäjän nimi, jolla saadaan näkyviin sovellukset, jotka kyseinen käyttäjä on luonut tähän ympäristöön:

    ![Hae sovelluksia](./media/powerapps-gdpr-delete-dsr/search-apps.png)

4. Valitse **Tiedot** käyttäjän omistaman jokaisen sovelluksen kohdalla:

    ![Valitse sovelluksen tiedot](./media/powerapps-gdpr-delete-dsr/select-app-details.png)

5. Valitse **Poista** kunkin sovelluksen poistamiseksi:

### <a name="delete-a-users-canvas-app-using-the-powerapps-admin-powershell-cmdlets"></a>Poista käyttäjän kangassovellus PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komentojen avulla
Jos järjestelmänvalvoja päättää poistaa kaikki käyttäjän omistamat kangassovellukset, hän voi tehdä niin käyttämällä **Remove-AdminApp**-toimintoa kohdassa [PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all apps owned by the DSR user and deletes them
Get-AdminApp -Owner "0ecb1fcc-6782-4e46-a4c4-738c1d3accea" | Remove-AdminApp
```

## <a name="step-4-delete-the-users-permissions-to-canvas-apps"></a>Vaihe 4: Poista käyttäjän oikeudet kangassovelluksiin
Aina, kun sovellus on jaettu käyttäjän kanssa, PowerApps tallentaa tietueen nimeltä ”roolimääritys”, joka kuvaa käyttäjän käyttöoikeuksia (CanEdit tai CanUse) sovellukseen. Lisätietoja saat kohdasta Sovelluksen jakaminen.

> [!NOTE]
> Sovelluksen roolimääritykset poistetaan, kun sovellus poistetaan.

> [!NOTE]
> Sovelluksen omistajan roolimääritys voidaan poistaa vain määrittämällä sovellukselle uusi omistaja.

### <a name="powerapps-admin-center"></a>PowerApps-hallintakeskus
Järjestelmänvalvoja voi poistaa käyttäjän sovellusroolimääritykset alkaen [PowerAppsin hallintakeskuksesta](https://admin.powerapps.com/) seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com/) kukin ympäristö organisaatiossasi.

    Sinun on oltava [Office 365:n yleinen järjestelmänvalvoja](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleinen järjestelmänvalvoja](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal), jotta voit tarkastella kaikkia ympäristöjä, jotka on luotu organisaation sisällä.

    ![Hallintakeskuksen aloitussivu](./media/powerapps-gdpr-delete-dsr/admin-center-landing.png)

2. Valitse kussakin ympäristössä **Resurssit** > **Sovellukset**.

3. Valitse **Jaa** kullekin ympäristössä olevalle sovellukselle:

    ![Valitse sovelluksen jakaminen](./media/powerapps-gdpr-delete-dsr/select-admin-share-nofilter.png)

4. Jos käyttäjällä on käyttöoikeus sovellukseen, poista sovelluksen **Jaa**-näytöllä hänen käyttöoikeutensa ja valitse **Tallenna**.

    ![Järjestelmänvalvojan sovelluksen jakaminen -sivu](./media/powerapps-gdpr-delete-dsr/admin-share-page.png)

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvoja voi poistaa kaikki käyttäjän kangassovellusten roolimääritykset käyttämällä **Remove-AdminAppRoleAssignmnet**-toimintoa kohdassa [PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#find all app role assignments for the DSR user and deletes them
Get-AdminAppRoleAssignment -UserId $deleteDsrUserId | Remove-AdminAppRoleAssignment
```

## <a name="step-5-delete-connections-created-by-a-user"></a>Vaihe 5: Poista käyttäjän luomat yhteydet
Yhteyksiä käytetään yhdistimien kanssa muodostettaessa yhteyksiä muihin ohjelmointirajapintoihin ja SaaS-järjestelmiin.  Yhteyksien sisällä on viittauksia käyttäjään, joka ne on luonut, ja sen vuoksi ne voidaan poistaa, jotta saadaan poistettua mahdolliset viittaukset käyttäjään.

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjä voi poistaa kaikki yhteytensä käyttämällä Remove-Connection-toimintoa kohdassa [Sovellusten luojien PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all connections for the calling user and deletes them
Get-Connection | Remove-Connection
```

### <a name="powershell-cmdlets-for-powerapps-administrators"></a>PowerShellin cmdlet-komennot PowerAppsin järjestelmänvalvojille
Järjestelmänvalvoja voi poistaa kaikki käyttäjän yhteydet käyttämällä **Remove-AdminConnection**-funktiota kohdassa [PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all connections for the DSR user and deletes them
Get-AdminConnection -CreatedBy $deleteDsrUserId | Remove-AdminConnection
```

## <a name="step-6-delete-the-users-permissions-to-shared-connections"></a>Vaihe 6: Poista käyttäjän oikeudet jaettuihin yhteyksiin

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjä voi poistaa kaikki yhteysroolimäärityksensä jaetuille yhteyksille käyttämällä Remove-ConnectionRoleAssignment-toimintoa kohdassa [Sovellusten luojien PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all connection role assignments for the calling users and deletes them
Get-ConnectionRoleAssignment | Remove-ConnectionRoleAssignment
```
> [!NOTE]
> Omistajan roolimäärityksiä ei voi poistaa poistamatta yhteysresurssia.

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvoja voi poistaa kaikki käyttäjän yhteysroolimääritykset käyttämällä **Remove-AdminConnectionRoleAssignment**-funktiota kohdassa [PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all connection role assignments for the DSR user and deletes them
Get-AdminConnectionRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectionRoleAssignment
```

## <a name="step-7-delete-custom-connectors-created-by-the-user"></a>Vaihe 7: Poista käyttäjän luomat mukautetut yhdistimet
Mukautetut yhdistimet täydentävät valmiina tulevia yhdistimiä ja mahdollistavat yhdistämisen muihin ohjelmointirajapintoihin, SaaS-järjestelmiin ja asiakkaan kehittämiin järjestelmiin. Haluat ehkä siirtää Mukautetun yhdistimen omistajuuden muille käyttäjille organisaatiossa tai poistaa Mukautetun yhdistimen.

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjä voi poistaa kaikki mukautetut yhdistimensä käyttämällä Remove-Connector-toimintoa kohdassa [Sovellusten luojien PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all custom connectors for the calling user and deletes them
Get-Connector -FilterNonCustomConnectors | Remove-Connector
```

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvoja voi poistaa kaikki käyttäjän luomat mukautetut liittimet käyttämällä **Remove-AdminConnector**-funktiota kohdassa [PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all custom connectors created by the DSR user and deletes them
Get-AdminConnector -CreatedBy $deleteDsrUserId | Remove-AdminConnector
```

## <a name="step-8-delete-the-users-permissions-to-shared-custom-connectors"></a>Vaihe 8: Poista käyttäjän oikeudet jaettuihin mukautettuihin yhdistimiin

### <a name="powershell-cmdlets-for-app-creators"></a>Sovellusten luojien PowerShellin cmdlet-komennot
Käyttäjä voi poistaa kaikki yhdistinroolimäärityksensä jaetuille mukautetuille yhdistimille käyttämällä Remove-ConnectorRoleAssignment-toimintoa kohdassa [Sovellusten luojien PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871448):

```
Add-PowerAppsAccount

#Retrieves all connector role assignments for the calling users and deletes them
Get-ConnectorRoleAssignment | Remove-ConnectorRoleAssignment
```

> [!NOTE]
> Omistajan roolimäärityksiä ei voi poistaa poistamatta yhteysresurssia.

### <a name="powershell-cmdlets-for-admins"></a>Järjestelmänvalvojien PowerShellin cmdlet-komennot
Järjestelmänvalvoja voi poistaa kaikki käyttäjän mukautetut liittimen roolimääritykset käyttämällä **Remove-AdminConnectorRoleAssignment**-funktiota kohdassa [PowerAppsin järjestelmänvalvojan PowerShellin cmdlet-komennot](https://go.microsoft.com/fwlink/?linkid=871804):

```
Add-PowerAppsAccount
$deleteDsrUserId = "0ecb1fcc-6782-4e46-a4c4-738c1d3accea"

#Retrieves all custom connector role assignments for the DSR user and deletes them
Get-AdminConnectorRoleAssignment -PrincipalObjectId $deleteDsrUserId | Remove-AdminConnectorRoleAssignment
```

## <a name="step-9-delete-the-users-personal-data-in-microsoft-flow"></a>Vaihe 9: Poista käyttäjän henkilötiedot Microsoft Flow’sta
PowerApps-käyttöoikeudet sisältävät aina Microsoft Flow -ominaisuudet. Sen lisäksi, että Microsoft Flow sisältyy PowerAppsin käyttöoikeuksiin, se on saatavilla erillisenä palvelunakin. Saat lisätietoja Microsoft Flow -palvelua käyttäneiden käyttäjien DSR-pyyntöihin vastaamisesta ohjeartikkelista [GPDR DSR:ien suorittaminen Microsoft Flow’n asiakastiedoille](https://go.microsoft.com/fwlink/?linkid=872250).

> [!IMPORTANT]
> Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjän puolesta.

## <a name="step-10-delete-the-users-personal-data-in-instances-of-cds-for-apps"></a>Vaihe 10: Poista käyttäjän henkilötiedot Sovellusten CDS:n esiintymistä
Tietyt PowerApps-käyttöoikeudet, esimerkiksi PowerAppsin yhteisön palvelupaketti, antavat organisaatiosi käyttäjille mahdollisuuden luoda sovellusten CDS:n esiintymiä sekä luoda ja kehittää sovelluksia sovellusten CDS:n avulla. PowerAppsin yhteisön palvelupaketti on maksuton käyttöoikeus, jolla käyttäjät voivat kokeilla sovellusten CDS:ää yksittäisessä ympäristössä. PowerAppsin hinnoittelusivulta saat lisätietoa kapasiteeteista, jotka kukin PowerApps-käyttöoikeus sisältää.

Saat lisätietoja CDC for Appsia käyttäneiden käyttäjien DSR-pyyntöihin vastaamisesta ohjeartikkelista [DSR:ien suorittaminen CDC for Appsin asiakastiedoille](common-data-service-gdpr-dsr-guide.md).

> [!IMPORTANT]
> Suosittelemme, että järjestelmänvalvoja suorittaa tämän vaiheen PowerApps-käyttäjän puolesta.

## <a name="step-11-delete-the-user-from-azure-active-directory"></a>Vaihe 11: Poista käyttäjä Azure Active Directorysta
Kun edellä olevat vaiheet on suoritettu, viimeinen vaihe on poistaa käyttäjän Azure Active Directory -tili.

### <a name="managed-tenant"></a>Hallittu vuokraaja
Hallitun Azure AD -vuokraajan järjestelmänvalvojana voit poistaa käyttäjän tilin [Office 365 Service Trust Portalissa](https://servicetrust.microsoft.com/ViewPage/GDPRDSR) olevan Azuren rekisteröityjen tietopyyntöjen GDPR -dokumentaation ohjeiden mukaisesti.

### <a name="unmanaged-tenant"></a>Muu kuin hallittu vuokraaja
Jos olet muun kuin hallitun vuokraajan jäsen, sinun on poistettava tilisi Azure AD -vuokraajasta noudattamalla seuraavia ohjeita:

> [!NOTE]
> Tarkista edellä olevan [Muu kuin hallittu vuokraaja -osion](#unmanaged-tenant) ohjeiden mukaisesti, oletko hallitun vai muun vuokraajan jäsen.

1. Siirry [työpaikan ja koulun tietosuojasivulle](https://go.microsoft.com/fwlink/?linkid=87312) ja kirjaudu sisään Azure AD -tililläsi.

2. Valitse **Sulje tili** ja poista tilisi Azure AD -vuokraajasta ohjeiden mukaisesti.

    ![Valitse sovelluksen jakaminen](./media/powerapps-gdpr-delete-dsr/close-account.png)
