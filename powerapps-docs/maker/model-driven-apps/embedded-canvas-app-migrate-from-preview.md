---
title: 'Upotettujen kaaviosovellusten siirtäminen mallipohjaisista lomakkeista, jotka on luotu julkista esikatseluversiota käyttäen | MicrosoftDocs'
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

# <a name="migrate-embedded-canvas-apps-on-model-driven-forms-created-using-the-public-preview-release"></a>Upotettujen kaaviosovellusten siirtäminen mallipohjaisista lomakkeista, jotka on luotu julkista esikatseluversiota käyttäen
> [!IMPORTANT]
> Uusimman version ansiosta mallipohjaisten lomakkeiden upotetut kaaviosovellukset ovat yleensä käytettävissä. Kaikki julkista esikatseluversiota käyttäen luodut malliin perustuvia lomakkeita koskevat upotetut kaaviosovellukset on siirrettävä uusimpaan julkaisuun luotuihin uusiin upotettuihin kaaviosovelluksiin.
> Tuki julkisen esikatseluohjelman avulla luotujen mallipohjaisten lomakkeiden sulautetuille kaaviosovelluksille poistetaan pian. 

Jos haluat siirtää upotetun kaaviosovelluksen mallipohjaisen lomakkeen, joka on luotu yleisen esikatselun julkaisun avulla, tekijöiden on ensin luotava uusi upotettu kaaviosovellus käyttäen uusinta versiota. Tämän jälkeen tekijät voivat kopioida ohjausobjekteja aiemmin luodusta upotetusta kaaviosovelluksesta uuteen, lisätä tarvittavat tietolähteet ja päivittää mahdolliset katkenneet viittaukset. Yksityiskohtaiset ohjeet on esitetty alla.

1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.
2. Avaa upotettu kaaviosovellus, joka on luotu käyttämällä julkista esikatseluversiota PowerApps Studio -sovelluksessa muokkaamista varten. Jos haluat nähdä kaaviosovelluksen muokkausohjeita, katso: [Kaaviosovelluksen muokkaaminen](../canvas-apps/edit-app.md).
3. Noudata ohjeita, jotka liittyvät [upotetun kaaviosovelluksen lisäämiseen malliin perustuvan lomakkeen avulla](embedded-canvas-app-add-classic-designer.md).
4. Kopioi ohjausobjektit upotetusta kaaviosovelluksesta, joka on luotu käyttämällä julkista esijulkaisuversiota ja uutta upotettua kaaviosovellusta, yhden näytön kerrallaan alla olevien ohjeiden mukaisesti.
    1. Valitse selainvälilehti vaiheesta 2, jossa on upotettu kaaviosovellus, joka on luotu käyttämällä julkista esijulkaisuversiota, avoinna PowerApps Studioissa.
    2. Valitse näyttö, josta ohjausobjektit kopioidaan.
    3. Voit valita kaikki näytössä olevat ohjausobjektit painamalla **CTRL+A**.
    4. Kopioi kaikki valitut ohjausobjektit **CTRL+C**-näppäin yhdistelmällä.
    5. Valitse selainvälilehti vaiheesta 3, jossa on uusi upotettu kaaviosovellus, joka on luotu käyttämällä uusinta julkaisuversiota.
    6. Valitse näyttö tai lisää uusi.
    7. Liitä ohjausobjektit valittuun näyttöön **Ctrl+V**-näppäin yhdistelmällä.
    8. Kopioi kukin näyttö toistamalla vaiheet.
5. Kun olet kopioinut kaikki näytöt, valitse selainvälilehti vaiheesta 3, jossa on uusi upotettu kaaviosovellus, joka on luotu käyttämällä uusinta julkaisuversiota.
6. Päivitä kaikki sijainnit, joissa käytetään mallipohjaisen isäntälomakkeen tietuetta. Korvaa **First(ModelDrivenFormIntegration.Data)** kohteella **ModelDrivenFormIntegration.Item**.
7. Lisää puuttuvat tietolähteet uuteen upotettuun kaaviosovellukseen.
8. Päivitä kaikki katkenneet viittaukset uudessa upotetussa kaaviosovelluksessa. 
9. Kun olet tehnyt haluamasi muutokset, valitse **Tiedosto**-välilehti ja valitse sitten **Tallenna**.
10. Muutokset ovat loppukäyttäjien käytettävissä, kun valitset ensin **Julkaise** ja sitten **Julkaise tämä versio**.

