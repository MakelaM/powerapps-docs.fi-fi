---
title: Color-luettelointi ja ColorFade-, ColorValue- ja RGBA-funktiot | Microsoft Docs
description: Viitetiedot Color-luetteloinnille ja ColorFade-, ColorValue- ja RGBA-funktioille, mukaan lukien syntaksi ja esimerkkejä
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 10/25/2015
ms.author: gregli
ms.openlocfilehash: f4eeabf5708fffa6881b84402280d5639d96cc0a
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="color-enumeration-and-colorfade-colorvalue-and-rgba-functions-in-powerapps"></a>Color-luettelointi ja ColorFade-, ColorValue- ja RGBA-funktiot PowerAppsissa
Valmiiden väriarvojen käyttäminen sekä mukautettujen värien ja alfasekoituksen määrittäminen.

## <a name="description"></a>Kuvaus
**Color**-luettelointi on helppo tapa käyttää värejä, jotka on määritetty HTML:n CSS-tyylimäärityksissä.  Esimerkiksi **Color.Red** palauttaa puhtaan punaisen värin.  Tämän artikkelin lopussa on luettelo näistä väreistä.   

**ColorValue**-funktio palauttaa CSS-värimerkkijonon mukaisen värin.  Voit käyttää sekä CSS-värien nimiä, kuten ”RosyBrown”, että heksadesimaaleja, kuten ”#bc8f8f”.

**RGBA**-funktio palauttaa värin, joka määritetään punaisen, vihreän ja sinisen värikomponentin yhdistelmänä.  Siihen sisältyy myös alfakomponentti, jota käytetään sekoitettaessa päällekkäisten kohteiden värejä.  Alfakomponentin arvo on välillä 0–1, missä 0 eli 0 % tarkoittaa täysin läpinäkyvää ja 1 eli 100 % tarkoittaa täysin läpinäkymätöntä väriä, joka peittää alla olevat tasot kokonaan.

**ColorFade**-funktio palauttaa värin sävyn kirkkaampana tai tummempana.  Häivytyksen määrän asetusalue on –1:stä (joka tummentaa värin täysin mustaksi) 0:aan (joka ei vaikuta väriin lainkaan) ja 1:een (joka kirkastaa värin kokonaan valkoiseksi).  

## <a name="syntax"></a>Syntaksi
**Color**.*ColorName*

* *ColorName* - Pakollinen.  CSS-tyylimäärityksen mukainen värin nimi.  Katso mahdolliset arvot alla olevasta luettelosta.

**ColorValue**( *CSSColor* )

* *CSSColor* – Pakollinen.  CSS-tyylimäärityksen mukainen värin määritys.  Voit käyttää sekä värien nimiä, kuten ”OliveDrab”, että heksadesimaaleja, kuten ”#6b8e23”.  

**RGBA**( *punainen*, *vihreä*, *sininen*, *alfa* )

* *Punainen*, *vihreä*, *sininen* – Pakollinen.  Värikomponenttiarvot 0 (ei värikylläisyyttä) – 255 (täysi värikylläisyys).
* *Alfa* – pakollinen.  Alfakomponentti väliltä 0 (täysin läpinäkyvä) – 1 (täysin läpinäkymätön).  Voit käyttää myös prosenttimäärää 0 % – 100 %.

**ColorFade**( *Color*, *FadeAmount* )

* *Color* – Pakollinen.  Väriarvo, kuten **Color.Red** tai **ColorValue**- tai **RGBA**-arvo.
* *FadeAmount* - Pakollinen.  Luku väliltä –1 ja 1.  –1 tummentaa värin kokonaan mustaksi, 0 ei vaikuta väriin ja 1 kirkastaa värin kokonaan valkoiseksi.  

