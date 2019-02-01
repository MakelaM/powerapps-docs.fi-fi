---
title: Upotettujen kaaviosovellusten käsittelyohjeita | MicrosoftDocs
ms.custom: ''
ms.date: 01/07/2019
ms.reviewer: ''
ms.service: crm-online
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
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Tässä ohjeaiheessa on upotettujen kaaviosovellusten käsittelyohjeita sekä käteviä vihjeitä mahdollisten ongelmien vianmääritykseen.

-   Upotettuja kaaviosovelluksia tuetaan vain Unified Interface -mallipohjaisissa sovelluksissa.
-   Kussakin lomakkeessa voi ottaa käyttöön vain yhden upotetun kaaviosovelluksen. 
     - Lomakkeeseen voi lisätä useita upotettuja kaaviosovelluksia, mutta vain yksi niistä voi olla käytössä samanaikaisesti.
     - Jos yrität ottaa useita upotettuja kaaviosovelluksia käyttöön mallipohjaisessa lomakkeessa, saat seuraavan ilmoituksen: Lomakkeessa voidaan ottaa käyttöön vain yksi pohjasovellus.
     - Lisätietoja upotetun kaaviosovelluksen ottamisesta käyttöön tai sen poistamisesta käytöstä on kohdissa [Upotetun kaaviosovelluksen ottaminen käyttöön](#enable-an-embedded-canvas-app) ja [Upotetun kaaviosovelluksen poistaminen käytöstä](#disable-an-embedded-canvas-app).
-   Upotettuja kaaviosovelluksia voidaan luoda, muokata ja toistaa vain mallipohjaisessa isäntälomakkeessa.
     - Upotettua kaaviosovellusta ei voi luoda suoraan mallipohjaisen lomakkeen ulkopuolella.
     - Myöskään upotetun kaaviosovelluksen avaamista muokattavaksi tai toistettavaksi mallipohjaisen lomakkeen ulkopuolella ei tueta.

     > [!NOTE]
     > Vaikka upotetun kaaviosovelluksen avaaminen mallipohjoisen sovelluksen ulkopuolella onnistuisi, sitä ei tueta.

-   Ota seuraavat seikat huomioon, kun lisäät upotetun kaaviosovelluksen mallipohjaiseen lomakkeeseen aliruudukon ohjausobjektin avulla.
     - Upotettuun kaaviosovellukseen suorituksen aikana lähetettävät tiedot (kentät ja arvot) määritetään sen näkymän mukaan, joka on määritetty aliruudukon ohjausobjektin asetusten **Tietolähde**-kohdassa **oletusnäkymäksi**. Käytä vain tähän näkymään sisältyviä kenttiä upotetussa kaaviosovelluksessa tai lisää ne tarvittaessa näkymään. Jos kenttä ei sisälly näkymään, kentässä näkyy suorituksen aikana tyhjä arvo. 
     - Näkymän suodatusehtoja ei käytetä laatimisen aikana. Tämän vuoksi upotettuja kaaviosovelluksia laadittaessa näkyviä tietoja ei ole suodatettu, Kyse onkin muutaman sellaisen tärkeimmän tietueen luettelosta, joiden käyttöoikeus sinulla on. Näkymän suodatusehtoja käytetään suorituksen aikana odotetusti, ja vain olennaiset tiedot näytetään.
-   Jos upotettu kaaviosovellus lisätään mallipohjaiseen lomakkeeseen kentän ohjausobjektin avulla, on käytettävä pakollista kenttää, koska siinä on aina arvo. Jos kentässä ei ole arvoa, upotettu kaaviosovellus ei päivity, kun mallipohjaisen isäntälomakkeen tiedot muuttuvat.
-   Mallipohjaisen lomakkeen julkaiseminen ei aiheuta myös upotetun kaaviosovelluksen julkaisemista.
     - Upotetut kaaviosovellukset on julkaistava erillään mallipohjaisesta isäntälomakkeesta. Lisätietoja: [Sovelluksen julkaiseminen](../canvas-apps/save-publish-app.md#publish-an-app).
-   Jos selaimen ponnahdusikkunoiden estotoiminto estää upotetun kaaviosovelluksen luomisen tai muokkaamisen avaamalla PowerApps Studion kaaviosovelluksen ohjausobjektin asetusten **Mukauta**-painikkeella, web.powerapps.com on otettava käyttöön tai ponnahdusikkunoiden estotoiminto on poistettava tilapäisesti käytöstä, jonka jälkeen on valittava **Mukauta** uudelleen.
-   Upotettuja kaaviosovelluksia ei näytetä uutta tietuetta luotaessa, sillä tietuekonteksti on välitettävä niihin.
-   ModelDrivenFormIntegration.Data-objekti on vain luku ‑muotoinen. 
     - Jos haluat kirjoittaa tietoja, sinun on käytettävä Common Data Service -yhdysohjelmaa. Lisätietoja: [Common Data Service](/connectors/commondataservice/)
-   ModelDrivenFormIntegration.Data-objekti on tietueluettelo. 
     - Myös nykyinen tietue välitetään upotettuun kaaviosovellukseen yhden tietueen sisältävänä ModelDrivenFormIntegration.Data-luettelona.
     - Voit viitata suoraan tietueeseen käyttämällä [First-funktiota](../canvas-apps/functions/function-first-last.md). Esimerkki: First(ModelDrivenFormIntegration.Data).Name
-   Sovellustunnuksen muuttamista manuaalisesti kaaviosovelluksen ohjausobjektin ominaisuuksissa on syytä välttää, mikäli se suinkin on mahdollista.
     - Kaaviosovelluksen tunnus luodaan ja täytetään automaattisesti puolestasi. 
     - Jos sitä on jostain syystä muokattava manuaalisesti, muista varmistaa, että käytettävä sovellustunnus vastaa *upotettua* kaaviosovellusta eikä vain erillistä kaaviosovellusta.
     - Lisäksi upotettu kaaviosovellus on luotava siinä tietokontekstissa, jonka mallipohjainen lomake tulee lähettämään.
     - Kun olet päivittänyt sovellustunnuksen, muodosta yhteys uuteen sovellukseen valitsemalla **Mukauta**.
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
- Kaaviosovelluksen mukautettua ohjausobjektia tuetaan vain **Verkko**-asiakasohjelmatyypin yhteydessä. Tällä hetkellä **Puhelin**- ja **Tabletti**-asiakasohjelmatyyppejä ei tueta. Lisätietoja: [Mallipohjaisen sovelluksen tietojen visualisointien mukautettujen ohjausobjektien käyttäminen](use-custom-controls-data-visualizations.md)
- Kun luot uuden tietueen, lomakkeen upotettua kaaviosovellusta ei näytetä edes tietueen tallentamisen jälkeen. 
-    ModelDrivenFormIntegration.Data-objekti ei toimi tällä hetkellä lomakkeen näyttämisen ja muokkauksen ohjausobjektien kanssa.
- Et voi myöntää käyttöoikeusroolin **Kaaviosovellus**-oikeuden avulla sovelluksen käyttäjille upotetun etkä erillisen kaaviosovelluksen käyttöoikeutta. Lisätietoja upotetun kaaviosovelluksen jakamisesta: [Upotetun kaaviosovelluksen jakaminen](share-embedded-canvas-app.md).
- Jos kirjoitat takaisin samat mallipohjaisessa isäntälomakkeessa näytettävät tiedot, lomake jatkaa vanhojen tietojen näyttämistä päivittämiseen saakka. 

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Nykyisen tietueen välittäminen tietokontekstina upotettuun kaaviosovellukseen](pass-current-embedded-canvas-app.md) <br />
[Liittyvien tietueiden luettelon välittäminen tietokontekstina upotettuun kaaviosovellukseen](pass-related-embedded-canvas-app.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md)
