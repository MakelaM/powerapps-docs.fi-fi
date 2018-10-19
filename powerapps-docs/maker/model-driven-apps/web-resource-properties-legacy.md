---
title: Mallipohjaisen sovelluksen päälomakkeiden WWW-resurssin ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeiden WWW-resurssin ominaisuuksista
Keywords: Main form; Web resource properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 82cd41ea-95b0-4606-9e7d-43eb5ce9ecd6
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="web-resource-properties-for-model-driven-app-forms"></a>Mallipohjaisten sovellusten lomakkeiden WWW-resurssien ominaisuudet

Voit lisätä tai muokata lomakkeen verkkoresursseja niin, että se on kiinnostavampi tai hyödyllisempi sovelluskäyttäjille. Lomakkeessa käyttöön otetut verkkoresurssit ovat kuvia tai HTML-tiedostojen ohjausobjekteja.

> [!NOTE]
> Silverlightin WWW-resurssit ovat vanhentuneet. Ne eivät toimi Unified Interface -asiakasohjelmassa.

## <a name="access-web-resource-properties"></a>WWW-resurssin ominaisuuksien käyttäminen

Lomakkeen tarkastelemisen yhteydessä:
- **WWW-resurssin lisääminen:**: Valitse välilehti (esimerkiksi **Yleinen** tai **Huomautukset**), johon haluat sen lisätä, ja valitse **Lisää**-välilehdessä **WWW-resurssit**.<br />![WWW-resurssin lisääminen](media/insert-web-resource.png)
- **WWW-resurssin muokkaaminen**: Valitse lomakkeen välilehti ja muokattava WWW-resurssi. Valitse sitten **Koti**-välilehdessä **Muuta ominaisuuksia**. <br />![WWW-resurssin ominaisuuksien muuttaminen](media/web-resource-change-properties.png)

**Lisää WWW-resurssi**- tai **WWW-resurssin ominaisuudet** -valintaikkuna avautuu.

![Lisää WWW-resurssi -valintaikkuna](media/add-web-resource-dialog.png)


## <a name="web-resource-properties"></a>Verkkoresurssin ominaisuudet

 **Lisää WWW-resurssi**- tai **WWW-resurssin ominaisuudet** -valintaikkunassa on kaksi tai joskus kolme välilehteä WWW-resurssin tyypistä riippuen.

### <a name="general-tab"></a>Yleiset-välilehti

Nämä ominaisuudet määrittävät käytettävän WWW-resurssin ja sen toimintatavat.

|Kenttä|Kuvaus|
|--|--|
|**WWW-resurssi**|*Pakollinen.* Etsi olemassa oleva WWW-resurssi tai luo uusi. Sisällytä vain HTML:n tai kuvan WWW-resurssit, jotka lisätään lomakkeeseen visuaalisina elementteinä, käyttämällä **Lomakkeessa käytössä olevat WWW-resurssit** -näkymää.|
|**Nimi**|*Pakollinen.* Määritä lomakkeeseen lisättävän WWW-resurssin ohjausobjektin nimi. Tämä arvo yksilöi lomakkeen ohjausobjektin.|
|**Otsikko**|*Pakollinen.* Automaattisesti luotu peruste **Nimi**-kentän arvolle. Määritä lomakkeeseen lisättävän WWW-resurssin lokalisoitava teksti. Valitse **Näytä otsikko lomakkeessa**, jos haluat tehdä tästä näkyvän.|
|**Oletusarvoisesti näkyvissä**|Jos tämä on käytössä, WWW-resurssi näkyy lomakkeen latautuessa. Jos käytössä on liiketoimintasääntö tai lomakkeen komentosarja, joka näyttää WWW-resurssin tarvittaessa, poista tämän kentän valinta. Lisätietoja: [Lomake-elementtien näyttäminen tai piilottaminen](visibility-options-legacy.md)|
|**Ota käyttöön mobiililaitteissa**|Valitse tämä asetus, jos tämä WWW-resurssi saa näkyä mobiilisovelluksissa.|

Määritä lisäominaisuudet valitun WWW-resurssin tyypin mukaan.

HTML:n WWW-resursseilla näkyvät seuraavat kohdat:

![HTML:n WWW-resurssin ominaisuudet](media/web-resource-general-html-properties.png)

