---
title: Mallipohjaisen sovelluksen tietojen visualisointien mukautettujen ohjausobjektien käyttäminen PowerAppsissa | MicrosoftDocs
description: Opettele käyttämään kenttien mukautettuja ohjausobjekteja
ms.custom: ''
ms.date: 06/07/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 0d6064cd-4d38-4fc2-a564-735cb453a4b2
caps.latest.revision: 8
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-custom-controls-for-model-driven-app-data-visualizations"></a>Mallipohjaisen sovelluksen tietojen visualisointien mukautettujen ohjausobjektien käyttäminen

Tässä ohjeaiheessa on tietoja kentän mukautetun ohjausobjektin määrittämisestä. 

Mukautettujen ohjausobjektien avulla voi muuntaa visualisoinneiksi sovelluksen käyttöliittymäosia, kuten kenttiä ja perinteisesti tekstiä sisältäviä näkymiä. Mukautettuja ohjausobjekteja voidaan määrittää kentille, lomakkeille, koontinäytöille, näkymille ja ruudukoille. Esimerkiksi liukusäädinohjausobjekti voidaan määrittää useille kentille.

   > [!div class="mx-imgBorder"] 
   > ![Mukautettu liukusäädinohjausobjekti](media/slider-control.PNG "Kentän liukusäädinohjausobjekti")

Muokattavan ruudukon ohjausobjekti voidaan määrittää myös näkymälle. 

   > [!div class="mx-imgBorder"] 
   > ![Muokattavan ruudukon ohjausobjekti](media/editable-grid-example.png)

Voit määrittää yhden mukautetun ohjausobjektityypin näkymään WWW-selainasiakasohjelmassa samaan aikaan, kun toinen mukautettu ohjausobjekti näkyy Dynamics 365:n puhelin- ja tablettimobiilisovelluksissa. Voit esimerkiksi käyttää lukusyöte mukautettua ohjausobjektia kentässä verkkoselainasiakasohjelmissa ja puhelinsovelluksen liukusäätimen ohjausobjektia. Kun mukautukset on julkaistu, käyttäjät voivat käsitellä täysin ohjausobjektia muuttaakseen arvoa, kuten siirtämällä ohjausobjektia käytettäessä lineaarista mukautettua liukusäädinohjausobjektia. Muutokset tallennetaan automaattisesti, kun lomake suljetaan, kuten silloinkin, kun käyttäjä muuttaa perinteisistä kenttää lomakkeesta.  
  
## <a name="use-a-custom-control-to-add-visualizations-to-a-field"></a>Mukautetun ohjausobjektin avulla voit lisätä visualisointeja kenttään  
 Seuraavien vaiheiden mukaisesti muuttuu oletusotsikko ja **budjettisumma**-kentän tekstiruutukenttä liukusäädinohjausobjektiksi mahdollisuusentiteetissä. Samanlaisten vaiheiden mukaisesti voit korvata mukautetun ohjausobjektin aiemmin luodun kentän tai määrittää mukautetun kentän mukautetun ohjausobjektin.  
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

     

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.  
  
2.  Avaa mahdollisuusentiteetin lomake, esimerkiksi **päälomake**. 
  
3.  Kaksoisnapsauta avattavaa kenttää, johon haluat lisätä mukautetun ohjausobjektin lomake-editorissa, kuten **budjettisumma**-kentän ensisijaisessa mahdollisuuslomakkeessa. Vaihtoehtoisesti voit luoda mukautetun kentän. 
  
4.  Valitse **kenttäominaisuudet**-sivulla **ohjausobjektit**-välilehti ja valitse sitten **Lisää ohjausobjekti**.  
  
5.  Valitse Lisää ohjausobjekti -sivulta ohjausobjekti, jonka haluat esimerkiksi **lineaarinen liukusäädin** ohjausobjekti, joka näkyy tässä, ja valitse sitten **Lisää**.  

   > [!div class="mx-imgBorder"] 
   > ![Lisää lineaarinen liukusäädinohjausobjekti](media/add-slider.PNG "Lisää lineaarinen liukusäädinohjausobjekti")  
  
6.  Valitse asiakasohjelma, jossa haluat ohjausobjektin näkyvän.  
  
    - **Internet**. Ottaaksesi käyttöön ohjausobjektin kaikissa verkkoselaimissa valitse **Internet** ohjausobjektin vierestä. Huomaa, että **Internet**-asetus sisältää ohjausobjektin hahmontamisen PC-tietokoneista ja MAC-koneissa ja mobiililaitteiden selaimissa.  
  
    - **Puhelin**. Voit ottaa mukautetun ohjausobjektin käyttöön puhelimissa, joissa on käytössä Dynamics 365 for phones, valitsemalla ohjausobjektin vieressä olevan **Puhelin**-asetuksen.  
  
    - **taulutietokone**. Voit ottaa mukautetun ohjausobjektin käyttöön tablettilaitteissa, joissa on käytössä Dynamics 365 for tablets, valitsemalla ohjausobjektin vieressä olevan **Tabletti**-asetuksen.  
  
   > [!div class="mx-imgBorder"] 
   > ![Valitse asiakassovellukset tarkastellaksesi mukautettua ohjausobjektia](media/choose-client.png "Valitse asiakassovellukset tarkastellaksesi mukautettua ohjausobjektia")  
  
