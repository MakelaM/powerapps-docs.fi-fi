---
title: 'Opetusohjelma, jossa kerrotaan PowerApps-sovelluksen kanssa osia sisältävän mukautetun entiteetin luomisesta | Microsoft Docs'
description: 'Opetusohjelma, joka sisältää vaiheittaiset ohjeet PowerApps-sovelluksessa käytettävän entiteetin luomisesta ja määrittämisestä.'
author: Mattp123
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: tutorial
ms.date: 06/22/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-a-custom-entity-that-has-components-in-powerapps"></a>Opetusohjelma: Osia sisältävän mukautetun entiteetin luominen PowerAppsissa

PowerApps-sovelluksen avulla voit mukauttaa mallipohjaista sovellusta niin, että se vastaa organisaatiosi toimialaa, terminologian yhtenäistämistä ja yksilöllisiä liiketoimintaprosesseja. PowerApps-sovelluksen kehitystyö sisältää valmiiden vakioentiteettien lisäämisen tai mukautettujen entiteettien luomisen. Entiteetti määrittää tiedot, joita tietueiden lomakkeessa seurataan. Ne ovat yleensä ominaisuuksia, kuten yrityksen nimi, sijainti, tuotteet, sähköposti ja puhelin. 

Tässä opetusohjelmassa luodaan entiteetti ja lisätään tärkeimmät osat, kuten kentät, suhteet, näkymät ja lomakkeet, ja mukautetaan niitä. Saat lisätietoja seuraavista toiminnoista:

- Mukautetun entiteetin luominen
- Mukautettujen kenttien lisääminen entiteettiin
- Entiteettisuhteen lisääminen
- Näkymän mukauttaminen 
- Lomakkeen mukauttaminen

Opetusohjelma seuraa yritystä, Contosoa, joka tarjoaa trimmauspalvelua koirille ja kissoille. Contoso tarvitsee työntekijöiden eri laitteissa toimivan sovelluksen asiakkaiden ja lemmikkien seuraamista varten.

