---
title: Upotetun kaaviosovelluksen jakaminen | MicrosoftDocs
ms.custom: ''
ms.date: 01/07/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="share-an-embedded-canvas-app"></a>Upotetun sovelluksen jakaminen
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Tässä ohjeaiheessa käsitellään aiemmin luodun upotetun kaaviosovelluksen jakamista.

Kun upotettu kaaviosovellus on luotu ja lisätty mallipohjaiseen lomakkeeseen, sinun on varmistettava, että kaikki käyttäjät, jotka saavat käyttää mallipohjaista sovellusta, voivat käyttää myös kaaviosovellusta ja sen käyttämiä tietoja. Käytä seuraavaa ohjeistusta:
-   Jaa upotettu kaaviosovellus organisaatiossa kaikkien kanssa tai vain käyttöoikeusryhmän tai tiettyjen käyttäjien kanssa. Lisätietoja: [Sovelluksen jakaminen](../canvas-apps/share-app.md#share-an-app).
-   Varmista, että käyttäjillä on upotetun kaaviosovellusten käyttämien Common Data Service -entiteettien tarvittavat oikeudet. Lisätietoja: [Entiteetin oikeuksien hallinta](../canvas-apps/share-app.md#manage-entity-permissions)
-   Varmista, että käyttäjillä on upotetun kaaviosovellusten käyttämien pilvipalvelujen, kuten Sharepointin tai OneDriven, tietojen tarvittavat oikeudet. Jakamista koskevat ohjeet ovat pilvipalvelukohtaisia, eivätkä ne liity PowerAppsiin.

> [!NOTE]
> Tällä hetkellä et voi myöntää käyttöoikeusroolin **Kaaviosovellus**-oikeuden avulla sovelluksen käyttäjille upotetun etkä erillisen kaaviosovelluksen käyttöoikeutta.

Upotetut kaaviosovellukset ovat myös ratkaisukohtaisia. Upotetut kaaviosovellukset luodaan oletusarvoisesti samassa ratkaisussa kuin mallipohjainen isäntälomake. Upotetun kaaviosovelluksen voi siirtää ympäristöstä toiseen viemällä ja tuomalla upotetun kaaviosovelluksen ratkaisun osana muiden osien tavoin.

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Nykyisen tietueen välittäminen tietokontekstina upotettuun kaaviosovellukseen](pass-current-embedded-canvas-app.md) <br />
[Liittyvien tietueiden luettelon välittäminen tietokontekstina upotettuun kaaviosovellukseen](pass-related-embedded-canvas-app.md) <br />
[Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa](embedded-canvas-app-actions.md) <br />
[Upotettujen kaaviosovellusten käsittelyohjeita](embedded-canvas-app-guidelines.md)
