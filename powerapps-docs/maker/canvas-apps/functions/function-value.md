---
title: Value-funktio | Microsoft Docs
description: PowerAppsin Value-funktion viitetiedot, mukaan lukien syntaksi
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
ms.openlocfilehash: 1e54072771bf92dc6237620cfbd260cd4af55e22
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63321826"
---
# <a name="value-function-in-powerapps"></a>PowerAppsin Value-funktio
Muuntaa merkkijonon luvuksi.

## <a name="description"></a>Kuvaus
**Value**-funktio muuntaa numeromerkkejä sisältävän tekstimerkkijonon lukuarvoksi. Käytä tätä toimintoa, kun haluat suorittaa laskutoimituksia luvuilla, jotka käyttäjä on lisännyt tekstinä.

Eri kielissä merkit **,** ja **.** tulkitaan eri tavalla.  Oletusarvoisesti teksti tulkitaan nykyisen käyttäjän kielellä.  Voit määrittää käytettävän kielen kielitunnisteella käyttämällä samoja kielitunnisteita, jotka **[Language](function-language.md)** funktio palauttaa.

Merkkijonon muotoa koskevat huomautukset:

* Merkkijonossa voi olla etuliitteenä nykyisen kielen mukainen valuuttasymboli.  Valuuttasymboli ohitetaan.  Muiden kielten valuuttasymboleja ei jätetä huomioimatta.
* Merkkijonon loppuun voi sisältyä prosenttimerkki ( **%** ), joka ilmaisee, että kyseessä on prosenttiluku.  Luku jaetaan sadalla ennen tuloksen palauttamista.  Prosentti- ja valuuttasymboleita ei voi sekoittaa.
* Merkkijonossa voidaan käyttää tieteellistä merkintätapaa, jossa 12 x 10<sup>3</sup> ilmaistaan muodossa "12e3".

Jos luku ei ole oikeassa muodossa, **Value** palauttaa *tyhjän*.

Käytä funktioita [**DateValue**](function-datevalue-timevalue.md), [**TimeValue**](function-datevalue-timevalue.md) ja [**DateTimeValue**](function-datevalue-timevalue.md) päivä- ja aika-arvojen muuntamiseen.

## <a name="syntax"></a>Syntaksi
**Value**( *String* [, *LanguageTag* ] )

* *String* vaaditaan. Numeeriseksi arvoksi muunnettava merkkijono.
* *LanguageTag* – valinnainen.  Kielitunniste, jonka perusteella merkkijono jäsennetään.  Jos sitä ei syötetä, käytetään nykyisen käyttäjän kieltä.

## <a name="examples"></a>Esimerkkejä
Käyttäjä, joka suorittaa nämä kaavat, sijaitsee Yhdysvalloissa ja on valinnut kielekseen englannin.  **Language**-funktio palauttaa tuloksen "en-US".

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **Value( "123.456" )** |Käytetään oletuskieltä "en-US", jossa desimaalierottimena käytetään pistettä. |123.456 |
| **Value( "123.456", "es-ES" )** |"es-ES" on kielitunniste Espanjassa käytetylle espanjan kielelle.  Espanjassa tuhaterottimena käytetään pistettä. |123456 |
| **Value( "123,456" )** |Käytetään oletuskieltä "en-US", jossa tuhaterottimena käytetään pilkkua. |123456 |
| **Value( "123,456", "es-ES" )** |"es-ES" on kielitunniste Espanjassa käytetylle espanjan kielelle.  Espanjassa desimaalierottimena käytetään pilkkua. |123.456 |
| **Value( "12.34%" )** |Merkkijonon lopussa oleva prosenttimerkki ilmaisee, että tämä on prosenttiluku. |0.1234 |
| **Value( "$ 12.34" )** |Nykyisen kielen valuuttasymboli ohitetaan. |12.34 |
| **Value( "24e3" )** |Luvun 12 x 10<sup>3</sup> tieteellinen muoto. |24000 |

