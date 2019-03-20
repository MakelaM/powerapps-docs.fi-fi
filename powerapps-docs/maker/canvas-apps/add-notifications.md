---
title: Palveluilmoituksen lähettäminen | Microsoft Docs
description: Lue, kuinka voit lähettää sovellukselle natiiveja palveluilmoituksia PowerAppsissa.
author: kavishi
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/08/2017
ms.author: kaagar
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f5ee975343afc16faaca52194b16cedff57e7e9f
ms.sourcegitcommit: fe47ad47873a37fbe17b30d39fb2ca6035b7d152
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/07/2019
ms.locfileid: "57800855"
---
# <a name="send-a-push-notification-in-powerapps"></a>Palveluilmoituksen lähettäminen PowerAppsissa
Palveluilmoituksia käytetään kuluttaja- ja yritysmobiilisovelluksissa ensisijaisesti yhteydenpitoon sovellusten käyttäjien kanssa ja auttamaan heitä priorisoimaan tärkeitä tehtäviä. Voit lähettää PowerAppsissa ilmoituksia käyttämällä PowerApps Notification -yhdistintä. Voit lähettää natiiveja palveluilmoituksia mille tahansa sovellukselle, jonka luot PowerAppsissa. Aiomme lisätä tulevaisuudessa ilmoitustyyppejä.

![Esimerkki palveluilmoituksesta](./media/add-notifications/pic1-notification-screenshot.png)

Lisää sovellukseesi palveluilmoitus seuraavissa tilanteissa:

* Tieto tulee lähettää käyttäjälle heti.
* Käyttäjien täytyy suorittaa sovelluksessasi tärkeitä tehtäviä esiladatussa kontekstissa.
* Haluat pitää yhteyttä käyttäjiin tietyllä aikavälillä tai haluat, että käyttäjät siirtyvät sovellukseen tietyssä tilanteessa.

