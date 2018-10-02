---
title: Ratkaisun luominen | MicrosoftDocs
description: Ratkaisun luominen
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-solution"></a>Ratkaisun luominen

Koska oletusratkaisu sisältää kaikki ratkaisun osat, mukauttamiesi ratkaisun osien etsiminen voi helpottua, jos luot erillisen ratkaisun ja mukautat vain sitä. Tämä helpottaa myös ratkaisun varmuuskopion viemistä, sillä tiedosto on pienikokoisempi. Jos päätät toimia näin, muista aina lisätä myös kaikki muokkaamasi ratkaisun osat tähän ratkaisuun. Kun luot uusia ratkaisun osia, sinun on aina luotava ne tässä ratkaisukontekstissa. Tällä tavoin ratkaisujulkaisijan mukautuksen etuliitettä käytetään johdonmukaisesti. Kun olet luonut ratkaisun osat ratkaisussasi tai lisännyt aiemmin luodut ratkaisun osat kyseiseen ratkaisuun, voit muokata niitä halutessasi myös oletusratkaisussa.  
  
 Lisätietoja ratkaisun käsitteistä on aiheessa [Ratkaisujen käsitteleminen](solutions-overview.md).  
  
1.  Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**. 
  
2.  Valitse **Uusi** ja lisää tiedot ratkaisun pakollisiin kenttiin.  
  
    |Kenttä|Kuvaus|  
    |-----------|-----------------|  
    |**Näyttönimi**|Ratkaisuluettelossa näkyvä nimi. Voit muuttaa tätä nimeä myöhemmin.|  
    |**Nimi**|Ratkaisun yksilöivä nimi. Se luodaan Näyttönimi-kentässä ilmoitetun arvon perusteella. Voit muokata sitä ennen ratkaisun tallennusta, mutta sitä ei voi muuttaa tallennuksen jälkeen.|  
    |**Julkaisija**|Voit valita oletusjulkaisijan tai luoda uuden julkaisijan. Käytä organisaation oletusjulkaisijaa, jos et aio jakaa ratkaisua.|  
    |**Versio**|Kirjoita ratkaisun versionumero. Tämä on tärkeää vain siinä tapauksessa, että viet ratkaisun. Versionumero on vietäessä osa ratkaisun tiedostonimeä.|  
  
3.  Valitse **Tallenna**.  
  
 Haluat ehkä lisätä ratkaisun tallennuksen jälkeen tietoja kenttiin, jotka eivät ole pakollisia. Seuraavat vaiheet ovat valinnaisia. Kirjoita **Kuvaus**-kenttään ratkaisun kuvaus ja valitse HTML-verkkoresurssi ratkaisun **määrityssivuksi**. Määrityssivua käyttävät yleensä ratkaisua jakavat riippumattomat ohjelmistotoimittajat. Kun se on määritetty, uusi **Määritys**-solmu näkyy **Tiedot**-solmun alapuolella ja verkkoresurssi näkyy siinä. Kehittäjät lisäävät tällä sivulla ohjeita tai ohjausobjekteja, joilla voit määrittää määritystietoja tai käynnistää ratkaisun.  
  
<a name="BKMK_AddSolutionComponents"></a>   

## <a name="add-solution-components"></a>Ratkaisun osien lisääminen  
 Luotu ratkaisu ei sisällä ratkaisun osia. Voit luoda uusia ratkaisun osia tai lisätä oletusratkaisun ratkaisun osia luettelovalikon **Lisää aiemmin luotu** -painikkeella.  
  
 Kun teet tämän, **Pakollisia osia puuttuu** -dialogi voi avautua.  
   
 ![Lisää Pakolliset osat -valintaikkuna](media/crm-itpro-cust-addrequiredcomponents.PNG "Lisää Pakolliset osat -valintaikkuna")  
  
 Dialogi varoittaa, että ratkaisun osa on riippuvainen muista ratkaisun osista. Jos valitset **Ei, älä lisää pakollisia osia**, ratkaisu ei ehkä toimi, jos viet sen toiseen organisaatioon, jossa ei ole kaikkia pakollisia osia. Jos ratkaisun tuonti onnistuu, ratkaisu ei ehkä toimi samoin kuin alkuperäisessä organisaatiossa, koska osat on määritetty eri tavalla kuin lähderatkaisun osat.  
  
 Yleensä on turvallisempaa lisätä pakolliset osat, jos aiot viedä ratkaisun toiseen organisaatioon. Jos et lisää näitä osia, kun lisäät yksittäisen ratkaisun osan, voit palata myöhemmin takaisin, valita lisätyn ratkaisun osan ja valita sitten valikossa **Lisää pakolliset osat**.  
  
 Jos et aio viedä ratkaisua tai jos aiot viedä sen vain ei-hallittuna ratkaisuna ja tuoda sen takaisin samaan organisaatioon, pakollisia osia ei tarvitse lisätä. Jos joskus viet ratkaisun, sama puuttuvista pakollista osista ilmoittava varoitus avautuu. Jos aiot tuoda ratkaisun vain takaisin samaan organisaatioon, tästä varoituksesta ei tarvitse välittää. Ohjeissa, jotka koskevat sovelluksen siirtymisruudun tai valintanauhan muokkaamista ilman kolmannen osapuolen työkalua, oletetaan, että viet ratkaisun takaisin samaan organisaatioon.  

> [!IMPORTANT]
>  Jos aiot lisätä ratkaisuihin tapaamisia, on erittäin suositeltavaa, ettet lisää erillisiin ratkaisuihin pelkästään tapaamisia tai pelkästään toistuvia tapaamisia. Jos asennat ja poistat erilaisia tapaamistyyppejä sisältäviä erillisiä ratkaisuja, järjestelmässä tapahtuu SQL Server -virhe ja tapaamiset täytyy luoda uudelleen. 
