---
title: IfError-funktio | Microsoft Docs
description: PowerAppsin IfError-funktion viitetietoja, kuten syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/21/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 992ff4ccfae533908acac96efaa117a726198334
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71984728"
---
# <a name="iferror-function-in-powerapps"></a>IfError-funktio PowerAppsissa

Havaitsee virheitä ja tarjoaa vaihtoehtoisen arvon tai suorittaa toiminnon.

## <a name="description"></a>Kuvaus

> [!NOTE]
> Tämä funktio on osa kokeellista ominaisuutta, ja se voi muuttua. Toiminta, jota tämä aihe kuvaa, on käytettävissä vain, kun *kaava tason virheen hallinta* ominaisuus on käytössä. Tämä sovellus tason asetus on oletus arvon mukaan poissa käytöstä. Jos haluat ottaa tämän ominaisuuden käyttöön, avaa *tiedosto* -väli lehti, valitse vasemmalla olevasta valikosta *sovellus asetukset* ja valitse sitten *kokeelliset ominaisuudet*. Palautteesi on meille erittäin arvokasta. Kerro meille mielipiteesi [PowerApps-yhteisön keskustelupalstoilla](https://powerusers.microsoft.com/t5/Expressions-and-Formulas/bd-p/How-To).

**Iferror** -funktiolla testataan vähintään yhtä arvoa, kunnes se löytää virhe tuloksen. Jos funktio havaitsee virheen, funktio palauttaa vastaavan arvon. Muussa tapa uksessa funktio palauttaa oletus arvon. Kummassakin tapa uksessa funktio voi palauttaa näytettävän merkki jonon, kaavan arvioitavaksi tai toisen tulos muodon. **Iferror-** funktion kohde on **IF** -funktion kaltainen: **Iferor** Testaa virheitä, mutta **Jos** testit **True**.

Käytä **Iferror** -kohdetta, jos haluat korvata virhe arvot kelvollisella arvoilla. Käytä tätä funktiolla esimerkiksi, jos käyttäjän syöte saattaa aiheuttaa jakamisen nollalla. Luo kaava, joka korvaa tuloksen arvolla 0 tai muulla sovellukselle sopivalla arvolla, jotta loppu pään laskelmat voidaan jatkaa. Kaava voi olla yhtä yksinkertainen kuin tämä esimerkki:

```powerapps-dot
IfError( 1/x, 0 )
```

Jos **x** -arvo ei ole nolla, kaava palauttaa arvon **1/x**. Muussa tapa uksessa **1/x** tuottaa virheen, ja kaava palauttaa sen sijaan arvon 0.

Käytä **Iferror** -toimintoa toiminta [kaavoissa](../working-with-formulas-in-depth.md) , jos haluat suorittaa toiminnon ja tarkistaa virheen ennen lisä toimintojen suorittamista, kuten tässä ohjeessa:

```powerapps-dot
IfError(
    Patch( DS1, ... ), Notify( "problem in the first action" ),
    Patch( DS2, ... ), Notify( "problem in the second action" )
)
```

Jos ensimmäisessä korjaus tiedostosta ilmenee ongelma, ensimmäinen **ilmoitus** suoritetaan, mitään jatko jalostusta ei tapahdu ja toista korjaus tiedostoa ei suoriteta. Jos ensimmäinen korjaus tiedosto onnistuu, toinen korjaus tiedosto suoritetaan, ja jos se havaitsee ongelman, toinen **ilmoitus** suoritetaan.

Jos kaava ei löydä mitään virheitä ja olet määrittänyt valinnaisen *Defaultresult* -argumentin, kaava palauttaa argumentille määrittämäsi arvon. Jos kaavassa ei ole virheitä, mutta et ole määrittänyt tätä argumenttia, kaava palauttaa lasketun viimeisimmän *arvo* argumentin.

## <a name="syntax"></a>Syntaksi

**Iferor**( *arvo1*, *Fallback1* [, *arvo2*, *Fallback2*,... [, *Defaultresult* ]] )

* *Arvo (t)* – pakollinen. Kaavat virhearvojen testaamiseksi.
* *Fallback(s)* – Pakollinen. Arvioitavat kaavat ja arvot, jotka palautetaan, jos vastaavat *arvo* argumentit palauttivat virheen.
* *DefaultResult* – Valinnainen.  Kaavat, jotka arvioidaan, jos kaavassa ei löydy virheitä.

## <a name="examples"></a>Esimerkkejä

| Kaava | Kuvaus | Tulos |
| --- | --- | --- |
| **IfError( 1, 2 )** |Ensimmäinen argumentti ei ole virhe. Funktiolla ei ole muita virheitä, jotka voidaan tarkistaa eikä oletus palautus arvoa. Funktio palauttaa arvioinnin viimeisestä *arvo* argumentista.   | 1 |
| **IfError( 1/0, 2 )** | Ensimmäinen argumentti palauttaa virhe arvon (jako nollalla). Funktio arvioi toisen argumentin ja palauttaa tuloksen. | 2 |
| **IfError( 1/0, Notify( "Sisäinen virhe", NotificationType.Error ) )** | Ensimmäinen argumentti palauttaa virhe arvon (jako nollalla). Funktio arvioi toisen argumentin ja näyttää sanoman käyttäjälle. **IfError**-funktion palautusarvo on **Notify**-funktion palautusarvo, joka on pakotettu samantyyppiseksi kuin ensimmäinen argumentti funktioon **IfError** (luku). | 1 |
| **Iferor (1, 2, 3, 4, 5)** | Ensimmäinen argumentti ei ole virhe, joten funktio ei laske kyseisen argumentin vastaavaa toissijaiskohtaa. Kolmas argumentti ei ole myöskään virhe, joten funktio ei laske kyseisen argumentin vastaavaa varmistus kohtaa. Viidennessä argumentissa ei ole vastaavaa vara osaa, ja se on oletus tulos. Funktio palauttaa tuloksen, koska kaava ei sisällä virheitä. | 5 |

### <a name="step-by-step"></a>Vaihe vaiheelta

1. Lisää **[Tekstisyöte](../controls/control-text-input.md)** -ohjausobjekti ja anna sille nimeksi **TextInput1**, jos tämä ei ole sen oletusnimi.

2. Lisää **[Nimi](../controls/control-text-box.md)** -ohjausobjekti ja anna sille nimeksi **Label1**, jos tämä ei ole sen oletusnimi.

3. Määritä **Label1**:n **Text**-ominaisuuden kaavaksi:

    **IfError( Value( TextInput1.Text ), -1 )**

4. Kirjoita **TextInput1**-kohtaan **1234**.  

    Label1 näyttää arvon **1234**, koska tämä on kelvollinen syöte Value-funktioon.

5. Kirjoita **TextInput1**-kohtaan **ToInfinity**.

    Label1 näyttää arvon **-1**, koska tämä ei ole kelvollinen syöte Value-funktioon.  Jos Value-funktiota ei rivitettäisi IfError-funktion kanssa, otsikko ei näyttäisi arvoa, koska virhearvoa kohdellaan *tyhjänä*. 

