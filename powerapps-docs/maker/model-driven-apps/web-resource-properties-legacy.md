---
title: 'Verkkoresurssiominaisuudet mallipohjaisten sovellusten päälomakkeille: PowerApps | MicrosoftDocs'
description: Tutustu päälomakkeiden verkkoresurssiominaisuuksien ominaisuuksiin
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
ms.openlocfilehash: a08ca32b1d300d4302064940e65fd1d067c3ade6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679392"
---
# <a name="web-resource-properties-for-model-driven-app-forms"></a>Verkkoresurssiominaisuudet mallipohjaisten sovellusten lomakkeille

Voit lisätä tai muokata verkkoresursseja lomakkeella, jotta se olisi kiinnostavampi tai hyödyllisempi sovelluksen käyttäjien kannalta. Lomakkeen mahdollistamia verkkoresursseja ovat kuvat tai HTML-tiedostojen ohjausobjektit.

> [!NOTE]
> Silverlight-verkkoresurssit ovat vanhentuneita, eivätkä ne toimi Unified Interface -asiakasohjelmassa.

## <a name="access-web-resource-properties"></a>Verkkoresurssin ominaisuuksiin pääsy

Kun tarkastelet lomaketta:
- **Verkkoresurssin lisääminen:**: Valitse välilehti (esimerkiksi **Yleistä** tai **Huomautuksia**), jonka haluat lisätä, ja valitse sitten **Lisää**-välilehdestä  **Verkkoresurssi**.<br />![Lisää verkkoresurssi](media/insert-web-resource.png)
- **Verkkoresurssin muokkaaminen**: Valitse lomake-välilehti ja verkkoresurssi, jota haluat muokata, ja valitse sitten **Koti** -välilehdeltä **Ominaisuuksien muuttaminen**. <br />![Verkkoresurssin ominaisuuksien muuttaminen](media/web-resource-change-properties.png)

Tämä avaa **Lisää verkkoresurssi** tai **Verkkoresurssin ominaisuudet** -valintaikkunan.

![Lisää verkkoresurssi -valintaikkuna](media/add-web-resource-dialog.png)


## <a name="web-resource-properties"></a>Verkkoresurssin ominaisuudet

 **Lisää verkkoresurssi** tai **Verkkoresurssin ominaisuudet** -valintaikkunassa on kaksi, joskus kolme välilehteä verkkoresurssin tyypin mukaan.

### <a name="general-tab"></a>Yleinen välilehti

Nämä ominaisuudet määrittävät käytettävän verkkoresurssin sekä sen, miten se tulee toimia.

|Kenttä|Kuvaus|
|--|--|
|**Verkkoresurssi**|*Pakollinen.* Etsi aiemmin luotu verkkoresurssi tai luo uusi. Käytä **Lomaketta käyttävä verkkoresurssi** -näkymää sisältämään vain HTML- ja kuvaverkkoresurssit, jotka voidaan lisätä lomakkeeseen visuaalisina elementteinä.|
|**Nimi**|*Pakollinen.* Määritä nimi verkkoresurssin ohjausobjektille, joka lisätään lomakkeeseen. Tämä arvo yksilöi lomakkeen ohjausobjektin.|
|**Selite**|*Pakollinen.* Luodaan automaattisesti **Nimi**-kentän arvon perusteella. Määritä lokalisoitava teksti verkkoresurssin ohjausobjektille, joka lisätään lomakkeeseen. Valitse **Näytä selite lomakkeessa**, jos haluat tämän näkyviin.|
|**Oletusarvoisesti näkyvissä**|Kun tämä on käytössä, verkkoresurssi tulee näkyviin, kun lomake latautuu. Jos sinulla on liiketoimintasääntö tai lomakkeen komentosarja, joka näyttää verkkoresurssin tarvittaessa, poista valinta tästä kentästä. Lisätietoja: [Näytä tai piilota lomake-elementit](visibility-options-legacy.md)|
|**Ota käyttöön mobiililaitteille**|Valitse tämä vaihtoehto, jotta tämä verkkoresurssi näkyy mobiilisovelluksissa.|

Lisäominaisuudet valitaan ja määritetään verkkoresurssin tyypistä riippuen.

HTML-verkkoresurssien kohdalla näet nämä:

![HTML-verkkoresurssin ominaisuudet](media/web-resource-general-html-properties.png)

