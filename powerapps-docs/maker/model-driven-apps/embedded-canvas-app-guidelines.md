---
title: Upotettujen kaaviosovellusten käsittelyohjeita | MicrosoftDocs
ms.custom: ''
ms.date: 06/25/2019
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

# <a name="guidelines-on-working-with-embedded-canvas-apps"></a>Upotettujen kaaviosovellusten käsittelyohjeita
Tässä ohjeaiheessa on upotettujen kaaviosovellusten käsittelyohjeita sekä käteviä vihjeitä mahdollisten ongelmien vianmääritykseen.

-   Upotettuja kaaviosovelluksia tuetaan vain Unified Interface -mallipohjaisissa sovelluksissa.
-   Kussakin lomakkeessa voi ottaa käyttöön vain yhden upotetun kaaviosovelluksen. 
     - Lomakkeeseen voi lisätä useita upotettuja kaaviosovelluksia, mutta vain yksi niistä voi olla käytössä samanaikaisesti.
     - Jos yrität ottaa useita upotettuja kaaviosovelluksia käyttöön mallipohjaisessa lomakkeessa, saat seuraavan ilmoituksen: Lomakkeessa voidaan ottaa käyttöön vain yksi pohjasovellus.
     - Lisätietoja upotetun kaaviosovelluksen ottamisesta käyttöön tai sen poistamisesta käytöstä on kohdissa [Upotetun kaaviosovelluksen ottaminen käyttöön](#enable-an-embedded-canvas-app) ja [Upotetun kaaviosovelluksen poistaminen käytöstä](#disable-an-embedded-canvas-app).
-   Kun upotettu kaaviosovellus lisätään mallipohjaiseen lomakkeeseen, on käytettävä pakollista kenttää, koska siinä on aina arvo. Jos kentässä ei ole arvoa, upotettu kaaviosovellus ei päivity, kun mallipohjaisen isäntälomakkeen tiedot muuttuvat.
-   Mallipohjaisen lomakkeen julkaiseminen ei aiheuta myös upotetun kaaviosovelluksen julkaisemista.
     - Upotetut kaaviosovellukset on julkaistava erillään mallipohjaisesta isäntälomakkeesta. Lisätietoja: [Sovelluksen julkaiseminen](../canvas-apps/save-publish-app.md#publish-an-app).
-   Jos selaimen ponnahdusikkunoiden estotoiminto estää upotetun kaaviosovelluksen luomisen tai muokkaamisen avaamalla PowerApps Studion kaaviosovelluksen ohjausobjektin asetusten **Mukauta**-painikkeella, web.powerapps.com on otettava käyttöön tai ponnahdusikkunoiden estotoiminto on poistettava tilapäisesti käytöstä, jonka jälkeen on valittava **Mukauta** uudelleen.
-   Upotettuja kaaviosovelluksia ei näytetä uutta tietuetta luotaessa, sillä tietuekonteksti on välitettävä niihin.
-   ModelDrivenFormIntegration.Item-objekti on vain luku ‑muotoinen. 
     - Jos haluat kirjoittaa tietoja, sinun on käytettävä Common Data Service -yhdysohjelmaa. Lisätietoja: [Common Data Service](/connectors/commondataservice/)
-   Upotettuja kaaviosovelluksia voidaan luoda vain mallipohjaisessa isäntälomakkeessa. 
    - Aiemmin luotuja kaaviosovelluksia, jotka on upotettu malliin perustuviin lomakkeisiin, ei tueta tällä hetkellä.
    - Tuki, jolla aiemmin luotu kaaviosovellus upotetaan malliin perustuvaan lomakkeeseen sovellustunnuksen avulla, toimitetaan tulevassa päivityksessä.
- Jos tarkastelet upotetun kaaviosovelluksen sisältävää mallipohjaista lomaketta ja näkyvissä on virhesanoma, jonka mukaan sovellusta ei löytynyt, varmista, että upotettu kaaviosovellus on samassa ratkaisussa kuin mallipohjainen sovellus.
- Jos tarkastelet upotetun kaaviosovelluksen sisältävää mallipohjaista lomaketta ja näkyvissä on virhesanoma, jonka mukaan sinulla ei ilmeisesti ole tämän sovelluksen käyttöoikeutta ja kehottaa pyytämään, että omistaja jakaa sen kanssasi, varmista, että tekijä on jakanut upotetun kaaviosovelluksen kanssasi. Lisätietoja: [Upotetun kaaviosovelluksen jakaminen](share-embedded-canvas-app.md).

## <a name="enable-an-embedded-canvas-app"></a>Upotetun sovelluksen ottaminen käyttöön
1. Valitse kentän tai aliruudukon ohjausobjekti, joka on mukautettu näkymään upotettuna kaaviosovelluksena.
2. Valitse **Kentän ominaisuudet** -valintaikkunassa (tai aliruudukon **Määritä ominaisuudet** -valintaikkunassa) **Ohjausobjektit**-välilehti.
3. Valitse ensin ohjausobjektiluettelossa **Kaaviosovellus** ja sitten **Verkko**-asetus.
4. Valitse **OK**.

## <a name="disable-an-embedded-canvas-app"></a>Upotetun sovelluksen poistaminen käytöstä
1. Valitse kentän tai aliruudukon ohjausobjekti, joka on mukautettu näkymään upotettuna kaaviosovelluksena.
2. Valitse **Kentän ominaisuudet** -valintaikkunassa (tai aliruudukon **Määritä ominaisuudet** -valintaikkunassa) **Ohjausobjektit**-välilehti.
3. Valitse ensin ohjausobjektiluettelossa oletusohjausobjekti ja sitten **Verkko**-asetus.
4. Valitse **OK**.

## <a name="known-issues-and-limitations-with-embedded-canvas-apps"></a>Upotettujen kaaviosovellusten tunnetut ongelmat ja rajoitukset
- Kaaviosovelluksen mukautettua ohjausobjektia tuetaan vain **Verkko**-asiakasohjelmatyypin yhteydessä. Tällä hetkellä **Puhelin**- ja **Tabletti**-asiakasohjelmatyyppejä ei tueta.
- Et voi myöntää käyttöoikeusroolin **Kaaviosovellus**-oikeuden avulla sovelluksen käyttäjille upotetun etkä erillisen kaaviosovelluksen käyttöoikeutta. Lisätietoja upotetun kaaviosovelluksen jakamisesta: [Upotetun kaaviosovelluksen jakaminen](share-embedded-canvas-app.md).
- Jos kirjoitat takaisin samat mallipohjaisessa isäntälomakkeessa näytettävät tiedot, lomake jatkaa vanhojen tietojen näyttämistä päivittämiseen saakka. Tämän voi tehdä helposti käyttämällä [RefreshForm](embedded-canvas-app-actions.md#refreshformshowprompt)-menetelmää.

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Upotetun kaaviosovelluksen lisääminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-add-classic-designer.md) <br />
[Upotetun kaaviosovelluksen muokkaaminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-edit-classic-designer.md) <br />
[Mallin mukaiseen lomakkeeseen upotetun kaaviosovelluksen näytön koon ja suunnan mukauttaminen](embedded-canvas-app-customize-screen.md) <br />
[Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa](embedded-canvas-app-actions.md) <br />
[ModelDrivenFormIntegration-ohjausobjektin ominaisuudet ja toiminnot](embedded-canvas-app-properties-actions.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md) <br />
[Upotettujen kaaviosovellusten siirtäminen mallipohjaisista lomakkeista, jotka on luotu julkista esikatseluversiota käyttäen uusimpaan](embedded-canvas-app-migrate-from-preview.md) <br />
