---
title: SaveData- ja LoadData-funktiot | Microsoft Docs
description: PowerAppsin SaveData- ja LoadData-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3fb23fec6f6885a55b054889b90fed0c5efafd5e
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61520486"
---
# <a name="savedata-and-loaddata-functions-in-powerapps"></a>SaveData- ja LoadData-funktiot PowerAppsissa
Tallentaa ja lataa uudelleen [kokoelman](../working-with-data-sources.md#collections).

## <a name="description"></a>Kuvaus
**SaveData**-funktio tallentaa valikoiman nimellä myöhempää käyttöä varten.  

**LoadData**-funktio lataa valikoiman uudelleen nimellä, joka tallennettiin aiemmin **SaveData**-funktiolla. Tämän funktion avulla ei voi ladata kokoelmaa toisesta lähteestä.  

Näiden funktioiden avulla voit parantaa sovelluksen käynnistyksen suorituskykyä tallentamalla tietoja välimuistiin **[App.OnStart](../controls/control-screen.md#additional-properties)** kaavan ensimmäisen suorittamisen ja ladataan paikallisen välimuistin, myöhemmät suoritukset uudelleen. Näiden funktioiden avulla voit myös lisätä [yksinkertainen offline-ominaisuuksista](../offline-apps.md) sovellukseesi.

Et voi käyttää näitä funktioita selaimen sisällä, kun kehität sovellusta PowerApps Studio tai suoritettaessa sovelluksen web Playeristä. Sovelluksen testaaminen suorittaa sen PowerApps Mobilessa iPhone-laitteessa.

Nämä funktiot rajoittavat käytettävissä oleva sovellus muistin määrä, koska ne toimivat muistissa-kokoelma. Käytettävissä olevaa muistia voi vaihdella laite ja käyttöjärjestelmän ja PowerApps-toisto-ohjelmassa käyttämän muistin näyttöjä ja ohjausobjekteja sovelluksen monimutkaisuudesta riippuen. Jos tallennat useita megatavua, kokeile sovellusta odotettua skenaarioita, jolloin oletat sovellus suoritetaan laitteissa. Tulee yleisesti odottaa oltava 30 – 70 muistia megatavua.  

**LoadData** ei luo kokoelmaa; se vain täyttää olemassa olevan kokoelman. Sinun on ensin luotava oikeat [sarakkeet](../working-with-tables.md#columns) sisältävä kokoelma **[Collect](function-clear-collect-clearcollect.md)**-funktiolla. Ladatut tiedot lisätään kokoelmaa; Käytä **[Tyhjennä](function-clear-collect-clearcollect.md)** funktion ensin, jos haluat aloittaa tyhjä kokoelma.

Tallennustila on salattu ja sijaitsee erillään laitteesta ja eristettynä muilta käyttäjiltä ja muilta sovelluksilta.

## <a name="syntax"></a>Syntaksi
**SaveData**( *Collection*, *Name* )<br>**LoadData**( *Collection*, *Name* [, *IgnoreNonexistentFile* ])

* *Collection* – Pakollinen.  Tallennettava tai ladattava kokoelma.
* *Name* – Pakollinen.  Tallennustilan nimi. Käytä samaa nimeä saman tietojoukon tallentamiseen ja lataamiseen. Nimi-tilaa ei jaeta muiden sovellusten tai käyttäjien kanssa.
* *IgnoreNonexistentFile* – Valinnainen. Totuusarvo (**true**/**false**), joka ilmaisee, näyttääkö vai ohittaako **LoadData**-funktio virheitä, kun se ei löydä vastaavaa tiedostoa. Jos määrität **false**, virheet näytetään. Jos määrität **true**, virheet ohitetaan, mikä on hyödyllistä offline-tilassa tapahtuvia tilanteita varten. **SaveData** voi luoda tiedoston, jos laite on offline-tilassa (toisin sanoen, jos **Connection.Connected**-tila on **false**).

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **If(Connection.Connected, ClearCollect(LocalTweets, Twitter.SearchTweet("PowerApps", {maxResults: 100})), LoadData (LocalTweets, ”Tweets”, true))** |Jos laite on yhdistetty, lataa LocalTweets-kokoelma Twitter-palvelusta. Lataa kokoelma muussa tapauksessa paikallisesta tiedostovälimuistista. |Sisältö hahmonnetaan riippumatta siitä, onko laite online- vai offline-tilassa. |
| **SaveData(LocalTweets, ”Tweets”)** |Tallenna LocalTweets-kokoelma laitteen paikalliseen tiedostovälimuistiin. |Tiedot tallennetaan paikallisesti, jotta **LoadData** voi ladata sen kokoelmaan. |

