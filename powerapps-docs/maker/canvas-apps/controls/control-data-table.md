---
title: 'Tietotaulukko-ohjausobjekti: viittaus | Microsoft Docs'
description: Tietotaulukko-ohjausobjektin ominaisuudet ja joitakin esimerkkejä
services: powerapps
documentationcenter: na
author: jasongre
manager: kfend
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/05/2017
ms.author: kfend
ms.openlocfilehash: 431fb0233fa58d59a62a9d5d2cf07bfdd23d6271
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/12/2018
---
# <a name="data-table-control-in-powerapps"></a>Tietotaulukko-ohjausobjekti PowerAppsissa
Näyttää tietojoukon taulukkomuodossa.

## <a name="description"></a>Kuvaus
**Tietotaulukko**-ohjausobjekti muodostuu sarakeotsikoilla varustetuista tietokentistä. Sovelluksen tekijänä sinä itse määräät kenttien näkyvyyden ja järjestyksen. **Valikoima**-ohjausobjektin tavoin myös **Tietotaulukko**-ohjausobjekti käyttää **Valittu**-ominaisuutta, joka osoittaa valittuun riviin. Siksi voit linkittää **Datataulukko**-ohjausobjektin toisiin ohjausobjekteihin.

## <a name="capabilities"></a>Ominaisuudet
PowerAppsin **Tietotaulukko**-ohjausobjekti otettiin käyttöön 5.5.2017. Tässä osiossa on tietoja ominaisuuksista, joita tuetaan, sekä ominaisuudet, joita ei tueta.

### <a name="now-available"></a>Nyt käytettävissä
* **Tietotaulukko**-ohjausobjekti on vain luku -tilassa.
* **Tietotaulukko**-ohjausobjektissa on aina valittuna yksi rivi kerrallaan.
* Linkitä **Tietotaulukko**-ohjausobjekti yhdistettyyn tai paikalliseen tietolähteeseen.
* Voit muuttaa sarakkeiden leveyttä **Tietotaulukko**-ohjausobjektissa samalla, kun käytät sovellusta, mutta muutoksia ei tallenneta.
* Jos **Tietotaulukko**-ohjausobjekti linkitetään Common Data Service -palveluun tai johonkin muuhun sovellukseen, jossa tämä ominaisuus on käytössä, ohjausobjektissa näkyy joukko oletusmuotoisia kenttiä. Voit näyttää tai piilottaa näitä kenttiä tarpeen mukaan.
* Mukauta sarakkeen leveyttä ja otsikkotekstiä.
* Näytä **Tietotaulukko**-ohjausobjektissa olevat hyperlinkit.
* Kopioi ja liitä **Tietotaulukko**-ohjausobjekti.

### <a name="not-yet-available"></a>Ei ole vielä käytettävissä
* Muokkaa yksittäisten sarakkeiden ulkoasua.
* Lisää **Tietotaulukko**-ohjausobjekti lomakeohjausobjektiin.
* Muuta kaikkien rivien korkeutta.
* Näytä **Tietotaulukko** ohjausobjektissa olevat kuvat.
* Näytä vastaavista entiteeteistä olevat kentät.
* Käytä sisäänrakennettua toimintoa tietojen suodattamiseen ja lajitteluun sarakeotsikon mukaan.
* Lisää **Tietotaulukko**-ohjausobjekti **Valikoima**-ohjausobjektiin.
* Muokkaa **Tietotaulukko**-ohjausobjektin tietoja.
* Valitse useita rivejä.

### <a name="known-issues"></a>Tunnetut ongelmat
* Tietoja ei tule näkyviin, jos käytät **FirstN** -funktiota **Kohteet**-ominaisuudessa.

## <a name="key-properties"></a>Keskeiset ominaisuudet
* [**Kohteet** ](properties-core.md) –Tietolähde, joka näkyy **Tietotaulukko**-ohjausobjektissa.
* **Valittu** – **Tietotaulukko**-ohjausobjektissa valittuna oleva rivi.