## <a name="built-in-colors"></a>Valmiit värit
| Väriluettelointi | ColorValue esitettynä heksadesimaaleina | RGBA | Väriruutu |
| --- | --- | --- | --- |
| **Color.AliceBlue** |**ColorValue( "#f0f8ff" )** |**RGBA( 240, 248, 255, 1 )** |![erittäin vaalea sininen](./media/function-colors/color-aliceblue.png) |
| **Color.AntiqueWhite** |**ColorValue( "#faebd7" )** |**RGBA( 7, "250, 235,215, 1 )** |![antiikinvalkoinen](./media/function-colors/color-antiquewhite.png) |
| **Color.Aqua** |**ColorValue( "#00ffff" )** |**RGBA( 0, 255, 255, 1 )** |![turkoosi](./media/function-colors/color-aqua.png) |
| **Color.Aquamarine** |**ColorValue( "#7fffd4" )** |**RGBA( 127, 255, 212, 1 )** |![vedenvihreä](./media/function-colors/color-aquamarine.png) |
| **Color.Azure** |**ColorValue (”#f0ffff”)** |**RGBA( 240, 255, 255, 1 )** |![asuurinsininen](./media/function-colors/color-azure.png) |
| **Color.Beige** |**ColorValue( "#f5f5dc" )** |**RGBA( 245, 245, 220, 1 )** |![beige](./media/function-colors/color-beige.png) |
| **Color.Bisque** |**ColorValue( "#ffe4c4" )** |**RGBA( 255, 228, 196, 1 )** |![vaaleanruskea](./media/function-colors/color-bisque.png) |
| **Color.Black** |**ColorValue( "#000000" )** |**RGBA( 0, 0, 0, 1 )** |![musta](./media/function-colors/color-black.png) |
| **Color.BlanchedAlmond** |**ColorValue( "#ffebcd" )** |**RGBA( 255, 235, 205, 1 )** |![kuorittu manteli](./media/function-colors/color-blanchedalmond.png) |
| **Color.Blue** |**ColorValue( "#0000ff" )** |**RGBA( 0, 0, 255, 1 )** |![sininen](./media/function-colors/color-blue.png) |
| **Color.BlueViolet** |**ColorValue( "#8a2be2" )** |**RGBA (138, 43, 226, 1)** |![sinivioletti](./media/function-colors/color-blueviolet.png) |
| **Color.Brown** |**ColorValue( "#a52a2a" )** |**RGBA( 165, 42, 42, 1 )** |![ruskea](./media/function-colors/color-brown.png) |
| **Color.Burlywood** |**ColorValue( "#deb887" )** |**RGBA( 222, 184, 135, 1 )** |![puunruskea](./media/function-colors/color-burlywood.png) |
| **Color.CadetBlue** |**ColorValue( "#5f9ea0" )** |**RGBA( 95, 158, 160, 1 )** |![kadetinsininen](./media/function-colors/color-cadetblue.png) |
| **Color.Chartreuse** |**ColorValue( "#7fff00" )** |**RGBA( 127, 255, 0, 1 )** |![keltavihreä](./media/function-colors/color-chartreuse.png) |
| **Color.Chocolate** |**ColorValue( "#d2691e" )** |**RGBA( 210, 105, 30, 1 )** |![suklaanruskea](./media/function-colors/color-chocolate.png) |
| **Color.Coral** |**ColorValue( "#ff7f50" )** |**RGBA( 255, 127, 80, 1 )** |![koralli](./media/function-colors/color-coral.png) |
| **Color.CornflowerBlue** |**ColorValue( "#6495ed" )** |**RGBA( 100, 149, 237, 1 )** |![ruiskukansininen](./media/function-colors/color-cornflowerblue.png) |
| **Color.Cornsilk** |**ColorValue( "#fff8dc" )** |**RGBA( 255, 248, 220, 1 )** |![maissinkeltainen](./media/function-colors/color-cornsilk.png) |
| **Color.Crimson** |**ColorValue( "#dc143c" )** |**RGBA( 220, 20, 60, 1 )** |![karmiininpunainen](./media/function-colors/color-crimson.png) |
| **Color.Cyan** |**ColorValue( "#00ffff" )** |**RGBA( 0, 255, 255, 1 )** |![syaani](./media/function-colors/color-cyan.png) |
| **Color.DarkBlue** |**ColorValue( "#00008b" )** |**RGBA( 0, 0, 139, 1 )** |![tummansininen](./media/function-colors/color-darkblue.png) |
| **Color.DarkCyan** |**ColorValue( "#008b8b" )** |**RGBA( 0, 139, 139, 1 )** |![tumma syaani](./media/function-colors/color-darkcyan.png) |
| **Color.DarkGoldenRod** |**ColorValue( "#b8860b" )** |**RGBA( 184, 134, 11, 1 )** |![tumma kultapiisku](./media/function-colors/color-darkgoldenrod.png) |
| **Color.DarkGray** |**ColorValue( "#a9a9a9" )** |**RGBA( 169, 169, 169, 1 )** |![tummanharmaa](./media/function-colors/color-darkgray.png) |
| **Color.DarkGreen** |**ColorValue( "#006400" )** |**RGBA( 0, 100, 0, 1 )** |![tummanvihreä](./media/function-colors/color-darkgreen.png) |
| **Color.DarkGrey** |**ColorValue( "#a9a9a9" )** |**RGBA( 169, 169, 169, 1 )** |![tummanharmaa](./media/function-colors/color-darkgrey.png) |
| **Color.DarkKhaki** |**ColorValue( "#bdb76b" )** |**RGBA( 189, 183, 107, 1 )** |![tumma khaki](./media/function-colors/color-darkkhaki.png) |
| **Color.DarkMagenta** |**ColorValue( "#8b008b" )** |**RGBA( 139, 0, 139, 1 )** |![tumma magenta](./media/function-colors/color-darkmagenta.png) |
| **Color.DarkOliveGreen** |**ColorValue( "#556b2f" )** |**RGBA( 85, 107, 47, 1 )** |![tumma oliivinvihreä](./media/function-colors/color-darkolivegreen.png) |
| '**Color.DarkOrange** |**ColorValue( "#ff8c00" )** |**RGBA( 255, 140, 0, 1 )** |![tummanoranssi](./media/function-colors/color-darkorange.png) |
| **Color.DarkOrchid** |**ColorValue( "#9932cc" )** |**RGBA( 153, 50, 204, 1 )** |![tumma orkidea](./media/function-colors/color-darkorchid.png) |
| **Color.DarkRed** |**ColorValue( "#8b0000" )** |**RGBA( 139, 0, 0, 1 )** |![tummanpunainen](./media/function-colors/color-darkred.png) |
| **Color.DarkSalmon** |**ColorValue( "#e9967a" )** |**RGBA( 233, 150, 122, 1 )** |![tumma lohenpunainen](./media/function-colors/color-darksalmon.png) |
| **Color.DarkSeaGreen** |**ColorValue( "#8fbc8f" )** |**RGBA( 143, 188, 143, 1 )** |![tumma merenvihreä](./media/function-colors/color-darkseagreen.png) |
| **Color.DarkSlateBlue** |**ColorValue( "#483d8b" )** |**RGBA( 72, 61, 139, 1 )** |![tumma siniharmaa](./media/function-colors/color-darkslateblue.png) |
| **Color.DarkSlateGray** |**ColorValue( "#2f4f4f" )** |**RGBA( 47, 79, 79, 1 )** |![tumma savenharmaa](./media/function-colors/color-darkslategray.png) |
| **Color.DarkSlateGrey** |**ColorValue( "#2f4f4f" )** |**RGBA( 47, 79, 79, 1 )** |![tumma savenharmaa](./media/function-colors/color-darkslategrey.png) |
| **Color.DarkTurquoise** |**ColorValue( "#00ced1" )** |**RGBA( 0, 206, 209, 1 )** |![tumma turkoosi](./media/function-colors/color-darkturquoise.png) |
| **Color.DarkViolet** |**ColorValue( "#9400d3" )** |**RGBA( 148, 0, 211, 1 )** |![tummanvioletti](./media/function-colors/color-darkviolet.png) |
| **Color.DeepPink** |**ColorValue( "#ff1493" )** |**RGBA( 255, 20, 147, 1 )** |![syvä vaaleanpunainen](./media/function-colors/color-deeppink.png) |
| **Color.DeepSkyBlue** |**ColorValue( "#00bfff" )** |**RGBA( 0, 191, 255, 1 )** |![tumma taivaansininen](./media/function-colors/color-deepskyblue.png) |
| **Color.DimGray** |**ColorValue( "#696969" )** |**RGBA( 105, 105, 105, 1 )** |![himmeänharmaa](./media/function-colors/color-dimgray.png) |
| **Color.DimGrey** |**ColorValue( "#696969" )** |**RGBA( 105, 105, 105, 1 )** |![himmeänharmaa](./media/function-colors/color-dimgrey.png) |
| **Color.DodgerBlue** |**ColorValue( "#1e90ff" )** |**RGBA( 30, 144, 255, 1 )** |![kirkkaansininen](./media/function-colors/color-dodgerblue.png) |
| **Color.FireBrick** |**ColorValue( "#b22222" )** |**RGBA( 178, 34, 34, 1 )** |![poltettu tiili](./media/function-colors/color-firebrick.png) |
| **Color.FloralWhite** |**ColorValue( "#fffaf0" )** |**RGBA( 255, 250, 240, 1 )** |![kukanvalkoinen](./media/function-colors/color-floralwhite.png) |
| **Color.ForestGreen** |**ColorValue( "#228b22" )** |**RGBA( 34, 139, 34, 1 )** |![metsänvihreä](./media/function-colors/color-forestgreen.png) |
| **Color.Fuchsia** |**ColorValue( "#ff00ff" )** |**RGBA( 255, 0, 255, 1 )** |![aniliini](./media/function-colors/color-fuchsia.png) |
| **Color.Gainsboro** |**ColorValue( "#dcdcdc" )** |**RGBA( 220, 220, 220, 1 )** |![gainsboro](./media/function-colors/color-gainsboro.png) |
| **Color.GhostWhite** |**ColorValue( "#f8f8ff" )** |**RGBA( 248, 248, 255, 1 )** |![lakananvalkoinen](./media/function-colors/color-ghostwhite.png) |
| **Color.Gold** |**ColorValue( "#ffd700" )** |**RGBA( 255, 215, 0, 1 )** |![kulta](./media/function-colors/color-gold.png) |
| **Color.GoldenRod** |**ColorValue( "#daa520" )** |**RGBA( 218, 165, 32, 1 )** |![kultapiisku](./media/function-colors/color-goldenrod.png) |
| **Color.Gray** |**ColorValue( "#808080" )** |**RGBA( 128, 128, 128, 1 )** |![harmaa](./media/function-colors/color-gray.png) |
| **Color.Green** |**ColorValue( "#008000" )** |**RGBA( 0, 128, 0, 1 )** |![vihreä](./media/function-colors/color-green.png) |
| **Color.GreenYellow** |**ColorValue( "#adff2f" )** |**RGBA( 173, 255, 47, 1 )** |![vihreänkeltainen](./media/function-colors/color-greenyellow.png) |
| **Color.Grey** |**ColorValue( "#808080" )** |**RGBA( 128, 128, 128, 1 )** |![harmaa](./media/function-colors/color-grey.png) |
| **Color.Honeydew** |**ColorValue( "#f0fff0" )** |**RGBA( 240, 255, 240, 1 )** |![hunajameloni](./media/function-colors/color-honeydew.png) |
| **Color.HotPink** |**ColorValue( "#ff69b4" )** |**RGBA( 255, 105, 180, 1 )** |![pinkki](./media/function-colors/color-hotpink.png) |
| **Color.IndianRed** |**ColorValue (”#cd5c5c”)** |**RGBA( 205, 92, 92, 1 )** |![intianpunainen](./media/function-colors/color-indianred.png) |
| **Color.Indigo** |**ColorValue( "#4b0082" )** |**RGBA( 75, 0, 130, 1 )** |![indigonsininen](./media/function-colors/color-indigo.png) |
| **Color.Ivory** |**ColorValue( "#fffff0" )** |**RGBA( 255, 255, 240, 1 )** |![norsunluu](./media/function-colors/color-ivory.png) |
| **Color.Khaki** |**ColorValue( "#f0e68c" )** |**RGBA( 240, 230, 140, 1 )** |![khaki](./media/function-colors/color-khaki.png) |
| **Color.Lavender** |**ColorValue (”#e6e6fa”)** |**RGBA( 230, 230, 250, 1 )** |![laventeli](./media/function-colors/color-lavender.png) |
| **Color.LavenderBlush** |**ColorValue( "#fff0f5" )** |**RGBA( 255, 240, 245, 1 )** |![laventelinsininen](./media/function-colors/color-lavenderblush.png) |
| **Color.LawnGreen** |**ColorValue( "#7cfc00" )** |**RGBA( 124, 252, 0, 1 )** |![ruohonvihreä](./media/function-colors/color-lawngreen.png) |
| **Color.LemonChiffon** |**ColorValue( "#fffacd" )** |**RGBA( 255, 250, 205, 1 )** |![sitruunankeltainen](./media/function-colors/color-lemonchiffon.png) |
| **Color.LightBlue** |**ColorValue( "#add8e6" )** |**RGBA( 173, 216, 230, 1 )** |![vaaleansininen](./media/function-colors/color-lightblue.png) |
| **Color.LightCoral** |**ColorValue( "#f08080" )** |**RGBA( 240, 128, 128, 1 )** |![vaalea koralli](./media/function-colors/color-lightcoral.png) |
| **Color.LightCyan** |**ColorValue( "#e0ffff" )** |**RGBA( 224, 255, 255, 1 )** |![vaalea syaani](./media/function-colors/color-lightcyan.png) |
| **Color.LightGoldenRodYellow** |**ColorValue( "#fafad2" )** |**RGBA( 250, 250, 210, 1 )** |![vaalea kultapiiskunkeltainen](./media/function-colors/color-lightgoldenrodyellow.png) |
| **Color.LightGray** |**ColorValue( "#d3d3d3" )** |**RGBA( 211, 211, 211, 1 )** |![vaaleanharmaa](./media/function-colors/color-lightgray.png) |
| **Color.LightGreen** |**ColorValue( "#90ee90" )** |**RGBA( 144, 238, 144, 1 )** |![vaaleanvihreä](./media/function-colors/color-lightgreen.png) |
| **Color.LightGrey** |**ColorValue( "#d3d3d3" )** |**RGBA( 211, 211, 211, 1 )** |![vaaleanharmaa](./media/function-colors/color-lightgrey.png) |
| **Color.LightPink** |**ColorValue( "#ffb6c1" )** |**RGBA( 255, 182, 193, 1 )** |![vaalea pinkki](./media/function-colors/color-lightpink.png) |
| **Color.LightSalmon** |**ColorValue( "#ffa07a" )** |**RGBA( 255, 160, 122, 1 )** |![vaalea lohenpunainen](./media/function-colors/color-lightsalmon.png) |
| **Color.LightSeaGreen** |**ColorValue( "#20b2aa" )** |**RGBA( 32, 178, 170, 1 )** |![vaalea merenvihreä](./media/function-colors/color-lightseagreen.png) |
| **Color.LightSkyBlue** |**ColorValue (”#87cefa”)** |**RGBA( 135, 206, 250, 1 )** |![vaalea taivaansininen](./media/function-colors/color-lightskyblue.png) |
| **Color.LightSlateGray** |**ColorValue (”#778899”)** |**RGBA( 119, 136, 153, 1 )** |![vaalea savenharmaa](./media/function-colors/color-lightslategray.png) |
| **Color.LightSlateGrey** |**ColorValue (”#778899”)** |**RGBA( 119, 136, 153, 1 )** |![vaalea savenharmaa](./media/function-colors/color-lightslategrey.png) |
| **Color.LightSteelBlue** |**ColorValue( "#b0c4de" )** |**RGBA( 176, 196, 222, 1 )** |![vaalea teräksensininen](./media/function-colors/color-lightsteelblue.png) |
| **Color.LightYellow** |**ColorValue (”#ffffe0”)** |**RGBA( 255, 255, 224, 1 )** |![vaaleankeltainen](./media/function-colors/color-lightyellow.png) |
| **Color.Lime** |**ColorValue (”#00ff00”)** |**RGBA( 0, 255, 0, 1 )** |![keltavihreä](./media/function-colors/color-lime.png) |
| **Color.LimeGreen** |**ColorValue( "#32cd32" )** |**RGBA( 50, 205, 50, 1 )** |![limetinvihreä](./media/function-colors/color-limegreen.png) |
| **Color.Linen** |**ColorValue (”#faf0e6”)** |**RGBA( 250, 240, 230, 1 )** |![pellavanvaalea](./media/function-colors/color-linen.png) |
| **Color.Magenta** |**ColorValue( "#ff00ff" )** |**RGBA( 255, 0, 255, 1 )** |![magenta](./media/function-colors/color-magenta.png) |
| **Color.Maroon** |**ColorValue( "#800000" )** |**RGBA( 128, 0, 0, 1 )** |![kastanjanruskea](./media/function-colors/color-maroon.png) |
| **Color.MediumAquamarine** |**ColorValue (”#66cdaa”)** |**RGBA( 102, 205, 170, 1 )** |![keskivaalea vedenvihreä](./media/function-colors/color-mediumaquamarine.png) |
| **Color.MediumBlue** |**ColorValue (”#0000 cd”)** |**RGBA( 0, 0, 205, 1 )** |![keskivaalea sininen](./media/function-colors/color-mediumblue.png) |
| **Color.MediumOrchid** |**ColorValue (”#ba55d3”)** |**RGBA( 186, 85, 211, 1 )** |![keskivaalea orkidea](./media/function-colors/color-mediumorchid.png) |
| **Color.MediumPurple** |**ColorValue( "#9370db" )** |**RGBA( 147, 112, 219, 1 )** |![keskivaalea purppura](./media/function-colors/color-mediumpurple.png) |
| **Color.MediumSeaGreen** |**ColorValue( "#3cb371" )** |**RGBA( 60, 179, 113, 1 )** |![keskivaalea merenvihreä](./media/function-colors/color-mediumseagreen.png) |
| **Color.MediumSlateBlue** |**ColorValue (”#7b68ee”)** |**RGBA( 123, 104, 238, 1 )** |![keskivaalea siniharmaa](./media/function-colors/color-mediumslateblue.png) |
| **Color.MediumSpringGreen** |**ColorValue (”#00fa9a”)** |**RGBA( 0, 250, 154, 1 )** |![keskivaalea keväänvihreä](./media/function-colors/color-mediumspringgreen.png) |
| **Color.MediumTurquoise** |**ColorValue (”#48d1cc”)** |**RGBA( 72, 209, 204, 1 )** |![keskivaalea turkoosi](./media/function-colors/color-mediumturquoise.png) |
| **Color.MediumVioletRed** |**ColorValue( "#c71585" )** |**RGBA (199, 21, 133, 1)** |![keskivaalea lila](./media/function-colors/color-mediumvioletred.png) |
| **Color.MidnightBlue** |**ColorValue( "#191970" )** |**RGBA( 25, 25, 112, 1 )** |![yönsininen](./media/function-colors/color-midnightblue.png) |
| **Color.MintCream** |**ColorValue (”#f5fffa”)** |**RGBA( 245, 255, 250, 1 )** |![minttukreemi](./media/function-colors/color-mintcream.png) |
| **Color.MistyRose** |**ColorValue( "#ffe4e1" )** |**RGBA( 255, 228, 225, 1 )** |![utuinen ruusu](./media/function-colors/color-mistyrose.png) |
| **Color.Moccasin** |**ColorValue( "#ffe4b5" )** |**RGBA( 255, 228, 181, 1 )** |![nahanruskea](./media/function-colors/color-moccasin.png) |
| **Color.NavajoWhite** |**ColorValue( "#ffdead" )** |**RGBA( 255, 222, 173, 1 )** |![navajonvalkoinen](./media/function-colors/color-navajowhite.png) |
| **Color.Navy** |**ColorValue (”#000080”)** |**RGBA( 0, 0, 128, 1 )** |![laivastonsininen](./media/function-colors/color-navy.png) |
| **Color.OldLace** |**ColorValue( "#fdf5e6" )** |**RGBA( 253, 245, 230, 1 )** |![vanha pitsi](./media/function-colors/color-oldlace.png) |
| **Color.Olive** |**ColorValue (”#808000”)** |**RGBA( 128, 128, 0, 1 )** |![oliivi](./media/function-colors/color-olive.png) |
| **Color.OliveDrab** |**ColorValue (”#6b8e23”)** |**RGBA( 107, 142, 35, 1 )** |![oliivinruskea](./media/function-colors/color-olivedrab.png) |
| **Color.Orange** |**ColorValue( "#ffa500" )** |**RGBA( 255, 165, 0, 1 )** |![oranssi](./media/function-colors/color-orange.png) |
| **Color.OrangeRed** |**ColorValue( "#ff4500" )** |**RGBA( 255, 69, 0, 1 )** |![oranssinpunainen](./media/function-colors/color-orangered.png) |
| **Color.Orchid** |**ColorValue (”#da70d6”)** |**RGBA( 218, 112, 214, 1 )** |![orkidea](./media/function-colors/color-orchid.png) |
| **Color.PaleGoldenRod** |**ColorValue (”#eee8aa”)** |**RGBA( 238, 232, 170, 1 )** |![vaalea kultapiisku](./media/function-colors/color-palegoldenrod.png) |
| **Color.PaleGreen** |**ColorValue( "#98fb98" )** |**RGBA (152, 251, 152, 1)** |![hailakanvihreä](./media/function-colors/color-palegreen.png) |
| **Color.PaleTurquoise** |**ColorValue (”#afeeee”)** |**RGBA( 175, 238, 238, 1 )** |![vaalea turkoosi](./media/function-colors/color-paleturquoise.png) |
| **Color.PaleVioletRed** |**ColorValue( "#db7093" )** |**RGBA( 219, 112, 147, 1 )** |![vaalea lila](./media/function-colors/color-palevioletred.png) |
| **Color.PapayaWhip** |**ColorValue (”#ffefd5”)** |**RGBA( 255, 239, 213, 1 )** |![papaijavaahto](./media/function-colors/color-papayawhip.png) |
| **Color.PeachPuff** |**ColorValue( "#ffdab9" )** |**RGBA( 255, 218, 185, 1 )** |![persikka](./media/function-colors/color-peachpuff.png) |
| **Color.Peru** |**ColorValue( "#cd853f" )** |**RGBA( 205, 133, 63, 1 )** |![peru](./media/function-colors/color-peru.png) |
| **Color.Pink** |**ColorValue( "#ffc0cb" )** |**RGBA( 255, 192, 203, 1 )** |![vaaleanpunainen](./media/function-colors/color-pink.png) |
| **Color.Plum** |**ColorValue( "#dda0dd" )** |**RGBA( 221, 160, 221, 1 )** |![luumu](./media/function-colors/color-plum.png) |
| **Color.PowderBlue** |**ColorValue (”#b0e0e6”)** |**RGBA( 176, 224, 230, 1 )** |![harmaansininen](./media/function-colors/color-powderblue.png) |
| **Color.Purple** |**ColorValue( "#800080" )** |**RGBA( 128, 0, 128, 1 )** |![purppura](./media/function-colors/color-purple.png) |
| **Color.Red** |**ColorValue( "#ff0000" )** |**RGBA( 255, 0, 0, 1 )** |![punainen](./media/function-colors/color-red.png) |
| **Color.RosyBrown** |**ColorValue (”#bc8f8f”)** |**RGBA( 188, 143, 143, 1 )** |![punertavanruskea](./media/function-colors/color-rosybrown.png) |
| **Color.RoyalBlue** |**ColorValue (”#4169e1”)** |**RGBA( 65, 105, 225, 1 )** |![syvänsininen](./media/function-colors/color-royalblue.png) |
| **Color.SaddleBrown** |**ColorValue (”#8b4513”)** |**RGBA( 139, 69, 19, 1 )** |![satulanruskea](./media/function-colors/color-saddlebrown.png) |
| **Color.Salmon** |**ColorValue( "#fa8072" )** |**RGBA( 250, 128, 114, 1 )** |![lohenpunainen](./media/function-colors/color-salmon.png) |
| **Color.SandyBrown** |**ColorValue( "#f4a460" )** |**RGBA( 244, 164, 96, 1 )** |![hiekanruskea](./media/function-colors/color-sandybrown.png) |
| **Color.SeaGreen** |**ColorValue (”#2e8b57”)** |**RGBA( 46, 139, 87, 1 )** |![merenvihreä](./media/function-colors/color-seagreen.png) |
| **Color.SeaShell** |**ColorValue (”#fff5ee”)** |**RGBA( 255, 245, 238, 1 )** |![kotilo](./media/function-colors/color-seashell.png) |
| **Color.Sienna** |**ColorValue( "#a0522d" )** |**RGBA( 160, 82, 45, 1 )** |![siena](./media/function-colors/color-sienna.png) |
| **Color.Silver** |**ColorValue (”#c0c0c0”)** |**RGBA( 192, 192, 192, 1 )** |![hopea](./media/function-colors/color-silver.png) |
| **Color.SkyBlue** |**ColorValue (”#87ceeb”)** |**RGBA( 135, 206, 235, 1 )** |![taivaansininen](./media/function-colors/color-skyblue.png) |
| **Color.SlateBlue** |**ColorValue (”#6a5acd”)** |**RGBA( 106, 90, 205, 1 )** |![siniharmaa](./media/function-colors/color-slateblue.png) |
| **Color.SlateGray** |**ColorValue( "#708090" )** |**RGBA( 112, 128, 144, 1 )** |![savenharmaa](./media/function-colors/color-slategray.png) |
| **Color.SlateGrey** |**ColorValue( "#708090" )** |**RGBA( 112, 128, 144, 1 )** |![savenharmaa](./media/function-colors/color-slategrey.png) |
| **Color.Snow** |**ColorValue( "#ff7f50" )** |**RGBA( 255, 250, 250, 1 )** |![lumivalkoinen](./media/function-colors/color-snow.png) |
| **Color.SpringGreen** |**ColorValue( "#00ff7f" )** |**RGBA( 0, 255, 127, 1 )** |![keväänvihreä](./media/function-colors/color-springgreen.png) |
| **Color.SteelBlue** |**ColorValue( "#4682b4" )** |**RGBA( 70, 130, 180, 1 )** |![teräksensininen](./media/function-colors/color-steelblue.png) |
| **Color.Tan** |**ColorValue( "#d2b48c" )** |**RGBA( 210, 180, 140, 1 )** |![keltaisenruskea](./media/function-colors/color-tan.png) |
| **Color.Teal** |**ColorValue (”#008080”)** |**RGBA( 0, 128, 128, 1 )** |![sinivihreä](./media/function-colors/color-teal.png) |
| **Color.Thistle** |**ColorValue( "#d8bfd8" )** |**RGBA( 216, 191, 216, 1 )** |![ohdake](./media/function-colors/color-thistle.png) |
| **Color.Tomato** |**ColorValue( "#ff6347" )** |**RGBA( 255, 99, 71, 1 )** |![tomaatti](./media/function-colors/color-tomato.png) |
| **Color.Turquoise** |**ColorValue (”#40e0d0”)** |**RGBA( 64, 224, 208, 1 )** |![turkoosi](./media/function-colors/color-turquoise.png) |
| **Color.Violet** |**ColorValue (”#ee82ee”)** |**RGBA( 238, 130, 238, 1 )** |![violetti](./media/function-colors/color-violet.png) |
| **Color.Wheat** |**ColorValue( "#f5deb3" )** |**RGBA( 245, 222, 179, 1 )** |![vehnä](./media/function-colors/color-wheat.png) |
| **Color.White** |**ColorValue( "#fff8dc" )** |**RGBA( 255, 255, 255, 1 )** |![valkoinen](./media/function-colors/color-white.png) |
| **Color.WhiteSmoke** |**ColorValue( "#f5f5f5" )** |**RGBA( 245, 245, 245, 1 )** |![savunvalkea](./media/function-colors/color-whitesmoke.png) |
| **Color.Yellow** |**ColorValue( "#ffff00" )** |**RGBA( 255, 255, 0, 1 )** |![keltainen](./media/function-colors/color-yellow.png) |
| **Color.YellowGreen** |**ColorValue (”#9acd32”)** |**RGBA( 154, 205, 50, 1 )** |![kellanvihreä](./media/function-colors/color-yellowgreen.png) |

