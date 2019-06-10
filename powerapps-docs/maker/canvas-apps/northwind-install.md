---
title: Asenna Northwind Traders tietokantaa ja sovelluksia | Microsoft Docs
description: Asenna ympäristö, jossa voit tutkia suhteellisena käsitteitä Northwind tietokantaa ja sovelluksia.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/06/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 351f9fd4fe369b3073a9edfb0158883140f50693
ms.sourcegitcommit: e85072f7a80da308c4caabe20adbf2509588ca57
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/07/2019
ms.locfileid: "66761024"
---
# <a name="install-northwind-traders-database-and-apps"></a>Asenna Northwind Traders tietokantaa ja sovelluksia

Noudattamalla seuraavia vaiheita [aiheita opetusohjelmasarjassa](northwind-orders-canvas-part1.md), löytää käsitteitä relaatiotietoja tietoja Common Data Service-mallitietokannan toteutettu. Voit myös tutustua business Mallisovelluksia, sekä pohjaan ja malliin perustuvien, että tietojen hallintaa varten ja ansaita käytännön kokemusta luomalla olevan sovelluksen. Tässä ensimmäisessä ohjeaiheessa kerrotaan, miten voit asentaa Northwind Traders tietokannan oman ympäristön ja käyttää Mallisovelluksia, joka pystyy avaamaan näyttämään, miten ne on luotu muokkaamista varten.

Northwind Traders on kuvitteellisia organisaatioon, joka hoitaa tilaukset, tuotteet, asiakkaille, Toimittajat ja pienyrityksen monista muista ominaisuuksista. Tässä esimerkissä olivat ensimmäisen Microsoft Access-versioiden kanssa, ja se on edelleen saatavilla Access-mallin.

## <a name="prerequisites"></a>Edellytykset

