---
title: Opetusohjelma sellaisen mukautetun entiteetin luomiseen, jossa on osia PowerAppsin kanssa| Microsoft Docs
description: Opetusohjelma, joka sisältää vaiheittaiset ohjeet entiteetin luomiseen ja määrittämiseen PowerApps-sovelluksessa käyttämistä varten.
documentationcenter: na
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: dcd7acb9b6a7556e30cfa1aa46385024dcd0bcb5
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="tutorial-create-a-custom-entity-that-has-components-in-powerapps"></a>Opetusohjelma: Luo osia sisältävä mukautettu entiteetti PowerAppsissa

[!INCLUDE [powerapps](../../includes/powerapps.md)]in avulla räätälöit sovelluksesi sopimaan läheisesti yhteen organisaatiosi alan, tuotenimikkeistön ja yksilöllisten liiketoimintaprosessien kanssa. [!INCLUDE [powerapps](../../includes/powerapps.md)]-sovelluskehitykseen kuuluu valmiiden, vakiomallisten entiteettien lisäys tai mukautettujen entiteettien luonti. Entiteetti määrittää tiedot, joita haluat seurata sellaisten tietueiden muodossa, jotka yleensä sisältävät ominaisuuksia, kuten yrityksen nimi, sijainti, tuotteet, sähköposti ja puhelinnumero. 

Tässä opetusohjelmassa luot entiteetin ja lisäät tai mukautat tärkeimpiä osia, kuten kenttiä, suhteita, näkymiä ja lomakkeita. Ohjeet:

- Luo mukautettu kohde
- Lisää mukautettuja kenttiä entiteettiin
- Lisää entiteettisuhde
- Mukauta näkymää 
- Mukauta lomaketta

Opetusohjelman esimerkkitapauksena on lemmikkieläinten hoitoyritys Contoso, joka tarjoaa kissojen ja koirien trimmauspalveluja. Contoso tarvitsee asiakkaiden ja lemmikkien seurantaan sovelluksen, jota työntekijät voivat käyttää useissa eri laitteissa.

## <a name="prerequisites"></a>Edellytykset

