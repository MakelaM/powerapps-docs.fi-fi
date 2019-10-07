---
title: SharePoint-luettelolomakkeen mukauttaminen | Microsoft Docs
description: PowerAppsin avulla voit mukauttaa lomaketta, jonka avulla käyttäjät luovat ja päivittävät SharePoint-luettelon merkintöjä.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/04/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 60d4fb21bc2f298b1dd2ce37c3e25f5355e881cb
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993145"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>SharePoint-luettelolomakkeen mukauttaminen PowerAppsin avulla

Voit helposti mukauttaa SharePoint-luettelon lomaketta avaamalla PowerAppsin selaimessa. Sinun ei tarvitse kirjoittaa perinteistä koodia, kuten C#, tai ladata toista sovellusta, kuten InfoPath. Kun julkaiset tekemäsi muutokset, lomake upotetaan SharePoint-luetteloon kaikkien sen käyttäjien käytettäväksi. PowerAppsissa voit myös tarkastella analyysiraportteja, luoda helposti ehdollisen muotoilun ja muodostaa yhteyden muihin tietolähteisiin.

Tämän artikkelin ohjeita noudattamalla luot yksinkertaisen luettelon, jonka avulla näet, miten mukauttaminen toimii, ja voit sitten käyttää samoja menetelmiä omassa luettelossasi.

