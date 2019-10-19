---
title: PowerApps-sovelluksen upottaminen tiimeihin | Microsoft Docs
description: Voit upottaa Powerappsissa luodun sovelluksen Microsoft Teamsiin jakamaan sen.
author: jimholtz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 09/09/2019
ms.author: jimholtz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ba08437dc144fc81aa9748163b1005222735cb69
ms.sourcegitcommit: a560630f5ee83629a7236ae774fc0c8195b95efa
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/18/2019
ms.locfileid: "70842244"
---
# <a name="embed-a-powerapps-app-in-teams"></a>PowerApps-sovelluksen upottaminen tiimeihin 

Voit kertoa luomiasi PowerApps-sovelluksia upottamalla ne suoraan Microsoft Teamsiin. Kun käyttäjä on valmis, hän voi valita **+** , jos haluat lisätä sovelluksesi mihin tahansa ryhmäsi kanavasi tai **keskusteluisi** ryhmässä, jossa olet. Sovellus näkyy ruutuna **ryhmäsi väli lehtien**alla. 

Järjestelmänvalvoja voi ladata sovelluksen, jotta se näkyy **kaikissa** vuokra ajan tiimeissä **Kaikki väli lehdet-osiossa**. Tutustu [sovelluksen jakamiseen Microsoft teamsissa](https://docs.microsoft.com/en-us/power-platform/admin/embed-app-teams).

> [!NOTE]
> Mukautettujen sovelluksien lataaminen on sallittu mukautetun ryhmän sovellus käytännöillä. Jos et voi upottaa sovellustasi tiimeihin, kysy järjestelmänvalvojaltasi, onko hän määrittänyt [mukautettuja sovellus asetuksia](https://docs.microsoft.com/MicrosoftTeams/teams-custom-app-policies-and-settings#custom-app-policy-and-settings). 

## <a name="prerequisites"></a>Edellytykset

- [Sinulla on PowerApps-käyttö oikeus](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus)
- Luo kangas sovellus

## <a name="locate-your-powerapps-guid"></a>Etsi Powerappin GUID

Etsi ja pane muistiin Powerappin GUID, jota voit käyttää myöhemmässä vaiheessa.

1. Kirjaudu sisään [https://web.powerapps.com](https://web.powerapps.com)ja valitse sitten valikosta **sovellukset** .

   > [!div class="mx-imgBorder"] 
   > ![Näytä sovellusten luettelo](./media/embed-teams-app/file-apps2.png "Näytä sovellusluettelo")

2. Valitse **Lisää komentoja** (...) sovellukselle, jonka haluat jaettavan teamsissa, ja valitse sitten **tiedot**.

   > [!div class="mx-imgBorder"] 
   > ![Sovelluksen tiedot](./media/embed-teams-app/app-details.png "Sovelluksen tiedot")


3. Tallenna **sovellus tunnus** myöhempää käyttöä varten.

   > [!div class="mx-imgBorder"] 
   > ![Sovelluksen tiedot](./media/embed-teams-app/app-details2.png "Sovelluksen tiedot")

## <a name="install-app-studio"></a>Asenna sovellus Studio

Voit ohittaa nämä vaiheet, jos sovellus Studio on jo asennettuna. 

1. Valitse joukkueet-kohdassa ryhmät-valikon vasemmasta alavalikosta **sovellukset** (![apps-kuvake](./media/embed-teams-app/apps-icon.png "Sovellukset-kuvake")).

2. Hae haku ruudusta "App Studio" ja valitse se.

   > [!div class="mx-imgBorder"] 
   > ![Sovellus Studio](./media/embed-teams-app/store-app-studio.png "Sovellus Studio")

3. Valitse **Asenna**. 

   > [!div class="mx-imgBorder"] 
   > ![Asenna sovellus Studio](./media/embed-teams-app/install-app-studio.png "Asenna sovellus Studio")

4. Valitse sovellus ominaisuudelle **Avaa** .

   > [!div class="mx-imgBorder"] 
   > ![Avaa sovellus Studio](./media/embed-teams-app/open-app-studio.png "Avaa sovellus Studio")

## <a name="create-a-teams-app-for-your-powerapp"></a>Tiimi sovelluksen luominen Powerappille

1. Avaa Teamsissa App Studio.

   > [!div class="mx-imgBorder"] 
   > ![Avaa sovellus Studio](./media/embed-teams-app/open-app-studio2.png "Avaa sovellus Studio")

2. Valitse **luettelo editori** -väli lehti ja valitse sitten **Luo uusi sovellus** Tervetuloa-kohdassa.

   > [!div class="mx-imgBorder"] 
   > ![Luo uusi sovellus](./media/embed-teams-app/create-new-app.png "Luo uusi sovellus")

3. Täytä tietoja sovelluksestasi **sovelluksen tiedot** -sivulla.  Jos kyseessä on sovellus tunnuksen GUID-tunnus, sinun tulee käyttää yllä tallentamasi Powerappin sovellus tunnuksen GUID-tunnusta.  Näin vältetään teamsin sovellusten päällekkäinen tietyn Powerappin kanssa.
 
   > [!div class="mx-imgBorder"] 
   > ![Täytä tiedot](./media/embed-teams-app/fill-in-info-about-app.png "Täytä tiedot")

   |Kentät  |Kuvaus  |
   |---------|---------|
   |**Sovellusten nimet** |    |
   |Lyhyt nimi     | Tarvitaan. Sovelluksen lyhyt näyttö nimi. 30 merkin enimmäisarvo.        |
   |Pitkä nimi     | Sovelluksen koko nimi, jota käytetään, jos sovelluksen koko nimi ylittää 30 merkkiä.       | 
   |**Tunnistus**     |         |
   |Sovellus tunnus     | Tarvitaan. Tämän sovelluksen yksilöivä Microsoftin luoma tunnus.        |
   |Paketin nimi     | Tarvitaan. Tämän sovelluksen yksilöivä tunnus. Suosittelemme käyttämään käänteisen toimi alueen merkintää; Esimerkki: com. esimerkki. <AppName>.       |
   |Versio     | Tarvitaan. Määritetyn sovelluksen versio. Jos päivität jotakin luettelo tiedostosi, versio on myös suurennettava.     |
   |**Kuva ukset**    |     |
   | Lyhyt kuvaus    | Tarvitaan. Lyhyt kuvaus sovelluskokemuksestasi, jota käytetään, kun tilaa on rajoitetusti. 80-merkki rajoitusta.   |
   | Pitkä kuvaus    | Tarvitaan. Sovelluksesi täydellinen kuvaus.     |
   | **Kehittäjien tiedot**    |     |
   | Nimi    | Tarvitaan. Yrityksen tai kehittäjän näyttö nimi.     |
   | Sivuston    | Tarvitaan. Https://-URL-osoite sovelluksellesi powerapps.com-sivuston kautta. Kun joku asentaa sovelluksesi, näkyviin tulee "About Your App"-sivu. Sen pitäisi linkittää sovelluksesi verkko versioon osoitteessa powerapps.com.   |
   | **Sovelluksen URL-osoitteet**    | Nämä linkit näkyvät **tietoja** -sivulla sivuston URL-osoitteen lisäksi.     |
   | Tieto suoja tiedot    | Tarvitaan. Https://-URL-osoite kehittäjän tieto suoja käytäntöön. [Esimerkki](https://go.microsoft.com/fwlink/p/?LinkID=698505).   |
   | Käyttöehdot    | Tarvitaan. Kehittäjän käyttö ehtojen https://URL-osoite.  [Esimerkki](https://go.microsoft.com/fwlink/p/?LinkID=698507).  |
   | **Mukauttamisen**    |     |
   | Nelivärinen    | Suhteellinen tiedosto polku neliväriseen 192x192 PNG-kuvakkeeseen.    |
   | Läpinäkyvä ääri viiva    |Läpinäkyvä 32 x 32 PNG-jäsennys kuvakkeen suhteellinen tiedosto polku.     |
   | Korostus väri    | Väri, jota käytetään jäsennys kuvakkeiden yhteydessä ja taustana.     |

Lisä tietoja on kohdassa [luettelo editori](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio#manifest-editor) ja [luettelo rakenne](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema).

4. Vieritä alaspäin branding-osioon ja lisää logot sekä sovelluksen korostus väri.  Nämä ovat logot, jotka näkyvät Sovelluksellesi tiimeissä. 

   > [!div class="mx-imgBorder"] 
   > ![Tuote merkki ja väli lehdet](./media/embed-teams-app/branding-tabs.png "Tuote merkki ja väli lehdet")

5. Valitse **toiminnot**-kohdassa **väli lehdet**.

6. Valitse **Ryhmä-väli lehdeltä** **Lisää**.

   > [!div class="mx-imgBorder"] 
   > ![Ryhmän väli lehti lisää](./media/embed-teams-app/team-tab-add.png "Ryhmän väli lehti lisää")

7. Lisää sovelluksesi määrityksen URL-osoite "määrityksen URL-osoite"-syöte kenttään käyttäen seuraavaa muotoa: `https://apps.powerapps.com/teams/settings/<PowerApp ID>`

   Korvaa `<PowerApp ID>` yllä mainitulla sovellus tunnuksen GUID-tunnuksella.

   Valitse sovelluksesi [vaikutus alue](https://docs.microsoft.com/microsoftteams/platform/concepts/tabs/tabs-overview#tab-scope) . Varmista, että **määritysten päivittäminen** on valittuna, ja valitse sitten **Tallenna**.

   > [!div class="mx-imgBorder"] 
   > ![Määrityksen URL-osoite](./media/embed-teams-app/configuration-url.png "Määrityksen URL-osoite")

8. Valitse **valmis**-kohdassa **kelvolliset verkko tunnukset**. Lisää **apps.powerapps.com** -ja **apps.Preview.powerapps.com** -käyttö ehdot tiimit-sovelluksen kelvollisiksi toimialueiksi.

   > [!div class="mx-imgBorder"] 
   > ![Lisää kelvolliset verkko tunnukset](./media/embed-teams-app/add-valid-domains.png "Lisää kelvolliset verkko tunnukset")

9. Valitse **valmis**-kohdassa **Testaa ja Jaa**. Valitse **Asenna**-kohdassa **Asenna**.

   > [!div class="mx-imgBorder"] 
   > ![Valitse Asenna](./media/embed-teams-app/test-distribute-app.png "Valitse Asenna")

10. Valitse ryhmä, johon haluat asentaa sovelluksen, ja valitse sitten **Asenna**.

    > [!div class="mx-imgBorder"] 
    > ![Lisää ryhmän asennukseen](./media/embed-teams-app/new-app-add-to-team.png "Lisää ryhmän asennukseen")
11. Jos haluat lisätä kyseisen sovelluksen esiintymän kanavalle heti, valitse kanava, johon haluat käyttää sovellusta, ja valitse **Määritä**.

    > [!div class="mx-imgBorder"] 
    > ![Valitse Määritä](./media/embed-teams-app/app-now-available.png "Valitse Määritä")

12. Valitse **Tallenna**.

## <a name="add-the-app-as-a-tab"></a>Lisää sovellus väli lehti

Jos haluat lisätä sovelluksen väli lehdeksi mihin tahansa kanavaan tai keskusteluun, valitse **+** ja valitse sitten ryhmäsi **väli lehdet** -kohdasta sovelluksesi. 

> [!div class="mx-imgBorder"] 
> ![Lisää sovellus väli lehdelle](./media/embed-teams-app/add-app-as-tab.png "Lisää sovellus väli lehdelle")

Sovellus näkyy nyt väli lehdellä.

> [!div class="mx-imgBorder"] 
> ![Sovellus väli lehdeltä](./media/embed-teams-app/app-as-tab.png "Sovellus väli lehdeltä")

### <a name="see-also"></a>Katso myös
[Tervetuloa Microsoft Teamsille](https://docs.microsoft.com/MicrosoftTeams/teams-overview)<br />
[Järjestelmänvalvojille: sovelluksen upottaminen Microsoft Teamsissa](https://docs.microsoft.com/power-platform/admin/share-app-teams)
