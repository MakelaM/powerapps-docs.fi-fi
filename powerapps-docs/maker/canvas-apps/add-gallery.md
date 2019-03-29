---
title: Kohdeluettelon näyttäminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Näytä kohdeluettelo pohjaan perustuvassa sovelluksessasi valikoiman avulla ja suodata luetteloa määrittämällä kriteeri.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/28/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f45948bc16f036669a09ed2c566c60440d24a797
ms.sourcegitcommit: 2180982e57f0d161610be584fdae9424fe7e06b5
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/29/2019
ms.locfileid: "58616704"
---
# <a name="show-a-list-of-items-in-powerapps"></a>Kohdeluettelon näyttäminen PowerAppsissa

Näytä kohdeluettelo mistä tahansa tietolähteestä lisäämällä pohjaan perustuvaan sovellukseesi **[Valikoima](controls/control-gallery.md)**-ohjausobjekti. Tässä aiheessa käytetään tietolähteenä Exceliä. Suodata luetteloa määrittämällä **Valikoima**-ohjausobjekti näyttämään vain ne kohteet, jotka vastaavat **[Tekstisyöte](controls/control-text-input.md)**-ohjausobjektissa annettua suodatuskriteeriä.

## <a name="prerequisites"></a>Edellytykset

- Lue, miten [voit lisätä ja määrittää ohjausobjektin](add-configure-controls.md) PowerAppsissa.

- Esimerkkitietojen määrittäminen:
    1. Lataa [tämä Excel-tiedosto](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), joka sisältää opetusohjelman näytetiedot.

    2. Lataa Excel-tiedosto [pilvitallennuspalveluun](connections/cloud-storage-blob-connections.md), kuten OneDrive for Business -palveluun.

- Avaa tyhjä sovellus:
    1. [Kirjaudu sisään PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

    1. Valitse **Tee oma sovelluksesi** -kohdasta vaihtoehto **Pohjan sovellus tyhjästä**.

    1. Määritä sovelluksesi nimi, valitse **Puhelin** ja valitse sitten **Luo**.

    1. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, valitse **Ohita**.

    1. [Lisää yhteys](add-data-connection.md) Excel-tiedoston **FlooringEstimates**-taulukkoon.

## <a name="add-a-gallery-to-a-blank-screen"></a>Lisää valikoima tyhjä näyttö

1. Käyttöön **Lisää** -välilehden **valikoiman**, ja valitse sitten **pystysuuntainen**.

    ![Lisää pystysuuntainen valikoima](./media/add-gallery/gallery-dropdown.png)

1. Valitse **ominaisuudet** välilehti oikeanpuoleisessa ruudussa, Avaa **kohteet** luettelo ja valitse sitten **Flooring Estimates**.

    ![Flooring estimates](./media/add-gallery/select-layout.png)

1. (valinnainen) Tässä **asettelu** -luettelosta vaihtoehdon.

## <a name="add-a-gallery-in-a-screen"></a>Lisää valikoima näyttöön

1. Valitse **aloitus** -välilehden **uuden näytön** > **luettelonäyttö**.

    Näyttö, joka sisältää **valikoiman** ohjausobjektin ja muita ohjausobjekteja, kuten hakupalkin, tulee näkyviin.

1. Määritä valikoiman **Kohteet**-ominaisuuden arvoksi `FlooringEstimates`.

    **Valikoima**-ohjausobjekti näyttää esimerkkitiedot.

    ![Näytä tiedot](./media/add-gallery/show-data-default.png)

## <a name="add-a-control-to-the-gallery-control"></a>Ohjausobjektin lisääminen Valikoima-ohjausobjektiin
Ennen kuin teet muita mukautuksia, varmista, että asettelu- **valikoiman** ohjausobjektin aihettasi parhaiten vastaava mitä. Sieltä voit muokata **valikoiman** malli, joka määrittää, miten kaikki tiedot **valikoiman** ohjausobjekti näkyy.

1. Valitse malli napsauttamalla tai napauttamalla lähellä **valikoiman** ohjausobjektin ja valitsemalla sitten sen vasemmassa yläkulmassa olevaa kynäkuvaketta.

    ![Valikoimamallin muokkaus](./media/add-gallery/edit-item.png)

2. Kun mallipohja on valittuna, lisää **[Selite](controls/control-text-box.md)**-ohjausobjekti ja sitten siirrä sitä ja muuta sen kokoa niin, että se ei ole muiden mallipohjan ohjausobjektien päällä.

    ![Lisää nimi](./media/add-gallery/add-text-box.png)

3. Valitse valikoima ja valitse sitten **Muokkaa** kohdan **kentät** , **ominaisuudet** välilehti oikeanpuoleisessa ruudussa.

4. Valitse aiemmin lisäämäsi selite ja avaa korostettu luettelo **Tiedot**-ruudussa.

    ![Avattavan luettelon avaaminen](./media/add-gallery/open-dropdown.png)

5. Napsauta tai napauta luettelon kohtaa **Price**.

    **Valikoima**-ohjausobjekti näyttää uudet arvot.

    ![Lopullinen valikoima](./media/add-gallery/final-gallery.png)

## <a name="filter-and-sort-a-gallery"></a>Suodattaa ja lajitella valikoiman
**Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuus määrittää, mitä se näyttää. Tässä toimintosarjassa kyseinen ominaisuus määritetään niin, että se myös määrittää, mitkä tietueet näkyvät perusteella suodatusehdot ja missä järjestyksessä.

![Hakukuvaketta ruutuun ja lajitteleminen](./media/add-gallery/text-search-box.png)

1. Aseta **Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    ```powerapps-dot
    Sort
        (If
            (IsBlank(TextSearchBox1.Text),
            FlooringEstimates,
            Filter(
                FlooringEstimates,
                TextSearchBox1.Text in Text(Name)
            )
        ),
        Name,
        If(
            SortDescending1,
            SortOrder.Descending,
            SortOrder.Ascending
        )
    )
    ```

    Lisätietoja tämän kaavan funktioista on aiheessa [Lisätietoja kaavasta](formula-reference.md).

1. Kaksoisnapsauta hakuruutua ja kirjoita sitten sen tai osa siitä tuotteen nimi.

    Näkyvät vain ne kohteet, jotka täyttävät suodatuskriteeriä.

1. Kun painamalla Alt-näppäintä, valitse lajittelukuvake kerran tai useita kertoja Vaihda lajittelujärjestystä.

    Tietueet viivakaaviosta nousevan ja laskevan tuotteen nimen mukaan aakkosjärjestyksessä.

## <a name="highlight-the-selected-item"></a>Valitun kohteen korostaminen
Määritä **valikoiman** ohjausobjektin **TemplateFill** ominaisuudeksi kaava, joka muistuttaa tätä esimerkkiä, mutta voit määrittää eri värejä, jos haluat:

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>Oletusvalinnan muuttaminen
Aseta **Valikoima**-ohjausobjektin **Default**-ominaisuudeksi se tietue, jonka haluat olevan valittuna oletuksena. Voit esimerkiksi määrittää viides **FlooringEstimates** tietolähde:

**Last(FirstN(FlooringEstimates, 5))**

Tässä esimerkissä määritetään **FlooringEstimates**-tietolähteen **Hardwood**-luokka:

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>Seuraavat vaiheet
Opi käyttämään [lomakkeita](working-with-forms.md) ja [kaavoja](working-with-formulas.md).
