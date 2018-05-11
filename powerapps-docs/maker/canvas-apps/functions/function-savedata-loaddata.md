---
title: SaveData- ja LoadData-funktiot | Microsoft Docs
description: PowerAppsin SaveData- ja LoadData-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: aa62882841ee4d585720a2241dff8b9f35c88059
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>SaveData- ja LoadData-funktiot | Microsoft Docs
Tallentaa ja lataa uudelleen [kokoelman](../working-with-data-sources.md#collections).

## <a name="description"></a>Kuvaus
**SaveData**-funktio tallentaa valikoiman nimellä myöhempää käyttöä varten.  

**LoadData**-funktio lataa valikoiman uudelleen nimellä, joka tallennettiin aiemmin **SaveData**-funktiolla. Tämän funktion avulla ei voi ladata kokoelmaa toisesta lähteestä.  

**LoadData** ei luo kokoelmaa; se vain täyttää olemassa olevan kokoelman. Joudut ensin luomaan kokoelman oikeilla [sarakkeilla](../working-with-tables.md#columns) **[Kerää](function-clear-collect-clearcollect.md)**-toiminnon avulla.

Tallennustila on salattu ja sijaitsee erillään laitteesta ja eristettynä muilta käyttäjiltä ja muilta sovelluksilta.  

## <a name="syntax"></a>Syntaksi
**SaveData**( *Collection*, *Name* )<br>**LoadData**( *Collection*, *Name* [, *IgnoreNonexistentFile* ])

* *Kokoelma* – Pakollinen.  Tallennettava tai ladattava kokoelma.
* *Nimi* – Pakollinen.  Tallennustilan nimi. Joudut käyttämään samaa nimeä saman tietojoukon tallentamiseen ja lataamiseen. Nimi-tilaa ei jaeta muiden sovellusten tai käyttäjien kanssa.
* *IgnoreNonexistentFile* – valinnainen. Totuusarvo (**true**/**false**), joka ilmaisee, näyttääkö vai ohittaako **LoadData**-funktio virheitä, kun se ei löydä vastaavaa tiedostoa. Jos määrität **false**, virheet näytetään. Jos määrität **true**, virheet ohitetaan, mikä on hyödyllistä offline-tilassa tapahtuvia tilanteita varten. **SaveData** voi luoda tiedoston, jos laite on offline-tilassa (toisin sanoen, jos **Connection.Connected**-tila on **false**).

## <a name="examples"></a>Esimerkkejä
| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If(Connection.Connected, ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100})),LoadData(LocalTweets, "Tweets", true))** |Jos laite on yhdistetty, lataa LocalTweets-kokoelma Twitter-palvelusta; lataa kokoelma muussa tapauksessa paikallisesta tiedostovälimuistista. |Sisältö hahmonnetaan riippumatta siitä, onko laite online- vai offline-tilassa. |
| **SaveData(LocalTweets, "Tweets")** |Tallenna LocalTweets-kokoelma paikalliseen tiedostovälimuistiin laitteessa. |Tiedot tallennetaan paikallisesti, jotta **LoadData** voi ladata sen kokoelmaan. |

