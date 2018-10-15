---
title: Tilan syyn siirtymien määrittäminen PowerAppsissa | MicrosoftDocs
description: Lue, miten voit määrittää tilan syyn siirtymiä
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
ms.openlocfilehash: e21069a86d2ef21e8209fea6ea4a4b05e604cda4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678547"
---
# <a name="define-status-reason-transitions-for-the-case-or-custom-entities"></a>Tilan syyn siirtymien määrittäminen Tapaukselle tai mukautetuille entiteeteille

Voit määrittää tilan syyn siirtymät Incident (**Tapaus**) -entiteetille tai mukautetulle entiteetille.

> [!NOTE]
> Vaikka Incident (tapaus) -entiteetti ei sisälly oletusarvoiseen Common Data Service for Apps -ympäristöön, [Dynamics 365 for Customer Service](https://dynamics.microsoft.com/customer-service/) käyttää sitä, ja se on määritetty [Common Data Modelin](https://github.com/Microsoft/CDM/blob/master/schemaDocuments/core/applicationCommon/foundationCommon/crmCommon/service/Incident.cdm.json) sisällä
  
Tilan syyn siirtymät ovat valinnaisia lisätason suodattimia, joiden avulla voit määrittää, mikä tilan syyn arvo voidaan määrittää kullekin tilan syylle. Voit helpottaa muiden käyttäjien työtä rajoittamalla kelvollisten vaihtoehtojen määrää, jolloin sopivimman seuraavan tietueen tilan syyn valitseminen on yksinkertaisempaa, erityisesti jos käytettävissä on suuri määrä kelvollisia tilan syy -arvojen yhdistelmiä.  
  
<a name="BKMK_StatusAndStatusReasons"></a>

## <a name="what-is-the-connection-between-status-and-status-reason-fields"></a>Mikä on Tila ja Tilan syy -kenttien välinen yhteys?  

Entiteeteillä, joilla voi olla eri tila-arvoja, on kaksi kenttää, jotka sieppaavat näitä tietoja:  
  
|Näyttönimi|Kuvaus|  
|------------------|-----------------|  
|**Tila**|Esittää tietueen tilan. Yleensä **Aktiivinen** tai **Passiivinen**. Et voi lisätä uusia tila-asetuksia.|  
|**Tilan syy**|Esittää syyn, joka on yhdistetty tiettyyn tilaan. Jokaisella tilalla on oltava vähintään yksi mahdollinen tilan syy. Voit lisätä muita tilan syyn asetuksia.|  
  
Kentän metatiedot määrittävät ne tila-arvot, jotka kelpaavat kussakin tilassa. Esimerkiksi Incident (**Tapaus**) -entiteetin oletustila ja tilan syyn asetukset ovat:  
  
|Tila|Tilan syy|  
|------------|-------------------|  
|**Aktiivinen**|<li>**Keskeneräinen**</li><li>**Pidossa**</li><li>**Odotetaan tietoja**</li><li>**Tutkittavana**</li>| 
|**Ratkaistu**|<li>**Ongelma selvitetty**</li><li>**Tiedot annettu**</li>|
|**Peruutettu**|<li>**Peruutettu**</li><li>**Yhdistetty**</li>|
  
  
<a name="BKMK_EditStatusReasonTransitions"></a>   

## <a name="edit-status-reason-transitions"></a>Tila syyn siirtymien muokkaaminen
 
Voit muokata tilan syy -kentän asetuksia Tapaus-entiteetin ja mukautettujen entiteettien osalta, jolloin voit määrittää, mitä muita tilan syy -asetuksia käyttäjät saavat valita. Ainoa rajoitus on, että jokainen tilan syy -asetus aktiiviselle tilalle tulee sisältää ainakin yksi polku, joka johtaa passiiviseen tilaan. Muussa tapauksessa voisit luoda ehdon, joka ei antaisi ratkaista tai peruuttaa tapausta.  

> [!NOTE]
> Tilan syyn siirtymien muokkaaminen edellyttää ratkaisunhallinnan käyttöä. Saat lisätietoja kenttien muokkaamisesta kohdasta [Common Data Service for Appsin kenttien luominen ja muokkaaminen PowerAppsin ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md).
  
 Kun muokkaat tilan syy -kenttää, **Muokkaa tilan syyn siirtymiä** -painike näkyy valikossa. 

![Muokkaa tilan syyn siirtymiä -komento](media/status-reason-transitions-command.png)

Kun napsautat tätä painiketta, **Tilan syyn siirtymät** -valintaikkuna mahdollistaa **Ota käyttöön tilan syyn siirtymät** -asetuksen valitsemisen. Kun tämä asetus on valittuna, sinun tulee määrittää mitkä *muut* tilan syy -arvot sallitaan kullekin tilan syylle. Jos haluat lopettaa suodatuksen, poista **Ota käyttöön tilan syyn siirtymät** -asetuksen valinta. Määrittämäsi siirtymät säilytetään, mutta niitä ei käytetä.  
  
Alla olevassa näyttökuvassa on esimerkki, joka täyttää seuraavat vaatimukset: 
 
- Tapaus voidaan yhdistää milloin tahansa. Et voi yhdistää tapauksia, jos tilan syyn siirtymä ei salli sitä.  
- Aktiivisen tapauksen voi peruuttaa milloin tahansa.  
- Ratkaistua tai peruutettua tapausta ei voi aktivoida uudelleen.  
- Kaikkien tapauksien on käytävä läpi seuraavat vaiheet: **Keskeneräinen** > **Pidossa** > **Odotetaan tietoja** > **Tutkittavana** ennen kuin ne voidaan ratkaista. Tätä kokoonpanoa käytettäessä tapausta ei voi asettaa aiempaan tilaan.  
  > [!NOTE]
  >  Tämä ei ole hyvä esimerkki todellisesta työtilanteesta, mutta se osoittaa, miten eri tilan vaiheet voidaan pakottaa tilan syyn siirtymien kautta.  
  
 ![Esimerkki tapauksen tilan syyn siirtymistä](media/status-reason-transitions-example.PNG)  
  
### <a name="see-also"></a>Katso myös  

[Common Data Service for Appsin kenttien luominen ja muokkaaminen PowerAppsin ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md)<br />
[Entiteetin metatiedot > Entiteetin tilat](/powerapps/developer/common-data-service/entity-metadata#entity-states)<br />
[Mukautetun tilamallin siirrosten määrittäminen](/dynamics365/customer-engagement/developer/define-custom-state-model-transitions)

