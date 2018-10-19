---
title: Mallipohjaisen sovelluksen muistiinpano-ohjausobjektin määrittäminen viestejä koskevien tietojen käyttämistä varten PowerAppsissa | MicrosoftDocs
ms.custom: ''
ms.date: 05/06/2018
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
ms.assetid: f10cdf1c-3540-439c-a171-27a10e72da45
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-up-the-model-driven-app-notes-control-to-access-information-about-posts"></a>Mallipohjaisen sovelluksen muistiinpano-ohjausobjektin määrittäminen viestejä koskevien tietojen käyttämistä varten

 Tiettyjen PowerApps-lomakkeissa, joissa on käytössä [päivitetyt lomakkeet](main-form-presentations.md#updated-forms), muistiinpano-ohjausobjektilla voidaan käyttää **viestejä**, **aktiviteetteja** ja **muistiinpanoja** koskevia tietoja. Mukautetuissa entiteeteissä, joissa muistiinpanot ja aktiviteetit on otettu käyttöön, vain **muistiinpanot** ja **aktiviteetit** näkyvät. Jos haluat myös **viestien** näkyvän, ne on otettava käyttöön mukautetussa entiteetissä.  
  
## <a name="enable-posts-for-a-custom-entity"></a>Viestien ottaminen käyttöön mukautetussa entiteetissä  
  
1.  Siirry kohtaan **[Asetukset](advanced-navigation.md#settings)** > **Toimintasyötteiden määrittäminen**. 
  
2.  Avaa tietue mukautettua entiteettiä varten.  
  
3.  Varmista, että **Ota seinät käyttöön tälle tietuelomakkeen tyypille** on valittu ja tallenna tietue.  
  
4.  Valitse komentopalkista **Aktivoi**.  
  
5.  Jos seinät on otettava käyttöön, entiteetti on julkaistava.  
  
 Muistiinpano-ohjausobjekti on sijoitettu järjestelmäentiteeteissä yhteisöruutuosaan, joka on kolmisarakkeisen välilehden keskellä lomakkeen yläosassa. Se voi olla lomakkeessa vain kerran. Voit siirtää tai poistaa muistiinpano-ohjausobjektin. Voit lisätä sen takaisin **Lisää**-välilehden **Ohjausobjekti**-ryhmän **Muistiinpanot**-painikkeella.  
  
 Seuraavassa taulukossa käsitellään muistiinpano-ohjausobjektin ominaisuuksia.  
  
|Välilehti|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Näyttö**|**Otsikko**|**Pakollinen**: vaikka otsikko ei näy oletusarvoisesti, se on pakollinen.|  
||**Näytä otsikko lomakkeessa**|Voit valita otsikon näyttämisen.|  
||**Lukitse kenttä lomakkeessa**|Tämä estää sen, että muistiinpanot poistettaisiin vahingossa lomakkeesta.|  
||**Oletusvälilehti**|Valitse oletusarvoisesti näytettävä välilehti. Vaihtoehdot ovat seuraavat:<br /><br /> - **Aktiviteetit**<br />- **Viestit**<br />- **Muistiinpanot**|  
|**Muotoilu**|**Valitse sarakkeiden määrä ohjausobjektia varten**|Kun muistiinpano-ohjausobjektin sisältävässä osassa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osassa on.|  
||**Rivien lukumäärä**|Voit hallita muistiinpano-ohjausobjektin korkeutta valitsemalla, kuinka monta riviä ohjausobjektia käyttää.|  
||**Laajenna automaattisesti käytettävissä olevaan tilaan**|Sen sijaan että korkeus määritettäisiin rivien määrän perusteella, voit sallia muistiinpano-ohjausobjektin laajentumisen käytettävissä olevaan tilaan.|  
  
## <a name="next-steps"></a>Seuraavat vaiheet
[Lomake-editorin avaaminen](open-form-editor.md)