## <a name="prerequisites"></a>Edellytykset

Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen. Jos sinulla ei vielä ole PowerApps-tiliä, valitse **Aloita ilmaiseksi** -linkki sivustossa [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-a-custom-entity"></a>Mukautetun entiteetin luominen

1. Laajenna vasemmanpuoleisessa siirtymisruudussa **Tiedot**-kohta, valitse **Entiteetit** ja valitse sitten **Uusi entiteetti**.
    > [!div class="mx-imgBorder"] 
    > ![uusi kohde](media/create-custom-entity/create-new-entity.png)
2. Anna oikeanpuoleiseen ruutuun seuraavat arvot ja valitse **Seuraava**.
  - **Näyttönimi**: *Lemmikki* 
  - **Kuvaus**: *Mukautettu entiteetti lemmikkieläinten palveluiden seuraamista varten*
3. Valitse **Tallenna entiteetti**.

## <a name="add-and-customize-fields"></a>Kenttien lisääminen ja mukauttaminen
 
1. Valitse entiteettiluettelosta edellisessä osassa luotu **Lemmikki**-entiteetti.
2. Valitse **Kentät**-välilehdessä **Lemmikki**-kenttä.
3. Tee oikeanpuoleisessa ruudussa seuraavat muutokset **Näyttönimi**-kenttään. 
  - Muuta **Näyttönimi**-kohdan arvo **Lemmikki**-arvosta *Lemmikin nimi* -arvoksi
  - Valitse **Haettavissa**.  
  
    > [!div class="mx-imgBorder"] 
    > ![Ensisijaisen kentän muuttaminen](media/create-custom-entity/primary-field.png)
3. Valitse **Valmis**.
4. Valitse **Kentät**-välilehden entiteetin suunnitteluohjelman työkaluriviltä **Lisää kenttä**. Anna tai valitse seuraavat arvot ja asetukset **Kentän ominaisuudet** -ruutuun.
  - **Näyttönimi**. *Laji*
  - **Tietotyyppi** *Asetusjoukko*
  - **Asetusjoukko**. *Uusi asetusjoukko*
5. Asetusjoukon luominen

  a. Valitse **Lisää uusi kohde**. 
  
  b. Korvaa **Uusi asetus** -arvo *Koira*-arvolla. 
   
  c. Valitse **Lisää uusi kohde**. 
    
  d.  Korvaa **Uusi asetus** -arvo *Kissa*-arvolla. 
    
  e. Valitse **Tallenna**. 

  > [!div class="mx-imgBorder"] 
  > ![Uusi asetusjoukko](media/create-custom-entity/optionset-add-items.png)

6. Valitse **Haettavissa** ja valitse sitten **Valmis**.

7. Valitse entiteetin suunnitteluohjelman työkaluriviltä **Lisää kenttä**. Anna tai valitse seuraavat arvot ja asetukset **Kentän ominaisuudet** -ruutuun ja valitse **Valmis**.
  - **Näyttönimi**. *Rotu*
  - **Tietotyyppi** *Teksti*
  - **Haettavissa**. *Kyllä*

8. Valitse entiteetin suunnitteluohjelman työkaluriviltä **Lisää kenttä**. 

9. Anna tai valitse seuraavat arvot ja asetukset **Kentän ominaisuudet** -ruutuun ja valitse **Valmis**. 
  - **Näyttönimi**. *Tapaamisen päivämäärä*
  - **Tietotyyppi** *Päivämäärä ja aika*

10. Valitse **Tallenna entiteetti**.

## <a name="add-a-relationship"></a>Suhteen lisääminen

1. Valitse **Suhteet**-välilehdessä entiteetin suunnitteluohjelman työkaluriviltä **Lisää suhde** ja valitse sitten **Monta yhteen**. 
2. Valitse oikeanpuoleisessa ruudussa **Liittyvät**-luettelosta **Asiakas**.
3. Valitse **Valmis**.
4. Valitse **Tallenna entiteetti**.

  Ota huomioon, että kun lisäät monta yhteen -suhteen, **Asiakas**-kenttä, jonka tietotyyppi on **Haku**, lisätään automaattisesti **Kentät**-välilehden kenttäluetteloon.
  > [!div class="mx-imgBorder"]
  > ![Asiakkaan hakukenttä](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>Näkymän mukauttaminen

1. Valitse **Näkymät**-välilehti ja valitse sitten **Aktiiviset lemmikit** -näkymä. Jos et näe **Aktiiviset lemmikit** -näkymää, valitse **Poista suodatin**.
2. Valitse näkymän suunnitteluohjelmassa **Lisää sarakkeet**. Valitse seuraavat sarakkeet ja valitse sitten **OK**.
  - Asiakas
  - Tapaamisen päivämäärä 
  - Rotu 
  - Laji
3. Valitse **Luotu**-sarake ja valitse sitten **Poista**. Vahvista sarakkeen poisto valitsemalla **OK**.
4. Voit järjestää sarakkeet valitsemalla siirrettävän sarakkeen ja käyttämällä nuolipainikkeita <- ja -> niin kauan, kuin näkymä näyttää tältä.
    > [!div class="mx-imgBorder"] 
    > ![Aktiiviset lemmikit -näkymä](media/create-custom-entity/active-pets-view.png)
5. Valitse näkymän suunnitteluohjelman työkaluriviltä **Tallenna ja sulje**.  

## <a name="model-driven-apps-only-customize-the-main-form"></a>Vain malliin pohjautuvat sovellukset: Mukauta päälomake

Ohita tämä vaihe, jos haluat käyttää Lemmikki-entiteettiä vain kaaviosovelluksessa. 

1. Valitse PowerAppsin vasemmanpuoleisessa siirtymisruudussa **Mallipohjainen**.
2. Laajenna vasemmanpuoleisessa siirtymisruudussa **Tiedot**-kohta ja valitse **Entiteetit**. Valitse sitten **Lemmikki**.
3. Valitse **Lomakkeet**-välilehti ja valitse sitten **päälomaketyypin** vieressä oleva **Tiedot**-kohta ja avaa lomake-editori.
    > [!div class="mx-imgBorder"] 
    > ![Päälomakkeen muokkaaminen](media/create-custom-entity/main-form-edit.png)
4. Vedä ja pudota lomake-editorin **Laji**-, **Rotu**-, **Tapaamisen päivämäärä**- ja **Asiakas**-kentät, jotka sijaitsevat lomakekaavion Yleistä-osan Kenttien hallinta -ruudussa. Lopuksi lomake näyttää tältä.
    > [!div class="mx-imgBorder"] 
    > ![Päälomakkeen kenttien valitseminen](media/create-custom-entity/main-form-edit2.png) 
5. Valitse **Tallenna**.
6. Valitse **Julkaise**.
7. Valitse **Tallenna ja sulje**, kun haluat sulkea lomakkeen suunnitteluohjelman.

## <a name="add-the-custom-entity-to-an-app"></a>Mukautetun entiteetin lisääminen sovellukseen

Nyt entiteettiä voi käyttää kaavion tai mallipohjaisen sovelluksen luomisessa. 

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa oli tietoja hyödyllisen sovelluksen luomisessa käytettävän entiteetin luomisesta. 
- Lisätietoja mallipohjaisen sovelluksen luomisesta on kohdassa [Ensimmäisen mallipohjaisen sovelluksen luominen](../model-driven-apps/build-first-model-driven-app.md).
- Lisätietoja kaaviosovelluksen luomisesta on kohdassa [Sovelluksen luominen alusta alkaen](../canvas-apps/get-started-create-from-blank.md).
