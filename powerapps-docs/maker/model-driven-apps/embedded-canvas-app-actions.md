---
title: Toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa | MicrosoftDocs
ms.custom: ''
ms.date: 03/29/2019
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
# <a name="perform-predefined-actions-on-the-host-form-from-within-an-embedded-canvas-app"></a>Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa
Upotetut kaaviosovellukset mahdollistavat ennalta määritettyjen toimintojen suorittamisen isäntälomakkeessa. Näiden toimintojen avulla tekijät voivat siirtyä, päivittää ja tallentaa isäntälomakkeen. Näiden toimintojen avulla upotettu kaaviosovellus voi toimia lomakkeen ja mallipohjaisen sovelluksen aiempaa integroidumpana osana.  

> [!NOTE]
> Tämä ominaisuus on käytettävissä vain esiversiona. <br />
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)] 

**ModelDrivenFormIntegration**-objekti sisältää nyt seuraavat uudet menetelmät, joiden avulla tekijät voivat suorittaa toimintoja isäntälomakkeessa.  
  
### <a name="navigatetomainformentityname-mainformname-recordid"></a>NavigateToMainForm(entityName, mainFormName, recordId)
Siirtyy isäntälomakkeesta päälomakkeeseen ja näyttää määritetyn tietueen.  
* **entityName** - Pakollinen merkkijonoparametri, joka määrittää päälomakkeen pääentiteetin.  
* **formName** - Pakollinen merkkijonoparametri, joka määrittää sen päälomakkeen nimen, johon siirrytään.  
* **recordId** - Pakollinen merkkijonoparametri, joka määrittää päälomakkeessa näytettävän tietueen tunnuksen.  
 
NavigateToMainForm-menetelmän kutsuminen voi tuoda esille seuraavat virhesanomat.
  
| Virhesanoma | Vianmäärityksen ohjeet |
|:--------------|:-------------------------|
|**Entiteettiä ei löytynyt: *[EntityName]*** | Tarkista *entityName*-parametrin arvo ja varmista, että se on sallittu entiteetin nimi ja käyttäjällä on sen käyttöoikeus. |
|**Lomaketta ei löytynyt: *[FormName]*** | Tarkista *mainFormName*-parametrin arvo ja varmista, että se on sallittu päälomakkeen nimi ja käyttäjällä on sen käyttöoikeus. |
|**Ongelma ladattaessa tietuetta.** | Tarkista *recordId*-parametrin arvo ja varmista, että se on sallittu tietueen tunnus ja käyttäjällä on sen käyttöoikeus. |
  
  
### <a name="navigatetoviewentityname-viewname"></a>NavigateToView(entityName, viewName)
Siirtyy näkymän isäntälomakkeeseen.  
* **entityName** - Pakollinen merkkijonoparametri, joka määrittää näkymän pääentiteetin.  
* **viewName** - Pakollinen merkkijonoparametri, joka määrittää sen päälomakkeen nimen, johon siirrytään.  
 
NavigateToView-menetelmän kutsuminen voi tuoda esille seuraavat virhesanomat.
  
| Virhesanoma | Vianmäärityksen ohjeet |
|:--------------|:-------------------------|
|**Entiteettiä ei löytynyt: *[EntityName]*** | Tarkista *entityName*-parametrin arvo ja varmista, että se on sallittu entiteetin nimi ja käyttäjällä on sen käyttöoikeus. |
|**Näkymää ei löytynyt: *[ViewName]*** | Tarkista *viewName*-parametrin arvo ja varmista, että se on sallittu näkymän nimi ja käyttäjällä on sen käyttöoikeus. |
  
  
### <a name="openquickcreateformentityname"></a>OpenQuickCreateForm(entityName)  
Avaa entiteetin oletuspikaluontilomakkeen.  
* **entityName** - Pakollinen merkkijonoparametri, joka määrittää pikaluontilomakkeen pääentiteetin.  
 
OpenQuickCreateForm-menetelmän kutsuminen voi tuoda esille seuraavat virhesanomat.
  
| Virhesanoma | Vianmäärityksen ohjeet |
|:--------------|:-------------------------|
|**Entiteettiä ei löytynyt: *[EntityName]*** | Tarkista *entityName*-parametrin arvo ja varmista, että se on sallittu entiteetin nimi ja käyttäjällä on sen käyttöoikeus. |
  
  
### <a name="refreshformshowprompt"></a>RefreshForm(showPrompt)  
Päivittää isäntälomakkeen tiedot.  
* **showPrompt** - Pakollinen totuusarvoparametri, joka osoittaa, näytetäänkö vahvistuskehote käyttäjälle ennen isäntälomakkeen tallentamattomien tietojen tallentamista. Arvo voi olla Tosi tai Epätosi.
 
RefreshForm-menetelmän kutsuminen voi tuoda esille seuraavat virhesanomat.
  
| Virhesanoma | Vianmäärityksen ohjeet |
|:--------------|:-------------------------|
|**Käytä parametrin arvona tosi- tai epätosi-arvoa.** | Tarkista *showPrompt*-parametrin arvo ja varmista, että se on Tosi tai Epätosi. |
  
  
### <a name="saveform"></a>SaveForm()  
Tallentaa isäntälomakkeen tiedot.  


> [!NOTE]
> Jos IntelliSensessä ei näy niiden upotettujen kaaviosovellusten ennalta määritettyjen toimintojen suorittamisessa tarvittavia menetelmiä, jotka luotiin ennen kuin toiminnot olivat käytettävissä, tallenna ja sulje sovellus ja avaa se sitten uudelleen. 

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Nykyisen tietueen välittäminen tietokontekstina upotettuun kaaviosovellukseen](pass-current-embedded-canvas-app.md) <br />
[Liittyvien tietueiden luettelon välittäminen tietokontekstina upotettuun kaaviosovellukseen](pass-related-embedded-canvas-app.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md) <br />
[Upotettujen kaaviosovellusten käsittelyohjeita](embedded-canvas-app-guidelines.md)
