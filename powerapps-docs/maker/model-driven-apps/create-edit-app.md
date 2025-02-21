---
title: Mallipohjaisen sovelluksen luominen tai muokkaaminen sovellusten suunnitteluohjelmalla PowerAppsissa | MicrosoftDocs
description: Tietoja sovellusten luomisesta tai muokkaamisesta sovellusten suunnitteluohjelmalla
keywords: ''
ms.date: 02/05/2019
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 2a44229e-44f0-4c4e-ba21-a476210d0a12
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 19
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-model-driven-app-by-using-the-app-designer"></a>Mallipohjaisen sovelluksen luominen sovellusten suunnitteluohjelmalla

Tässä ohjeaiheessa on perustietoja mallipohjaisen sovelluksen luomisesta ja muokkaamisesta ruutuihin perustuvan sovellusten suunnitteluohjelman avulla.

## <a name="prerequisites"></a>Edellytykset
Tarkista seuraavat edellytykset, ennen kuin alat luoda sovellusta:
- PowerApps-ympäristö. Lisätietoja: [Ympäristön luominen](https://docs.microsoft.com/powerapps/administrator/create-environment)
- Järjestelmänvalvojan tai järjestelmän mukauttajan käyttöoikeusrooli. Lisätietoja: [Tietoja ennalta määritetyistä käyttöoikeusrooleista](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app#about-predefined-security-roles)
 
<a name="createApp"></a>   
## <a name="create-an-app"></a>Sovelluksen luominen  

1.  Valitse [PowerAppsin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) **aloitussivulla** mallipohjaisen sovelluksen **Mallipohjainen sovellus tyhjästä** -asetus.  

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2. Syötä **Luo uusi sovellus** -sivulla seuraavat tiedot: 

    - **Nimi**: Anna sovelluksen nimi.  
  
    - **Yksilöllinen nimi**: Yksilöllinen nimi annetaan automaattisesti määrittämäsi sovelluksen nimen perusteella. Sille annetaan julkaisijan etuliite. Voit muuttaa sitä yksilöllisen nimen osaa, joka on muokattavissa. Yksilöllisessä nimessä voi olla vain englanninkielisiä merkkejä ja numeroita.  
  
        > [!NOTE]
        >  Julkaisijan etuliite on teksti, joka lisätään tämän julkaisijan ratkaisulle luotaviin entiteetteihin tai kenttiin.   
  
    - **Kuvaus**: Kirjoita lyhyt kuvaus sovelluksesta ja sen toiminnoista.  
  
    - **Kuvake**: **Käytä oletussovellusta** -pikkukuvan valintaruutu on valittuna oletusarvoisesti. Voit valita toisen WWW-resurssin sovelluksen kuvakkeeksi tyhjentämällä valintaruudun ja valitsemalla sitten kuvakkeen avattavasta luettelosta. Tämä kuvake näytetään sovelluksen esikatseluruudussa.  
  
    - **Aiemman ratkaisun avulla voit luoda sovelluksen**: valitsemalla tämän voit luoda sovelluksen asennettujen ratkaisujen luettelosta. Kun olet valinnut tämän vaihtoehdon **valmis** siirtyy **seuraava** otsikossa. Jos valitset **seuraava**, **Luo sovellus aiemmasta ratkaisusta** -sivu avautuu. Valitse **Valitse ratkaisu** -pudotusvalikosta ratkaisu, josta haluat luoda sovelluksen. Jos kaikkia sivustokarttoja voi käyttää valitulle ratkaisulle, **Valitse sivustokartta** avattava luettelo tulee näkyviin. Valitse sivustokartta ja valitse sitten **valmis**.

      > [!NOTE]
      > Valitsemalla **oletusratkaisu** lisättäessä sivustokarttaa, komponentit, jotka on liitetty kyseiseen sivustokarttaan lisätään automaattisesti sovellukseen.  

      ![Aiemman ratkaisun avulla voit luoda sovellussivun](media/use-existing-solution-to-create-the-app.png "Aiemman ratkaisun avulla voit luoda sovellussivun") 

    - **Valitse tervetulosivu**: Tällä vaihtoehdolla voit valita organisaatiosi käytettävissä olevista verkkoresursseista. Luotavilla aloitussivuilla voi olla hyödyllisiä tietoja käyttäjille, kuten videolinkkejä, päivitysohjeita tai aloitustietoja. Aloitussivu avautuu, kun sovellus avataan. Käyttäjät voivat valita aloitussivulla **Älä näytä tätä Tervetuloa-ruutua seuraavalla kerralla**, aloitussivu poistetaan käytöstä eikä se avaudu, kun sovellus käynnistyy seuraavan kerran. Huomaa, että **Älä näytä tätä Tervetuloa-ruutua seuraavalla kerralla** -asetus on käyttäjätason asetus, jota järjestelmänvalvojat tai sovelluskehittäjät eivät voi hallita. Lisätietoja verkkoresurssin, kuten aloitussivuna käytettävän HTML-tiedoston, luonnista on kohdassa [Verkkosovelluksen laajentaminen luomalla ja muokkaamalla verkkoresursseja](create-edit-web-resources.md).  
      
    Voit muokata sovelluksen ominaisuuksia myöhemmin siirtymällä sovelluksen suunnitteluohjelman **Ominaisuudet**-välilehteen. Lisätietoja: [Sovelluksen ominaisuuksien hallinta](manage-app-properties.md)  
  
     > [!NOTE]
     >  Et voi muuttaa yksilöllistä nimeä ja sovelluksen URL-jälkiliitettä **Ominaisuudet**-välilehdessä.  
  
3. Valitse **Valmis** tai&mdash;jos olet valinnut **Sovelluksen luonti aiemmin luodun ratkaisun avulla**&mdash;valitse **seuraava**, jotta voit valita käytettävissä olevista ratkaisuista, joiden tuonti onnistui organisaatioon.  
  
    Luodaan uusi sovellus, joka on luonnostilassa. Uuden sovelluksen sovelluksen suunnitteluohjelman kaavio on näkyvissä. Siellä voit lisätä osia, kuten entiteettejä, näkymiä ja koontinäyttöjä, joiden avulla voit tehdä sovelluksestasi hyödyllisen. Lisätiedot: [Sovelluksen osien lisääminen tai muokkaaminen](add-edit-app-components.md)  
   
<a name="editApp"></a>   
## <a name="edit-an-app"></a>Sovelluksen muokkaaminen  
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

> [!IMPORTANT]
> Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2. Valitse vasemmanpuoleisessa siirtymisruudussa **Sovellukset** ja valitse sitten mallipohjainen. Valitse lopuksi työkaluriviltä **Muokkaa**.   

3. Lisää tai muokkaa osia sovelluksen suunnitteluohjelmassa tarvittaessa. Lisätiedot: [Sovelluksen osien lisääminen tai muokkaaminen](add-edit-app-components.md)  
 
  
### <a name="next-steps"></a>Seuraavat vaiheet  
 [Sovelluksen osien lisääminen tai muokkaaminen](add-edit-app-components.md)   


