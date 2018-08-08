---
title: Kohdeluettelon näyttäminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Näytä kohdeluettelo pohjaan perustuvassa sovelluksessasi valikoiman avulla ja suodata luetteloa määrittämällä kriteeri.
author: karthik-1
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/28/2017
ms.author: sharik
ms.openlocfilehash: 753a4508890f5ab007bef2a1f4d81bb46043a089
ms.sourcegitcommit: e3f5a2bef64085d02aec82e62ff94ae8a4d01d24
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/02/2018
ms.locfileid: "39470496"
---
# <a name="show-a-list-of-items-in-powerapps"></a>Kohdeluettelon näyttäminen PowerAppsissa

Näytä kohdeluettelo mistä tahansa tietolähteestä lisäämällä pohjaan perustuvaan sovellukseesi **[Valikoima](controls/control-gallery.md)**-ohjausobjekti. Tässä aiheessa käytetään tietolähteenä Exceliä. Suodata luetteloa määrittämällä **Valikoima**-ohjausobjekti näyttämään vain ne kohteet, jotka vastaavat **[Tekstisyöte](controls/control-text-input.md)**-ohjausobjektissa annettua suodatuskriteeriä.

## <a name="prerequisites"></a>Edellytykset

* Lue, miten [voit lisätä ja määrittää ohjausobjektin](add-configure-controls.md) PowerAppsissa.

* Esimerkkitietojen määrittäminen:
    1. Lataa [tämä Excel-tiedosto](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), joka sisältää opetusohjelman näytetiedot.

    2. Lataa Excel-tiedosto [pilvitallennuspalveluun](connections/cloud-storage-blob-connections.md), kuten OneDrive for Business -palveluun.

## <a name="add-a-gallery-control"></a>Valikoima-ohjausobjektin lisääminen
1. Avaa PowerApps ja napsauta tai napauta **Uusi** lähellä vasenta reunaa.

2. Napsauta tai napauta **Tyhjä sovellus** -ruudussa kohtaa **Puhelinasettelu**.

3. Jos **Tervetuloa PowerApps Studioon** -valintaikkuna avautuu, napsauta tai napauta **Ohita**.

4. [Lisää yhteys](add-data-connection.md) Excel-tiedoston **FlooringEstimates**-taulukkoon.

5. (valinnainen) Lisää oletusnäytölle **Valikoima**-ohjausobjekti valitsemalla **Lisää**-välilehti ja napsauttamalla tai napauttamalla ensin kohtaa **Valikoima** ja sitten joko tyhjää tai ohjausobjektien oletusjoukon sisältävää **Valikoima**-ohjausobjektia.

    Näihin vaihtoehtoihin kuuluu **Valikoima**-ohjausobjekteja, joita voi vierittää vaaka- tai pystysuoraan. Voit myös lisätä **Valikoima**-ohjausobjektin, jonka koko perustuu automaattisesti kohteissa olevan sisällön määrään.

    ![Valikoiman lisääminen](./media/add-gallery/gallery-dropdown.png)

6. Napsauta tai napauta **Aloitus**-välilehdestä **Uusi näyttö**.

    Voit lisätä näytön, joka on tyhjä, jota voi vierittää, joka sisältää **Valikoima**-ohjausobjektin tai joka sisältää lomakkeen.

7. Lisää näyttö, joka sisältää **Valikoima**-ohjausobjektin ja muita ohjausobjekteja, kuten hakupalkin, napsauttamalla tai napauttamalla kohtaa **Luettelonäyttö**.

    > [!NOTE]
   > Lisäsitpä **Valikoima**-ohjausobjektin uuteen tai olemassa olevaan näyttöön, voit valita sen napauttamalla tai napsauttamalla **Valikoima**-ohjausobjektin alaosaa. Valitse sitten oikeanpuoleisessa ruudussa **FlooringEstimates** ja napsauta tai napauta eri asettelua **Tiedot**-ruudussa. Jätä tätä opetusohjelmaa varten asettelu oletusarvoonsa.

    ![Valikoiman asettelun valinta](./media/add-gallery/select-layout.png)

8. Napsauta tai napauta **Valikoima**-ohjausobjektia näytössä, jonka juuri lisäsit.

9. Napsauta tai napauta oikean ruudun **Ominaisuudet**-välilehden kohtaa **CustomGallerySample**.

10. Valitse **Tiedot**-ruudussa ensin **CustomGallerySample** ja sitten **FlooringEstimates**.

    ![Tietolähteen valinta](./media/add-gallery/choose-data.png)

    **Valikoima**-ohjausobjekti näyttää esimerkkitiedot.

    ![Näytä tiedot](./media/add-gallery/show-data-default.png)

    Tämän aiheen myöhemmässä osiossa määritetään lajittelu ja haku.

## <a name="add-a-control-to-the-gallery-control"></a>Ohjausobjektin lisääminen Valikoima-ohjausobjektiin
Ennen kuin teet mukautuksia, valitse **Valikoima**-ohjausobjektin asettelu. **Valikoima**-ohjausobjektin ensimmäinen ohjausobjektijoukko on mallipohja, joka määrittää, miten kaikki **Valikoima**-ohjausobjektin tiedot näytetään.