## <a name="migrating-embedded-canvas-apps-on-model-driven-forms-that-use-a-list-of-records-related-to-the-current-main-form-record"></a>Upotettujen kaaviosovellusten siirtäminen mallipohjaisiin lomakkeisiin, jotka käyttävät nykyiseen (päälomakkeeseen) tietueeseen liittyviä tietueita

Esijulkaisuversiossa voit upottaa kaaviosovelluksen mallipohjaiseen lomakkeeseen, joten päättäjien oli päätettävä etukäteen, halusivatko he siirtää nykyisen (päälomakkeen) tietueen tietokontekstiin tai nykyiseen (päälomakkeeseen) tietueeseen liittyvien tietueiden luetteloon. Tämän jälkeen heidän täytyi lisätä kaaviosovelluksen ohjausobjekti joko kenttä- tai aliruudukko-ohjausobjektiin.

Uusimmassa versiossa upotettu kaaviosovellus voidaan lisätä mallipohjaisen lomakkeen avulla yksinkertaisemmaksi ja virtaviivaistetuksi vain kenttään. Tekijät voivat silti helposti käyttää toisiinsa liittyvien tietueiden luetteloa suoraan kaaviosovelluksessa Common Data Service -liitintä käyttämällä. 

Seuraa seuraavia ohjeita siirtääksesi upotetun kaaviosovelluksen mallipohjaiseen lomakkeeseen, joka käyttää nykyiseen (päälomakkeeseen) tietueeseen liittyviä tietueita.

1. Voit siirtää upotetut kaaviosovellukset uusimpiin esiversion avulla luotuihin mallipohjaisiin lomakkeisiin noudattamalla yllä olevan osion ohjeita.
2. Lisää Common Data Service -yhdistimen avulla sovellukseen liittyvä entiteetin tietolähde. Lisätietoja tietolähteen lisäämisestä kaaviosovellukseen on ohjeaiheessa [Tietoyhteyden lisääminen PowerApps-kaaviosovellukseen](../canvas-apps/add-data-connection.md).
3. Kun käytät liittyvän entiteetin tietolähdettä ohjausobjektiin, kuten [galleriaan](../canvas-apps/controls/control-gallery.md) tai [tietotaulukkoon](../canvas-apps/controls/control-data-table.md), käytä **[Suodata](../canvas-apps/functions/function-filter-lookup.md)**-toimintoa suodattaaksesi tietueet nykyiseen (päälomakkeeseen) tietueeseen liittyvistä tietueista. Nykyinen (päälomake) tietue on käytettävissä **ModelDrivenFormIntegration.Item**-kohteen kautta.
    > [!NOTE]
    > Upotetulla kaaviosovelluksella on täydet käyttöoikeudet, jotta se voidaan tallentaa mallipohjaisen lomakkeen avulla kohteen ModelDrivenFormIntegration.Item kautta. Jos esimerkiksi haluat saada kentän arvon nimellä **accountnumber** ja näyttönimellä **Tilinumero**, voit käyttää ominaisuuksia **ModelDrivenFormIntegration.Item.accountnumber** tai **ModelDrivenFormIntegration.Item.'Account Number**.
4. Uusimpien päivitysten myötä Common Data Service tukee nyt myös entiteettinäkymien käyttämistä suodattimena. Lisätietoja on tässä blogikirjoituksessa: [Parannettu tietolähteen valinta ja Common Data Service -näkymät](https://powerapps.microsoft.com/blog/improved-data-source-selection-and-common-data-service-views/). 

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Upotetun kaaviosovelluksen lisääminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-add-classic-designer.md) <br />
[Upotetun kaaviosovelluksen muokkaaminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-edit-classic-designer.md) <br />
[Mallin mukaiseen lomakkeeseen upotetun kaaviosovelluksen näytön koon ja suunnan mukauttaminen](embedded-canvas-app-customize-screen.md) <br />
[Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa](embedded-canvas-app-actions.md) <br />
[ModelDrivenFormIntegration-ohjausobjektin ominaisuudet ja toiminnot](embedded-canvas-app-properties-actions.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md) <br />
[Upotettujen kaaviosovellusten käsittelyohjeita](embedded-canvas-app-guidelines.md) <br />
