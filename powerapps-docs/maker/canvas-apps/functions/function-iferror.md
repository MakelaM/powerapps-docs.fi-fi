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
ms.openlocfilehash: 63a837eff2944569f5f66223690b11ddcfd399f6
ms.sourcegitcommit: aa9f78c304fe46922aecfe3b3fadb6bda72dfb23
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/24/2019
ms.locfileid: "66215918"
---
# <a name="iferror-function-in-powerapps"></a>IfError-funktio PowerAppsissa

Havaitsee virheitä ja tarjoaa vaihtoehtoisen arvon tai suorittaa toiminnon.

## <a name="description"></a>Kuvaus

> [!NOTE]
> Tämä funktio on osa kokeellista ominaisuutta, ja se voi muuttua. Tässä aiheessa kuvatut toiminta on käytettävissä vain, kun *kaavatason virheiden hallinta* ominaisuus on otettu käyttöön. Sovelluksen tasolla-asetus on käytössä oletusarvoisesti. Jos haluat ottaa tämän ominaisuuden käyttöön, Avaa *tiedoston* -välilehden *sovellusasetukset* vasemmalla olevan valikon ja valitse sitten *kokeelliset ominaisuudet*. Palautteesi on meille erittäin arvokasta. Kerro meille mielipiteesi [PowerApps-yhteisön keskustelupalstoilla](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

**IfError** funktio Testaa yhden tai useita arvoja, kunnes se etsii virhe tuloksen. Jos funktio löytää virheen, funktio palauttaa vastaava arvo. Muussa tapauksessa funktio palauttaa oletusarvon. Kummassakin tapauksessa funktio saattaa palauttaa näytettävä merkkijono, laskettava kaava tai muunlainen tuloksen. **IfError** funktio muistuttaa **Jos** funktio: **IfError** Testaa virheitä, kun **Jos** Testaa **true**.

Käytä **IfError** virhearvojen korvaamiseen kelvollisten arvojen kanssa. Käytä tätä funktiota esimerkiksi, jos käyttäjän syöte voi aiheuttaa jakolaskun nollalla. Luoda kaavan, joka korvaa tuloksen 0 tai toisen arvon, joka soveltuu sovelluksesi, jotta tuotantovirran laskutoimituksia voidaan suorittaa. Kaava voi olla yksinkertaisesti tässä esimerkissä:

```powerapps-dot
IfError( 1/x, 0 )
```

Jos arvo **x** ei ole nolla, kaava palauttaa **1 / x**. Muussa tapauksessa **1 / x** tuottaa virheen ja kaava palauttaa arvon 0 sen sijaan.

Käytä **IfError** - [toimintakaavoissa](../working-with-formulas-in-depth.md) suorittaa toiminnon ja tarkista virhe ennen tekemistä lisätoimintoja, kuten tätä mallia:

```powerapps-dot
IfError(
    Patch( DS1, ... ), Notify( "problem in the first action" ),
    Patch( DS2, ... ), Notify( "problem in the second action" )
)
```

Jos ensimmäisen patch havaitsee ongelma, ensimmäinen **Ilmoita** suoritetaan, ei enää käsittelyn ilmenee, ja toinen patch ei toimi. Jos ensimmäisen patch onnistuu, toinen patch suoritetaan ja, jos se havaitsee ongelma, toinen **Ilmoita** suoritetaan.

Jos kaavan ei löydä virheitä ja olet määrittänyt valinnainen *oletustulos* argumentti, kaava palauttaa arvo, jonka määritit argumentille. Jos et ole määrittänyt argumentille kaava ei löydä virheitä, kaava palauttaa viimeisimmän *arvo* argumentti arvioidaan.

## <a name="syntax"></a>Syntaksi

**IfError**( *arvo1*, *Fallback1* [, *arvo2*, *Fallback2*,... [, *Oletustulos* ]])

* *Arvo(t)* – pakollinen. Kaavat virhearvojen testaamiseksi.
* *Fallback(s)* – Pakollinen. Arvioitavat kaavat ja palautettavat Jos vastaavaa arvot *arvo* argumentit palauttivat virheen.
* *DefaultResult* – Valinnainen.  Kaavat, jotka arvioidaan, jos kaavaa ei löydä virheitä.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **IfError( 1, 2 )** |Ensimmäinen argumentti ei ole virhe. Funktio on ei tarkista virheitä ja palautusarvo oletusasetusta. Funktio palauttaa viimeisimmän *arvo* argumentti arvioidaan.   | 1 |
| **IfError( 1/0, 2 )** | Ensimmäinen argumentti palauttaa virhearvon (jakolasku nollalla). Funktio arvioi toinen argumentti, ja palauttaa tuloksen. | 2 |
| **IfError( 1/0, Notify( "Sisäinen virhe", NotificationType.Error ) )** | Ensimmäinen argumentti palauttaa virhearvon (jakolasku nollalla). Funktio arvioi toinen argumentti ja ilmoittaa käyttäjälle. **IfError**-funktion palautusarvo on **Notify**-funktion palautusarvo, joka on pakotettu samantyyppiseksi kuin ensimmäinen argumentti funktioon **IfError** (luku). | 1 |
| **IfError (1, 2, 3, 4, 5)** | Ensimmäinen argumentti ei ole virhe, joten toiminto ei arvioida, että argumentille vastaava fallback. Kolmas argumentti ei virheen joko, joten toiminto ei arvioida, että argumentille vastaava fallback. Viidennen argumentin on ei ole vastaavaa fallback ja oletusarvon tulos. Funktio palauttaa tuloksen, koska kaavassa on virheitä. | 5 |

### <a name="step-by-step"></a>Vaihe vaiheelta

1. Lisää **[Tekstisyöte](../controls/control-text-input.md)**-ohjausobjekti ja anna sille nimeksi **TextInput1**, jos tämä ei ole sen oletusnimi.

2. Lisää **[Nimi](../controls/control-text-box.md)**-ohjausobjekti ja anna sille nimeksi **Label1**, jos tämä ei ole sen oletusnimi.

3. Määritä **Label1**:n **Text**-ominaisuuden kaavaksi:

    **IfError( Value( TextInput1.Text ), -1 )**

4. Kirjoita **TextInput1**-kohtaan **1234**.  

    Label1 näyttää arvon **1234**, koska tämä on kelvollinen syöte Value-funktioon.

5. Kirjoita **TextInput1**-kohtaan **ToInfinity**.

    Label1 näyttää arvon **-1**, koska tämä ei ole kelvollinen syöte Value-funktioon.  Jos Value-funktiota ei rivitettäisi IfError-funktion kanssa, otsikko ei näyttäisi arvoa, koska virhearvoa kohdellaan *tyhjänä*. 