1. Valitse mallipohja napsauttamalla tai napauttamalla **Valikoima**-ohjausobjektin alaosaa ja sitten napsauttamalla tai napauttamalla vasemman yläkulman lyijykynäkuvaketta.

    ![Valikoimamallin muokkaus](./media/add-gallery/edit-item.png)

2. Kun mallipohja on valittuna, lisää **[Selite](controls/control-text-box.md)**-ohjausobjekti ja sitten siirrä sitä ja muuta sen kokoa niin, että se ei ole muiden mallipohjan ohjausobjektien päällä.

    ![Selitteen lisääminen](./media/add-gallery/add-text-box.png)
3. Avaa **Tiedot**-ruutu valitsemalla mallipohja ja napsauttamalla tai napauttamalla sitten oikeanpuoleisessa ruudussa kohtaa **Flooring Estimates**.

4. Valitse aiemmin lisäämäsi selite ja avaa korostettu luettelo **Tiedot**-ruudussa.

    ![Avattavan luettelon avaaminen](./media/add-gallery/open-dropdown.png)

5. Napsauta tai napauta luettelon kohtaa **Price**.

    ![Selitteen sidonnan muuttaminen](./media/add-gallery/change-binding.png)

    **Valikoima**-ohjausobjekti näyttää uudet arvot.

    ![Lopullinen valikoima](./media/add-gallery/final-gallery.png)

## <a name="filter-the-gallery-control"></a>Valikoima-ohjausobjektin suodattaminen
**Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuus määrittää, mitä se näyttää. Tässä toimintosarjassa kyseinen ominaisuus määritetään niin, että **Valikoima**-ohjausobjekti näyttää vain ne kohteet, joissa tuotteen nimi sisältää **TextSearchBox1**-kentässä määritetyn tekstin.

![Tekstihakukenttä](./media/add-gallery/text-search-box.png)

1. Valitse **Valikoima**-ohjausobjekti napsauttamalla tai napauttamalla ohjausobjektin alaosaa.

2. Määritä **Lisäasetukset**-välilehdessä **Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:

    **If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name)))**

    Lisätietoja tämän kaavan funktioista on aiheessa [Lisätietoja kaavasta](formula-reference.md).

3. Kirjoita tuotteen nimi tai osa siitä hakukenttään.

    **Valikoima**-ohjausobjekti näyttää vain kohteet, jotka täyttävät suodatusehdon.

## <a name="sort-the-gallery-control"></a>Valikoima-ohjausobjektin lajittelu
**Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuus määrittää järjestyksen, jossa kohteet näytetään. Tässä toimintosarjassa ominaisuus määritetään niin, että **Valikoima**-ohjausobjekti näyttää kohteet kohdassa **ImageSortUpDown1** määritetyssä järjestyksessä.

![Lajittelun kuva](./media/add-gallery/image-sorting.png)

1. Aseta **Valikoima**-ohjausobjektin **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **Sort(If(IsBlank(TextSearchBox1.Text), FlooringEstimates, Filter(FlooringEstimates, TextSearchBox1.Text in Text(Name))), Name, If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

2. Vaihda **Valikoima**-ohjausobjektin lajittelujärjestys tuotteiden nimien mukaiseksi valitsemalla lajittelukuvake.

**Valikoima**-ohjausobjektin lajittelu *ja* suodattaminen:

* Korvaa tämän kaavan kumpikin *Tietolähde*-kohta tietolähteesi nimellä.

* Korvaa tämän kaavan kumpikin *SarakkeenNimi*-kohta sen sarakkeen nimellä, jonka mukaan haluat lajitella ja suodattaa.

**Sort(If(IsBlank(TextSearchBox1.Text),** *Tietolähde*, **Filter(** *Tietolähde*, **TextSearchBox1.Text in Text(** *SarakkeenNimi* **))),** *SarakkeenNimi*, **If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

## <a name="highlight-the-selected-item"></a>Valitun kohteen korostaminen
Aseta **Valikoima**-ohjausobjektin **TemplateFill**-ominaisuudeksi kaava, joka muistuttaa tätä esimerkkiä:

**If(ThisItem.IsSelected, LightCyan, White)**

## <a name="change-the-default-selection"></a>Oletusvalinnan muuttaminen
Aseta **Valikoima**-ohjausobjektin **Default**-ominaisuudeksi se tietue, jonka haluat olevan valittuna oletuksena. Määritä esimerkiksi **FlooringEstimates**-tietolähteen viides kohta:

**Last(FirstN(FlooringEstimates, 5))**

Tässä esimerkissä määritetään **FlooringEstimates**-tietolähteen **Hardwood**-luokka:

**First(Filter(FlooringEstimates, Category = "Hardwood"))**

## <a name="next-steps"></a>Seuraavat vaiheet
Opi käyttämään [lomakkeita](working-with-forms.md) ja [kaavoja](working-with-formulas.md).
