---
title: Mallipohjaisen sovelluksen verkkoresurssien luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Lue, miten voit luoda näkymän tai muokata verkkoresurssia
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
ms.openlocfilehash: 8d9414ba4c900f98ac26010e4e6d7240b336e2d7
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679899"
---
# <a name="create-or-edit-model-driven-app-web-resources-to-extend-an-app"></a>Luo tai muokkaa mallipohjaisen sovelluksen verkkoresursseja sovelluksen laajentamiseksi

Verkkoresursseja käyttävät yleensä sovelluskehittäjät laajentamaan tiedostoja, joita käytetään verkkokehitystyössä. Sovelluksen käyttäjät joutuvat ehkä hallitsemaan kehittäjän tai suunnittelijan tekemiä verkkoresursseja.  

> [!TIP]
> Katso verkkoresurssien tarkempi kuvaus asiakirjasta [Kehittäjän dokumentaatio: Customer Engagement -verkkoresurssit](/dynamics365/customer-engagement/developer/web-resources).<br /> Lisätietoa PowerAppsiin lisätyistä verkkoresurssien riippuvuussuhteista saa asiakirjasta [Kehittäjän dokumentaatio: verkkoresurssien riippuvuudet](/dynamics365/customer-engagement/developer/web-resources).
   
<a name="BKMK_WhatAreWebResources"></a>

## <a name="what-are-web-resources"></a>Mitä ovat verkkoresurssit?  

Verkkoresurssit ovat virtuaalisia järjestelmään tallennettuja tiedostoja. Kullakin verkkoresurssilla on yksilöllinen nimi, jota voidaan käyttää URL-osoitteessa tiedoston hakua varten. Tätä voi ajatella myös seuraavasti: jos pääset varsinaiselle verkkopalvelimelle, jolla verkkosovellus suoritetaan, voit kopioida tiedostot kyseiselle sivustolle. Mutta useimmissa online-palveluissa se ei ole mahdollista.  Voit sen sijaan käyttää verkkoresursseja tiedostojen lataamiseen järjestelmään ja viitata niihin nimellä aivan kuin olisit kopioinut ne tiedostoina verkkopalvelimelle.  
  
Jos esimerkiksi luot HTML-sivun verkkoresurssina, jonka nimi on ”new_myWebResource.htm”, voit avata kyseisen sivun selaimessa URL-osoitteen avulla seuraavasti:  
 
`<base URL>/WebResources/new_myWebResource.htm   `
  
kun  *\<perus-URL >* on osa URL-osoitetta, jota käytät sovellusten tarkasteluun ja sen loppu on `dynamics.com`. Koska verkkoresurssi on järjestelmässä oleva data, vain käyttöoikeuden omaavat käyttäjät voivat käyttää niitä tällä tavalla. Yleensä verkkoresurssit ovat osa lomakkeita suorien viittausten sijaan. Yleisin käyttö on luoda JavaScript-kirjastoja komentosarjojen muodostamiseksi.  
    
Koska verkkoresurssit ovat osa järjestelmän dataa ja ratkaisutietoisia, voit siirtää niitä eri organisaatioihin viemällä ne osana ratkaisua ja tuomalla ratkaisun eri organisaatioon. Ratkaisunhallintaa on käytettävä verkkoresurssien kanssa.
  
## <a name="open-solution-explorer"></a>Avaa ratkaisunhallinta

