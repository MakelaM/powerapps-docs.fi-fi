---
title: Patch-funktio | Microsoft Docs
description: PowerAppsin Patch-funktion viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/21/2015
ms.author: gregli
ms.openlocfilehash: d0b2ff351f7026967359f1b4d386a71d7ed5441f
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="patch-function-in-powerapps"></a>PowerAppsin Patch-funktio
Muokkaa [tietolähteen](../working-with-data-sources.md) [tietuetta](../working-with-tables.md#records) tai luo sellaisen tai yhdistää tietueita tietolähteen ulkopuolella.

Käytä **Patch**-funktiota tietueiden muokkaamiseksi monimutkaisissa tilanteissa, kun esimerkiksi suoritat päivityksiä, jotka eivät vaadi käyttäjän toimia tai käytät lomakkeita, jotka ulottuvat usealle näytölle.

Vähemmän monimutkaisissa tilanteissa voit käyttää **Muokkaa lomaketta** -ohjausobjektia tietolähteen tietueiden helpompaa päivittämistä varten. Kun lisäät **Muokkaa lomaketta** -ohjausobjektin, tarjoat käyttäjille täytettävän lomakkeen, jonka muutokset tallennetaan tietolähteeseen. Lisätietoja on kohdassa [Tutustu tietolomakkeisiin](../working-with-forms.md).

## <a name="overview"></a>Yleiskatsaus
Käytä **Patch**-funktiota muokkaamaan yhtä tai useampaa tietolähteen tietuetta.  Tiettyjen [kenttien](../working-with-tables.md#elements-of-a-table) arvoja muokataan vaikuttamatta muihin ominaisuuksiin. Esimerkiksi tämä kaava muuttaa Contoso-nimisen asiakkaan puhelinnumeroa:

**Patch( Customers, First( Filter( Customers, Name = "Contoso" ) ), { Phone: "1-212-555-1234" } )**

Käytä **Patch**-funktiota **[Defaults](function-defaults.md)**-funktion kanssa tietueiden luomiseen. Käytä tätä toimintaa rakentamaan [yksi näyttö](../working-with-data-sources.md) sekä tietueiden luomiseen että muokkaamiseen. Esimerkiksi tämä kaava luo tietueen asiakkaalle nimeltä Contoso:

**Patch( Customers, Defaults( Customer ), { Name: "Contoso" } )**

Vaikka et työskentelisikään tietolähteen kanssa, voit käyttää **Patch**-funktiota kahden tai useamman tietueen yhdistämiseen. Esimerkiksi tämä kaava yhdistää kaksi tietuetta yhdeksi tietueeksi, joka sisältää sekä Contoson puhelinnumeron että sijainnin:

**Patch( { Name: "Contoso", Phone: "1-212-555-1234" }, { Name: "Contoso", Location: "Midtown"  } )**

## <a name="description"></a>Kuvaus
### <a name="modify-or-create-a-record-in-a-data-source"></a>Tietueen luominen tai muokkaaminen tietolähteessä
Tämän funktion käyttämiseksi tietolähteen kanssa määritä tietolähde ja sitten määritä perustietue:

* Tietueen muokkaamiseksi perustietueen täytyy olla peräisin tietolähteestä.  Perustietue saattaa olla peräisin valikoiman **[Items](../controls/properties-core.md)**-ominaisuudesta, se saatettiin sijoittaa [kontekstimuuttujan](../working-with-variables.md#create-a-context-variable) kautta tai se voi olla peräisin jostain muualta. Tietue pitää kuitenkin pystyä jäljittämään takaisin tietolähteeseen.  Tämä on tärkeää, sillä tietue sisältää lisätietoja, jotka auttavat löytämään tietueen uudelleen muokkausta varten.  
* Luo tietue käyttämällä **[Defaults](function-defaults.md)**-funktiota perustietueen luomiseksi oletusarvoilla.  

Määritä sitten yksi tai useampi muutostietue, jotka sisältävät uusia ominaisuusarvoja, jotka korvaavat perustietueen arvot. Muutostietueet käsitellään järjestyksessä argumenttiluettelon alusta loppuun niin, että myöhemmät ominaisuusarvot korvaavat aiemmat.

**Patch**-funktion palautusarvo on tietue, jota muokkasit tai jonka loit.  Jos loit tietueen, palautusarvo voi sisältää ominaisuuksia, joita tietolähde loi automaattisesti.

Kun päivität tietolähdettä, voi esiintyä yksi tai useampi ongelma. Käytä **[Errors](function-errors.md)**-funktiota ongelmien tunnistamiseen ja tarkasteluun, kuten kuvaillaan aiheessa [Tietolähteiden kanssa työskentely](../working-with-data-sources.md).

Liittyviin funktioihin kuuluvat **[Update](function-update-updateif.md)**-funktio, jota voidaan käyttää kokonaisen tietueen korvaamiseen, sekä **[Collect](function-clear-collect-clearcollect.md)**-funktio, jota voidaan käyttää tietueen luomiseen.  Voit käyttää **[UpdateIf](function-update-updateif.md)**-funktiota muokkaamaan useiden tietueiden tiettyjä ominaisuuksia ehdon perusteella.

### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Tietueiden joukon luominen tai muokkaaminen tietolähteessä
**Patch**-funktiota voidaan myös käyttää useiden tietueiden luomiseen tai muokkaamiseen yhdellä kutsulla.

Yhden perustietueen välittämisen sijaan toisessa argumentissa voidaan antaa perustietueiden taulukko.  Muutostietueet annetaan myös taulukkona, jonka tietueet vastaavat jokainen yhtä perustietuetta.  Muutostaulukon tietueiden määrän täytyy vastata perustaulukon tietueiden määrää.

Kun **Patch**-funktiota käytetään tällä tavalla, palautusarvo on myös taulukko, jonka jokainen tietue vastaa yhtä perus- ja muutostietuetta.

### <a name="merge-records-outside-of-a-data-source"></a>Tietueiden yhdistäminen tietolähteen ulkopuolella
Määritä kaksi tai useampaa tietuetta, jotka haluat yhdistää. Tietueet käsitellään järjestyksessä argumenttiluettelon alusta loppuun niin, että myöhemmät ominaisuusarvot korvaavat aiemmat.

**Patch** palauttaa yhdistetyn tietueen eikä muokkaa sen argumentteja tai minkään tietolähteen tietueita.

## <a name="syntax"></a>Syntaksi
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Tietueen luominen tai muokkaaminen tietolähteessä
**Patch**( *TietoLähde*, *Perustietue*, *Muutostietue1* [, *Muutostietue2*, … ])

* *Tietolähde* – Pakollinen. Tietolähde, joka sisältää tietueen, jota haluat muokata tai tulee sisältämään tietueen, jonka haluat luoda.
* *Perustietue* – Pakollinen. Muokattava tai luotava tietue.  Jos tietue on peräisin tietolähteestä, tietue etsitään ja sitä muokataan. Jos **[Defaults](function-defaults.md)**-funktion tulosta käytetään, tietue luodaan.
* *Muutostietue(et)* – Pakollinen.  Yksi tai useampi tietue, jotka sisältävät *Perustietueen* muokattavat ominaisuudet.  Muutostietueet käsitellään järjestyksessä argumenttiluettelon alusta loppuun niin, että myöhemmät ominaisuusarvot korvaavat aiemmat.

#### <a name="modify-or-create-a-set-of-records-in-a-data-source"></a>Tietueiden joukon luominen tai muokkaaminen tietolähteessä
**Patch**( *Tietolähde*, *Perustietuetaulukko*, *Muutostietuetaulukko1*, [, *Muutostietuetaulukko2*, … ] )

* *Tietolähde* – Pakollinen. Tietolähde, joka sisältää tietueet, joita haluat muokata tai tulee sisältämään tietueet, jotka haluat luoda.
* *Perustietuetaulukko* – Pakollinen. Muokattavien tai luotavien tietueiden taulukko.  Jos tietue on peräisin tietolähteestä, tietue etsitään ja sitä muokataan. Jos **[Defaults](function-defaults.md)**-funktion tulosta käytetään, tietue luodaan.
* *Muutostietuetaulukko* – Pakollinen.  Yksi tai useampi tietueiden taulukko, jotka sisältävät *Perustietuetaulukon* tietueiden muokattavat ominaisuudet.  Muutostietueet käsitellään järjestyksessä argumenttiluettelon alusta loppuun niin, että myöhemmät ominaisuusarvot korvaavat aiemmat.

#### <a name="merge-records"></a>Tietueiden yhdistäminen
**Patch**( *Tietue1*, *Tietue2* [, …] )

* *Tietue(et)* – Pakollinen.  Vähintään kaksi tietuetta, jotka haluat yhdistää. Tietueet käsitellään järjestyksessä argumenttiluettelon alusta loppuun niin, että myöhemmät ominaisuusarvot korvaavat aiemmat.

## <a name="examples"></a>Esimerkkejä
#### <a name="modify-or-create-a-record-in-a-data-source"></a>Tietueen luominen tai muokkaaminen (tietolähteessä)
Näissä esimerkeissä muokataan tai luodaan tietue tietolähteessä nimeltä **IceCream**, joka sisältää tämän [taulukon](../working-with-tables.md) tiedot, ja luodaan automaattisesti arvot **ID**[-sarakkeelle](../working-with-tables.md#columns):

![](media/function-patch/icecream.png)

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Patch(&nbsp;IceCream,<br>First( Filter( IceCream, Flavor = "Chocolate" ) ), {&nbsp;Quantity:&nbsp;400&nbsp;} )** |Muokkaa **IceCream**-tietolähteen tietuetta:<ul><li> Muokattavan tietueen **ID**-sarake sisältää arvon **1**. (**Chocolate**-tietueella on kyseinen ID.)</li><li>**Quantity**-sarakkeen arvoksi muuttuu **400**. |{&nbsp;ID:&nbsp;1, Flavor:&nbsp;"Chocolate", Quantity:&nbsp;400 }<br><br>**IceCream**-tietolähteen **Chocolate**-tietuetta on muokattu. |
| **Patch( IceCream, Defaults(&nbsp;IceCream ), {&nbsp;Flavor:&nbsp;"Strawberry"&nbsp;}&nbsp;)** |Luo **IceCream**-tietolähteeseen tietueen:<ul><li>**ID**-sarake sisältää arvon **3**, jonka tietolähde luo automaattisesti.</li><li>**Quantity**-sarake sisältää arvon **0**, joka on kyseisen sarakkeen oletusarvo **IceCream**-tietolähteessä, kuten **[Defaults](function-defaults.md)**-funktio määrittää.<li>**Flavor**-sarake sisältää arvon **Strawberry**.</li> |{ ID:&nbsp;3, Flavor:&nbsp;"Strawberry", Quantity:&nbsp;0&nbsp;}<br><br>**IceCream**-tietolähteen **Strawberry**-tietue on luotu. |

Kun edelliset kaavat on arvioitu, tietolähteessä on lopulta nämä arvot:

![](media/function-patch/icecream-after.png)

#### <a name="merge-records-outside-of-a-data-source"></a>Tietueiden yhdistäminen (tietolähteen ulkopuolella)
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Patch(&nbsp;{&nbsp;Name:&nbsp;"James",&nbsp;Score:&nbsp;90&nbsp;}, {&nbsp;Name:&nbsp;"Jim",&nbsp;Passed:&nbsp;true&nbsp;} )** |Yhdistää kaksi tietuetta tietolähteen ulkopuolella:<br><ul><li>Tietueiden **Name**-sarakkeen arvot eivät täsmää. Tulos sisältää arvon (**Jim**) tietueessa, joka on lähempänä argumenttiluettelon loppua arvon (**James**) sijaan, joka on lähempänä alkua.</li><li>Ensimmäinen tietue sisältää sarakkeen (**Score**), joka ei ole olemassa toisessa tietueessa. Tulos sisältää kyseisen sarakkeen arvollaan (**90**).</li><li>Toinen sarake sisältää sarakkeen (**Passed**), joka ei ole olemassa ensimmäisessä tietueessa. Tulos sisältää kyseisen sarakkeen arvollaan (**true**). |{&nbsp;Name:&nbsp;"Jim", Score:&nbsp;90, Passed:&nbsp;true&nbsp;} |

