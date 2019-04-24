---
title: 'Tekstimuotoilueditorin ohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja, kuten ominaisuudet ja esimerkkejä, tekstimuotoilueditorin ohjausobjektista
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/24/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3174d959a2360b36e82cd7070c4401251ca9fe18
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61526259"
---
# <a name="rich-text-editor-control-in-powerapps"></a>Rich text ohjausobjekti powerappsissa
Sallii käyttäjien muotoilla tekstiä WYSIWYG-muokkausalueen sisällä.  Tulostemuoto on HTML.

## <a name="description"></a>Kuvaus
**Tekstimuotoilueditori**-ohjausobjekti tarjoaa sovelluksen käyttäjälle WYSIWYG-muokkausalueen tekstin muotoilemista varten.  Ohjausobjektin syöte- ja tulostemuoto on HTML.

Ohjausobjektin avulla kopioitu muotoiltu teksti (eli selaimesta tai Wordista peräisin oleva) voidaan liittää ohjausobjektiin.  

Ohjausobjektin käyttötarkoitus on muotoilla tekstiä, eikä syöte-HTML:n eheyden säilymistä taata.  Editori poistaa kaikki komentosarjat, tyylit, objektit ja muut mahdollisesti vaarantavat tunnisteet.  Tämä tarkoittaa sitä, että jos muotoiltu teksti luotiin muualla kuin PowerAppsissa, se ei välttämättä näytä samalta kuin tuotteessa, jossa se luotiin.

Tällä hetkellä tuettuja ominaisuuksia ovat muun muassa seuraavat:
- Lihavointi, kursivointi, alleviivaus
- Tekstin väri, korostusväri
- Tekstin koko
- Numeroidut luettelot, luettelomerkeillä varustetut luettelot
- Hyperlinkit
- Muotoilun poistaminen

Jos haluat käyttää ohjausobjektia lomakkeen sisällä, valitse Muokkaa monirivistä tekstiä -kortti ja mukauta sitä lisäämällä RTE-ohjausobjekti.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Oletus](properties-core.md)** – Editorissa näkyvän ensimmäisen tekstiarvon syöteominaisuus.

**HtmlText** – Tuloksena saatavan HTML-muodossa olevan tekstin tulosteominaisuus.


## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Tulee kuvata liitteiden käyttötarkoituksen.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvä vai piilotettu.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **[AccessibleLabel](properties-accessibility.md)** on oltava läsnä.

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.

> [!TIP]
> Käytä **Alt + 0** aikana editorin on kohdistettu lisätietoja muiden pikanäppäimet.