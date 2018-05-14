---
title: Skannaa viivakoodi | Microsoft Docs
description: Skannaa useita erityyppisiä viivakoodeja, kuten UPC ja Codabar
documentationcenter: na
author: aftowen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/23/2016
ms.author: anneta
ms.openlocfilehash: 6960b41effb109f6f2266ba279b4d51ea51e744f
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="scan-a-barcode-in-powerapps"></a>Skannaa viivakoodi PowerAppsissa
Skannaa useita erityyppisiä viivakoodeja luomalla sovellus ja suorittamalla se kamerallisessa laitteessa, kuten puhelimessa. Viivakoodia vastaava numeerinen arvo näkyy **Otsikko**-ohjausobjektissa, ja voit ladata nämä tiedot erilaisiin [tietolähteisiin](connections-list.md).

Jos et tunne PowerAppsia, katso [Aloittaminen](getting-started.md).

## <a name="known-limitations"></a>Tunnetut rajoitukset
* Viivakoodien on oltava vähintään 2,5 cm korkeita ja 4 cm leveitä.
* Skannaa viivakoodeja puhelimella: pidä puhelinta pystysuunnassa ja siirrä sitä hitaasti 18–25 cm:n päähän viivakoodista.
* Pitkät viivakoodityypit (kuten I2of5, jossa voi olla yli 15 merkkiä) voi antaa katkaistun tai muuten väärän tuloksen etenkin, jos viivakoodin tuloste on epäselvä.
* iPhone-ja Android-laitteissa voit määrittää **Viivakoodi**-ohjausobjektin **Korkeus**-ominaisuuden, mutta kiinteä kuvasuhde määrittää sen leveyden.
* Joudut ehkä määrittämään **Viivakoodi**-ohjausobjektin **Scanrate**-ominaisuudeksi **35** tai vähemmän.
* Voit pidentää muistin kestoa iOS-laitteissa määrittämällä **Viivakoodi**-ohjausobjektin **Korkeus**-ominaisuudeksi **700** (tai alhaisempi) ja **Scanrate**-ominaisuudeksi **30**.
* Jos muisti loppuu laitteesta ja sovellus kaatuu, käynnistä sovellus uudelleen.

## <a name="create-a-blank-app"></a>Tyhjän sovelluksen luominen
1. [Rekisteröidy PowerAppsiin](../signup-for-powerapps.md) ja tee sitten *jompikumpi* seuraavista toimista:

