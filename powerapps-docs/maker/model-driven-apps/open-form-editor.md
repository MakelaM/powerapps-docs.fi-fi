---
title: Mallipohjaisen sovelluksen lomake-editorin avaaminen PowerAppsissa | MicrosoftDocs
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
ms.assetid: 8478a07a-c697-4784-874b-36958eb4f95d
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="open-the-model-driven-app-form-editor"></a>Mallipohjaisen sovelluksen lomake-editorin avaaminen 
Lomake-editorissa suunnitellaan lomakkeet pudottamalla lomake-editorin kaavioon osat, esimerkiksi osia, välilehtiä, kenttiä ja ohjausobjekteja. Tässä ohjeaiheessa on tietoja useista lomake-editorin käyttötavoista.
 
Jos haluat luoda lomaketta muokattaessa ratkaisun osia, kuten verkkoresursseja, osien nimet käyttävät oletusratkaisussa ratkaisujulkaisijan mukautuksen etuliitettä ja kyseiset osat sisältyvät vain oletusratkaisuun. Jos haluat uusien ratkaisun osien sisältyvän tiettyyn ei-hallittuun ratkaisuun, avaa lomake-editori kyseisessä ei-hallitussa ratkaisussa.  

## <a name="access-the-form-editor-from-the-powerapps-site"></a>Lomake-editorin käyttäminen PowerApps-sivustossa

1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/) -sovellukseen. 

2. Valitse **Mallipohjainen** > **Tiedot** > **Entiteetit** > ja valitse sitten haluamasi entiteetti, esimerkiksi asiakasentiteetti. 

3. Valitse **Lomakkeet**-välilehti ja avaa sitten haluamasi lomake, esimerkiksi **Asiakas**-päälomake.

## <a name="access-the-form-editor-from-solution-explorer"></a>Lomake-editorin käyttäminen ratkaisunhallinnassa
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).
  
2.  Laajenna ensin **Osat**-kohdassa **Entiteetit**, sitten haluamasi entiteetti ja valitse **Lomakkeet**.  
  
3.  Napsauta muokattavaa lomaketta lomakeluettelossa.  
  

## <a name="access-the-form-editor-through-the-command-bar-within-a-model-driven-app"></a>Lomake-editorin käyttäminen mallipohjaisen sovelluksen komentopalkissa 
  
1.  Avaa tietue.  
  
2.  Jos entiteetillä on useita päälomakkeita, varmista, että kyse on muokattavasta lomakkeesta. Jos näin ei ole, valitse muokattava lomake lomakevalitsimella.  
  
3.  Valitse **Lisää komentoja** -painike ![Tapahtuma-aktiviteetin Lisää komentoja -painike](media/more-commands.gif "Tapahtuma-aktiviteetin Lisää komentoja -painike").  
  
4.  Valitse **Lomake-editori**.  

## <a name="access-the-form-editor-from-within-dynamics-365-customer-engagement"></a>Lomake-editorin käyttäminen Dynamics 365 Customer Engagement -sovelluksessa
  
 Entiteetti määrittää, käytetäänkö lomake-editoria Dynamics 365 Customer Engagement -sovelluksessa komentopalkista vai valintanauhasta. Kumpikin menetelmä avaa lomakkeen oletusratkaisussa. 

## <a name="access-the-form-editor-for-an-unmanaged-solution"></a>Ei-hallitun ratkaisun lomake-editorin käyttäminen  
  
1.  Avaa [Ratkaisut](advanced-navigation.md#solutions).  
  
2.  Kaksoisnapsauta käsiteltävää ei-hallittua ratkaisua.  
  
3.  Etsi entiteetti, jonka lomaketta haluat muokata. Jos entiteettiä ei ole, se on lisättävä. Lisätietoja: [Entiteetin lisääminen hallitsemattomaan ratkaisuun](#add-an-entity-to-an-unmanaged-solution) 
  
### <a name="add-an-entity-to-an-unmanaged-solution"></a>Entiteetin lisääminen ei-hallittuun ratkaisuun  
  
1.  Valitse **Entiteetit**-solmu ja napsauta sitten luettelon yläpuolella olevalta työkaluriviltä **Lisää aiemmin luotu**.  
  
2.  Varmista ensin, että **Valitse ratkaisun osat** -valintaikkunan **Osan tyyppi** -valitsimessa on valittu **Entiteetti**, napsauta sitten lisättävä entiteetti ja napsauta lopuksi **OK**.  
  
3.  Jos **Pakollisia osia puuttuu** -valintaikkuna avautuu, voit valita **Ei, älä lisää pakollisia osia**, jos et aio viedä tätä hallitsematonta ratkaisua toiseen ympäristöön. Jos et sisällytä puuttuvia pakollisia osia nyt, voit lisätä ne myöhemmin. Ilmoitus näkyy uudelleen, jos viet ratkaisun myöhemmin.  
  
5.  Laajenna ratkaisunhallinnassa entiteetti, jonka lomaketta haluat muokata, ja valitse **Lomakkeet**.  
  
6.  Kaksoisnapsauta muokattavaa lomaketta lomakeluettelossa.  

## <a name="next-steps"></a>Seuraavat vaiheet

[Luo ja suunnittele lomakkeita](create-design-forms.md)
