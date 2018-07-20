---
title: 'Tietotaulukko-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietotaulukko-ohjausobjektin ominaisuudet ja joitakin esimerkkejä
author: jasongre
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/05/2017
ms.author: jasongre
ms.openlocfilehash: c282301ffafd1214c072c5b29e87fbba1515eda2
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39017544"
---
# <a name="data-table-control-in-powerapps"></a>Tietotaulukko-ohjausobjekti PowerAppsissa
Näyttää tietojoukon taulukkomuodossa.

## <a name="description"></a>Kuvaus
**Tietotaulukko**-ohjausobjekti näyttää tietosarjan muodossa, johon sisältyy sarakeotsikot kullekin ohjausobjektin näyttämälle kentälle. Sovelluksen tekijänä sinä itse määräät kenttien näkyvyyden ja järjestyksen. **Valikoima**-ohjausobjektin tavoin myös **Tietotaulukko**-ohjausobjekti ylläpitää **Valittu**-ominaisuutta, joka osoittaa valittuun riviin. Siksi voit linkittää **Tietotaulukko**-ohjausobjektin toisiin ohjausobjekteihin.

## <a name="capabilities"></a>Ominaisuudet
PowerAppsin **Tietotaulukko**-ohjausobjekti otettiin käyttöön 5.5.2017. Tässä osiossa on tietoja ominaisuuksista, joita tuetaan, sekä ominaisuuksista, joita ei tueta.

### <a name="now-available"></a>Nyt käytettävissä
* **Tietotaulukko**-ohjausobjekti on vain luku -tilassa.
* **Tietotaulukko**-ohjausobjektissa on aina valittuna yksi rivi kerrallaan.
* Linkitä **Tietotaulukko**-ohjausobjekti yhdistettyyn tai paikalliseen tietolähteeseen.
* Voit muuttaa sarakkeiden leveyttä **Tietotaulukko**-ohjausobjektissa samalla, kun käytät sovellusta, mutta muutoksia ei tallenneta.
* Kun **Tietotaulukko**-ohjausobjekti linkitetään liittimeen, jossa tämä ominaisuus on käytössä, kuten Common Data Service, ohjausobjektissa näkyy joukko oletusmuotoisia kenttiä. Voit näyttää tai piilottaa näitä sekä muita kenttiä tarpeen mukaan.
* Mukauta sarakkeen leveyttä ja otsikkotekstiä.
* Näytä **Tietotaulukko**-ohjausobjektissa olevat hyperlinkit.
* Kopioi ja liitä **Tietotaulukko**-ohjausobjekti.

### <a name="not-yet-available"></a>Ei vielä käytettävissä
* Muokkaa yksittäisten sarakkeiden ulkoasua.
* Lisää **Tietotaulukko**-ohjausobjekti lomakeohjausobjektiin.
* Muuta kaikkien rivien korkeutta.
* Näytä **Tietotaulukko**-ohjausobjektissa olevat kuvat.
* Näytä vastaavista entiteeteistä olevat kentät.
* Käytä sisäänrakennettua toimintoa tietojen suodattamiseen ja lajitteluun sarakeotsikon mukaan.
* Lisää **Tietotaulukko**-ohjausobjekti **Valikoima**-ohjausobjektiin.
* Muokkaa **Tietotaulukko**-ohjausobjektin tietoja.
* Valitse useita rivejä.

### <a name="known-issues"></a>Tunnetut ongelmat
* Tietoja ei tule näkyviin, jos käytät **FirstN**-funktiota **Kohteet**-ominaisuudessa.

## <a name="key-properties"></a>Keskeiset ominaisuudet
* [**Kohteet** ](properties-core.md) – Tietolähde, joka näkyy **Tietotaulukko**-ohjausobjektissa.
* **Valittu** – **Tietotaulukko**-ohjausobjektissa valittuna oleva rivi.

