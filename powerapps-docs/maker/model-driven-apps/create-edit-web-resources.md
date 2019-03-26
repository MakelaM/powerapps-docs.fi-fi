---
title: Mallipohjaisen sovelluksen WWW-resurssien luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Tietoja verkkoresurssien luomisesta tai muokkaamisesta
ms.custom: ''
ms.date: 06/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: ef4ba8df-9ba9-4066-b40d-def9761c7de2
caps.latest.revision: 21
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-model-driven-app-web-resources-to-extend-an-app"></a>Mallipohjaisen sovelluksen WWW-resurssien luominen tai muokkaaminen sovelluksen laajentamiseksi

Verkkoresurssien käyttäjiä ovat yleensä kehittäjät, jotka laajentavat sovellusta kehitystyössä käytettävien tiedostojen avulla. Sovelluksen käyttäjien on ehkä hallittava kehittäjän tai suunnittelijan toimittamia verkkoresursseja.  

> [!TIP]
> Lisätietoja WWW-resursseista on kohdassa [Sovelluskehittäjän dokumentaatio: Customer Engagement -sovelluksen WWW-resurssit](/dynamics365/customer-engagement/developer/web-resources).<br /> Lisätietoja PowerAppsissa lisätyistä WWW-resurssien riippuvuuksista kohdassa [Sovelluskehittäjän dokumentaatio: WWW-resurssien riippuvuudet](/dynamics365/customer-engagement/developer/web-resources).
   
<a name="BKMK_WhatAreWebResources"></a>

## <a name="what-are-web-resources"></a>Mitä verkkoresurssit ovat?  

Verkkoresurssit ovat järjestelmään tallennettuja virtuaalitiedostoja. Kullakin verkkoresurssilla on yksilöivä nimi ja tiedosto voidaan noutaa käyttämällä sitä URL-osoitteessa. Voit hahmottaa ne seuraavasti: Jos voisit käyttää varsinaista verkkopalvelinta, jossa verkkosovellusta käytetään, voisit kopioida tiedostot kyseiseen sivustoon. Useimmissa verkkopalveluissa tämä ei kuitenkaan ole mahdollista.  Voit sen sijaan ladata tiedostot järjestelmään verkkoresurssien avulla ja viitata sitten niihin nimen avulla aivan kuin olisit kopioinut ne tiedostona verkkopalvelimeen.  
  
Jos esimerkiksi luot HTML-sivun new_myWebResource.htm-nimisenä verkkoresurssina, voit avata kyseisen sivun selaimessa käyttämällä seuraavanlaista URL-osoitetta:  
 
`<base URL>/WebResources/new_myWebResource.htm   `
  
jossa *\<URL-perusosoite>* on sen URL-osoitteen osa, joiden avulla tarkastellaan sovelluksia, joiden lopussa on `dynamics.com`. Koska verkkoresurssi on järjestelmässä olevaa tietoa, vain organisaation käyttöoikeuden omaavat käyttäjät voivat käyttää niitä tällä tavoin. Yleensä verkkoresurssit sisältyvät lomakkeisiin sen sijaan, että niihin viitattaisiin suoraan. Yleisimmin niitä käytetään lomakkeiden komentosarjojen JavaScript-kirjastoina.  
    
Koska verkkoresurssit ovat järjestelmässä olevia tietoja ja ratkaisutietoisia, voit siirtää niitä toisiin organisaatioihin viemällä ne ratkaisun osana ja tuomalla ratkaisun toiseen organisaatioon. Käsittele WWW-resursseja ratkaisunhallinnassa.
  
## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luodun WWW-resurssin nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle WWW-resurssille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](../common-data-service/change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-web-resources"></a>WWW-resurssien tarkasteleminen

Kun ratkaisunhallinta on avattu, valitse **Osat**-kohdassa **WWW-resurssit**.

![WWW-resurssien tarkasteleminen](media/view-web-resources-solution-explorer.png)

<a name="BKMK_CreateAndEditWebResources"></a>

## <a name="create-or-edit-web-resources"></a>Verkkoresurssien luominen ja muokkaaminen  

