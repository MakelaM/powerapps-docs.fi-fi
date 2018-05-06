---
title: User-funktio | Microsoft Docs
description: PowerAppsin User-funktion viitetiedot, mukaan lukien syntaksi
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2016
ms.author: gregli
ms.openlocfilehash: 2053f69146bcd952f61916ef9e41150791a243a5
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="user-function-in-powerapps"></a>PowerAppsin User-funktio
Palauttaa tietoja nykyisestä käyttäjästä.

## <a name="description"></a>Kuvaus
**User**-funktio palauttaa [tietueen](../working-with-tables.md#records) nykyisen käyttäjän tietoja:

| Ominaisuus | Kuvaus |
| --- | --- |
| **User().Email** |Nykyisen käyttäjän sähköpostiosoite. |
| **User().FullName** |Nykyisen käyttäjän koko nimi, mukaan lukien etu-ja sukunimet. |
| **User().Image** |Nykyisen käyttäjän kuva. Tämä on kuvan URL muodossa "blob:*identifier*". Määritä **[kuva](../controls/control-image.md)**-ohjausobjektin **[kuva](../controls/properties-visual.md)**-ominaisuudelle tämä arvo, jos haluat näyttää kuvan sovelluksessa. |

> [!NOTE]
> Palautetut tiedot koskevat PowerAppsin nykyistä käyttäjää.  Se vastaa ”tili”-tietoja, jotka näytetään PowerAppsin soittimissa ja studiossa, jotka löytyvät muualta kuin laadituista sovelluksista.  Tämä ei välttämättä vastaa nykyisen käyttäjän tietoja Office 365: ssä tai muissa palveluissa.

## <a name="syntax"></a>Syntaksi
**User**()

## <a name="examples"></a>Esimerkkejä
Nykyisellä PowerApps-käyttäjällä on seuraavat tiedot:

* Koko nimi: **”John Doe”**
* Sähköpostiosoite: **"john.doe@contoso.com"**
* Kuva: ![](media/function-user/john-doe-picture.png) 

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **User()** |Tietue PowerAppsin nykyisen käyttäjän kaikista tiedoista. |{ FullName:&nbsp;"John Doe", Email:&nbsp;"john.doe@contoso.com", Image:&nbsp;"blob:1234...5678" } |
| **User().Email** |Nykyisen PowerAppsin käyttäjän sähköpostiosoite. |"john.doe@contoso.com" |
| **User().FullName** |Nykyisen PowerAppsin käyttäjän koko nimi. |”John Doe” |
| **User().Image** |Nykyisen PowerAppsin käyttäjän kuvan URL-osoite.  Määritä **kuva**-ohjausobjektin **kuva**-ominaisuudeksi tämä arvo voidaksesi näyttää kuvan sovelluksessa. |"blob:1234...5678"<br><br>Kun käytössä on **ImageControl.Image**:<br>![](media/function-user/john-doe-picture.png) |

