---
title: PowerApps-osakehyksen luettelotiedoston rakenteen tietoja | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
manager: ''
ms.date: 06/4/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 045a395b-4475-48dd-8f67-6bc2b33cd89c
ms.openlocfilehash: 88e9d35792d86e279b9af4a19eaff288643412ca
ms.sourcegitcommit: c52c1869510a9a37d9f7b127e06f07583529588b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2019
ms.locfileid: "64524317"
---
# <a name="manifest-schema-reference"></a>Luettelotiedoston rakenteen tietoja

[!INCLUDE[cc-beta-prerelease-disclaimer](../../../includes/cc-beta-prerelease-disclaimer.md)]

Tässä osassa on tietoja luettelotiedoston rakenteesta, joka luodaan PowerApps-komentorivikäyttöliittymän (CLI) avulla.

|Elementti|Kuvaus|
|----|-----------|
|[code](code.md)|[!INCLUDE [code-description](includes/code-description.md)]|
|[control](control.md)|[!INCLUDE [control-description](includes/control-description.md)]|
|[css](css.md)|[!INCLUDE [css-description](includes/css-description.md)]|
|[data-set](data-set.md)|[!INCLUDE [data-set-description](includes/data-set-description.md)]|
|[html](html.md)|[!INCLUDE [html-description](includes/html-description.md)]|
|[img](img.md)|[!INCLUDE [img-description](includes/img-description.md)]|
|[manifest](manifest.md)|Luettelotiedosto on metatietotiedosto, joka määrittää osan. Se on XML-tiedosto, joka kuvaa<br/> - osan nimitilan<br/> - minkä tyyppisiä tietoja osa voi määrittää (joko kentän tai tietojoukon)<br/> - ominaisuudet, jotka voidaan määrittää sovelluksessa, kun osa lisätään<br/> - luettelon resurssitiedostoista, joita osa tarvitsee<br/> - yhden resurssitiedostoista on oltava JavaScript-verkkoresurssi. Tämän JavaScript-kohteen tulee sisältää funktio, joka alustaa objektin. Näin toteutetaan liittymä, joka paljastaa komponentin toimintaan tarvittavat metodit. Tätä kutsutaan osan toteutuskirjastoksi.<br/> - sen JavaScript-funktion nimen, joka toteutuskirjastossa palauttaa tarvitun käyttöliittymän toteuttavan objektin.<br/> Kun joku määrittää osan sovelluksessa, kokoonpanotiedot suodattavat käytettävissä olevat osat niin, että vain kontekstissa kelvolliset osat ovat määritettävissä. Kokoonpanotiedoissa määritetyt osan ominaisuudet hahmonnetaan määrityskenttinä, niin että ohjausobjektia määrittävä henkilö voi määrittää arvot. Ominaisuuksien arvot ovat sitten osafunktion käytettävissä suoritusaikaan.|
|[property](property.md)|[!INCLUDE [property-description](includes/property-description.md)]|
|[property-set](property-set.md)|[!INCLUDE [property-set-description](includes/property-set-description.md)]|
|[resources](resources.md)|[!INCLUDE [resources-description](includes/resources-description.md)]|
|[resx](resx.md)|[!INCLUDE [resx-description](includes/resx-description.md)]|
|[type-group](type-group.md)|[!INCLUDE [type-group-description](includes/type-group-description.md)]|


### <a name="related-topics"></a>Samankaltaiset ohjeartikkelit

[PowerApps-osakehyksen luettelotiedoston rakenteen tietoja](index.md)<br/>
[PowerApps-osakehyksen API-tietoja](../reference/index.md)<br/>
[PowerApps-osakehyksen yleiskatsaus](../overview.md)