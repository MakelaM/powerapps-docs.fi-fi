---
title: Näytä, lajittele ja suodata tietoja valikoimassa | Microsoft Docs
description: Valikoiman avulla voit näyttää kuvia ja tekstiä. Lajittele ja suodata kuvia PowerAppsissa.
author: adrianorth
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/02/2015
ms.author: aorth
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3a25654f0304fce9978ae1f7b1410cfb557ef32c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995589"
ms.PowerAppsDecimalTransform: true
---
# <a name="show-sort-and-filter-data-in-a-powerapps-gallery"></a>Näytä, lajittele ja suodata tietoja PowerApps-valikoimassa
Luo valikoima, jonka avulla voit näyttää kuvia ja tekstiä useista tuotteista, ja lajittele ja suodata näitä tietoja.

PowerAppsissa voit valikoiman avulla näyttää useita liittyviä kohteita samalla tavalla kuin luettelossa. Valikoimissa esittelet kätevästi tuotteiden tietoja, kuten nimiä ja hintoja. Tässä ohjeaiheessa luomme valikoiman ja lajittelemme ja suodatamme sen tietoja Excel-tyyppisten funktioiden avulla. Lisäksi, kun kohde on valittuna, sen ympärillä näkyy reuna.

> [!NOTE]
> Tässä ohjeaiheessa käytetään tablettisovellusta. Voit käyttää puhelinsovellusta, mutta joudut muuttamaan joidenkin ohjausobjektien kokoa.
> 
> 

### <a name="prerequisites"></a>Edellytykset
* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
* Luo tablettisovellus [mallista](get-started-test-drive.md), [tiedoista](get-started-create-from-data.md) tai [tyhjästä](get-started-create-from-blank.md).
* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md).
* Näissä vaiheissa käytetään [CreateFirstApp](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip)-sovellusta mallisyötetietoina, jotka sisältävät .jpg-kuvia. Zip-tiedosto sisältää XML-tiedoston, joka voidaan muuntaa Excel-muotoon. Muussa tapauksessa PowerApps lukee .zip-tiedostojen tiedostot automaattisesti ja tuo sitten tiedot onnistuneesti. Voit ladata ja käyttää mallitietoja tai tuoda omasi.

## <a name="show-data-in-a-gallery"></a>Tietojen näyttäminen valikoimassa
1. Luo valikoima nimeltä **Inventory** mallitietoja käyttäen. Tähän kuuluvat seuraavat vaiheet:  
   
   1. Valitse **Lisää**-välilehdestä **Ohjausobjektit** ja valitse sitten **Tuo**:
      
      ![][1]  
   2. Määritä tuontiohjausobjektin **[OnSelect](controls/properties-core.md)** -ominaisuudeksi seuraava kaava:  
      **Collect (Inventory, Import1. Data)**
      
      ![][12]  
   3. Avaa Windowsin Resurssienhallinta valitsemalla **Tuo tiedot** -painike. Valitse *CreateFirstApp.zip* ja sitten **Avaa**.
   4. Valitse **Tiedosto**-valikosta **Kokoelmat**. Inventory-kokoelma näytetään, ja se sisältää tuomasi tiedot:
      
      ![][3]  
      
      Olemme nyt luoneet Inventory-kokoelman, joka sisältää viiden tuotteen tietoja, kuten mallikuvan, tuotteen nimen ja kappaleiden määrän varastossa.
      
      > [!NOTE]
      > Tuontiohjausobjektilla tuodaan Excel-tyyppisiä tietoja ja luodaan kokoelma. Tuontiohjausobjekti tuo tiedot, kun luot ja esikatselet sovellusta. Tuontiohjausobjekti ei tällä hetkellä tuo tietoja, kun sovellus julkaistaan.
      > 
      > 
2. Palaa suunnittelijatyökaluun valitsemalla taaksepäin osoittava nuoli.
3. Napsauta tai napauta **Lisää**-välilehdessä **Valikoima** ja sitten **Vaaka**-valikoima.
   
    ![][4]
4. Napsauta tai napauta oikeanpuoleisessa ruudussa vaihtoehtoa, jossa otsikko ja alaotsikko peittävät grafiikan:
   
    ![][15]
5. Määritä valikoiman **[Items](controls/properties-core.md)** -ominaisuudeksi **Inventory**:
   
    ![][5]
6. Anna valikoimalle uusi nimi **ProductGallery** ja siirrä valikoimaa siten, että se ei peitä muita ohjausobjekteja. Muuta valikoiman kokoa siten, että siinä näkyy kolme tuotetta:
   
    ![][6]
7. Valitse valikoiman ensimmäisen kohteen alaosassa oleva selite:  
   
    ![][7]  
   
   > [!NOTE]
   > Kun muutat minkä tahansa valikoiman ensimmäistä kohdetta, muutat automaattisesti valikoiman kaikkia muita kohteita.  
   > 
   > 
