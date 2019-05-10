---
title: SharePoint-luettelolomakkeen mukauttaminen | Microsoft Docs
description: PowerAppsin avulla voit mukauttaa lomaketta, jonka avulla käyttäjät luovat ja päivittävät SharePoint-luettelon merkintöjä.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 04/04/2019
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 66fe60c0d74c86705615522621d8f277fcc343ae
ms.sourcegitcommit: dbd922de8f2e97a478df64e7e9ba33b48574af5c
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/06/2019
ms.locfileid: "65088187"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>SharePoint-luettelolomakkeen mukauttaminen PowerAppsin avulla

Voit helposti mukauttaa SharePoint-luettelon lomaketta avaamalla PowerAppsin selaimessa. Sinun ei tarvitse kirjoittaa perinteistä koodia, kuten C#, tai ladata toista sovellusta, kuten InfoPath. Kun julkaiset tekemäsi muutokset, lomake upotetaan SharePoint-luetteloon kaikkien sen käyttäjien käytettäväksi. PowerAppsissa voit myös tarkastella analyysiraportteja, luoda helposti ehdollisen muotoilun ja muodostaa yhteyden muihin tietolähteisiin.

Tämän artikkelin ohjeita noudattamalla luot yksinkertaisen luettelon, jonka avulla näet, miten mukauttaminen toimii, ja voit sitten käyttää samoja menetelmiä omassa luettelossasi.

