---
title: UserSettings | Microsoft Docs
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
ms.assetid: c237ff96-9268-4068-9d61-aea0bdc79fc2
ms.openlocfilehash: 5325091d8f82ffd98cfc4e5fdab4e0228a5d541e
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72341031"
---
# <a name="usersettings"></a>UserSettings

[!INCLUDE [usersettings-description](includes/usersettings-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="dateformattinginfo"></a>Dateformattadinginfo

Palvelimesta noudetut päivämäärä muotoilun tiedot.

**Tyyppi**: [dateformattadinginfo](dateformattinginfo.md)

### <a name="isrtl"></a>Istrtl

Palauttaa arvon TRUE, jos kieli on oikealta vasemmalle.

**Tyyppi**: `boolean`

### <a name="languageid"></a>languageId

Nykyisen käyttäjän kieli tunnus.

**Tyyppi**: `number`

### <a name="numberformattinginfo"></a>kohteen Numberformatttinginfo

Palvelimesta noudetut luku muotoilu tiedot.

**Tyyppi**: [numberformatttinginfo](numberformattinginfo.md)

### <a name="securityroles"></a>securityRoles

Nykyiset käyttäjä roolit.

**Tyyppi**: `string[]`

### <a name="userid"></a>Käyttäjä tunnus

Nykyisen käyttäjän tunnus.

**Tyyppi**: `string`

### <a name="username"></a>Käyttäjätunnus

Nykyisen käyttäjän käyttäjä nimi.

**Tyyppi**: `string`

## <a name="methods"></a>Menetelmiä

|Menetelmä | Kuvaus | 
| ------|-------------|
|[getTimeZoneOffsetMinutes](usersettings/gettimezoneoffsetminutes.md)|[!INCLUDE [gettimezoneoffsetminutes-description](usersettings/includes/gettimezoneoffsetminutes-description.md)]|

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)