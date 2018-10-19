---
title: Koontinäyttöön sisältyvän mallipohjaisen sovelluksen kaavion tai luettelon ominaisuuksien määrittäminen PowerAppsissa | MicrosoftDocs
description: Koontinäyttöön sisältyvän kaavion tai luettelon ominaisuuksien määrittäminen
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 50fb2ab0-5c1a-4a5e-8ebc-5603fecc4da0
caps.latest.revision: 26
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-properties-for-a-model-driven-app-chart-or-list-included-in-a-dashboard"></a>Koontinäyttöön sisältyvän mallipohjaisen sovelluksen kaavion tai luettelon ominaisuuksien määrittäminen

Voit muokata kaaviota tai luettelo-osaa koontinäytön suunnitteluohjelmassa, kun valitset haluamasi kaavion tai luettelon ja valitset sitten koontinäytön suunnitteluohjelman työkaluriviltä Muokkaa osaa -kohdan.   
  > [!div class="mx-imgBorder"] 
  > ![Koontinäytön suunnitteluohjelman kaavion osan muokkaaminen](media/dashboard-chart-select.png)

**Määritä ominaisuudet** -valintaikkuna avautuu.

  > [!div class="mx-imgBorder"] 
  > ![Kaaviojoukon ominaisuudet.](media/set-properties-chart.png)  
 
Voit määrittää seuraavat kaavion ominaisuudet **Määritä ominaisuudet** -valintaikkunassa:  
  
- **Nimi**. Kaavion yksilöllinen nimi. Järjestelmä ehdottaa arvoa, mutta voit vaihtaa sen.  
  
- **Otsikko** Kaavion yläpuolella näkyvä otsikko.  
  
- **Näytä otsikko koontinäytössä** Valitse tämä valintaruutu tai poista sen valinta sen mukaan, haluatko näyttää vai piilottaa kaavion otsikon.  
  
- **Entiteetti**. Valitse entiteetti (tietuetyyppi), johon kaavio perustuu. Tämä asetus määrittää arvot, joita voi käyttää Oletusnäkymä- ja Oletuskaavio-ominaisuuksissa.  
  
- **Oletusnäkymä**. Valitse näkymä, johon kaavion tiedot haetaan.  
  
- **Oletuskaavio**. Valitse oletuskaavio, jonka haluat näytettävän koontinäytön ensimmäisellä avauskerralla. Entiteetti-ominaisuudelle määritetty arvo määrittää käytettävissä olevat arvot. Tätä ominaisuutta käytetään yhdessä Näytä kaavion valinta -ominaisuuden kanssa. Käyttäjä voi vaihtaa kaaviotyyppiä, jos **Näytä kaavion valinta** -asetus on käytössä, mutta kaavio palautuu Oletuskaavio-asetuksen mukaiseksi, kun koontinäyttö avataan seuraavan kerran.  
  
- **Näytä vain kaavio**. Valitse tämä valintaruutu, jos haluat, että vain kaavio näkyy. Poista tämän valintaruudun valinta, jos haluat näyttää kaavion ja siihen liittyvät tiedot.  
  
- **Näytä kaavion valinta**. Kun valitset tämän valintaruudun, käyttäjät voivat kaavion tyyppiä (sarake, palkki, ympyrä jne.) koontinäytössä. Jos käyttäjä muuttaa kaavion tyyppiä, asetuksia ei tallenneta. Kaaviotyyppi palautuu oletuskaavioasetukseen, kun koontinäyttö suljetaan.  
  
Voit määrittää seuraavat luettelon ominaisuudet **Määritä ominaisuudet** -valintaikkunassa:  
  
- **Nimi**. Luettelon yksilöllinen nimi. Järjestelmä ehdottaa arvoa, mutta voit vaihtaa sen.  
  
- **Otsikko** Luettelon yläpuolella näkyvä otsikko.  
  
- **Näytä otsikko koontinäytössä** Valitse tämä valintaruutu tai poista sen valinta sen mukaan, haluatko näyttää vai piilottaa luettelon otsikon.  
  
- **Entiteetti**. Valitse entiteetti (tietuetyyppi), johon luettelo perustuu. Tämä asetus määrittää arvot, joita voi käyttää Oletusnäkymä-ominaisuudessa.  
  
- **Oletusnäkymä**. Valitse näkymä, johon luettelon tiedot haetaan. Käyttäjä voi muuttaa näkymää, mutta luettelo palautuu Oletusnäkymä-asetuksen mukaiseksi, kun koontinäyttö avataan seuraavan kerran.  
  
- **Näytä hakukenttä**. Valitse tämä valintaruutu, jos haluat, että hakukenttä näkyy luettelon yläreunassa. Jos hakukenttä on otettu mukaan, sinä ja muut käyttäjät voitte etsiä luettelosta tietueita suorituksen aikana.  
  
- **Näytä indeksi**. Valitse tämä valintaruutu, jos haluat, että A–Ö-suodattimet näkyvät luettelon alareunassa. Kun A–Ö-suodattimet näkyvät, sinä ja muut käyttäjät voitte siirtyä kyseisellä kirjaimella alkaviin tietueisiin valitsemalla kirjaimen.  
  
- **Näkymän valitsin**. Valittavana on seuraavat arvot:  
  
    - **Ei käytössä**. Näkymän valitsinta ei näytetä. Näkymiä ei voi vaihtaa suorituksen aikana.  
  
    - **Näytä kaikki näkymät**. Sisältää täydellisen luettelon Entiteetti-ominaisuudessa määritettyyn arvoon liitetyistä näkymistä.  
  
    - **Näytä valitut näkymät**. Valitsemalla tämän asetuksen voit rajoittaa suorituksen aikana käytettävissä olevien näkymien luetteloa. Voit valita näytettäväksi tietyt näkymät painamalla pitkään Ctrl-näppäintä ja napauttamalla tai napsauttamalla kutakin näkymää, jonka haluat luetteloon.  
 
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Koontinäyttöjen luominen tai mukauttaminen](create-edit-dashboards.md)
