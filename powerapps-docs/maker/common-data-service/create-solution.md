---
title: Ratkaisun luominen | MicrosoftDocs
description: Lue ohjeet ratkaisun luomiseen
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
author: Mattp123
ms.assetid: e21a4876-08b4-417a-a644-c577a27c5cf1
caps.latest.revision: 12
ms.author: matp
manager: kvivek
ms.openlocfilehash: 26ecc9b2f83375ba10e6b32dfc12d6cc37342cf4
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681206"
---
# <a name="create-a-solution"></a>Ratkaisun luominen

Jos olet luomassa erillistä ratkaisua, sinulle voi olla helpompaa etsiä vain mukauttamasi ratkaisukomponentit, ja tehdä sitten kaikki mukautuksesi tässä erillisessä ratkaisussa, koska oletusratkaisu sisältää kaikki ratkaisukomponentit. Tämän ansiosta voit myös viedä ratkaisusi varmuuskopion pienempänä tiedostona. Jos teet näin, sinun täytyy muistaa aina lisätä kaikki muokkaamasi ratkaisukomponentit tähän ratkaisuun. Kun luot uusia ratkaisukomponentteja, luo ne aina tämän ratkaisun kontekstissa. Tällä tavalla käytetty ratkaisujulkaisijan etuliite pysyy johdonmukaisena. Kun olet luonut ratkaisukomponentteja ratkaisuusi tai lisännyt olemassa olevia ratkaisukomponentteja tähän ratkaisuun, voit muokata niitä halutessasi myös oletusratkaisussa.  
  
 Lue lisätietoja [ratkaisujen käytöstä](solutions-overview.md).  
  
1.  Valitse **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**. 
  
2.  Valitse **Uusi** ja anna tiedot ratkaisun pakollisiin kenttiin.  
  
    |Kenttä|Kuvaus|  
    |-----------|-----------------|  
    |**Näyttönimi**|Tämä on nimi, joka näytetään ratkaisuluettelossa. Voit vaihtaa tätä myöhemmin.|  
    |**Nimi**|Tämä on ratkaisun yksilöivä nimi. Se luodaan Näyttönimi-kentässä antamasi nimen pohjalta. Voit muokata tätä ennen ratkaisun tallentamista, mutta et tallentamisen jälkeen.|  
    |**Julkaisija**|Voit valita oletusjulkaisijan tai luoda uuden julkaisijan. Jos et aio jaella ratkaisuasi, käytä organisaatiosi oletusjulkaisijaa.|  
    |**Versio**|Anna tähän ratkaisusi versionumero. Tällä on merkitystä vain, jos viet ratkaisun. Versionumero sisällytetään tiedostonimeen, kun viet ratkaisun.|  
  
3.  Valitse **Tallenna**.  
  
 Kun olet tallentanut ratkaisun, voit lisätä tietoja myös vapaaehtoisiin kenttiin. Tämä ei ole pakollista. **Kuvaus**-kenttään voit antaa kuvauksen ratkaisustasi. Voit myös valita verkkoresurssin, jota käytetään ratkaisun **määrityssivuna**. Määrityssivua käyttävät yleensä itsenäiset ohjelmistokehittäjät, jotka jakelevat ratkaisuja. Kun olet määrittänyt nämä, näet **tietosolmun** alla **määrityssolmun**, jossa tämä verkkoresurssi näytetään. Kehittäjät voivat lisätä tälle sivulle ohjeita tai ohjausobjekteja, joilla voidaan määrittää määritystietoja tai käynnistää ratkaisu.  
  
<a name="BKMK_AddSolutionComponents"></a>   

## <a name="add-solution-components"></a>Ratkaisukomponenttien lisääminen  
 Kun olet luonut ratkaisun, se ei sisällä mitään ratkaisukomponentteja. Voit luoda uusia ratkaisukomponentteja tai lisätä oletusratkaisun ratkaisukomponentteja luettelovalikon **Lisää aiemmin luotu** -painikkeella.  
  
 Jos teet näin, saatat nähdä **Pakollisia osia puuttuu** -valintaikkunan.  
   
 ![Lisää pakolliset osat -valintaikkuna](media/crm-itpro-cust-addrequiredcomponents.PNG "Lisää pakolliset osat -valintaikkuna")  
  
 Tässä valintaikkunassa saat varoituksen, jos ratkaisukomponentilla on riippuvuuksia muihin ratkaisukomponentteihin. Jos valitset toiminnon, joka **ei sisällytä pakollisia komponentteja**, ratkaisu saattaa epäonnistua, jos tuot sen toiseen organisaatioon, jossa näitä pakollisia komponentteja ei ole olemassa. Jos ratkaisun tuominen onnistuu, se ei ehkä toimi täysin samalla tavalla kuin alkuperäisessä organisaatiossa, koska komponentit on määritetty eri tavalla kuin lähderatkaisussa.  
  
 Yleensä pakolliset komponentit kannattaa sisällyttää, jos aiot viedä ratkaisun toiseen organisaatioon. Jos et lisää näitä komponentteja, kun lisäät yksittäisen ratkaisukomponentin, voit palata myöhemmin, valita lisäämäsi ratkaisukomponentin ja valitse valikosta **Lisää pakolliset osat**.  
  
 Jos et aio viedä ratkaisua tai jos aiot ainoastaan viedä sen hallitsemattomana ratkaisuna ja tuoda sen sitten takaisin samaan organisaatioon, pakollisia komponentteja ei ole tarpeen sisällyttää. Jos joskus viet ratkaisun, saat uuden varoituksen siitä, että joitain pakollisia komponentteja puuttuu. Jos aiot ainoastaan tuoda tämän ratkaisun takaisin samaan organisaatioon, voit ohittaa tämän varoituksen. Toimenpiteet sovelluksen siirtymistoimintojen tai valintanauhan muokkaamiseksi ilman ulkopuolisen palveluntarjoajan työkalua toimivat sillä oletuksella, että viet ratkaisun takaisin samaan organisaatioon.  

> [!IMPORTANT]
>  Jos aiot sisällyttää tapaamisia ratkaisuihin, suosittelemme vahvasti, että et sisällytä vain tapaamisia ja vain toistuvia tapaamisia erillisiin ratkaisuihin. Jos asennat ja poistat erilliset ratkaisut erilaisilla tapaamistyypeillä, saat SQL Serverin virheen. Lisäksi sinun täytyy luoda tapaamiset uudelleen. 
