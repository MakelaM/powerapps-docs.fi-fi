---
title: Mallipohjaisen sovelluksen lomakkeen suorituskyvyn optimointi PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten voit välttää lomakkeen suunnitteluja, jotka saavat lomakkeen lataamaan hitaasti'
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 59cfa5e6-638a-437f-a462-fddfd26fb07d
caps.latest.revision: 8
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="optimize-model-driven-app-form-performance"></a>Mallipohjaisen sovelluksen lomakkeen suorituskyvyn optimointi

Lomakkeet, joka latautuvat hitaasti, voivat vähentää tuottavuutta ja käyttäjän käyttöönottoa. Seuraavien suositusten avulla suurennat lomakkeiden nopeaa latautumista. Monet näistä suosituksista kertovat siitä, miten sovelluskehittäjä voi toteuttaa lomakkeen komentosarjoja organisaatiossasi. Muista neuvotella näistä suosituksista niiden sovelluskehittäjien kanssa, jotka luovat lomakkeiden komentosarjoja lomakkeisiisi.  
  
<a name="BKMK_FormDesign"></a>   
## <a name="form-design"></a>Lomakkeen asettelu  
 Mieti sitä vuorovaikutusta, joka käyttäjällä on lomakkeen kanssa sekä sitä tietomäärää, joka lomakkeen on näytettävä.  
  
 **Säilytä kenttien määrä vähimmäismäärässä**  
 Mitä enemmän kenttiä sinulla on lomakkeessa, sitä enemmän tietoa täytyy siirtää Internetiin tai intranetiin kunkin tietueen tarkastelua varten.  
  
<a name="BKMK_FormScripts"></a>   
## <a name="form-scripts"></a>Lomakkeiden komentosarjat  
 Kun sinulla on mukautuksia, jotka käyttävät lomakkeen komentosarjoja, varmista, että kehittäjä ymmärtää näitä strategioita parantaakseen suorituskykyä.  
  
 **Vältä tarpeetonta JavaScript WWW-resurssikirjastojen sisällyttämistä**  
 Mitä enemmän komentosarjoja lisäät lomakkeeseen, sitä enemmän aikaa menee niiden lataamiseen. Yleensä komentosarjat tallennetaan välimuistiin selaimessasi, kun ne on ladattu ensimmäisen kerran, mutta suorituskyky ensimmäisen kerran, kun lomaketta tarkastellaan, luo usein merkittävän vaikutelman.  
  
 **Vältä kaikkien komentosarjojen lataamista Onload-tapahtumaan**  
 Jos koodi tukee ainoastaan `OnChange` tapahtumia kentissä tai `OnSave` tapahtumaa, varmista, että voit määrittää komentosarjan kirjaston tapahtuman käsittelijän kanssa niille tapahtumille `OnLoad` -tapahtuman sijaan. Tällä tavoin ladatut kirjastot voidaan lykätä, ja parantaa suorituskykyä, kun lomake latautuu.  
  
 **Käytä tiivistettyjä välilehtiä lykätäksesi verkkoresurssien latausta**  
 Kun verkkoresursseja tai IFRAMEja sisältyy osiin tiivistetyssä välilehdessä, niitä ei ladata, jos välilehti on tiivistetty. Ne ladataan, kun välilehti on laajennettu. Välilehti-tilan muuttuessa `TabStateChange` -tapahtuma toteutuu. Mikä tahansa koodi, jota tarvitaan tukemaan WWW-resursseja tai IFRAME-kehystä tiivistettyjen välilehtien sisällä, voi käyttää tapahtumankäsittelijöitä **TabStateChange** -tapahtumaan ja vähentää koodia, joka ehkä muuten ilmenisi `OnLoad` -tapahtumassa.  
  
 **Määrittää näkyvyyden oletusasetukset**  
 Vältä käyttämästä lomakkeen komentosarjoja `OnLoad` -tapahtumassa, joka piilottaa lomakkeen osia. Sen sijaan määritä lomake-elementeille näkyvyyden oletusasetukset, jotka saattavat olla piilossa oletusarvoisesti, kun lomake latautuu. Voit käyttää komentosarjoja `OnLoad` -tapahtumassa näyttääksesi ne lomakkeen osat, jotka haluat näyttää.  
  
<a name="BKMK_CommandBar"></a>   
## <a name="command-bar-or-ribbon"></a>Työkalurivi tai valintanauha  
 Pidä mielessä nämä suositukset, kun muokkaat työkaluriviä tai valintanauhaa.  
  
 **Säilytä ohjausobjektien määrä vähimmäismäärässä**  
 Komentopalkin tai lomakkeen valintanauhassa arvioi, mitkä ohjausobjektit ovat tarpeen ja piilota kaikki ne, joita et tarvitse. Jokainen ohjausobjekti, joka on näkyvissä, kasvattaa resursseja, jotka pitää ladata selaimeen.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Luo ja suunnittele lomakkeita](create-design-forms.md)    
    
 