## <a name="other-properties"></a>Muut ominaisuudet
* [**Reunan väri**](properties-color-border.md) – **Tietotaulukko**-ohjausobjektin reunan väri.
* [**Reunan tyyli**](properties-color-border.md) – **Tietotaulukko**-ohjausobjektin reunan tyyli. Vaihtoehdot ovat **tasainen**, **katkoviiva**, **pisteviiva** ja **ei mitään**.
* [**Reunan paksuus**](properties-color-border.md) – **Tietotaulukko**-ohjausobjektin reunan paksuus.
* [**Väri** ](properties-color-border.md) – Tietorivien tekstin oletusmuotoinen väri.
* [**Väri** ](properties-color-border.md) – Tietorivien oletusmuotoinen taustaväri.
* [**Fontti** ](properties-text.md) – Tietorivien tekstin oletusmuotoinen fontti.
* [**Fontti leveys** ](properties-text.md) – Tietorivien fontin oletusmuotoinen leveys.
* **Otsikon väri** – Sarakeotsikoiden tekstin väri.
* **Otsikon täyttö** – Sarakeotsikoiden taustaväri.
* **Otsikon fontti**  – Sarakeotsikoiden fontti.
* **Otsikon fontin leveys**  – Sarakeotsikoiden fontin leveys.
* **Otsikon koko**  – Sarakeotsikoiden fonttikoko.
* [**Korkeus**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin ylä- ja alareunan välinen etäisyys.
* [**Valintaväri** ](properties-color-border.md) – Tekstin väri rivillä, jonka päällä on hiiren kohdistin.
* [**Valintatäyttö** ](properties-color-border.md) – Taustaväri rivillä, jonka päällä on hiiren kohdistin.
* **Ei tietotekstiä** – Sanoma, joka ilmoittaa, että **Tietotaulukko**-ohjausobjektissa ei ole tietueita näytettäväksi.
* **Valittu väri** – Valitun rivin tekstin värin.
* **Valittu täyttö** – Valitun rivin taustaväri.
* [**Koko** ](properties-text.md) – Tietorivien tekstin oletusmuotoinen fonttikoko.
* [**Näkyvissä** ](properties-core.md) – Arvo, joka määrittää, onko **Tietotaulukko**-ohjausobjekti näkyvissä vai piilotettu.
* [**Leveys**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin vasemman ja oikean reunan etäisyys.
* [**X**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön vasemman reunan, jos pääsäilöä ei ole).
* [**X**](properties-size-location.md) – **Tietotaulukko**-ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön yläreunan, jos pääsäilöä ei ole).

## <a name="related-functions"></a>Liitetyt toiminnot
* [**Suodatin (tietolähde, kaava)**](../functions/function-filter-lookup.md)(*tietolähde*, *kaava*)
* [**Haku (tietolähde, hakujono, sarake)**](../functions/function-filter-lookup.md)(*tietolähde*, *hakujono*, *sarake*)

## <a name="examples"></a>Esimerkkejä
### <a name="basic-usage"></a>Peruskäyttö
1. Luo tyhjä tablettisovellus.
2. Valitse **Lisää**-välilehti ja napsauta tai napauta kohtaa **Tietotaulukko**.
   
    ![Lisää Tietotaulukko-ohjausobjekti näyttöön](./media/control-data-table/insert-data-table.png)
   
    Näyttöön lisätään **Tietotaulukko**-ohjausobjekti.
3. Vaihda **Tietotaulukko**-ohjausobjektin nimeksi **Myyntitilaustaulukko** ja muuta sen kokoa niin, että se täyttää koko näytön.
4. Napsauta tai napauta alanuolta, joka on oikeanpuoleisessa ruudussa olevan tekstin **Tietolähdettä ei ole valittu** oikealla puolella, ja napsauta tai napauta kohtaa **Lisää tietolähde**.
   
    ![Lisää tietolähde](./media/control-data-table/add-data-to-data-table.png)
5. Napsauta tai napauta yhteysluettelossa yhteyttä, jonka haluat luoda Common Data Service -tietokantaasi.
   
    ![Valitse yhteys tietolähteeseen](./media/control-data-table/choose-cds-data-table.png)
6. Napsauta tai napauta entiteettiluettelosta **Myyntitilaus** ja napsauta tai napauta **Yhdistä**.
   
    ![Valitse Myyntitilaus-entiteetti](./media/control-data-table/choose-so-data-table.png)
   
    **Tietotaulukko**-ohjausobjekti on nyt liitetty **Myyntitilaus**-tietolähteeseen. **Tietotaulukko**-ohjausobjektissa näkyy aluksi useita kenttiä, koska käytämme yhdistintä, joka tukee kyseistä ominaisuutta.
   
    ![Tietotaulukko](./media/control-data-table/pre-order-data-table.png)
7. Voit näyttää tai piilottaa kentät merkitsemällä valintamerkit haluamiesi vaihtoehtojen kohdalle oikeanpuoleisessa ruudussa.
   
    Jos haluat piilottaa esimerkiksi **Asiakkaan ostotilausviite**-kentän, merkitse sen vieressä oleva valintaruutu.
8. Voit muuttaa kenttien järjestystä oikeanpuoleisessa ruudussa vetämällä niitä ylös tai alas.
   
    ![Järjestä kentät haluamallasi tavalla](./media/control-data-table/field-re-order-data-table.png)
   
    Kentät näkyvät määrittämässäsi järjestyksessä **Myyntitilaustaulukko**-ohjausobjektissa.
   
    ![Päivitetty tietotaulukko](./media/control-data-table/post-order-data-table.png)

### <a name="restyle-the-header-for-the-data-table-control"></a>Muotoile tietotaulukko-ohjausobjektin otsikkoa
1. Kun **Tietotaulukko**-ohjausobjekti on valittuna, napsauta tai napauta oikeassa ruudussa olevaa **Lisäasetukset**-välilehteä.
2. Napsauta tai napauta **Otsikon täyttö** -ominaisuutta ja muuta arvoksi **RGBA(62,96,170,1)**.
3. Napsauta tai napauta **Otsikon väri** -ominaisuutta ja muuta arvoksi **Valkoinen**.
4. Napsauta tai napauta **Otsikon koko** -ominaisuuden kenttää ja muuta arvoksi **14**.
   
    ![Tietotaulukko](./media/control-data-table/restyled-data-table.png)

### <a name="connect-a-data-table-control-to-another-control"></a>Tietotaulukko-ohjausobjektin yhdistäminen toiseen ohjausobjektiin
1. Lisää näyttöön **Muokkauslomake**-ohjausobjekti.
2. Muuta **Tietotaulukko**- ja **Muokkauslomake** -ohjausobjektien kokoa niin, että **Tietotaulukko**-ohjausobjekti näkyy näytössä vasemmalla ja **Muokkauslomake**-ohjausobjekti näkyy oikealla.
   
    ![Tietotaulukko ja muokkauslomake samassa näytössä](./media/control-data-table/data-table-empty-form.png)
3. Kun **Lomake1** on valittuna, muuta oikeanpuoleisessa ruudussa sarakkeiden määräksi **1**.
4. Yhdistä **Lomake1** **Myyntitilaus**- tietolähteeseen.
   
    Useita kenttiä näkyy aluksi kohteessa **Lomake1**.
   
    ![Lomake1 ja alkuperäiset kentät](./media/control-data-table/data-table-disconnected-form.png)
5. Napsauta tai napauta oikeassa ruudussa olevaa **Lisäasetukset**-välilehteä.
6. Määritä **Lomake1**-ohjausobjektin **Kohde**-ominaisuudeksi **SalesOrderTable.Selected**.
   
    **Lomake1** näyttää valittuna olevan rivin tiedot **Tietotaulukko**-ohjausobjektissa.
   
    ![Tietotaulukkoon yhdistetty muokkauslomake](./media/control-data-table/connected-form-data-table.png)

