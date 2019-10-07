---
title: Asenna Northwind Traders-tieto kanta ja-sovellukset | Microsoft Docs
description: Asenna Northwind-tieto kanta ja sovellukset ympäristöön, jotta voit tutkia relaatio konsepteja.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/06/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3a2c3b468c7ccc09c49221c65113e66b562f5ed1
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71990500"
---
# <a name="install-northwind-traders-database-and-apps"></a>Asenna Northwind Traders-tieto kanta ja-sovellukset

Noudattamalla [tämän aiheiden sarjan](northwind-orders-canvas-part1.md)vaiheita voit tutustua relaatio tietojen käsitteisiin, jotka on otettu käyttöön Common Data Service malli tieto kannassa. Voit myös tutkia malli yritys sovelluksia, sekä pohjaan perustuvaa että mallipohjaista, jotta voit hallita näitä tietoja ja ansaita käytännön kokemusta luomalla tällaisen sovelluksen. Tässä ensimmäisessä ohje aiheessa kerrotaan, miten voit asentaa Northwind Traders-tieto kannan omassa ympäristössäsi ja käyttää malli sovelluksia, jotka voit avata muokkaamista varten ja paljastaa, miten ne on muodostettu.

Northwind Traders on kuvitteellinen organisaatio, joka hallitsee tila uksia, tuotteita, asiakkaita, toimittajia ja monia muita pienen yrityksen näkö kohtia. Tämä malli ilmestyi Microsoft Accessin ensimmäisissä versioissa, ja se on yhä käytettävissä käyttö oikeus mallina.

## <a name="prerequisites"></a>Edellytykset

