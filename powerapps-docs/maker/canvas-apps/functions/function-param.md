---
title: Download-, Launch- ja Param-funktiot | Microsoft Docs
description: PowerAppsin Download-, Launch- ja Param-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 146372c723df6089890100abd67d1175ba4b4a04
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31828746"
---
# <a name="download-launch-and-param-functions-in-powerapps"></a>PowerAppsin Download-, Launch- ja Param-funktiot
Lataa tai avaa verkkosivun tai sovelluksen parametreilla.  

## <a name="description"></a>Kuvaus
**Download**-funktio lataa tiedoston verkosta paikalliseen laitteeseen.  Käyttäjältä pyydetään tiedoston tallennussijainti.  **Download** palauttaa tiedoston paikallisen tallennussijainnin merkkijonona.  

**Launch**-funktio avaa verkkosivun tai sovelluksen.  Tämä funktio voi valinnaisesti välittää sovellukselle parametreja.  

**Param**-funktio noutaa sovellukselle avaamisen yhteydessä välitetyn parametrin.  Jos nimettyä parametria ei välitetty, **Param** palauttaa *tyhjän*.

## <a name="syntax"></a>Syntaksi
**Download**( *Osoite* )

* *Osoite* – Pakollinen.  Ladattavan verkkoresurssin osoite.

**Launch**( *Osoite* [, *ParametrinNimi1*, *ParametrinArvo1*, ... ] )

* *Osoite* – Pakollinen.  Avattavan verkkosivun osoite tai sovelluksen tunnus.
* *ParametrinNimet* – Valinnaisia.  Parametrin nimi.
* *ParametrinArvot* – Valinnaisia.  Vastaavat parametriarvot, jotka välitetään sovellukselle tai verkkosivulle.

**Param**( *ParametrinNimi* )

* *ParametrinNimi* – Pakollinen.  Sovellukselle välitettävän parametrin nimi.

