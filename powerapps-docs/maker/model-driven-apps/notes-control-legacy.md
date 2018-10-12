---
title: Malliin perustuvan sovelluksen huomautusohjausobjektin määrittäminen julkaisujen tietojen tarkistamiseksi PowerAppsissa | MicrosoftDocs
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
ms.openlocfilehash: 014f0c2516813b7cbcaa8e44a188455b07056c71
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681217"
---
# <a name="set-up-the-model-driven-app-notes-control-to-access-information-about-posts"></a>Malliin perustuvan sovelluksen huomautusohjausobjektin määrittäminen julkaisujen tietojen tarkistamiseksi

 Tiettyjen [päivitettyjä lomakkeita](main-form-presentations.md#updated-forms) käyttävien järjestelmäentiteettien PowerApps-lomakkeiden huomautusohjausobjektin avulla voit tarkistaa tietoja **julkaisuista**, **aktiviteeteista** ja **huomautuksista**. Mukautetuissa entiteeteissä, joissa olet ottanut käyttöön huomautukset ja aktiviteetit, näet vain **huomautukset** ja **entiteetit**. Jos haluat sisällyttää myös **julkaisut**, sinun täytyy ottaa ne käyttöön mukautetulle entiteetille.  
  
## <a name="enable-posts-for-a-custom-entity"></a>Mukautetun entiteetin julkaisujen käyttöönotto  
  
1.  Valitse **[Asetukset](advanced-navigation.md#settings)** > **Toimintasyötteiden määritys**. 
  
2.  Avaa mukautetun entiteettisi tietue.  
  
3.  Tarkista, että asetus, jolla **otetaan käyttöön seinät tälle tietuelomaketyypille** on käytössä. Tallenna sitten tietue.  
  
4.  Valitse komentopalkista **Aktivoi**.  
  
5.  Jos sinun piti ottaa seinät käyttöön, sinun täytyy julkaista entiteetti.  
  
 Järjestelmäentiteeteissä huomautusohjausobjekti sijoitetaan oletusarvoisesti yhteisöosioon, joka sijaitsee kolmisarakkeisen välilehden keskellä lomakkeen yläreunassa. Se voidaan näyttää lomakkeessa vain kerran. Voit siirtää huomautusohjausobjektia ja poistaa sen. Jos haluat lisätä sen uudelleen, napsauta **Lisää**-välilehden **Ohjausobjekti**-ryhmän **Huomautukset**-painiketta.  
  
 Seuraavassa taulukossa kuvataan huomautusohjausobjektin ominaisuudet.  
  
|Välilehti|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Näyttö**|**Selite**|**Pakollinen**: vaikka selitettä ei oletusarvoisesti näytetä, se on pakollinen.|  
||**Näytä selite lomakkeessa**|Voit valita, näytetäänkö selite vai ei.|  
||**Lukitse kenttä lomakkeessa**|Tämä estää huomautusohjausobjektin poistamisen lomakkeesta vahingossa.|  
||**Oletusvälilehti**|Valitse, mikä välilehti näytetään oletusarvoisesti. Vaihtoehtoja ovat seuraavat:<br /><br /> - **Aktiviteetit**<br />- **Julkaisut**<br />- **Huomautukset**.|  
|**Muotoilu**|**Valitse ohjausobjektin kattamien sarakkeiden määrä**|Kun huomautusohjausobjektin sisältävässä osiossa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osiossa on.|  
||**Rivien määrä**|Voit määrittää huomautusohjausobjektin korkeuden valitsemalla sen rivien määrän.|  
||**Laajenna automaattisesti käytettävissä olevaan tilaan**|Sen sijaan, että määrittäisit korkeuden rivimäärän avulla, voit sallia huomautusohjausobjektin laajentamisen käytettävissä olevaan tilaan.|  
  
## <a name="next-steps"></a>Seuraavat vaiheet
[Lomake-editorin avaaminen](open-form-editor.md)
