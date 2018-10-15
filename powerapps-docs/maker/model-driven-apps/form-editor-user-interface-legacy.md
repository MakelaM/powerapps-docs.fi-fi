---
title: Yleiskatsaus malliin perustuvan sovelluksen lomake-editorin käyttöliittymään PowerAppsille | MicrosoftDocs
description: Tutustu lomake-editorin käyttöliittymään ja muokkaa lomakkeita PowerAppsissa
keywords: Lomakkeet; Päälomake; Unified Interface -sovellus; Dynamics 365 for customer engagement
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.assetid: 146f8035-4fcd-4572-8e71-4270cd150495
ms.openlocfilehash: a44987e7b8809dea46f164224974a21a2d9a5010
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680459"
---
# <a name="overview-of-the-model-driven-app-form-editor-user-interface"></a>Yleiskatsaus malliin perustuvan sovelluksen lomake-editorin käyttöliittymään

Lomake-editori näyttää komentoja kolmessa välilehdessä: **Tiedosto**, **Aloitus** ja **Lisää**.  

- [Tiedosto-välilehti](#file-tab)
- [Aloitus-välilehti](#home-tab)
- [Lisää-välilehti](#insert-tab)
  
Lomake-editori on jaettu kolmeen alueeseen: **Siirtyminen**, **Leipäteksti** ja **Explorer**.  

![Lomake-editorin käyttöliittymä](media/form-user-interface.png)
  
**Siirtyminen**  
Vasemmalla puolella sijaitsevan siirtymisalueen avulla voit hallita liittyvien entiteettien käyttöä tai lisätä linkkejä URL-osoitteisiin, jotka näytetään lomakkeen pääikkunassa. Jos haluat muokata siirtyminen, valitse ensin **Siirtyminen**-komento **Aloitus**-välilehden **Valitse**-ryhmässä.

Päälomakkeissa on vaihtoehtoja siirtymispalkissa siirtymiseen kautta, mutta voit käyttää samoja tietoja siirtymisalueella määrittääksesi, mitä siirtymisvaihtoehtoja on käytettävissä. Lisätietoja: [Siirtymisen muokkaaminen](use-the-form-editor-legacy.md)  


**Leipäteksti** <br>
Keskellä sijaitsevan leipätekstialueen avulla voit hallita lomakkeen asettelua. Voit valita lomake-elementtejä ja vetää niitä uuteen sijaintiin. Elementtiä kaksoisnapsauttamalla voit avata elementin ominaisuudet. 

Oletusarvoisesti Palvelupyyntö-, Yhteyshenkilö- ja Tili-päälomakkeiden kohdalla **Yhteenveto**-välilehden ensimmäisessä osassa on näkyvissä tilin tai yhteyshenkilökortin lomake tyyppiä **Pikanäkymä**. Tämä osa ei ole oletusarvoisesti käytettävissä mukautetuissa entiteeteissä. Voit lisätä uuden osan ja pikanäkymälomakkeen siihen. Kortin lomakkeessa on näkyvissä enintään viisi kenttää. Kenttien lisäksi muita ohjausobjekteja ei ole mahdollista näyttää sinisessä ruudussa, vaikka pikalomake sisältäisi sen. 
 
>[!NOTE] 
> Kortin muodon säilyttämiseksi (seuraavassa kuvassa näkyvällä tavalla) suosittelemme, että et siirrä pikalomaketta lomakkeen toiseen osaan.

![Kortin muoto](media/card-format.png)
   
Lisätietoja: [Pikalomakkeiden luominen ja muokkaaminen](create-edit-quick-view-forms.md)  
 
-   Lisää kenttä valitsemalla se **kenttien hallinnassa** ja vetämällä se osaan.  
  
    -   Jos haluat lisätä elementin, joka ei ole kenttä, valitse sen sijoituspaikka ja lisää se käyttämällä asianmukaista komentoa **Lisää**-välilehdestä.  
  
    -   Jos haluat poistaa elementin, valitse se ja käytä **Poista**-komentoa **Aloitus**-välilehden **Muokkaa**-ryhmässä.  
  
    -   Jotta voit muokata lomakkeen **ylätunnistetta** tai **alatunnistetta**, valitse ensin asianmukainen komento **Aloitus**-välilehden **Valitse**-ryhmässä.  
  
**Hallinta**  
Oikealla puolella sijaitsevan hallinta-alueen sisältö riippuu kontekstista.  
  
Kun valitset **Leipäteksti**, **Ylätunniste** tai **Alatunniste** **Aloitus**-välilehden **Valitse**-ryhmässä, **Kenttien hallinta** tulee näkyviin. **Kenttien hallinnan** avulla voit vetää näytettävät kentät lomakkeen osaan tai ylä- tai alatunnisteeseen. Voit sisällyttää saman kentän lomakkeeseen useita kertoja. Voit luoda uuden kentän käyttämällä **Uusi kenttä** -painiketta pikakuvakkeena.  
  
Kun valitset **Siirtyminen** **Aloitus**-välilehden **Valitse**-ryhmässä, näkyviin tulee **Suhteiden hallinta**. Vedä jokin suhteista johonkin ryhmän siirtymisalueella. Samaa suhdetta ei voi lisätä kahdesti. Suhteet ovat käytettävissä sen perusteella, miten ne on määritetty. Jos määrität suhteen niin, että sitä ei näy, se ei näy **suhteiden hallinnassa**. Lisätietoja suhteiden oletusnäyttöasetusten määrittämisestä on kohdassa [Ensisijaisen entiteetin siirtymisruudun kohde](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity).
  
Voit määrittää **Uusi 1:N**- ja **Uusi N:N -painikkeet** pikakuvakkeiksi uusien entiteettien välisten suhteiden lisäämiseen.  

## <a name="file-tab"></a>Tiedosto-välilehti

Valitsemalla **Tiedosto**-välilehden voit lisätä tai tarkastella seuraavia vaihtoehtoja:

- **Uusi toiminto** Lisää uusi toiminto
- **Uusi tietue** Lisää uusi tietue
- **Työkalut** Hyödynnä toimintoja, kuten Tietojen tuominen, Kaksoiskappaleiden tunnistus ja Ohjattu joukkopoisto
- **Asetukset** Oletusnäyttöasetuksia muuttamalla voit mukauttaa oletusratkaisua ja hallita sähköpostimalleja
    - Yleistä
    - Synkronointi
    - Aktiviteetit
    - Muodot
    - Sähköpostimallit
    - Sähköpostin allekirjoitukset
    - Email
    - Tietosuoja
    - Languages
- Ohje
- Sulje


## <a name="home-tab"></a>Aloitus-välilehti  
 **Aloitus**-välilehdessä näkyvät seuraavassa taulukossa luetellut komennot:

![aloitus-välilehti](media/home-tab.png)

|Ryhmä|Komento|Kuvaus|
|-----------|-------------|-----------------| 
|**Tallenna**|**Tallenna**  **(Ctrl + S)**|Tallenna lomake.|
||**Tallenna nimellä**|Luo kopio tästä lomakkeesta eri nimellä.|
||**Tallenna ja sulje**|Tallenna lomake ja sulje lomake-editori.|
||**Julkaise**|Julkaise lomake. Lisätietoja: Mukautusten julkaiseminen|
|**Muokkaa**|**Muuta ominaisuuksia**|Muuta leipätekstissä valitun kohteen ominaisuuksia.<br /><br /> Katso seuraavat osat valitun kohteen mukaan:<br /><br /> -   [Välilehden ominaisuudet](tab-properties-legacy.md)<br />-   [Osan ominaisuudet](section-properties-legacy.md)<br />-   [Yleisen kentän ominaisuudet](common-field-properties-legacy.md)<br />-   [Erikoiskentän ominaisuudet](special-field-properties-legacy.md)<br />-  [Aliruudukon ominaisuudet](sub-grid-properties-legacy.md)<br />-   [Pikanäkymän ohjausobjektin ominaisuudet](quick-view-control-properties-legacy.md)|
||**Poista**|Poista valittu kohde.|
||**Kumoa** **(Ctrl+Z)**|Kumoa edellinen toiminto.|
||**Tee uudelleen** **(Ctrl+Y)**|Tee uudelleen edellinen toiminto.|
|**Valitse**|**Leipäteksti**|Muokkaa lomakkeen pääleipätekstiä.|
||**Ylätunniste**|Muokkaa lomakkeen ylätunnistetta.|
||**Alatunniste**|Muokkaa lomakkeen alatunnistetta.|
||**Siirtyminen**|Muokkaa lomakkeen siirtymisosaa.<br /><br /> Lisätietoja: [Siirtymisen muokkaaminen](use-the-form-editor-legacy.md)
|**Lomake**|**Liiketoimintasäännöt**|Tarkastele, muokkaa tai luo uusia liiketoimintasääntöjä Liiketoimintasääntöjen hallinnassa. **Huomautus:** Vuorovaikutteisissa lomakkeissa tuetaan vain Entiteetti- ja Kaikki lomakkeet -vaikutusaluetta.<br /><br /> Lisätietoja: [Liiketoimintasääntöjen luominen ja muokkaaminen](create-business-rules-recommendations-apply-logic-form.md)|
||**Lomakkeen ominaisuudet**| Lisätietoja: [Lomakkeen ominaisuudet](form-properties-legacy.md)|  
||**Esikatselu**|Tämän avulla voit nähdä, miltä lomake näyttää julkaisemisen jälkeen. Voit myös esikatsella testataksesi lomakkeen tapahtumiin liittyviä komentosarjoja.|         
||**Ota käyttöön käyttöoikeusroolit**|Tätä käyttämällä voit määrittää, mitkä käyttöoikeusroolit voivat käyttää lomakkeita. Lisätietoja: [Lomakkeiden käyttöoikeuksien hallinta](control-access-forms.md) **Tärkeää:** Jos luot uutta lomaketta, vain järjestelmänvalvojan ja järjestelmämukauttajan käyttöoikeusrooleilla on lomakkeen käyttöoikeus. Sinun on määritettävä käyttöoikeus muille käyttöoikeusrooleille, ennen kuin muut henkilöt voivat käyttää sitä.|  
||**Näytä riippuvuudet**|Katso, millä ratkaisun osilla on riippuvuus tähän lomakkeeseen ja mitä ratkaisun osia tämä lomake vaatii. Lisätietoja: [Ratkaisun riippuvuudet](../common-data-service/overview.md)|  
||**Hallitut ominaisuudet**|Hallittu ominaisuudet -komennolla on kaksi ominaisuutta: **Mukautettavissa** ja **Voidaan poistaa**. Jos näiden ominaisuuksien arvoksi asetetaan epätosi, lomaketta ei voi mukauttaa eikä poistaa sen jälkeen, kun lisäät sen ratkaisuun, viet kyseisen ratkaisun hallittuna ratkaisuna ja tuot kyseisen hallitun ratkaisun eri ympäristöön. Lisätietoja: [Hallitut ominaisuudet](../common-data-service/solutions-overview.md#managed-properties)| 
|**Päivitä**|**Yhdistä lomakkeet**|Mikäli sovellettavissa, tämän asetuksen avulla voit yhdistää tämän lomakkeen Dynamics 365 -lomakkeen aiemman version lomakkeeseen|
  

## <a name="insert-tab"></a>Lisää-välilehti  
![lisää-välilehti](media/insert-tab.png)
 
Lisää-välilehdessä näkyvät seuraavassa taulukossa olevat komennot:

|Ryhmä|Komento|Kuvaus|
|-----------|-------------|-----------------| 
||**Osa**|Lisää osa valittuun välilehteen. Voit sisällyttää osion, jossa on 1–4 saraketta.<br /><br /> Voit myös lisätä viitepaneelin vuorovaikutteisiin lomakkeisiin. Viitepaneeli lisätään myös osana Ensisijainen – vuorovaikutteinen kokemus -lomakkeeseen. Oletusarvon mukaan viitepaneeliosa lisätään Palvelupyyntö-, Tili-, Yhteyshenkilö- ja mukautettujen entiteettien lomakkeisiin.<br /><br /> Lisätietoja: [Osan ominaisuudet](section-properties-legacy.md)|  
|**3 välilehteä**|**Kolme saraketta**|Lisää kolmen sarakkeen välilehti yhtä leveillä sarakkeilla.<br /><br /> Lisätietoja: [Välilehden ominaisuudet](tab-properties-legacy.md)|  
||**Kolme saraketta**|Lisää kolmen sarakkeen välilehti leveämmällä keskisarakkeella.|  
|**2 välilehteä**|**Kaksi saraketta**|Lisää kahden sarakkeen välilehti leveämmällä oikealla sarakkeella.|  
||**Kaksi saraketta**|Lisää kahden sarakkeen välilehti leveämmällä vasemmalla sarakkeella.|  
||**Kaksi saraketta**|Lisää kahden sarakkeen välilehti yhtä leveillä sarakkeilla.|  
|**1 välilehti**|**Yksi sarake**|Lisää yhden sarakkeen välilehti.|  
|**Ohjausobjekti**|**Aliruudukko**|Muotoile aliruudukkoa ja lisää se lomakkeeseen.<br /><br /> Lisätietoja: [Aliruudukon ominaisuudet](sub-grid-properties-legacy.md)|  
||**Tyhjä väli**|Lisää tyhjä väli.|  
||**Pikalomakkeet**|Lisää pikalomake.<br /><br /> Lisätietoja: [Pikanäkymän ohjausobjektin ominaisuudet](quick-view-control-properties-legacy.md)|  
||**Verkkoresurssi**|Lisää verkkoresurssi sisällön upottamiseksi muista sijainneista yhdellä sivulla.<br /><br /> Lisätietoja: [Verkkoresurssin ominaisuudet](web-resource-properties-legacy.md)|  
||**IFRAME-kehys**|Voit lisätä IFRAME-kehyksen lomakkeeseen integroidaksesi sisältöä toisesta sivustosta lomakkeessa.| 
||**Aikajana**|Lisää aikajanan ohjausobjekti lomakkeeseen. Tämä ohjausobjekti näyttää lomakkeessa olevaan entiteettiin liittyvien aktiviteettien aikajanan.|  
||**Siirtymislinkki**|Tämän vaihtoehdon avulla voit lisätä linkin lomakkeen siirtymisosaan.|  
||**Ajastin**|Lisää ajastinohjausobjekti entiteettilomakkeeseen seurataksesi aikaa palvelutasosopimukseen verrattuna. Lisätietoja: [Lisää ajastinohjausobjekti](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla)|
||**Haku tietokannasta**|Lisää hakuohjausobjekti, jonka avulla käyttäjät voivat etsiä tietoartikkeleita. Lisätietoja: [Tietokannan haun ohjausobjekti](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-knowledge-base-search-control-forms)|  
||**Suhdeavustaja**|Tämän vaihtoehdon avulla voit lisätä suhdeavustajan ohjausobjektin lomakkeeseen.|

>[!Note] 
>Seuraavia osia ei tueta päälomakkeissa:<br> <ul> <li>Bing maps <br><li>Yammer <br><li>Toimintosyötteet <br> </li> </ul>


## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja sen osien käyttäminen](use-main-form-and-components.md)  
