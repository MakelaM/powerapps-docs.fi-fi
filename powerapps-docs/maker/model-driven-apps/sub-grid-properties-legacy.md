---
title: Mallipohjaisen sovelluksen päälomakkeiden aliruudukon ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeiden Aliruudukko-resurssin ominaisuuksista
Keywords: Päälomake; aliruudukon ominaisuudet; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/07/2018
ms.service: powerapps
ms.topic: article
ms.assetid: 82892cd3-3436-4677-b96b-f2ccd0a4f078
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="sub-grid-properties-for-model-driven-app-main-forms-overview"></a>Mallipohjaisten sovellusten päälomakkeiden aliruudukoiden ominaisuuksien yleiskatsaus

Voit määrittää aliruudukon lomakkeessa näyttämään tietueluettelon tai kaavion. Kun valitset **Näytä vain kaavio** **Näytä**-välilehdessä, luettelon sijasta näytetään kaavio.  

Voit käyttää **Aliruudukon ominaisuudet** -kohtaa PowerApps-sivustossa. 
1.  Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

     ![Mallipohjainen suunnittelutila](media/model-driven-switch.png)

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti. 

3.  Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**. Voit tarkastella aliruudukon ominaisuuksia valitsemalla **Lisää**-välilehdessä **Aliruudukko**.

    ![aliruudukon ominaisuudet](media/sub-grid-properties.png)
  
