---
title: Luo ja päivitä kokoelma | Microsoft Docs
description: Luo kokoelmia ja lisää sarakkeita olemassa oleviin kokoelmiin PowerAppsissa
documentationcenter: ''
author: lonu
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 11/30/2015
ms.author: lonu
ms.openlocfilehash: 01065fd1a12b3d55e8726582cead3d86a6e6a8ad
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="create-and-update-a-collection-in-your-app"></a>Luo ja päivitä kokoelma sovelluksessasi
Kokoelman avulla voit tallentaa tietoja, joita voidaan käyttää sovelluksessasi. Kokoelma on joukko kohteita, jotka ovat samankaltaisia. Voit luoda esimerkiksi MyImages-kokoelman, johon tallennat kuvat kaikista tuotteista, joita yrityksesi myy. PowerAppsissa voit lisätä MyImages-kokoelman ja luoda sovelluksen, joka näyttää kuvia kyseisistä tuotteista. Voit myös luoda hinnastokokoelman, joka sisältää luettelon tuotteista ja kunkin tuotteen hinnan.

Voit luoda ja käyttää kokoelmia PowerAppsissa. Aloitetaan.

### <a name="prerequisites"></a>Edellytykset
* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin [ja kirjaudu sitten sisään](https://web.powerapps.com) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
* Luo sovellus tai avaa olemassa oleva sovellus PowerAppsissa.
* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md) PowerAppsissa.
* Näissä ohjeissa käytetään esimerkkisyötetietona [PriceList.zip](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip)-tiedostoa. Zip-tiedosto sisältää XML-tiedoston, joka voidaan muuntaa Excel-muotoon. Muussa tapauksessa PowerApps lukee .zip-tiedostojen tiedostot automaattisesti ja tuo sitten tiedot onnistuneesti. Voit ladata ja käyttää mallitietoa tai tuoda omasi.

## <a name="create-a-single-column-collection"></a>Luo yksisarakkeinen kokoelma
Seuraavissa vaiheittaisissa ohjeissa kerrotaan, miten luot Collect-funktiolla kokoelman sovelluksessasi ja miten lisäät kohteita kokoelmaan.

1. Avaa sovelluksesi.
2. Valitse **Lisää**-välilehdeltä **Teksti** ja valitse sitten **Tekstisyöte**:  
   ![][1]  
3. Valitse vasemmassa yläkulmassa **Teksti1** ja nimeä ohjausobjekti uudelleen nimellä **Kohde**:  
   ![][2]  
4. Lisää suunnittelutyökaluusi painikeohjausobjekti valitsemalla **Lisää**-välilehdeltä **Painike**. Avattavassa luettelossa näkyy **[OnSelect](controls/properties-core.md)**-ominaisuus. Aseta sen arvoksi seuraava funktio:  
   
    ```Collect(Destinations, Destination!Text)```
   
    Sen pitäisi näyttää tältä:  
    ![][3]  
5. Valitse painikkeen teksti ja kirjoita **Lisää**:  
   ![][5]  
6. Valitse **Lisää**-painike ja siirrä se tekstiohjausobjektisi alle. Voit siirtää sen haluamaasi kohtaan:  
   ![][6]  

Loit edellisissä vaiheissa kokoelman nimeltä **Destinations** käyttämällä Collect-funktiota. Lisäsit myös painikeohjausobjektin, jonka valitsemalla voit lisätä uusia kohteita kokoelmaasi. Nyt näet, mitä olet luonut:

1. Valitse esikatselu:  
   ![][7]  
2. Kirjoita ruutuun kaupungin nimi ja valitse sitten **Lisää**-painike.
3. Anna lisää kaupunkien nimiä ja valitse jokaisen jälkeen **Lisää**.
4. Sulje esikatseluikkuna painamalla **Esc**-näppäintä.
5. Näet Destinations-kokoelman ja antamasi tekstiarvot. Valitse **Tiedosto**-välilehdeltä **Kokoelmat**. Kirjoittamasi teksti näkyy luettelossa:  
   ![][8]

