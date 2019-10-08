---
title: SaveData- ja LoadData-funktiot | Microsoft Docs
description: PowerAppsin SaveData- ja LoadData-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e716de7a3551e2195d3f3459540a6f68acb4fd51
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992279"
ms.PowerAppsDecimalTransform: true
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>SaveData- ja LoadData-funktiot PowerAppsissa
Tallentaa ja lataa uudelleen [kokoelman](../working-with-data-sources.md#collections).

## <a name="description"></a>Kuvaus
**SaveData**-funktio tallentaa valikoiman nimellä myöhempää käyttöä varten.  

**LoadData**-funktio lataa valikoiman uudelleen nimellä, joka tallennettiin aiemmin **SaveData**-funktiolla. Tämän funktion avulla ei voi ladata kokoelmaa toisesta lähteestä.  

Näiden funktioiden avulla voit parantaa sovelluksen käynnistämisen suoritus tehoa tallentamalla tiedot väli muistiin **[sovelluksessa. OnStart](../controls/control-screen.md#additional-properties)** -kaavassa ensimmäisellä suoritus tavalla ja lataamalla sitten paikallisen väli muistin uudelleen seuraavissa suorituksessa. Voit myös käyttää näitä funktioita [yksinkertaisten offline-](../offline-apps.md) toimintojen lisäämiseen sovellukseesi.

Et voi käyttää näitä funktioita selaimessa, kun sovellus on PowerApps Studio tai kun sovellusta suoritetaan verkko soittimessa. Jos haluat testata sovellustasi, suorita se PowerApps Mobilessa iPhonessa tai Android-laitteessa.

Käytettävissä olevan sovelluksen muistin määrä rajoittaa näitä funktioita, koska ne toimivat muistissa olevassa kokoelmassa. Käytettävissä oleva muisti voi vaihdella laitteen ja käyttö järjestelmän, PowerApps-soittimen käyttämän muistin sekä näyttöjen ja ohjaus objektien suhteen monimutkaisuuden mukaan. Jos tallennat enemmän kuin muutaman Mega tavun tietoja, testaa sovelluksesi odotettuja tilanteita laitteilla, joissa sovellusta odotetaan suoritettavaksi. Yleensä sinulla pitäisi olla 30 – 70 Mega tavua vapaata muistia.  

**LoadData** ei luo kokoelmaa; se vain täyttää olemassa olevan kokoelman. Sinun on ensin luotava oikeat [sarakkeet](../working-with-tables.md#columns) sisältävä kokoelma **[Collect](function-clear-collect-clearcollect.md)** -funktiolla. Ladatut tiedot lisätään kokoelmaan. Käytä **[Clear](function-clear-collect-clearcollect.md)** -funktiolla First-kenttää, jos haluat aloittaa tyhjällä kokoelmalla.

Tallennustila on salattu ja sijaitsee erillään laitteesta ja eristettynä muilta käyttäjiltä ja muilta sovelluksilta.

## <a name="syntax"></a>Syntaksi
**SaveData**( *Collection*; *Name* )<br>**LoadData**( *Collection*; *Name* [; *IgnoreNonexistentFile* ])

* *Collection* – Pakollinen.  Tallennettava tai ladattava kokoelma.
* *Name* – Pakollinen.  Tallennustilan nimi. Käytä samaa nimeä saman tietojoukon tallentamiseen ja lataamiseen. Nimi-tilaa ei jaeta muiden sovellusten tai käyttäjien kanssa.
* *IgnoreNonexistentFile* – Valinnainen. Totuusarvo (**true**/**false**), joka ilmaisee, näyttääkö vai ohittaako **LoadData**-funktio virheitä, kun se ei löydä vastaavaa tiedostoa. Jos määrität **false**, virheet näytetään. Jos määrität **true**, virheet ohitetaan, mikä on hyödyllistä offline-tilassa tapahtuvia tilanteita varten. **SaveData** voi luoda tiedoston, jos laite on offline-tilassa (toisin sanoen, jos **Connection.Connected**-tila on **false**).

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If (yhteys. Connected; ClearCollect (LocalTweets; Twitter. SearchTweet ("PowerApps"; {maxResults: 100})); LoadData (LocalTweets; "twiitit"; True))** |Jos laite on yhdistetty, lataa LocalTweets-kokoelma Twitter-palvelusta. Lataa kokoelma muussa tapauksessa paikallisesta tiedostovälimuistista. |Sisältö hahmonnetaan riippumatta siitä, onko laite online- vai offline-tilassa. |
| **SaveData(LocalTweets; ”Tweets”)** |Tallenna LocalTweets-kokoelma laitteen paikalliseen tiedostovälimuistiin. |Tiedot tallennetaan paikallisesti, jotta **LoadData** voi ladata sen kokoelmaan. |

