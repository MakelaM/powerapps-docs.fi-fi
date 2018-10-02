---
title: Kentän lisääminen mallipohjaisen sovelluksen lomakkeeseen mallipohjaisen sovelluksen lomakkeeseen PowerAppsissa | MicrosoftDocs
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
ms.assetid: 29499887-6e7b-44a1-86a7-eaad33f3075d
caps.latest.revision: 30
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-a-field-to-a-model-driven-app-form"></a>Kentän lisääminen mallipohjaisen sovelluksen lomakkeeseen 

Jos vakioentiteetin PowerApps-lomake ei vastaa organisaation liiketoimintavaatimuksia, voit mukauttaa lomaketta aiemmin luotuja kenttiä muuttamalla tai lisäämällä uusia kenttiä. Saattaa olla helpompaa muokata aiemmin luotuja kenttiä lomakkeeseen, joskus on parempi lisätä kenttä tietyn liiketoimintaskenaarion osoitteeseen.

Tässä ohjeaiheessa lisätään kenttä lomakkeeseen.   
  
1.  Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

    ![Mallipohjainen suunnittelutila](../model-driven-apps/media/model-driven-switch.png)

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.  

3.  Avaa luettelossa **päälomake** muokkaamista varten.  
  
4.  Valitse lomakkeessa osa, johon haluat lisätä kentän, ja kaksoisnapsauta sitten **Kenttien hallinta**-ruudussa kenttää, jonka haluat lisätä lomakkeeseen.  
  
    > [!TIP]
    >  Kun lisäät asetusjoukko-kentän lomakkeeseen, asetusjoukon arvot sisältävä avattava luettelo voi näyttää vain kaksi arvoa. Käyttäjä saa näkyviin useita arvoja vierittämällä. Jos haluat näyttää käyttäjille useamman kuin kaksi arvoa ilman vierittämättä, lisää vähintään yksi **Tyhjä väli** -ohjausobjektit asetusjoukkokentän alapuolelle lomakkeeseen. Kunkin **Tyhjä väli**-ohjausobjektin avulla voidaan lisätä yksi asetusjoukon arvo. Esimerkiksi jos haluat näyttää neljä arvoja avattavasta luettelosta vierittämättä, lisää kaksi **Tyhjä väli** -ohjausobjektia lomakkeeseen asetusjoukkokentän alapuolelle.  
  
5.  Esikatsele päälomakkeen ulkoasua ja tapahtumien suorittamista:  
  
    1.  Valitse **Etusivu**-välilehdessä **Esikatsele** ja valitse sitten **Luo lomake**, **Päivitä lomake** tai **Vain luku -lomake**.  
  
    2.  Voit sulkea esikatselulomakkeen valitsemalla **Sulje**.  
  
    3.  Kun lomake on avoinna, voit julkaista muokattavan lomakkeen mukautukset valitsemalla **Julkaise**.  
  
6.  Kun lomakkeen muokkaus on valmis, valitse **Tallenna ja sulje**.  
  
7. Jos haluat julkaista kaikkien julkaisemattomien osien mukautukset yhtä aikaa, valitse **Tiedosto** ja valitse sitten **Julkaise kaikki mukautukset**.  
  
> [!NOTE]
>  Mukautusten julkaiseminen saattaa häiritä järjestelmän normaalikäyttöä. Suosittelemme, että julkaiset sellaisena ajankohtana, kun tästä on vähiten häiriötä käyttäjille.  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 
 [Luo ja suunnittele lomakkeita](create-design-forms.md)
