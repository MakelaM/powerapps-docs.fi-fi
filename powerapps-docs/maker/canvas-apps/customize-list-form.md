---
title: SharePoint-luettelolomakkeen mukauttaminen PowerAppsin avulla | Microsoft Docs
description: Käytä PowerAppsia luettelolomakkeen mukauttamiseksi SharePointissa.
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 02/05/2018
ms.author: anneta
ms.openlocfilehash: 34c4e4126015f9a5f53ef6f07c9c66e4a4141db0
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="customize-a-sharepoint-list-form-using-powerapps"></a>SharePoint-luettelon mukauttaminen PowerAppsin avulla

Nyt voit mukauttaa helposti mitä tahansa SharePoint-luettelolomaketta PowerAppsissa. Voit tehdä nyt monia InfoPathissa tekemiäsi SharePoint-luettelolomakkeiden mukauttamistoimintoja selaimen sisällä PowerAppsissa. Lisäksi PowerApps antaa mahdollisuuden tehdä paljon muutakin.

PowerApps on integroitu suoraan SharePointiin. Sinun ei tarvitse ladata toista sovellusta tietokoneeseesi. PowerAppsin avulla voit luoda monimutkaisesti muokattuja lomakkeita kirjoittamatta koodia. Kun lomakkeet julkaistaan, ne upotetaan SharePoint-luetteloon ja ne ovat luettelon kaikkien käyttäjien käytettävissä.

Koska PowerApps on integroitu saumattomasti SharePointiin, lomakkeita ei tarvitse hallita kahdesta paikasta: oikeudet peritään ja niitä hallitaan SharePointin kautta. Mikä parasta, koska PowerApps on integroitu SharePointiin, voit käyttää monia tehokkaita ominaisuuksia, kuten analytiikkaraportteja, helppoja ehdollisen muotoilun ”osoita ja napsauta” -sääntöjä sekä yhteyksiä muihin tietolähteisiin.

Oletko valmis mukauttamaan? Aloitetaan!

## <a name="create-a-custom-list-form-app-in-powerapps"></a>Mukautetun luettelolomakesovelluksen luominen PowerAppsissa

> [!NOTE]
> **Mukauta lomakkeita** -vaihtoehto ei ole käytettävissä tai se ei välttämättä toimi oikein, jos SharePoint-luettelo sisältää tietotyyppejä, joita PowerApps ei tue.

Napsauta tai napauta SharePoint-luettelon komentopalkissa **PowerApps** ja napsauta tai napauta **Mukauta lomakkeita**. Toiminto avaa PowerApps Studion selaimessa, jossa PowerApps luo yhden näytön lomakesovelluksen seuraavan esimerkin mukaan.

![Yhden näytön lomakesovellus](./media/customize-list-form/list-form-app.png)

Voit palata SharePoint-luetteloosi milloin tahansa napsauttamalla tai napauttamalla **Takaisin SharePointiin** PowerApps Studion vasemmassa ylälaidassa.

## <a name="customize-the-list-form"></a>Luettelolomakkeen mukauttaminen

PowerApps tarjoaa useita tapoja lomakkeen mukauttamiseen. Seuraavassa on joitakin esimerkkejä:

