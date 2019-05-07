---
title: IfError-funktio | Microsoft Docs
description: PowerAppsin IfError-funktion viitetietoja, kuten syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/21/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1bf9f3cf075441dd3264b5a2f6533671d2e08654
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61562809"
ms.PowerAppsDecimalTransform: true
---
# <a name="iferror-function-in-powerapps"></a>IfError-funktio PowerAppsissa
Havaitsee virheitä ja tarjoaa vaihtoehtoisen arvon tai suorittaa toiminnon.

## <a name="description"></a>Kuvaus
> [!NOTE]
> Tämä funktio on osa kokeellista ominaisuutta, ja se voi muuttua.  Tässä kuvattu toiminta on käytettävissä vain, kun *Kaavatason virheiden hallinta* -ominaisuus on käytössä.  Tämä on sovellustason asetus, jonka oletusarvo on pois käytöstä.  Ota tämä ominaisuus käyttöön siirtymällä *Tiedosto*-välilehden vasemmalla olevan valikon kohtaan *Sovellusasetukset* ja valitsemalla *Kokeiluominaisuudet*.  Palautteesi on meille erittäin arvokasta. Kerro meille mielipiteesi [PowerApps-yhteisön keskustelupalstoilla](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

**IfError**-funktio testaa virhearvot jokaisesta argumentista järjestyksessä. Se pysähtyy, kun ensimmäinen ei-virhearvo löydetään.  Ei-virhearvon jälkeen löydetyt argumentit ohitetaan eikä niitä arvioida.

Käytä **IfError**-funktiota virhearvojen korvaamiseen kelvollisella arvolla.  Jos on esimerkiksi mahdollista, että käyttäjän syöte voi aiheuttaa jakolaskun nollalla, korvaa se 0:lla tai muulla kelvollisella, sovellukseen sopivalla arvolla, jotta tuotantovirran laskutoimituksia voidaan suorittaa.

Käytä **IfError**-funktiota [toimintakaavoissa](../working-with-formulas-in-depth.md) toimintojen suorittamiseen, tulosten mahdollisten virheiden tarkistamiseen sekä tarvittaessa lisätoimenpiteiden suorittamiseen tai virheviestin näyttämiseen käyttäjälle [**Notify**](function-showerror.md)-funktiolla.

Jos kaikki argumentit funktioon **IfError** aiheuttavat virheen, viimeisen argumentin arvo palautetaan (se on virhearvo). 

## <a name="syntax"></a>Syntaksi
**IfError**( *Value*; *Fallback1* [; *Fallback2*; ... ] )

* *Value* – Pakollinen. Kaavat virhearvojen testaamiseksi. 
* *Fallback(s)* – Pakollinen. Arvioitavat kaavat ja palautettavat arvot, jos edelliset argumentit palauttivat virheen.  *Fallback* argumentit arvioidaan järjestyksessä, kunnes ei-virhearvo löydetään.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **IfError( 1; 2 )** |Ensimmäinen argumentti ei ole virhe.  Se palautetaan, eikä seuraavia argumentteja arvioida.   | 1 |
| **IfError( 1/0; 2 )** | Ensimmäinen argumentti palauttaa virhearvon (jakolasku nollalla).  Toinen argumentti arvioidaan, jolloin syntyy ei-virhearvo, joka palautetaan. | 2 | 
| **IfError( 1/0; Notify( "Sisäinen virhe"; NotificationType.Error ) )** | Ensimmäinen argumentti palauttaa virhearvon (jakolasku nollalla).  Toinen argumentti arvioidaan, ja käyttäjälle näytetään viesti.  **IfError**-funktion palautusarvo on **Notify**-funktion palautusarvo, joka on pakotettu samantyyppiseksi kuin ensimmäinen argumentti funktioon **IfError** (luku). | 1 |
| **IfError( 1/0; 1/0; 2; 1/0; 3 )** | Ensimmäinen argumentti palauttaa virhearvon (jakolasku nollalla).  Toinen argumentti arvioidaan. Myös tästä syntyy virhearvo (toinen jakolasku nollalla).  Kolmas argumentti arvioidaan. Tämä ei tuota palautettavaa virhearvoa.  Neljäs ja viides argumentti ohitetaan.  | 2 |

### <a name="step-by-step"></a>Vaihe vaiheelta

1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimeksi **TextInput1**, jos tämä ei ole sen oletusnimi.

2. Lisää **[Nimi](../controls/control-text-box.md)**-ohjausobjekti ja anna sille nimeksi **Label1**, jos tämä ei ole sen oletusnimi.

3. Määritä **Label1**:n **Text**-ominaisuuden kaavaksi:

    **IfError( Value( TextInput1.Text ); -1 )**

4. Kirjoita **TextInput1**-kohtaan **1234**.  

    Label1 näyttää arvon **1234**, koska tämä on kelvollinen syöte Value-funktioon.

5. Kirjoita **TextInput1**-kohtaan **ToInfinity**.

    Label1 näyttää arvon **-1**, koska tämä ei ole kelvollinen syöte Value-funktioon.  Jos Value-funktiota ei rivitettäisi IfError-funktion kanssa, otsikko ei näyttäisi arvoa, koska virhearvoa kohdellaan *tyhjänä*. 

