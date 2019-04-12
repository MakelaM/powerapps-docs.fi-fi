---
title: Mallipohjaisen sovelluksen yleisen kentän ominaisuudet PowerAppsissa | MicrosoftDocs
description: Päälomakkeen yleiset kentän ominaisuudet Dynamics 365 Customer Engagementissa
Keywords: Päälomake; yleiset kenttäominaisuudet; Dynamics 365
author: Mattp123
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: powerapps
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 2b91ee28-7f09-435e-9fae-5225aa698e22
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-common-field-properties"></a>Mallipohjaisen sovelluksen yleisen kentän ominaisuudet

 Ohjausobjektit, joilla käyttäjät tarkastelevat tai muokkaavat entiteettitietueen tietoja, näkyvät lomakkeen kentissä. Kentät voidaan muotoilla käyttämään neljää osan saraketta.  

Voit käyttää **yleisiä kentän ominaisuuksia** ratkaisunhallinnassa. Laajenna ensin **Osat**-kohdassa **Entiteetit**, sitten haluamasi entiteetti ja napsauta **Lomakkeet**. Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**. Voit tarkastella yleisiä kentän ominaisuuksia kaksoisnapsauttamalla sitten jotakin kenttää.

![common-field-properties](media/common-field-properties.png)
  
Seuraavassa taulukossa on kuvaus kaikissa kentissä olevista ominaisuuksista. Tietyillä kentillä on erityisiä ominaisuuksia. Seuraavassa on kuvattu [erityiset kenttäominaisuudet](special-field-properties-legacy.md).  
  
|Välilehti|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Näytä**|**Otsikko**|**Pakollinen**: Otsikko vastaa oletusarvoisesti kentän nimeä. Voit ohittaa tämän lomakkeen nimen kirjoittamalla uuden otsikon tähän.|  
||**Näytä otsikko lomakkeessa**|Voit myös olla näyttämättä otsikkoa.|  
||**Kentän toiminta**|Määritä kenttätason toiminta valintaruutujen avulla.|  
||**Lukitus**|Tämä estää sen, että kenttä poistettaisiin vahingossa lomakkeesta. Tämä estää sen, että kentässä käytetty määritys, kuten tapahtumakäsittelijät, poistettaisiin kentän poiston yhteydessä. Jos mukauttaja haluaa poistaa tämän kentän, hänen olisi ensin poistettava tämä asetus.|  
||**Näkyvyys**|Kentän näyttäminen on valinnaista, ja sitä voidaan hallinta komentosarjoilla. Lisätietoja: [Näkyvyysasetukset](visibility-options-legacy.md)|  
||**Käytettävyys**|Valitse, haluatko, että puhelimessa voi käyttää välilehteä.|
|**Muotoilu**|**Valitse sarakkeiden määrä ohjausobjektia varten**|Kun kenttiä sisältävässä osassa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osassa on.|  
|**Tiedot**|**Näyttönimi**, **Nimi** ja **Kuvaus**|Nämä vain luku -kentät on tarkoitettu viitteeksi. Jos haluat muokata kentän kuvausta, voit avata sen kätevästi **Muokkaa**-painikkeella.<br /><br /> Lomakkeen kentän jokaisella ilmentymällä on nimiominaisuus, joiden avulla niihin viitataan lomakkeen komentosarjoissa. Nimen hallinnasta vastaa kuitenkin sovellus. Kentän ensimmäinen ilmentymä on nimi, joka kentälle luotaessa määritettiin. Lisätietoja: [Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-fields.md)<br /><br /> Aina kun kenttä sisällytetään lomakkeeseen, sen nimen loppuun liitetään numero luvusta 1 alkaen. Jos kentän nimi on siis new_cost, ensimmäisen ilmentymän nimi lomakkeessa on new_cost, toisen new_cost1 ja niin edelleen kentän kunkin ilmentymän kohdalla.<br /><br />**Huomautus:** **Kuvaus**-kentän arvo on kentän vieressä näkyvän työkaluvihjeen teksti, joka näkyy, kun käyttäjä asettaa osoittimen sen päälle.|  
|**Tapahtumat**|**Lomakekirjastot**|Määritä mikä tahansa JavaScript-WWW-resurssi, joita käytetään kentän `OnChange`-tapahtumakäsittelijässä.<br /><br />|  
||**Tapahtumakäsittelijät**|Määritä toiminnot lomakekirjastoista, jotka on kutsuttava kentän `OnChange`-tapahtumaa varten. Lisätietoja: [Tapahtumankäsittelijöiden määrittäminen](configure-event-handlers-legacy.md)|  
|**Liiketoimintasäännöt**|**Liiketoimintasäännöt**|Näytä ja hallitse tähän kenttään viittaavia liiketoimintasääntöjä. Lisätietoja: [Liiketoimintasääntöjen ja suositusten luominen](create-business-rules-recommendations-apply-logic-form.md)|  
|**Ohjausobjektit**|**Ohjausobjektit**|Lisää ohjausobjekteja ja määritä niiden saatavuus verkossa, puhelimessa ja tabletissa.|  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)
