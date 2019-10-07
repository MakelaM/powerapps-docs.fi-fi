---
title: Pohjaan perustuvan sovelluksen jakaminen | Microsoft Docs
description: Jaa pohjaan perustuva sovelluksesi antamalla käyttäjille käyttöoikeus sen suorittamiseen tai muokkaamiseen
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/09/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: cb8c77b60caa1f1ddf07e12f50e3cd52df764627
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995614"
---
# <a name="share-a-canvas-app-in-powerapps"></a>Pohjaan perustuvan sovelluksen jakaminen PowerAppsissa

Kun olet luonut pohjaan perustuvan sovelluksen, joka vastaa liiketoiminnan tarpeiseen, määritä organisaatiosi käyttäjät, jotka voivat suorittaa sovelluksen, muokata sitä ja jopa jakaa sen uudelleen. Määrittä kukin käyttäjä nimen perusteella tai määritä käyttöoikeusryhmä Azure Active Directoryssä. Jos kaikki hyötyisivät sovelluksestasi, määritä, että koko organisaatio voi suorittaa sen.

> [!IMPORTANT]
> Jotta jaettu sovellus toimisi odotetulla tavalla, sinun on myös hallittava tieto lähteen tai sovelluksen pohjana olevien lähteiden käyttö oikeuksia, kuten [Common Data Service](#common-data-service) tai [Exceliä](share-app-data.md). Voit myös joutua jakamaan sovelluksen perustana toimivia [muita resursseja](share-app-resources.md), kuten työnkulkuja, yhdyskäytäviä tai yhteyksiä.

## <a name="prerequisites"></a>Edellytykset

Ennen kuin jaat sovelluksen, tallenna sen pilvipalveluun (ei paikallisesti) ja julkaise se sitten.

- Anna sovelluksellesi kuvaava nimi ja selkeä kuvaus niin, että käyttäjät tietävät, mitä sovellus tekee ja se on helposti löydettävissä luettelossa. Valitse PowerApps Studiossa **Tiedosto**-valikko, valitse valikosta **Sovellusasetukset**, määritä nimi ja kirjoita tai liitä kuvaus.

- Aina, kun olet tehnyt muutoksia, sinun täytyy tallentaa ja julkaista sovellus uudelleen, jos haluat, että muut näkevät muutoksesi.

## <a name="share-an-app"></a>Sovelluksen jakaminen

1. [Kirjaudu](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerAppsiin ja valitse **Sovellukset** lähellä vasenta reunaa.

    ![Näytä sovellusluettelo](./media/share-app/file-apps.png)

1. Valitse sovellus, jonka haluat vaihtaa, valitsemalla sen kuvake.

    ![Valitse sovellus](./media/share-app/select-app.png)

1. Valitse bannerissa **jako**.

    ![Avaa jakonäyttö](./media/share-app/banner-share.png)

1. Määritä nimen tai aliaksen mukaan Azure Active Directory käyttäjät tai käyttö oikeus ryhmät, joiden kanssa haluat vaihtaa sovelluksen.

    - Jos haluat sallia koko organisaation suorittaa sovelluksen (mutta ei muokata tai jakaa sitä), kirjoita **Kaikki** jako-paneeliin.
    - Voit jakaa sovelluksen, jossa on luettelo aliaksista, kutsumanimistä tai niiden yhdistelmästä (esimerkiksi **Jane doe &lt; @ no__t-2 >** ), jos Kohteet erotetaan puoli pisteillä. Jos useammalla kuin yhdellä henkilöllä on sama nimi mutta eri aliakset, ensimmäinen löydetty henkilö lisätään listaan. Työkalu Vihje tulee näkyviin, jos nimellä tai aliaksella on jo käyttö oikeus tai sitä ei voi selvittää. 

    ![Määritä käyttäjät ja osaomistajat](./media/share-app/share-everyone.png)

    > [!NOTE]
    > Et voi jaella sovellusta organisaatiosi jakelu ryhmän tai organisaatiosi ulkopuolisen käyttäjän tai ryhmän kanssa.

1. Jos haluat sallia niiden, joiden kanssa jaat sovelluksen, muokata ja jakaa sitä (sen lisäksi, että se on käynnissä), valitse **toinen omistaja-** valinta ruutu.

    Et voi myöntää **osaomistajan** käyttö oikeutta käyttö oikeus ryhmälle, jos [loit sovelluksen ratkaisun sisältä](add-app-solution.md).

    > [!NOTE]
    > Käyttö oikeuksista riippumatta kaksi käyttäjää ei voi muokata sovellusta yhtä aikaa. Jos yksi henkilö Avaa sovelluksen muokkaamista varten, muut käyttäjät voivat suorittaa sen, mutta eivät muokata sitä.

1. Jos sovelluksesi muodostaa yhteyden tietoihin, joille käyttäjillä on käyttö oikeudet, määritä ne.

    Sovelluksesi voi esimerkiksi muodostaa yhteyden entiteettiin Common Data Service-tieto kannassa. Kun jaat tällaisen sovelluksen, jakamis paneeli kehottaa sinua hallitsemaan kyseisen entiteetin suojausta.

    > [!div class="mx-imgBorder"]
    > ![Määritä käyttö oikeus rooli @ no__t-1

    Lisä tietoja entiteetin suoja uksen Hallin nasta on kohdassa [entiteetin käyttö oikeuksien hallinta](share-app.md#manage-entity-permissions) myöhemmin tässä ohje aiheessa.

1. Jos haluat auttaa käyttäjiä löytämään sovelluksesi, valitse **Lähetä Sähkö posti kutsu uusille käyttäjille** -valinta ruutu.

1. Valitse jako-paneelin alareunasta **jako**.

    Kaikki, joiden kanssa olet jakanut sovelluksen, voivat suorittaa sen PowerApps Mobilessa mobiililaitteessa tai [Dynamics 365](https://home.dynamics.com) appsourcessa selaimessa. Apuomistajat voivat muokata ja vaihtaa sovellusta [Powerappsissa](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    Jos lähetit Sähkö posti kutsun, kaikki, joiden kanssa olet jakanut sovelluksen, voivat suorittaa sen valitsemalla linkin kutsussa.

    - Jos käyttäjä valitsee linkin mobiililaitteessa, sovellus avautuu PowerApps Mobilessa.
    - Jos käyttäjä valitsee linkin pöytä tieto koneessa, sovellus avautuu selaimessa.

    Kutsun vastaanottavat apuomistajat saavat toisen linkin, joka avaa sovelluksen muokattavaksi PowerApps Studio.

Voit muuttaa käyttäjän tai käyttö oikeus ryhmän käyttö oikeuksia valitsemalla hänen nimensä ja suorittamalla jommankumman seuraavista vaiheista:

- Jos haluat sallia muiden omistajien suorittaa sovelluksen, mutta ei enää muokata tai vaihtaa sitä, tyhjennä **osaomistaja-** valinta ruutu.
- Jos haluat lopettaa sovelluksen jakamisen kyseisen käyttäjän tai ryhmän kanssa, valitse Poista (x)-kuvake.

## <a name="security-group-considerations"></a>Käyttöoikeusryhmän huomioon otettavia seikkoja

- Jos jaat sovelluksen käyttöoikeusryhmän kanssa, kaikki ryhmään kuuluvat ja siihen myöhemmin liittyvät jäsenet saavat käyttöoikeudet, jotka olet kyseiselle ryhmälle määrittänyt. Kaikki ryhmästä poistuvat menettävät käyttöoikeutensa, paitsi jos he kuuluvat toiseen ryhmään, jolla on käyttöoikeudet, tai annat heille käyttöluvan yksittäisinä käyttäjinä.

- Jokaisella käyttöoikeusryhmän jäsenellä on samat käyttöoikeudet sovellukseen kuin ryhmällä yleensä. Voit kuitenkin halutessasi määrittää yhdelle tai useammalle ryhmän jäsenelle laajemmat käyttöoikeudet. Voit esimerkiksi antaa käyttö oikeus ryhmälle käyttö oikeuden sovelluksen suorittamiseen, mutta voit myös antaa käyttäjälle B, joka kuuluu kyseiseen ryhmään, jonka **omistajan** käyttö oikeus on. Jokainen käyttöoikeusryhmän jäsen voi suorittaa sovelluksen, mutta vain käyttäjä B voi muokata sitä. Jos annat käyttö oikeus ryhmälle **osaomistaja-** käyttö oikeuden ja käyttäjän B-käyttö oikeuden sovelluksen suorittamiseen, kyseinen käyttäjä voi edelleen muokata sovellusta.

## <a name="manage-entity-permissions"></a>Entiteetin käyttöoikeuksien hallinta

### <a name="common-data-service"></a>Common Data Service

Jos luot Common Data Service perustuvan sovelluksen, sinun on myös varmistettava, että käyttäjillä, joiden kanssa jaat sovelluksen, on asianmukaiset käyttö oikeudet entiteettiin tai entiteetteihin, joihin sovellus vetoaa. Erityisesti kyseisten käyttäjien on kuuluttava käyttö oikeus rooliin, joka voi suorittaa tehtäviä, kuten luoda, lukea, kirjoittaa ja poistaa olennaisia tietueita. Monissa tapa uksissa sinun kannattaa luoda vähintään yksi mukautettu käyttö oikeus rooli käyttäen tarkkoja käyttö oikeuksia, jotka käyttäjien on suoritettava sovellus. Voit sitten tarvittaessa antaa kullekin käyttäjälle roolin.

> [!NOTE]
> Tätä kirjoitettaessa voit antaa käyttö oikeus rooleja yksittäiselle käyttäjälle ja käyttö oikeus ryhmälle Azure Active Directory, mutta et Office-ryhmään.

#### <a name="prerequisite"></a>Edellytys

Jotta voit määrittää roolin, sinulla on **oltava järjestelmänvalvojan oikeudet Common Data Service** -tieto kantaan.

#### <a name="assign-a-security-group-in-azure-ad-to-a-role"></a>Määritä käyttö oikeus ryhmä Azure AD:ssä rooliin

1. Valitse jako-paneelissa Määritä käyttö **oikeus rooli** **tietojen käyttö oikeudet**-kohdassa.

1. Valitse Common Data Service rooli tai roolit, jotka haluat määrittää käyttäjälle tai käyttö oikeus ryhmälle Azure AD:ssä, jonka kanssa haluat jakaa sovelluksen.
     > [!div class="mx-imgBorder"] 
     > ![Käyttö oikeus rooli luetteloiden](media/share-app/cds-assign-security-role-list.png "käyttö oikeus roolien luettelot")

### <a name="common-data-service-previous-version"></a>Common Data Service (aiempi versio)

Kun jaat sovelluksen, joka perustuu Common Data Service vanhempaan versioon, sinun on jaettava palvelun suorituksenaikainen käyttö oikeus erikseen. Jos sinulla ei ole käyttö oikeutta tähän, tutustu ympäristön järjestelmänvalvojaan.

## <a name="share-with-guests"></a>Kerro vieraille

> [!IMPORTANT]
> - Esikatselutoimintoja ei ole tarkoitettu tuotantokäyttöön ja ne saattavat käyttää rajoitettua toiminnallisuutta. Nämä ominaisuudet ovat käytettävissä ennen virallista julkaisua, jotta asiakkaat voivat saada pääsyn etukäteen ja antaa palautetta. 
> - Esikatseluosominaisuudet tukevat Microsoftin tukea rajoitetusti, ja ne saattavat olla käytettävissä vain valituilla maantieteellisillä alueilla. 

Powerappsin pohjaan liittyvät sovellukset voidaan jakaa Azure Active Directory vuokra ajan vierailevien käyttäjien kanssa. Tämän avulla ulkoiset liike kumppanit, alihankkijat ja kolmannet osapuolet voivat suorittaa yrityksesi kangas sovelluksia. 

> [!NOTE]
> Vieraille voidaan määrittää vain **käyttäjä** rooli, ei **osaomistaja-** roolia, heidän kanssaan jaetuille sovelluksille.

### <a name="prerequisites"></a>Edellytykset
- Ota käyttöön Azure Active Directory (Azure AD) vuokraajaan B2B-ulkoinen yhteistyö. Lisätietoja: [Ota käyttöön B2B-ulkoinen yhteistyö ja hallitse, ketkä voivat kutsua vieraita](/azure/active-directory/b2b/delegate-invitations)
    - Ota käyttöön B2B-ulkoinen yhteistyö on oletus arvon mukaan käytössä. Vuokra ajan järjestelmänvalvoja voi kuitenkin muuttaa asetuksia.  Lisä tietoja Azure AD B2B-artikkelista on Ohje aiheessa [mikä on vieras käyttö oikeus Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) -sovelluksessa?  
- Käyttö oikeus tiliin, joka voi lisätä vieras käyttäjiä Azure AD-vuokraajaan. Järjestelmänvalvojat ja käyttäjät, joilla on vieras-Invaiter-rooli, voivat lisätä vieraita vuokraajaan.   
- Vieras käyttäjällä on oltava PowerApps-käyttö oikeus, joka on määritetty jollakin seuraavista vuokralaisista:
    - Jaettavan sovelluksen isännöivä vuokraaja.
    - Vieras käyttäjän koti vuokra ajan.

### <a name="steps-to-grant-guest-access"></a>Vieras käyttö oikeuksien myöntämisen vaiheet
1. Valitse **Uusi vieras käyttäjä** , jos haluat lisätä vieras käyttäjiä Azure AD:ssä. Lisätietoja: [Pikaopas: Lisää uusi vieras käyttäjä Azure AD:ssä @ no__t-0.
    > [!div class="mx-imgBorder"] 
    > ![Lisää vieras AZUREN AD](media/share-app/guest_access_doc_1.png "Add-vieraana Azure") AD:ssä
2. Jos vierailevassa käyttäjällä ei vielä ole käyttö oikeutta koti vuokraajaan, Anna vieras käyttäjälle käyttö oikeus.
   - Lisä tietoja vieras käyttäjien määrittämisestä osoitteesta admin.microsoft.com on kohdassa [käyttö oikeuksien määritteleminen yhdelle käyttäjälle](/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
   - Lisä tietoja vieras käyttäjien määrittämisestä osoitteesta portal.azure.com on kohdassa [käyttö oikeuksien määritteleminen tai poistaminen](/azure/active-directory/fundamentals/license-users-groups).
 
   > [!IMPORTANT]
   > Saatat joutua poistamaan Microsoft 365 hallinta keskuksen esikatselun käytöstä, jotta voit antaa käyttö oikeuden vieras-kohteelle. 

3. Jako kangas sovellus. 
    1. Kirjaudu sisään https://make.powerapps.com  
    2. Siirry **sovelluksiin**, valitse pohjaan perustuva sovellus ja valitse sitten komento palkissa **jako**. 
    3. Anna vieras käyttäjän Sähkö posti osoite Azure AD-vuokraajalta. Lisätietoja: [Mikä on vieras käyttö oikeus Azure AD B2B-sovelluksessa?](/azure/active-directory/b2b/what-is-b2b)
          > [!div class="mx-imgBorder"] 
          > ![Kerro]vieras-(media/share-app/guest_access_doc_2.png "osakkella vieraan kanssa")
 
Kun olet jakanut sovelluksen vieras käyttöä varten, asiakkaat voivat etsiä ja käyttää heidän kanssaan jaettuja sovelluksia Sähkö posti viestistä, joka lähetetään heille osana jakamista.

> [!div class="mx-imgBorder"]  
> ![Asiakkaat saavat sovelluksen jakamisen sähkö postin](media/share-app/guest_access_doc_4.png "Asiakkaat saavat sovelluksen jakamisen Sähkö posti viestin")

### <a name="frequently-asked-questions"></a>Usein kysytyt kysymykset

#### <a name="whats-the-difference-between-canvas-app-guest-access-and-powerapps-portals"></a>Mitä eroa on kangas sovelluksen vieras käyttö-ja PowerApps-portaalien välillä? 
Canvas-sovellusten avulla voit luoda sovelluksen, joka on räätälöity liiketoiminta prosessien digitointiin kirjoittamatta koodia perinteisellä ohjelmointi kielellä, kuten C#. Kangas sovellusten vieras käyttö mahdollistaa sen, että työryhmät, jotka koostuvat eri organisaatioista, jotka osallistuvat yhteiseen liiketoiminta prosessiin, voivat käyttää samoja sovellus resursseja, jotka voidaan integroida useisiin erilaisiin Microsoftin ja kolmannen osapuolen lähteisiin. Lisätietoja: [Powerappsin kangas sovellusten liittimien yleiskatsaus](/powerapps/maker/canvas-apps/connections-list).

[Powerapps-portaalien](/powerapps/maker/portals/overview) anna mahdollisuus luoda pienikoodisia, reagoivia sivustoja, joiden avulla ulkoiset käyttäjät voivat käsitellä Common Data Service tallennettuja tietoja. Sen avulla organisaatiot voivat luoda sivustoja, jotka voidaan jakaa organisaationsa ulkopuolisten käyttäjien kanssa joko anonyymisti tai heidän valitsemansa kirjautumispalvelun kautta, kuten LinkedIn, Microsoft-tili tai muu kaupallinen kirjautumispalvelu. 

Seuraavassa taulukossa esitellään joitakin perusominaisuuksien eroja PowerApps-portaalien ja Canvas-sovellusten välillä.  

| | Liittymä | Todennus | Helppokäyttöisiin tieto lähteisiin |
|------|--------|----------|-------------------|
| PowerApps-portaalit | Vain selain käyttö kokemus | Sallii anonyymin ja todennetun käytön | Common Data Service |
| Pohjaan perustuvat sovellukset | Selain-ja mobiilisovellukset | Edellyttää todentamista Azuren mainosten kautta | Mikä tahansa ~ 150 out-of-Box-liittimet ja mikä tahansa mukautettu liitin  |
||

#### <a name="can-guests-access-customized-forms-in-sharepoint"></a>Voiko asiakkaat käyttää mukautettuja lomakkeita SharePointissa?
Kyllä. Kuka tahansa käyttäjä, joka voi käyttää mukautettua lomaketta käyttäviä SharePoint-luettelo tietoja, voi luoda ja muokata kohteita-lomakkeessa ilman PowerApps-käyttö oikeutta.

#### <a name="can-guests-access-apps-embedded-in-sharepoint"></a>Voimmeko käyttää SharePointiin upotettuja sovelluksia? 
Kyllä. Käyttö oikeus pohjaan erillisiin sovelluksiin edellyttää kuitenkin Powerappsin käyttö oikeutta, mukaan lukien upotettuja sovelluksia. Kun upotat pohjaan linkitetyn sovelluksen SharePointissa Microsoft PowerApps upotus-ohjaus objektin avulla, anna sovellus tunnus. Voit tehdä tämän kirjoittamalla sovelluksen tunnuksen **sovelluksen verkko linkki-tai tunnus** -ruutuun. 

> [!div class="mx-imgBorder"]  
> ![Upota pohjaan-sovellus SharePointissa vieraille](media/share-app/guest_access_doc_5.PNG "Upota pohjaan sovellus SharePointissa vieraille")

Kun upotat pohjaan kuuluvan sovelluksen SharePointissa iFrame-HTML-tunnisteen kautta, viittaa sovellukseen käyttäen täydellistä verkko-URL-osoitetta. Jos haluat löytää URL-osoitteen, siirry http://make.powerapps.com -kohtaan, valitse sovellus, valitse **tiedot** -väli lehti ja URL-osoite näytetään kohdassa **verkko linkki**.

> [!div class="mx-imgBorder"]  
> ![Kangas sovelluksen tietojen]pohjaan liittyviä(media/share-app/guest_access_doc_6.PNG "sovelluksen tiedot")

#### <a name="how-come-guests-can-launch-the-app-shared-with-them-but-connections-fail-to-be-created"></a>Miten tulevat asiakkaat voivat käynnistää sovelluksen, joka on jaettu heidän kanssaan, mutta yhteyksiä ei luoda?
Kuten muidenkin kuin asiakkaiden, myös sovelluksen käyttämät pohjana olevat tieto lähteet on asetettava asiakkaan saataville.

#### <a name="what-license-must-be-assigned-to-my-guest-so-they-can-run-an-app-shared-with-them"></a>Mikä käyttö oikeus on määritettävä vierailijalleni, jotta hän voi suorittaa sovelluksen, joka on jaettu heidän kanssaan?
Sama käyttö oikeus, joka vaaditaan sovelluksen suorittamiseen muille kuin vieraille. Jos sovellus ei käytä esimerkiksi Premium connecters-sovellusta, PowerApps P1-käyttö oikeus on riittävä, jotta se voidaan määrittää vierailijoille.  


|                                 | Mukautettu SharePoint-lomake | Itsenäinen kangas sovellus, joka käyttää muita kuin Premium-liittimiä | Itsenäinen kangas sovellus Premium-liittimillä | Mallipohjainen sovellus |
|---------------------------------|----------------------------|----------------------------------------------------|------------------------------------------------|------------------|
| SharePoint-käyttäjä (ei PA-käyttö oikeutta) | x                          |                                                    |                                                |                  |
| PowerApps sisälsi w/Office    | x                          |                                                    |                                                |                  |
| Powerappsin sopimus 1                | x                          | x                                                  |                                                |                  |
| PowerApps Plan2                 | x                          | x                                                  | x                                              | x                |

#### <a name="in-powerapps-mobile-how-does-a-guest-see-apps-for-their-home-tenant"></a>Miten asiakas näkee sovelluksia koti vuokraajansa PowerApps Mobilessa?
Jokainen käyttäjä, joka on käyttänyt pohjaan perustuvia sovelluksia mobiililaitteessaan, joka on julkaistu Azure AD-vuokraajassa, joka ei ole heidän kotivuokraajansa, on kirjauduttava Powerappsiin ja kirjauduttava takaisin sisään PowerApps Mobileen.  

#### <a name="must-a-guest-accept-the-azure-ad-guest-invitation-prior-to-sharing-an-app-with-the-guest"></a>Onko vieras hyväksyttävä Azure AD-vieras kutsu ennen sovelluksen jakamista vieraan kanssa?
Ei. Jos vieras käynnistää heidän kanssaan jaetun sovelluksen ennen vieras kutsun hyväksymistä, sinua pyydetään hyväksymään kutsu osana sisäänkirjautumiskokemusta, kun sovellus käynnistetään.  

#### <a name="what-azure-ad-tenant-are-connections-for-a-guest-user-created-in"></a>Mitä Azure AD-vuokraaja on yhteydessä luotavaan vieras käyttäjään?
Sovelluksen yhteydet tehdään aina Azure AD-vuokra ajan yhteydessä, johon sovellus liittyy. Jos sovellus luodaan esimerkiksi contoso-vuokra ajassa, contoso-vuokraajaan liittyvät yhteydet tehdään contoso-vuokra ajan yhteydessä.

#### <a name="can-guests-use-microsoft-graph-via-microsoft-security-graph-connector-or-a-custom-connector-using-microsoft-graph-apis"></a>Voiko asiakkaat käyttää Microsoft Graph Microsoft Security Graph Connectorin kautta tai mukautettua liitintä Microsoft Graph ohjelmointi raja pintojen avulla?
Ei, Azure AD-asiakkaat eivät voi tehdä kyselyitä Microsoft Graph hake maan tietoja vuokraajalta, jossa he ovat vieras.

#### <a name="what-intune-policies-apply-to-guests-using-my-powerapps"></a>Mitä InTune-käytännöt koskevat asiakkaita, jotka käyttävät Powerappsia?
InTune koskee vain käyttäjän koti vuokra ajan käytäntöjä. Jos esimerkiksi Alice@Contoso.com jakaa sovelluksen Vikram@Fabrikam.com kanssa, InTune käyttää edelleen Fabrikam.com-käytäntöjä Virkam-laitteessa riippumatta siitä, mitä Powerappsia hän suorittaa.

#### <a name="what-connectors-support-guest-access"></a>Mitkä liittimet tukevat vieras käyttöä?
Kaikki liittimet, jotka eivät suorita Azure AD-todentamista, tukevat vieras käyttöä. Seuraavassa taulukossa luetellaan kaikki liittimet, jotka suorittavat Azure AD-todentamista ja mitkä liittimet tukevat tällä hetkellä vieras käyttöä. Monet näistä päivitetään, mikä johtaa yleiseen käytettävyyteen.

| **Liitin**                                     | **Tukee vieras käyttöä**                                              |
|---------------------------------------------------|------------------------------------------------------------------------|
| 10to8 Appointment Scheduling                      | Ei                                                                     |
| Adobe Creative Cloud                              | Ei                                                                     |
| Adobe Sign                                        | Ei                                                                     |
| Asana                                             | Ei                                                                     |
| AtBot-järjestelmänvalvoja                                       | Ei                                                                     |
| AtBot-logiikka                                       | Ei                                                                     |
| Azure AD                                          | Kyllä                                                                    |
| Azure Automation                                  | Kyllä                                                                    |
| Azure-säiliön esiintymä                          | Kyllä                                                                    |
| Azure Data Factory                                | Kyllä                                                                    |
| Azure Data Lake                                   | Kyllä                                                                    |
| Azure-DevOps                                      | Ei                                                                     |
| Azure Event Grid                                  | Ei                                                                     |
| Azure IoT Central                                 | Kyllä                                                                    |
| Azure Key Vault                                   | Ei                                                                     |
| Azure Kuto                                       | Kyllä                                                                    |
| Azure Log Analytics                               | Kyllä                                                                    |
| Azure Resource Manager                            | Kyllä                                                                    |
| Basecamp 2                                        | Ei                                                                     |
| Bitbucket                                         | Ei                                                                     |
| Bitly                                             | Ei                                                                     |
| bttn                                              | Ei                                                                     |
| Buffer                                            | Ei                                                                     |
| Liike toiminnan keskus                                  | Ei                                                                     |
| Ehdotezip                                      | Ei                                                                     |
| Capsule CRM                                       | Ei                                                                     |
| Pilvi palvelun PKI-hallinta                              | Ei                                                                     |
| Cognito Forms                                     | Ei                                                                     |
| Common Data Service                               | Ei                                                                     |
| Common Data Service (vanha)                      | Ei                                                                     |
| D & B-optimoija                                     | Ei                                                                     |
| Derdack SIGNL4:N avulla                                    | Ei                                                                     |
| Disqus                                            | Ei                                                                     |
| Asia kirjan yhdistäminen                                    | Ei                                                                     |
| Dynamics 365                                      | Ei                                                                     |
| Dynamics 365 AI myynnissä                         | Kyllä                                                                    |
| Dynamics 365 for fin & Ops                        | Ei                                                                     |
| Enadocin                                            | Ei                                                                     |
| Eventbrite                                        | Ei                                                                     |
| Excel Online (yritys)                           | Ei                                                                     |
| Excel Online (OneDrive)                           | Ei                                                                     |
| Vanhentumisen muistutus                               | Ei                                                                     |
| FreshBooks                                        | Ei                                                                     |
| GoToMeeting                                       | Ei                                                                     |
| GoToTraining                                      | Ei                                                                     |
| GoToWebinar                                       | Ei                                                                     |
| Harvest                                           | Ei                                                                     |
| HTTP with Azure AD                                | Ei                                                                     |
| Infusionsoft                                      | Ei                                                                     |
| Inoreader                                         | Ei                                                                     |
| Intercom                                          | Ei                                                                     |
| JotForm                                           | Ei                                                                     |
| kintonen                                           | Ei                                                                     |
| LinkedIn                                          | Ei                                                                     |
| Markkinoinnin sisältö keskus                             | Ei                                                                     |
| Medium                                            | Ei                                                                     |
| Metatask                                          | Ei                                                                     |
| Microsoft Forms                                   | Ei                                                                     |
| Microsoft Forms Pro                               | Ei                                                                     |
| Microsoft Graph suojaus                          | Ei                                                                     |
| Microsoft Kaizala                                 | Ei                                                                     |
| Microsoft School-tietojen synkronointi                        | Ei                                                                     |
| Microsoft StaffHub                                | Ei                                                                     |
| Microsoft Teams                                   | Kyllä                                                                    |
| Microsoft to-do (yritys)                        | Ei                                                                     |
| Muhimbi PDF                                       | Ei                                                                     |
| NetDocuments                                      | Ei                                                                     |
| Office 365 Groups                                 | Kyllä                                                                    |
| Office 365 Outlook                                | Ei                                                                     |
| Office 365 -käyttäjät                                  | Kyllä                                                                    |
| Office 365 Video                                  | Ei                                                                     |
| OneDrive                                          | Ei                                                                     |
| OneDrive for Business                             | Ei                                                                     |
| OneNote (Business)                                | Ei                                                                     |
| Outlook Customer Manager                          | Ei                                                                     |
| Outlook Tasks                                     | Kyllä                                                                    |
| Outlook.com                                       | Ei                                                                     |
| Paylocity                                         | Ei                                                                     |
| Planner                                           | Ei                                                                     |
| Plumsail-lomakkeet                                    | Ei                                                                     |
| Power BI                                          | Kyllä                                                                    |
| Project Online                                    | Ei                                                                     |
| ProjectWise-suunnittelu integraatio                    | Ei                                                                     |
| ProjectWise-jako                                 | Ei                                                                     |
| SharePoint                                        | Kyllä                                                                    |
| SignNow                                           | Ei                                                                     |
| Skype for Business Online                         | Ei                                                                     |
| Soft1                                             | Ei                                                                     |
| Storwboard                                        | Ei                                                                     |
| Survey123                                         | Ei                                                                     |
| SurveyMonkey                                      | Ei                                                                     |
| Toodledo                                          | Ei                                                                     |
| Typeform                                          | Ei                                                                     |
| Vimeo                                             | Ei                                                                     |
| WebEx-tiimit                                       | Ei                                                                     |
| Windows Defenderin laajennetun uhan suojaus (ATP) | Ei                                                                     |
| Word online (yritys)                            | Ei                                                                     |
