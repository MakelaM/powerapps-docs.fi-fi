---
title: Malliin perustuvien sovelluslomakkeiden suunnitteleminen ja luominen | MicrosoftDocs
ms.custom: ''
ms.date: 06/26/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.assetid: 99c795e0-9165-4112-85b1-6b5e1a4aa5ec
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags:
- Links to topic not migrated
ms.openlocfilehash: ed51d04919c6316c827b0286eefaaccdf539c6ef
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681494"
---
# <a name="create-and-design-model-driven-app-forms"></a>Malliin perustuvien sovelluslomakkeiden suunnitteleminen ja luominen 

PowerAppsin lomakkeet tarjoavat käyttöliittymän, jossa käyttäjät voivat käyttää tarvitsemiaan tietoja. On tärkeää, että käyttäjien käyttämät lomakkeet on suunniteltu siten, että niiden avulla voidaan etsiä ja antaa tarvittavia tietoja tehokkaasti. 

Oletusratkaisussa tai hallitsemattomassa ratkaisussa voit luoda uusia lomakkeita ja muokata olemassa olevia lomakkeita kaikille entiteeteille, jotka sallivat lomakkeiden mukauttamisen. Hallitsemattomassa ratkaisussa voit muokata ratkaisulle luodun hallitsemattoman mukautetun entiteetin hallittuja ominaisuuksia.
Jos käytät hallittua ratkaisua, et voi luoda uusia lomakkeita entiteeteille tai muokata niiden olemassa olevia lomakkeita. Jos hallitun ratkaisun entiteetin hallitut ominaisuudet on määritetty sallimaan mukauttaminen, voit kuitenkin lisätä lomakkeita tälle entiteetille ja muokata sen lomakkeita. 
  

<a name="BKMK_TypesOfForms"></a> 
## <a name="type-of-forms"></a>Lomaketyypit
Lomakkeita on erityyppisiä: kullakin tyypillä on omat tietyt toimintonsa tai oma käyttötarkoituksena. Lisätiedot: [PowerAppsin lomaketyypit](types-forms.md).  

  
<a name="BKMK_FormDifferencesByEntity"></a>   
## <a name="updated-versus-classic-entities"></a>Päivitetyt ja perinteiset entiteetit  
PowerApps tarjoaa monia vaihtoehtoja lomakkeiden suunnitteluun. Unified Interfacessa useimmat entiteetit päivitettiin, jotta ne soveltuvat paremmin laiteriippumattomalle käyttöliittymälle. Päivitetyt entiteetit sekä omat mukautetut entiteettisi tukevat Dynamics 365 for Tablets -sovellusta, liiketoimintaprosesseja ja liiketoimintasääntöjä. Kun käytät näitä entiteettejä, voit suunnitella ne kerran ja ottaa ne käyttöön kaikissa asiakasohjelmissa.  
  
Monet entiteetit, joita kutsumme tässä perinteisiksi entiteeteiksi, ovat kuitenkin ulkoasultaan ja toiminnoiltaan edelleen samanlaisia kuin vanhemmissa versioissa. Näitä entiteettejä käytetään harvemmin. Ne on lueteltu alla:  
  
||||||  
|-|-|-|-|-|  
|Osoite|Artikkeli|Artikkelin kommentti|Joukkopoistotoiminto|Yhteys|  
|Alennus|Alennusluettelo|Tiedoston sijainti|Sähköpostin liite|Seuraa|  
|Tavoite|Tavoitteen mittausarvo|Tuo lähdetiedosto|Laskutustuote|Tilaustuote|  
|Hinnasto|Jonon kohde|Tarjoustuote|Koontikenttä|Koontikysely|  
|Tallennettu näkymä|Palvelu|Palveluaktiviteetti|SharePoint-sivusto|Sivusto|  
|Alue|Yksikkö|Yksikköryhmä|||  
  
### <a name="related-topics"></a>Samankaltaiset ohjeartikkelit  
    
[Lomakejärjestyksen määrittäminen](assign-form-order.md) <br />
[Lomakkeiden käyttöoikeuksien hallinta](control-access-forms.md) <br />
[Päälomakkeiden ulkoasu eri asiakasohjelmissa](main-form-presentations.md) <br />