|Välilehti|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Näytä**|**Nimi**|**Pakollinen**: Aliruudukon yksilöivä nimi, jolla siihen viitataan komentosarjoissa. Nimessä voi olla vain aakkosnumeerisia merkkejä ja alaviivoja.|  
||**Otsikko**|**Pakollinen**: aliruudukon lokalisoitava otsikko, jonka käyttäjä näkee.|  
||**Näytä otsikko lomakkeessa**|Valitaan, näytetäänkö otsikko lomakkeessa. Tämä on pakollinen, jos **Näytä hakukenttä** on otettu käyttöön. Voit valita myös paneelin otsikon värin.|  
||**Tietueet**|Valitse jompikumpi vaihtoehto:<br /><br /> - **Vain liittyvät tietueet**: aliruudukko näyttää vain nykyiseen tietueeseen liittyvät tietueet.<br />- **Kaikki tietuetyypit**: aliruudukko näyttää vain oletusnäkymän suodattamat tietueet tai, jos näkymän valitsin on otettu käyttöön, kaikki käyttäjän valitsemat näkymät.<br /><br /> Valittu vaihtoehto vaikuttaa Näytä luettelo -ohjausobjektin toimintaan. Lisätietoja: [Luettelon toimintatavan näyttäminen](#show-list-behavior) |  
||**Entiteetti**|**Tietueet**-kohdassa valitun asetuksen mukaan luettelossa näkyy jompikumpi seuraavista:<br /><br /> - **Vain liittyvät tietueet**: luettelo kaikista tähän entiteettiin liittyvistä entiteeteistä ja sulkeissa suhteen määrittävän entiteetin valintakentän nimi.<br />- **Kaikki tietuetyypit**: kaikki entiteetit sisältävä luettelo.|  
||**Oletusnäkymä**|Valitse oletusarvoisesti käytettävä näkymä. Jos et ota muita näkymiä käyttöön **Näkymän valitsin** -ominaisuudella, tämä on ainoa näkymä.<br /><br /> Avaa oletusnäkymä muokkausta varten **Muokkaa**-painikkeella. Luo aliruudukossa käytettävä uusi näkymä **Uusi**-painikkeella.|  
||**Näytä hakukenttä**|Näytä hakukenttä. Kun tämä vaihtoehto on valittu, **Näytä otsikko lomakkeessa** -asetus on pakollinen.|  
||**Näytä indeksi**|Vain lomakkeet, joissa on käytössä [Klassiset lomakkeet](main-form-presentations.md#classic-forms) tukevat indeksin näyttöä.<br /><br /> Valitse tämä valintaruutu, jos haluat, että luettelossa on käytettävissä aakkosellinen hakemisto. Näin voit siirtyä suoraan tietyllä kirjaimella tai numerolla alkaviin tietueisiin.|  
||**Näkymän valitsin**|Käytössä on kolme vaihtoehtoa:<br /><br /> - **Ei käytössä**: vain oletusnäkymää voidaan käyttää.<br />- **Näytä kaikki näkymät**: käyttäjät voivat valinta minkä tahansa näkymän.<br />- **Näytä valitut näkymät**: valitse näytettävät näkymät Ctrl-näppäimellä ja kohdistimella.|  
||**Oletuskaavio**|Valitse, mikä kaavio näytetään, jos **Näytä vain kaavio** on valittu.|  
||**Näytä vain kaavio**|Tietueluettelon sijaan näytetään kaavio.|  
||**Näytä kaavion valinta**|Jos **Näytä vain kaavio** on valittu, käyttäjät voivat valita erilaisia kaavioita.|  
||**Käytettävyys**|Määritä, onko osa käytettävissä puhelimessa.|
|**Muotoilu**|**Asettelu**|**Valitse sarakkeiden määrä ohjausobjektia varten**.<br /><br /> Kun aliruudukon sisältävässä osassa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osassa on.|  
||**Riviasettelu**|**Rivien määrä** määrittää, kuinka monta tietuetta aliruudukon sivulla näytetään.<br /><br /> Jos **Laajenna automaattisesti käytettävissä olevaan tilaan** on valittu, lomakkeessa on tilaa kahdelle tietueelle ja tilaa laajennetaan tietueiden määrän kasvaessa. Jos tietueiden määrä on suurempi kuin **Rivien määrä**, käyttäjät voivat tarkastella tietueita siirtymällä muille sivuille.<br /><br /> Jos **Laajenna automaattisesti käytettävissä olevaan tilaan** ei ole valittu, lomake varaa tilaa tietueille **Rivien määrä** -kohdan määritysten mukaisesti ja käyttäjät voivat tarkastella muita tietueita siirtymällä muille sivuille.|  
|**Ohjausobjektit**|**Ohjausobjektit**|Valitse ohjausobjektien lisääminen. Valitse valintanappi käytettäväksi verkossa, puhelimessa tai tabletissa.|
  
 Jos lomakkeessa ovat käytössä [klassiset lomakkeet](main-form-presentations.md#classic-forms), aliruudukon toiminnot olivat käytettävissä valintanauhasta. Kehittäjät voivat mukauttaa näiden toimintojen toimintaa tai lisätä muita toimintoja mukauttamalla valintanauhaa.  
  
 Jos lomakkeiden aliruudukoissa käytetään [Päivitettyjä lomakkeita](main-form-presentations.md#updated-forms), ne sijoitetaan aliruudukon lähelle, mikä helpottaa niiden käyttöä. Komentopalkki ei kuitenkaan salli mukautettujen toimintojen lisäämistä. Kehittäjät voivat muokata jäljellä olevan kolmen toiminnon toimintoja valintanauhaa muokkaamalla. Nämä toiminnot ovat luettelon näyttäminen, tietueen lisääminen ja tietueen poistaminen.  
  

## <a name="show-list-behavior"></a>Luettelon toiminnan näyttäminen  
 Kun luettelo näytetään lomakkeissa, joissa on käytössä [Updated forms](main-form-presentations.md#updated-forms), kussakin aliruudukossa näkyy **Avaa näkymä** painike ![Avaa näkymä -painike](media/crm-itpro-cust-openview.PNG "Avaa näkymä -painike") oikeassa yläkulmassa, kun entiteetti näkyy yhtenä lomake-editorin siirtymisalueen entiteettinä. Näkymän voi avata valitsemalla tämän painikkeen. Toiminto muuttuu **Tietueet**-ominaisuudelle valitun asetuksen mukaan.  
  
 Kun valitset **Vain liittyvät tietueet**, näkymä avataan käyttämällä yhtä saman ikkunan liittyvää näkymää. Palaa lomakkeeseen siirtymispalkin Takaisin-painikkeella tai valitsemalla nykyisen tietueen ensisijaisen nimen arvo.  
  
 Kun valitset **Kaikki tietuetyypit**, näkymä avautuu uuteen ikkunaan.  

## <a name="add-record-behavior"></a>Tietueen lisäystoiminto  
 Kun luettelo näytetään lomakkeessa, jossa on käytössä [päivitetyt lomakkeet](main-form-presentations.md#updated-forms), kussakin aliruudukossa näkyy **Lisää tietue** -painike ![Lisää painike](media/crm-itpro-cust-subgridadd.PNG "Lisää painike") aliruudukon oikeassa yläkulmassa. Voit lisätä tietueen valitsemalla tämän painikkeen. Toiminto määräytyy **Tietueet**-ominaisuudelle valitun asetuksen mukaan ja sen mukaan, onko valinnassa kyse aktiviteettitietueista.  
  
 Kun valitset **Vain liittyvät tietueet**, oletustoimintana on aiemmin luotujen tietueiden lisääminen. Käyttäjät näkevät tekstiin sidotun valinnan, jolla he voivat hakea ensin aiemmin luotua tietuetta. Tämä estää tietueiden kaksoiskappaleiden luonnin.  Jos aiemmin luotua tietuetta ei löydy, he voivat valita **Uusi**-asetuksen. Uutta tietuetta luotaessa otetaan käyttöön suhteeseen määritetty kentän yhdistämismääritys. Lisätietoja: [Entiteettikenttien yhdistäminen](../common-data-service/map-entity-fields.md)   
  
 Kun valitset **Kaikki tietuetyypit**, oletustoimintana on uuden tietueen lisääminen. Pikalomake näytetään, jos kohde-entiteetissä on sellainen. Muussa tapauksessa näytetään entiteetin päälomake.  
  
 Jos aliruudukossa näkyy aktiviteetteja, käyttäjien on ensin valittava aktiviteettityyppi, jolloin näkyviin tulee Lisää uusi tietue -toiminto.  
  
## <a name="delete-record-behavior"></a>Tietueen poistotoiminto  
 Kun valitset tietueen aliruudukossa, **Poista**-painike ![Aliluettelon poistokuvake](media/crm-itpro-cust-subgriddelete.PNG "Aliluettelon poistokuvake") tulee näkyviin rivin oikealle puolelle. Poistotoiminnon toiminta vaihtelee sen mukaan, minkälainen suhde nykyiseen entiteettiin on.  
  
 Kun aliruudukossa käytetään 1:N (yksi moneen) -suhdetta, tietueen normaalissa poistotoiminnassa näytetään vahvistusikkuna ennen tietueen poistamista.  
  
 Jos aliruudukossa käytetään N:N (monta moneen) -suhdetta, suhteen (tai leikkauksen) entiteetin tietue, joka liittyy kahteen tietueeseen, poistetaan ilman vahvistusta eikä tietue enää näy aliruudukossa. Näytettyä tietuetta ei kuitenkaan poisteta.  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)