> [!NOTE]
> Jos **Mukauta lomakkeita** -vaihtoehto ei ole käytettävissä tai se ei toimi oikein luettelosi kanssa, siinä voi olla tietotyyppejä, joita [PowerApps ei tue](connections/connection-sharepoint-online.md#known-issues). Et myöskään voi siirtää lomakettasi toiseen luetteloon tai [ympäristöön](working-with-environments.md).

## <a name="create-a-list"></a>Luo lista

Luo SharePoint-sivustossa lista ja lisää sitten nämä sarakkeet tähän listaan:

- **Tiedot** (kyllä/ei)
- **Hinta** (valuutta)
- **Saatavuus** (päivämäärä ilman aikaa)
- **Väri** (vaihtoehto)

> [!div class="mx-imgBorder"]
> ![Valitse sivuston sisältö > Uusi > luettelo, kirjoita luettelon nimi ja valitse Luo. Valitse kullekin sarakkeelle Lisää sarake, määritä luettelosta tyyppi (kyllä/ei, valuutta, päivä määrä, vaihto ehto), määritä listan nimi (tiedot, hinta, saatavuus, väri) ja valitse Tallenna. ](./media/customize-list-form/create-list.gif)

## <a name="open-the-form"></a>Avaa lomake

1. Valitse komento palkissa **Powerapps**ja valitse sitten **Mukauta lomaketta**.

    PowerApps Studio avautuu samaan selaimen välilehteen.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

> [!div class="mx-imgBorder"]
> ![Valitse komento palkissa PowerApps ja valitse sitten Mukauta lomaketta. PowerApps Studio avautuu samaan selaimen välilehteen. Jos Tervetuloa PowerApps Studio-valinta ikkuna avautuu, valitse Ohita. ](./media/customize-list-form/create-form.gif)

## <a name="move-and-remove-a-field"></a>Kentän siirtäminen ja poistaminen

1. Vedä **käytettävyyskenttä** kenttä luettelon alareunaan.

    Kentät näkyvät määrittämässäsi järjestyksessä.

1. Vie hiiren osoitin **Liitteet** -kentän päälle, valitse esiin tulevassa kolme pistettä (...) ja valitse sitten **Poista**.

    Määrittämäsi kenttä katoaa lomakkeesta.

> [!div class="mx-imgBorder"]
> ![Vedä Käytettävyyskenttä kenttä luettelon alareunaan. Vie hiiren osoitin liitteet-kentän päälle, valitse esiin tulevassa kolme pistettä (...) ja valitse sitten Poista. ](./media/customize-list-form/move-remove-fields.gif)

## <a name="set-conditional-formatting"></a>Ehdollisen muotoilun määrittäminen

Voit määrittää kentät **Hinta**, **Saatavuus** ja **Värit** näytettäviksi vain, jos **Tiedot**-asetuksena on kyllä.

1. Laajenna vasemmassa siirtymis palkissa **Details_DataCard1**ja merkitse **Datacardvalue**-kohdan lopussa näkyvä numero muistiin.

1. Valitse **väri**-, **saatavuus**-ja **hinta** korttien **Visible** -ominaisuudeksi Tämä kaava (korvaa tarvittaessa numero, joka on edellisessä vaiheessa huomasit):

    **If (DataCardValue2. Value = True, True)**

1. Pidä Alt-näppäintä painettuna ja valitse **Tiedot**-vaihtopainike (napsauttamalla tai napauttamalla sitä) useita kertoja.

    Kolme määrittämääsi kenttää tulevat näkyviin korttiin ja katoavat siitä.

> [!div class="mx-imgBorder"]
> ![Kirjoita vasemmassa siirtymis palkissa DataCardValue-arvon lopussa näkyvä numero. Valitse väri-, saatavuus-ja hinta-korttien näkyvyys-ominaisuudeksi Tämä kaava. Pidä Alt-näppäintä painettuna ja valitse tiedot-ohjaus objekti useita kertoja. ](./media/customize-list-form/conditional-format.gif)

## <a name="save-and-publish-the-form"></a>Tallenna ja julkaise lomake

1. Avaa **Tiedosto**-valikko, valitse **Tallenna** ja valitse sitten **Julkaise SharePointiin** kahdesti.

1. Valitse vasemmassa yläkulmassa, paluunuoli ja valitse sitten **Takaisin SharePointiin**.

> [!div class="mx-imgBorder"]
> ![Avaa tiedosto-valikko, valitse Tallenna ja valitse sitten Julkaise SharePointiin kahdesti. Valitse vasemmasta yläkulmasta takaisin-nuoli ja valitse sitten takaisin SharePointiin. ](./media/customize-list-form/save-form.gif)

## <a name="further-customize-your-form"></a>Lomakkeen lisä mukauttaminen

1. Avaa luettelosi, valitse komento palkissa **Uusi** ja valitse sitten **Mukauta** lähellä lomakkeen yläreunaa.

1. Mukauta lomakkeesi monella eri tavalla, kuten näissä aiheissa:

    - Muuta sen kokoa, suuntaa tai molempia (esimerkiksi [lomakkeen leventämistä varten](set-aspect-ratio-portrait-landscape.md)).
    - [Mukauta yhtä tai useampaa korttia](working-with-cards.md) (esimerkiksi muuta kortin näyttö teksti tai syöte-ohjaus objekti).
    - Luo [hakukenttä](sharepoint-lookup-fields.md).

    Lisätietoja: [Tutustu SharePoint Forms-integrointiin](sharepoint-form-integration.md).

## <a name="use-the-default-form"></a>Oletuslomakkeen käyttäminen

1. Avaa asetussivu luettelossasi SharePointissa (valitsemalla rataskuvake lähellä oikeaa yläkulmaa) ja valitse sitten **Luetteloasetukset**.

2. Valitse **Yleiset asetukset** -kohdassa **Lomakeasetukset**.

3. Valitse **Lomakeasetukset**-sivulla jokin näistä vaihtoehdoista ja valitse sitten **OK**.

    - **Käytä oletusarvoista SharePoint-lomaketta** – Kun käyttäjä avaa luettelosi ja valitsee komentopalkissa **Uusi**, luettelon oletuslomake tulee näkyviin.

    - **Käytä PowerAppsissa luotua mukautettua lomaketta** – Kun käyttäjä avaa luettelosi ja valitsee komentopalkissa **Uusi**, mukautettu lomakkeesi tulee näkyviin. (Vaihtoehtoisesti voit julkaista lomakkeen uudelleen PowerAppsissa.)

    Voit siirtyä asetusten välillä tarpeen mukaan.

    ![Lomakkeen asetusvaihtoehdot](./media/customize-list-form/form-settings.png)

## <a name="delete-the-custom-form"></a>Poista mukautettu lomake

1. Avaa asetussivu luettelossasi SharePointissa (valitsemalla rataskuvake lähellä oikeaa yläkulmaa) ja valitse sitten **Luetteloasetukset**.

1. Valitse **Yleiset asetukset** -kohdassa **Lomakeasetukset**.

1. Valitse **Lomakeasetukset**-sivulla **Käytä oletusarvoista SharePoint-lomaketta** ja valitse sitten **Poista mukautettu lomake**.

    ![Poista mukautettu lomake](./media/customize-list-form/use-default-sharepoint.png)

## <a name="q--a"></a>Kysymyksiä ja vastauksia

### <a name="forms-vs-apps"></a>Lomakkeet ja sovellukset

**Q** Miten mukautettu lomake eroaa erillisestä sovelluksesta, jonka luon SharePointista tai Powerappista?

**ON** Jos mukautat SharePoint-luetteloiden lomaketta, lomake ei näy sovelluksena PowerApps Studio tai PowerApps Mobilessa. Voit avata lomakkeen vain luettelosta, jota varten olet luonut sen.

**Q** Milloin kannattaa mukauttaa lomaketta SharePoint-luetteloiden tietojen hallintaa varten, ja milloin minun tulee luoda itsenäinen sovellus?

**ON** Mukauta lomaketta, jos haluat käyttäjien hallitsevan tietoja poistumatta SharePointista (esimerkiksi Työpöytä selaimessa). Luo sovellus, jos haluat käyttäjien hallitsevan tietoja SharePointin ulkopuolella (esimerkiksi mobiililaitteessa).

**Q** Voinko mukauttaa lomaketta ja luoda sovelluksen samalle luettelolle?

**ON** Kyllä.

**Q** Voinko mukauttaa listaa ja luoda sovelluksen käyttämällä samoja ominaisuuksia?

**ON** Kyllä.

**Q** Voinko mukauttaa lomaketta ympäristössä, joka on muu kuin organisaation oletus ympäristö?

**ON** Ei.

### <a name="manage-your-custom-form"></a>Mukautetun lomakkeen hallinta

**Q** Kuinka voin helposti kertoa lomakkeeni muille?

**ON** Avaa lomake, valitse **Kopioi linkki**ja lähetä sitten linkki kenelle tahansa, jolle haluat käyttää lomaketta.

**Q** Voinko päivittää lomakkeeni ilman, että muutokset näkyvät muille?

**ON** Kyllä. Voit muuttaa lomakettasi ja tallentaa niin monta kertaa kuin haluat, mutta muutoksesi eivät näy muille, ennen kuin valitset **Julkaise SharePointiin** kahdesti.

**Q** Jos mukautan lista lomaketta ja teet virheen, Voinko palauttaa aiemman version?

**ON** Kyllä.

1. Avaa luettelosi, valitse komentopalkissa **PowerApps** ja valitse sitten **Mukauta lomakkeita**.

1. Valitse PowerApps Studiossa **Tiedosto** ja valitse sitten **Näytä kaikki versiot**. **Versiot**-sivu avautuu uudessa selaimen välilehdessä.

    > [!NOTE]
    > Jos **Näytä kaikki versiot** -painiketta ei ole, valitse **Tallenna**. Painikkeen pitäisi tulla näkyviin.

1. Palaa toisen selainvälilehden **Tallenna**-sivulle sulkematta **Versiot**-sivua tai selaimen välilehteä. Napsauta tai napauta sitten vasemman siirtymisruudun ylälaidassa olevaa nuolta ja valitse **Takaisin SharePointiin** lomakkeen avaamiseksi ja PowerApps Studion sulkemiseksi.

1. Palaa toisen selainvälilehden **Versiot**-sivulle, etsi palautettava versio ja valitse **Palauta**.

    > [!NOTE]
    > Jos näyttöön tulee virhe sanoma, joka ilmoittaa, että palautus epäonnistui, koska toinen käyttäjä on lukinnut lomakkeen, odota, kunnes käyttäjä avaa lomakkeen, ja yritä sitten uudelleen.

**Q** Voinko siirtää lomakkeeni yhdestä listasta toiseen?

**ON** Ei.

### <a name="administer-your-custom-form"></a>Mukautetun lomakkeen hallinnointi

**Q** Ohjevalikko lomakkeen jakamisen?

**ON** Sinun ei tarvitse luovuttaa lomaketta – lomake perii käyttö oikeudet SharePoint-listasta. Kun olet tehnyt kaikki muutokset lomakkeeseen, [julkaise se takaisin SharePointiin](customize-list-form.md#save-and-publish-the-form), jotta muut voivat käyttää sitä.

**Q** Kuka voi mukauttaa lomakkeita?

**ON** Kuka tahansa, jolla on SharePoint-käyttö oikeudet, hallita, suunnitella tai muokata liittyvää listaa.

**Q** Tarvitsenko PowerApps-käyttö oikeuden mukautettujen lista lomakkeiden luomiseen tai käyttämiseen?

**ON** Tarvitset [Office 365-paketin, joka sisältää Powerappsin](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus#licenses).

**Q** Mitä tapahtuu, kun vieras käyttäjät käyttävät mukautettua lomaketta sisältävän listan?

**ON** Vieras käyttäjät saavat virhe sanoman, jos he yrittävät käyttää Powerappsin avulla muokattua lista lomaketta.

**Q** Miten saan järjestelmänvalvojana luettelon kaikista mukautetusta lomakkeista organisaatiossani?

**ON** Jos olet Powerappsin vuokraajajärjestelmänvalvoja tai sinulla on ympäristön järjestelmänvalvojan oikeudet organisaatiosi oletusarvoiseen PowerApps-ympäristöön, toimi seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com) ja valitse ympäristöluettelosta organisaatiosi oletusympäristö.

1. Valitse oletusympäristösivun ylälaidassa **Resurssit**.

1. Etsi sovellus listasta sovelluksia, joissa on **SharePoint-lomake** -sovellus tyyppi – Nämä ovat mukautettuja lomakkeita.

    ![Mukautettujen lomakkeiden luettelo](./media/customize-list-form/all-customized-forms.png)