|Kenttä|Kuvaus|
|--|--|
|**Mukautettu parametri (tiedot)**|Ovat yleensä määritystietoja, jotka lähetetään HTML-verkkoresurssiin `data` kyselymerkkijonoparametrina. HTML-sivuun liittyviä komentosarjoja voidaan käyttää näihin tietoihin pääsemiseksi, ja niiden avulla voidaan muuttaa sivun toimintaa.|
|**Rajoita kehysten komentosarjat, jos tuettu**|Käytä tätä vaihtoehtoa, jos et luota täysin HTML-verkkoresurssin sisältöön. Lisätietoja: [Kehittäjän dokumentaatio: Valitse, haluatko rajoittaa kehysten komentosarjoja](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#select-whether-to-restrict-cross-frame-scripting)|
|**Siirrä tietueen objektityyppinen koodi ja yksilöllinen tunniste parametreina**|Lomakkeella näkyvät tiedot nykyisestä tietueesta voidaan välittää HTML-verkkoresurssisivulle niin, että sivun komentosarjalla voidaan päästä tietueen tietoihin. Lisätietoja: <br />[Parametrien välittäminen verkkoresursseihin](#pass-parameters-to-web-resources)<br />[Kehittäjän dokumentaatio: välitä tilannekohtaisia tietueen tietoja](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)|

Kuvan verkkoresursseja varten sinulla on mahdollisuus määrittää **Vaihtoehtoinen teksti**, joka on tärkeä käyttöä helpottavien toimintojen kanssa ja jonka avulla sivu on kaikkien käyttäjien käytettävissä.

<!-- TODO: Why are Custom Parameters available to pass to image web resources? -->

### <a name="formatting-tab"></a>Muotoilu-välilehti

**Muotoilu**-välilehdellä näkyviin tulevat asetukset vaihtelevat lisätyn verkkoresurssin tyypin ja kontekstin mukaan. Näihin vaihtoehtoihin kuuluu näkyviin tulevien sarakkeiden ja rivien määrä, onko reuna näkyvissä sekä vieritysasetukset.

![Verkkoresurssin muotoilun ominaisuudet](media/web-resource-formatting-properties.png)

|Ominaisuus|Kuvaus|  
|--------------|-----------------|
|**Valitse ohjausobjekti kattamien sarakkeiden määrä**|Kun verkkoresurssin sisältävässä osassa on useampi kuin yksi sarake, voit määrittää kentän käsittämään sarakkeiden määrän, jotka osa sisältää.|  
|**Valitse ohjausobjekti kattamien rivien määrä**|Voit hallita verkkoresurssin korkeutta määrittämällä rivien määrän tai valitsemalla **Laajenna automaattisesti käytettävissä olevaan tilaan**, jolloin verkkoresurssin korkeutta voidaan laajentaa käytettävissä olevaan tilaan.|  
|**Valitse IFRAME-vieritystyyppi**|HTML-verkkoresurssi lisätään lomakkeeseen IFRAMEn avulla.<br /><br /> - **Tarvittaessa**: Näytä vierityspalkit, kun verkkoresurssin koko on suurempi kuin käytettävissä oleva tila.<br />- **Aina**: Näytä aina vierityspalkit.<br />- **Ei koskaan**: Älä koskaan näytä vierityspalkkeja.|  
|**Näytä reunus**|Näyttää verkkoresurssin reunuksen.|  


### <a name="dependencies-tab"></a>Riippuvuudet-välilehti

Verkkoresurssi voi olla vuorovaikutuksessa kenttien kanssa lomakkeella komentosarjan avulla. Jos kenttä poistetaan lomakkeesta, verkkoresurssin komentosarja voi lakata toimimasta. Lisää verkkoresurssin komentosarjojen viittaamat kentät kohtaan **Riippuvaiset kentät** niin, että niitä ei voi poistaa vahingossa.

![Verkkoresurssin riippuvuusominaisuudet](media/web-resource-dependency-properties.png)
  
<a name="BKMK_PassingParametersToWebResource"></a> 
 
## <a name="pass-parameters-to-web-resources"></a>Parametrien välittäminen verkkoresursseihin 

HTML-verkkoresurssi voi hyväksyä parametrit välitettäviksi kuin kyselymerkkijonon parametreina.  
  
Tietueen tietoja voidaan välittää ottamalla käyttöön **Siirrä tietueen objektityypin koodi ja yksilöivät tunnisteet parametreina** -vaihtoehto. Jos tiedot on kirjoitettu **Mukautettu parametri (tiedot)** -kenttään, ne välitetään dataparametrin avulla. Välitetty arvoja ovat:  
  
|Parametri|Kuvaus|  
|---------------|-----------------|  
|`data`|Tämä parametri välitetään vain, kun teksti annetaan **Mukautettu parametri (tiedot)** -kenttään.|  
|`orglcid`|Organisaation oletuskieli on LCID.|  
|`orgname`|Organisaation nimi.|  
|`userlcid`|Käyttäjän ensisijainen kieli on LCID|  
|`type`|**Älä käytä tätä.** Entiteettityypin koodi. Tämä numeerinen arvo voi olla toinen kuin eri organisaatioiden mukautetut entiteetit. Käytä sen sijaan entiteetin nimeä.|  
|`typename`|Entiteettityypin nimi.|  
|`id`|Tietueen tunnusarvo. Tällä parametrilla ei ole arvoa, ennen kuin sen entiteettitietue on tallennettu.|  
  
Muita parametreja ei sallita eikä verkkoresurssi avaudu, jos muita parametreja käytetään. Jos haluat välittää useita arvoja, dataparametria voit ylikuormittaa sisältämään enemmän parametreja.

Lisätietoja: [Kehittäjän dokumentaatio: välitä tilannekohtaisia tietueen tietoja](/dynamics365/customer-engagement/developer/use-iframe-and-web-resource-controls-on-a-form#pass-contextual-information-about-the-record)

### <a name="see-also"></a>Katso myös

[Luo tai muokkaa verkkoresursseja sovelluksen laajentamiseksi](create-edit-web-resources.md)<br />
[Päälomakkeen ja sen osien käyttäminen](use-main-form-and-components.md)
