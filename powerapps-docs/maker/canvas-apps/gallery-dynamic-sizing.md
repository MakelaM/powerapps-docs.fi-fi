---
title: Erikorkuisten kohteiden näyttäminen valikoimassa | Microsoft Docs
description: Voit lisätä ja määrittää korkeudet valikoimaan niin, että ne sopivat automaattisesti kunkin kohteen sisältöön
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/01/2017
ms.author: fikaradz
ms.openlocfilehash: a6f475277e7cde25fea350634aa60e8b150e304d
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39018579"
---
# <a name="show-items-of-different-heights-in-a-powerapps-gallery"></a>Erikorkuisten kohteiden näyttäminen PowerApps-valikoimassa
Jos tietojoukon kentässä on kohteita, joiden tietomäärät poikkeavat toisistaan, voit näyttää enemmän tietoja sisältävän kohteen kokonaan tarvitsematta jättää tyhjää tilaa vähemmän tietoja sisältävien kenttien loppuun. Lisää ja määritä valikoiman ohjausobjektille **joustava korkeus**, jotta voit:

* Määrittää **Otsikko**-ohjausobjekteja, joiden sisältöjen perusteella kenttiä suurennetaan tai pienennetään.
* Sijoita kukin ohjausobjekti niin, että se ilmaantuu automaattisesti yläpuolella olevan ohjausobjektin yläpuolelle.

Tässä opastustoiminnossa haetaan lattiapäällystetuotteita koskevia tietoja ohjausobjektiin, jossa käytetään **Joustava korkeus** -ominaisuutta. Kunkin tuotteen kuva näkyy viiden (5) kuvapisteen verran tuotteen kuvauksen alapuolella, riippumatta siitä, onko kuvauksessa viisi vai kaksi riviä tekstiä.

![Lopullinen sovellus](./media/gallery-dynamic-sizing/dynamic-app.png)

**Suositeltavat ohjeet**

Jos et ole koskaan lisännyt ohjausobjekteja valikoimaan, katso ohjeet kohdasta [Kohdeluettelon näyttäminen](add-gallery.md), ennen kuin jatkat tätä opastustoimintoa.

## <a name="add-data-to-a-blank-app"></a>Tietojen lisääminen tyhjään sovellukseen
1. Lataa [tämä Excel-tiedosto](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), joka sisältää lattiapäällystetuotteiden nimiä, yleiskuvauksia ja linkkejä kuviin.

    ![Lattiapäällystetuotteet](./media/gallery-dynamic-sizing/flooring-products.png)

2. Lataa Excel-tiedosto pilvitallennuspalveluun, kuten OneDriveen, Dropboxiin tai Google Driveen.

3. Napsauta tai napauta PowerApps Studion **Tiedosto-valikon** kohtaa **Uusi**.

4. Napsauta tai napauta **Tyhjä sovellus** -ruudussa kohtaa **Puhelinasettelu**.

    ![Tiedosto-valikon Uusi-vaihtoehto](./media/gallery-dynamic-sizing/blank-app.png)

5. Lisää yhteys Excel-tiedoston **FlooringEstimates**-taulukkoon.

    Lisätietoja on kohdassa [Yhteyden lisääminen](add-data-connection.md).

## <a name="add-data-to-a-gallery"></a>Tietojen lisääminen valikoimaan
1. Napsauta tai napauta **Lisää**-välilehdessä **Valikoima**, ja napsauta tai napauta **Joustava korkeus**.

    ![Lisää valikoima](./media/gallery-dynamic-sizing/add-flexible.png)
2. Muuta valikoiman mitat niin, että se täyttää koko näytön.

3. Määritä valikoiman **[Kohteet](controls/properties-core.md)**-ominaisuuden asetukseksi **FlooringEstimates**.

## <a name="show-the-product-names"></a>Tuotenimien näyttäminen
1. Napsauta tai napauta valikoiman vasemmassa yläkulmassa olevaa kynäkuvaketta ja valitse haluamasi valikoiman mallipohja.

    ![Kynäkuvake](./media/gallery-dynamic-sizing/edit-template.png)

2. Kun Valikoiman mallipohja on valittuna, lisää siihen **[Otsikko](controls/control-text-box.md)**- ohjausobjekti.

3. Määritä **Otsikko**-ohjausobjektin **Teksti**-ominaisuus tällä lausekkeella:<br>
   **ThisItem.Name**

    ![Lisää otsikko](./media/gallery-dynamic-sizing/add-text-box.png)

## <a name="show-the-product-overviews"></a>Tuotekuvausten näyttäminen
1. Kun valikoiman mallipohja on valittuna, lisää toinen **Otsikko**-ohjausobjekti ja siirrä se ensimmäisen **Otsikko**-ohjausobjektin alle.  

2. Määritä toisen **Otsikko**-ohjausobjektin **Teksti**-ominaisuus tällä lausekkeella:<br> **ThisItem.Overview**

3. Kun toinen **Otsikko**-ohjausobjekti on valittuna, napsauta tai napauta **Sisältö**-välilehdessä olevaa nimitunnisteen kuvaketta ja muuta ohjausobjektin nimeksi **OverviewText**.

    ![Otsikon nimeäminen uudelleen](./media/gallery-dynamic-sizing/rename-text-box.png)

4. Aseta **AutoHeight**-ominaisuuden **OverviewText**-ruudun arvoksi **tosi**.

    Tällä vaiheella varmistetaan, että ruutu suurenee tai pienenee sisällön mukaan.

      ![Tekstin korkeuden automaattinen säätö](./media/gallery-dynamic-sizing/autoheight-text.png)

## <a name="show-the-product-images"></a>Tuotekuvien näyttäminen
1. Muuta mallipohjan koko kaksi kertaa alkuperäistä korkeammaksi.

    Näin sinun on helpompi lisätä rakennettavan sovelluksen mallipohjaan ohjausobjekteja, eikä muutos vaikuta siihen, miltä sovellus näyttää, kun sitä käytetään.

2. Kun valikoiman mallipohja on valittuna, lisää toinen **[Kuva](controls/control-image.md)**-ohjausobjekti ja siirrä se ensimmäisen **OverviewText**-ohjausobjektin alle.

3. Varmista, että **Kuva**-ohjausobjektin **Kuva**-ominaisuus määritetään seuraavalla lausekkeella:<br>
    **ThisItem.Image**

4. Määritä **Kuva**-ohjausobjektin **[Y](controls/properties-core.md)**-asetus **OverviewText**-ruudun sijainnin ja koon perusteella seuraavan lausekkeen mukaisesti:
   <br>**OverviewText.Y + OverviewText.Height + 5**

    ![Lopullinen sovellus](./media/gallery-dynamic-sizing/final-app.png)

Jos haluat lisätä useita ohjausobjekteja, käytä samaa menetelmää: määritä kunkin ohjausobjektin **Y**-asetus yläpuolella olevan ohjausobjektin **Y**- ja **Korkeus**-ominaisuuksien perusteella.

## <a name="next-steps"></a>Seuraavat vaiheet
Lue lisää siitä, miten voit käsitellä [valikoiman](working-with-forms.md) ohjausobjektia ja [kaavoja](working-with-formulas.md).
