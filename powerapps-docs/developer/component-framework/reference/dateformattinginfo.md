---
title: DateFormattingInfo | Microsoft Docs
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
ms.assetid: 4e7d43fb-b6b7-4f1d-89e3-0b8157c9d2d9
ms.openlocfilehash: fb6dc5c67cc0ea031ab4e264d282458163ee46a0
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72344826"
---
# <a name="dateformattinginfo"></a>DateFormattingInfo

[!INCLUDE [context-description](includes/dateformattinginfo-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="abbreviateddaynames"></a>Lyhentä päivä nimet

{"Sun", "Mon", "ti", "ke", "Thu", "Fri", "SAT"}

**Tyyppi**: `string`

### <a name="abbreviatedmonthgenitivenames"></a>Lyhenteitä

{"Jan", "Feb", "Mar", "APR", "May", "Jun", "jul", "Aug", "SEP", "Oct", "Nov", "Dec", ""}

**Tyyppi**: `string[]`

### <a name="abbreviatedmonthnames"></a>lyhentele nimet

{"Jan", "Feb", "Mar", "APR", "May", "Jun", "jul", "Aug", "SEP", "Oct", "Nov", "Dec", ""}

**Tyyppi**: `string[]`

### <a name="amdesignator"></a>amDesignator

AM

**Tyyppi**: `string`

### <a name="calendar"></a>kalenterin

**Tyyppi**: `object`

@No__t_0-objekti sisältää seuraavat ominaisuudet:

|Nimi|Tyyppi|Kuvaus|
|--|--|--|
|`algorithmType`|`number`|1|
|`calendarType`|`number`|1|
|`maxSupportedDateTime`|`Date`|"/Date (253402300799999)/"|
|`minSupportedDateTime`|`Date`|"/Date (-62135568000000)/"|
|`twoDigitYearMax`|`number`|2029|

### <a name="calendarweekrule"></a>Calendarweeweule

**Tyyppi**: `number`

### <a name="dateseparator"></a>dateSeparator

"/"

**Tyyppi**: `string`

### <a name="daynames"></a>Päivä nimet

{"Sunday", "maanantai", "tiistai", "Keski viikko", "torstai", "perjantai", "lauantai"}

**Tyyppi**: `string[]`

### <a name="firstdayofweek"></a>firstDayOfWeek

**Tyyppi**: `number`

@No__t_0-ominaisuuden arvo voi olla jokin seuraavista:

|Value|Merkitys|
|--|--|
|0|Sunnuntai|
|1|Maanantai|
|2|Tiistai|
|3|Keski viikko|
|4|Torstai|
|5|Perjantai|
|6|Lauantai|

### <a name="fulldatetimepattern"></a>Fulldatetimespatterne

"dddd, mmmm d, vvvv h:mm: SS TT"

**Tyyppi**: `string`

### <a name="longdatepattern"></a>Longdatepatterne

dddd, MMMM d, VVVV "

**Tyyppi**: `string`

### <a name="longtimepattern"></a>Longtime-muoto

"hh:mm: SS TT"

**Tyyppi**: `string`

### <a name="monthdaypattern"></a>Kuukauden päivä muoto

"MMMM DD"

**Tyyppi**: `string`

### <a name="monthgenitivenames"></a>Kuukauden aikana

{"January", "February", "March",...  "Joulukuu", ""}

**Tyyppi**: `string[]`

### <a name="monthnames"></a>Monmontnames

{"January", "February", "March",...  "Joulukuu", ""}

**Tyyppi**: `string[]`

### <a name="pmdesignator"></a>Ppdesignator

PM

**Tyyppi**: `string`

### <a name="shortdatepattern"></a>Shortdatepatterne

"M/d/VVVV"

**Tyyppi**: `string`

### <a name="shorttimepattern"></a>Shorttime-muoto

"h:mm TT"

**Tyyppi**: `string`

### <a name="shortestdaynames"></a>shortestDayNames

{"Su", "mo", "tu", "me", "ITH", "FR", "SA"}

**Tyyppi**: `string[]`

### <a name="sortabledatetimepattern"></a>Lajittelu menetelmä

yyyy'-'MM'-'dd'T'HH ': ' mm ': ' SS '

**Tyyppi**: `string`

### <a name="timeseparator"></a>timeSeparator

":"

**Tyyppi**: `string`

### <a name="universalsortabledatetimepattern"></a>Universsortabledatetimestabe

"vvvv-'MM'-'dd HH": "mm": "ss'Z" "

**Tyyppi**: `string`

### <a name="yearmonthpattern"></a>vuoden kuukausi rakenne

"MMMM VVVV"

**Tyyppi**: `string`


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)