- PowerApps-käyttöoikeus, joka tukee Common Data Service. Voit myös [käyttää ilmainen kokeilu](../signup-for-powerapps.md) 30 päivän ajalta.
- Ympäristön Common Data Service-tietokannan kanssa. Voit myös [tällaisen ympäristön](https://docs.microsoft.com/power-platform/admin/create-environment) Jos sinulla on tarvittavat oikeudet.

## <a name="download-the-solution"></a>Lataa ratkaisu

> [!div class="nextstepaction"]
> [Lataa Northwind Traders ratkaisutiedosto](https://pwrappssamples.blob.core.windows.net/samples/NorthwindTraders_1_0_0_6.zip)

Tämä [ratkaisun](../../developer/common-data-service/introduction-solutions.md) (.zip)-tiedosto sisältää entiteettien, asetusjoukkojen ja liiketoimintaprosessien sujuvuus määritykset; piirtoalustan ja mallipohjaisia sovelluksia ja muita osia, joita käytetään yhdessä.

## <a name="install-the-solution"></a>Asenna ratkaisu

1. Kirjaudu sisään [Powerappsin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), ja varmista, että käytät ympäristössä, joka sisältää Common Data Service-tietokannan.

1. Valitse vasemmassa siirtymisruudussa **ratkaisuja**, ja valitse sitten **tuonti** työkalurivin näytön yläreunan lähellä:

    > [!div class="mx-imgBorder"]
    > ![Ratkaisuja näkymä- ja tuonti-ratkaisun aloituskohta](media/northwind-install/solution-import.png)

1. Tässä **Valitse ratkaisupaketin** sivulla, **Selaa**.

    > [!div class="mx-imgBorder"]
    > ![Valitse ratkaisun sivu, ennen kuin paketti on valittuna](media/northwind-install/select-solution2.png)

1. Etsi tiedosto ladataan ja valitse sitten **Avaa**.

    Jos et valinnut eri sijaintia, tiedosto on ladatut tiedostot-kansio.

1. Jos sinulla on oikea tiedosto (versionumero saattaa vaihdella), valitse **seuraava**:

    > [!div class="mx-imgBorder"]
    > ![Valitse ratkaisun sivu, kun paketti on valittuna](media/northwind-install/confirm-solution2.png)

1. - **Ratkaisutiedot** sivulla **seuraava** Jos ratkaisun ja julkaisijan nimi ovat oikein.

    > [!div class="mx-imgBorder"]
    > ![Ratkaisun tietosivu](media/northwind-install/confirm-publisher.png)

1. - **Tuontiasetukset** sivulla **tuonti** Vahvista SDK viestin käsittely, joka edellyttää mallin:

    > [!div class="mx-imgBorder"]
    > ![Tuonnin asetukset-sivulla](media/northwind-install/confirm-sdk.png)

    Toiselle sivulle tulee näkyviin ja näyttää edistymisen ratkaisu on asennettu seuraavan muutaman minuutin ajalta:

    > [!div class="mx-imgBorder"]
    > ![tilanneilmaisin](media/northwind-install/solution-progress.png)

    Kun asennus on valmis, alkuperäisellä sivulla näkyvät tulokset:

    > [!div class="mx-imgBorder"]
    > ![Tuodaan sivu](media/northwind-install/solution-success.png)

1. Valitse **Sulje**.

## <a name="load-the-sample-data"></a>Lataa mallitiedot

1. Valitse **sovelluksia**, ja valitse sitten **Northwind mallitietoja**.

    Odota muutama minuutti, jos Northwind-sovellukset eivät näy heti, kun olet asentanut ratkaisu:

    > [!div class="mx-imgBorder"]
    > ![Northwind tietokannan sovellusten luettelo](media/northwind-install/sample-data-app.png)

1. Kun sovellus pyytää lupaa käyttää Common Data Service, valitse **Salli**:

    > [!div class="mx-imgBorder"]
    > ![Suostumuksen Common Data Service-valintaikkuna](media/northwind-install/sample-data-permission.png)

1. Kun sovellus Lataa ja näyttää mallin-entiteetit eivät sisällä tietueita, valitse **tietoja** täyttämiseen entiteetit:

    > [!div class="mx-imgBorder"]
    > ![Lataa tiedot-painike mallin tietojen hallinta](media/northwind-install/sample-data-load.png)

    Kun sovellus ladataan, pistettä maaliskuuta sovelluksen yläosassa ja tietueiden jakautumisen määrä.

    Entiteetit ladataan tietyssä järjestyksessä niin, että yhteydet voidaan tietueiden välillä. Esimerkiksi **Tilaustiedot** entiteetillä on monta-yhteen suhdetta **tilaukset** ja **tilata tuotteita** entiteettejä, jotka on ladattu ensin.

    Voit peruuttaa prosessi milloin tahansa valitsemalla **Peruuta**, voit poistaa tiedot milloin tahansa valitsemalla **poistaa tietojen**:

    > [!div class="mx-imgBorder"]
    > ![Esimerkki tietojen hallinnan, kun tiedot on ladattu](media/northwind-install/sample-data-progress.png)

    Kun tiedot on ladataan, viimeinen rivi (**monta useiden väliset suhteet**) näyttää **valmis**, ja **tietoja** ja **poistaa tietojen** painikkeet ovat käytettävissä uudelleen:

    > [!div class="mx-imgBorder"]
    > ![Esimerkki tietojen hallinnan, tietojen lataamisen jälkeen](media/northwind-install/sample-data-complete.png)

## <a name="sample-apps"></a>Mallisovellukset

Northwind-ratkaisu sisältää näiden sovellusten käsittelyyn nämä tiedot:

- Northwind tilaukset (pohjaan perustuvat)
- Northwind tilaukset (mallipohjaiset)

Voit avata näitä sovelluksia samalla tavalla kuin avata sovelluksen edellisten ohjeiden mukaisesti.

### <a name="canvas"></a>Pohja

Tämä yhden näytön sovellus tarjoaa yksinkertaisia päätieto-näkymän **tilaukset** entiteetin, jossa voit tarkastella ja muokata tilauksen ja tilauksen kunkin rivinimikkeen yhteenveto. Luettelon tilausten tulee lähellä vasenta reunaa, voit valita nuoli luettelon yhteenveto ja järjestyksessä tiedot. Lisätietoja: [Yleiskatsaus Northwind Traders kangas-sovelluksen](northwind-orders-canvas-overview.md).

> [!div class="mx-imgBorder"]
> ![Luettelon tilausten ja tiedot-Northwind pohjaan sovellus](media/northwind-install/orders-canvas.png)

### <a name="model-driven"></a>Mallipohjainen

Tämä sovellus toimii samoja tietoja (- **tilaukset** entiteetin) kuin kangas-sovellus. Näytä tilausten luettelon tilauksen lisätietoja valitsemalla sen numero:

> [!div class="mx-imgBorder"]
> ![tilausten Northwind malliin perustuvien sovellusten luettelo](media/northwind-install/orders-model.png)

Tilauksen yhteenveto näkyy erillinen lomake:

> [!div class="mx-imgBorder"]
> ![mallipohjaisen sovelluksen Tilaustiedot](media/northwind-install/orders-model-2.png)

Jos vierität alas lomakkeessa, se näyttää saman nimikkeiden kuin kangas-sovellus:

> [!div class="mx-imgBorder"]
> ![mallipohjaisen sovelluksen Lisää Tilaustiedot](media/northwind-install/orders-model-3.png)

## <a name="do-it-yourself"></a>Tehdä sen itse

Voit seurata Luo kangas-sovellus, joka on kuvattu aiemmin tässä ohjeaiheessa vaiheittaisia ohjeita.  Ohjeita jaetaan kolme osaa:

1. [Luo order-valikoima](northwind-orders-canvas-part1.md).
1. [Luo yhteenveto lomake](northwind-orders-canvas-part2.md).
1. [Luo tietoja-valikoiman](northwind-orders-canvas-part3.md).

Jos haluat Ohita ratkaisu sisältää kunkin osan aloituskohta-sovellus.  Etsi sovellusten luettelo **Northwind tilaukset (pohjaan perustuvat) - Aloita osa 1** ja niin edelleen.

Tämä [sovelluksen yleiskatsaus](northwind-orders-canvas-overview.md) kerrotaan käyttäjän liittymän tietolähteitä ja miten yhteyksiä käytetään.

> [!div class="nextstepaction"]
> [Aloita lukemalla yleiskatsaus](northwind-orders-canvas-overview.md)
