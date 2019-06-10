---
title: Northwind Traders kangas-sovelluksen yleiskatsaus | Microsoft Docs
description: ''
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/17/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e2f28b07f53646e6fbf5afc0b1510bd37e3262b8
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/07/2019
ms.locfileid: "66761047"
---
# <a name="overview-of-the-canvas-app-for-northwind-traders"></a>Yleiskatsaus Northwind Traders kangas-sovellus

Lue lisätietoja pohjaan perustuvan sovelluksen hallintaan suhteellisena Northwind Traders tietoja tietokannan, [asennettu ympäristösi](northwind-install.md). Noudata tämän sovelluksen alusta alkaen, kasvun siten käytännönläheisen kokemuksen relaatiotietoja seuraavat aiheet vaiheittaiset ohjeet.

Tässä ohjeaiheessa löytää:

- Miten sovelluksen käyttäjälle näytetään ja hallitsee relaatiotietoja sovelluksessa.
- Näytettävien tietojen asema sovelluksen.
- Miten kyseiset tietotyyppejä välisiä luotiin.

Samassa näytössä sovelluksen käyttäjälle voi näyttää, päivittää, luoda ja poistaa tilauksia.

> [!div class="mx-imgBorder"]
> ![Valmis kangas-sovellus](media/northwind-orders-canvas-part1/orders-finished.png)

## <a name="explore-the-user-interface"></a>Tutustu käyttöliittymän

### <a name="order-gallery"></a>Tilauksen valikoima

Sovelluksen vasemmassa reunassa valikoimassa näytetään tilauksia, mukaan lukien tilausnumero, tilan, joiden asiakkaan nimi ja tilauksen kokonaiskustannusten luettelo. Käyttäjä voi selata luettelon tilauksen etsii ja näyttää lisätietoja siitä sitten valitsemalla tilauksen nuolta. Lisätietoja: [Luo tilauksen valikoiman](northwind-orders-canvas-part1.md).

### <a name="summary-form"></a>Yhteenveto

Oikeassa yläkulmassa lomakkeen on, että käyttäjä valitsi valikoimassa tilauksen tilauksen yhteenveto. Yhteenveto sisältää paljon samoja tietoja, kuten valikoiman ei, mutta yhteenveto näkyy myös päivämäärät, kun tilaus on luotu ja maksettu sekä nimi ja työntekijä, joka hallittu tilauksen kuva. Käyttäjä muuttaa lomakkeen tietoja, tallennat muutokset, Peruuta ne tai Poista tilaus valitsemalla kuvake lähellä oikeaa reunaa otsikkorivin. Lisätietoja: [Luo yhteenveto lomake](northwind-orders-canvas-part2.md).

### <a name="detail-gallery"></a>Valikoiman tiedot

Oikeassa yläkulmassa toinen valikoima näyttää tiedot siitä, mitkä tuotteet valitun tilauksen sisältää ja kuinka paljon. Valikoiman kohteen kutsutaan tilauksen tiedot. Sovelluksen käyttäjälle voit lisätä ja poistaa minkä tahansa valikoiman kohteen käyttämällä ohjausobjekteja- ja sen alla. Lisätietoja: [Luo tietoja-valikoiman](northwind-orders-canvas-part3.md).

> [!div class="mx-imgBorder"]
> ![Näytön alueiden määritys](media/northwind-orders-canvas-part1/orders-parts.png)

## <a name="explore-the-data-sources"></a>Tutustu tietolähteisiin

Tämän sovelluksen luomiseen näytät tiedot viisi entiteetit ja asetusjoukon. Itse asiassa useimmissa alue tämän sovelluksen esittää useita entiteettejä tietoja. Esimerkiksi valikoiman tilaus sisältää nämä tiedot:

- Tilausnumero on kenttä **tilaukset** entiteetin.
- Tila on toisen kentän **tilaukset** entiteetin, vaihtoehto **tilausten tila** asetusjoukko.
- Asiakkaan nimi on kenttä **asiakkaille** entiteetin.
- Kokonaiskustannukset lasketaan tietojen perusteella **Tilaustiedot** entiteetin.

Yhteenveto sisältää joitakin samat tiedot kuin luettelon tilausten, mutta se sisältää myös nimi ja työntekijä, joka hallittu tilauksen kuva. Tiedot tulevat kenttien **työntekijät** entiteetin. Tiedot-valikoima näyttää tietueita **Tilaustiedot** entiteetin ja kunkin tuotteen nämä tiedot on tietueen **tilata tuotteita** entiteetin.

## <a name="explore-the-relationships"></a>Tutustu suhteet

