---
title: Northwind Traders-kangas sovelluksen Yleiskatsaus | Microsoft Docs
description: ''
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 48966659ca12ada12448543492731fff8431fbde
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995835"
---
# <a name="overview-of-the-canvas-app-for-northwind-traders"></a>Northwind Traders-kangas sovelluksen Yleiskatsaus

Lue tietoja kangas sovelluksesta, jonka avulla voit hallita relaatio tietoja [ympäristössäsi asennetussa](northwind-install.md)Northwind Traders-tieto kannassa. Tämän jälkeen voit luoda tämän sovelluksen alusta alkaen noudattamalla vaiheittaisia ohjeita ja hankkimalla näin käytännön kokemusta relaatio tietojen käyttämisestä.

Tutustu tähän aiheeseen:

- Miten sovelluksen käyttäjä näkee ja hallitsee relaatio tietoja sovelluksessa.
- Minkä tyyppiset tiedot ohjaavat sovellusta.
- Miten näiden tieto tyyppien väliset yhteydet luotiin.

Yhdessä näytössä sovelluksen käyttäjä voi näyttää, päivittää, luoda ja poistaa tila uksia.

> [!div class="mx-imgBorder"]
> ![Viimeistele kangas sovellus @ no__t-1

## <a name="explore-the-user-interface"></a>Tutustu käyttö liittymään

### <a name="order-gallery"></a>Tilaus valikoima

Sovelluksen vasemmassa reunassa olevassa valikoimassa näytetään luettelo tila uksista, mukaan lukien tila uksen numero, tila, asiakkaan nimi ja tila uksen kokonaiskustannukset. Käyttäjä voi selata luetteloa löytääksesi tila uksen ja näyttää sen jälkeen lisä tietoja valitsemalla tila uksen nuolen. Lisätietoja: [Luo tilaus valikoima](northwind-orders-canvas-part1.md).

### <a name="summary-form"></a>Yhteenveto lomake

Oikeassa yläkulmassa oleva lomake tekee yhteenvedon järjestyksestä, jonka käyttäjä valitsi järjestys valikoimassa. Yhteenvedossa on paljon samoja tietoja kuin valikoimassa, mutta yhteenvedossa näytetään myös päivä määrät, jolloin tilaus luotiin ja maksetaan, sekä tila uksen hallinnoidun työn tekijän nimi ja kuva. Käyttäjä voi muuttaa lomakkeen tietoja, tallentaa muutokset, peruuttaa ne tai poistaa tila uksen valitsemalla kuvakkeen otsikko rivin oikean reunan läheltä. Lisätietoja: [Luo Yhteenveto lomake](northwind-orders-canvas-part2.md).

### <a name="detail-gallery"></a>Tieto valikoima

Oikeassa alakulmassa on toinen valikoima, joka sisältää tietoja siitä, mitä tuotteita valittu järjestys sisältää ja mitä määriä. Kutakin tämän valikoiman kohdetta kutsutaan tila uksen yksityiseksi. Sovelluksen käyttäjä voi lisätä ja poistaa minkä tahansa kyseisen valikoiman kohteen käyttämällä ohjaus objektien käyttö-ja hallinta-kohteita. Lisätietoja: [Luo tieto valikoima](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Näytön alueiden määritelmät @ no__t-1

## <a name="explore-the-data-sources"></a>Tutustu tieto lähteisiin

Jos haluat luoda tämän sovelluksen, Näytä tiedot viidestä entiteetistä ja asetus joukosta. Itse asiassa suurin osa tämän sovelluksen alueista näyttää tietoja useista entiteeteistä. Esimerkiksi tilaus valikoima sisältää nämä tiedot:

- Järjestys numero on **tila ukset** -entiteetin kenttä.
- Tila on toinen kenttä **tila ukset** -entiteetissä, joka on vaihto ehto **tilausten tila** -asetus joukosta.
- Asiakkaan nimi on kenttä **Customers** -entiteetissä.
- Kokonaiskustannukset lasketaan **Order Details** -entiteetin tietojen perusteella.

Yhteenvedossa on joitakin samoja tietoja kuin tilausten luettelossa, mutta se sisältää myös tila uksen hallinnoidun työn tekijän nimen ja kuvan. Nämä tiedot vedetään **työn tekijät** -entiteetin kentistä. Tieto valikoima sisältää **tila uksen tiedot** -entiteetin tietueet, ja kukin kyseisten tietojen tuote on tietue **Order Products** -entiteetissä.

## <a name="explore-the-relationships"></a>Tutki suhteita

Voit näyttää tietoja eri lähteistä (esimerkiksi entiteeteistä) samassa valikoimassa tai lomakkeessa, koska näillä entiteeteillä on suhteita, jotka luotiin tieto kannassa.

### <a name="many-to-one-relationships"></a>Monta yhteen-yhteydet

Esimerkiksi tietoja asiakkaasta ja työn tekijästä kullekin tilaukselle on **Asiakkaat** -ja **työn tekijät** -entiteeteissä. Näin ollen **tila ukset** -entiteetillä on monta yhteen-suhteita näihin entiteetteihin, koska on olemassa useita tila uksia, joista kutakin voi tehdä vain yksi asiakas ja joita hallitsee vain yksi työn tekijä.

Jokaisella tila uksessa on myös yksi tai useampi Line-kohde, joka edustaa tila uksen sisältämiä tuotteita ja niiden määriä. Jokainen rivin kohde on **tila uksen tiedot** -entiteetin tietue, joka noutaa tietoja kustakin tuotteesta **Order Products** -entiteetistä. Jokainen yksityiskohta tunnistaa vain yhden tuotteen, mutta jokainen tuote voi näkyä useissa tiedoissa. Näin ollen **Order Details** -entiteetillä on monta yhteen-suhde **Order Products** -entiteettiin.

### <a name="one-to-many-relationships"></a>Yksi moneen-suhde

Jokainen järjestys voi sisältää useita Line-kohteita, mutta kukin rivin osa koskee vain yhtä tilausta. Tästä syystä **tila ukset** -entiteetillä on yksi-moneen-suhde **Order Details** -entiteettiin.

### <a name="dot-notation-for-relationships"></a>Yhteyksien piste merkintä 

Jos haluat näyttää tiedot entiteettien välisen suhteen perusteella, voit käyttää dot-ominaisuuden valitsinta, kun haluat kävellä suhteessa entiteetistä toiseen.  Esimerkiksi jokainen **tila ukset** -entiteetin tietue noutaa tietoja **Customers** -entiteetistä niin, että tilaus valikoima voi näyttää asiakkaiden nimet. Tämän valikoiman avulla voit määrittää tämän toiminnon asettamalla selitteen **Text** -ominaisuudeksi tämän lausekkeen:<br>`ThisItem.Customer.Company`

**Thisitem** määrittää **tila ukset** -entiteetin tietueen ja noutaa tila uksen tehneelle asiakkaalle tietoja **Customers** -entiteetistä. Tässä tapa uksessa lauseke määrittää, että asiakkaan yrityksen nimi tulee näkyviin. Kyseisen asiakkaan koko tietue on kuitenkin vedetty, joten voit yhtä helposti näyttää esimerkiksi kyseisen asiakkaan Sähkö posti osoitteen sen sijaan.

Toisena esimerkkinä siitä, miten voit kävellä entiteetistä toiseen, voit määrittää, että valikoiman tulee näyttää tietueita yhdessä entiteetissä sellaisen tietueen perusteella, jonka käyttäjä on valinnut toisessa valikoimassa ja joka on toisessa entiteetissä. Jos haluat näyttää tila uksen tiedot, sinun on asetettava yksityiskohta valikoiman **Items** -ominaisuudeksi tämä lauseke:<br>`Gallery1.Selected.'Order Details'`

Tässä tapa uksessa **Gallery1. Selected** määrittää tietueen **tila ukset** -entiteetissä samalla tavalla kuin **thisitem** edellisessä esimerkissä. Tämä lauseke ei kuitenkaan Vedä vain yhtä tietuetta kuin edellinen lauseke. Sen sijaan se poimii koko tietue taulukon, joka näyttää kunkin tuotteen nimen ja yksikkökohtaisen hinnan (mikä näkyy **Order Products** -entiteetissä) ja määrän ( **tila uksen tiedot** -entiteetissä).

## <a name="do-it-yourself"></a>Tee se itse

Voit seurata vaiheittaisia ohjeita Northwind orders Canvas-sovelluksen luomi seksi.  Ohjeet on jaettu kolmeen osaan:

1. [Luo tilaus valikoima](northwind-orders-canvas-part1.md).
1. [Luo Yhteenveto lomake](northwind-orders-canvas-part2.md).
1. [Luo tieto valikoima](northwind-orders-canvas-part3.md).

Jos haluat siirtyä eteenpäin, liuos sisältää aloitus kohdan sovelluksen kullekin osalle.  Etsi sovellus listasta **Northwind-tila ukset (piirto alusta) – Aloita osa 1** ja niin edelleen.

> [!div class="nextstepaction"]
> [Jatka luomalla tilaus valikoima](northwind-orders-canvas-part1.md)
