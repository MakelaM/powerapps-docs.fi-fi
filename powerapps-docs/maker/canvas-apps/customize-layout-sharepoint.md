---
title: Opetusohjelma – Luodun sovelluksen valikoiman mukauttaminen | Microsoft Docs
description: Tässä opetusohjelmassa mukautat PowerAppsissa automaattisesti luodun sovelluksen valikoimassa ja muissa elementeissä näkyvät tiedot.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: tutorial
ms.custom: canvas
ms.reviewer: ''
ms.date: 05/06/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4ca9ed14f96dbad52fe6f7b0318f520dbdd33d10
ms.sourcegitcommit: fc604f3e7f0399bdabee86ce94f67de49531a444
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2019
ms.locfileid: "58545080"
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>Opetusohjelma: Powerappsin valikoiman mukauttaminen

Tässä opetusohjelmassa mukautat valikoimaksi kutsutun tietueluettelon ja teet muita muutoksia sovellukseen, joka luotiin automaattisesti Microsoft PowerAppsissa. Käyttäjät voivat hallita sovelluksen tietoja, vaikka et tee näitä muutoksia, mutta sovellusta on helpompi käyttää, jos mukautat sitä organisaatiosi tarpeiden mukaan.

Esimerkiksi tässä opetusohjelmassa valikoima vastaa oletuksena tätä kaaviota. Sähköpostiosoite esitetään muita tietotyyppejä näkyvämmin, ja käyttäjät voivat lajitella ja suodattaa valikoiman osoitteen tekstin perusteella:

![Oletusvalikoima](./media/customize-layout-sharepoint/gallery-before.png)

Käyttäjiäsi saattaa kuitenkin kiinnostaa enemmän tilin nimi kuin sähköpostiosoite, joten voit määrittää valikoiman uudelleen korostamaan, lajittelemaan ja suodattamaan organisaatiosi tärkeiden tietojen perusteella. Lisäksi voit muuttaa oletusnäytön otsikon, jotta se eroaa sovelluksen muista näytöistä.

![Lopullinen valikoima](./media/customize-layout-sharepoint/gallery-after.png)

Voit myös lisätä vierityspalkin, jotta käyttäjät, joilla ei ole kosketusnäyttöä tai hiiren kiekkopainiketta, voivat selata koko valikoimaa.

> [!div class="checklist"]
> * Muuta valikoiman asettelua
> * Muuta valikoimassa näkyvää tietotyyppiä
> * Muuta sarakkeita, joilla käyttäjät voivat lajitella ja hakea tietoja
> * Muuta näytön otsikkoa
> * Näytä vierityspalkki

Tämä opetusohjelma alkaa sovelluksella, joka luotiin tietystä tietolähteestä. Samat käsitteet koskevat kuitenkin mitä tahansa sovellusta, jonka luot PowerAppsissa SharePoint-luettelosta, Excel-taulukosta tai jostakin muusta tietolähteestä.