Voit näyttää tietoja eri lähteistä (esimerkiksi entiteetit) ovat samassa valikoimassa tai lomakkeessa koska entiteeteistä on suhteita, jotka on luotu tietokannan puolestasi.

### <a name="many-to-one-relationships"></a>Monta yhteen-suhteita

Esimerkiksi asiakkaan ja kunkin tilauksen työntekijän tietoja sijaitsevat **asiakkaille** ja **työntekijät** entiteettejä. Tämän vuoksi **tilaukset** entiteetillä on monta-yhteen suhteita kyseisten entiteetteihin, koska on olemassa useita tilauksia, jotka voidaan asettaa vain yksi asiakkaan mukaan ja vain yksi työntekijä hallitsee.

Jokaisen order on myös yksi tai useampi rivit, jotka edustavat tuotetta, jotka tilaus sisältää sekä niiden määrät. Kunkin on tietueen **Tilaustiedot** entiteettiä, joka hakee tietoja kunkin tuotteen **tilata tuotteita** entiteetin. Kunkin tiedot tunnistaa vain yhdessä tuotteessa, mutta jokainen tuote voi olla useita tiedot. Tämän vuoksi **Tilaustiedot** entiteetillä on monta-yhteen suhdetta **tilata tuotteita** entiteetin.

### <a name="one-to-many-relationships"></a>Yksi moneen suhteita

Jokaisen order voi sisältää useita nimikkeiden, mutta kunkin koskee vain yksi tilaus. Tämän vuoksi **tilaukset** entiteetillä on yksi moneen suhteen **Tilaustiedot** entiteetin.

### <a name="dot-notation-for-relationships"></a>Suhteiden merkintätapaa piste 

Näytetään entiteettien välisen suhteen perusteella, voit piste ominaisuuden valitsin ja opit luomaan suhdetta kaikissa yhdestä entiteetistä toiseen.  Esimerkiksi jokaiselle tietueelle **tilaukset** entiteetin hakee tiedot **asiakkaille** entiteetti niin, että tilauksen valikoima näyttää asiakkaiden nimiä. Valikoiman, voit määrittää tämän ongelman määrittämällä **tekstin** ominaisuuden nimen seuraava lauseke:<br>`ThisItem.Customer.Company`

**ThisItem** määrittää tietueen **tilaukset** entiteetin sekä vedetään **asiakkaille** entiteettiin tilauksen tehneen asiakkaan tietoja. Tässä tapauksessa lauseke määrittää, että asiakkaan yrityksen nimi näkyy. Kuitenkin asiakkaan koko tietueen on koonneet, joten voit aivan yhtä vaivattomasti näyttää, esimerkiksi sähköpostiosoite asiakkaan sen sijaan.

Toinen esimerkki, tarvitset lisäapua toiseen yhdestä entiteetistä luomiseen voit määrittää, valikoima näyttää yhden entiteetin, jonka käyttäjä valitsi toinen valikoiman, joka ei toisen entiteetin tietueen perusteella tietueet. Tilauksen tiedot näytetään, määritä tietoja-valikoiman **kohteet** ominaisuudeksi seuraava lauseke:<br>`Gallery1.Selected.'Order Details'`

Tässä tapauksessa **Gallery1.Selected** määrittää tietueen **tilaukset** entiteetin, samoin kuin **ThisItem** ollut edellisessä esimerkissä. Tämä lauseke ei kuitenkaan Nouda vain yhden tietueen kuin edellisen lausekkeen. Sen sijaan se hakee koko taulukon tietueiden näyttää kunkin tuotteen nimi ja yksikköä kohti resurssitarve (joka näkyy **tilata tuotteita** entiteetin) ja määrä (joka näkyy **Tilaustiedot** entiteetti).

## <a name="do-it-yourself"></a>Tehdä sen itse

Voit seurata vaiheittaiset ohjeet Northwind tilaukset pohjaan perustuvan sovelluksen luomiseen.  Ohjeita jaetaan kolme osaa:

1. [Luo order-valikoima](northwind-orders-canvas-part1.md).
1. [Luo yhteenveto lomake](northwind-orders-canvas-part2.md).
1. [Luo tietoja-valikoiman](northwind-orders-canvas-part3.md).

Jos haluat Ohita ratkaisu sisältää kunkin osan aloituskohta-sovellus.  Etsi sovellusten luettelo **Northwind tilaukset (pohjaan perustuvat) - Aloita osa 1** ja niin edelleen.

> [!div class="nextstepaction"]
> [Jatka luomalla order-valikoima](northwind-orders-canvas-part1.md)
