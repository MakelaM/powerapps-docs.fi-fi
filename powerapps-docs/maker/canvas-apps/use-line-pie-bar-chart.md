---
title: Kaavion luominen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Tietoluokkien näyttäminen PowerAppsissa viiva-, ympyrä- tai palkkikaavioina pohjaan perustuvassa sovelluksessa
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/23/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0b710346c5e264fc13ee3cacb00073a32a4de0f0
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63318311"
---
# <a name="show-data-in-a-line-pie-or-bar-chart-in-powerapps"></a>Tietojen näyttäminen viiva-, ympyrä- tai palkkikaavioina PowerAppsissa

Käytä viiva-, ympyrä- ja palkkikaavioita tietojesi näyttämiseen pohjaan perustuvassa sovelluksessa. Kun käsittelet kaavioita, tuomiesi tietojen jäsentelyn tulee perustua seuraaviin ehtoihin:

* Jokaisen sarjan tulee olla ensimmäisellä rivillä.
* Otsikkojen tulee olla vasemmanpuoleisimmassa sarakkeessa.

Tietojesi tulee näyttää esimerkiksi seuraavan kaltaisilta:

![][9]

Voit luoda ja käyttää näitä kaavioita PowerAppsissa. Aloitetaan.

## <a name="prerequisites"></a>Edellytykset

* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
* Luo sovellus [mallista](get-started-test-drive.md), [tiedoista](get-started-create-from-data.md) tai itse [alusta alkaen](get-started-create-from-blank.md).
* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md) PowerAppsissa.
* Lataa [ChartData.zip](http://pwrappssamples.blob.core.windows.net/samples/ChartData.zip), joka sisältää mallitietoja XML-tiedostomuodossa. Tuo tiedosto suoraan sovellukseesi noudattamalla tämän aiheen vaiheita. Voit vaihtoehtoisesti purkaa .zip-tiedoston, avata XML-tiedoston Excelissä ja tallentaa tiedoston [pilvipalveluun](connections/cloud-storage-blob-connections.md).

## <a name="import-the-sample-data"></a>Mallitietojen tuominen
Näissä vaiheissa tuomme mallitiedot kokoelmaan, jonka nimi on **ProductRevenue**.

1. Valitse **Lisää**-välilehdestä **Ohjausobjektit** ja valitse sitten **Tuo**:  

    ![][11]  

2. Määritä ohjausobjektin **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava funktio:  

   ```Collect(ProductRevenue, Import1.Data)```

3. Avaa esikatselutila painamalla F5-näppäintä ja valitse **Tuo tiedot** -painike.

4. Valitse **Avaa**-valintaikkunassa ChartData.zip, valitse **Avaa** ja paina sitten Esc-näppäintä.

5. Valitse **Tiedosto**-valikosta **Kokoelmat**.

    Näyttöön tulee ProductRevenue-kokoelma, joka sisältää tuomasi kaaviotiedot:

    ![][1]  

   > [!NOTE]
   > Tuontiohjausobjektin avulla tuodaan Excel-tyyppisiä tietoja ja luodaan kokoelma. Tuontiohjausobjekti tuo tiedot, kun luot ja esikatselet sovellusta. Tuontiohjausobjekti ei tällä hetkellä tuo tietoja, kun sovellus julkaistaan.
   >

6. Palaa oletustyötilaan painamalla Esc-näppäintä.

## <a name="add-a-pie-chart"></a>Ympyräkaavion lisääminen
1. Valitse **Lisää**-välilehdellä **Kaaviot** ja valitse sitten **Ympyräkaavio**.

2. Siirrä ympyräkaavio **Tuo tiedot** -painikkeen alle.

3. Valitse ympyräkaavion keskikohta ympyräkaavion ohjausobjektissa:   

    ![][10]

4. Määritä ympyräkaavion **[Items](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke: `ProductRevenue.Revenue2014`

    ![][2]  

    Ympyräkaavio näyttää vuoden 2014 tuottotiedot.

    ![][3]  

## <a name="add-a-bar-chart-to-display-your-data"></a>Palkkikaavion lisääminen tietojen näyttämiseksi
Käytämme seuraavaksi ProductRevenue-kokoelmaa palkkikaaviossa:

1. Lisää näyttö **Aloitus**-välilehdellä.]

2. Valitse **Lisää**-välilehdellä **Kaaviot** ja valitse sitten **Pylväskaavio**.

3. Valitse pylväskaavion keskikohta. Määritä pylväskaavion **[Items](controls/properties-core.md)**-ominaisuudeksi ```ProductRevenue```:

    ![][12]  

    Pylväskaavio näyttää vuoden 2012 tuottotiedot:

    ![][4]  

4. Valitse keskimmäinen neliö pylväskaaviossa:

    ![][5]

5. Valitse **Kaavio**-välilehdellä **Sarjan numero** ja syötä kaavariville **3**:

    ![][6]  

    Pylväskaavio näyttää kunkin tuotteen tuottotiedot kolmen vuoden ajalta:

    ![][7]  

[1]: ./media/use-line-pie-bar-chart/productrevenuecollection.png
[2]: ./media/use-line-pie-bar-chart/itemsexpression.png
[3]: ./media/use-line-pie-bar-chart/piechart.png
[4]: ./media/use-line-pie-bar-chart/columnchart.png
[5]: ./media/use-line-pie-bar-chart/columnchartseries.png
[6]: ./media/use-line-pie-bar-chart/columnchartseriesfunction.png
[7]: ./media/use-line-pie-bar-chart/columnchartthreeyears.png
[8]: ./media/use-line-pie-bar-chart/preview.png
[9]: ./media/use-line-pie-bar-chart/tableformat.png
[10]: ./media/use-line-pie-bar-chart/middlepiechart.png
[11]: ./media/use-line-pie-bar-chart/import.png
[12]: ./media/use-line-pie-bar-chart/itemscolumnchart.png