8. Määritä selitteen **[Text](controls/properties-core.md)** -ominaisuudeksi seuraava lauseke:  
    **Kohteen ThisItem. Unitsinstanck** <br/>
   
    Tämän jälkeen selite näyttää kappaleiden lukumäärän varastossa kullekin tuotteelle:

![][8]  

> [!NOTE]
> Yläselitteen **[Text](controls/properties-core.md)** -ominaisuudeksi tulee oletusarvoisesti ```ThisItem.ProductName```. Voit muuttaa sen joksikin muuksi kohteeksi kokoelmassa. Jos kokoelmassa on esimerkiksi kentät *ProductDescription* tai *Price*, voit määrittää selitteeksi ```ThisItem.ProductDescription``` tai ```ThisItem.Price```.
> 
> 

Näissä vaiheissa toimme kokoelmaan .jpg-kuvia sisältäviä tietoja. Sitten lisäsimme valikoiman, jossa näkyvät nämä tiedot, ja määritimme selitteen, joka ilmoittaa kunkin tuotteen varastossa olevan määrän.

## <a name="highlight-the-gallery-item-you-select"></a>Korosta valitsemasi valikoiman kohde
1. Valitse mikä tahansa valikoiman kohde *paitsi* ensimmäinen. Muokkauskuvake tulee näkyviin (vasemmassa yläkulmassa). Valitse muokkauskuvake:  
   ![][9]  
2. Valitse **Lisää**-välilehdestä **Muodot** ja valitse sitten suorakulmio. Täytetty sininen suorakulmio tulee näkyviin valikoiman jokaisen kohteen kohdalle.
3. Valitse **Aloitus**-välilehdestä **Täyttö** ja sitten **Ei täyttöä**.
4. Valitse **Reunus**, **Reunan tyyli** ja sitten yhtenäinen viiva.
5. Valitse **Reunus** uudelleen ja aseta paksuudeksi 3. Muuta suorakulmion kokoa niin, että se ympäröi valikoiman kohteen. Valikoiman kohteissa on nyt sininen reunaviiva, joka näyttää seuraavanlaiselta:  
   ![][10]  
6. Valitse **Muoto**-välilehdessä **Näkyvissä** ja kirjoita sitten kaavariville seuraava kaava:  
   
    **If (ThisItem. onselected, True)**
   
    Sininen suorakulmio ympäröi nykyisen valinnan valikoimassa. Vahvista, että suorakulmio näkyy jokaisen valitsemasi kohteen ympärillä valitsemalla muutamia valikoiman kohteita. Muista, että voit myös avata **esikatselun** ![][2] ja tarkastaa ja testata tuloksen.

> [!TIP]
> Valitse suorakulmio, valitse sitten **Aloitus**-välilehdessä **Järjestä uudelleen** ja lopuksi **Lähetä taustalle**. Tämän toiminnon avulla voit valita valikoiman kohteen ilman, että reunus peittää mitään.
> 
> 

Näissä vaiheissa lisäsimme reunuksen valikoiman nykyisen valinnan ympärille.

## <a name="sort-and-filter-items-in-the-gallery"></a>Valikoiman kohteiden lajitteleminen ja suodattaminen
Näissä vaiheissa lajittelemme valikoiman kohteet nousevassa ja laskevassa järjestyksessä. Lisäksi lisäämme liukusäätimen, jolla suodatetaan valitsemiasi varastossa olevia valikoiman kohteita.

#### <a name="sort-in-ascending-or-descending-order"></a>Lajittelu nousevassa tai laskevassa järjestyksessä
1. Valitse mikä tahansa valikoiman kohde *paitsi* ensimmäinen.
2. **[Items](controls/properties-core.md)** -ominaisuutena on tällä hetkellä Inventory (kokoelmasi nimi). Muuta se seuraavaksi:  
   
    **Sort(Inventory; ProductName)**
   
    Kun teet näin, valikoiman kohteet lajitellaan nousevassa järjestyksessä tuotteen nimen mukaan:  ![][11]  
   
    Kokeile laskevaa järjestystä. Määritä valikoiman **[Items](controls/properties-core.md)** -ominaisuudeksi seuraava kaava:  
   
    Sort(Inventory, ProductName, Descending)  

#### <a name="add-a-slider-control-and-filter-items-in-the-gallery"></a>Lisää liukusäädin ja suodata kohteita valikoimassa
1. Lisää liukusäädin (**Lisää**-välilehti > **Ohjausobjektit**), anna sille uusi nimi **StockFilter** ja siirrä se valikoiman alle.
2. Määritä liukusäädin niin, että käyttäjät eivät voi määrittää sitä varastossa olevien kohteiden lukumäärän ulkopuolelle:  
   
   1. Valitse **Sisältö**-välilehdestä **Pienin** ja kirjoita sitten seuraava lauseke:  
      ```Min(Inventory; UnitsInStock)```  
   2. Valitse **Sisältö**-välilehdestä **Suurin** ja kirjoita sitten seuraava lauseke:  
      ```Max(Inventory; UnitsInStock)```