Kirjaudu sisään [PowerAppsiin](https://powerapps.microsoft.com/). Jos sinulla ei ole vielä [!INCLUDE [powerapps](../../includes/powerapps.md)]tiliä, valitse **Aloita maksutta** -linkki [powerapps.com](https://web.powerapps.com)issa.

## <a name="create-a-custom-entity"></a>Luo mukautettu kohde

1. Laajenna vasemmassa siirtymisruudussa **Tiedot**, valitse **Entiteetit** ja valitse sitten **Uusi entiteetti**.
    ![Uusi entiteetti](media/create-custom-entity/create-new-entity.png)
2. Lisää seuraavat arvot oikeanpuoleiseen ruutuun ja valitse sitten **Seuraava**.
  - **Näyttönimi**: *Lemmikki* 
  - **Kuvaus**: *mukautettu entiteetti lemmikkieläinpalvelujen seuraamiseen*
3. Valitse **Tallenna entiteetti**.

## <a name="add-and-customize-fields"></a>Lisää ja mukauta kenttiä
 
1. Valitse **Kentät**-välilehdestä **Ensisijainen nimi** -kenttä.
2. Tee seuraavat muutokset **Ensisijainen nimi** -kenttään oikeanpuoleisessa ruudussa: 
  - Muuta **Näyttönimi** nimestä **Ensisijainen nimi** nimeksi *Lemmikin nimi*
  - Valitse **Haettavissa**  
  
    ![Vaihda ensisijaista kenttää](media/create-custom-entity/primary-field.png)
3. Valitse **Valmis**.
4. Valitse entiteetin suunnittelutoiminnon työkalurivin **Kentät**-välilehdestä **Lisää**-kenttä. Kirjoita tai valitse seuraavat arvot ja valinnat **Kentän ominaisuudet** -ruudussa.
  - **Näyttönimi**. *Lajit*
  - **Tietotyyppi**. *Asetusjoukko*
  - **Asetusjoukko**. *Uusi asetusjoukko*
5. Luo asetusjoukko

  a. Valitse **Lisää uusi kohde**. 
  
  b. Vaihda **Uusi vaihtoehto** -kohtaan *Koira*. 
   
  c. Valitse **Lisää uusi kohde**. 
    
  d.  Vaihda **Uusi vaihtoehto** -kohtaan *Kissa*. 
    
  e. Valitse **Tallenna**. 

  ![Uusi asetusjoukko](media/create-custom-entity/optionset-add-items.png)

6. Valitse **Haettavissa** ja sitten **Valmis**.

7. Valitse **Lisää kenttä** entiteetin suunnittelutoiminnon työkaluriviltä. Kirjoita tai valitse seuraavat arvot **Kentän ominaisuudet** -ruudussa ja valitse sitten **Valmis**.
  - **Näyttönimi**. *Rotu*
  - **Tietotyyppi**. *Teksti*
  - **Haettavissa**. *Kyllä*

8. Valitse **Lisää kenttä** entiteetin suunnittelutoiminnon työkaluriviltä. 

9. Kirjoita tai valitse seuraavat arvot **Kentän ominaisuudet** -ruudussa ja valitse sitten **Valmis**. 
  - **Näyttönimi**. *Tapaamisen päivämäärä*
  - **Tietotyyppi**. *Päivämäärä ja aika*

10. Valitse **Tallenna entiteetti**.

## <a name="add-a-relationship"></a>Määritä suhde

1. Valitse **Suhde**-välilehti ja valitse entiteetin suunnittelutyökalun työkaluriviltä **Lisää suhde** ja sitten **Monta yhteen**. 
2. Valitse oikeanpuoleisen ruudun **Liittyvät**-luettelossa **Tili**.
3. Valitse **Valmis**.
4. Valitse **Tallenna entiteetti**.

Huomaa, että kun lisäät monta yhteen -suhteen, **Tili**-kenttä, jossa on tietotyyppi **Lookup**, lisätään automaattisesti kenttien luetteloon **Kentät**-välilehdessä. ![Asiakkaan hakukenttä](media/create-custom-entity/account-lookup-field.png)

## <a name="customize-a-view"></a>Mukauta näkymää

1. Valitse **Näkymät**-välilehti ja sitten **Aktiiviset lemmikit** -näkymä. Jos et näe **Aktiiviset lemmikit** -näkymää, valitse **Poista suodatin**.
2. Valitse näkymän suunnittelutyökalusta **Lisää sarakkeita**, valitse seuraavat sarakkeet ja valitse sitten **OK**.
  - Tili
  - Tapaamisen päivämäärä 
  - Rotu 
  - Lajit
3. Valitse **Luotu**-sarakkeesta **Poista** ja vahvista sarakkeen poistaminen valitsemalla sitten **OK**.
4. Järjestä sarakkeita valitsemalla siirrettävä sarake ja käytä sitten nuolinäppäimiä <- ja ->, kunnes näkymä näyttää tältä.
    ![Aktiivisten lemmikkien näkymä](media/create-custom-entity/active-pets-view.png)
5. Valitse näkymän suunnittelutyökalun työkaluriviltä **Tallenna ja sulje**.  

## <a name="model-driven-apps-only-customize-the-main-form"></a>Vain mallipohjaiset sovellukset: päälomakkeen mukauttaminen

Ohita tämä vaihe, jos haluat käyttää Lemmikki-entiteettiä vain pohjaan perustuvassa sovelluksessa. 

1. Valitse [!INCLUDE [powerapps](../../includes/powerapps.md)]in vasemmassa siirtymisruudussa **Mallipohjainen**.
2. Laajenna vasemmassa siirtymisruudussa **Tiedot**, valitse **Entiteetit** ja valitse sitten **Lemmikki**.
3. Avaa lomake-editori valitsemalla **Lomakkeet**-välilehti ja sitten **Pääasiallinen**-lomaketyypin vierestä **Tiedot**.
    ![Muokkaa päälomaketta](media/create-custom-entity/main-form-edit.png)
4. Vedä ja pudota lomake-editorissa Kenttien hallinta -ruudussa kenttiä **Lajit**, **Rotu**, **Tapaamisen päivämäärä** ja **Tili** lomakepohjan Yleiset-osioon, kunnes lomake näyttää tältä.
    ![Valitse kenttiä päälomakkeeseen](media/create-custom-entity/main-form-edit2.png) 
5. Valitse **Tallenna**.
6. Valitse **Julkaise**.
7. Sulje lomakkeen suunnittelutyökalu valitsemalla **Tallenna ja sulje**.

## <a name="add-the-custom-entity-to-an-app"></a>Lisää mukautettu entiteetti sovellukseen

Entiteetti on nyt valmis käytettäväksi joko pohjaan tai malliin perustuvan sovelluksen luomiseen. 

## <a name="next-steps"></a>Seuraavat vaiheet

Tässä opetusohjelmassa opit luomaan entiteetin, jonka avulla voidaan luoda hyödyllisiä sovelluksia. 
- Lisätietoja mallipohjaisen sovelluksen luomisesta on artikkelissa [Luo ensimmäinen mallipohjainen sovelluksesi](../model-driven-apps/build-first-model-driven-app.md).
- Lisätietoja pohjaan perustuvan sovelluksen luomisesta on artikkelissa [Sovelluksen luominen alusta alkaen](../canvas-apps/get-started-create-from-blank.md).
