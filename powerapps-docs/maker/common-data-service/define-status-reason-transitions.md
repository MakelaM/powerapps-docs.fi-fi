---
title: Tilan syyn siirtymien määrittäminen PowerAppsin avulla | MicrosoftDocs
description: Tilan syyn siirtymien määrittäminen
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: dbc4f436-0b23-42f9-8079-b0de482aaebe
caps.latest.revision: 11
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="define-status-reason-transitions-for-the-case-or-custom-entities"></a>Palvelupyyntöjen tai muokattujen entiteetien tilan syyn siirtojen määrittäminen

Voit määrittää tilan syyn siirtymät Esiintymä (**Palvelupyyntö**) -entiteetille tai mukautetuille entiteeteille.

> [!NOTE]
> Vaikka tapauksen (palvelupyynnön) entiteetti ei kuulu Common Data Service sovelluksille -oletusratkaisuun, [Dynamics 365 for Customer Service](https://dynamics.microsoft.com/customer-service/) käyttää sitä ja se on määritetty [Common Data Model](https://github.com/Microsoft/CDM/blob/master/schemaDocuments/core/applicationCommon/foundationCommon/crmCommon/service/Incident.cdm.json) -palvelussa
  
Tilan syyn siirtymät ovat valinnainen, ylimääräinen suodatustaso, jolla määritetään, mitä tilan syyn arvoa voidaan muuttaa kussakin tilan syyssä. Kun rajallinen arvovaihtoehtojen luettelo on määritetty, käyttäjien on helpompi valita tietueelle oikea seuraava tilan syy, kun valittavana on runsaasti kelvollisia tilan syyn arvoyhdistelmiä.  
  
<a name="BKMK_StatusAndStatusReasons"></a>

## <a name="what-is-the-connection-between-status-and-status-reason-fields"></a>Tila- ja Tilan syy-kenttien välinen yhteys  

Entiteeteillä jolla voi olla eri tila-arvoja on kaksi kenttää näiden tietojen keräämiseksi:  
  
|Näyttönimi|Kuvaus|  
|------------------|-----------------|  
|**Tila**|Ilmaisee tietueen aktiivisuustilan. Yleensä **Aktiivinen** tai **Passiivinen**. Et voi lisätä uusia tilavaihtoehtoja.|  
|**Tilan syy**|Ilmaisee tiettyyn tilaan linkitetyn syyn. Kullakin tilalla on oltava vähintään yksi mahdollinen tilan syy. Voit lisätä uusia tilan syy -vaihtoehtoja.|  
  
Kentän metatiedot määrittävät, mitä tilan arvoja voi käyttää tietyssä tilassa. Esimerkiksi (**Palvelupyyntö**)-entiteetillä on seuraavat oletustila- ja tilan syy -vaihtoehdot:  
  
|Tila|Tilan syy|  
|------------|-------------------|  
|**Aktiivinen**|<li>**Kesken**</li><li>**Pidossa**</li><li>**Odotetaan tietoja**</li><li>**Tutkittavana**</li>| 
|**Ratkaistu**|<li>**Ongelma ratkaistu**</li><li>**Annetut tiedot**</li>|
|**Peruutettu**|<li>**Peruutettu**</li><li>**Yhdistetty**</li>|
  
  
<a name="BKMK_EditStatusReasonTransitions"></a>   

## <a name="edit-status-reason-transitions"></a>Tilan syyn siirtymien muokkaaminen
 
Voit muokata Tapaus-entiteetin ja mukautettujen entiteettien tilan syy -kenttäasetuksia määrittääksesi, mitä muita tilan syy -vaihtoehtoja käyttäjät voivat valita. Ainoa rajoitus on, että kullekin tilan syy -vaihtoehdon aktiiviselle tilalle on sallittava vähintään yksi polku passiiviseen tilaan. Muussa tapauksessa voitaisiin luoda ehto, jossa palvelupyyntöä ei voi ratkaista eikä peruuttaa.  

> [!NOTE]
> Tilan syyn siirtojen muokkaaminen edellyttää ratkaisunhallintaa. Lisätietoja kenttien muokkaamisesta on kohdassa [Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md).
  
 Tilan syy -kenttää muokatessa **Muokkaa tilan syyn siirtymiä** -painike näkyy valikossa. 

![Muokkaa tilan syyn siirtoja -komento](media/status-reason-transitions-command.png)

Kun napsautat painiketta, voit valita **Tilan syyn siirrot** -valintaikkunassa **Ota tilan syyn siirrot käyttöön**. Kun tämä vaihtoehto on valittu, sinun on määritettävä kunkin tilan syyn käytössä olevat *muut* tilan syyn arvot. Voit poistaa käytetyn suodatuksen poistamalla **Ota tilan syyn siirtymät käyttöön** -vaihtoehdon valinta. Määritetyt siirtymät säilytetään, mutta niitä ei käytetä.  
  
Seuraavassa näyttökuvassa on esimerkki, joka täyttää seuraavat vaatimukset: 
 
- Palvelupyyntö voidaan yhdistää milloin tahansa. Et voi yhdistää palvelupyyntöjä, jos tilan syyn siirtymä ei salli sitä.  
- Aktiivinen palvelupyyntö voidaan peruuttaa milloin tahansa.  
- Ratkaistua tai peruutettua palvelupyyntöä ei voi aktivoida uudelleen.  
- Kaikki palvelupyynnöt on käsiteltävä seuraavissa vaiheissa, ennen kuin ne voidaan ratkaista: **Kesken** > **Pidossa** > **Odotetaan tietoja** > **Tutkittavana**. Tässä määrityksessä palvelupyyntöä ei voitu määrittää aiempaan tilaan.  
  > [!NOTE]
  >  Tämä ei kuvaa hyvin todellisia töitä mutta se osoittaa, miten tilan vaiheet voidaan pakottaa käyttöön tilan syyn siirtymien avulla.  
  
 ![Esimerkki palvelupyynnön tilan syyn siirrolle](media/status-reason-transitions-example.PNG)  
  
### <a name="see-also"></a>Katso myös  

[Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md)<br />
[Entiteetin metatiedot > Entiteetin tilat](/powerapps/developer/common-data-service/entity-metadata#entity-states)<br />
[Mukautetun tilan mallisiirtojen määrittäminen](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions)

