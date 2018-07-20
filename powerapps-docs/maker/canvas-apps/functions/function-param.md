---
title: Download-, Launch- ja Param-funktiot | Microsoft Docs
description: PowerAppsin Download-, Launch- ja Param-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: f2af4fef413aa5502c57e7158d9efdddd36757c9
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39021868"
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

