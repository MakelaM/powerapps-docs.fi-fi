---
title: Käyttäjä-funktio | Microsoft Docs
description: PowerAppsin Käyttäjä-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 69da2bbdadc40421e9962de73d531b6c19554eeb
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983484"
---
# <a name="user-function-in-powerapps"></a>PowerAppsin Käyttäjä-funktio
Palauttaa tietoja nykyisestä käyttäjästä.

## <a name="description"></a>Kuvaus
**Käyttäjä**-funktio palauttaa [tietueen](../working-with-tables.md#records) nykyisen käyttäjän tietoja:

| Ominaisuus | Kuvaus |
| --- | --- |
| **User().Email** |Nykyisen käyttäjän sähköpostiosoite. |
| **User().FullName** |Nykyisen käyttäjän koko nimi, mukaan lukien etu- ja sukunimet. |
| **User().Image** |Nykyisen käyttäjän kuva. Tämä on kuva-URL muodossa "blob:*identifier*". Määritä **[Kuva](../controls/control-image.md)** -ohjausobjektin **[Kuva](../controls/properties-visual.md)** -ominaisuudelle tämä arvo, jos haluat näyttää kuvan sovelluksessa. |

> [!NOTE]
> Palautetut tiedot koskevat PowerAppsin nykyistä käyttäjää.  Se vastaa ”Tili”-tietoja, jotka näytetään PowerAppsin soittimissa ja studiossa, jotka löytyvät muualta kuin laadituista sovelluksista.  Tämä ei välttämättä vastaa nykyisen käyttäjän tietoja Office 365:ssä tai muissa palveluissa.

## <a name="syntax"></a>Syntaksi
**User**()

## <a name="examples"></a>Esimerkkejä
Nykyisellä PowerApps-käyttäjällä on seuraavat tiedot:

* Koko nimi: **"John Doe"**
* Sähköpostiosoite: **"john.doe@contoso.com"**
* Kuva: ![](media/function-user/john-doe-picture.png) 

|       Kaava       |                                                                    Kuvaus                                                                    |                                                 Tulos                                                  |
|---------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
|     **User()**      |                                             Tietue PowerAppsin nykyisen käyttäjän kaikista tiedoista.                                             |    { FullName:&nbsp;"John Doe", Email:&nbsp;"john.doe@contoso.com", Image:&nbsp;"blob:1234...5678" }    |
|  **User().Email**   |                                                 Nykyisen PowerAppsin käyttäjän sähköpostiosoite.                                                  |                                         "john.doe@contoso.com"                                          |
| **User().FullName** |                                                   Nykyisen PowerAppsin käyttäjän koko nimi.                                                    |                                               ”John Doe”                                                |
|  **User().Image**   | Nykyisen PowerAppsin käyttäjän kuva-URL-osoite.  Määritä **Kuva**-ohjausobjektin **Kuva**-ominaisuudeksi tämä arvo voidaksesi näyttää kuvan sovelluksessa. | "blob:1234...5678"<br><br>Kun käytössä on **ImageControl.Image**:<br>![](media/function-user/john-doe-picture.png) |