3. Valitse mikä tahansa valikoiman kohde *paitsi* ensimmäinen. Määritä valikoiman **[Items](controls/properties-core.md)** -ominaisuudeksi seuraava lauseke:  
   ```Filter(Inventory; UnitsInStock<=StockFilter.Value)```
4. Aseta **esikatselussa** liukusäädin arvoon, joka on valikoiman suurimman ja pienimmän määrän välissä. Kun säädät liukusäädintä, valikoimassa näkyvät vain ne tuotteet, joita on valitsemaasi arvoa vähemmän:  
   ![][13]  

Lisätään seuraavaksi suodatin:

1. Palaa takaisin suunnittelutyökaluun.
2. Valitse **Lisää**-välilehdessä **Teksti**, valitse **Syöteteksti** ja anna uudelle ohjausobjektille uusi nimi **NameFilter**. Siirrä Teksti-ohjausobjekti liukusäätimen alle.
3. Määritä valikoiman **[Items](controls/properties-core.md)** -ominaisuudeksi seuraava lauseke:  
   ```Filter(Inventory; UnitsInStock<=StockFilter.Value && NameFilter.Text in ProductName)```
4. Aseta **esikatselussa** liukusäädin arvoon *30* ja kirjoita kirjain *g* Tekstisyöte-ohjausobjektiin. Näyttöön tulee valikoiman ainoa tuote, jota on varastossa alle 30 kappaletta *ja* jonka nimessä on g-kirjain:  
   ![][14]  

## <a name="tips-and-tricks"></a>Vihjeitä ja vinkkejä
* Voit valita Esikatselu-painikkeen (![][2]) milloin tahansa ja katsella ja testata tulosta.
* Voit muuttaa ohjausobjektien kokoa ja siirrellä niitä napsauttamalla ja vetämällä, kun suunnittelet sovellustasi.
* Sulje esikatseluikkuna painamalla **ESC**-näppäintä tai valitsemalla **X**-merkki.
* Kun käytät valikoimaa, valitse sen ensimmäinen kohde, kun haluat tehdä muutoksia kaikkiin valikoiman kohteisiin. Valitse ensimmäinen kohde, kun haluat lisätä esimerkiksi reunan kaikkiin valikoiman kohteisiin.
* Voit päivittää valikoiman ominaisuuksia valitsemalla minkä tahansa valikoiman kohteen *paitsi* ensimmäisen. Valitse esimerkiksi toinen kohde, kun haluat päivittää *Items*- tai *ShowScrollbar*-ominaisuuksia, jotka koskevat valikoimaa (ei valikoiman kohteita).  

## <a name="what-you-learned"></a>Mitä opimme
Tässä aiheessa:

* Loimme kokoelman, toimme .jpg-kuvia sisältäviä tietoja kokoelmaan ja näytimme valikoiman tiedot.
* Määritimme valikoiman kunkin kuvan alapuolelle selitteen, joka ilmoittaa kyseisen kohteen kappalemäärän varastossa.
* Lisäsimme reunuksen valitun kohteen ympärille.
* Lajittelimme kohteet tuotteen nimen mukaan nousevassa ja laskevassa järjestyksessä.
* Lisäsimme liukusäätimen ja Syöteteksti-ohjausobjektin, jolla suodatimme tuotteita niiden varastossa olevan lukumäärän ja tuotteen nimen mukaan.

[1]: ./media/show-images-text-gallery-sort-filter/import.png
[2]: ./media/show-images-text-gallery-sort-filter/preview.png
[3]: ./media/show-images-text-gallery-sort-filter/inventorycollection.png
[4]: ./media/show-images-text-gallery-sort-filter/insert-vertical.png
[5]: ./media/show-images-text-gallery-sort-filter/itemsinventory.png
[6]: ./media/show-images-text-gallery-sort-filter/threeimages.png
[7]: ./media/show-images-text-gallery-sort-filter/firstitem.png
[8]: ./media/show-images-text-gallery-sort-filter/bottomlabel.png
[9]: ./media/show-images-text-gallery-sort-filter/editgallery.png
[10]: ./media/show-images-text-gallery-sort-filter/border.png
[11]: ./media/show-images-text-gallery-sort-filter/sort.png
[12]: ./media/show-images-text-gallery-sort-filter/onselect.png
[13]: ./media/show-images-text-gallery-sort-filter/slider.png
[14]: ./media/show-images-text-gallery-sort-filter/inputandslider.png
[15]: ./media/show-images-text-gallery-sort-filter/select-overlay.png
