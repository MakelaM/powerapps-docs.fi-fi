---
title: DataSet | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0202d51f-e9a9-4a2e-b3e9-0bfd7f6afb86
ms.openlocfilehash: 5e9408c81fc9587b9dec30f18fc68c3112ba6125
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345309"
---
# <a name="dataset"></a>Tietojoukko

[!INCLUDE [dataset-description](includes/dataset-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="addcolumn"></a>addColumn ()

Lisää sarakkeen sarake joukkoon

### <a name="remarks"></a>Huomautuksia

Tämä menetelmä hyväksyy kaksi parametria.

|Nimi|Tyyppi|Pakollinen|Kuvaus|
|------|-----|------|-----|
|Nimi|`string`|Kyllä|Tieto joukkoon lisättävä sarakkeen nimi.|
|Ententalias|`string`|Ei| Entiteetin alias, jolle sarakkeen nimi on lisättävä.|

### <a name="columns"></a>Sarakkeet

Tässä tieto joukossa käytettävissä olevien sarakkeiden joukko.

**Tyyppi**: [sarake](column.md)[]

### <a name="error"></a>Virhe

Onko tietojen noutamiseen ilmennyt virhe.

**Tyyppi**: `boolean`

### <a name="errormessage"></a>errorMessage

Viimeksi kohdattiin virheeseen liittyvä virhe sanoma, jos sellainen on käytettävissä.

**Tyyppi**: `string`

### <a name="filtering"></a>suodatus

Nykyisen kyselyn sarake suodatus.

**Tyyppi**: [suodatus](filtering.md)

### <a name="linking"></a>yhdistää

Määrittää linkitetyn entiteetin tiedot.

**Tyyppi**: [linkittäminen](linking.md)

### <a name="loading"></a>ladataan

Ilmaisee, latautuuko tieto joukko vai ei.

**Tyyppi**: `boolean`

### <a name="paging"></a>sivutus

Sivutus tila ja toiminnot.

**Tyyppi**: [sivutus](paging.md)

### <a name="records"></a>Tietueet

Koko tietue objektin tunnusten kartta.

**Tyyppi: Entityrecord** [](entityrecord.md)

### <a name="sortedrecordids"></a>Sortedrecorddids

Tieto joukon tietueiden tunnukset, order by-kyselyn vastaus tulos.

**Tyyppi**: `string[]`

### <a name="sorting"></a>lajittelu

Nykyisen kyselyn lajittelu tila.

**Tyyppi**: [sortstatus](sortstatus.md)

## <a name="methods"></a>Menetelmiä

|Menetelmä | Kuvaus | 
| ------------- |-------------|
|[Clearselectedrecorddids](dataset/clearselectedrecordids.md)|[!INCLUDE [clearselectedrecordids-description](dataset/includes/clearselectedrecordids-description.md)]| 
|[Getselectedrecorddids](dataset/getselectedrecordids.md)|[!INCLUDE [getselectedrecordids-description](dataset/includes/getselectedrecordids-description.md)]| 
|[kohteen getTargetEntityType](dataset/gettargetentitytype.md)|[!INCLUDE [gettargetentitytype-description](dataset/includes/gettargetentitytype-description.md)]| 
|[getTitle](dataset/gettitle.md)|[!INCLUDE [gettitle-description](dataset/includes/gettitle-description.md)]| 
|[getViewId](dataset/getviewid.md)|[!INCLUDE [getviewid-description](dataset/includes/getviewid-description.md)]| 
|[openDatasetItem](dataset/opendatasetitem.md)|[!INCLUDE [opendatasetitem-description](dataset/includes/opendatasetitem-description.md)]| 
|[päivitys](dataset/refresh.md)|[!INCLUDE [refresh-description](dataset/includes/refresh-description.md)]| 
|[Setselectedrecorddids](dataset/setselectedrecordids.md)|[!INCLUDE [setselectedrecordids-description](dataset/includes/setselectedrecordids-description.md)]| 

## <a name="example"></a>Esimerkki

Lisä tietoja tieto joukko menetelmien toteuttamisesta on kohdassa tieto [joukko ruudukon osa](../sample-controls/data-set-grid-control.md)

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)