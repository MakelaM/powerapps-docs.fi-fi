---
title: Color-luettelointi ja ColorFade-, ColorValue- ja RGBA-funktiot | Microsoft Docs
description: Tietoa PowerAppsin Color-luetteloinnista ja ColorFade-, ColorValue- ja RGBA-funktioista, sekä syntakseja ja muutamia esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/04/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e8861ad4265165afcb6af1d51f0326638b521394
ms.sourcegitcommit: 2084789802fc5134dbeb888e759cced46019a017
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/06/2019
ms.locfileid: "66736330"
---
# <a name="color-enumeration-and-colorfade-colorvalue-and-rgba-functions-in-powerapps"></a>Color-luettelointi ja ColorFade-, ColorValue- ja RGBA-funktiot PowerAppsissa

Käyttää sisäinen väriarvot, Määritä mukautetut värit ja Käytä alfa-kanavaa.

## <a name="description"></a>Kuvaus

Käyttämällä **väri** luettelointi, voit helposti käyttää värejä, jotka on määritetty mukaan HTML: n CSS-tyylin CSS-tyylimäärityksillä. Esimerkiksi **Color.Red** palauttaa puhtaan punaisen. Löydät nämä värit tämän aiheen lopussa luettelo.

**ColorValue** funktio palauttaa värin CSS väri merkkijonon. Merkkijono voi olla näitä lomakkeita:

- **CSS-värinimen:** **”RoxyBrown”** ja **”OliveDrab”** ovat esimerkkejä. Nämä nimet eivät välilyöntejä. Tuetut värit näkyy myöhemmin tässä aiheessa.
- **6-numeroinen heksadesimaaliarvo:** Esimerkiksi **”#ffd700”** on sama kuin **(Gold)** . Merkkijono on muodossa ”#*rrggbb*” jossa *rr* on punainen osa heksadesimaalikoodaus kaksinumeroisena *gg* on vihreä, ja *bb* on sininen.
- **8-numeroinen heksadesimaaliarvo:** Esimerkiksi **”#ff7f5080”** on sama kuin **”koralli”** kanssa 50 prosenttia alfa-kanavaa. Merkkijono on muodossa ”#*rrggbbaa*” jossa *rr*, *gg*, ja *bb* samalla tavalla kuin 6-numeroinen lomakkeen. Edustaa alfa-kanavaa *aa*: **00** edustaa täysin läpinäkyvä ja **ff** edustaa täysin läpinäkymätön.

**RGBA** funktio palauttaa värin punaisen, vihreän ja sinisen osia. Funktio sisältää myös alfa-kanavaa värejä ohjausobjekteja, jotka ovat kerrostetun eteen toisiinsa. Alfa-kanavaa vaihtelee 0 tai 0 (joka on täysin läpinäkyvä ja näkymätön) 1 tai 100 % (joka on täysin läpinäkymätön ja minkä tahansa ohjausobjektin takana kerroksia ulos kokonaan estää).

**ColorFade**-funktio palauttaa värin sävyn kirkkaampana tai tummempana. Häivytyksen määrän asetusalue 1 (joka tummentaa värin mustaksi) 0 (joka ei vaikuta väri) ja 1 (täysin kirkastaa värin valkoiseksi).

## <a name="alpha-channel"></a>Alfa-kanavaa

Pohjaan perustuvan sovelluksen voit kerroksen eteen toisiinsa ohjausobjekteja ja määrittää ohjausobjektin takana olevat ohjausobjektit läpinäkyvyyden. Näin ollen värit korostaminen kerrokset kautta. Esimerkiksi Tässä kaaviossa näkyy, miten kolme ensisijainen väriä sekoittaa alfa asetus 50 prosenttia:

> [!div class="mx-imgBorder"]
> ![Kolme alfa asetusta 50 prosenttia ensisijainen väriä](media/function-colors/alpha-primary.png)

Voit myös korostaminen kuvien tiedostomuodoissa, jotka tukevat alpha-kanavia. Esimerkiksi ei korostaminen .jpeg-tiedostoja, mutta voit korostaminen .png-tiedostoja. Seuraavassa kuvassa sama punaisen, vihreän ja sinisen värejä edellisessä esimerkissä, mutta punainen väri näkyy muodossa aaltoalleviivaus (sen sijaan, että ympyrän) .png-tiedosto, jossa 50 prosenttia alfa kanava:

> [!div class="mx-imgBorder"]
> ![Punainen aaltoalleviivaus alfa asetusta 50 prosenttia sininen ja vihreä ympyröitä eteen](media/function-colors/alpha-image.png)

Jos määrität **väri** luettelointiarvo tai voit luoda **ColorValue** värin nimi tai heksadesimaaliarvo 6-numeroinen kaavan alfa asetus on 100 %, joka on täysin läpinäkymätön.

## <a name="syntax"></a>Syntaksi

**Color**.*ColorName*

- *ColorName* – Pakollinen.  CSS-tyylimäärityksen mukainen värin nimi. Mahdolliset arvot näkyy tämän aiheen lopussa.

**ColorValue**( *CSSColor* )

- *CSSColor* – Pakollinen.  CSS-tyylimäärityksen mukainen värin määritys. Voit määrittää joko nimi, kuten **OliveDrab**, tai heksadesimaaliarvo, kuten **#6b8e23** tai **#7fffd420**. Heksamerkkijono arvot voit toteuttaa joko #*rrggbb* tai #*rrggbbaa*.

**RGBA**( *punainen*, *vihreä*, *sininen*, *alfa* )

- *Punainen*, *vihreä*, *sininen* – Pakollinen.  Värikomponentille arvoja, jotka välillä 0 (ei värikylläisyyttä) – 255 (täysi värikylläisyys).
- *Alfa* – pakollinen.  Alfa komponentti, joka on välillä 0 (täysin läpinäkyvä) – 1 (täysin läpinäkymätön). Voit käyttää myös prosenttimäärää 0–100 %.

**ColorFade**( *Color*, *FadeAmount* )

- *Color* – Pakollinen.  Väriarvo, kuten **Color.Red** tai **ColorValue**- tai **RGBA**-määritys.
- *FadeAmount* – Pakollinen.  Luku väliltä –1 ja 1. arvo -1 tummentaa värin mustaksi, 0 ei vaikuta väri ja 1 kirkastaa värin valkoinen kokonaan. Voit myös käyttää-100 prosenttiarvo % 100 %.

## <a name="built-in-colors"></a>Sisäinen värit