> [!NOTE]
> Jos **Mukauta lomakkeita** -vaihtoehto ei ole käytettävissä tai se ei toimi oikein luettelosi kanssa, siinä voi olla tietotyyppejä, joita [PowerApps ei tue](connections/connection-sharepoint-online.md#known-issues). Et myöskään voi siirtää lomakettasi toiseen luetteloon tai [ympäristöön](working-with-environments.md).

## <a name="create-a-list"></a>Luo luettelo

SharePoint-sivuston Luo luettelo ja lisää sitten näiden sarakkeiden luetteloon:

- **Tiedot** (kyllä/ei)
- **Hinta** (valuutta)
- **Saatavuus** (päivämäärä ilman aikaa)
- **Väri** (vaihtoehto)

> [!div class="mx-imgBorder"]
> ![Valitse sivuston sisältö > Uusi > luettelon, kirjoita Luettelonimi ja valitse Luo. Kussakin sarakkeessa, valitse Lisää sarake, Määritä luettelotyypin (Kyllä/ei, valuutta, päivämäärä, valinta), Määritä Luettelonimi (tiedot, hinta, käytettävyyteen, väri) ja valitse Tallenna.](./media/customize-list-form/create-list.gif)

## <a name="open-the-form"></a>Avaa lomake

1. Valitse komentopalkissa **Powerappsin**, ja valitse sitten **mukauttaminen**.

    PowerApps Studio avautuu samaan selaimen välilehteen.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

> [!div class="mx-imgBorder"]
> ![Valitse komentopalkissa PowerApps ja valitse Mukauta lomaketta. PowerApps Studio avautuu samaan selaimen välilehteen. Jos Tervetuloa PowerApps Studio-valintaikkuna avautuu, valitse Ohita.](./media/customize-list-form/create-form.gif)

## <a name="move-and-remove-a-field"></a>Siirrä ja Poista kenttä

1. Vedä **Käytettävyysryhmän** kentän kentät-luettelon loppuun.

    Kentät näkyvät siinä järjestyksessä, jotka olet määrittänyt.

1. Osoita **liitteet** kentän, valitse kolme pistettä (...), joka näkyy ja valitse sitten **poistaa**.

    Kenttä, jonka määrität katoaa lomakkeesta.

> [!div class="mx-imgBorder"]
> ![Vedä kenttiä luettelon loppuun käytettävyys-kenttä. Osoita liitteet-kenttä, valitse kolme pistettä (...), joka näkyy ja valitse sitten Poista.](./media/customize-list-form/move-remove-fields.gif)

## <a name="set-conditional-formatting"></a>Ehdollisen muotoilun määrittäminen

Voit määrittää kentät **Hinta**, **Saatavuus** ja **Värit** näytettäviksi vain, jos **Tiedot**-asetuksena on kyllä.

1. Laajenna vasemmassa siirtymispalkissa **Details_DataCard1**, ja Huomaa numero, joka näkyy lopussa **DataCardValue**.

1. Määritä **näkyvissä** -ominaisuuden **väri**, **Käytettävyysryhmän**, ja **hinta** kortit tämä kaava (korvaa, jos se on tarpeen, numero otsikkokohteelle, joka edellisessä vaiheessa):

    **Jos (DataCardValue2.Value = true, true)**

1. Pidä Alt-näppäintä painettuna ja valitse **Tiedot**-vaihtopainike (napsauttamalla tai napauttamalla sitä) useita kertoja.

    Kolme määrittämääsi kenttää tulevat näkyviin korttiin ja katoavat siitä.

> [!div class="mx-imgBorder"]
> ![Vasemmassa siirtymispalkissa Huomaa numero, joka näkyy DataCardValue lopussa. Ominaisuuden näkyvyyden väriä, käytettävyys ja hinta kortit tämä kaava. Pidä Alt-näppäintä ja valitse tiedot-ohjausobjektin useita kertoja.](./media/customize-list-form/conditional-format.gif)

## <a name="save-and-publish-the-form"></a>Tallenna ja julkaise lomake

1. Avaa **Tiedosto**-valikko, valitse **Tallenna** ja valitse sitten **Julkaise SharePointiin** kahdesti.

1. Valitse vasemmassa yläkulmassa, paluunuoli ja valitse sitten **Takaisin SharePointiin**.

> [!div class="mx-imgBorder"]
> ![Avaa tiedosto-valikon, valitse Tallenna ja valitse sitten Julkaise SharePointiin kahdesti. Vasemmassa yläkulmassa Valitse takaisin-nuoli ja valitse sitten takaisin SharePointiin.](./media/customize-list-form/save-form.gif)

## <a name="further-customize-your-form"></a>Mukauttaa lomaketta enemmän

1. Avaa luettelostasi, valitse **uusi** -komennon ja sitten Valitse **Mukauta** yläosan lomakkeen.

1. Mukauta lomakettasi eri tavoin, kuten tiedot, joita nämä ohjeaiheissa:

    - Muuta sen kokoa, suuntaa tai molempia (esimerkiksi [lomakkeen leventämistä varten](set-aspect-ratio-portrait-landscape.md)).
    - [Mukauta yhdelle tai useammalle](working-with-cards.md) (esimerkiksi muuttaa kortin Näytä teksti- tai syöte-ohjausobjekti).
    - Luo [hakukenttä](sharepoint-lookup-fields.md).

    Lisätietoja: [SharePoint-lomakkeiden integrointi](sharepoint-form-integration.md).

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

**K:** Miten mukautetun lomakkeen eroaa erillisestä sovelluksesta, jonka luon SharePointista tai Powerappsista?

**A:** Jos mukautat lomakkeen SharePoint-luetteloa varten, lomakkeen ei näy sovellusta PowerApps Studio tai PowerApps Mobilessa. Voit avata lomakkeen vain luettelosta, jota varten olet luonut sen.

**K:** Kun lomakkeen SharePoint-luettelon tiedonhallintaa varten tulee mukauttaminen ja milloin minun tulisi luoda erillisen sovelluksen?

**A:** Lomakkeen mukauttaminen, jos haluat käyttäjien tietojen hallitsemiseksi SharePoint poistumatta (esimerkiksi selaimessa työpöydän). Luo sovellus, jos haluat käyttäjien hallitsevan tietoja SharePointin ulkopuolella (esimerkiksi mobiililaitteessa).

**K:** Voit mukauttaa lomaketta ja luoda sovelluksen samalle luettelolle?

**A:** Kyllä.

**K:** Voit mukauttaa luettelon ja luo sovellus käyttämällä samoja ominaisuuksia?

**A:** Kyllä.

**K:** Oletusympäristön muussa ympäristössä lomakkeen mukauttaminen organisaationi

**A:** Ei.

### <a name="manage-your-custom-form"></a>Mukautetun lomakkeen hallinta

**K:** Miten voin helposti jakaa lomakkeen muiden kanssa?

**A:** Avaa lomake, valitse **Kopioi linkki**, ja lähetä sitten linkin kaikille, joille haluat käyttää lomakkeen.

**K:** Lomakkeen päivittää tekemättä muut näkevät muutokseni

**A:** Kyllä. Voit muuttaa lomakettasi ja tallentaa niin monta kertaa kuin haluat, mutta muutoksesi eivät näy muille, ennen kuin valitset **Julkaise SharePointiin** kahdesti.

**K:** Jos voinko mukauttaa luettelolomakkeen ja tulee virhe, voinko palauttaa aiemman version?

**A:** Kyllä.

1. Avaa luettelosi, valitse komentopalkissa **PowerApps** ja valitse sitten **Mukauta lomakkeita**.

1. Valitse PowerApps Studiossa **Tiedosto** ja valitse sitten **Näytä kaikki versiot**. **Versiot**-sivu avautuu uudessa selaimen välilehdessä.

    > [!NOTE]
    > Jos **Näytä kaikki versiot** -painiketta ei ole, valitse **Tallenna**. Painikkeen pitäisi tulla näkyviin.

1. Palaa toisen selainvälilehden **Tallenna**-sivulle sulkematta **Versiot**-sivua tai selaimen välilehteä. Napsauta tai napauta sitten vasemman siirtymisruudun ylälaidassa olevaa nuolta ja valitse **Takaisin SharePointiin** lomakkeen avaamiseksi ja PowerApps Studion sulkemiseksi.

1. Palaa toisen selainvälilehden **Versiot**-sivulle, etsi palautettava versio ja valitse **Palauta**.

    > [!NOTE]
    > Jos saat virheviestin, että palauttaminen epäonnistui, koska lomake on toisen käyttäjän lukitsema Odota ja yritä sitten uudelleen.

**K:** Voin siirtää lomakkeen yhdestä luettelosta toiseen?

**A:** Ei.

### <a name="administer-your-custom-form"></a>Mukautetun lomakkeen hallinnointi

**K:** Miten voin jakaa lomakkeen?

**A:** Sinun ei tarvitse jakaa lomaketta – lomake perii käyttöoikeudet SharePoint-luettelosta. Kun olet tehnyt kaikki muutokset lomakkeeseen, [julkaise se takaisin SharePointiin](customize-list-form.md#save-and-publish-the-form), jotta muut voivat käyttää sitä.

**K:** Kuka voi mukauttaa lomakkeet?

**A:** Kuka tahansa, jolla hallinta, suunnittelemiseen tai muokkaamiseen liittyvä luettelo SharePoint-käyttöoikeudet.

**K:** Tarvitsenko PowerApps-käyttöoikeus, voit luoda tai käyttää mukautettuja luettelolomakkeita?

**A:** Sinun [Office 365-sopimus, joka sisältää Powerappsin](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus#licenses).

**K:** Mitä tapahtuu, kun vierailevien käyttäjien luettelo, jossa on mukautettua lomaketta?

**A:** Vieraskäyttäjät saavat virheviestin, jos he yrittävät käyttää luettelolomakkeen, joka on mukautettu Powerappsin avulla.

**K:** Järjestelmänvalvoja miten saan kaikkien mukautettujen lomakkeiden luettelo organisaationi?

**A:** Jos olet vuokraajan järjestelmänvalvoja, powerappsin, tai sinulla on ympäristön järjestelmänvalvojan oikeudet organisaatiosi oletusarvoisessa PowerApps-ympäristössä, toimi seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com) ja valitse ympäristöluettelosta organisaatiosi oletusympäristö.

1. Valitse oletusympäristösivun ylälaidassa **Resurssit**.

1. Sovellusten luettelo, Etsi sovellusluettelosta sovelluksia **SharePoint-lomaketta** sovellustyyppi – nämä ovat mukautettuja lomakkeita.

    ![Mukautettujen lomakkeiden luettelo](./media/customize-list-form/all-customized-forms.png)
