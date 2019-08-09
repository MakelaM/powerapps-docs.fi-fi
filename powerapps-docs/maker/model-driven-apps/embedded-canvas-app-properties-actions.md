---
title: ModelDrivenFormIntegration-ohjausobjektin ominaisuudet ja toiminnot | MicrosoftDocs
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
ms.assetid: 00e62904-2ce9-4730-a113-02b1fedbf22e
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
# <a name="modeldrivenformintegration-control-properties-and-actions"></a>ModelDrivenFormIntegration-ohjausobjektiominaisuudet ja toiminnot
Mallipohjaisia lomakkeita varten upotetut kaaviosovellukset sisältävät erityisen ohjausobjektin, jonka nimi on **ModelDrivenFormIntegration**. Tämä ohjausobjekti tuo kontekstitiedot mallipohjaisesta lomakkeesta upotettuun kaaviosovellukseen.  

Tässä aiheessa selitetään ModelDrivenFormIntegration-ohjausobjektin ominaisuudet ja toiminnot.

| Ominaisuudet vai toiminnot | Kuvaus |
|:--------------|:-------------------------|
|**DataSource** | On asetettava tietolähteeseen, joka on liitetty malliin perustuvan isäntälomakkeen pääentiteettiin. <br />Määritä automaattisesti [upotettaessa uusi kaaviosovellus](embedded-canvas-app-add-classic-designer.md). |
|**Kohde** | Vain luku -ominaisuus, joka mahdollistaa upotetun kaaviosovelluksen käyttöoikeudet tietueeseen mallipohjaisen isäntälomakkeen avulla. <br />Jos esimerkiksi haluat saada kentän arvon nimellä accountnumber ja näyttönimellä Tilinumero, voit käyttää ominaisuuksia ModelDrivenFormIntegration.Item.accountnumber tai ModelDrivenFormIntegration.Item.'Account Number. |
|**OnDataRefresh** | Tämän ominaisuuden kaavaa arvioidaan, kun malliin perustuva isäntälomake tallentaa tietoja. <br />Sen avulla voit päivittää malliin perustuvan isäntälomakkeen pääentiteettiin liitetyn tietolähteen ja suorittaa muita toimintoja, kuten muuttujien määrittämistä tai päivittämistä. <br /> Jos määrität sen esimerkiksi alla olevaan kaavaan, se päivittää asiakastietolähteen ja määrittää CurrentAccountNumber-nimisen muuttujan nykyisen tietueen tilinumerokentän arvoksi. <br /> Refresh(Accounts); Set(CurrentAccountNumber, ModelDrivenFormIntegration.Item.'Account Number') |
|**RefreshForm** | Päivittää mallipohjaisen isäntälomakkeen tiedot. <br />Lisätietoja on kohdassa [Ennalta määritettyjen toimintojen suorittaminen isäntälomakkeessa](embedded-canvas-app-actions.md#refreshformshowprompt). |
|**SaveForm** | Tallentaa mallipohjaisen isäntälomakkeen tiedot. <br />Lisätietoja on kohdassa [Ennalta määritettyjen toimintojen suorittaminen isäntälomakkeessa](embedded-canvas-app-actions.md#saveform).  |
|**NavigateToMainForm** | Siirtyy mallipohjaista isäntälomakkeesta päälomakkeeseen ja näyttää määritetyn tietueen. <br />Lisätietoja on kohdassa [Ennalta määritettyjen toimintojen suorittaminen isäntälomakkeessa](embedded-canvas-app-actions.md#navigatetomainformentityname-mainformname-recordid). |
|**NavigateToView** | Siirtyy näkymän mallipohjaiseen isäntälomakkeeseen. <br />Lisätietoja on kohdassa [Ennalta määritettyjen toimintojen suorittaminen isäntälomakkeessa](embedded-canvas-app-actions.md#navigatetoviewentityname-viewname).  |
|**OpenQuickCreateForm** | Avaa entiteetin oletuspikaluontilomakkeen.  <br />Lisätietoja on kohdassa [Ennalta määritettyjen toimintojen suorittaminen isäntälomakkeessa](embedded-canvas-app-actions.md#openquickcreateformentityname).  |
|**Tiedot** | Kehyksen käyttämä vain luku -ominaisuus, joka lähettää joitakin tärkeitä tietoja mallipohjaisesta isäntälomakkeesta upotettuun kaaviosovellukseen.  <br /> Älä käytä tätä ominaisuutta. Käytä nimikettä, kun haluat käyttää tietuetta mallipohjaisesta isäntälomakkeesta.  |

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Upotetun kaaviosovelluksen lisääminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-add-classic-designer.md) <br />
[Upotetun kaaviosovelluksen muokkaaminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-edit-classic-designer.md) <br />
[Mallin mukaiseen lomakkeeseen upotetun kaaviosovelluksen näytön koon ja suunnan mukauttaminen](embedded-canvas-app-customize-screen.md) <br />
[Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa](embedded-canvas-app-actions.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md) <br />
[Upotettujen kaaviosovellusten käsittelyohjeita](embedded-canvas-app-guidelines.md) <br />
[Upotettujen kaaviosovellusten siirtäminen mallipohjaisista lomakkeista, jotka on luotu julkista esikatseluversiota käyttäen uusimpaan](embedded-canvas-app-migrate-from-preview.md) <br />