| Color-luettelointi | ColorValue | RGBA | Väriruutu |
| --- | --- | --- | --- |
| **Color.AliceBlue** |**ColorValue( "#f0f8ff"&nbsp;)**<br>**ColorValue (”erittäin Vaalea sininen”&nbsp;)** |**RGBA(&nbsp;240,&nbsp;248,&nbsp;255,&nbsp;1&nbsp;)** |![erittäin vaalea sininen](./media/function-colors/color-aliceblue.png) |
| **Color.AntiqueWhite** |**ColorValue (”#faebd7”&nbsp;)**<br>**ColorValue (”AntiqueWhite”&nbsp;)** |**RGBA(&nbsp;250,&nbsp;235,&nbsp;215,&nbsp;1&nbsp;)** |![antiikinvalkoinen](./media/function-colors/color-antiquewhite.png) |
| **Color.Aqua** |**ColorValue (”#00ffff”&nbsp;)**<br>**ColorValue (”TURKOOSI”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;255,&nbsp;255,&nbsp;1&nbsp;)** |![turkoosi](./media/function-colors/color-aqua.png) |
| **Color.Aquamarine** |**ColorValue (”#7fffd4”&nbsp;)**<br>**ColorValue (”vedenvihreä”&nbsp;)** |**RGBA(&nbsp;127,&nbsp;255,&nbsp;212,&nbsp;1&nbsp;)** |![vedenvihreä](./media/function-colors/color-aquamarine.png) |
| **Color.Azure** |**ColorValue (”#f0ffff”&nbsp;)**<br>**ColorValue (”azure”&nbsp;)** |**RGBA(&nbsp;240,&nbsp;255,&nbsp;255,&nbsp;1&nbsp;)** |![asuurinsininen](./media/function-colors/color-azure.png) |
| **Color.Beige** |**ColorValue( "#f5f5dc"&nbsp;)**<br>**ColorValue (”Beige”&nbsp;)** |**RGBA(&nbsp;245,&nbsp;245,&nbsp;220,&nbsp;1&nbsp;)** |![beige](./media/function-colors/color-beige.png) |
| **Color.Bisque** |**ColorValue (”#ffe4c4”&nbsp;)**<br>**ColorValue (”BISQUE”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;228,&nbsp;196,&nbsp;1&nbsp;)** |![vaaleanruskea](./media/function-colors/color-bisque.png) |
| **Color.Black** |**ColorValue (”#000000”&nbsp;)**<br>**ColorValue (”musta”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;0,&nbsp;0,&nbsp;1&nbsp;)** |![musta](./media/function-colors/color-black.png) |
| **Color.BlanchedAlmond** |**ColorValue( "#ffebcd"&nbsp;)**<br>**ColorValue (”Kuorittu manteli”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;235,&nbsp;205,&nbsp;1&nbsp;)** |![kuorittu manteli](./media/function-colors/color-blanchedalmond.png) |
| **Color.Blue** |**ColorValue (”#0000ff”&nbsp;)**<br>**ColorValue (”Blue”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;0,&nbsp;255,&nbsp;1&nbsp;)** |![sininen](./media/function-colors/color-blue.png) |
| **Color.BlueViolet** |**ColorValue (”#8a2be2”&nbsp;)**<br>**ColorValue (”BLUEVIOLET”&nbsp;)** |**RGBA(&nbsp;138,&nbsp;43,&nbsp;226,&nbsp;1&nbsp;)** |![sinivioletti](./media/function-colors/color-blueviolet.png) |
| **Color.Brown** |**ColorValue (”#a52a2a”&nbsp;)**<br>**ColorValue (”Brown”&nbsp;)** |**RGBA(&nbsp;165,&nbsp;42,&nbsp;42,&nbsp;1&nbsp;)** |![ruskea](./media/function-colors/color-brown.png) |
| **Color.Burlywood** |**ColorValue (”#deb887”&nbsp;)**<br>**ColorValue (”burlywood”&nbsp;)** |**RGBA(&nbsp;222,&nbsp;184,&nbsp;135,&nbsp;1&nbsp;)** |![puunruskea](./media/function-colors/color-burlywood.png) |
| **Color.CadetBlue** |**ColorValue (”#5f9ea0”&nbsp;)**<br>**ColorValue (”CadetBlue”&nbsp;)** |**RGBA(&nbsp;95,&nbsp;158,&nbsp;160,&nbsp;1&nbsp;)** |![kadetinsininen](./media/function-colors/color-cadetblue.png) |
| **Color.Chartreuse** |**ColorValue (”#7fff00”&nbsp;)**<br>**ColorValue (”KELLANVIHREÄ”&nbsp;)** |**RGBA(&nbsp;127,&nbsp;255,&nbsp;0,&nbsp;1&nbsp;)** |![keltavihreä](./media/function-colors/color-chartreuse.png) |
| **Color.Chocolate** |**ColorValue (”#d2691e”&nbsp;)**<br>**ColorValue (”suklaa”&nbsp;)** |**RGBA(&nbsp;210,&nbsp;105,&nbsp;30,&nbsp;1&nbsp;)** |![suklaanruskea](./media/function-colors/color-chocolate.png) |
| **Color.Coral** |**ColorValue (”#ff7f50”&nbsp;)**<br>**ColorValue (”koralli”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;127,&nbsp;80,&nbsp;1&nbsp;)** |![koralli](./media/function-colors/color-coral.png) |
| **Color.CornflowerBlue** |**ColorValue (”#6495ed”&nbsp;)**<br>**ColorValue (”CornflowerBlue”&nbsp;)** |**RGBA(&nbsp;100,&nbsp;149,&nbsp;237,&nbsp;1&nbsp;)** |![ruiskukansininen](./media/function-colors/color-cornflowerblue.png) |
| **Color.Cornsilk** |**ColorValue( "#fff8dc"&nbsp;)**<br>**ColorValue (”CORNSILK”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;248,&nbsp;220,&nbsp;1&nbsp;)** |![maissinkeltainen](./media/function-colors/color-cornsilk.png) |
| **Color.Crimson** |**ColorValue (”#dc143c”&nbsp;)**<br>**ColorValue (”Crimson”&nbsp;)** |**RGBA(&nbsp;220,&nbsp;20,&nbsp;60,&nbsp;1&nbsp;)** |![karmiininpunainen](./media/function-colors/color-crimson.png) |
| **Color.Cyan** |**ColorValue (”#00ffff”&nbsp;)**<br>**ColorValue (”syaani”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;255,&nbsp;255,&nbsp;1&nbsp;)** |![syaani](./media/function-colors/color-cyan.png) |
| **Color.DarkBlue** |**ColorValue (”#00008b”&nbsp;)**<br>**ColorValue (”DarkBlue”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;0,&nbsp;139,&nbsp;1&nbsp;)** |![tummansininen](./media/function-colors/color-darkblue.png) |
| **Color.DarkCyan** |**ColorValue (”#008b8b”&nbsp;)**<br>**ColorValue (”Tumma SYAANI”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;139,&nbsp;139,&nbsp;1&nbsp;)** |![tumma syaani](./media/function-colors/color-darkcyan.png) |
| **Color.DarkGoldenRod** |**ColorValue (”#b8860b”&nbsp;)**<br>**ColorValue (”Tumma kultapiisku”&nbsp;)** |**RGBA(&nbsp;184,&nbsp;134,&nbsp;11,&nbsp;1&nbsp;)** |![tumma kultapiisku](./media/function-colors/color-darkgoldenrod.png) |
| **Color.DarkGray** |**ColorValue (”#a9a9a9”&nbsp;)**<br>**ColorValue (”darkgray”&nbsp;)** |**RGBA(&nbsp;169,&nbsp;169,&nbsp;169,&nbsp;1&nbsp;)** |![tummanharmaa](./media/function-colors/color-darkgray.png) |
| **Color.DarkGreen** |**ColorValue (”#006400”&nbsp;)**<br>**ColorValue (”DarkGreen”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;100,&nbsp;0,&nbsp;1&nbsp;)** |![tummanvihreä](./media/function-colors/color-darkgreen.png) |
| **Color.DarkGrey** |**ColorValue (”#a9a9a9”&nbsp;)**<br>**ColorValue (”DARKGREY”&nbsp;)** |**RGBA(&nbsp;169,&nbsp;169,&nbsp;169,&nbsp;1&nbsp;)** |![tummanharmaa](./media/function-colors/color-darkgrey.png) |
| **Color.DarkKhaki** |**ColorValue (”#bdb76b”&nbsp;)**<br>**ColorValue (”Tumma khaki”&nbsp;)** |**RGBA(&nbsp;189,&nbsp;183,&nbsp;107,&nbsp;1&nbsp;)** |![tumma khaki](./media/function-colors/color-darkkhaki.png) |
| **Color.DarkMagenta** |**ColorValue (”#8b008b”&nbsp;)**<br>**ColorValue (”Tumma magenta”&nbsp;)** |**RGBA(&nbsp;139,&nbsp;0,&nbsp;139,&nbsp;1&nbsp;)** |![tumma magenta](./media/function-colors/color-darkmagenta.png) |
| **Color.DarkOliveGreen** |**ColorValue (”#556b2f”&nbsp;)**<br>**ColorValue (”Tumma oliivinvihreä”&nbsp;)** |**RGBA(&nbsp;85,&nbsp;107,&nbsp;47,&nbsp;1&nbsp;)** |![tumma oliivinvihreä](./media/function-colors/color-darkolivegreen.png) |
| '**Color.DarkOrange** |**ColorValue( "#ff8c00"&nbsp;)**<br>**ColorValue (”DARKORANGE”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;140,&nbsp;0,&nbsp;1&nbsp;)** |![tummanoranssi](./media/function-colors/color-darkorange.png) |
| **Color.DarkOrchid** |**ColorValue (”#9932cc”&nbsp;)**<br>**ColorValue (”Tumma orkidea”&nbsp;)** |**RGBA(&nbsp;153,&nbsp;50,&nbsp;204,&nbsp;1&nbsp;)** |![tumma orkidea](./media/function-colors/color-darkorchid.png) |
| **Color.DarkRed** |**ColorValue (”#8b0000”&nbsp;)**<br>**ColorValue (”darkred”&nbsp;)** |**RGBA(&nbsp;139,&nbsp;0,&nbsp;0,&nbsp;1&nbsp;)** |![tummanpunainen](./media/function-colors/color-darkred.png) |
| **Color.DarkSalmon** |**ColorValue (”#e9967a”&nbsp;)**<br>**ColorValue (”Tumma lohenpunainen”&nbsp;)** |**RGBA(&nbsp;233,&nbsp;150,&nbsp;122,&nbsp;1&nbsp;)** |![tumma lohenpunainen](./media/function-colors/color-darksalmon.png) |
| **Color.DarkSeaGreen** |**ColorValue (”#8fbc8f”&nbsp;)**<br>**ColorValue (”Tumma MERENVIHREÄ”&nbsp;)** |**RGBA(&nbsp;143,&nbsp;188,&nbsp;143,&nbsp;1&nbsp;)** |![tumma merenvihreä](./media/function-colors/color-darkseagreen.png) |
| **Color.DarkSlateBlue** |**ColorValue (”#483d8b”&nbsp;)**<br>**ColorValue (”Tumma siniharmaa”&nbsp;)** |**RGBA(&nbsp;72,&nbsp;61,&nbsp;139,&nbsp;1&nbsp;)** |![tumma siniharmaa](./media/function-colors/color-darkslateblue.png) |
| **Color.DarkSlateGray** |**ColorValue (”#2f4f4f”&nbsp;)**<br>**ColorValue( "darkslategray"&nbsp;)** |**RGBA(&nbsp;47,&nbsp;79,&nbsp;79,&nbsp;1&nbsp;)** |![tumma savenharmaa](./media/function-colors/color-darkslategray.png) |
| **Color.DarkSlateGrey** |**ColorValue (”#2f4f4f”&nbsp;)**<br>**ColorValue( "DarkSlateGrey"&nbsp;)** |**RGBA(&nbsp;47,&nbsp;79,&nbsp;79,&nbsp;1&nbsp;)** |![tumma savenharmaa](./media/function-colors/color-darkslategrey.png) |
| **Color.DarkTurquoise** |**ColorValue (”#00ced1”&nbsp;)**<br>**ColorValue (”Tumma TURKOOSI”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;206,&nbsp;209,&nbsp;1&nbsp;)** |![tumma turkoosi](./media/function-colors/color-darkturquoise.png) |
| **Color.DarkViolet** |**ColorValue (”#9400 d 3”&nbsp;)**<br>**ColorValue (”DarkViolet”&nbsp;)** |**RGBA(&nbsp;148,&nbsp;0,&nbsp;211,&nbsp;1&nbsp;)** |![tummanvioletti](./media/function-colors/color-darkviolet.png) |
| **Color.DeepPink** |**ColorValue (”#ff1493”&nbsp;)**<br>**ColorValue( "deeppink"&nbsp;)** |**RGBA(&nbsp;255,&nbsp;20,&nbsp;147,&nbsp;1&nbsp;)** |![syvä vaaleanpunainen](./media/function-colors/color-deeppink.png) |
| **Color.DeepSkyBlue** |**ColorValue (”#00bfff”&nbsp;)**<br>**ColorValue (”Tumma taivaansininen”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;191,&nbsp;255,&nbsp;1&nbsp;)** |![tumma taivaansininen](./media/function-colors/color-deepskyblue.png) |
| **Color.DimGray** |**ColorValue (”#696969”&nbsp;)**<br>**ColorValue (”DIMGRAY”&nbsp;)** |**RGBA(&nbsp;105,&nbsp;105,&nbsp;105,&nbsp;1&nbsp;)** |![himmeänharmaa](./media/function-colors/color-dimgray.png) |
| **Color.DimGrey** |**ColorValue (”#696969”&nbsp;)**<br>**ColorValue (”DimGrey”&nbsp;)** |**RGBA(&nbsp;105,&nbsp;105,&nbsp;105,&nbsp;1&nbsp;)** |![himmeänharmaa](./media/function-colors/color-dimgrey.png) |
| **Color.DodgerBlue** |**ColorValue (”#1e90ff”&nbsp;)**<br>**ColorValue (”dodgerblue”&nbsp;)** |**RGBA(&nbsp;30,&nbsp;144,&nbsp;255,&nbsp;1&nbsp;)** |![kirkkaansininen](./media/function-colors/color-dodgerblue.png) |
| **Color.FireBrick** |**ColorValue (”#b22222”&nbsp;)**<br>**ColorValue (”poltettu Tiili”&nbsp;)** |**RGBA(&nbsp;178,&nbsp;34,&nbsp;34,&nbsp;1&nbsp;)** |![poltettu tiili](./media/function-colors/color-firebrick.png) |
| **Color.FloralWhite** |**ColorValue (”#fffaf0”&nbsp;)**<br>**ColorValue (”FLORALWHITE”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;250,&nbsp;240,&nbsp;1&nbsp;)** |![kukanvalkoinen](./media/function-colors/color-floralwhite.png) |
| **Color.ForestGreen** |**ColorValue (”#228b22”&nbsp;)**<br>**ColorValue (”ForestGreen”&nbsp;)** |**RGBA(&nbsp;34,&nbsp;139,&nbsp;34,&nbsp;1&nbsp;)** |![metsänvihreä](./media/function-colors/color-forestgreen.png) |
| **Color.Fuchsia** |**ColorValue( "#ff00ff"&nbsp;)**<br>**ColorValue (”fuksia”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;0,&nbsp;255,&nbsp;1&nbsp;)** |![aniliini](./media/function-colors/color-fuchsia.png) |
| **Color.Gainsboro** |**ColorValue (”#dcdcdc”&nbsp;)**<br>**ColorValue (”Gainsboro”&nbsp;)** |**RGBA(&nbsp;220,&nbsp;220,&nbsp;220,&nbsp;1&nbsp;)** |![gainsboro](./media/function-colors/color-gainsboro.png) |
| **Color.GhostWhite** |**ColorValue( "#f8f8ff"&nbsp;)**<br>**ColorValue (”GHOSTWHITE”&nbsp;)** |**RGBA(&nbsp;248,&nbsp;248,&nbsp;255,&nbsp;1&nbsp;)** |![lakananvalkoinen](./media/function-colors/color-ghostwhite.png) |
| **Color.Gold** |**ColorValue (”#ffd700”&nbsp;)**<br>**ColorValue (”Gold”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;215,&nbsp;0,&nbsp;1&nbsp;)** |![kulta](./media/function-colors/color-gold.png) |
| **Color.GoldenRod** |**ColorValue (”#daa520”&nbsp;)**<br>**ColorValue (”kultapiisku”&nbsp;)** |**RGBA(&nbsp;218,&nbsp;165,&nbsp;32,&nbsp;1&nbsp;)** |![kultapiisku](./media/function-colors/color-goldenrod.png) |
| **Color.Gray** |**ColorValue (”#808080”&nbsp;)**<br>**ColorValue (”harmaa”&nbsp;)** |**RGBA(&nbsp;128,&nbsp;128,&nbsp;128,&nbsp;1&nbsp;)** |![harmaa](./media/function-colors/color-gray.png) |
| **Color.Green** |**ColorValue (”#008000”&nbsp;)**<br>**ColorValue (”vihreä”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;128,&nbsp;0,&nbsp;1&nbsp;)** |![vihreä](./media/function-colors/color-green.png) |
| **Color.GreenYellow** |**ColorValue (”#adff2f”&nbsp;)**<br>**ColorValue (”GreenYellow”&nbsp;)** |**RGBA(&nbsp;173,&nbsp;255,&nbsp;47,&nbsp;1&nbsp;)** |![vihreänkeltainen](./media/function-colors/color-greenyellow.png) |
| **Color.Grey** |**ColorValue (”#808080”&nbsp;)**<br>**ColorValue (”harmaa”&nbsp;)** |**RGBA(&nbsp;128,&nbsp;128,&nbsp;128,&nbsp;1&nbsp;)** |![harmaa](./media/function-colors/color-grey.png) |
| **Color.Honeydew** |**ColorValue (”#f0fff0”&nbsp;)**<br>**ColorValue (”mesikaste”&nbsp;)** |**RGBA(&nbsp;240,&nbsp;255,&nbsp;240,&nbsp;1&nbsp;)** |![hunajameloni](./media/function-colors/color-honeydew.png) |
| **Color.HotPink** |**ColorValue (”#ff69b4”&nbsp;)**<br>**ColorValue (”HOTPINK”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;105,&nbsp;180,&nbsp;1&nbsp;)** |![pinkki](./media/function-colors/color-hotpink.png) |
| **Color.IndianRed** |**ColorValue (”#cd5c5c”&nbsp;)**<br>**ColorValue (”IndianRed”&nbsp;)** |**RGBA(&nbsp;205,&nbsp;92,&nbsp;92,&nbsp;1&nbsp;)** |![intianpunainen](./media/function-colors/color-indianred.png) |
| **Color.Indigo** |**ColorValue (”#4b0082”&nbsp;)**<br>**ColorValue (”indigo”&nbsp;)** |**RGBA(&nbsp;75,&nbsp;0,&nbsp;130,&nbsp;1&nbsp;)** |![indigonsininen](./media/function-colors/color-indigo.png) |
| **Color.Ivory** |**ColorValue (”#fffff0”&nbsp;)**<br>**ColorValue (”Norsunluinen”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;255,&nbsp;240,&nbsp;1&nbsp;)** |![norsunluu](./media/function-colors/color-ivory.png) |
| **Color.Khaki** |**ColorValue (”#f0e68c”&nbsp;)**<br>**ColorValue (”KHAKI”&nbsp;)** |**RGBA(&nbsp;240,&nbsp;230,&nbsp;140,&nbsp;1&nbsp;)** |![khaki](./media/function-colors/color-khaki.png) |
| **Color.Lavender** |**ColorValue (”#e6e6fa”&nbsp;)**<br>**ColorValue (”laventeli”&nbsp;)** |**RGBA(&nbsp;230,&nbsp;230,&nbsp;250,&nbsp;1&nbsp;)** |![laventeli](./media/function-colors/color-lavender.png) |
| **Color.LavenderBlush** |**ColorValue (”#fff0f5”&nbsp;)**<br>**ColorValue (”lavenderblush”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;240,&nbsp;245,&nbsp;1&nbsp;)** |![laventelinsininen](./media/function-colors/color-lavenderblush.png) |
| **Color.LawnGreen** |**ColorValue (”#7cfc00”&nbsp;)**<br>**ColorValue (”LawnGreen”&nbsp;)** |**RGBA(&nbsp;124,&nbsp;252,&nbsp;0,&nbsp;1&nbsp;)** |![ruohonvihreä](./media/function-colors/color-lawngreen.png) |
| **Color.LemonChiffon** |**ColorValue (”#fffacd”&nbsp;)**<br>**ColorValue (”LEMONCHIFFON”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;250,&nbsp;205,&nbsp;1&nbsp;)** |![sitruunankeltainen](./media/function-colors/color-lemonchiffon.png) |
| **Color.LightBlue** |**ColorValue (”#add8e6”&nbsp;)**<br>**ColorValue (”LightBlue”&nbsp;)** |**RGBA(&nbsp;173,&nbsp;216,&nbsp;230,&nbsp;1&nbsp;)** |![vaaleansininen](./media/function-colors/color-lightblue.png) |
| **Color.LightCoral** |**ColorValue (”#f08080”&nbsp;)**<br>**ColorValue (”Vaalea koralli”&nbsp;)** |**RGBA(&nbsp;240,&nbsp;128,&nbsp;128,&nbsp;1&nbsp;)** |![vaalea koralli](./media/function-colors/color-lightcoral.png) |
| **Color.LightCyan** |**ColorValue (”#e0ffff”&nbsp;)**<br>**ColorValue (”Vaalea syaani”&nbsp;)** |**RGBA(&nbsp;224,&nbsp;255,&nbsp;255,&nbsp;1&nbsp;)** |![vaalea syaani](./media/function-colors/color-lightcyan.png) |
| **Color.LightGoldenRodYellow** |**ColorValue( "#fafad2"&nbsp;)**<br>**ColorValue (”Vaalea kultapiiskunkeltainen”&nbsp;)** |**RGBA(&nbsp;250,&nbsp;250,&nbsp;210,&nbsp;1&nbsp;)** |![vaalea kultapiiskunkeltainen](./media/function-colors/color-lightgoldenrodyellow.png) |
| **Color.LightGray** |**ColorValue (”#d3d3d3”&nbsp;)**<br>**ColorValue (”LightGray”&nbsp;)** |**RGBA(&nbsp;211,&nbsp;211,&nbsp;211,&nbsp;1&nbsp;)** |![vaaleanharmaa](./media/function-colors/color-lightgray.png) |
| **Color.LightGreen** |**ColorValue (”#90ee90”&nbsp;)**<br>**ColorValue (”lightgreen”&nbsp;)** |**RGBA(&nbsp;144,&nbsp;238,&nbsp;144,&nbsp;1&nbsp;)** |![vaaleanvihreä](./media/function-colors/color-lightgreen.png) |
| **Color.LightGrey** |**ColorValue (”#d3d3d3”&nbsp;)**<br>**ColorValue (”LightGrey”&nbsp;)** |**RGBA(&nbsp;211,&nbsp;211,&nbsp;211,&nbsp;1&nbsp;)** |![vaaleanharmaa](./media/function-colors/color-lightgrey.png) |
| **Color.LightPink** |**ColorValue (”#ffb6c1”&nbsp;)**<br>**ColorValue( "LIGHTPINK"&nbsp;)** |**RGBA(&nbsp;255,&nbsp;182,&nbsp;193,&nbsp;1&nbsp;)** |![vaalea pinkki](./media/function-colors/color-lightpink.png) |
| **Color.LightSalmon** |**ColorValue (”#ffa07a”&nbsp;)**<br>**ColorValue (”Vaalea lohenpunainen”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;160,&nbsp;122,&nbsp;1&nbsp;)** |![vaalea lohenpunainen](./media/function-colors/color-lightsalmon.png) |
| **Color.LightSeaGreen** |**ColorValue (”#20b2aa”&nbsp;)**<br>**ColorValue (”Vaalea merenvihreä”&nbsp;)** |**RGBA(&nbsp;32,&nbsp;178,&nbsp;170,&nbsp;1&nbsp;)** |![vaalea merenvihreä](./media/function-colors/color-lightseagreen.png) |
| **Color.LightSkyBlue** |**ColorValue (”#87cefa”&nbsp;)**<br>**ColorValue( "LightSkyBlue"&nbsp;)** |**RGBA(&nbsp;135,&nbsp;206,&nbsp;250,&nbsp;1&nbsp;)** |![vaalea taivaansininen](./media/function-colors/color-lightskyblue.png) |
| **Color.LightSlateGray** |**ColorValue (”#778899”&nbsp;)**<br>**ColorValue (”Vaalea SAVENHARMAA”&nbsp;)** |**RGBA(&nbsp;119,&nbsp;136,&nbsp;153,&nbsp;1&nbsp;)** |![vaalea savenharmaa](./media/function-colors/color-lightslategray.png) |
| **Color.LightSlateGrey** |**ColorValue (”#778899”&nbsp;)**<br>**ColorValue( "LightSlateGrey"&nbsp;)** |**RGBA(&nbsp;119,&nbsp;136,&nbsp;153,&nbsp;1&nbsp;)** |![vaalea savenharmaa](./media/function-colors/color-lightslategrey.png) |
| **Color.LightSteelBlue** |**ColorValue( "#b0c4de"&nbsp;)**<br>**ColorValue (”Vaalea teräksensininen”&nbsp;)** |**RGBA(&nbsp;176,&nbsp;196,&nbsp;222,&nbsp;1&nbsp;)** |![vaalea teräksensininen](./media/function-colors/color-lightsteelblue.png) |
| **Color.LightYellow** |**ColorValue (”#ffffe0”&nbsp;)**<br>**ColorValue (”LightYellow”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;255,&nbsp;224,&nbsp;1&nbsp;)** |![vaaleankeltainen](./media/function-colors/color-lightyellow.png) |
| **Color.Lime** |**ColorValue (”#00ff00”&nbsp;)**<br>**ColorValue (”KELTAVIHREÄ”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;255,&nbsp;0,&nbsp;1&nbsp;)** |![keltavihreä](./media/function-colors/color-lime.png) |
| **Color.LimeGreen** |**ColorValue (”#32 cd 32”&nbsp;)**<br>**ColorValue( "LimeGreen"&nbsp;)** |**RGBA(&nbsp;50,&nbsp;205,&nbsp;50,&nbsp;1&nbsp;)** |![limetinvihreä](./media/function-colors/color-limegreen.png) |
| **Color.Linen** |**ColorValue (”#faf0e6”&nbsp;)**<br>**ColorValue (”pyyheliinat”&nbsp;)** |**RGBA(&nbsp;250,&nbsp;240,&nbsp;230,&nbsp;1&nbsp;)** |![pellavanvaalea](./media/function-colors/color-linen.png) |
| **Color.Magenta** |**ColorValue( "#ff00ff"&nbsp;)**<br>**ColorValue (”Magenta”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;0,&nbsp;255,&nbsp;1&nbsp;)** |![magenta](./media/function-colors/color-magenta.png) |
| **Color.Maroon** |**ColorValue (”#800000”&nbsp;)**<br>**ColorValue (”KASTANJANRUSKEA”&nbsp;)** |**RGBA(&nbsp;128,&nbsp;0,&nbsp;0,&nbsp;1&nbsp;)** |![kastanjanruskea](./media/function-colors/color-maroon.png) |
| **Color.MediumAquamarine** |**ColorValue( "#66cdaa"&nbsp;)**<br>**ColorValue (”Keskivaalea vedenvihreä”&nbsp;)** |**RGBA(&nbsp;102,&nbsp;205,&nbsp;170,&nbsp;1&nbsp;)** |![keskivaalea vedenvihreä](./media/function-colors/color-mediumaquamarine.png) |
| **Color.MediumBlue** |**ColorValue (”#0000 cd”&nbsp;)**<br>**ColorValue (”Keskivaalea sininen”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;0,&nbsp;205,&nbsp;1&nbsp;)** |![keskivaalea sininen](./media/function-colors/color-mediumblue.png) |
| **Color.MediumOrchid** |**ColorValue( "#ba55d3"&nbsp;)**<br>**ColorValue (”Keskivaalea orkidea”&nbsp;)** |**RGBA(&nbsp;186,&nbsp;85,&nbsp;211,&nbsp;1&nbsp;)** |![keskivaalea orkidea](./media/function-colors/color-mediumorchid.png) |
| **Color.MediumPurple** |**ColorValue (”#9370db”&nbsp;)**<br>**ColorValue (”Keskivaalea PURPPURA”&nbsp;)** |**RGBA(&nbsp;147,&nbsp;112,&nbsp;219,&nbsp;1&nbsp;)** |![keskivaalea purppura](./media/function-colors/color-mediumpurple.png) |
| **Color.MediumSeaGreen** |**ColorValue (”#3cb371”&nbsp;)**<br>**ColorValue (”Keskivaalea merenvihreä”&nbsp;)** |**RGBA(&nbsp;60,&nbsp;179,&nbsp;113,&nbsp;1&nbsp;)** |![keskivaalea merenvihreä](./media/function-colors/color-mediumseagreen.png) |
| **Color.MediumSlateBlue** |**ColorValue (”#7b68ee”&nbsp;)**<br>**ColorValue( "mediumslateblue"&nbsp;)** |**RGBA(&nbsp;123,&nbsp;104,&nbsp;238,&nbsp;1&nbsp;)** |![keskivaalea siniharmaa](./media/function-colors/color-mediumslateblue.png) |
| **Color.MediumSpringGreen** |**ColorValue (”#00fa9a”&nbsp;)**<br>**ColorValue (”Keskivaalea keväänvihreä”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;250,&nbsp;154,&nbsp;1&nbsp;)** |![keskivaalea keväänvihreä](./media/function-colors/color-mediumspringgreen.png) |
| **Color.MediumTurquoise** |**ColorValue (”#48d1cc”&nbsp;)**<br>**ColorValue (”Keskivaalea TURKOOSI”&nbsp;)** |**RGBA(&nbsp;72,&nbsp;209,&nbsp;204,&nbsp;1&nbsp;)** |![keskivaalea turkoosi](./media/function-colors/color-mediumturquoise.png) |
| **Color.MediumVioletRed** |**ColorValue (”#c71585”&nbsp;)**<br>**ColorValue (”Keskivaalea lila”&nbsp;)** |**RGBA(&nbsp;199,&nbsp;21,&nbsp;133,&nbsp;1&nbsp;)** |![keskivaalea lila](./media/function-colors/color-mediumvioletred.png) |
| **Color.MidnightBlue** |**ColorValue (”#191970”&nbsp;)**<br>**ColorValue (”midnightblue”&nbsp;)** |**RGBA(&nbsp;25,&nbsp;25,&nbsp;112,&nbsp;1&nbsp;)** |![yönsininen](./media/function-colors/color-midnightblue.png) |
| **Color.MintCream** |**ColorValue (”#f5fffa”&nbsp;)**<br>**ColorValue (”MintCream”&nbsp;)** |**RGBA(&nbsp;245,&nbsp;255,&nbsp;250,&nbsp;1&nbsp;)** |![minttukreemi](./media/function-colors/color-mintcream.png) |
| **Color.MistyRose** |**ColorValue (”#ffe4e1”&nbsp;)**<br>**ColorValue (”Utuinen RUUSU”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;228,&nbsp;225,&nbsp;1&nbsp;)** |![utuinen ruusu](./media/function-colors/color-mistyrose.png) |
| **Color.Moccasin** |**ColorValue (”#ffe4b5”&nbsp;)**<br>**ColorValue (”Moccasin”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;228,&nbsp;181,&nbsp;1&nbsp;)** |![nahanruskea](./media/function-colors/color-moccasin.png) |
| **Color.NavajoWhite** |**ColorValue (”#ffdead”&nbsp;)**<br>**ColorValue (”navajowhite”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;222,&nbsp;173,&nbsp;1&nbsp;)** |![navajonvalkoinen](./media/function-colors/color-navajowhite.png) |
| **Color.Navy** |**ColorValue (”#000080”&nbsp;)**<br>**ColorValue (”Laivastonsininen”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;0,&nbsp;128,&nbsp;1&nbsp;)** |![laivastonsininen](./media/function-colors/color-navy.png) |
| **Color.OldLace** |**ColorValue (”#fdf5e6”&nbsp;)**<br>**ColorValue (”vanha PITSI”&nbsp;)** |**RGBA(&nbsp;253,&nbsp;245,&nbsp;230,&nbsp;1&nbsp;)** |![vanha pitsi](./media/function-colors/color-oldlace.png) |
| **Color.Olive** |**ColorValue (”#808000”&nbsp;)**<br>**ColorValue (”oliivinvihreä”&nbsp;)** |**RGBA(&nbsp;128,&nbsp;128,&nbsp;0,&nbsp;1&nbsp;)** |![oliivi](./media/function-colors/color-olive.png) |
| **Color.OliveDrab** |**ColorValue (”#6b8e23”&nbsp;)**<br>**ColorValue (”olivedrab”&nbsp;)** |**RGBA(&nbsp;107,&nbsp;142,&nbsp;35,&nbsp;1&nbsp;)** |![oliivinruskea](./media/function-colors/color-olivedrab.png) |
| **Color.Orange** |**ColorValue (”#ffa500”&nbsp;)**<br>**ColorValue (”Orange”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;165,&nbsp;0,&nbsp;1&nbsp;)** |![oranssi](./media/function-colors/color-orange.png) |
| **Color.OrangeRed** |**ColorValue (”#ff4500”&nbsp;)**<br>**ColorValue (”ORANGERED”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;69,&nbsp;0,&nbsp;1&nbsp;)** |![oranssinpunainen](./media/function-colors/color-orangered.png) |
| **Color.Orchid** |**ColorValue (”#da70d6”&nbsp;)**<br>**ColorValue (”orkidea”&nbsp;)** |**RGBA(&nbsp;218,&nbsp;112,&nbsp;214,&nbsp;1&nbsp;)** |![orkidea](./media/function-colors/color-orchid.png) |
| **Color.PaleGoldenRod** |**ColorValue (”#eee8aa”&nbsp;)**<br>**ColorValue (”Vaalea kultapiisku”&nbsp;)** |**RGBA(&nbsp;238,&nbsp;232,&nbsp;170,&nbsp;1&nbsp;)** |![vaalea kultapiisku](./media/function-colors/color-palegoldenrod.png) |
| **Color.PaleGreen** |**ColorValue (”#98fb98”&nbsp;)**<br>**ColorValue (”PaleGreen”&nbsp;)** |**RGBA(&nbsp;152,&nbsp;251,&nbsp;152,&nbsp;1&nbsp;)** |![hailakanvihreä](./media/function-colors/color-palegreen.png) |
| **Color.PaleTurquoise** |**ColorValue (”#afeeee”&nbsp;)**<br>**ColorValue (”Vaalea TURKOOSI”&nbsp;)** |**RGBA(&nbsp;175,&nbsp;238,&nbsp;238,&nbsp;1&nbsp;)** |![vaalea turkoosi](./media/function-colors/color-paleturquoise.png) |
| **Color.PaleVioletRed** |**ColorValue (”#db7093”&nbsp;)**<br>**ColorValue (”Vaalea lila”&nbsp;)** |**RGBA(&nbsp;219,&nbsp;112,&nbsp;147,&nbsp;1&nbsp;)** |![vaalea lila](./media/function-colors/color-palevioletred.png) |
| **Color.PapayaWhip** |**ColorValue (”#ffefd5”&nbsp;)**<br>**ColorValue (”papayawhip”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;239,&nbsp;213,&nbsp;1&nbsp;)** |![papaijavaahto](./media/function-colors/color-papayawhip.png) |
| **Color.PeachPuff** |**ColorValue (”#ffdab9”&nbsp;)**<br>**ColorValue (”PeachPuff”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;218,&nbsp;185,&nbsp;1&nbsp;)** |![persikka](./media/function-colors/color-peachpuff.png) |
| **Color.Peru** |**ColorValue (”#cd853f”&nbsp;)**<br>**ColorValue (”PERU”&nbsp;)** |**RGBA(&nbsp;205,&nbsp;133,&nbsp;63,&nbsp;1&nbsp;)** |![peru](./media/function-colors/color-peru.png) |
| **Color.Pink** |**ColorValue( "#ffc0cb"&nbsp;)**<br>**ColorValue (”vaaleanpunainen”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;192,&nbsp;203,&nbsp;1&nbsp;)** |![vaaleanpunainen](./media/function-colors/color-pink.png) |
| **Color.Plum** |**ColorValue (”#dda0dd”&nbsp;)**<br>**ColorValue( "plum"&nbsp;)** |**RGBA(&nbsp;221,&nbsp;160,&nbsp;221,&nbsp;1&nbsp;)** |![luumu](./media/function-colors/color-plum.png) |
| **Color.PowderBlue** |**ColorValue (”#b0e0e6”&nbsp;)**<br>**ColorValue (”PowderBlue”&nbsp;)** |**RGBA(&nbsp;176,&nbsp;224,&nbsp;230,&nbsp;1&nbsp;)** |![harmaansininen](./media/function-colors/color-powderblue.png) |
| **Color.Purple** |**ColorValue (”#800080”&nbsp;)**<br>**ColorValue (”PURPPURA”&nbsp;)** |**RGBA(&nbsp;128,&nbsp;0,&nbsp;128,&nbsp;1&nbsp;)** |![purppura](./media/function-colors/color-purple.png) |
| **Color.Red** |**ColorValue (”#ff0000”&nbsp;)**<br>**ColorValue (”Red”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;0,&nbsp;0,&nbsp;1&nbsp;)** |![punainen](./media/function-colors/color-red.png) |
| **Color.RosyBrown** |**ColorValue (”#bc8f8f”&nbsp;)**<br>**ColorValue (”rosybrown”&nbsp;)** |**RGBA(&nbsp;188,&nbsp;143,&nbsp;143,&nbsp;1&nbsp;)** |![punertavanruskea](./media/function-colors/color-rosybrown.png) |
| **Color.RoyalBlue** |**ColorValue (”#4169e1”&nbsp;)**<br>**ColorValue (”RoyalBlue”&nbsp;)** |**RGBA(&nbsp;65,&nbsp;105,&nbsp;225,&nbsp;1&nbsp;)** |![syvänsininen](./media/function-colors/color-royalblue.png) |
| **Color.SaddleBrown** |**ColorValue (”#8b4513”&nbsp;)**<br>**ColorValue (”SADDLEBROWN”&nbsp;)** |**RGBA(&nbsp;139,&nbsp;69,&nbsp;19,&nbsp;1&nbsp;)** |![satulanruskea](./media/function-colors/color-saddlebrown.png) |
| **Color.Salmon** |**ColorValue( "#fa8072"&nbsp;)**<br>**ColorValue (”lohenpunainen”&nbsp;)** |**RGBA(&nbsp;250,&nbsp;128,&nbsp;114,&nbsp;1&nbsp;)** |![lohenpunainen](./media/function-colors/color-salmon.png) |
| **Color.SandyBrown** |**ColorValue (”#f4a460”&nbsp;)**<br>**ColorValue (”sandybrown”&nbsp;)** |**RGBA(&nbsp;244,&nbsp;164,&nbsp;96,&nbsp;1&nbsp;)** |![hiekanruskea](./media/function-colors/color-sandybrown.png) |
| **Color.SeaGreen** |**ColorValue (”#2e8b57”&nbsp;)**<br>**ColorValue (”SeaGreen”&nbsp;)** |**RGBA(&nbsp;46,&nbsp;139,&nbsp;87,&nbsp;1&nbsp;)** |![merenvihreä](./media/function-colors/color-seagreen.png) |
| **Color.SeaShell** |**ColorValue (”#fff5ee”&nbsp;)**<br>**ColorValue (”SEASHELL”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;245,&nbsp;238,&nbsp;1&nbsp;)** |![kotilo](./media/function-colors/color-seashell.png) |
| **Color.Sienna** |**ColorValue( "#a0522d"&nbsp;)**<br>**ColorValue (”Sienna”&nbsp;)** |**RGBA(&nbsp;160,&nbsp;82,&nbsp;45,&nbsp;1&nbsp;)** |![siena](./media/function-colors/color-sienna.png) |
| **Color.Silver** |**ColorValue (”#c0c0c0”&nbsp;)**<br>**ColorValue (”hopea”&nbsp;)** |**RGBA(&nbsp;192,&nbsp;192,&nbsp;192,&nbsp;1&nbsp;)** |![hopea](./media/function-colors/color-silver.png) |
| **Color.SkyBlue** |**ColorValue (”#87ceeb”&nbsp;)**<br>**ColorValue (”SkyBlue”&nbsp;)** |**RGBA(&nbsp;135,&nbsp;206,&nbsp;235,&nbsp;1&nbsp;)** |![taivaansininen](./media/function-colors/color-skyblue.png) |
| **Color.SlateBlue** |**ColorValue (”#6a5acd”&nbsp;)**<br>**ColorValue (”SLATEBLUE”&nbsp;)** |**RGBA(&nbsp;106,&nbsp;90,&nbsp;205,&nbsp;1&nbsp;)** |![siniharmaa](./media/function-colors/color-slateblue.png) |
| **Color.SlateGray** |**ColorValue (”#708090”&nbsp;)**<br>**ColorValue (”SlateGray”&nbsp;)** |**RGBA(&nbsp;112,&nbsp;128,&nbsp;144,&nbsp;1&nbsp;)** |![savenharmaa](./media/function-colors/color-slategray.png) |
| **Color.SlateGrey** |**ColorValue (”#708090”&nbsp;)**<br>**ColorValue (”slategrey”&nbsp;)** |**RGBA(&nbsp;112,&nbsp;128,&nbsp;144,&nbsp;1&nbsp;)** |![savenharmaa](./media/function-colors/color-slategrey.png) |
| **Color.Snow** |**ColorValue (”#fffafa”&nbsp;)**<br>**ColorValue (”lumi”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;250,&nbsp;250,&nbsp;1&nbsp;)** |![lumivalkoinen](./media/function-colors/color-snow.png) |
| **Color.SpringGreen** |**ColorValue (”#00ff7f”&nbsp;)**<br>**ColorValue (”SPRINGGREEN”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;255,&nbsp;127,&nbsp;1&nbsp;)** |![keväänvihreä](./media/function-colors/color-springgreen.png) |
| **Color.SteelBlue** |**ColorValue (”#4682b4”&nbsp;)**<br>**ColorValue (”SteelBlue”&nbsp;)** |**RGBA(&nbsp;70,&nbsp;130,&nbsp;180,&nbsp;1&nbsp;)** |![teräksensininen](./media/function-colors/color-steelblue.png) |
| **Color.Tan** |**ColorValue (”#d2b48c”&nbsp;)**<br>**ColorValue (”tan”&nbsp;)** |**RGBA(&nbsp;210,&nbsp;180,&nbsp;140,&nbsp;1&nbsp;)** |![keltaisenruskea](./media/function-colors/color-tan.png) |
| **Color.Teal** |**ColorValue (”#008080”&nbsp;)**<br>**ColorValue (”sinivihreä”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;128,&nbsp;128,&nbsp;1&nbsp;)** |![sinivihreä](./media/function-colors/color-teal.png) |
| **Color.Thistle** |**ColorValue (”#d8bfd8”&nbsp;)**<br>**ColorValue (”OHDAKKEEN”&nbsp;)** |**RGBA(&nbsp;216,&nbsp;191,&nbsp;216,&nbsp;1&nbsp;)** |![ohdake](./media/function-colors/color-thistle.png) |
| **Color.Tomato** |**ColorValue (”#ff6347”&nbsp;)**<br>**ColorValue (”tomaatin”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;99,&nbsp;71,&nbsp;1&nbsp;)** |![tomaatti](./media/function-colors/color-tomato.png) |
| **Color.Transparent** |**ColorValue (”#00000000”&nbsp;)**<br>**ColorValue (”läpinäkyvä”&nbsp;)** |**RGBA(&nbsp;0,&nbsp;0,&nbsp;0,&nbsp;0&nbsp;)** |![läpinäkyvä](./media/function-colors/color-transparent.png) |
| **Color.Turquoise** |**ColorValue (”#40e0d0”&nbsp;)**<br>**ColorValue (”turkoosi”&nbsp;)** |**RGBA(&nbsp;64,&nbsp;224,&nbsp;208,&nbsp;1&nbsp;)** |![turkoosi](./media/function-colors/color-turquoise.png) |
| **Color.Violet** |**ColorValue (”#ee82ee”&nbsp;)**<br>**ColorValue (”Violet”&nbsp;)** |**RGBA(&nbsp;238,&nbsp;130,&nbsp;238,&nbsp;1&nbsp;)** |![violetti](./media/function-colors/color-violet.png) |
| **Color.Wheat** |**ColorValue( "#f5deb3"&nbsp;)**<br>**ColorValue (”osalta”&nbsp;)** |**RGBA(&nbsp;245,&nbsp;222,&nbsp;179,&nbsp;1&nbsp;)** |![vehnä](./media/function-colors/color-wheat.png) |
| **Color.White** |**ColorValue (”#ffffff”&nbsp;)**<br>**ColorValue (”valkoinen”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;255,&nbsp;255,&nbsp;1&nbsp;)** |![valkoinen](./media/function-colors/color-white.png) |
| **Color.WhiteSmoke** |**ColorValue (”#f5f5f5”&nbsp;)**<br>**ColorValue (”whitesmoke”&nbsp;)** |**RGBA(&nbsp;245,&nbsp;245,&nbsp;245,&nbsp;1&nbsp;)** |![savunvalkea](./media/function-colors/color-whitesmoke.png) |
| **Color.Yellow** |**ColorValue (”#ffff00”&nbsp;)**<br>**ColorValue (”keltainen”&nbsp;)** |**RGBA(&nbsp;255,&nbsp;255,&nbsp;0,&nbsp;1&nbsp;)** |![keltainen](./media/function-colors/color-yellow.png) |
| **Color.YellowGreen** |**ColorValue (”#9acd32”&nbsp;)**<br>**ColorValue (”YELLOWGREEN”&nbsp;)** |**RGBA(&nbsp;154,&nbsp;205,&nbsp;50,&nbsp;1&nbsp;)** |![kellanvihreä](./media/function-colors/color-yellowgreen.png) |
