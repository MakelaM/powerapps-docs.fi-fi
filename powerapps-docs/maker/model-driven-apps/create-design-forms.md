---
title: Mallipohjaisen sovelluksen lomakkeiden luominen ja suunnittelu | MicrosoftDocs
ms.custom: ''
ms.date: 12/06/2018
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-design-model-driven-app-forms"></a>Mallipohjaisen sovelluksen lomakkeiden luominen ja suunnittelu 

PowerAppsin lomakkeissa on käyttöliittymä, jonka avulla käyttäjät voivat käyttää työssään tarvitsemiaan tietoja. On tärkeää, että ihmisten käyttämät lomakkeet on suunniteltu niin, että he löytävät tai pystyvät syöttämään tehokkaasti tarvitsemiaan tietoja. 

Voit luoda oletusratkaisussa tai hallitsemattomassa ratkaisussa uusia lomakkeita tai muokata lomakkeiden mukautuksen sallivien entiteettien aiemmin luotuja lomakkeita. Hallitsemattomassa ratkaisussa voit muokata ratkaisulle luodun hallitsemattoman mukautetun entiteetin hallittuja ominaisuuksia.
Hallitussa ratkaisussa ei voi luoda uusia lomakkeita eikä muokata entiteettien aiemmin luotuja lomakkeita. Jos hallittuun ratkaisuun kuuluvan entiteetin hallitut ominaisuudet on kuitenkin määritetty sallimaan mukauttaminen, voit lisätä tai muokata kyseisen entiteetin lomakkeita. 
  

<a name="BKMK_TypesOfForms"></a> 
## <a name="type-of-forms"></a>Lomakkeiden tyypit
Lomakkeiden tyyppejä on erilaisia. Jokaisella tyypillä on tiettyjä toimintoja tai käyttöjä. Lisätietoja: [Lomakkeiden tyyppi PowerAppsissa](types-forms.md).  

  
<a name="BKMK_FormDifferencesByEntity"></a>   
## <a name="updated-versus-classic-entities"></a>Päivitetyt ja perinteiset entiteetit  
PowerApps tarjoaa monia vaihtoehtoja lomakkeiden suunnittelemiseen. Useimmilla kohteilla on päivitetty vastaamaan reagoivaa käyttöliittymää Unified Interfacessa. Päivitetyt ja mukautetut entiteetit sisältävät Dynamics 365 for tablets -asiakasohjelman, -liiketoimintaprosessien ja -liiketoimintasääntöjen tuen. Kun käytä näitä entiteettejä, voit ottaa kerran suunnittelut entiteetit käyttöön kaikissa asiakasohjelmissa.  
  
Järjestelmässä on vielä useita entiteettejä (perinteiset entiteetit), joilla on aiempien versioiden ulkoasu ja ominaisuudet. Näiden entiteettejä käytetään harvemmin. Ne on lueteltu tässä:  
  
||||||  
|-|-|-|-|-|  
|Osoite|Artikkeli|Artikkelin kommentti|Joukkopoistotoiminto|Yhteys|  
|Alennus|Alennusluettelo|Tiedoston sijainti|Sähköpostiliite|Seuraa|  
|Tavoite|Tavoitteen mittausarvo|Tuonnin lähdetiedosto|Laskutustuote|Tilaustuote|  
|Hinnasto|Jonon kohde|Tarjoustuote|Koontikenttä|Koontikysely|  
|Tallennettu näkymä|Palvelu|Palveluaktiviteetti|SharePoint-sivusto|Sijainti|  
|Alue|Yksikkö|Yksikköryhmä|||  
  
## <a name="form-display-faq"></a>Lomakkeen näytön usein kysytyt kysymykset

### <a name="why-is-my-form-not-visible-in-the-form-selector-drop-down-in-my-app"></a>Miksi lomakkeeni ei näy sovelluksen lomakkeiden valinnan avattavassa luettelossa?
Lomake ei ehkä ole saatavissa, koska sitä ei ole lisätty sovellukseen.
1. Avaa sovellus sovellusten suunnitteluohjelmassa.
2. Valitse **Entiteettinäkymä**-alueella entiteetin vieressä oleva **Lomakkeet**-kohta.
3. Vahvista **Komponentit**-välilehden avulla, että sovellus sisältää päälomakkeet. Varmista, että näytettävä lomake on valittu. Jos sitä ei ole valittu, valitse se ja tallenna. Julkaise sovellus lopuksi.

   > [!div class="mx-imgBorder"] 
   > ![](media/forms-included-in-app.png "Sovellukseen lisätyt lomakkeet")
   
### <a name="why-isnt-my-form-displayed-as-the-default-form-in-the-app"></a>Miksi lomakkeeni ei näy sovelluksessa oletuslomakkeena?
Lomake voidaan määrittää oletuslomakkeeksi lomakkeiden järjestyksen määrityksessä tai silloin, kun käyttäjä määrittää oletuslomakkeen mukautusasetuksena.
1. Avaa ratkaisunhallinta. Laajenna entiteetti, joka sisältää järjestettävät lomakkeet, ja valitse sitten **Lomakkeet**.
2. Valitse työkalurivillä **Lomakejärjestys** > **Päälomakejoukko**. 

   > [!div class="mx-imgBorder"] 
   > ![](media/form-order-toolbar.png "Lomakejärjestyksen työkalurivin komento")
   
3. Lomakejärjestys tulee esille. Valitse lomake ja siirrä lomaketta ylä- ja alanuolien avulla lomakejärjestyksessä. Luettelon yläosassa oleva lomake on oletuslomake. 

   > [!div class="mx-imgBorder"] 
   > ![](media/form-order-dialog.png "Lomakejärjestys-valintaikkuna")
   
4. Valitse **OK**, kun haluat tallentaa lomakejärjestyksen muutokset.
5. Valitse lomakkeen suunnitteluohjelman työkalurivillä **Julkaise**, kun haluat lomakejärjestyksen olevan sovellusten käytettävissä.
 
#### <a name="form-order-user-personalization-setting"></a>Lomakejärjestyksen käyttäjän mukautusasetus
Huomaa, että kun sovelluksen käyttäjä muuttaa lomakevalintaa sovelluksen lomakkeiden valinnan avattavassa luettelossa, kyseisestä lomakkeesta tulee käyttäjän oletuslomake. Mukauttaminen korvaa oletuslomakkeen, joka on määritetty entiteetille sovelluksessa.

   > [!div class="mx-imgBorder"] 
   > ![](media/change-form-user-setting.png "Käyttäjän asetus oletuslomakkeen muuttamista varten")
   
### <a name="related-topics"></a>Asiaan liittyviä aiheita  
    
[Delegoi lomaketilaus](assign-form-order.md) <br />
[Lomakkeiden käytön valvominen](control-access-forms.md) <br />
[Päälomakkeiden ulkoasu eri asiakasohjelmissa](main-form-presentations.md) <br />
