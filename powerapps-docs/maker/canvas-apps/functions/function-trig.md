---
title: Acos-, Acot-, Asin-, Atan-, Atan2-, Cos-, Cot-, Degrees-, Pi-, Radians-, Sin- ja Tan-funktiot | Microsoft Docs
description: Tietoa PowerAppsin Abs- ja Sqrt-funktiosta, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 09/13/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6eab89f436bc00ae0c447494607b5c1bb0cec875
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61519892"
---
# <a name="acos-acot-asin-atan-atan2-cos-cot-degrees-pi-radians-sin-and-tan-functions-in-powerapps"></a>Acos-, Acot-, Asin-, Atan-, Atan2-, Cos-, Cot-, Degrees-, Pi-, Radians-, Sin- ja Tan-funktiot PowerAppsissa
Laskee trigonometriset arvot.

## <a name="description"></a>Kuvaus
### <a name="primary-functions"></a>Pääfunktiot
**Cos**-funktio palauttaa kosinin argumentista, joka on kulman arvo radiaaneina.

**Cot**-funktio palauttaa kotangentin argumentista, joka on kulman arvo radiaaneina.

**Sin**-funktio palauttaa sinin argumentista, joka on kulman arvo radiaaneina.

**Tan**-funktio palauttaa tangentin argumentista, joka on kulman arvo radiaaneina.

### <a name="inverse-functions"></a>Käänteiset funktiot
**Acos**-funktio palauttaa argumentista arkuskosinin (käänteisen kosinin). Arkuskosini on kulma, jonka kosini on argumentti.  Palautettu kulma annetaan radiaaneina alueella 0 (nolla) ja &pi;.

**Acot**-funktio palauttaa argumentista arkuskotangentin (käänteisen kotangentin) pääarvon.  Palautettu kulma annetaan radiaaneina alueella 0 (nolla) ja &pi;.

**Asin**-funktio palauttaa argumentista arkussinin (käänteisen sinin). Arkussini on kulma, jonka sini on argumentti.  Palautettu kulma annetaan radiaaneina alueella –&pi;/2 ja &pi; /2.

**Atan**-funktio palauttaa argumentista arkustangentin (käänteisen tangentin). Arkustangentti on kulma, jonka tangentti on argumentti. Palautettu kulma annetaan radiaaneina alueella –&pi;/2 ja &pi; /2.