Jos et ole rekisteröitynyt PowerAppsiin, [rekisteröidy ilmaiseksi](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ennen aloittamista.

## <a name="prerequisites"></a>Edellytykset

[Sovelluksen luominen](data-platform-create-app.md) - **tilit** Common Data Service-entiteettiin.

## <a name="open-the-generated-app"></a>Avaa luotu sovellus

1. Kirjaudu [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja valitse **Sovellukset** lähellä vasenta reunaa.

1. Etsi luomasi sovellus, valitse kolme pistettä (**...**) sovelluksen kohdalla ja valitse sitten **Muokkaa**.

    ![Avaa sovellus muokkaamista varten](./media/customize-layout-sharepoint/open-app.png)

1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

## <a name="change-the-layout"></a>Asettelun muuttaminen

1. Valitse vasemmassa siirtymisruudussa **BrowseGallery1**.

    Kun valikoima on valittuna, sen ympärillä näkyy valintakehys kahvoineen.

    ![Valitse valikoima](media/customize-layout-sharepoint/select-gallery-1.png)

1. Käyttöön **ominaisuudet** välilehti oikeanpuoleisessa ruudussa, Avaa kohdan vaihtoehtoluettelo **asettelu**, ja valitse sitten haluamasi vaihtoehdon näkyy vain otsikko.

    ![Valitse vain otsikko -asettelu](./media/customize-layout-sharepoint/choose-layout.png)

1. Kohdan **kentät**, valitse **Muokkaa**, ja valitse sitten otsikkoruutuun alanuolta.

    Tämän ohjausobjektin nimi päättyy numeroon, kuten **Title1**, mutta numero saattaa vaihdella muiden mahdollisesti tekemiesi toimintojen perusteella.

1. Valitse valintaluettelossa, **tilin nimi**, ja sulje sitten **tietojen** ruudussa.

    Valikoima näyttää kunkin tilin nimen.

    ![Lopullinen valikoima](./media/customize-layout-sharepoint/final-gallery.png)

## <a name="change-sort-and-search-columns"></a>Muuta lajittelu- ja hakusarakkeita

1. Valitse valikoima edellisen osan ohjeiden mukaan.

    ![Valitse valikoima](./media/customize-layout-sharepoint/select-gallery-title.png)

1. Varmista vasemmasta yläkulmasta, että ominaisuusluettelo näyttää **Kohteet**.

    ![Kohteiden ominaisuus](./media/customize-layout-sharepoint/items-property.png)

    Tämän ominaisuuden arvo näkyy kaavarivillä. Voit asettaa tämän ominaisuuden määrittämään valikoiman tietolähteen lisäksi myös sarakkeet, joiden mukaan käyttäjät voivat lajitella ja hakea tietoja.

1. Kopioi tämä kaava ja liitä se kaavariville.

    ```SortByColumns(Search(Accounts, TextSearchBox1.Text, "name"), "name", If(SortDescending1, Descending, Ascending))```

    Käyttämällä tätä kaavaa varmistat seuraavat seikat:

    * Jos käyttäjä kirjoittaa vähintään yhden merkin hakupalkkiin, valikoimassa näkyvät vain ne tilin nimet, jotka sisältävät käyttäjän kirjoittaman tekstin.
    * Jos käyttäjä valitsee lajittelukuvakkeen, valikoima lajitellaan tilin nimen mukaan aakkosjärjestyksessä nousevaan tai laskevaan järjestykseen sen perusteella, kuinka monta kertaa käyttäjä valitsee kuvakkeen.

     Lisätietoja näistä ja muista funktioista on artikkelissa [Lisätietoja kaavasta](formula-reference.md).

### <a name="test-sorting-and-searching"></a>Testaa lajittelu ja haku

1. Avaa esikatselutila painamalla F5-näppäintä (tai valitsemalla oikean yläkulman alueella oleva toistopainike).

    ![Esikatselutilan avaaminen](./media/customize-layout-sharepoint/open-preview.png)

1. Valitse selausnäytön oikean yläkulman lähellä oleva lajittelukuvake kerran tai useita kertoja. Näin aakkosjärjestys muuttuu nousevan ja laskevan välillä.

    ![Testaa lajittelukuvake](./media/customize-layout-sharepoint/sort-button.png)

1. Kirjoita hakukenttään **k**. Näin näytetään vain ne tilin nimet, jotka sisältävät kirjoittamasi kirjaimen.

    ![Testaa hakupalkki](./media/customize-layout-sharepoint/test-filter.png)

1. Poista kaikki teksti hakupalkista ja sulje sitten esikatselutila painamalla Esc-näppäintä (tai valitsemalla sulkemiskuvake lähellä oikeaa yläkulmaa).

## <a name="change-the-screen-title"></a>Muuta näytön otsikkoa

1. Valitse näytön otsikko napsauttamalla tai napauttamalla sitä.

    ![Valitse näytön otsikko](./media/customize-layout-sharepoint/select-title.png)

1. Varmista, että ominaisuusluettelossa näkyy **Teksti** ja korvaa sitten kaavarivin **Tilit** **Selaa**-nimellä (säilytä lainausmerkit).

    ![Päivitä näytön otsikko](./media/customize-layout-sharepoint/change-screen-title.png)

    Näyttö päivittyy muutoksen mukaisesti.

    ![Uusi näyttöotsikko](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scrollbar"></a>Vierityspalkin näyttäminen

Jos käyttäjillä ei mahdollisesti ole kosketusnäyttöä tai hiiren kiekkopainiketta, määritä valikoima näyttämään vierityspalkki, kun käyttäjä siirtää kohdistimen sen päälle. Näin käyttäjät voivat tuoda näkyviin kaikki tilit, vaikka näyttö ei pystyisi näyttämään niitä kaikkia kerralla.

1. Valitse valikoima ensimmäisen toimenpiteen ohjeiden mukaan.

    ![Valitse valikoima](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. Määritä valikoiman **Näytä vierityspalkki** ominaisuudeksi **true**.

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa olet mukauttanut valikoiman ja tehnyt muita muutoksia oletusnäyttöön tietueiden selaamiseksi luodussa sovelluksessa. Voit myös mukauttaa oletusnäyttöjä tietojen näyttämistä ja tilien luomista tai päivittämistä varten. Selausnäyttö sisältää valikoiman ja sovelluksen muut kaksi näyttöä sisältävät lomakkeita. Voit muuttaa esimerkiksi sitä, mitä tietotyyppejä lomakkeissa näytetään ja missä järjestyksessä.

> [!div class="nextstepaction"]
> [Lomakkeiden mukauttaminen](customize-forms-sharepoint.md)
