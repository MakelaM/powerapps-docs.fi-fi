---
title: Kohdeluettelon näyttäminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Näytä kohdeluettelo pohjaan perustuvassa sovelluksessasi valikoiman avulla ja suodata luetteloa määrittämällä kriteeri.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 09/28/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3df6227ed33c5154e1e5dd700e6a87c3e8305f01
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987580"
---
# <a name="show-a-list-of-items-in-powerapps"></a>Kohdeluettelon näyttäminen PowerAppsissa

Näytä kohdeluettelo mistä tahansa tietolähteestä lisäämällä pohjaan perustuvaan sovellukseesi **[Valikoima](controls/control-gallery.md)** -ohjausobjekti. Tässä aiheessa käytetään tietolähteenä Exceliä. Suodata luetteloa määrittämällä **Valikoima**-ohjausobjekti näyttämään vain ne kohteet, jotka vastaavat **[Tekstisyöte](controls/control-text-input.md)** -ohjausobjektissa annettua suodatuskriteeriä.

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

## <a name="add-a-gallery-to-a-blank-screen"></a>Valikoiman lisääminen tyhjään näyttöön

1. Valitse **Lisää** -väli lehdeltä **valikoima**ja valitse sitten **pysty**.

    ![Lisää pystysuuntainen valikoima](./media/add-gallery/gallery-dropdown.png)

1. Avaa oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdellä **kohteet** -luettelo ja valitse sitten lattia- **arviot**.

    ![Lattia päällyste ennusteet](./media/add-gallery/select-layout.png)

1. valinnainen Valitse eri asetus **ulkoasu** -luettelosta.

## <a name="add-a-gallery-in-a-screen"></a>Valikoiman lisääminen näyttöön

1. Valitse **Aloitus** -väli lehdeltä **Uusi näyttö** > -**lista näyttö**.

    Näyttöön tulee näyttö, joka sisältää **valikoima** -ohjaus objektin ja muita ohjaus objektin, kuten haku palkin.

1. Määritä valikoiman **Kohteet**-ominaisuuden arvoksi `FlooringEstimates`.

    **Valikoima**-ohjausobjekti näyttää esimerkkitiedot.

    ![Näytä tiedot](./media/add-gallery/show-data-default.png)

## <a name="add-a-control-to-the-gallery-control"></a>Ohjausobjektin lisääminen Valikoima-ohjausobjektiin
Ennen kuin teet mitään muita mukautuksia, varmista, että **valikoima** -ohjaus objektin ulkoasu vastaa parhaiten sitä, mitä haluat. Sieltä voit edelleen muokata **valikoima** -mallia, joka määrittää, miten kaikki **valikoima** -ohjaus objektin tiedot näkyvät.

1. Valitse malli napsauttamalla tai napauttamalla **valikoima** -ohjaus objektin alareunaa ja valitsemalla sitten kynä kuvake vasemmasta yläkulmasta.

    ![Valikoimamallin muokkaus](./media/add-gallery/edit-item.png)

2. Kun mallipohja on valittuna, lisää **[Selite](controls/control-text-box.md)** -ohjausobjekti ja sitten siirrä sitä ja muuta sen kokoa niin, että se ei ole muiden mallipohjan ohjausobjektien päällä.

    ![Lisää nimi](./media/add-gallery/add-text-box.png)

3. Valitse valikoima ja valitse sitten oikeanpuoleisen ruudun **Ominaisuudet** -väli lehden **kenttien** vierestä **Muokkaa** .

4. Valitse aiemmin lisäämäsi selite ja avaa korostettu luettelo **Tiedot**-ruudussa.

    ![Avattavan luettelon avaaminen](./media/add-gallery/open-dropdown.png)

5. Napsauta tai napauta luettelon kohtaa **Price**.

    **Valikoima**-ohjausobjekti näyttää uudet arvot.

    ![Lopullinen valikoima](./media/add-gallery/final-gallery.png)

## <a name="filter-and-sort-a-gallery"></a>Valikoiman suodattaminen ja lajitteleminen
**Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)** -ominaisuus määrittää, mitä se näyttää. Tässä toimenpiteessä määrität kyseisen ominaisuuden niin, että se myös määrittää, mitkä tietueet näkyvät suodatus ehtojen ja järjestyksen mukaan.

![Haku ruutu ja lajittelu kuvake](./media/add-gallery/text-search-box.png)

1. Aseta **Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

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

1. Kaksoisnapsauta haku ruutua ja kirjoita siihen tuotteen nimi tai osa siitä.

    Vain ne kohteet, jotka täyttävät suodatus kriteerin, näkyvät.

1. Kun painat Alt-näppäintä, valitse lajittelu kuvake vähintään kerran, jos haluat vaihtaa lajittelu järjestystä.

    Tietueet vaihtuva nousevassa ja laskevassa aakkos järjestyksessä tuotteen nimen perusteella.

## <a name="highlight-the-selected-item"></a>Valitun kohteen korostaminen
Määritä **valikoima** -ohjaus objektin **templatefill** -ominaisuudeksi kaava, joka on samankaltainen kuin tässä esimerkissä, mutta voit halutessasi määrittää eri värit:

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>Oletusvalinnan muuttaminen
Aseta **Valikoima**-ohjausobjektin **Default**-ominaisuudeksi se tietue, jonka haluat olevan valittuna oletuksena. Voit esimerkiksi määrittää viidennen kohteen **Flouringin arviot** -tieto lähteessä:

**Last(FirstN(FlooringEstimates, 5))**

Tässä esimerkissä määritetään **FlooringEstimates**-tietolähteen **Hardwood**-luokka:

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>Seuraavat vaiheet
Opi käyttämään [lomakkeita](working-with-forms.md) ja [kaavoja](working-with-formulas.md).