**Atan2**-funktio palauttaa määritettyjen *x*- ja *y* -koordinaattien arkustangentin (käänteisen tangentin) argumentteina. Arkustangentti on kulma, joka muodostuu *x*-akselin ja sen suoran väliin, joka sisältää origon (0, 0) ja koordinaattipisteen (*x*, *y*). Kulma annetaan radiaaneina alueella –&pi; ja &pi;, pois lukien –&pi;.  Positiivinen tulos edustaa kulmaa, joka aukeaa vastapäivään suhteessa *x*-akseliin; negatiivinen tulos edustaa kulmaa, joka aukeaa myötäpäivään.  **Atan2(&nbsp;*a*,&nbsp;*b*&nbsp;)** on yhtä suuri kuin **Atan(&nbsp;*b*/*a*&nbsp;)**, paitsi että**Atan2**-funktiolla ***a*** voi olla 0 (nolla).

### <a name="helper-functions"></a>Apufunktiot
**Degrees**-funktio muuntaa radiaanit asteiksi.  &pi; radiaania on 180 astetta.

**Pi**-funktio palauttaa transsendenttiluvun &pi;, joka alkaa 3.141592...

**Radians**-funktio muuntaa asteet radiaaneiksi.  

### <a name="notes"></a>Huomautuksia
Jos välität näihin funktioihin yksittäisen numeron, palautusarvo on yksittäinen tulos.  Jos välität yksisarakkeisen [taulukon](../working-with-tables.md), joka sisältää numeroita, palautusarvo on yksisarakkeinen tulostaulukko, jossa on yksi tulos jokaiselle argumentin taulukossa olevalle tietueelle. Jos käytät monisarakkeista taulukkoa, voit muokata sen yksisarakkeiseksi taulukoksi kohdan [Taulukoiden käyttö](../working-with-tables.md) mukaisesti.  

Jos argumentti tuottaisi määrittämättömän arvon, tulos on *tyhjä*.  Näin voi käydä esimerkiksi, jos käänteisiä funktioita käytetään argumenteilla, jotka ovat arvojen ulkopuolella.

## <a name="syntax"></a>Syntaksi
### <a name="primary-functions"></a>Pääfunktiot
**Cos**( *Radians* )<br>**Cot**( *Radians* )<br>**Sin**( *Radians* )<br>**Tan**( *Radians* )

* *Radians* – Pakollinen. Käsittelyn kohteena oleva kulma.

**Cos**( *SingleColumnTable* )<br>**Cot**( *SingleColumnTable* )<br>**Sin**( *SingleColumnTable* )<br>**Tan**( *SingleColumnTable* )

* *SingleColumnTable* – Pakollinen. Yksisarakkeinen taulukko, joka sisältää käsittelyn kohteena olevat kulmat.

### <a name="inverse-functions"></a>Käänteiset funktiot
**Acos**( *Number* )<br>**Acot**( *Number* )<br>**Asin**( *Number* )<br>**Atan**( *Number* )

* *Number* – pakollinen. Käsittelyn kohteena oleva numero.

**Acos**( *SingleColumnTable* )<br>**Acot**( *SingleColumnTable* )<br>**Asin**( *SingleColumnTable* )<br>**Atan**( *SingleColumnTable* )

* *SingleColumnTable* – Pakollinen. Yksisarakkeinen taulukko, joka sisältää käsittelyn kohteena olevat numerot.

**Atan2**( *X*, *Y* )

* *X* – Pakollinen.  *X*-akselin koordinaatti.
* *Y* – Pakollinen.  *Y*-akselin koordinaatti.

### <a name="helper-functions"></a>Apufunktiot
**Degrees**( *Radians* )

* *Radians* – Pakollinen.  Radiaaneina ilmaistu kulma, joka muunnetaan asteiksi.

**Pi**()

**Radians**( *Degrees* )

* *Degrees* – Pakollinen.  Asteina ilmaistu kulma, joka muunnetaan radiaaneiksi.

## <a name="examples"></a>Esimerkkejä
### <a name="single-number"></a>Yksittäinen luku

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Cos(&nbsp;1.047197&nbsp;)** |Palauttaa kosinin arvolle 1.047197 radiaania eli 60 astetta. |0.5 |
| **Cot(&nbsp;Pi()/4&nbsp;)** |Palauttaa kotangentin arvolle 0.785398...radiaania eli 45 astetta. |1 |
| **Sin(&nbsp;Pi()/2&nbsp;)** |Palauttaa sinin arvolle 1.570796... radiaania eli 90 astetta. |1 |
| **Tan(&nbsp;Radians(60)&nbsp;)** |Palauttaa tangentin arvolle 1.047197... radiaania eli 60 astetta. |1.732050... |
| **Acos(&nbsp;0.5&nbsp;)** |Palauttaa arkuskosinin arvolle 0.5 radiaania. |1.047197... |
| **Acot(&nbsp;1&nbsp;)** |Palauttaa arkustangentin arvolle 1 radiaani. |0.785398... |
| **Asin(&nbsp;1&nbsp;)** |Palauttaa arkustangentin arvolle 1 radiaani. |1.570796... |
| **Atan(&nbsp;1.732050&nbsp;)** |Palauttaa arkustangentin arvolle 1.732050 radiaania. |1.047197... |
| **Atan2 (&nbsp;5,&nbsp;3&nbsp;)** |Palauttaa arkustangentin kulmalle, joka muodostuu *x*-akselin ja suoran, joka sisältää origon (0,0) ja koordinaatin (5,3), välille, mikä on noin 31 astetta. |0.540419... |
| **Atan2(&nbsp;4,&nbsp;4&nbsp;)** |Palauttaa arkustangentin kulmalle, joka muodostuu *x*-akselin ja suoran, joka sisältää origon (0,0) ja koordinaatin (4,4), välille, mikä on täsmälleen &pi;/4 radiaania eli 45 astetta. |0.785398... |
| **Degrees(&nbsp;1.047197&nbsp;)** |Palauttaa astemääräisen arvon, joka vastaa 1.047197 radiaania. |60 |
| **Pi()** |Palauttaa transsendenttiluvun&pi;. |3.141592... |
| **Radians(&nbsp;15&nbsp;)** |Palauttaa radiaaneina arvon, joka vastaa 15 astetta. |0.261799... |

### <a name="single-column-table"></a>Yksisarakkeinen taulukko
Tämän osion esimerkeissä käytetään [tietolähdettä](../working-with-data-sources.md) nimeltä **ValueTable**, joka sisältää seuraavat tiedot.  Taulukon viimeinen tietue on &pi;/2 radiaania tai 90 astetta.

![](media/function-trig/values.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Cos (&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen kosinin. |<style> img { max-width: none } </style> ![](media/function-trig/values-cos.png) |
| **Cot(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen kotangentin. |<style> img { max-width: none } </style> ![](media/function-trig/values-cot.png) |
| **Sin(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen sinin. |<style> img { max-width: none } </style> ![](media/function-trig/values-sin.png) |
| **Tan(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen tangentin. |<style> img { max-width: none } </style> ![](media/function-trig/values-tan.png) |
| **Acos(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen arkussinin. |<style> img { max-width: none } </style> ![](media/function-trig/values-acos.png) |
| **Acot(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen arkustangentin. |<style> img { max-width: none } </style> ![](media/function-trig/values-acot.png) |
| **Asin(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen arkussinin. |<style> img { max-width: none } </style> ![](media/function-trig/values-asin.png) |
| **Atan(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon lukujen arkustangentin. |<style> img { max-width: none } </style> ![](media/function-trig/values-atan.png) |
| **Degrees(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon luvut astemääräisinä olettaen, että ne ovat radiaaneina ilmaistuja kulmia. |<style> img { max-width: none } </style> ![](media/function-trig/values-degrees.png) |
| **Radians(&nbsp;ValueTable&nbsp;)** |Palauttaa taulukon luvut radiaaneina olettaen, että ne ovat asteina ilmaistuja kulmia. |<style> img { max-width: none } </style> ![](media/function-trig/values-radians.png) |