## <a name="other-properties"></a>Muut ominaisuudet
* [**BorderColor**](properties-color-border.md) – **Tietotaulukko**-ohjausobjektin reunan väri.
* [**BorderStyle**](properties-color-border.md) – **Tietotaulukko**-ohjausobjektin reunan tyyli. Vaihtoehdot ovat **yhtenäinen**, **katkoviivat**, **pisteet** ja **ei mitään**.
* [**BorderThickness**](properties-color-border.md) – **Tietotaulukko**-ohjausobjektin reunan paksuus.
* [**Väri** ](properties-color-border.md) – Tietorivien tekstin oletusmuotoinen väri.
* [**Väri** ](properties-color-border.md) – Tietorivien oletusmuotoinen taustaväri.
* [**Fontti** ](properties-text.md) – Tietorivien tekstin oletusmuotoinen fontti.
* [**FontWeight** ](properties-text.md) – Tietorivien fontin oletusmuotoinen leveys.
* **HeadingColor** – Sarakeotsikoiden tekstin väri.
* **HeadingFill** – Sarakeotsikoiden taustaväri.
* **HeadingFont** – Sarakeotsikoiden fontti.
* **HeadingFontWeight** – Sarakeotsikoiden fontin leveys.
* **HeadingSize** – Sarakeotsikoiden fonttikoko.
* [**Korkeus**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin ylä- ja alareunan välinen etäisyys.
* [**HoverColor** ](properties-color-border.md) – Tekstin väri rivillä, jonka päällä on hiiren kohdistin.
* [**HoverFill** ](properties-color-border.md) – Taustan väri rivillä, jonka päällä hiiren kohdistin on.
* **NoDataText** – Sanoma, joka ilmoittaa käyttäjälle, että **Tietotaulukko**-ohjausobjektissa ei ole tietueita näytettäväksi.
* **SelectedColor** – Valitun rivin tekstin värin.
* **SelectedFill** – Valitun rivin taustaväri.
* [**Koko**](properties-text.md) – Kaikkien tietorivien oletusmuotoinen fonttikoko.
* [**Näkyvissä**](properties-core.md) – Arvo, joka määrittää, onko **Tietotaulukko**-ohjausobjekti näkyvissä vai piilotettu.
* [**Leveys**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin vasemman ja oikean reunan etäisyys.
* [**X**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön vasemman reunan, jos pääsäilöä ei ole).
* [**Y**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön yläreunan, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liitetyt toiminnot
* [**Filter(DataSource, Formula)**](../functions/function-filter-lookup.md)(*DataSource*, *Formula*)
* [**Search(DataSource, SearchString, Column)**](../functions/function-filter-lookup.md)(*DataSource*, *SearchString*, *Column*)

## <a name="examples"></a>Esimerkkejä
### <a name="basic-usage"></a>Peruskäyttö
1. Luo tyhjä tablettisovellus.
2. Valitse **Lisää**-välilehti ja napsauta tai napauta **Tietotaulukko**.
   
    ![Lisää Tietotaulukko-ohjausobjekti näyttöön](./media/control-data-table/insert-data-table.png)
   
    Näyttöön lisätään **Tietotaulukko**-ohjausobjekti.
3. Vaihda **Tietotaulukko**-ohjausobjektin nimeksi **SalesOrderTable** ja muuta sen kokoa niin, että se täyttää koko näytön.
4. Napsauta tai napauta alanuolta, joka on oikeanpuoleisessa ruudussa olevan tekstin **Tietolähdettä ei ole valittu** oikealla puolella, ja napsauta tai napauta kohtaa **Lisää tietolähde**.
   
    ![Lisää tietolähde](./media/control-data-table/add-data-to-data-table.png)
5. Napsauta tai napauta yhteysluettelossa yhteyttä, jonka haluat luoda Common Data Service -tietokantaasi.
   
    ![Valitse yhteys tietolähteeseen](./media/control-data-table/choose-cds-data-table.png)
6. Napsauta tai napauta entiteettiluettelosta **Myyntitilaus** ja sitten **Yhdistä**.
   
    ![Valitse Myyntitilaus-entiteetti](./media/control-data-table/choose-so-data-table.png)
   
    **Tietotaulukko**-ohjausobjekti on nyt liitetty **Myyntitilaus**-tietolähteeseen. **Tietotaulukko**-ohjausobjektissa näkyy aluksi useita kenttiä, koska käytämme yhdistintä, joka tukee kyseistä ominaisuutta.
   
    ![Tietotaulukko](./media/control-data-table/pre-order-data-table.png)
7. Voit näyttää tai piilottaa yksittäiset kentät merkitsemällä valintamerkit haluamiesi vaihtoehtojen kohdalle oikeanpuoleisessa ruudussa.
   
    Jos haluat piilottaa esimerkiksi **CustomerPurchaseOrderReference**-kentän, merkitse sen vieressä oleva valintaruutu.
8. Voit muuttaa kenttien järjestystä oikeanpuoleisessa ruudussa vetämällä niitä ylös tai alas.
   
    ![Järjestä kentät haluamallasi tavalla](./media/control-data-table/field-re-order-data-table.png)
   
    Kentät näkyvät määrittämässäsi järjestyksessä **SalesOrderTable**-ohjausobjektissa.
   
    ![Päivitetty tietotaulukko](./media/control-data-table/post-order-data-table.png)

### <a name="restyle-the-header-for-the-data-table-control"></a>Muotoile Tietotaulukko-ohjausobjektin otsikko
1. Kun **Tietotaulukko**-ohjausobjekti on valittuna, napsauta tai napauta oikeassa ruudussa olevaa **Lisäasetukset**-välilehteä.
2. Napsauta tai napauta **HeadingFill**-ominaisuuden kenttää ja muuta arvoksi **RGBA(62,96,170,1)**.
3. Napsauta tai napauta **HeadingColor**-ominaisuuden kenttää ja muuta arvoksi **Valkoinen**.
4. Napsauta tai napauta **HeadingSize**-ominaisuuden kenttää ja muuta arvoksi **14**.
   
    ![Tietotaulukko](./media/control-data-table/restyled-data-table.png)

### <a name="connect-a-data-table-control-to-another-control"></a>Tietotaulukko-ohjausobjektin yhdistäminen toiseen ohjausobjektiin
1. Lisää näyttöön **Muokattu lomake** -ohjausobjekti.
2. Muuta **Tietotaulukko**- ja **Muokattu lomake** -ohjausobjektien kokoa niin, että **Tietotaulukko**-ohjausobjekti näkyy näytössä vasemmalla ja **Muokattu lomake** -ohjausobjekti näkyy oikealla.
   
    ![Tietotaulukko ja Muokattu lomake samassa näytössä](./media/control-data-table/data-table-empty-form.png)
3. Kun **Form1** on valittuna, muuta oikeanpuoleisessa ruudussa sarakkeiden määräksi **1**.
4. Yhdistä **Form1** **Myyntitilaus**- tietolähteeseen.
   
    Useita kenttiä näkyy aluksi kohteessa **Form1**.
   
    ![Form1 ja alkuperäiset kentät](./media/control-data-table/data-table-disconnected-form.png)
5. Napsauta tai napauta oikeassa ruudussa olevaa **Lisäasetukset**-välilehteä.
6. Määritä **Form1**-ohjausobjektin **Kohde**-ominaisuudeksi **SalesOrderTable.Selected**.
   
    **Form1** näyttää valittuna olevan rivin tiedot **Tietotaulukko**-ohjausobjektissa.
   
    ![Tietotaulukkoon yhdistetty muokkauslomake](./media/control-data-table/connected-form-data-table.png)


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* [**Color**](properties-color-border.md) ja [**Fill**](properties-color-border.md)
* **HeadingColor** ja **HeadingFill**
* **SelectedColor** ja **SelectedFill**
* [**HoverColor**](properties-color-border.md)-väri ja [**HoverFill**](properties-color-border.md)-täyttö

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **NoDataText** on oltava käytössä.
