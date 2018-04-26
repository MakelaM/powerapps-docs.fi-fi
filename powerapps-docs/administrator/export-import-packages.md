---
title: Tuo ja vie resursseja | Microsoft Docs
description: Tuo ja vie resursseja
services: powerapps
documentationcenter: na
author: nimakms
manager: kfend
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/28/2017
ms.author: kfend
ms.openlocfilehash: c1788d4119d9b4efbeabe8d6fa4fa45f293c2a9d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="export-and-import-resources"></a>Tuo ja vie resursseja
Jos kehität tietokantaa ja sovelluksia usean ympäristön avulla, muutokset on siirrettävä ympäristöstä toiseen. Voit siirtää resursseja ympäristöstä toiseen **Vie resurssit**- ja **Tuo resurssit** -toiminnoilla.

## <a name="why-use-multiple-environments"></a>Miksi kannattaa käyttää useita ympäristöjä?
Jokainen ympäristö sisältää entiteettien, työnkulkujen ja sovellusten kaltaisia resursseja, joita luot tai muokkaat kehitysprosessin aikana. 

Yleensä kehitysympäristönä käytetään organisaation loppukäyttäjien käyttämää ympäristöä. Tätä ympäristöä kutsutaan oletusympäristöksi. On melko helppoa hallita resurssimuutoksia yhdessä ympäristössä. Ennen sovelluksen julkaisemista vahvistat muutokset ja varmistat, että kaikki tärkeät liiketoimintaprosessit ja sovellukset toimivat.

Joskus kehitys ja testaus tehdään erillisissä ympäristöissä ja muutokset siirretään oletusympäristöön, kun ne ovat valmiita loppukäyttäjien käytettäviksi. Erillisten ympäristöjen käyttämiseen on monia syitä. Saatoit esimerkiksi alun perin arvioida järjestelmän erillisessä ympäristössä. Toisaalta haluat ehkä vähentää oletusympäristön muuttamiseen liittyviä riskejä. Erilliset ympäristöt eristävät mahdolliset ongelmat, sillä muutokset tehdään muualla kuin oletusympäristössä. Riskiä voi vähentää merkittävästi luomalla vielä ylimääräisen valmisteluympäristön. Silloin käytössä on kehitysympäristö, valmisteluympäristö ja oletusympäristö.

## <a name="moving-resource-changes"></a>Resurssimuutosten siirto
Resurssit siirretään erillisten vienti- ja tuontiprosessien pakettitiedostoina (.zip). Pakettitiedosto viedään ja tallennetaan paikalliseen tallennustilaan, lähetetään kohdeympäristön järjestelmänvalvojalle ja tuodaan sitten kohdeympäristöön. Tuontiprosessin jälkeen varmistetaan usein tarkistustesteillä, etteivät mitkään tärkeät liiketoimintaprosessit vahingoittuneet siirrossa.

Sekä resurssien tuonti että vienti on käytettävissä hallintakeskuksen **Ympäristöt**-osiossa. Sekä vienti että tuonti tehdään valitussa ympäristössä.

### <a name="export-resources"></a>Resurssien vienti
Vientipaketti sisältää kaikki **entiteettien ja valintaluetteloiden muutokset**. Pyrimme siihen, että tulevaisuudessa voitaisiin viedä myös muuntyyppisiä resursseja, kuten sovelluksia, työnkulkuja, liittimiä ja rooleja. Tällä toiminnolla voit siirtää sisältöä ympäristöstä toiseen.

