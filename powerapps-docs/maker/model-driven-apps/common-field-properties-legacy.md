---
title: Mallipohjaisten sovellusten yleiset kentän ominaisuudet PowerAppsissa | MicrosoftDocs
description: Päälomakkeen yleisiin kentän ominaisuuksiin tutustuminen Dynamics 365 Customer Engagementissa
Keywords: Main form; Common field properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 2b91ee28-7f09-435e-9fae-5225aa698e22
ms.openlocfilehash: 74e67dd4299d06a54d5ec85765e4e5d03710b432
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675019"
---
# <a name="model-driven-app-common-field-properties"></a>Mallipohjaisten sovellusten yleiset kentän ominaisuudet

 Lomakkeen kentissä näytetään ohjausobjekteja, joiden avulla käyttäjät tarkastelevat tai muokkaavat entiteettitietueen tietoja. Kenttiä voi muotoilla siten, että ne kattavat jopa neljä saraketta osiossa.  

Voit käyttää **yleisiä kentän ominaisuuksia** ratkaisunhallinnassa. Valitse **Osat**, laajenna **Entiteetit** ja sitten haluamasi entiteetti ja valitse **Lomakkeet**. Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**. Voit tarkastella yleisiä kentän ominaisuuksia kaksoisnapsauttamalla jotakin kenttää.

![yleiset-kentän-ominaisuudet](media/common-field-properties.png)
  
Seuraavassa taulukossa on kuvaus kaikissa kentissä olevista ominaisuuksista. Tietyillä kentillä on erityisiä ominaisuuksia. Seuraavassa on kuvattu [erityiset kentän ominaisuudet](special-field-properties-legacy.md).  
  
|Sarkain|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Näytä**|**Selite**|**Pakollinen**: Selite vastaa oletusarvoisesti kentän näyttönimeä. Voit ohittaa tämän lomakkeen nimen kirjoittamalla uuden selitteen tähän.|  
||**Näytä selite lomakkeessa**|Voit myös olla näyttämättä selitettä.|  
||**Kentän toiminta**|Määritä kenttätason toiminta valintaruutujen avulla.|  
||**Lukitus**|Tämä estää sen, että kenttä poistettaisiin vahingossa lomakkeesta. Tämä estää sen, että kentässä käytetty määritys, kuten tapahtumakäsittely, poistettaisiin kentän poiston yhteydessä. Jos mukauttaja haluaa poistaa tämän kentän, hänen on ensin poistettava tämä asetus.|  
||**Näkyvyys**|Kentän näyttäminen on valinnaista, ja sitä voidaan hallita komentosarjoilla. Lisätietoja: [Näkyvyysasetukset](visibility-options-legacy.md)|  
||**Käytettävyys**|Valitse, haluatko, että puhelimessa voi käyttää välilehteä.|
|**Muotoilu**|**Valitse ohjausobjektin kattamien sarakkeiden määrä**|Kun kenttiä sisältävässä osiossa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osiossa on.|  
|**Tiedot**|**Näyttönimi**, **Nimi** ja **Kuvaus**|Nämä vain luku -kentät on tarkoitettu viitteeksi. Jos haluat muokata kentän kuvausta, voit avata sen kätevästi **Muokkaa**-painikkeella.<br /><br /> Lomakkeen kentän jokaisella esiintymällä on nimiominaisuus, jonka avulla niihin viitataan lomakkeen komentosarjoissa, mutta nimeä hallitsee sovellus. Kentän ensimmäinen esiintymä on nimi, joka kentälle luotaessa määritettiin. Lisätietoja: [Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-fields.md)<br /><br /> Aina kun lomakkeeseen lisätään kenttä, sen nimen loppuun liitetään numero luvusta 1 alkaen. Jos kentän nimi on siis new_cost, ensimmäisen esiintymän nimi lomakkeessa on new_cost, toisen new_cost1 ja niin edelleen kentän kunkin esiintymän kohdalla.<br /><br />**Huomautus:** **Kuvaus**-kentän arvo on työkaluvihjeen teksti, joka näkyy, kun käyttäjä asettaa osoittimen kentän päälle.|  
|**Tapahtumat**|**Lomakekirjastot**|Määritä JavaScript-verkkoresurssit, joita käytetään kentän `OnChange`-tapahtumakäsittelyssä.<br /><br />|  
||**Tapahtumakäsittelijät**|Määritä toiminnot lomakekirjastoista, jotka on kutsuttava kentän `OnChange`-tapahtumaa varten. Lisätietoja: [Tapahtumakäsittelijöiden määrittäminen](configure-event-handlers-legacy.md)|  
|**Liiketoimintasäännöt**|**Liiketoimintasäännöt**|Näytä ja hallitse tähän kenttään viittaavia liiketoimintasääntöjä. Lisätietoja: [Liiketoimintasääntöjen tai -suositusten luominen](create-business-rules-recommendations-apply-logic-form.md)|  
|**Ohjausobjektit**|**Ohjausobjektit**|Lisää ohjausobjekteja ja määritä niiden saatavuus verkossa, puhelimessa ja tabletissa.|  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja sen osien käyttäminen](use-main-form-and-components.md)