#### <a name="extra-credit"></a>Lisätehtävä
Sidotaan Destinations-kokoelma luetteloruutuun:

1. Palaa takaisin suunnittelutyökaluusi.
2. Valitse **Lisää**-välilehdeltä **Ohjausobjektit** ja valitse sitten **Luetteloruutu**:  
   ![][22]  
3. Siirrä luetteloruutua, jotta näet sen helposti. Määritä sen **[Items](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:  
   ```Destinations!Value```  <br/>
   
    Kun teet näin, luetteloruutu täytetään automaattisesti kohteilla, jotka olet aiemmin lisännyt Destinations-kokoelmaan:  
   ![][4]  

Esikatsele tekemiäsi muutoksia: ![][7]. Antamasi kaupungit näkyvät luetteloruudussa. Kirjoita tekstisyöte-ohjausobjektiin uusi kaupunki ja valitse **Lisää**-painike. Antamasi uusi kaupunki päivittyy automaattisesti luetteloruutuun.

## <a name="create-a-multi-column-collection"></a>Luo monisarakkeinen kokoelma
Seuraavissa vaiheittaisissa ohjeissa näytetään, miten luot Collect-funktiolla kokoelman sovelluksessasi ja miten lisäät kokoelmaan useita rivejä.

1. Avaa **Aloitus**-välilehdeltä uusi näyttö.
2. Valitse **Lisää**-välilehdeltä **Teksti** ja valitse sitten **Tekstisyöte**.
3. Nimeä tekstiohjausobjekti uudelleen nimellä **City**:  
   ![][9]  
4. Lisää toinen tekstisyöte-ohjausobjekti ja nimeä se uudelleen nimellä **States**.
5. Siirrä City- ja States-tekstiohjausobjekteja siten, että näet ne molemmat:  
   ![][10]  
   
    > [!NOTE]
> Voit korvata tekstinsyötön toisella sanalla, esimerkiksi sanalla ”city” tai ”state”, kuten kuvassa on tehty.  
6. Valitse **Lisää**-välilehdeltä **Painike**. Määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava funktio:  
   ```Collect(Destinations, {Cities:City!Text, States:States!Text})```  
   
    Sen pitäisi näyttää tältä:  
    ![][11]  
   
    > [!NOTE]
> Saman funktion avulla voit lisätä sarakkeita kokoelmaan. Voit lisätä esimerkiksi toisen tekstisyöte-ohjausobjektin Country, jos haluat lisätä Countries-sarakkeen:
   
    `Collect(Destinations, {Cities:City!Text, States:States!Text}, {Countries:Country!Text})`
7. Nimeä painikeohjausobjekti uudelleen nimellä **AddCityStateButton** ja määritä sen **[Text](controls/properties-core.md)**-ominaisuudeksi **Add City and State**:  
   ![][12]  

Näitä vaiheita noudattamalla lisäsit **Destinations**-kokoelmaan **Cities**- ja **States**-sarakkeet. Painikeohjausobjekti lisää uudet tekstikohteet kokoelmaasi. Nyt näet, mitä olet luonut:

1. Valitse esikatselu:  
   ![][7]  
2. Kirjoita tekstiä City- ja State-ruutuihin ja valitse sitten **Add City and State** -painike.
3. Lisää vielä muutama kaupunki ja osavaltio.
4. Sulje esikatseluikkuna painamalla **Esc**-näppäintä.
5. Voit tarkastella Destinations-kokoelmaan lisäämiäsi kohteita valitsemalla **Tiedosto**-välilehden ja valitsemalla sitten **Kokoelmat**:  
   ![][13]

## <a name="add-columns-to-a-collection"></a>Lisää sarakkeita kokoelmaan
Tässä ohjeessa on muutama osa. Kun olet valmis, osaat tuoda tietoja kokoelmaan ja luoda valikoiman, joka sisältää tietoja hinnastossa. Osaat myös käyttää liukusäädintä, joka määrittää tuotteiden määrän.

### <a name="import-the-price-list-and-create-the-collection"></a>Tuo hinnasto ja luo kokoelma
1. Lataa [PriceList.zip](http://pwrappssamples.blob.core.windows.net/samples/PriceList.zip)-tiedosto.
2. Lisää **Aloitus**-välilehdeltä uusi näyttö.
3. Valitse **Lisää**-välilehdeltä **Ohjausobjektit** ja valitse sitten **Tuo**:  
   ![][14]  
4. Valitse **Toiminto**-välilehdeltä **OnSelect**. Kirjoita seuraava funktio:  
   
    ```Collect(PriceList, Import1!Data)```  
5. Esikatsele sovellustasi. Valitse **Tuo tiedot** -painike, valitse PriceList.zip-tiedosto ja valitse **Avaa**.
6. Sulje esikatseluikkuna.
7. Valitse **Tiedosto**-välilehdeltä **Kokoelmat**. Tuodut hinnastokohteet on lisätty luetteloon:  
   ![][15]

### <a name="add-the-gallery-to-show-the-collection-items"></a>Lisää valikoima kokoelman kohteiden näyttämistä varten
1. Palaa takaisin suunnittelutyökaluusi.
2. Palaa **Lisää**-välilehdelle ja valitse **Valikoima**, vieritä alaspäin kohtaan **Mukautetut valikoimat** ja valitse **Pysty**:    
   ![][16]  
3. Nimeä valikoima uudelleen nimellä **PriceGallery** ja määritä **[Items](controls/properties-core.md)**-ominaisuudeksi **PriceList**:  
   ![][18]  
4. Siirrä hinnastovalikoima **Tuo tiedot** -ohjausobjektin alle. Valitse valikoiman reunat ja muuta valikoiman kokoa napsauttamalla ja vetämällä niin, että näkyviin tulee kolme neliötä.
5. Valitse valikoimasta ensimmäisen neliö ja lisää kolme selitettä (**Lisää**-välilehti > **Selite**).
6. Muuta selitteiden kokoa ja järjestä ne riviin ensimmäisen neliön yläosaan. Valikoimasi näyttää jotakuinkin seuraavalta:  
   ![][19]
7. Määritä jokaisen selitteen **[Text](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:  
   
   | Selite | Aseta Text-ominaisuudeksi |
   | --- | --- |
   | Label1 |``ThisItem!Name`` |
   | Label2 |``Text(ThisItem!Price, "$#")`` |
   | Label3 |``ThisItem!Maker`` |
   
    Kun teet näin, nimi, hinta ja maker-arvo päivittyvät automaattisesti PriceList-kokoelman selitteisiin.
8. Poista ylimääräinen tila muuttamalla selitteiden ja valikoiman kokoa. Näyttösi näyttää jotakuinkin seuraavalta:  
   ![][17]

### <a name="add-the-quantity-slider-and-update-the-collection"></a>Lisää määrän liukusäädin ja päivitä kokoelma
1. Valitse **Lisää**-valikosta **Ohjausobjektit** ja valitse **Liukusäädin**. Nimeä liukusäädin uudelleen nimellä **OrderQty** ja siirrä se valikoiman alle.
2. Lisää painike, aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi **Lisää** ja siirrä se **OrderQty**-liukusäätimen alle. Sovelluksesi näyttää jotakuinkin seuraavalta:  
   ![][20]
3. Määritä **Lisää**-painikkeen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:  
   
    ```Collect(OrderList, {Name:PriceGallery!Selected!Name, Qty:OrderQty!Value, Cost:OrderQty!Value*LookUp(PriceList, PriceGallery!Selected!Name in Name, Price)});SaveData(OrderList, "orderfile")```  
   
    > [!NOTE]
> Kun valitset tämän painikkeen myöhemmin tämän toimintosarjan aikana, luot ja tallennat kokoelman nimeltä **OrderList**. Kokoelma sisältää valikoimaan lisäämäsi tuotteen nimen, liukusäätimellä valitun määrän ja kokonaiskustannukset, jotka lasketaan kertomalla tuotteen hinta määrällä.
4. Valitse **Näyttö**-välilehti ja määritä **[OnVisible](controls/control-screen.md)**-ominaisuudeksi seuraava lauseke:  
   
    ```If(IsEmpty(PriceList), LoadData(PriceList, "pricefile"));If(IsEmpty(OrderList), LoadData(OrderList, "orderfile"))```

Nyt näet, mitä olet luonut:

1. Avaa **esikatselu**.
2. Valitse valikoimasta tuote, siirrä liukusäädintä haluamasi määrän kohdalle ja valitse sitten **Lisää**-painike.  
   
   > [!IMPORTANT]
   > Kun valitset tuotteen, kyseisen tuotteen valintaa ei osoiteta korostamalla. Emme lisänneet tätä toimintoa, kun loimme valikoiman. Tuotteen napsauttaminen valitsee sen.  
   > 
   > 
3. Toista nämä vaiheet ja lisää muutama tuote. Sulje esikatseluikkuna painamalla **ESC**-näppäintä.
4. Avaa luomasi **OrderList**-kokoelman esikatselu valitsemalla **Tiedosto**-välilehdeltä **Kokoelmat**:  
   ![][21]

> [!TIP]
> Jos haluat poistaa kaikki kohteet tilausluettelosta, lisää painike, määritä sen **[Text](controls/properties-core.md)**-ominaisuudeksi **Tyhjennä** ja määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:  
> ```Clear(OrderList);SaveData(OrderList, "orderfile")```  
> Jos haluat poistaa yhden kohteen kerrallaan, näytä **OrderList**-kokoelma valikoimassa ja määritä kyseisessä valikoimassa olevan selitteen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:  
> ```Remove(OrderList, ThisItem);SaveData(OrderList, "orderfile")```
> 
> 

## <a name="tips-and-tricks"></a>Vihjeitä ja vinkkejä
* Voit tarkastella kaavioitasi tietojen kanssa milloin tahansa valitsemalla Esikatselu-painikkeen (![][7]).
* Voit muuttaa ohjausobjektien kokoa ja siirrellä niitä napsauttamalla ja vetämällä, kun suunnittelet sovellustasi.

## <a name="what-you-learned"></a>Mitä olet oppinut
Tässä aiheessa:

* Loit sovellukseesi kokoelman Collect()-funktion avulla.
* Lisäsit painikeohjausobjektin, jonka valitsemalla voit lisätä uusia kohteita kokoelmaasi.
* Lisäsit kohteita kokoelmaan luetteloruudun avulla.
* Lisäsit liukusäätimen kokoelmassa olevien kohteiden päivittämiseen.

[1]: ./media/create-update-collection/insertmenu-inputtext.png
[2]: ./media/create-update-collection/renametext.png
[3]: ./media/create-update-collection/buttononselect.png
[4]: ./media/create-update-collection/listboxpreview.png
[5]: ./media/create-update-collection/buttontext.png
[6]: ./media/create-update-collection/buttonundertext.png
[7]: ./media/create-update-collection/preview.png
[8]: ./media/create-update-collection/existingcollections.png
[9]: ./media/create-update-collection/renametext-city.png
[10]: ./media/create-update-collection/citystate.png
[11]: ./media/create-update-collection/buttononselectcitystate.png
[12]: ./media/create-update-collection/buttononcitystate.png
[13]: ./media/create-update-collection/existingcollectionscitystate.png
[14]: ./media/create-update-collection/import.png
[15]: ./media/create-update-collection/pricelistcollection.png
[16]: ./media/create-update-collection/portrait.png
[17]: ./media/create-update-collection/resizedgallery.png
[18]: ./media/create-update-collection/galleryitems.png
[19]: ./media/create-update-collection/gallerylabels.png
[20]: ./media/create-update-collection/slider.png
[21]: ./media/create-update-collection/existingcollectionsorderlist.png
[22]: ./media/create-update-collection/listbox.png
