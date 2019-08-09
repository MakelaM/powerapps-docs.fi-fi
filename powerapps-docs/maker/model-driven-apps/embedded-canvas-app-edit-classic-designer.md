---
title: Upotetun kaaviosovelluksen muokkaaminen malliin perustuvaan lomakkeeseen | MicrosoftDocs
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

# <a name="edit-a-canvas-app-embedded-on-a-model-driven-form"></a>Upotetun kaaviosovelluksen muokkaaminen malliin perustuvaan lomakkeeseen.
Tässä ohjeaiheessa kerrotaan, miten mallipohjaiseen lomakkeeseen upotettua kaaviosovellusta voidaan muokata.

## <a name="edit-the-canvas-app-directly"></a>Kaaviosovelluksen muokkaaminen suoraan
Voit muokata mallipohjaisen lomakkeen upotettua kaaviosovellusta samalla tavalla kuin mitä tahansa kaaviosovellusta. Jos haluat nähdä kaaviosovelluksen muokkausohjeita, katso: [Kaaviosovelluksen muokkaaminen](../canvas-apps/edit-app.md)

## <a name="edit-the-canvas-app-via-the-host-model-driven-form"></a>Kaaviosovelluksen muokkaaminen mallipohjaisen isäntälomakkeen kautta
Toinen vaihtoehto on muokata upotettua kaaviosovellusta mallipohjaisen isäntälomakkeen kautta.

Kuvittele, että haluat muokata upotettua kaaviosovellusta lomakkeesta, jonka nimi on Asiakkuuksien päälomake Asiakkuudet-entiteetissä. Voit tehdä tämän seuraavasti: 

1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.
2.  [Muokkaa lomaketta](create-and-edit-forms.md), joka on asiakkuuksien päälomake Asiakkuudet-entiteetissä. 
3.  Avaa lomake perinteisessä lomakkeen suunnitteluohjelmassa valitsemalla komentoriviltä **Vaihda perinteiseen**.
4.  Valitse perinteisessä lomakkeensuunnitteluohjelmassa kenttä, joka on mukautettu upotettavan kaaviosovelluksen näyttämiseksi.
5.  Kun kenttä on valittu, valitse ensin **Aloitus**-välilehti **Muokkaa**-ryhmässä ja sitten **Muuta ominaisuuksia**.
6.  Valitse **Kentän ominaisuudet** -valintaikkunassa **Ohjausobjektit**-välilehti.
7.  Valitse **Kentän ominaisuudet** -valintaikkunan ohjausobjektiluettelossa **Kaaviosovellus**.
8.  Muokkaa kaaviosovellusta valitsemalla ohjausobjektit-luettelon alapuolella olevassa osassa **Mukauta**. Tämä avaa kaaviosovelluksen muokkausta varten uudessa PowerApps Studio -välilehdessä.
       > [!NOTE]
       > Jos selaimen ponnahdusikkunan estotoiminto estää PowerApps Studion avaamisen, web.powerapps.com on otettava käyttöön tai ponnahdusikkunoiden estotoiminto on poistettava tilapäisesti käytöstä, ja **Mukauta** on valittava uudelleen.
9. Kun olet tehnyt haluamasi muutokset, valitse **Tiedosto**-välilehti ja valitse sitten **Tallenna**.
10. Muutokset ovat loppukäyttäjien käytettävissä, kun valitset ensin **Julkaise** ja sitten **Julkaise tämä versio**.

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Upotetun kaaviosovelluksen lisääminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-add-classic-designer.md) <br />
[Mallin mukaiseen lomakkeeseen upotetun kaaviosovelluksen näytön koon ja suunnan mukauttaminen](embedded-canvas-app-customize-screen.md) <br />
[Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa](embedded-canvas-app-actions.md) <br />
[ModelDrivenFormIntegration-ohjausobjektin ominaisuudet ja toiminnot](embedded-canvas-app-properties-actions.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md) <br />
[Upotettujen kaaviosovellusten käsittelyohjeita](embedded-canvas-app-guidelines.md) <br />
[Upotettujen kaaviosovellusten siirtäminen mallipohjaisista lomakkeista, jotka on luotu julkista esikatseluversiota käyttäen uusimpaan](embedded-canvas-app-migrate-from-preview.md) <br />
