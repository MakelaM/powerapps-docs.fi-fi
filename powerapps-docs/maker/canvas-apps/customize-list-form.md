---
title: SharePoint-luettelolomakkeen mukauttaminen | Microsoft Docs
description: PowerAppsin avulla voit mukauttaa lomaketta, jonka avulla käyttäjät luovat ja päivittävät SharePoint-luettelon merkintöjä.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/11/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 218fb97f6cd523275c0ba296ea120d487cf67e4c
ms.sourcegitcommit: c26976af24a3e510e4eced78cf5c48cc2f71cae2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/02/2018
ms.locfileid: "48025667"
---
# <a name="customize-a-sharepoint-list-form-by-using-powerapps"></a>SharePoint-luettelolomakkeen mukauttaminen PowerAppsin avulla

Voit helposti mukauttaa SharePoint-luettelon lomaketta avaamalla PowerAppsin selaimessa. Sinun ei tarvitse kirjoittaa perinteistä koodia, kuten C#, tai ladata toista sovellusta, kuten InfoPath. Kun julkaiset tekemäsi muutokset, lomake upotetaan SharePoint-luetteloon kaikkien sen käyttäjien käytettäväksi. PowerAppsissa voit myös tarkastella analyysiraportteja, luoda helposti ehdollisen muotoilun ja muodostaa yhteyden muihin tietolähteisiin.

Tämän artikkelin ohjeita noudattamalla luot yksinkertaisen luettelon, jonka avulla näet, miten mukauttaminen toimii, ja voit sitten käyttää samoja menetelmiä omassa luettelossasi.

