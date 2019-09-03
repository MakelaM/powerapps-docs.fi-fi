---
title: Funktiolla | Microsoft Docs
description: Powerappsin with-funktiolla viite tiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 08/15/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c8d793fcfd2992a781f92d529002e22a34a9df5a
ms.sourcegitcommit: 742a5a21e73a811e9cea353d8275f09c22366afc
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/29/2019
ms.locfileid: "70130329"
ms.PowerAppsDecimalTransform: true
---
# <a name="with-function-in-powerapps"></a>Powerappsissa olevalla funktiolla
Laskee arvot ja suorittaa toimintoja yksittäiselle [tietueelle](../working-with-tables.md#records), mukaan lukien nimettyjen arvojen sisäiset tietueet.

## <a name="description"></a>Kuvaus

**With-** funktio laskee kaavan yksittäiselle tietueelle.  Kaava voi laskea arvon ja suorittaa toimintoja, kuten tietojen muokkaus tai yhteyden käyttäminen.  Laske kaikkien tietueiden taulukon tietueiden kaava käyttämällä [ **forall** -funktiolla](function-forall.md) .

[!INCLUDE [record-scope](../../../includes/record-scope.md)]

Voit parantaa monimutkaisten kaavojen luettavuutta jakamalla sen pienempiin nimettyihin alikaavoihin.  Nämä nimetyt arvot toimivat kuten yksinkertaiset paikalliset muuttujat, jotka rajoittuvat **with-** kohteen vaikutus alueeseen.  Samaa inline-tietueen syntaksia, jota käytetään [ **Updatecontext** -funktiolla](function-updatecontext.md) , voidaan käyttää with-kohteen kanssa.  **With-** toiminnon käyttäminen on suositeltavin kontekstista tai yleisistä muuttujista, koska se on itsenäinen, helppo ymmärtää ja sitä voidaan käyttää missä tahansa määrittävä kaava kontekstista.  

Käytä **with** -toimintoa, kun haluat käyttää niiden tietueiden kenttiä, jotka on palautettu funktioilla, kuten [**patch**](function-patch.md) tai [**Match**](function-ismatch.md).  Sisältää näiden funktioiden arvon, joka on tarpeeksi pitkä, jotta sitä voi käyttää lisä laskelmissa tai-toiminnoissa.  

Jos *tietue* **-** argumentin arvona on virhe, funktio palauttaa tämän virheen, eikä *kaavaa* lasketa.

## <a name="syntax"></a>Syntaksi
**Kanssa** ( *Tietue*, *kaava* )

* *Tietue* – pakollinen. Tietue, jolle suoritetaan.  Käytä nimet-arvoissa inline-syntaksia`{ name1: value1; name2: value2; ... }`
* *Formula* – pakollinen.  *Tietueen*arviointi kaava.  Kaava voi viitata mihin tahansa *tietue* kenttiin suoraan tietue alueena.

## <a name="examples"></a>Esimerkkejä

### <a name="simple-named-values"></a>Yksinkertaiset nimetyt arvot

```powerapps-comma
With( { radius: 10; 
        height: 15 };
    Pi() * (radius*radius) * height
)
// Result: 4712,38898038 (as shown in a label control)
```

Tässä esimerkissä käytetään nimettyjen arvojen tietuetta laskemaan sylin terin tilavuus.  **Kun-** arvoa käytetään kaikkien syöte arvojen sieppaamiseen, niiden erottaminen itse laskennasta on helppoa.  

### <a name="nested-with"></a>Sisäkkäin

![Korko Laskin käyttäen funktiolla](media/function-with/interest-calculator.gif)

```powerapps-comma
With( { AnnualRate: RateSlider/8/100;        // slider moves in 1/8th increments and convert to decimal
        Amount: AmountSlider*10000;          // slider moves by 10;000 increment
        Years: YearsSlider;                  // slider moves in single year increments; no adjustment required
        AnnualPayments: 12 };                // number of payments per year
      With( { r: AnnualRate/AnnualPayments;  // interest rate
              P: Amount;                     // loan amount
              n: Years*AnnualPayments };     // number of payments
            r*P / (1 - (1+r)^-n)             // standard interest calculation
      )
)  
```

Tämä esimerkki **sisältää** funktioita, jotka luovat kaksivaiheisen laskennan [kuukausittaisiin kiinnitys maksuihin](https://en.wikipedia.org/wiki/Mortgage_calculator#Monthly_payment_formula).  Niin kauan kuin risti riitaa ei ole, kaikki ulkoiset **ja** nimetyt arvot ovat käytettävissä sisempi **-** kohteen sisällä.

Koska liuku säädin-ohjaus objekti voi liikkua vain 1-välein, liuku säätimet jaetaan tai kerrotaan, jotta mukautettu lisäys voidaan luoda tehokkaasti.  Koron osalta Rateslider-kohteen Max -ominaisuudeksi on määritetty **48**, jaettuna 8 1/8 prosentti yksiköllä, ja se jaetaan luvulla 100, jotta prosentti osuus voidaan muuntaa prosentti luvuksi, joka kattaa alueen 0,125% – 6%.  Kun kyseessä on lainan määrä, **Amountslider** -ominaisuuden enimmäisominaisuudeksi on määritetty **60** ja kerrottuna 10 000, joka kattaa alueen 10 000 – 600 000.

**With** lasketaan automaattisesti uudelleen liuku säätiminä ja uusi lainan maksu näytetään.  Muuttujia ei käytetä, joten liuku säätimien **onChange** -ominaisuutta ei tarvitse käyttää.

Tässä on tarkat ohjeet tämän sovelluksen luomiseen:
1. Luo uusi sovellus.
2. Lisää [ **liuku** säätimen ohjaus objekti](../controls/control-slider.md) ja nimeäse.  Valitse sen **Max** -ominaisuudeksi 48.
3. Lisää liuku säätimen vasemmalla puolella oleva [ **Selite** -ohjaus](../controls/control-text-box.md) objekti.  Valitse sen **Text** -ominaisuudeksi **"korko:"** .
3. Lisää liuku säädin-ohjaus objektin oikealla puolella oleva **Selite** -ohjaus objekti.  Valitse sen **Text** -ominaisuudeksi kaavan **rateslider/8&nbsp;& "%"** .
3. Lisää toinen **liuku** säädin ja nimeä se **liuku säätimellä**.  Valitse sen **Max** -ominaisuudeksi 60.
3. Lisää tämän liuku säätimen vasemmalla puolella oleva **Selite** -ohjaus objekti.  Määrittämällä sen **Text** -ominaisuudeksi **lainan määrä:** . 
3. Lisää **Selite** -ohjaus objekti tämän liuku säätimen oikealla puolella.  Valitse sen **Text** -ominaisuudeksi kaava **amountslider/8 * 10000**.
4. Lisää toinen **liuku** säädin ja nimeä se **yearslider**.  Valitse sen **Max** -ominaisuudeksi 40.
3. Lisää tämän liuku säätimen vasemmalla puolella oleva **Selite** -ohjaus objekti.  Valitse sen **Text** -ominaisuudeksi **"vuosien määrä:"** . 
3. Lisää **Selite** -ohjaus objekti tämän liuku säätimen oikealla puolella.  Sen **Text** -ominaisuudeksi on määritetty kaava **Yearsslider**.
5. Lisää **Selite** -ohjaus objekti ja määrittää sen **Text** -ominaisuudeksi kaava, joka näkyy yllä.
3. Lisää **Selite** -ohjaus objekti viimeisen otsikko-ohjaus objektin vasemmalle puolelle.  Valitse sen **Text** -ominaisuudeksi **toistuva kuukausi maksu:** .  

### <a name="primary-key-returned-from-patch"></a>Korjaus tiedostosta palautettu perusavain

```powerapps-comma
With( Patch( Orders; Defaults( Orders ); { OrderStatus: "New" } );
      ForAll( NewOrderDetails; 
              Patch( OrderDetails; Defaults( OrderDetails ); 
                     { Order: OrderID;          // from With's first argument; primary key of Patch result
                       Quantity: Quantity;      // from ForAll's NewOrderDetails table
                       ProductID: ProductID }   // from ForAll's NewOrderDetails table
              )
      )
)
```

Tämä esimerkki lisää tietueen SQL Server **Order** -taulukkoon.  Sen jälkeen se käyttää tila uksen palautettua perusavainta, jonka **patch** -funktio palautti OrderID-kentässä, luodaksesi liittyviä tietueita orderDetails -taulukkoon.  

### <a name="extracted-values-with-a-regular-expression"></a>Poimitut arvot Säännöllisellä lausekkeella

```powerapps-comma
With( 
    Match( "PT2H1M39S"; "PT(?:<hours>\d+)H)?(?:(?<minutes>\d+)M)?(?:(?<seconds>\d+)S)?" );
    Time( Value( hours ); Value( minutes ); Value( seconds ) )
)
// Result: 2:01 AM (as shown in a label control; use the Text function to see the seconds)
```

Tämä esimerkki poimii tunnit, minuutit ja sekunnit ISO 8601-kesto arvosta ja käyttää sitten näitä alivastaavu uksia päivä määrä-ja aika-arvon luomiseen. 

Huomioi, että vaikka alivastaavuudet sisältävät numeroita, ne ovat yhä teksti merkki jonossa.  Käytä [**Value**](function-value.md) -funktiolla lukua ennen matemaattisten toimintojen suorittamista.  

