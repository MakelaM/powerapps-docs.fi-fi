---
title: SaveData- ja LoadData-funktiot | Microsoft Docs
description: PowerAppsin SaveData- ja LoadData-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 26fd26df5b0d2e083288a8a4be63f3ed9d46c610
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39014416"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>SaveData- ja LoadData-funktiot PowerAppsissa
Tallentaa ja lataa uudelleen [kokoelman](../working-with-data-sources.md#collections).

## <a name="description"></a>Kuvaus
**SaveData**-funktio tallentaa valikoiman nimellä myöhempää käyttöä varten.  

**LoadData**-funktio lataa valikoiman uudelleen nimellä, joka tallennettiin aiemmin **SaveData**-funktiolla. Tämän funktion avulla ei voi ladata kokoelmaa toisesta lähteestä.  

**LoadData** ei luo kokoelmaa; se vain täyttää olemassa olevan kokoelman. Sinun on ensin luotava oikeat [sarakkeet](../working-with-tables.md#columns) sisältävä kokoelma **[Collect](function-clear-collect-clearcollect.md)**-funktiolla.

Tallennustila on salattu ja sijaitsee erillään laitteesta ja eristettynä muilta käyttäjiltä ja muilta sovelluksilta.  

## <a name="syntax"></a>Syntaksi
**SaveData**( *Kokoelma*, *Nimi* )<br>**LoadData**( *Kokoelma*, *Nimi* [, *IgnoreNonexistentFile* ])

* *Kokoelma* – Pakollinen.  Tallennettava tai ladattava kokoelma.
* *Nimi* – Pakollinen.  Tallennustilan nimi. Käytä samaa nimeä saman tietojoukon tallentamiseen ja lataamiseen. Nimi-tilaa ei jaeta muiden sovellusten tai käyttäjien kanssa.
* *IgnoreNonexistentFile* – Valinnainen. Totuusarvo (**true**/**false**), joka ilmaisee, näyttääkö vai ohittaako **LoadData**-funktio virheitä, kun se ei löydä vastaavaa tiedostoa. Jos määrität **false**, virheet näytetään. Jos määrität **true**, virheet ohitetaan, mikä on hyödyllistä offline-tilassa tapahtuvia tilanteita varten. **SaveData** voi luoda tiedoston, jos laite on offline-tilassa (toisin sanoen, jos **Connection.Connected**-tila on **false**).

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If(Connection.Connected, ClearCollect(LocalTweets, Twitter.SearchTweet(”PowerApps”, {maxResults: 100})),LoadData(LocalTweets, ”Tweets”, true))** |Jos laite on yhdistetty, lataa LocalTweets-kokoelma Twitter-palvelusta. Lataa kokoelma muussa tapauksessa paikallisesta tiedostovälimuistista. |Sisältö hahmonnetaan riippumatta siitä, onko laite online- vai offline-tilassa. |
| **SaveData(LocalTweets, ”Tweets”)** |Tallenna LocalTweets-kokoelma laitteen paikalliseen tiedostovälimuistiin. |Tiedot tallennetaan paikallisesti, jotta **LoadData** voi ladata sen kokoelmaan. |