- Common Data Service tukeva PowerApps-käyttö oikeus. Voit [käyttää maksutonta kokeilu käyttö oikeutta](../signup-for-powerapps.md) 30 päivän ajan.
- Ympäristö, jossa on Common Data Service-tieto kanta. Voit [luoda tällaisen ympäristön](https://docs.microsoft.com/power-platform/admin/create-environment) , jos sinulla on tarvittavat käyttö oikeudet.

## <a name="download-the-solution"></a>Lataa liuos

> [!div class="nextstepaction"]
> [Lataa Northwind Traders-ratkaisun tiedosto](https://pwrappssamples.blob.core.windows.net/samples/NorthwindTraders_1_0_0_6.zip)

Tämä [ratkaisun](../../developer/common-data-service/introduction-solutions.md) tiedosto (. zip) sisältää entiteettien, asetus joukkojen ja liiketoiminta prosessien määritykset. pohjaan perustuvat ja mallipohjaiset sovellukset; ja kaikki muut osat, joita käytetään yhdessä.

## <a name="install-the-solution"></a>Asenna liuos

1. Kirjaudu sisään [Powerappsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)ja varmista, että työskentelet ympäristössä, joka sisältää Common Data Service-tieto kannan.

1. Valitse vasemmassa siirtymis ruudussa **ratkaisut**ja valitse sitten **tuo** työkalu riviltä näytön yläreunan lähellä:

    > [!div class="mx-imgBorder"]
    > ![Ratkaisujen tarkastelu ja tuonti – ratkaisun aloitus kohta @ no__t-1

1. Valitse **Valitse ratkaisun paketti** -sivulla **Selaa**.

    > [!div class="mx-imgBorder"]
    > ![Valitse ratkaisun paketin sivu ennen paketin valitsemista @ no__t-1

1. Etsi lataamasi tiedosto ja valitse sitten **Avaa**.

    Ellet ole valinnut eri sijaintia, tiedosto on lataukset-kansiossasi.

1. Jos sinulla on oikea tiedosto (versio numero voi vaihdella), valitse **Seuraava**:

    > [!div class="mx-imgBorder"]
    > ![Valitse ratkaisun paketin sivu, kun paketti on valittu @ no__t-1

1. Valitse **ratkaisun tiedot** -sivulla **Seuraava** , jos ratkaisun nimi ja julkaisija ovat oikein.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisun tietojen sivu @ no__t-1

1. Valitse **tuonti asetukset** -sivulla **tuo** vahvistaaksesi SDK-viestin käsittelyn, jota malli vaatii:

    > [!div class="mx-imgBorder"]
    > ![Tuonnin asetukset-sivu @ no__t-1

    Näkyviin tulee toinen sivu, joka näyttää edistymisen, kun ratkaisuun on asennettu muutaman minuutin kuluttua:

    > [!div class="mx-imgBorder"]
    > ![edistymis palkki @ no__t-1

    Kun asennus on valmis, alkuperäinen sivu esittää tuloksen:

    > [!div class="mx-imgBorder"]
    > ![Tuo ratkaisun sivu @ no__t-1

1. Valitse **Sulje**.

## <a name="load-the-sample-data"></a>Lataa malli tiedot

1. Valitse **sovellukset**ja valitse sitten **Northwind-malli tiedot**.

    Odota muutama minuutti, jos Northwind-sovellukset eivät näy heti ratkaisun asentamisen jälkeen:

    > [!div class="mx-imgBorder"]
    > ![Northwind-tieto kanta sovellusten luettelon @ no__t-1

1. Kun sovellus pyytää lupaa käsitellä Common Data Service, valitse **Salli**:

    > [!div class="mx-imgBorder"]
    > ![Suostumus-valinta ikkuna Common Data Service @ no__t-1

1. Kun sovellus on latautunut ja osoittaa, että malli entiteetit eivät sisällä tietueita, täytä entiteetit valitsemalla **Lataa tiedot** :

    > [!div class="mx-imgBorder"]
    > ![Lataa tiedot-painike malli tietojen hallinnassa @ no__t-1

    Koska sovellus lataa tiedot, pisteitä marssi sovelluksen yläosassa ja tietueiden määrä kasvaa.

    Entiteetit ladataan tietyssä järjestyksessä, jotta suhteita voidaan muodostaa tietueiden välillä. Esimerkiksi **Order Details** -entiteetillä on monta yhteen-suhde **tila ukset** -ja **tilaus tuotteet** -entiteetteihin, jotka on ladattu ensin.

    Voit peruuttaa prosessin milloin tahansa valitsemalla **Peruuta**, jolloin voit poistaa tiedot milloin tahansa valitsemalla **Poista tiedot**:

    > [!div class="mx-imgBorder"]
    > ![Esimerkki tietojen Hallin nasta, kun tiedot ladataan @ no__t-1

    Kun tiedot on ladattu, viimeinen rivi (monta moneen-**suhde** **) näytetään,** ja **Lataa tiedot** -ja **Poista tiedot** -painikkeet ovat käytössä uudelleen:

    > [!div class="mx-imgBorder"]
    > ![Sample Data Manager, kun tiedot on ladattu @ no__t-1

## <a name="sample-apps"></a>Mallisovellukset

Northwind-ratkaisussa nämä sovellukset ovat vuoro vaikutuksessa näiden tietojen kanssa:

- Northwind-tila ukset (piirto alusta)
- Northwind-tila ukset (mallipohjainen)

Avaat nämä sovellukset samalla tavalla kuin avasit sovelluksen edellisessä toiminnossa.

### <a name="canvas"></a>Pohja

Tämä yksinäyttöinen sovellus tarjoaa yksinkertaisen Master-Detail-näkymän **tila ukset** -entiteetistä, jossa voit tarkastella ja muokata tilausta koskevaa yhteenvetoa ja kutakin tila uksen riviä. Tilausten luettelo näkyy lähellä vasenta reunaa, ja voit valita luettelosta nuolen, joka näyttää yhteenvedon ja kyseisen järjestyksen tiedot. Lisätietoja: [Northwind Traders-kangas sovelluksen Yleiskatsaus](northwind-orders-canvas-overview.md).

> [!div class="mx-imgBorder"]
> ![Luettelon tila uksista ja tiedoista Northwind Canvas-sovelluksessa @ no__t-1

### <a name="model-driven"></a>Mallipohjainen

Tämä sovellus toimii samoilla tiedoilla ( **tila ukset** -entiteetissä) kangas sovelluksena. Näytä tilausten luettelon lisä tietoja tila uksesta valitsemalla sen numero:

> [!div class="mx-imgBorder"]
> ![luettelo Northwind-malliin perustuvan sovelluksen tila uksista @ no__t-1

Tila uksen yhteenveto tulee erilliseen lomakkeeseen:

> [!div class="mx-imgBorder"]
> ![tilauksen tiedot mallipohjaisessa sovelluksessa @ no__t-1

Jos vierität lomaketta alaspäin, se näyttää samat rivit kuin kangas sovelluksessa:

> [!div class="mx-imgBorder"]
> ![lisää tilaus tietoja mallipohjaisessa sovelluksessa @ no__t-1

## <a name="do-it-yourself"></a>Tee se itse

Voit seurata vaiheittaisia ohjeita tämän ohje aiheen aiemmin näytetyn kangas sovelluksen luomi seksi.  Ohjeet on jaettu kolmeen osaan:

1. [Luo tilaus valikoima](northwind-orders-canvas-part1.md).
1. [Luo Yhteenveto lomake](northwind-orders-canvas-part2.md).
1. [Luo tieto valikoima](northwind-orders-canvas-part3.md).

Jos haluat siirtyä eteenpäin, liuos sisältää aloitus kohdan sovelluksen kullekin osalle.  Etsi sovellus listasta **Northwind-tila ukset (piirto alusta) – Aloita osa 1** ja niin edelleen.

Tässä [sovelluksen yleiskatsauksessa](northwind-orders-canvas-overview.md) selitetään käyttö liittymä, tieto lähteet ja yhteyksien käyttö tavat.

> [!div class="nextstepaction"]
> [Aloita lukemalla yleiskatsaus](northwind-orders-canvas-overview.md)