7.  Valitse ![ohjausobjektin ominaisuuden muokkauskuvake](media/ccf-pencil-icon.png "ohjausobjektin ominaisuuden muokkauskuvake") -kynäkuvaketta **pienin**, **suurin**, ja **vaihe** joukkojen vieressä aseta jäljempänä kuvattu ominaisuusasetus ja valitse sitten **OK**.  
  
   > [!div class="mx-imgBorder"] 
   > ![Lisää mukautetut ohjausobjektiominaisuudet](media/ccf-add-properties.png "Lisää mukautetut ohjausobjektiominaisuudet")
  
   - **Pienin**. Määritä pienin hyväksytty arvo. Voit sitoa staattisen arvon, jonka annat tai sitoa arvon aiemmin luotuihin kenttiin. Tässä esimerkissä **sido staattiseen arvoon** on **valuutta** ja vähimmäisarvo, joka on annettava on *nolla*.  
  
       - **Sido staattiseen arvoon**. Valitse tietotyyppi, kuten kokonaisluku (Whole.None), valuutta, liukuluku (FP) tai desimaali. Kirjoita seuraavaksi luku, joka vastaa kentän hyväksyttyä vähimmäisarvoa.  
  
       - **Sido kentän arvoihin**. Valitse luettelosta kenttä, jota käytetään hyväksyttynä vähimmäisarvona.  
  
   - **Enintään**. Aseta kentän hyväksytty enimmäisarvo. Samalla tavalla kuin pienin arvo voit liittää staattisen arvon, jonka annat tai sitoa arvon aiemmin luotuihin kenttiin kuvatulla tavalla. Tässä esimerkissä **sido staattiseen arvoon** on **valuutta** ja enimmäisarvo, joka on annettava on **1 miljardi**.  
  
   - **Vaihe**. Tämä tarkoittaa, että yksikkö suurenee tai pienenee lisäämällä tai vähentämällä nykyisestä arvosta. Voit esimerkiksi valita 100 dollarin lisäykset/vähennykset budjettisummaan.  
  
   - **Piilota oletusohjausobjekti**. Tämä vaihtoehto piilottaa ohjausobjektin, joten ohjausobjektia eikä tietoja näytetä missään asiakasohjelmissa, jotka eivät tue ohjausobjektia. Huomaa, että perinteinen Dynamics 365:n WWW-asiakasohjelma ei tue mukautettuja ohjausobjekteja. Oletusarvon mukaan tämä asetus ei ole valittu ja normaalissa Dynamics 365:n WWW-asiakasohjelmassa näkyy oletusarvoinen, yleensä tekstipohjainen ohjausobjekti.  
  
       > [!NOTE]
       >  Oletusarvoinen ohjausobjekti tunnistetaan **(oletusarvo)**, joka seuraa komponentin nimeä.  
       >   
       > > [!div class="mx-imgBorder"] 
       > > ![oletusarvoinen ohjausobjekti](media/default-control.png "oletusarvoinen ohjausobjekti")  
  
8.  Valitse **OK**, jolloin **Kentän ominaisuudet** -sivu sulkeutuu.  
  
9. Voit aktivoida mukautukset entiteettilomakkeessa valitsemalla **Tallenna** ja valitsemalla sitten **Julkaise**.  
  
10. Valitse **Tallenna ja sulje**, kun haluat sulkea Suhde-lomakkeen.  
  
### <a name="see-the-custom-control-in-action"></a>Tarkastele mukautettua ohjausobjektia käytännössä  
 Avaa tietue, jossa on mukautetun ohjausobjektin sisältävä kenttä. Tietue voi olla esimerkiksi edellisen esimerkin mahdollisuuslomake. Tarkastele, miten kenttää on muutettu.  
  
   > [!div class="mx-imgBorder"] 
   > ![Lomakkeessa hahmonnettu liukusäädinohjausobjekti](media/slider-control.PNG "Lomakkeessa hahmonnettu liukusäädinohjausobjekti")  
  
 Kenttä näytetään liukusäädinohjausobjektina tekstikentän sijaan. 

## <a name="use-the-editable-grid-control-on-a-view-or-sub-grid"></a>Muokattavan ruudukon ohjausobjektin käyttäminen näkymässä tai aliruudukossa

Muokattavissa ruudukoissa käyttäjät voivat tehdä monipuolisia muokkauksia suoraan näkymissä ja aliruudukoissa niin WWW-sovelluksen, tabletin kuin puhelimenkin avulla. Lisätietoja: [Ruudukoiden (luetteloiden) muuttaminen muokattaviksi muokattavan ruudukon mukautetun ohjausobjektin avulla](make-grids-lists-editable-custom-control.md) 
  
## <a name="next-steps"></a>Seuraavat vaiheet  
[Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-fields.md)
