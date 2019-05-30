---
title: Upota PowerApps-sovellus teamsissa | Microsoft Docs
description: Voit upottaa sovelluksen powerappsissa ja jakaa sen Microsoft teamsissa.
author: jimholtz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/29/2019
ms.author: jimholtz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d17b02cc87bb219474aade955a2910f12fcf7f27
ms.sourcegitcommit: 2376c1f1f3431bca52a8deb9b966ce1fe9f88da0
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/30/2019
ms.locfileid: "66381382"
---
# <a name="embed-a-powerapps-app-in-teams"></a>Upota PowerApps-sovellus teamsissa 

Voit jakaa PowerApps, olet luonut upottamalla suoraan Microsoft Teamsissa. Kun valmis, käyttäjät voivat valita **+** Lisää sovelluksesi mihin tahansa **-** tiimin kanavat tai olet ryhmän keskustelut. Sovellus näkyy ruutuna **tiimisi välilehdet**. 

Järjestelmänvalvoja voit ladata sovelluksen, jotta se näyttää **kaikki** vuokraajasi teams **kaikki välilehdet kohdassa**. Katso [jakaa sovelluksen Microsoft teamsissa](https://review.docs.microsoft.com/en-us/power-platform/admin/embed-app-teams?branch=JimHoltzWorkBranch).

> [!NOTE]
> Ryhmän mukautettu sovellus käytännöt on määritettävä sallimaan ladataan mukautettuja sovelluksia. Jos sovelluksen upottaminen ryhmiä ei onnistu, ota yhteyttä järjestelmänvalvojaan nähdäksesi, jos ne määrittänyt [mukautetun sovelluksen asetuksissa](https://docs.microsoft.com/MicrosoftTeams/teams-custom-app-policies-and-settings#custom-app-policy-and-settings). 

## <a name="prerequisites"></a>Edellytykset

- [On PowerApps-käyttöoikeus](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus)
- Luotu pohjaan perustuva sovellus

## <a name="locate-your-powerapps-guid"></a>Etsi-PowerApp GUID-tunnus

Etsi ja muistiin-PowerApp käyttämään myöhemmin GUID-tunnus.

1. Kirjaudu sisään [ https://web.powerapps.com ](https://web.powerapps.com), ja valitse sitten **sovelluksia** -valikosta.

   > [!div class="mx-imgBorder"] 
   > ![Näytä sovellusluettelo](./media/embed-teams-app/file-apps2.png "Näytä sovellusten luettelo")

2. Valitse **Lisää komentoja** (...) haluat jakaa teamsissa ja valitse sitten sovelluksen **tiedot**.

   > [!div class="mx-imgBorder"] 
   > ![Sovelluksen tiedot](./media/embed-teams-app/app-details.png "sovelluksen tiedot")

3. Tietue **Sovellustunnus** myöhempää käyttöä varten.

   > [!div class="mx-imgBorder"] 
   > ![Sovelluksen tiedot](./media/embed-teams-app/app-details2.png "sovelluksen tiedot")

## <a name="install-app-studio"></a>Asenna App Studio

Voit ohittaa nämä vaiheet, jos App Studio on jo asennettu. 

1. Valitse Teamsissa **sovelluksia** -vasemmassa alakulmassa Teams-valikon (![sovelluksia-kuvake](./media/embed-teams-app/apps-icon.png "sovelluksia-kuvake")).

2. Hae ”App Studio-haku-ruutua ja valitse se.

   > [!div class="mx-imgBorder"] 
   > ![App Studio](./media/embed-teams-app/store-app-studio.png "App Studio")

3. Valitse **asentaa**. 

   > [!div class="mx-imgBorder"] 
   > ![Asenna App Studio](./media/embed-teams-app/install-app-studio.png "Asenna App Studio")

4. Valitse **Avaa** App-ominaisuuden.

   > [!div class="mx-imgBorder"] 
   > ![Avaa App Studio](./media/embed-teams-app/open-app-studio.png "Avaa App Studio")

## <a name="create-a-teams-app-for-your-powerapp"></a>Luo PowerApp-Teams-sovellus

1. Avaa App Studio Teamsissa.

   > [!div class="mx-imgBorder"] 
   > ![Avaa App Studio](./media/embed-teams-app/open-app-studio2.png "Avaa App Studio")

2. Valitse **tiedostojen editorin** välilehti ja valitse sitten **luomalla uusi sovellus** Tervetuloa-kohdassa.

   > [!div class="mx-imgBorder"] 
   > ![Luo uusi sovellus](./media/embed-teams-app/create-new-app.png "Luo uusi sovellus")

3. Täytä sovelluksesi tietoja **sovelluksen tiedot** sivun.  Sovelluksen tunnus GUID-tunnus on käyttää yllä kirjataan-PowerApp sovelluksen tunnuksen GUID.  Tämä välttämään Teams sovellusten tietyn PowerApp.
 
   > [!div class="mx-imgBorder"] 
   > ![Täytä tiedot](./media/embed-teams-app/fill-in-info-about-app.png "tiedot")

   |Kentät  |Kuvaus  |
   |---------|---------|
   |**Sovellusten nimet** |    |
   |Lyhyt nimi     | Pakollinen. Sovelluksen lyhyt näyttönimi. 30 merkkiä.        |
   |Pitkä nimi     | Koko nimi-sovelluksen käyttää, jos koko sovelluksen nimessä on yli 30 merkkiä.       | 
   |**Tunnus**     |         |
   |Sovelluksen tunnus     | Pakollinen. Microsoft luomien yksilöllinen tälle sovellukselle.        |
   |Pakettinimi     | Pakollinen. Tämä sovellus yksilöivä tunnus. Suosittelemme käänteiseen toimialueen merkintätapaa; esimerkiksi com.example. <AppName>.       |
   |Versio     | Pakollinen. Tietyn sovelluksen versio. Jos päivität jotakin-luettelo, versio on arvoon myös.     |
   |**Kuvaukset**    |     |
   | Lyhyt kuvaus    | Pakollinen. Sovelluksen käyttökokemus, käyttää, kun tila on rajallinen lyhyt kuvaus. 80 merkkiä.   |
   | Pitkä kuvaus    | Pakollinen. Sovelluksesi täydellinen kuvaus.     |
   | **Kehittäjille**    |     |
   | Nimi    | Pakollinen. Yrityksen tai developer näyttönimi.     |
   | Sivusto    | Pakollinen. Https:// URL-osoite sovelluksesi kautta powerapps.com-sivustossa. Kun joku asentaa sovelluksen ”sovelluksesta” sivu tulee näkyviin. Se olisi linkki sovelluksesi powerapps.comissa WWW-version.   |
   | **Sovelluksen URL-osoitteet**    | Nämä linkit näytetään **tietoja** sivulla kanssa sivuston URL-osoite.     |
   | Tietosuojatiedot    | Pakollinen. Https:// URL-osoite on kehittäjän tietosuojakäytäntö. [Esimerkki](https://go.microsoft.com/fwlink/p/?LinkID=698505).   |
   | Käyttöehdot    | Pakollinen. Https:// URL-osoite on kehittäjän käyttöehdot.  [Esimerkki](https://go.microsoft.com/fwlink/p/?LinkID=698507).  |
   | **Mukauttamisen**    |     |
   | Koko väri    | Koko väri 192 x 192 PNG-kuvake suhteellista tiedostopolkua.    |
   | Läpinäkyvä Jäsennys    |Suhteellista tiedostopolkua läpinäkyvä 32 x 32-PNG jäsennys-kuvake.     |
   | Korostuksen väri    | Ääriviivan kuvakkeiden yhteydessä ja taustana käytettävän värin.     |

Jos haluat lisätietoja, katso [Manifest editorin](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio#manifest-editor) ja [luettelo rakenteen](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema).

4. Vieritä alas Tuotemerkkiohjeet osioon ja lisää-logoja ja sovelluksen desired korostuksen väri.  Nämä ovat tunnuksia, joka näkyy sovelluksen teamsissa. 

   > [!div class="mx-imgBorder"] 
   > ![Mukauttamisen ja kirjaa](./media/embed-teams-app/branding-tabs.png "mukauttamisen ja välilehdet")

5. Valitse **ominaisuuksia**, valitse **välilehdet**.

6. Valitse **tiimin välilehti** Valitse **Lisää**.

   > [!div class="mx-imgBorder"] 
   > ![Tiimin välilehti Lisää](./media/embed-teams-app/team-tab-add.png "tiimin Lisää-välilehti")

7. Lisää sovelluksesi määrityksen URL-osoite ”määrityksen URL-osoite” syötekentän seuraavassa muodossa: `https://web.powerapps.com/webplayer/teamsapptabsettings?appid=<PowerApp ID>`

   Korvaa `<PowerApp ID>` sovelluksen tunnus GUID-tunnuksella yllä kirjataan.

   Valitse [vaikutusalueen](https://docs.microsoft.com/microsoftteams/platform/concepts/tabs/tabs-overview#tab-scope) sovelluksen näkyvät. Varmista, että **voi päivittää** on valittuna ja valitse sitten **Tallenna**.

   > [!div class="mx-imgBorder"] 
   > ![Määrityksen URL-osoite](./media/embed-teams-app/configuration-url.png "määrityksen URL-osoite")

8. Valitse **valmis**, valitse **kelvollinen toimialueiden**. Lisää **apps.powerapps.com** ja **apps.preview.powerapps.com** kuin kelvollinen toimialueiden Teams-sovelluksen.

   > [!div class="mx-imgBorder"] 
   > ![Lisää kelvollinen toimialueet](./media/embed-teams-app/add-valid-domains.png "Lisää kelvollinen toimialueet")

9. Valitse **valmis**, valitse **Test ja jaella**. Valitse **asentaa**, valitse **asentaa**.

   > [!div class="mx-imgBorder"] 
   > ![Valitse Asenna](./media/embed-teams-app/test-distribute-app.png "valitsemalla Asenna")

10. Valitse haluat asentaa sovelluksen ryhmän ja valitse sitten **asentaa**.

    > [!div class="mx-imgBorder"] 
    > ![Lisää ryhmän Asenna](./media/embed-teams-app/new-app-add-to-team.png "Lisää tiimin asennus")

11. Jos haluat sovelluksen esiintymä lisääminen kanavaan heti, valitse kanava, jota haluat käyttää sovelluksen sisään ja valitse **määrittää**.

    > [!div class="mx-imgBorder"] 
    > ![Valitse ylöspäin](./media/embed-teams-app/app-now-available.png "Valitse määrittäminen")

12. Valitse **Tallenna**.

## <a name="add-the-app-as-a-tab"></a>Lisää sovellus välilehti

Jos haluat lisätä välilehdeksi sovelluksen kanavan tai keskustelun, valitse **+** , ja valitse sitten **tiimisi välilehdet** Valitse sovelluksesi. 

> [!div class="mx-imgBorder"] 
> ![Lisää sovellus välilehti](./media/embed-teams-app/add-app-as-tab.png "välilehdessä Lisää sovellus")

Sovellus näkyy nyt välilehti.

> [!div class="mx-imgBorder"] 
> ![Sovelluksen kuin välilehdessä](./media/embed-teams-app/app-as-tab.png "välilehti sovellus")

### <a name="see-also"></a>Katso myös
[Tervetuloa Microsoft Teamsissa](https://docs.microsoft.com/MicrosoftTeams/teams-overview)<br />
[Järjestelmänvalvojille: Upota sovellus Microsoft teamsissa](https://docs.microsoft.com/power-platform/admin/share-app-teams)