1. Valitse [hallintakeskuksen](https://admin.powerapps.com) vasemmasta siirtymisruudusta **Ympäristöt**.
2. Valitse lähdeympäristö.
3. Valitse oikeasta yläkulmasta **Vie resurssit**.
4. Valitse resurssit, joista haluat aloittaa:
   1. Valitse haluamaasi resurssityyppiä vastaava välilehti, esimerkiksi **Entiteetit**.
   2. Valitse kaikki kyseisen tyypin resurssit napsauttamalla otsikon valintaruutua tai valitse resurssit yksitellen.
   3. Valitse **Seuraava**.
5. Liitä tarvittaessa aiheeseen liittyvät resurssit:
   1. Jos aiheeseen liittyviä resursseja ei löydy, esiin tulee ennalta valittu luettelo.
   2. Poista kaikkien aiheeseen liittyvien resurssien valinta napsauttamalla otsikon valintaruutua tai poista resurssivalinnat yksitellen.
   3. Valitse **Seuraava**.
6. Nimeä viety paketti **Nimi**-kentässä.
7. Vaihtoehtoisesti voit valita, että määritykset tehdään vasta resurssien tuonnin yhteydessä:
   1. Avaa kunkin resurssin valintaikkuna valitsemalla sen kohdalla **Tuonnin määritykset**.
   2. Valitse paketin tuonnin yhteydessä oletusarvoisesti suoritettava määritystoimenpide.
   3. Valitse **Tallenna**.
8. Valitse **Vie**.
9. Kun vienti on valmis, tallenna pakettitiedosto paikalliseen tallennustilaan.

Vaihtoehtoisesti voit valita kaikki lopullisen paketin tukemat resurssit napsauttamalla resurssien valintasivun kohtaa **Valitse kaikki resurssit**. Ohjaudut suoraan viimeiselle vientisivulle.

### <a name="import-resources"></a>Resurssien tuonti
Ensimmäiseksi on valittava lähdeympäristöstä viety pakettitiedosto. Tuontiprosessi vahvistaa, analysoi ja yrittää tuoda paketin.

1. Valitse [hallintakeskuksen](https://admin.powerapps.com) siirtymisruudusta **Ympäristöt**.
2. Valitse kohdeympäristö.
3. Valitse oikeasta yläkulmasta **Tuo resurssit**.
4. Napsauta kohtaa **Lataa** ja valitse pakettitiedosto paikallisesta tallennustilasta.
5. Siirry viimeiselle tuontisivulle napsauttamalla **Seuraava**-painiketta.
6. Tuonnin vahvistusvirheiden ja varoitusten ratkaiseminen:
   1. Varoituksista tai virheistä ilmoittaa resurssin **nimen** viereen ilmestyvä kuvake.
   2. Lisätietoja saa napsauttamalla **Tuonnin määritykset** -kenttää tai **toiminnon** alla olevaa kuvaketta.
   3. Valitse asianmukainen tuonnin määrityksen toiminto.
   4. Tuotava paketti vahvistetaan jälleen automaattisesti.
7. Jatka **tuontia**, jos virheitä ei ole.

Jos paketin tuonnin määritykset toteutuivat vain osittain, näet virheilmoituksesta, mitkä resurssit tuotiin ja mitkä ei.

## <a name="resource-types"></a>Resurssityypit
Kehitysprosessin aikana saatetaan tehdä muutoksia monentyyppisiin resursseihin. Sovellusta päivittäessä saatat esimerkiksi lisätä, poistaa tai päivittää useita entiteettejä tai yhteyksiä. Joidenkin, mutta ei kaikkien, resurssityyppien muutokset voidaan siirtää ympäristöstä toiseen. Seuraavissa osioissa kuvaillaan resurssityypit, jotka voi siirtää.

### <a name="entities-picklists"></a>Entiteetit ja valintaluettelot
Entiteettien ja valintaluetteloiden vienti- ja tuontiohjeet:

* **Vakioentiteetit** – Vain mukautukset siirretään ympäristöstä toiseen. (Vakioentiteettien valmiita kenttiä ei voi muokata.)
* **Mukautetut entiteetit** – Mukautetut entiteetit siirretään ympäristöstä toiseen.
* **Mukautetut valintaluettelot** – Mukautetut valintaluettelot siirretään ympäristöstä toiseen.

## <a name="data"></a>Tiedot
Tietokantatietoja ei voi siirtää osana resurssien vientiä ja tuontia. Voit siirtää tietoja Microsoft Excelillä. 

