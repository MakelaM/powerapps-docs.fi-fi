---
title: Mikä on Common Data Model | Microsoft Docs
description: Common Data Model on Microsoftin julkaisema standardoitu, modulaarinen ja laajennettava kokoelma tietorakenteita, joiden avulla tietojen luominen, käyttäminen ja analysoiminen on entistä helpompaa.
author: RobertBruckner
ms.service: powerapps
ms.topic: article
ms.date: 07/24/2018
ms.author: robruc
ms.openlocfilehash: 1469646301c273067ad035428f03c452ae223604
ms.sourcegitcommit: abe4d4728db7f56088f618af5b820af78e7099c9
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/28/2018
ms.locfileid: "39331990"
---
# <a name="what-is-the-common-data-model"></a>Mikä on Common Data Model?

Jos olet joskus törmännyt ongelmiin käyttäessäsi *lähes* samanlaisia tietoja tai tietoja, joiden *pitäisi* toimia yhdessä – ja nähnyt sen jälkeen merkittävästi vaivaa kenttien ja taulukoiden muuntamisessa, jotta ne toimivat muiden tietojesi kanssa – tiedät jo, että yleiset tietoelementit voivat säästää vaivaa, virtaviivaistaa tulevia kehitysprojekteja ja nopeuttaa analysointia. Common Data Model (CDM) tarjoaa muun muassa nämä ominaisuudet.