Luomasi verkkoresurssin nimeen sisältyy mukautusetuliite. Etuliite määräytyy käytössäsi olevan ratkaisun julkaisijan mukaan. Jos mukautusetuliitteellä on sinulle merkitystä, varmista, että käytät hallitsematonta ratkaisua, jossa mukautusetuliite on se, jota haluat käyttää kyseiselle verkkoresurssille. Lisätietoja: [Ratkaisun julkaisijan etuliitteen muuttaminen](../common-data-service/change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-web-resources"></a>Verkkoresurssien tarkastelu

Kun ratkaisunhallinta on avattu, valitse kohdasta **Osat** kohta **Verkkoresurssit**.

![Verkkoresurssien tarkastelu](media/view-web-resources-solution-explorer.png)

<a name="BKMK_CreateAndEditWebResources"></a>

## <a name="create-or-edit-web-resources"></a>Luo tai muokkaa verkkoresursseja  

Kun [tarkastelet verkkoresursseja](#view-web-resources), valitse **Uusi** luodaksesi uuden verkkoresurssin tai kaksoisnapsauta aiemmin luotua verkkoresurssia muokataksesi sitä.

![Uusi verkkoresurssilomake](media/new-web-resource-form.png)

Täytä lomake, kun luot tai muokkaat verkkoresurssia:
  
|Kenttä|Kuvaus|  
|-----------|-----------------|  
|**Nimi**|*Pakollinen*. Tämä on verkkoresurssin yksilöivä nimi. Et voi muuttaa tätä, kun olet tallentanut verkkoresurssin.<br />&bull; Tämä nimi voi sisältää vain kirjaimia, numeroita, pisteitä ja vinoviivoja (/).<br /> &bull; Ratkaisun julkaisijan mukautuksen etuliite liitetään verkkoresurssin nimeen.|  
|**Näyttönimi**|Nimi, joka tulee esiin, kun tarkastelet verkkoresurssiluetteloa.|  
|**Kuvaus**|Verkkoresurssin kuvaus.|  
|**Tyyppi**|*Pakollinen*. Tämä on verkkoresurssin tyyppi. Et voi muuttaa tätä, kun olet tallentanut verkkoresurssin.|  
|**Tekstieditori**|Kun verkkoresurssin tyyppi edustaa tätä tekstitiedostotyyppiä, valitse tämä painike avataksesi sivun ja muokataksesi sisältöä tekstieditorissa.<br />Lisätietoja: [käytä tekstieditoria asianmukaisesti](#use-the-text-editor-appropriately)| 
|**Kieli**|Mahdollistaa kielen valinnan. Tämä asetus antaa tunnisteet vain tietueelle, joka tallentaa verkkoresurssidataa. Se ei muuta verkkoresurssin toimintaa.|  
|**Lataa tiedosto palvelimeen**|Valitse **Selaa...** -painike ladattavan tiedoston verkkoresurssiksi valintaa varten.<br />&bull; Voit ladata tiedoston luotaessa uutta verkkoresurssia tai jos haluat korvata aiemmin luodun verkkoresurssiin.<br />&bull; Tiedostotunnisteen on vastattava sallittuja tunnisteita.<br />&bull; Oletusarvoisesti suurin tiedosto, joka voidaan ladata verkkoresurssina, on 5 Mt. Tätä arvoa voidaan muokata Dynamics 365 Customer Engagement -paketin kohdassa **Järjestelmäasetukset** > **Sähköposti**-välilehti > **Aseta tiedostolle liitteiden kokorajoitus**. Lisätietoja: [Järjestelmäasetukset -valintaikkuna - Sähköposti-välilehti](https://docs.microsoft.com/dynamics365/customer-engagement/admin/system-settings-dialog-box-email-tab) |  
|**URL-osoite**|Kun olet tallentanut verkkoresurssin, verkkoresurssin URL-osoite näkyy tässä. Valitsemalla tämän linkin voit tarkastella verkkoresurssia selaimessasi.|  
  
Kun olet tehnyt haluamasi muutokset, valitse **Tallenna** ja sitten **Julkaise**.  

> [!NOTE]
> Verkkoresurssin muutokset eivät näy sovelluksessa ennen kuin julkaiset sen.
  
<a name="BKMK_UsingTextEditor"></a>
   
### <a name="use-the-text-editor-appropriately"></a>Käytä tekstieditoria asianmukaisesti

Sovelluksen verkkoresursseille tarkoitettu tekstieditori on tarkoitettu vain tekstitiedostojen yksinkertaisiin muutoksiin. Sen avulla voit luoda ja muokata HTML-verkkoresursseja, mutta voit muokata vain niitä HTML-verkkoresursseja, jotka on luotu tekstieditoria käyttämällä. Tekstieditori on suunniteltu hyvin yksinkertaista HTML-sisältöä varten. 

> [!IMPORTANT]
> Jos HTML-verkkoresurssin sisältöä ei ole luotu tekstieditorissa, älä käytä tekstieditoria sen muokkaamiseen.  
> Tekstieditori käyttää ohjausobjektia, joka muuntaa HTML-tietolähdettä niin, että sitä voidaan muokata. Nämä muutokset voivat saada sivun toimimaan eri tavalla selaimessa ja aiheuttaa sen, että kehittyneimmät koodit lakkaavat toimimasta. HTML-verkkoresurssin avaaminen tekstieditorissa ja sen tallentaminen ilman muutoksia voi rikkoa osan HTML-verkkoresursseista.  Lisätietoja: [Kehittäjän dokumentaatio: Käytä tekstieditoria HTML-verkkoresursseissa](/dynamics365/customer-engagement/developer/webpage-html-web-resources#use-the-text-editor-for-html-web-resources)
  
Suosittelemme, että käytät ulkoista editoria muokatessasi tekstitiedostoja ja tallennat ne sitten paikallisesti ennen lataamista **Lataa tiedosto** -painikkeella. Tällä tavalla voit säilyttää kopion verkkoresurssista, jos haluat palauttaa sen aiemman version. Voit käyttää yksinkertaista editoria kuten Notepadia, mutta kehittyneempiä ominaisuuksia sisältävän tekstieditorin käyttö on erittäin suositeltavaa. [Visual Studio-yhteisö](https://www.visualstudio.com/vs/community/) ja [Visual Studio-koodi](https://code.visualstudio.com/) ovat maksuttomia ja tarjoavat tehokkaita ominaisuuksia muokata verkkoresurssien käyttämiä tekstipohjaisia tiedostoja.  

<a name="BKMK_CreateAndEditFormWebResources"></a>
 
## <a name="create-and-edit-a-web-resource-on-a-form"></a>Luo ja muokkaa verkkoresurssia lomakkeella

Voit lisätä tai muokata verkkoresursseja lomakkeella, jotta se olisi kiinnostavampi tai hyödyllisempi käyttäjien kannalta. 

> [!NOTE]
> Verkkoresurssia ei voi lisätä lomakkeen ylä- tai alatunnisteeseen.  

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="navigate-to-a-form"></a>Siirry lomakkeeseen
Kun ratkaisunhallinta on avattu, laajenna kohdasta **Osat** **Entiteetit**, ja laajenna sitten haluamasi entiteetti.

Valitse **Lomakkeet**, etsi luettelosta lomaketyyppi Päälomake ja kaksoisnapsauta tai napauta sitten syötettä lomakkeen avaamiseksi ja muokkaamiseksi.

### <a name="add-or-edit-web-resource-in-a-form"></a>Verkkoresurssin lisääminen tai muokkaaminen lomakkeessa

Katso kohdasta [Verkkoresurssin ominaisuudet](web-resource-properties-legacy.md) tietoja ominaisuuksista, joita voit asettaa lomakkeen verkkoresursseille.

### <a name="preview"></a>Esikatselu

Esikatselu päälomakkeen ulkoasun ja tapahtumien toimimisen suhteen:
- Valitse **Aloitus**-välilehdeltä **Esikatselu** ja valitse sitten **Luo lomake**, **Päivitä lomake**, tai **Vain luku-muoto**.
- Sulje esikatselulomake **Tiedosto**-valikosta ja valitse **Sulje**.

### <a name="save"></a>Tallenna

Kun olet muokannut lomaketta, valitse **Aloitus**-välilehdeltä **Tallenna ja sulje** lomakkeen sulkemiseksi. 

### <a name="publish"></a>Julkaise

Kun mukautukset on tehty, julkaise ne:
- Jos haluat julkaista vain sitä osa koskevia mukautuksia, joka on muokattavana,valitse siirtymisruudussa entiteetti, jota olet käsitellyt ja valitse sitten **Julkaise**.
- Jos haluat julkaista mukautukset kaikista julkaisemattomista osista yhtä aikaa siirtymisruudussa, valitse **Entiteetit** ja sitten **Toiminnot**-työkalurivi ja **Julkaise kaikki mukautukset**.
   
  
### <a name="see-also"></a>Katso myös  

[Verkkoresurssin ominaisuudet](web-resource-properties-legacy.md) <br /> 
[Luo ja suunnittele lomakkeita](create-design-forms.md) <br />
[Mukauttamisen aloittaminen](getting-started-customization.md) <br /> 
[Kehittäjien dokumentaatio: Customer Engagement -verkkoresurssit](/dynamics365/customer-engagement/developer/web-resources)
