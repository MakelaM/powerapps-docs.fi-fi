---
title: Download-, Launch- ja Param-funktiot | Microsoft Docs
description: Viite tiedot, mukaan lukien syntaksi ja esimerkit, lataus-, käynnistys-ja parametri funktioille kangas sovelluksissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c6fb3c5ef002ed0355cc8061603e4f4b1f438e6e
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992485"
ms.PowerAppsDecimalTransform: true
---
# <a name="download-launch-and-param-functions-in-canvas-apps"></a>Lataa-, Launch-ja PARAM-Funktiot kangas sovelluksissa
Lataa tai avaa verkkosivun tai sovelluksen parametreilla.  

## <a name="description"></a>Kuvaus
**Download**-funktio lataa tiedoston verkosta paikalliseen laitteeseen. Käyttäjältä pyydetään tiedoston tallennussijainti.  **Download** palauttaa tiedoston paikallisen tallennussijainnin merkkijonona.  

**Launch**-funktio avaa verkkosivun tai sovelluksen.  Tämä funktio voi valinnaisesti välittää sovellukselle parametreja.

Internet Explorerissa ja Microsoft Edgessä **Launch** -funktiolla avataan verkkosivusto tai sovellus vain, jos sen suojaus asetukset ovat samat tai suuremmat kuin sen sovelluksen, joka sisältää-ominaisuuden. Jos esimerkiksi lisäät **Launch** -funktiolla sovellukseen, joka suoritetaan **Luotetut sivustot** -suojaus vyöhykkeellä, varmista, että verkkosivusto tai sovellus, jonka haluat sen avaavan, on **Luotetut sivustot** -tai **Paikallinen intranet** -vyöhykkeellä (ei  **Rajoitetut sivustot**). Lisätietoja: [Muuta Internet Explorer 11: n suojaus-ja tieto suoja-asetuksia](https://support.microsoft.com/en-us/help/17479/windows-internet-explorer-11-change-security-privacy-settings).  

**Param**-funktio noutaa sovellukselle avaamisen yhteydessä välitetyn parametrin. Jos nimettyä parametria ei välitetty, **Param** palauttaa *tyhjän*.

## <a name="syntax"></a>Syntaksi
**Download**( *Address* )

* *Address* – Pakollinen.  Ladattavan verkkoresurssin osoite.

**Launch**( *Address* [; *ParameterName1*; *ParameterValue1*; ... ] )

* *Address* – Pakollinen.  Avattavan verkkosivun osoite tai sovelluksen tunnus.
* *ParameterName(s)* – Valinnaisia.  Parametrin nimi.
* *ParameterValue(s)* – Valinnaisia.  Vastaavat parametriarvot, jotka välitetään sovellukselle tai verkkosivulle.

**Param**( *ParameterName* )

* *ParameterName* – Pakollinen.  Sovellukselle välitettävän parametrin nimi.

