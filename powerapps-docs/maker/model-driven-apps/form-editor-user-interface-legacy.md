---
title: PowerAppsin mallipohjaisen sovelluksen lomake-editorin käyttöliittymän yleiskatsaus | MicrosoftDocs
description: Tutustu PowerAppsin lomake-editorin käyttöliittymään
keywords: Lomakkeet; päälomake; Unified interface -sovellukset; Dynamics 365 for customer engagement
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.assetid: 146f8035-4fcd-4572-8e71-4270cd150495
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-the-model-driven-app-form-editor-user-interface"></a>Mallipohjaisen sovelluksen lomake-editorin käyttöliittymän yleiskatsaus

Lomake-editorin komennot sijaitsevat kolmessa välilehdessä: **Tiedosto**, **Aloitus** ja **Lisää**.  

- [Tiedosto-välilehti](#file-tab)
- [Koti-välilehti](#home-tab)
- [Lisää-välilehti](#insert-tab)
  
Lomake-editorissa on kolme aluetta: **siirtyminen**, **sisältö** ja **hallinta**.  

> [!div class="mx-imgBorder"] 
> ![Lomake-editorin käyttöliittymä](media/form-user-interface.png)
  
**Siirtyminen**  
Vasemmalla sijaitsevalla siirtymisalueella voit hallinta liittyvien entiteettien käyttöä tai lisätä lomakkeen pääruudussa näkyvien URL-osoitteiden linkkejä. Voit muokata siirtymistä valitsemalla ensin **Siirtyminen**-komennon **Valitse**-ryhmästä **Koti**-välilehdessä.

Päälomakkeiden siirtymisvaihtoehdot saadaan siirtymispalkista, mutta voit hallita käytettävissä olevia siirtymisvaihtoehtoja samoilla tiedoilla siirtymisalueella. Lisätietoja: [Siirtymisen muokkaaminen](use-the-form-editor-legacy.md)  


**Teksti** <br>
Voit hallita lomakkeen asettelua editorin keskellä sijaitsevalta runkoalueelta. Voit sijoittaa lomake-elementit valitsemalla ne ja vetämällä ne paikalleen. Elementin kaksoisnapsauttaminen avaa elementin ominaisuudet. 

Oletusarvoisesti palvelupyynnön, yhteyshenkilön ja asiakkaan päälomakkeissa näytetään ensimmäisessä **Yhteenveto**-välilehden kohdassa asiakkaan tai yhteyshenkilön **Pikanäkymä**-tyyppinen kortti. Mukautetuissa entiteeteissä tämä osa ei ole oletusarvoisesti käytettävissä. Uuden osan ja pikalomakkeen voi siihen lisätä. Kortin lomake näyttää enintään viisi kenttää. Kenttiä lukuun ottamatta sinisessä ruudussa ei voi näyttää muita ohjausobjekteja, vaikka pikalomake sellaisia sisältäisikin. 
 
>[!NOTE] 
> Kortin muodon säilyttämiseksi (kuten kuvassa), on suositeltavaa, että pikalomaketta ei siirretä lomakkeen mihinkään muuhun osaan.

> [!div class="mx-imgBorder"] 
> ![Korttimuoto](media/card-format.png)
   
Lisätietoja: [Pikalomakkeiden luominen ja muokkaaminen](create-edit-quick-view-forms.md)  
 
-   Lisää kenttä valitsemalla se **kenttien hallinnassa** ja vetämällä se osaan.  
  
    -   Voit lisätä elementin, joka ei ole kenttä, valitsemalla sen sijoituskohdan ja lisäämällä sen sopivalla **Lisää**-välilehden komennolla.  
  
    -   Voit poistaa elementin valitsemalla sen ja käyttämällä **Koti**-välilehden **Muokkaa**-ryhmän **Poista**-komentoa.  
  
    -   Jos haluat muokata lomakkeen **ylä-** tai **alatunnistetta**, sinun on ensin valittava vastaava komento **Koti**-välilehden **Valitse**-ryhmässä.  
  
**Hallinta**  
Oikealla sijaitsevan hallinta-alueen sisältö määräytyy kontekstin mukaan.  
  
Kun valitset **Koti**-välilehden **Valitse**-ryhmässä **Teksti**, **Ylätunniste** tai **Alatunniste**, **Kenttien hallinta** avautuu. Voit vetää **kenttien hallinnassa**näytettäviä kenttiä johonkin lomakkeen osaan. Kenttiä voi vetää myös ylä- tai alatunnisteessa. Samaa kenttää voi käyttää lomakkeessa useita kertoja. Käytä **Uusi kenttä** -painiketta uuden kentän luonnin pikakuvakkeena.  
  
Kun valitset **Koti**-välilehden **Valitse**-ryhmässä **Siirtyminen**, **Suhteiden hallinta** avautuu. Vedä jokin suhteista johonkin siirtymisalueen ryhmään. Samaa suhdetta ei voi lisätä kahdesti. Suhteiden käytettävyys perustuu niiden määrityksiin. Jos määrität suhteen siten, että se ei näy, se ei näy **suhteiden hallinnassa**. Saat tietoja siitä, miten voit määrittää suhteiden oletusarvonäyttöasetukset aiheesta [Ensisijaisen entiteetin siirtymisruudun kohde](../common-data-service/create-edit-1n-relationships-solution-explorer.md#navigation-pane-item-for-primary-entity).
  
Voit käyttää **Uusi 1:N**- ja **Uusi N:N** -painikkeita entiteettisuhteiden lisäämiseen nopeasti.  

## <a name="file-tab"></a>Tiedosto-välilehti

Voit lisätä tai tarkastella seuraavia asetuksia valitsemalla **Tiedosto**:

- **Uusi aktiviteetti** Lisää uusi aktiviteetti
- **Uusi tietue** Lisää uusi tietue
- **Työkalut** Käytä asetuksia, kuten Tuo tietoja, Kaksoiskappaleiden tunnistus ja Ohjattu joukkopoisto
- **Asetukset** Muuta oletusnäyttöasetuksia oletusratkaisun ulkoasun mukauttamista ja sähköpostimallien hallintaa varten
    - Yleiset
    - Synkronoiminen
    - Aktiviteetit
    - Muotoilut
    - Sähköpostimallit
    - Sähköpostin allekirjoitukset
    - Sähköposti
    - Tietosuoja
    - Kielivaihtoehdot
- Ohje
- Sulje


## <a name="home-tab"></a>Koti-välilehti  
 Seuraavassa taulukossa olevat komennot näkyvät **Aloitus**-välilehdessä:

> [!div class="mx-imgBorder"] 
> ![koti-välilehti](media/home-tab.png)

|Ryhmä|Komento|Kuvaus|
|-----------|-------------|-----------------| 
|**Tallenna**|**Tallenna** **(Ctrl+S)**|Tallenna lomake.|
||**Tallenna nimellä**|Luo lomakkeen kopio eri nimellä.|
||**Tallenna ja sulje**|Tallenna lomake ja sulje lomake-editori.|
||**Julkaise**|Julkaise lomake. Lisätietoja: Mukautusten julkaiseminen|
|**Muokkaa**|**Muuta ominaisuuksia**|Muuta rungossa valitun kohteen ominaisuuksia.<br /><br /> Seuraavat osat määräytyvät valitun kohteen mukaan:<br /><br /> -   [Välilehden ominaisuudet](tab-properties-legacy.md)<br />-   [Osan ominaisuudet](section-properties-legacy.md)<br />-   [Yleiset kentän ominaisuudet](common-field-properties-legacy.md)<br />-   [Erikoiskentän ominaisuudet](special-field-properties-legacy.md)<br />-  [Aliruudukon ominaisuudet](sub-grid-properties-legacy.md)<br />-   [Pikanäkymän ohjausobjektin ominaisuudet](quick-view-control-properties-legacy.md)|
||**Poista**|Poista valittu kohde.|
||**Kumoa** **(Ctrl+Z)**|Kumoa edellinen toiminto.|
||**Tee uudelleen** **(Ctrl+Y)**|Tee edellinen toiminto uudelleen.|
|**Valitse**|**Teksti**|Muokkaa lomakkeen pääosaa.|
||**Ylätunniste**|Muokkaa lomakkeen otsikkoa.|
||**Alatunniste**|Muokkaa lomakkeen alatunnistetta.|
||**Siirtyminen**|Muokkaa lomakkeen siirtymisosaa.<br /><br /> Lisätietoja: [Siirtymisen muokkaaminen](use-the-form-editor-legacy.md)
|**Lomake**|**Liiketoimintasäännöt**|Näytä, muokkaa tai luo uusia liiketoimintasääntöjä liiketoimintasääntöjen hallinnassa. **Huomautus:**  Vuorovaikutteisissa lomakkeissa tuetaan vain "Entiteetti"- ja "Kaikki lomakkeet" -vaikutusalueita.<br /><br /> Lisätietoja: [Liiketoimintasääntöjen luominen ja muokkaaminen](create-business-rules-recommendations-apply-logic-form.md)|
||**Lomakkeen ominaisuudet**| Lisätietoja: [Lomakkeen ominaisuudet](form-properties-legacy.md)|  
||**Esiversio**|Tämän avulla näet, miltä lomake näyttää julkaisemisen jälkeen. Voit esikatsella myös lomaketapahtumiin liitetyt testikomentosarjat.|         
||**Ota käyttöön käyttöoikeusroolit**|Tällä asetuksella voit määrittää millä käyttöoikeusrooleilla lomaketta saa käyttää. Lisätietoja: [Lomakkeiden käytön valvominen](control-access-forms.md) **Tärkeää:** Kun luot uuden lomakkeen, lomaketta saa käyttää vain järjestelmänvalvojan ja järjestelmän mukauttajan käyttöoikeusrooleilla. Käyttö on delegoitava muille käyttöoikeusrooleille, ennen kuin työntekijät voivat käyttää sitä.|  
||**Näytä riippuvuudet**|Katso, mitkä ratkaisun osat ovat riippuvaisia tästä lomakkeesta tai mitä ratkaisun osia tämä lomake edellyttää. |  
||**Hallitut ominaisuudet**|Hallitut ominaisuudet -komennossa on kaksi ominaisuutta: **Mukautettavissa** ja **Voi poistaa**. Kun näiden ominaisuuksien arvoksi määritetään epätosi, lomaketta ei mukauttaa eikä poistaa sen jälkeen, kun olet sisällyttänyt sen ratkaisuun, vienyt ratkaisun hallittuna ratkaisuna ja tuonut kyseisen hallitun ratkaisun toiseen ympäristöön. Lisätietoja: [Hallitut ominaisuudet](../common-data-service/solutions-overview.md#managed-properties)| 
|**Päivitä**|**Lomakkeiden yhdistäminen**|Jos käytettävissä, voit yhdistää tämän lomakkeen tällä asetuksella Dynamics 365 -lomakkeen edelliseen versioon|
  

## <a name="insert-tab"></a>Lisää-välilehti  
> [!div class="mx-imgBorder"] 
> ![lisää-välilehti](media/insert-tab.png)
 
Seuraavassa taulukossa olevat komennot näkyvät Lisää-välilehdessä:

|Ryhmä|Komento|Kuvaus|
|-----------|-------------|-----------------| 
||**Osa**|Lisää osa valittuun välilehteen. Voit sisällyttää osan johonkin neljästä sarakkeesta.<br /><br /> Voit myös lisätä vuorovaikutteiseen lomakkeeseen viitepaneelin. Viitepaneeli lisätään myös osana Päälomake - vuorovaikutteinen kokemus -lomakkeeseen. Oletusarvon mukaan viitepaneeliosa lisätään palvelupyynnön, asiakkaan ja yhteyshenkilön lomakkeisiin sekä mukautettuihin entiteetin lomakkeisiin.<br /><br /> Lisätietoja: [Osan ominaisuudet](section-properties-legacy.md)|  
|**3 Välilehdet**|**Kolme saraketta**|Lisää kolmen yhtä leveän sarakkeen välilehti.<br /><br /> Lisätietoja: [Välilehden ominaisuudet](tab-properties-legacy.md)|  
||**Kolme saraketta**|Lisää kolmen sarakkeen välilehti, jonka keskimmäinen sarake on muita leveämpi.|  
|**2 Välilehdet**|**Kaksi saraketta**|Lisää kahden sarakkeen välilehti, jonka oikea sarake on leveämpi.|  
||**Kaksi saraketta**|Lisää kahden sarakkeen välilehti, jonka vasen sarake on leveämpi.|  
||**Kaksi saraketta**|Lisää kaksisarakkeinen välilehti, jonka sarakkeet ovat yhtä leveitä.|  
|**1 välilehti**|**Yksi sarake**|Lisää yksisarakkeinen välilehti.|  
|**Ohjausobjekti**|**Aliruudukko**|Muotoile aliruudukko ja lisää se lomakkeeseen.<br /><br /> Lisätietoja: [Aliruudukon ominaisuudet](sub-grid-properties-legacy.md)|  
||**Tyhjä väli**|Lisää väli.|  
||**Pikalomake**|Lisää pikalomake.<br /><br /> Lisätietoja: [Pikanäkymän ohjausobjektin ominaisuudet](quick-view-control-properties-legacy.md)|  
||**WWW-resurssi**|Lisää verkkoresurssi upottaaksesi sisältöä muista sijainneista yhdelle sivulle.<br /><br /> Lisätietoja: [WWW-resurssin ominaisuudet](web-resource-properties-legacy.md)|  
||**IFRAME**|Voit lisätä IFRAME-kehyksen integroimaan toisen sivuston sisältöä lomakkeeseen.| 
||**Aikajana**|Lisää aikajanaohjausobjekti lomakkeessa. Tässä ohjausobjektissa esitetään lomakkeen entiteettiin liittyvien aktiviteettien aikajana.|  
||**Siirtymislinkki**|Voit lisätä tällä asetuksella linkin lomakkeen siirtymisosaan.|  
||**Ajastin**|Lisää ajastimen ohjausobjektin entiteettilomakkeeseen palvelutasosopimukseen perustuvan ajan seuraamista varten. Lisätiedot: [Ajastimen ohjausobjekti lisääminen](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-timer-control-case-form-track-time-against-sla)|
||**Haku tietämyskannasta**|Lisää hakuohjausobjekti, josta käyttäjät voivat hakea tietoartikkeleita. Lisätietoja: [Tietämyskantahaun ohjausobjekti](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customer-service/add-knowledge-base-search-control-forms)|  
||**Suhdeavustaja**|Voit lisätä tällä toiminnolla suhdeavustajan ohjausobjektin lomakkeessa.|

>[!Note] 
>Seuraavia osia ei tueta päälomakkeissa:<br> <ul> <li>Bing-kartat <br><li>Yammer <br><li>Toimintasyötteet <br> </li> </ul>


## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)  
