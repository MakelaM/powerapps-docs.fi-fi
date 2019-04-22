---
title: Download-, Launch- ja Param-funktiot | Microsoft Docs
description: Viitetiedot, mukaan lukien syntaksi ja esimerkkejä latauksen, käynnistämisen ja Param-funktioiden pohjaan perustuvat sovellukset
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4a53d8c20bd4b7784cb94daa574682c041f104ea
ms.sourcegitcommit: 0267e58b305f9fb0a4b32130fb149cd6e34b3354
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/22/2019
ms.locfileid: "59993776"
---
# <a name="download-launch-and-param-functions-in-canvas-apps"></a>Latauksen, käynnistämisen ja Param-funktioiden pohjaan perustuvat sovellukset
Lataa tai avaa verkkosivun tai sovelluksen parametreilla.  

## <a name="description"></a>Kuvaus
**Download**-funktio lataa tiedoston verkosta paikalliseen laitteeseen. Käyttäjältä pyydetään tiedoston tallennussijainti.  **Download** palauttaa tiedoston paikallisen tallennussijainnin merkkijonona.  

**Launch**-funktio avaa verkkosivun tai sovelluksen.  Tämä funktio voi valinnaisesti välittää sovellukselle parametreja.

Internet Explorerin ja Microsoft Edge **Käynnistä** -funktio avaa sivustoon tai sovellukseen vain, jos sen tietoturva-asetukset ovat samat tai suurempi kuin ne sovelluksen, joka sisältää funktio. Jos esimerkiksi lisäät **Käynnistä** funktiota sovelluksen, joka suoritetaan **Luotetut sivustot** suojaus vyöhykkeen, varmista, että sivustoon tai sovellukseen, jotka haluat avata-funktio on **Luotetut sivustojen** tai **paikallisen lähiverkon** aikavyöhykkeen (ei **rajoitetut sivustojen**). Lisätietoja: [Internet Explorer 11 suojaus ja tietosuoja-asetusten muuttaminen](https://support.microsoft.com/en-us/help/17479/windows-internet-explorer-11-change-security-privacy-settings).  

**Param**-funktio noutaa sovellukselle avaamisen yhteydessä välitetyn parametrin. Jos nimettyä parametria ei välitetty, **Param** palauttaa *tyhjän*.

## <a name="syntax"></a>Syntaksi
**Download**( *Address* )

* *Address* – Pakollinen.  Ladattavan verkkoresurssin osoite.

**Launch**( *Address* [, *ParameterName1*, *ParameterValue1*, ... ] )

* *Address* – Pakollinen.  Avattavan verkkosivun osoite tai sovelluksen tunnus.
* *ParameterName(s)* – Valinnaisia.  Parametrin nimi.
* *ParameterValue(s)* – Valinnaisia.  Vastaavat parametriarvot, jotka välitetään sovellukselle tai verkkosivulle.

**Param**( *ParameterName* )

* *ParameterName* – Pakollinen.  Sovellukselle välitettävän parametrin nimi.

