---
title: PowerApps Component Framework-luettelon rakenteen viite tiedot | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 06/4/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 045a395b-4475-48dd-8f67-6bc2b33cd89c
ms.openlocfilehash: 8f58f10f6a3695615ddc3b58b540c59240af9641
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346367"
---
# <a name="manifest-schema-reference"></a>Luettelotiedoston rakenteen tietoja

Tässä osassa on tietoja luettelotiedoston rakenteesta, joka luodaan PowerApps-komentorivikäyttöliittymän (CLI) avulla.

> [!IMPORTANT]
> **Käytettävissä** väli lehdellä näytetään, mitä elementtejä mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset tukevat (kokeellinen esikatselu). On suositeltavaa tarkistaa kullekin yksittäiselle ominaisuudelle **käytettävissä oleva-** osio, onko sitä tuettu vai ei. **Koodi** -elementtiä tuetaan esimerkiksi sekä mallipohjaisissa sovelluksissa että pohjaan perustuvissa sovelluksissa, mutta **HTML** -ja **IMG** -ominaisuudet **koodi** elementeissä eivät tue pohjaan perustuvia sovelluksia. 

|Elementti|Kuvaus|Käytettävissä kohteelle|
|----|-----------|-----|
|[code](code.md)|[!INCLUDE [code-description](includes/code-description.md)]|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[control](control.md)|[!INCLUDE [control-description](includes/control-description.md)]|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[css](css.md)|[!INCLUDE [css-description](includes/css-description.md)]|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[data-set](data-set.md)|[!INCLUDE [data-set-description](includes/data-set-description.md)]|Mallipohjaiset sovellukset|
|[html](html.md)|[!INCLUDE [html-description](includes/html-description.md)]|Mallipohjaiset sovellukset|
|[img](img.md)|[!INCLUDE [img-description](includes/img-description.md)]|Mallipohjaiset sovellukset|
|[manifest](manifest.md)|Luettelotiedosto on metatietotiedosto, joka määrittää osan. Se on XML-tiedosto, joka kuvaa<br/> - osan nimitilan<br/> - minkä tyyppisiä tietoja osa voi määrittää (joko kentän tai tietojoukon)<br/> - ominaisuudet, jotka voidaan määrittää sovelluksessa, kun osa lisätään<br/> - luettelon resurssitiedostoista, joita osa tarvitsee<br/> - yhden resurssitiedostoista on oltava JavaScript-verkkoresurssi. Tämän JavaScript-kohteen tulee sisältää funktio, joka alustaa objektin. Näin toteutetaan liittymä, joka paljastaa komponentin toimintaan tarvittavat metodit. Tätä kutsutaan osan toteutuskirjastoksi.<br/> - sen JavaScript-funktion nimen, joka toteutuskirjastossa palauttaa tarvitun käyttöliittymän toteuttavan objektin.<br/> Kun joku määrittää osan sovelluksessa, kokoonpanotiedot suodattavat käytettävissä olevat osat niin, että vain kontekstissa kelvolliset osat ovat määritettävissä. Kokoonpanotiedoissa määritetyt osan ominaisuudet hahmonnetaan määrityskenttinä, niin että ohjausobjektia määrittävä henkilö voi määrittää arvot. Ominaisuuksien arvot ovat sitten osafunktion käytettävissä suoritusaikaan.|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[property](property.md)|[!INCLUDE [property-description](includes/property-description.md)]|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[property-set](property-set.md)|[!INCLUDE [property-set-description](includes/property-set-description.md)]|Mallipohjaiset sovellukset|
|[resources](resources.md)|[!INCLUDE [resources-description](includes/resources-description.md)]|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[resx](resx.md)|[!INCLUDE [resx-description](includes/resx-description.md)]|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[type-group](type-group.md)|[!INCLUDE [type-group-description](includes/type-group-description.md)]|Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)|
|[ominaisuus – käyttö](feature-usage.md)|Ominaisuus – käyttö-elementti toimii pakettina `uses-feature`-elementtien ympärillä, joiden avulla kehittäjät voivat itse määrittää, mitä ominaisuuksia heidän komponenttiensa haluaa käyttää. Jos ominaisuuksia ei ole määritetty, ominaisuus-käyttö-elementtiä ei tarvita.|Mallipohjaiset sovellukset|

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Frameworkin luettelon rakenteen viite](index.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)