|Kenttä|Kuvaus|
|--|--|
|**Mukautettu parametri (tiedot)**|Yleensä määritystietoja, jotka välitetään HTML:n WWW-resurssille `data`-kyselymerkkijonon parametrina. HTML-sivuun liitetyt komentosarjat voivat käyttää näitä tietoja sivun toimintatavan muuttamiseksi.|
|**Rajoita kehysten väliset komentosarjat silloin, kun sitä tuetaan**|Käytä tätä, jos et halua täysin luottaa HTML:n WWW-resurssin sisältöön. Lisätietoja: [Sovelluskehittäjän dokumentaatio: Kehysten välisten komentosarjojen rajoittamisen määrittäminen](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#select-whether-to-restrict-cross-frame-scripting)|
|**Siirrä tietueen objektilajikoodi ja yksilöllinen tunnus parametreina**|Lomakkeessa näkyvän nykyisen tietueen tiedot voidaan välittää HTML:n WWW-resurssin sivulle niin, että sivulla suoritettavat komentosarjat voivat käyttää tietueen tietoja. Lisätietoja: <br />[Parametrien välittäminen verkkoresursseihin](#pass-parameters-to-web-resources)<br />[Sovelluskehittäjän dokumentaatio: Tietueen tilannekohtaisten tietojen välittäminen](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)|

Voit määrittää kuvan WWW-resursseille **vaihtoehtoisen tekstin**, joka on tärkeä käyttöä helpottavissa toiminnoissa, joiden avulla sivu on kaikkien käytettävissä.

<!-- TODO: Why are Custom Parameters available to pass to image web resources? -->

### <a name="formatting-tab"></a>Muotoilu-välilehti

**Muotoilu**-välilehdellä näkyvät asetukset vaihtelevat lisätyn WWW-resurssin lajin ja mahdollisen kontekstin mukaan. Asetuksia ovat esimerkiksi näytettävien sarakkeiden ja rivien määrittäminen, näytetäänkö reuna sekä vieritystoiminto.

![WWW-resurssin muotoiluominaisuudet](media/web-resource-formatting-properties.png)

|Ominaisuus|Kuvaus|  
|--------------|-----------------|
|**Valitse sarakkeiden määrä ohjausobjektia varten**|Kun verkkoresurssin sisältävässä osassa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osassa on.|  
|**Valitse ohjausobjektin viemien rivien määrä**|Voit ohjata WWW-resurssin korkeutta määrittämällä rivien määrän tai valitsemalla **Laajenna automaattisesti käytettävissä olevaan tilaan** -kohdan, jolloin WWW-resurssin korkeus on sama kuin käytettävissä oleva tila.|  
|**Valitse IFRAME-kehyksen selaustapa**|HTML-verkkoresurssi lisätään lomakkeeseen IFRAME-kehyksen avulla.<br /><br /> - **Tarpeen mukaan**: näytä vierityspalkit, kun verkkoresurssi on suurempi kuin käytettävissä oleva tila.<br />- **Aina**: näytä vierityspalkit aina.<br />- **Ei koskaan**: älä näytä vierityspalkkeja koskaan.|  
|**Näytä reunaviiva**|Näytä reunaviivat verkkoresurssin ympärillä.|  


### <a name="dependencies-tab"></a>Riippuvuudet-välilehti

Verkkoresurssi voi olla yhteydessä lomakkeen kenttiin komentosarjojen avulla. Jos kenttä poistetaan lomakkeesta, verkkoresurssin komentosarja voi katketa. Lisää kentät, joihin komentosarjat viittaavat verkkoresurssissa, **alisteisiin kenttiin**, jotta niitä ei voi poistaa vahingossa.

![WWW-resurssin riippuvuuksien ominaisuudet](media/web-resource-dependency-properties.png)
  
<a name="BKMK_PassingParametersToWebResource"></a> 
 
## <a name="pass-parameters-to-web-resources"></a>Parametrien välittäminen verkkoresursseihin 

HTML-verkkoresurssi voi hyväksyä kyselymerkkijonon parametreina välitettävät parametrit.  
  
Tietuetta koskevat tiedot voidaan välittää ottamalla **Siirrä tietueen objektityyppikoodi ja yksilöllinen tunnus parametreina** -asetus käyttöön. Jos tiedot on kirjoitettu **Mukautettu parametri (tiedot)** -kenttään, ne välitetään tietoparametrin avulla. Välitetyt arvot:  
  
|Parametri|Kuvaus|  
|---------------|-----------------|  
|`data`|Tämä parametri välitetään vain, kyse on **Mukautettu parametri (tiedot)** -tekstistä.|  
|`orglcid`|Organisaation oletuskielen LCID-tunnus.|  
|`orgname`|Organisaation nimi.|  
|`userlcid`|Käyttäjän ensisijaisen kielen LCID-tunnus|  
|`type`|**Älä käytä tätä.** Entiteetin tyyppikoodi. Tämä numeerinen arvo voi olla erilainen eri organisaatioiden mukautetuissa entiteeteissä. Käytä sen sijaan entiteettityypin nimeä|  
|`typename`|Entiteettityypin nimi.|  
|`id`|Tietueen tunnusarvo. Tällä parametrilla ei ole arvoa, ennen kuin entiteettitietue on tallennettu.|  
  
Muita parametreja ei sallita eikä verkkoresurssi avaudu muita parametreja käytettäessä. Jos välitettäviä arvoja on useita, tietoparametriin voidaan kuormittaa lisää parametreja.

Lisätietoja: [Sovelluskehittäjän dokumentaatio: Tietueen tilannekohtaisten tietojen välittäminen](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)

### <a name="see-also"></a>Katso myös

[Sovelluksen laajentaminen verkkoresursseja luomalla tai muokkaamalla](create-edit-web-resources.md)<br />
[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)