Valitse [WWW-resurssien tarkastelemisen](#view-web-resources) yhteydessä **Uusi**, jos haluat luoda uuden WWW-resurssin, tai kaksoisnapsauta olemassa olevaa WWW-resurssia, jos haluat muokata sitä.

![Uuden WWW-resurssin lomake](media/new-web-resource-form.png)

Täytä lomake ja luo WWW-resurssi tai muokkaa sitä seuraavasti:
  
|Kenttä|Kuvaus|  
|-----------|-----------------|  
|**Nimi**|*Pakollinen*. Tämä on verkkoresurssin yksilöivä nimi. Et voi muuttaa sitä verkkoresurssin tallentamisen jälkeen.<br />&bull; Nimessä saa olla vain kirjaimia, numeroita, pisteitä ja vinoviivoja. Vinoviivoja (/) ei saa olla useita peräkkäin.<br /> &bull; Ratkaisujulkaisijan mukautuksen etuliite liitetään verkkoresurssin nimen alkuun.|  
|**Näyttönimi**|Tämä on verkkoresurssiluettelossa näkyvä nimi.|  
|**Kuvaus**|Verkkoresurssin kuvaus.|  
|**Tyyppi**|*Pakollinen*. Tämä on verkkoresurssin tyyppi. Et voi muuttaa sitä verkkoresurssin tallentamisen jälkeen.|  
|**Tekstieditori**|Jos verkkoresurssin tyyppi viittaa eräänlaiseen tekstitiedostoon, voit avata sivun valitsemalla painikkeen, jonka jälkeen voit muokata sisältöä tekstieditorilla.<br />Lisätietoja: [Tekstieditorin käyttö](#use-the-text-editor-appropriately)| 
|**Kieli**|Mahdollistaa kielen valinnan. Tämä vaihtoehto vain merkitsee tietueen, johon verkkoresurssin tiedot on tallennettu. Se ei muuta verkkoresurssin toimintaa.|  
|**Lataa tiedosto**|Valitse **Selaa…** -painiketta verkkoresurssina ladattava tiedosto valitsemiseksi.<br />&bull; Voit ladata tiedoston, kun luot uuden verkkoresurssin, tai korvata aiemmin luodun verkkoresurssin.<br />&bull; Tiedoston tiedostotunnisteen on oltava jokin hyväksytyistä tiedostotunnisteista.<br />&bull;Verkkoresurssina ladattavan tiedoston enimmäiskoko on oletusarvoisesti 5 Mt. Arvoa voidaan muokata Dynamics 365 Customer Engagementissa valitsemalla **Järjestelmäasetukset** > **Sähköposti**-välilehti > **Määritä liitetiedostojen enimmäiskoko** -asetus. Lisätietoja: [Järjestelmäasetukset-valintaikkuna – Sähköposti-välilehti](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-email-tab) |  
|**URL-osoite**|Verkkoresurssin URL-osoite näkyy tässä sen jälkeen, kun olet tallentanut verkkoresurssin. Voit tarkastella verkkoresurssia selaimessa valitsemalla tämän linkin.|  
  
Kun olet lisännyt muutokset, valitse ensin **Tallenna** ja sitten **Julkaise**.  

> [!NOTE]
> WWW-resurssin muutokset eivät näy sovelluksessa ennen julkaisemista.
  
<a name="BKMK_UsingTextEditor"></a>
   
### <a name="use-the-text-editor-appropriately"></a>Tekstieditorin käyttö

Sovelluksessa olevalla verkkoresurssien tekstieditorilla pitäisi tehdä tekstitiedostoihin vain yksinkertaisia muutoksia. Vaikka voit luoda ja muokata sillä HTML-verkkoresursseja, muokkaa kuitenkin vain tekstieditorilla luotuja HTML-verkkoresursseja. Tekstieditori on suunniteltu hyvin yksinkertaista HTML-sisältöä varten. 

> [!IMPORTANT]
> Jos HTML-verkkoresurssin sisältöä ei ole luotu tekstieditorissa, älä muokkaa sitä tekstieditorissa.  
> Tekstieditori käyttää ohjausobjektia, joka muokkaa HTML-lähteen muokattavaan muotoon. Sivu voi käyttäytyä näiden muutosten vuoksi selaimessa eri tavoin ja estää monimutkaisemman koodin toiminnan. HTML-verkkoresurssin avaaminen tekstieditorissa ja sen tallentaminen muutoksia tekemättä voi vaurioittaa joitakin HTML-verkkoresursseja.  Lisätietoja: [Sovelluskehittäjän dokumentaatio: HTML:n WWW-resurssien tekstieditorin käyttö](/dynamics365/customer-engagement/developer/webpage-html-web-resources#use-the-text-editor-for-html-web-resources)
  
Tekstitiedostojen muokkaamiseen onkin suositeltavaa käyttää ulkoista editoria. Tiedostot on myös hyvä tallentaa ensin paikallisesti ennen niiden lataamista **Lataa tiedosto** -painikkeella. Tällä tavoin sinulla on verkkoresurssin kopio, jos sinun on palattava aiempaan versioon. Voit käyttää yksinkertaista editoria, kuten Muistiota, mutta toiminnoiltaan monipuolisemman tekstieditorin käyttö on suositeltavaa. [Visual Studio -yhteisö](https://www.visualstudio.com/vs/community/) ja [Visual Studio -koodi](https://code.visualstudio.com/) ovat ilmaisia. Niiden avulla voi muokata WWW-resursseissa käytettäviä tekstipohjaisia tiedostoja tehokkaasti..  

<a name="BKMK_CreateAndEditFormWebResources"></a>
 
## <a name="create-and-edit-a-web-resource-on-a-form"></a>Lomakkeen verkkoresurssin lisääminen ja muokkaaminen

Voit lisätä tai muokata lomakkeen verkkoresursseja niin, että se on kiinnostavampi tai hyödyllisempi käyttäjille. 

> [!NOTE]
> WWW-resurssia ei voi sisällyttää lomakkeen ylä- tai alatunnisteeseen.  

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="navigate-to-a-form"></a>Lomakkeeseen siirtyminen
Laajenna ratkaisunhallinnan **Osat**-kohdassa **Entiteetit** ja laajenna sitten entiteetti, jota haluat käyttää.

Valitse **Lomakkeet**-luettelosta lomaketyyppi Päälomake. Voit sitten avata ja muokata lomaketta kaksoisnapsauttamalla tai -napauttamalla.

### <a name="add-or-edit-web-resource-in-a-form"></a>WWW-resurssin lisääminen lomakkeeseen tai WWW-resurssin muokkaaminen

Katso [WWW-resurssin ominaisuudet](web-resource-properties-legacy.md) -kohdasta lisätietoja ominaisuuksista, joita WWW-resursseille voi määrittää lomakkeessa.

### <a name="preview"></a>Esikatselu

Esikatsele päälomakkeen ulkoasua ja tapahtumien suorittamista:
- Valitse **Aloitussivu**-välilehdessä ensin **Esikatsele** ja sitten **Luo lomake**, **Päivitä lomake** tai **Vain luku -lomake**.
- Sulje esikatselulomake valitsemalla **Tiedosto**-valikossa **Sulje**.

### <a name="save"></a>Tallentaminen

Kun olet tehnyt lomakkeeseen haluamasi muutokset, sulje lomake valitsemalla **Aloitussivu**-välilehdessä **Tallenna ja sulje**. 

### <a name="publish"></a>Julkaise

Kun olet tehnyt haluamasi mukautukset, julkaise ne:
- Jos haluat julkaista mukautuksen vain juuri muokkaamallesi osalle, valitse siirtymisruudun siirtymispalkissa muokkaamaasi entiteetti ja valitse sitten **Julkaise**.
- Jos haluat julkaista kaikkien julkaisemattomien osien mukautukset yhtä aikaa, valitse ensin siirtymisruudussa **Entiteetit** ja sitten **Toiminnot**-työkalurivillä **Julkaise kaikki mukautukset**.
   
  
### <a name="see-also"></a>Katso myös  

[Verkkoresurssin ominaisuudet](web-resource-properties-legacy.md) <br /> 
[Luo ja suunnittele lomakkeita](create-design-forms.md) <br />
[Tietoja mallipohjaisen sovelluksen osista](model-driven-app-components.md) <br /> 
[Sovelluskehittäjän dokumentaatio: Customer Engagementin verkkoresurssit](/dynamics365/customer-engagement/developer/web-resources)
