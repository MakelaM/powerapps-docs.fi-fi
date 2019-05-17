---
title: Mallipohjaisen sovelluksen näkymien sarakkeiden valitseminen ja määrittäminen PowerAppsissa | MicrosoftDocs
description: Tietoja sovelluksen näkymien valitsemisesta ja määrittämisestä
keywords: ''
ms.date: 11/27/2018
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 31bfcf18-58c3-491c-91b5-f9b0f5424852
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 25
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="choose-and-configure-columns-in-model-driven-app-views"></a>Mallipohjaisen sovelluksen näkymien sarakkeiden valitseminen ja määrittäminen

<a name="BKMK_ChooseAndConfigureColumns"></a>   

 Suodatusehtojen lisäksi PowerAppsin näkymässä näkyvät sarakkeet ovat erittäin tärkeitä näkymässä annetulle arvolle. Tässä ohjeaiheessa luodaan ja muokataan näkymiä seuraavien tehtävien avulla:  

-   [Näkymäeditorin avaaminen](choose-and-configure-columns.md#open-the-view-editor)  
   
-   [Sarakkeiden lisääminen](choose-and-configure-columns.md#BKMK_AddColumns)  
  
-   [Sarakkeiden poistaminen](choose-and-configure-columns.md#BKMK_RemoveColumns)  
  
-   [Sarakeleveyden muuttaminen](choose-and-configure-columns.md#BKMK_ChangeColumnWidth)  
  
-   [Sarakkeen siirtäminen](choose-and-configure-columns.md#BKMK_MoveAColumns)  
    
  > [!IMPORTANT]
  > Näkymän suunnitteluohjelman uusin versio on tällä hetkellä esiversiotilassa. Joitakin ominaisuuksia, kuten sarakkeen tavoitettavuuden käyttöönottoa ja käytöstäpoistoa sekä sarakkeen lisäämistä, ei vielä tueta. Jos haluat suorittaa näitä tehtäviä, [avaa perinteisen näkymän suunnitteluohjelma](/dynamics365/customer-engagement/customize/create-and-edit-views#open-the-classic-view-designer).
  >  -   [Ota käyttöön tavoitettavuus tai poista se käytöstä sarakkeelle](/dynamics365/customer-engagement/customize/choose-and-configure-columns#BKMK_EnableOrDisablePresence)  
  >
  >  -   [Lisää hakusarakkeita](/dynamics365/customer-engagement/customize/choose-and-configure-columns#BKMK_AddFindColumns) 



### <a name="open-the-view-editor"></a>Näkymäeditorin avaaminen

1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Näkymät**-välilehti. 

    > [!div class="mx-imgBorder"] 
    > ![Näkymät](media/available-views.png)

3. Avaa olemassa oleva näkymä valitsemalla se tai valitsemalla työkaluriviltä **Lisää näkymä**. 

<a name="BKMK_AddColumns"></a>   
### <a name="add-columns"></a>Sarakkeiden lisääminen  
 Voit lisätä nykyisen entiteetin tai jonkin liitetyistä entiteeteistä, joilla on 1:N entiteettisuhde nykyisen entiteetin kanssa.  
  
 Esimerkiksi haluat ehkä näyttää käyttäjän omistamien entiteettien omistajat sarakkeessa. Voit valita nykyisen entiteetin **Omistaja** -kentän omistajan nimen esittämiseksi. Tämä näkyy linkkinä, josta avautuu **Käyttäjä**-tietue henkilölle, joka on omistaja.  
  
 Jos haluat näyttää tietueen omistajan puhelinnumeron, sinun on valittava **omistajakäyttäjä (User)** **tietuetyypin** avattavasta valikosta ja valitse sitten **Ensisijainen puhelin** -kenttä.  
  
#### <a name="add-columns-to-views"></a>Sarakkeiden lisääminen näkymään  
  
1.  Varmista näkymien luomisen ja muokkaamisen yhteydessä, että **Kentät**-paneeli on avoinna. Jos näin ei ole, valitse **Lisää kentät** työkaluriviltä. 

    > [!div class="mx-imgBorder"] 
    > ![Näkymäeditorin sarakkeiden lisääminen](media/fields-drawer-view-designer.png)

2.  Valitse näkymän suunnitteluohjelmaan lisättävät kentät. Tällöin kenttä lisätään sarakkeena näkymän oikealle puolelle.

3.  Valitse **Liittyvät**-välilehti ja katso liittyvät entiteetit ja niiden vastaavat kentät.
  
 Kun lisäät sarakkeita, kasvatat näkymän leveyttä. Jos näkymän leveys ylittää tilan, jolla sivu on näkyvissä, vaakasuorat vierityspalkit sallivat ihmisille piilotettujen sarakkeiden vierittämisen ja näkemisen.  
  
> [!TIP]
>  Jos näkymä suodattaa tietyn kentän tiedot siten, että näkyvissä ovat vain ne tietueet, joilla on tietty arvo, älä sisällytä sitä saraketta näkymään. Esimerkiksi jos näkyvissä ovat vain aktiiviset tietueet, älä sisällytä tilasaraketta näkymään. Sen sijaan nimeä näkymä niin, että kaikki näkymässä näkyvät tietueet ovat aktiivisia.  
  
> [!NOTE]
>  Kun lisäät sarakkeita päivitettyjen kohteiden valintanäkymille, vain kolme ensimmäistä saraketta näytetään.  
  
<a name="BKMK_RemoveColumns"></a>   
### <a name="remove-columns"></a>Sarakkeiden poistaminen  
  
1.  Valitse poistettavan sarakkeen otsikko.  
  
2.  Valitse luetteloruudusta **Poista**.  
  
<a name="BKMK_ChangeColumnWidth"></a>   
### <a name="change-column-width"></a>Sarakeleveyden muuttaminen  
  
1.  Vie kohdistin sarakkeiden väliselle alueelle näkymässä.  
  
2.  Näkyviin tulee viiva ja osoittimesta tulee kaksisuuntainen nuoli.  
  
3.  Vedä saraketta niin, että sen leveys on sopiva.  
  
<a name="BKMK_MoveAColumns"></a>   
### <a name="move-a-column"></a>Sarakkeen siirtäminen  
  
Napsauta sarakkeen otsikkoa ja vedä se oikeaan paikkaan.
  
> [!TIP]
>   Voit myös valita siirrettävän otsikon ja valita avattavasta luettelosta **Siirrä oikealle** tai **Siirrä vasemmalle**.  


  
## <a name="next-steps"></a>Seuraavat vaiheet
[Näkymien luominen tai muokkaaminen](create-edit-views.md)