* [Muuta kokoa ja suuntaa](set-aspect-ratio-portrait-landscape.md)
* [Muotoile tekstiä](controls/properties-text.md)
* [Lisää kuvia](add-images-pictures-audio-video.md) ja [kaavioita](use-line-pie-bar-chart.md)
* [Lisää mukautettu tiedon vahvistus](functions/function-validate.md)
* [Lisää sääntöjä](working-with-rules.md)
* [Luo lisänäkymiä](https://powerapps.microsoft.com/blog/separate-custom-forms/)

Tämän havainnollistamiseksi oletamme, että lomakkeessasi on **AccountID**-kenttä, jota et halua näkyviin.

![Valitse AccountID-kenttä](./media/customize-list-form/select-card.png)

Kentän piilottaminen on helppoa PowerAppsissa – sinun tarvitsee vain tyhjentää **AccountID**-valintaruutu lomakkeen mukauttamisasetuksissa.

![Tyhjennä AccountID-valintaruutu](./media/customize-list-form/checkbox.png)

Näet vaiheittaiset ohjeet kenttien piilottamiseen sekä muiden lomakemuutosten tekemiseen kohdasta [Lomakkeiden mukauttaminen PowerAppsissa](customize-forms-sharepoint.md). Näet täydellisen luettelon resursseista [Microsoft PowerApps -tiedostoista](https://docs.microsoft.com/powerapps/).

## <a name="save-and-publish-the-list-form-back-to-sharepoint"></a>Tallenna ja julkaise luettelolomake takaisin SharePointiin

1. Kun olet valmis, napsauta tai napauta **Tiedosto** ja sitten **Tallenna**. Tämä tallentaa muutoksesi PowerApps-lomakesovellukseen.

1. Julkaise lomakkeesi takaisin SharePointiin muiden käytettäväksi valitsemalla **Julkaise SharePointiin**. Sinun ei tarvitse huolehtia lomakkeen jakamisesta. Lomake perii käyttöoikeudet SharePoint-luettelosta.

    ![Julkaise SharePointiin](./media/customize-list-form/publish-to-sharepoint.png)  

## <a name="view-your-list-form-in-sharepoint"></a>Luettelolomakkeen näyttäminen SharePointissa

1. Näet mukautetun lomakkeesi napsauttamalla tai napauttamalla **Takaisin SharePointiin** ja sitten mitä tahansa kohdetta SharePoint-luettelossa. Lomake avautuu selainikkunan oikeaan laitaan.

    ![Lomakkeen avaaminen sisäisesti SharePointissa](./media/customize-list-form/list-form-open.png)

1. Jos haluat [mukauttaa lomaketta enemmän](sharepoint-form-integration.md), napsauta tai napauta **Mukauta** ja tee haluamasi muutokset. Muista tallentaa muutokset, kun olet valmis.

    ![Mukauta-painike](./media/customize-list-form/customize-button.png)

    Voit mukauttaa ja tallentaa niin monta kertaa kuin haluat, mutta muutoksesi eivät näy SharePointissa ennen kuin napsautat tai napautat **Julkaise SharePointissa**.

## <a name="toggle-between-using-the-default-sharepoint-form-and-the-custom-form"></a>SharePoint-oletuslomakkeen ja mukautetun lomakkeen välillä vaihtaminen

1. Napsauta tai napauta SharePoint-luettelostasi **Asetukset**, **Luetteloasetukset** ja sitten **Lomakeasetukset**.

1. Napsauta tai napauta **Lomakeasetukset**-sivulla yhtä seuraavista ja napsauta tai napauta **OK**.

    * **Käytä oletusarvoista SharePoint-lomaketta** – SharePoint käyttää SharePoint-oletuslomaketta luettelossasi.

    * **Käytä PowerAppsissa luotua mukautettua lomaketta** – SharePoint käyttää PowerAppsissa mukauttamaasi lomaketta. (Voit vaihtoehtoisesti julkaista lomakkeen uudelleen PowerApps Studion **Tallenna**-sivulta.)

    Voit siirtyä asetusten välillä tarpeen mukaan.

    ![Lomakkeen asetusvaihtoehdot](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-list-form"></a>Mukautetun luettelolomakkeen poistaminen

1. Napsauta tai napauta SharePoint-luettelostasi **Asetukset**, **Luetteloasetukset** ja sitten **Lomakeasetukset**.

1. Napsauta tai napauta **Lomakeasetukset**-sivulla **Käytä oletusarvoista SharePoint-lomaketta** ja napsauta tai napauta kohdassa **Käytä PowerAppsissa luotua mukautettua lomaketta** -kohdassa **Poista mukautettu lomake**. Toiminto poistaa mukautetun lomakkeen, jonka loit PowerAppsissa, ja lomakkeesi palautetaan oletusarvoiseen SharePoint-muotoon.

    ![Poista mukautettu lomake](./media/customize-list-form/use-default-sharepoint.png)

## <a name="top-questions-about-list-form-customization"></a>Yleisimmät kysymykset luettelolomakkeen mukauttamisesta

### <a name="customizing-forms-versus-creating-apps"></a>Lomakkeiden mukauttaminen verrattuna sovellusten luomiseen

**K:** Miten mukautettu luettelo eroaa erillisestä sovelluksesta, jonka luon SharePointista tai PowerAppsista?

**V:** SharePointista luomasi luettelolomakesovellus on erityisen tyyppinen PowerApps-sovellus, jota voidaan käyttää vain SharePoint-luettelossa. Nämä luettelolomakesovellukset eivät näy sovellusluettelossasi PowerApps Studiossa tai PowerApps Mobilessa, etkä voi suorittaa niitä SharePoint-luettelon ulkopuolella.

**K:** Milloin minun tulisi luoda mukautettu luettelolomake ja milloin erillinen sovellus?

**V:** Jos haluat käyttäjiesi käyttävän lomaketta SharePointilla ja haluat mukauttaa sitä, miten he luovat, tarkastelevat tai muokkaavat luettelokohtia, suosittelemme mukautetun luettelolomakkeen luomista Sharepointista. Jos haluat luoda täysin mukautettavan kokemuksen käyttäjillesi, jotta he voivat käyttää sitä SharePoint-sivustosta riippumatta, suosittelemme erillisen sovelluksen luomista.

**K:** Voinko mukauttaa luettelolomakkeen ja luoda erillisen sovelluksen samalle luettelolle?

**V:** Kyllä. Erilliset sovellukset ja mukautetut luettelot ovat toisistaan riippumattomia. Voit mukauttaa ja hallita niitä erillisinä.

**K:** Ovatko luettelolomakkeen mukauttamisen ja erillisen sovelluksen mukauttamisen ominaisuudet samat?

**V:** Kyllä. Voit [lisätä ja määrittää ohjausobjekteja](add-configure-controls.md), [yhdistää käytettävissä oleviin tietolähteisiin](add-data-connection.md) ja [lisätä omia tietolähteitäsi](../canvas-apps/register-custom-api.md) aivan kuten käyttämällä erillisiä sovelluksiakin.

**K:** Voinko luoda mukautettuja luettelolomakkeita muussa ympäristössä kuin organisaationi oletusympäristössä?

**V:** Et. Tällä hetkellä voit luoda mukautettuja luettelolomakkeita vain organisaatiosi oletusarvoisessa PowerApps-ympäristössä. Et voi luoda mukautettuja luettelolomakkeita toisessa ympäristössä tai siirtää niitä toiseen ympäristöön.

### <a name="managing-your-custom-list-form"></a>Mukautetun luettelolomakkeen hallinta

**K:** Miten saan luettelolomakkeeseeni suoran linkin, jonka voin jakaa muiden kanssa?

**V:** Avaa lomake SharePoint-luettelossa ja napsauta tai napauta **Kopioi linkki**.

**K:** Voinko päivittää luettelolomakkeeni niin, että muut eivät näe muutoksia?

**V:** Kyllä. Voit tehdä muutoksia lomakkeeseesi ja tallentaa niin monta kertaa kuin haluat, mutta muutoksesi eivät näy muille, ennen kuin napsautat tai napautat **[Julkaise SharePointiin](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint)**.

**K:** Jos teen virheen mukauttaessani luettelolomaketta, voinko palauttaa aiemman version?

**V:** Kyllä. Jos teet muutoksia lomakkeeseen, tallennat muutokset ja huomaat myöhemmin tehneesi virheen, voit palauttaa aiemman version lomakkeesta käyttämällä PowerAppsia:

1. Napsauta tai napauta SharePoint-luettelon komentopalkissa **PowerApps** ja napsauta tai napauta **Mukauta lomakkeita**.

1. Napsauta tai napauta PowerApps Studiossa **Tiedosto** ja sitten **Tallenna**-sivulla **Näytä kaikki versiot**. **Versiot**-sivu avautuu uudessa selaimen välilehdessä.

    > [!NOTE]
    > Jos et näe **Näytä kaikki versiot** -painiketta, napsauta tai napauta **Tallenna**. Painikkeen pitäisi tulla näkyviin.

1. Palaa toisen selainvälilehden **Tallenna**-sivulle sulkematta **Versiot**-sivua tai selaimen välilehteä. Napsauta tai napauta sitten vasemman siirtymisruudun ylälaidassa olevaa nuolta ja valitse **Takaisin SharePointiin** lomakkeen avaamiseksi ja PowerApps Studion sulkemiseksi.

1. Palaa toisen selainvälilehden **Versiot**-sivulle, etsi palautettava versio ja napsauta **Palauta**.

    > [!NOTE]
    > Jos saat virheviestin, jossa kerrotaan, että palauttaminen epäonnistui, koska lomake on toisen käyttäjän lukitsema, odota, kunnes lukitus poistetaan, ja yritä uudelleen.

**K:** Voinko siirtää mukautetun luetteloni yhdestä luettelosta toiseen?

**V:** Et. Tätä toimintoa ei tueta tällä hetkellä.

### <a name="administering-custom-list-forms"></a>Mukautettujen luettelolomakkeiden hallinnointi

**K:** Miten voin jakaa mukautetun luettelolomakkeeni muiden kanssa?

**V:** Sinun ei tarvitse jakaa lomaketta. Lomake perii käyttöoikeudet SharePoint-luettelosta. Kun olet tehnyt kaikki muutokset lomakkeeseen, [julkaise se takaisin SharePointiin](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint), jotta muut voivat käyttää sitä.

**K:** Kuka voi mukauttaa luettelolomakkeita?

**V:** Kuka tahansa, jolla on SharePoint-käyttöoikeudet liitetyn luettelon hallitsemiseen, suunnittelemiseen tai muokkaamiseen.

**K:** Tarvitsenko PowerApps-käyttöoikeuden mukautettujen luettelolomakkeiden luomiseen tai käyttämiseen?

**V:** Jos sinulla on [Office 365 -sopimus, joka sisältää PowerAppsin](../../administrator/pricing-billing-skus.md#licenses), voit luoda ja käyttää mukautettuja luettelolomakkeita.

**K:** Mitä tapahtuu, kun vieraskäyttäjät käyttävät luetteloa, jossa on mukautettu lomake?

**V:** Vieraskäyttäjät saavat virheviestin, jos he yrittävät käyttää PowerAppsin avulla mukautettua luettelolomaketta.

**K:** Miten saan järjestelmänvalvojana luettelon kaikista organisaationi mukautetuista lomakkeista?

**V:** Jos olet PowerAppsin vuokraajajärjestelmänvalvoja tai sinulla on ympäristön järjestelmänvalvojan oikeudet organisaatiosi oletusarvoiseen PowerApps-ympäristöön, toimi seuraavasti:

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com) ja valitse ympäristöluettelosta organisaatiosi oletusympäristö.

1. Napsauta tai napauta oletusympäristösivun ylälaidassa **Resurssit**.

1. Etsi sovellusluettelosta sovelluksia, joilla on **SharePoint-lomake**-sovellustyyppi – nämä ovat mukautettuja lomakkeita.

    ![Mukautettujen lomakkeiden luettelo](./media/customize-list-form/all-customized-forms.png)