**Common Data Model (CDM)** on Microsoftin julkaisema standardoitu, modulaarinen ja laajennettava kokoelma tietorakenteita, joiden avulla tietojen luominen, käyttäminen ja analysoiminen on entistä helpompaa. Tämä esimääritettyjen rakenteiden kokoelma, joka koostuu *entiteeteistä*, *määritteistä*, *semanttisista metatiedoista* ja *suhteista*, edustaa yleisesti käytettyjä käsitteitä ja toimintoja, kuten Tili ja Kampanja, jotta tietojen luomista, koostamista ja analysointia voidaan yksinkertaistaa. Lisätietoja: [CDM-raportti GitHubissa](https://aka.ms/cdmrepo)

![Common Data Model](media/cdm-entities.png)

Lisätietoja: [CDM-juliste](https://aka.ms/cdmposter)

## <a name="why-use-the-common-data-model"></a>Miksi Common Data Modelia kannattaa käyttää?

CDM yksinkertaistaa tietojen hallintaa ja sovelluskehitystä yhdistämällä tiedot tunnettuun lomakkeeseen ja käyttämällä rakenteellista ja semanttista yhdenmukaisuutta useissa sovelluksissa ja käyttöönotoissa. Kun tiedot toisin sanoen ovat CDM:ssä, voit käyttää niitä monissa sovelluksissa, virtaviivaistaa muiden olemassa olevia tietoja hyödyntävien sovellusten luomista tai käyttöä ja luoda helposti raportteja niistä kullekin (tai niille kaikille). Lisäksi tietojen integroijat, jotka tuovat tietoja monenlaisista järjestelmistä, voivat keskittyä tietojen sijoittamiseen CDM:ään sen sijaan, että jokaiselle sovellukselle jouduttaisiin luomaan uusi malli.

Oletetaan, että sinulla kolme yrityssovellusta: materiaalisovellus, tuotantosovellus ja myyntisovellus. Usein kukin sovelluksista luotaisiin erikseen, joten niistä jokaisessa on entiteettiä vastaavat erilaiset rakenteet, kuten *Tili*, joka on lähes sama (mutta silti hieman erilainen). CDM:n avulla tiedot voi koostaa standardoidussa muodossa (käyttämällä CDM:n entiteettejä, määritteitä ja suhteita), joten näitä samoja tietoja voidaan käyttää perustana kussakin kolmessa sovelluksessa. Jokaisessa sovelluksessa voi tietenkin olla myös muita tietoja ja rakenteita sovelluksen käyttötarkoituksen mukaan. Kehitysvaihteessa sovellukset ja raportit voivat noutaa yhteiset tietoelementit nopeasti, virheettömästi ja luotettavasti.

Entä jos tarvitsee luoda neljäs sovellus? Tiedot ovat valmiita CDM-rakenteessa, joten kehitysponnistuksissa voidaan keskittyä liiketoimintalogiikkaan upottavan tietoheteikön ja ongelmallisten muunnosten sijasta.

Toisin sanoen CDM tarjoaa tiedoille seuraavat ominaisuudet:

-   **Rakenteellinen ja semanttinen yhdenmukaisuus** eri sovelluksissa ja käyttöönotoissa.

-   Esimerkiksi prosesseista, digitaalisesta vuorovaikutuksesta, tuotetelemetriasta ja ihmisten keskinäisestä vuorovaikutuksesta kerättyjen **tietojen yksinkertaistettu integrointi ja tekeminen yksiselitteiseksi**.

-   **Yhtenäinen muoto**, jossa tietojen integroinnit voivat **yhdistää olemassa olevat yritystiedot muihin lähteisiin** ja käyttää tietoja kokonaisvaltaisesti uusien sovellusten kehittämiseen tai merkityksellisten tietojen koostamiseen.

-   **Mahdollisuuden laajentaa rakennetta ja CDM-entiteettejä**, jotta Common Data Model voidaan sovittaa organisaatioon.

CDM:n avulla voit luoda uusia tietosäilöjä, jotka vastaavat rakennetta, ja voit myös muuntaa olemassa olevat tiedot Common Data Model -rakenteen mukaisiksi. Kummassakin tapauksessa standardisoinnin tuoma tehokkuus voi nopeuttaa ja virtaviivaistaa tietojen tulevaa käyttöä.

## <a name="who-uses-the-common-data-model"></a>Ketkä voivat käyttää Common Data Modelia?

Monenlaiset asiakkaat, kumppanit ja tuotteet hyödyntävät CDM:ää. Kaikilla on sama tavoite yhtenäistää tiedot tunnettuun muotoon, jolla on semanttinen merkitys.

-   **Sovelluskehittäjät**: Riippumatta siitä, käyttävätkö nämä käyttäjät koodipohjaisia ympäristöjä vai vain vähän koodia tai koodittomia ympäristöjä (kuten PowerAppsia), sovellusten tiedot on tallennettava ja niitä on hallittava.

-   **Tietojen integroijat**: Nämä käyttäjät vastaavat monissa järjestelmissä olevien tietojen tuomisesta, jotta tiedot ovat käytettävissä sovelluksissa.

Perinteisesti sovelluksen kehitystyö on yhdistetty tiiviisti tietojen integrointiin, mutta CDM:ssä ja sitä tukevissa ympäristöissä nämä toiminnot voivat tapahtua erikseen.

## <a name="common-data-model-in-action"></a>Common Data Model käytännössä

Microsoft ja sen kumppanit käyttävät CDM:ää omissa sovelluksissaan ja tarjouksissaan. Ne luovat CDM-rakenteisiin perustuvia lisäpalveluja ja -tarjouksia. Seuraavissa esimerkeissä näytetään, miten organisaatiot käyttävät CDM:ää:

-   **Common Data Service (CDS) for Apps**, joka tukee Dynamicsia ja PowerAppsia, tallentaa tiedot CDM-määritysten mukaisesti. Itse asiassa monet CDM:ään sisältyvistä alkuperäisistä liiketoimintaentiteeteistä ovat peräisin Dynamics-tarjouksista, kuten Dynamics 365 for Sales ja Dynamics 365 for Marketing.

-   **Toimialat**, kuten terveydenhuolto, tekevät yhteistyötä Microsoftin kanssa CDM:n laajentamiseksi kyseisen alan liiketoimintakäsitteiden mukaiseksi. Tällaisia ovat esimerkiksi *Potilas* ja *Hoitosuunnitelma*, jotta aloilla voidaan jakaa tietoja ja kehittää palveluja siten, että kumppanit voivat jakaa tietoja helposti, luoda yhteentoimivia sovelluksia ja palveluja sekä luoda nopeasti analyyseja, jotka on helppo jakaa.

## <a name="next-step"></a>Seuraava vaihe

[Common Data Modelin käyttö](use-common-data-model.md): tässä aiheessa kuvataan CDM tarkasti ja käsitellään käyttötapauksia, joissa voidaan luoda uusia tietoja CDM:ssä tai muuntaa jo olemassa olevat tiedot CDM:ään.