> [!NOTE]
> Palveluilmoitusten saamiseksi käyttäjien täytyy avata sovellus PowerApps Mobilessa kerran tai vastaanottaa sovellus [Dynamics 365:n](https://home.dynamics.com/) AppSourcen kautta.

## <a name="before-you-start"></a>Ennen aloittamista
Lisää PowerApps Notification -yhteys sovellukseen, johon sinulla on **Osallistuja**-käyttöoikeus. Jos sinulla ei ole vielä sovellusta, voit [luoda sellaisen nopeasti mallin avulla](get-started-test-drive.md), jolloin sinulla on oletuksena tarvittava käyttöoikeus. Kyseinen opas ja opas perustuvat Palvelupyynnön hallinta -malliin.

## <a name="send-a-notification-from-a-flow"></a>Ilmoituksen lähettäminen työnkulusta
> [!NOTE]
> Jos aktivoit palveluilmoituksen työnkulun kautta, voit tällä hetkellä lähettää ilmoituksen kerralla vain yhdelle käyttäjälle tai käyttöoikeusryhmälle.

1. Luo [Microsoft Flow'ssa](https://flow.microsoft.com) käynnistin, joka määrittää, milloin palveluilmoitus lähetetään.

    Voit esimerkiksi lähettää ilmoituksen, kun tietue lisätään Common Data Servicen **Case**-entiteettiin.

    ![Näyttökuva Common Data Service -käynnistimen sisältävän työnkulun luomisesta](./media/add-notifications/pic4-step1-flowupdated.png)
2. Luo työnkululle toiminto käyttämällä **PowerApps Notification** -yhdistintä ja syöttämällä sen sovelluksen **sovellustunnus**, jolle haluat lähettää ilmoituksen.

    Voit myös nimetä yhteyden uudelleen skenaariosi mukaisesti.

    ![Näyttökuva yhteyden luomisesta PowerApps-sovelluksiin, jotka vastaanottavat nämä palveluilmoitukset](./media/add-notifications/pic5-step2-create-connection.jpg)
3. (valinnainen) Parametrin välittäminen sovellukselle, kun se avautuu (sen jälkeen, kun käyttäjä on napauttanut palveluilmoitusta).

    Tässä esimerkissä välitetään kentät **CaseID** ja **Initial Owner** valitulle yhteydelle.

    ![Näyttökuva valinnaisten parametrien välittämisestä palveluilmoitukseen](./media/add-notifications/pic6-step3-configure-notif.jpg)

## <a name="send-a-notification-from-an-app"></a>Ilmoituksen lähettäminen sovelluksesta
Voit lähettää palveluilmoituksen yhdestä sovelluksesta toiseen tai samaan sovellukseen.

1. Siirry [PowerAppsissa](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) sovellukseen, johon haluat lähettää palveluilmoituksen.
2. Kopioi **Tiedot**-välilehdeltä sovelluksen **sovellustunnus**.

    ![Sovellustunnuksen hakeminen](./media/add-notifications/grab-id.png)
3. Luo **Yhteydet**-välilehdellä yhteys PowerApps Notification -yhdistimeen ja liitä edellisessä vaiheessa haettu sovellustunnus.

    ![Yhteyden luominen](./media/add-notifications/create-connection.png)
4. Lisää yhteys käynnistinsovellukseen.

    Käytämme tässä esimerkissä samaa sovellusta käynnistinsovelluksena. Käyttäjä, joka määrittää tapauksen uudelleen, laukaisee palveluilmoituksen tapauksen uudelle omistajalle.

    ![Yhteyden lisääminen](./media/add-notifications/add-connection.png)
5. Kutsu palveluilmoitusyhteyden kautta **SendPushNotification**-menetelmä.

    Tässä esimerkissä aktivoimme ilmoituksen käyttämällä **OnSuccess**-ominaisuutta lomakkeessa.

    ![PowerApps-kaava](./media/add-notifications/powerapps-function.png)

## <a name="load-a-specific-page-and-context-when-a-user-taps-the-notification"></a>Tietyn sivun ja kontekstin lataaminen, kun käyttäjä napauttaa ilmoitusta
### <a name="pass-parameters"></a>Parametrien välittäminen
Palveluilmoituksesi voivat välittää sovellukselle parametreja. Esimerkiksi **CaseID**-arvon lukemiseen käytetään kaavaa *Param("CaseID")*. Tämän parametrin nopeaa tunnistamista varten lisää sovellukseesi **Otsikko**-ohjausobjekti. Aseta sen **Text**-ominaisuudeksi **Param("CaseID")**. Jos käyttäjä avaa sovelluksen **Kaikki sovellukset** -luettelon kautta, arvo on tyhjä. Jos käyttäjä avaa sovelluksen eri sijainnista laitteella, arvo täytetään **CaseID**-arvolla.

### <a name="set-the-start-page"></a>Aloitussivun asettaminen
Voit asettaa sovelluksen avaamaan esimerkiksi **Case details** -sivun, kun sovellus avautuu:

1. Lisää **Ajastin**-ohjausobjekti ja aseta sen **OnTimerEnd**-ominaisuudeksi seuraava kaava:
   <br>**Navigate(EditCase, ScreenTransition.None)**
2. (valinnainen) Piilota **Ajastin**-ohjausobjekti asettamalla sen **Visible**-ominaisuudeksi **false**.
3. Aseta näytön **OnVisible**-ominaisuudeksi **Timer.Start()**.

> [!TIP]
> Ilmoitusta varten sovellukseen voidaan luoda yksilöllinen aloitussivu:
> 
> 1. Luo tyhjä sivu, jota sovellus ei jo avaa muilla tavoin, lisää **Tekstisyöte**-ohjausobjekti ja aseta sen **timer.Duration**-arvo.
> 2. Kun luot sovelluksen, aseta ajastimelle arvo, joka ei ole nolla. Kun olet valmis julkaisemaan sovelluksen, laukaise ajastin välittömästi asettamalla arvoksi **0**.

## <a name="syntax"></a>Syntaksi

| Nimi | Kuvaus |
| --- | --- |
| SendPushNotification |Lähettää palveluilmoituksen sovellukselle, joka määritetään ilmoituksen yhteysasetuksissa. |

### <a name="parameters"></a>Parametrit

| Nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| recipients |Merkkijonomatriisi, pakollinen |Luettelo: <ul> <li>Käyttäjien tai käyttöoikeusryhmien sähköpostiosoitteista</li> <li>Käyttäjien tai käyttöoikeusryhmien objektitunnuksista Azure Active Directoryssä</li></ul> |
| message |Merkkijono, pakollinen |Palveluilmoituksen näytettävä viesti. |
| openApp |Totuusarvo, valinnainen |Avataanko sovellus, kun käyttäjä napauttaa palveluilmoitusta. |
| params |Parametrit, valinnainen |Ilmoituksen mukana välitettävät avain-arvo-parametrit. Näitä voidaan käsitellä edelleen sovelluksessa tietyn sivun avaamiseksi tai tietyn tilan lataamiseksi. |

### <a name="sample-formulas"></a>Esimerkkikaavoja
Perusilmoituksen lähettäminen.

```
PowerAppsNotification.SendPushNotification(
{
  recipients: [""f60ccf6f-7579-4f92-967c-2920473c966b", 72f988bf-86f1-41af-91ab-2d7cd011db47],
  message: "A new case was assigned to you."
 }
)
```

Sovelluksen avaavan ja parametreja välittävän ilmoituksen lähettäminen.

```
PowerAppsNotification.SendPushNotification(
{
  recipients:["email1@contoso.com", "email2@contoso.com"],
  message:"message in the notif toast",
  params:Table({key:"notificationKey", value:"The value for notificationKey"}),
  openApp:true
 }
)
```

## <a name="known-limitations"></a>Tunnetut rajoitukset
* Tällä hetkellä ilmoituksia ei näytetä PowerApps Mobilen Windows Phone -versiossa.
* Tällä hetkellä emme tarjoa palveluilmoituksia käyttäjille, jotka käyttävät sovelluksia vain verkkoselaimessa.
* Ilmoituksissa näytetään geneerinen PowerApps-kuvake tietyn sovelluksen kuvakkeen sijaan.
* Kun käytät Microsoft Flow'ta, voit lähettää palveluilmoituksen vain yhdelle vastaanottajalle kerrallaan.

Katso viitetiedot kohdasta [PowerApps Notification -viitetiedot](https://docs.microsoft.com/connectors/powerappsnotification/).