1. [Avaa PowerApps](https://create.powerapps.com) selaimessa laitteessa, jossa on kamera.

2. Napsauta tai napauta kohdassa **Aloita puhtaalta pöydältä tai mallin kanssa** **Puhelinasettelu** **Tyhjä sovellus** -ruudussa.

    ![Sovelluksen luominen alusta alkaen](./media/scan-barcode/create-from-blank.png)

3. Jos et ole käyttänyt PowerAppsia ennen, tutustu sovelluksen tärkeimpiin ominaisuuksiin käymällä johdanto läpi (tai napsauta tai napauta **Ohita**).

    ![Pikaesittelyn avausnäyttö](./media/scan-barcode/quick-tour.png)

    > [!NOTE]
> Voit aina katsella esittelyn myöhemmin napsauttamalla tai napauttamalla kysymysmerkkikuvaketta, joka on lähellä ruudun oikeaa yläkulmaa, ja napsauttamalla tai napauttamalla sitten **Katso esittely**.

## <a name="add-a-barcode-control"></a>Viivakoodi-ohjausobjektin lisääminen
1. Napsauta tai napauta **Lisää**-välilehdestä **Media** ja napsauta tai napauta sitten **Viivakoodi**.

    ![Lisää viivakoodiskanneri](./media/scan-barcode/add-scanner.png)

2. Varmista, että **Viivakoodi**-ohjausobjekti on valittuna vahvistamalla, että sen ympärillä on valintakehys (kahvoineen ohjausobjektin koon muuttamista varten).

    ![Valintaruutu](./media/scan-barcode/selection-box.png)

3. Napsauta tai napauta **Aloitus**-välilehdestä **Barcode1** ja kirjoita tai liitä **MyScanner** kohtaan **Nimeä uudelleen**.

    > [!TIP]
> Ensimmäinen lisäämäsi **Viivakoodi**-ohjausobjekti on oletusarvoisesti nimeltään **Barcode1**. Jos poistat kyseisen ohjausobjektin ja lisäät toisen **Viivakoodi**-ohjausobjektin, se saa oletusarvoisesti nimekseen **Barcode2**. Nimeämällä ohjausobjektin manuaalisesti voit varmistaa, että kaavat viittaavat ohjausobjektiin sen oikealla nimellä.

    ![Viivakoodin ohjausobjektin nimeäminen uudelleen](./media/scan-barcode/rename-barcode.png)

## <a name="add-a-text-input-control"></a>Lisää tekstisyötteen ohjausobjekti
1. Napsauta tai napauta **Lisää**-välilehdestä **Teksti** ja sitten **Tekstisyöte**.

    Jos **Lisää**-välilehti ei tule näkyviin, suurenna PowerApps-ikkunaa.

    ![Lisää tekstisyötteen ohjausobjekti](./media/scan-barcode/add-text-input.png)

2. Vedä valintakehys alas (ei koonmuuttokahvoja) **Tekstisyötteen**-ohjausobjektin ympärille, kunnes se näkyy **MyScanner**-kohdan alla.

    ![Otsikko ja valintakehys](./media/scan-barcode/move-input-text.png)

3. Varmista **Tekstisyöte**-ohjausobjektin ollessa yhä valittuna, että **Oletus** näkyy ominaisuusluettelossa, ja kirjoita tai liitä sitten **MyScanner.Text** kaavariville.

    ![Otsikko-ohjausobjektin Teksti-ominaisuus](./media/scan-barcode/default-text.png)

## <a name="change-the-barcode-type"></a>Muuta viivakoodin tyyppiä
1. Napsauta tai napauta **Lisää**-välilehdessä **Ohjausobjektit** ja sitten **Avattava luettelo**.

    ![Avattavan luettelon lisääminen](./media/scan-barcode/insert-dropdown.png)

2. Siirrä **Avattava luettelo** -ohjausobjektia siten, että se näkyy näytössä muiden ohjausobjektien alapuolella.

    ![Avattavan luettelon siirtäminen](./media/scan-barcode/move-dropdown.png)

3. Varmista **Avattava luettelo** -ohjausobjektin ollessa yhä valittuna, että **Kohteet** näkyy ominaisuusluettelossa, ja kirjoita tai liitä sitten tämä merkkijono kaavariville:<br>
    **[Codabar, Code128, Code39, Ean, I2of5, Upc]**

    ![Avattavan luettelon Kohteet-ominaisuuden määrittäminen](./media/scan-barcode/items-property.png)

4. Anna **Aloitus**-välilehdessä **Avattava luettelo** -ohjausobjektin uudeksi nimeksi **ChooseType**.

    ![Avattavan luettelon uudelleennimeäminen](./media/scan-barcode/rename-dropdown.png)

5. Valitse **MyScanner** napsauttamalla tai napauttamalla sitä, varmista, että ominaisuusluettelossa näkyy **BarcodeType**, ja kirjoita tai liitä sitten tämä merkkijono kaavariville:<br>
    **ChooseType.Selected.Value**

## <a name="test-the-app"></a>Sovelluksen testaus
1. Avaa esikatselutila painamalla F5-näppäintä (tai napsauttamalla tai napauttamalla toistokuvaketta oikean yläkulman läheltä).

    ![Esikatselutilan avaaminen](./media/scan-barcode/open-preview.png)

2. Pidä viivakoodia laitteen kameran edessä, kunnes viivakoodin numeerinen osa näkyy **Otsikko**-ohjausobjektissa.

    Jos numeerista osaa ei näy, kokeile eri asetusta **BarcodeType**-luettelossa. Jos oikeat tiedot eivät vieläkään näy, kirjoita oikea numero **Tekstisyöte**-ohjausobjektiin.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Yhdistä sovellus tietolähteeseen](add-data-connection.md) ja määritä **[Ohjelmakorjaus](functions/function-patch.md)**-funktio siten, että käyttäjät voivat tallentaa tulokset.
* Lisää **[Avattava luettelo](controls/control-drop-down.md)** -ohjausobjekti ja määritä se niin, että käyttäjät voivat valita skannattavan viivakoodin.
* Lisää **[Liukusäädin](controls/control-slider.md)**-ohjausobjekti ja määritä se niin, että käyttäjät voivat säätää **Viivakoodi**-ohjausobjektin skannausnopeutta tai korkeutta.