> [!NOTE]
> Jos **Mukauta lomakkeita** -vaihtoehto ei ole käytettävissä tai se ei toimi oikein luettelosi kanssa, siinä voi olla tietotyyppejä, joita [PowerApps ei tue](connections/connection-sharepoint-online.md#known-issues). Et myöskään voi siirtää lomakettasi toiseen luetteloon tai [ympäristöön](working-with-environments.md).

## <a name="prerequisites"></a>Edellytykset

Luo SharePoint-sivustossa luettelo, johon lisäät seuraavat sarakkeet:

- **Tuotenimi** (yksi tekstirivi)
- **Tiedot** (kyllä/ei)
- **Hinta** (valuutta)
- **Saatavuus** (päivämäärä ilman aikaa)
- **Väri** (vaihtoehto)

## <a name="open-the-form-in-powerapps"></a>Lomakkeen avaaminen PowerAppsissa

1. Avaa luomasi luettelo ja valitse komentopalkissa sitten **Uusi**.

    Lomake avautuu ja näyttää lisäämäsi kentät sekä kentät **Otsikko** ja **Liitteet**.

1. Valitse lähellä lomakkeen yläreunaa **Mukauta**.

    PowerApps Studio avautuu samaan selaimen välilehteen.

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

## <a name="hide-extra-fields"></a>Ylimääräisten kenttien piilottaminen

Näytön keskellä PowerApps näyttää lomakkeesi, mutta se sisältää joitakin kenttiä, joiden et tarvitse.

- Tyhjennä **Tiedot**-ruudussa **Otsikko**- ja **Liitteet**-kenttien valintaruudut.

    Nämä kentät katoavat lomakkeesta, ja vain sinun lisäämäsi kentät jäävät jäljelle.

    ![Kenttäluettelo](./media/customize-list-form/field-list.png)

## <a name="set-conditional-formatting"></a>Ehdollisen muotoilun määrittäminen

Voit määrittää kentät **Hinta**, **Saatavuus** ja **Värit** näytettäviksi vain, jos **Tiedot**-asetuksena on kyllä.

1. Valitse **Hinta**-kortti napsauttamalla tai napauttamalla sitä.

    ![Saatavuus-kortin valitseminen](./media/customize-list-form/select-card.png)

1. Valitse ominaisuusluettelossa **Visible**.

    ![Visible-ominaisuuden valitseminen](./media/customize-list-form/select-property.png)

1. Kirjoita tai liitä kaavariville tämä kaava:

    **If(DataCardValue3.Value = true, true)**

    ![Visible-ominaisuuden arvon määrittäminen](./media/customize-list-form/build-formula.png)

1. Toista kolme viimeistä vaihetta **Saatavuus**- ja **Väri**-korteille.

1. Pidä Alt-näppäintä painettuna ja valitse **Tiedot**-vaihtopainike (napsauttamalla tai napauttamalla sitä) useita kertoja.

    Kolme määrittämääsi kenttää tulevat näkyviin korttiin ja katoavat siitä.

1. (valinnainen) Mukauta lomakettasi useilla muilla tavoin, kuten näillä:

    - Muuta sen kokoa, suuntaa tai molempia (esimerkiksi [lomakkeen leventämistä varten](set-aspect-ratio-portrait-landscape.md)).
    - Lisää ohjausobjekti, jonka avulla käyttäjät voivat [ladata liitteitä](controls/properties-text.md).
    - Luo [hakukenttä](sharepoint-lookup-fields.md).

## <a name="save-publish-and-show-the-form"></a>Lomakkeen tallentaminen, julkaiseminen ja näyttäminen

1. Avaa **Tiedosto**-valikko, valitse **Tallenna** ja valitse sitten **Julkaise SharePointiin** kahdesti.

1. Valitse vasemmassa yläkulmassa, paluunuoli ja valitse sitten **Takaisin SharePointiin**.

1. Avaa mukautettu lomakkeesi valitsemalla komentopalkissa **Uusi**.

1. Voit piilottaa ja näyttää kolme viimeistä kenttää valitsemalla **Tiedot**-valintapainikkeen useita kertoja.

Jos haluat [mukauttaa lomaketta lisää](sharepoint-form-integration.md), avaa se, valitse **Mukauta** lähellä lomakkeen yläreunaa ja tee, tallenna ja julkaise haluamasi muutokset.

Jos luot vähintään yhden kohteen tällä lomakkeella, **Otsikko**-kenttä on tyhjä. Voit piilottaa tämän kentän muokkaamalla oletusnäkymää.

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

**K:** Miten mukautettu lomake eroaa erillisestä sovelluksesta, jonka luon SharePointista tai PowerAppsista?

**V:** Jos mukautat SharePoint-luettelon lomakkeen, lomake ei näy sovelluksena PowerApps Studiossa eikä PowerApps Mobilessa. Voit avata lomakkeen vain luettelosta, jota varten olet luonut sen.

**K:** Milloin minun pitäisi mukauttaa lomaketta SharePoint-luettelon tietojen hallintaa varten, ja milloin minun pitäisi luoda erillinen sovellus?

**V:** Mukauta lomaketta, jos haluat käyttäjien hallitsevan tietoja poistumatta SharePointista (esimerkiksi pöytäkoneen selaimessa). Luo sovellus, jos haluat käyttäjien hallitsevan tietoja SharePointin ulkopuolella (esimerkiksi mobiililaitteessa).

**K:** Voinko mukauttaa lomaketta ja luoda sovelluksen samalle luettelolle?

**V:** Kyllä.

**K:** Voinko mukauttaa luetteloa ja luoda sovelluksen käyttämällä samoja ominaisuuksia?

**V:** Kyllä.

**K:** Voinko mukauttaa lomaketta muussa ympäristössä kuin organisaationi oletusympäristössä?

**V:** Et.

### <a name="manage-your-custom-form"></a>Mukautetun lomakkeen hallinta

**K:** Miten voin helposti jakaa lomakkeen muiden kanssa?

**V:** Avaa lomake, valitse **Kopioi linkki** ja lähetä sitten linkki kenelle tahansa, jonka haluat käyttävän lomaketta.

**K:** Voinko päivittää lomakkeeni niin, että muut eivät näe muutoksia?

**V:** Kyllä. Voit muuttaa lomakettasi ja tallentaa niin monta kertaa kuin haluat, mutta muutoksesi eivät näy muille, ennen kuin valitset **Julkaise SharePointiin** kahdesti.

**K:** Jos teen virheen mukauttaessani luettelolomaketta, voinko palauttaa aiemman version?

**V:** Kyllä.

1. Avaa luettelosi, valitse komentopalkissa **PowerApps** ja valitse sitten **Mukauta lomakkeita**.

1. Valitse PowerApps Studiossa **Tiedosto** ja valitse sitten **Näytä kaikki versiot**. **Versiot**-sivu avautuu uudessa selaimen välilehdessä.

    > [!NOTE]
    > Jos **Näytä kaikki versiot** -painiketta ei ole, valitse **Tallenna**. Painikkeen pitäisi tulla näkyviin.

1. Palaa toisen selainvälilehden **Tallenna**-sivulle sulkematta **Versiot**-sivua tai selaimen välilehteä. Napsauta tai napauta sitten vasemman siirtymisruudun ylälaidassa olevaa nuolta ja valitse **Takaisin SharePointiin** lomakkeen avaamiseksi ja PowerApps Studion sulkemiseksi.

1. Palaa toisen selainvälilehden **Versiot**-sivulle, etsi palautettava versio ja valitse **Palauta**.

    > [!NOTE]
    > Jos saat virheviestin, jossa kerrotaan, että palauttaminen epäonnistui, koska lomake on toisen käyttäjän lukitsema, odota, kunnes lukitus poistetaan, ja yritä uudelleen.

**K:** Voinko siirtää luetteloni yhdestä luettelosta toiseen?

**V:** Et.

### <a name="administer-your-custom-form"></a>Mukautetun lomakkeen hallinnointi

**K:** Miten voin jakaa lomakkeeni?

**V:** Sinun ei tarvitse jakaa lomaketta. Lomake perii käyttöoikeudet SharePoint-luettelosta. Kun olet tehnyt kaikki muutokset lomakkeeseen, [julkaise se takaisin SharePointiin](customize-list-form.md#save-and-publish-the-list-form-back-to-sharepoint), jotta muut voivat käyttää sitä.

**K:** Kuka voi mukauttaa lomakkeita?

**V:** Kuka tahansa, jolla on SharePoint-käyttöoikeudet liitetyn luettelon hallitsemiseen, suunnittelemiseen tai muokkaamiseen.

**K:** Tarvitsenko PowerApps-käyttöoikeuden mukautettujen luettelolomakkeiden luomiseen tai käyttämiseen?

**V:** Tarvitset [Office 365 -palvelupaketin, joka sisältää PowerAppsin](../../administrator/pricing-billing-skus.md#licenses).

**K:** Mitä tapahtuu, kun vieraskäyttäjät käyttävät luetteloa, jossa on mukautettu lomake?

**V:** Vieraskäyttäjät saavat virheviestin, jos he yrittävät käyttää PowerAppsin avulla mukautettua luettelolomaketta.

**K:** Miten saan järjestelmänvalvojana luettelon kaikista organisaationi mukautetuista lomakkeista?

**V:** Jos olet PowerAppsin vuokraajajärjestelmänvalvoja tai sinulla on ympäristön järjestelmänvalvojan oikeudet organisaatiosi oletusarvoiseen PowerApps-ympäristöön, toimi seuraavasti:

1. Valitse [PowerApps-hallintakeskuksessa](https://admin.powerapps.com) ja valitse ympäristöluettelosta organisaatiosi oletusympäristö.

1. Valitse oletusympäristösivun ylälaidassa **Resurssit**.

1. Etsi sovellusluettelosta sovelluksia, joilla on **SharePoint-lomake**-sovellustyyppi – nämä ovat mukautettuja lomakkeita.

    ![Mukautettujen lomakkeiden luettelo](./media/customize-list-form/all-customized-forms.png)
