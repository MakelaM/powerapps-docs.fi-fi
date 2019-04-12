---
title: Päivitysten yksinkertaistaminen segmentoitujen ratkaisujen ja ohjelmakorjausten avulla PowerAppsissa | MicrosoftDocs
description: 'Opettele käyttämään ratkaisusegmentointia ratkaisujen päivittämiseen '
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 5c05f683-e1bd-4885-be23-b6973128773f
caps.latest.revision: 15
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="use-segmented-solutions-and-patches-to-export-selected-entity-assets"></a>Käytä segmentoitua ratkaisuja ja korjauksia valitun entiteettiresurssien viemiseen

Ratkaisun segmentoinnin avulla hallitset tiukemmin ratkaisujen ja ohjelmakorjausten jakelua. Ratkaisun segmentointitoiminnon avulla voit viedä ratkaisuja valitun entiteetin komponenteista, kuten määritteitä, lomakkeita, tai näkymiä sen sijasta, että veisit koko entiteetin ja kaikki sen komponentit. Voit käyttää ratkaisukäyttöliittymää segmentoitujen ratkaisujen ja korjaustiedostojen luomiseen kirjoittamatta koodia.  
  
 Voit valvoa entistä tarkemmin ratkaisujen ja korjaustiedostojen sisältöä. Voit luoda pääratkaisun korjaustiedoston ja viedä sen pienenä päivityksenä perusratkaisuun. Kun kloonaat ratkaisun, järjestelmä kokoaa kaikki tarvittavat korjaustiedostot pääratkaisuksi ja luo uuden version.  
  
 Muista seuraavat seikat, kun käsittelet korjaustiedostoja ja kloonattuja ratkaisuja:  
  
-   Korjaustiedosto on pieni lisäävä päivitys pääratkaisuun. Kohdejärjestelyyn asennettu korjaustiedosto voi lisätä tai päivittää komponentteja ja resursseja pääratkaisuun, mutta se ei voi poistaa komponentteja eikä resursseja pääratkaisusta.  
  
-   Korjaustiedostolla voi olla vain yksi pääratkaisu, mutta pääratkaisulla voi olla yksi tai useita korjaustiedostoja.  
  
-   Korjaustiedosto luodaan ei-hallittua ratkaisua varten. Hallittuun ratkaisuun ei voi luoda korjaustiedostoa.  
  
-   Vie korjaustiedosto kohdejärjestelmään hallittuna korjaustiedostona. Älä käytä ei-hallittuja korjaustiedostoja tuotantoympäristöissä.  
  
-   Pääratkaisun on oltava kohdejärjestelmässä, kun korjaustiedosto asennetaan.  
  
-   Voit poistaa tai päivittää korjaustiedoston.  
  
-   Jos poistat pääratkaisun, kaikki siihen kuuluvat korjaustiedostot poistuvat. Järjestelmä näyttää varoitusviestin, jonka mukaan poistotoimintoa ei voi kumota. Poisto suoritetaan yhtenä tapahtumasarjana. Jos korjaustiedostojen tai ylätason ratkaisun poistaminen epäonnistuu, koko tapahtuma peruuntuu.  
  
-   Kun olet luonut ensimmäisen pääratkaisun korjaustiedoston, ratkaisu lukitaan ja eikä ratkaisuun voi tehdä muutoksia eikä viedä sitä. Jos poistat kaikki alatason korjaustiedostot, pääratkaisu lukkiutuu.  
  
-   Kun kloonaat perusratkaisun, järjestelmä palauttaa kaikki tarvittavat alatason tiedostot perusratkaisuun, josta tulee uusi versio. Voit lisätä, muokata tai poistaa komponentteja ja resursseja kloonatusta ratkaisusta.  
  
-   Kloonattu ratkaisu korvaa perusratkaisun, kun se asennetaan kohdejärjestelmään hallittuna ratkaisuna. Kloonattua ratkaisua käytetään yleensä viemään suuria päivityksiä edelliseen ratkaisuun.  
  
## <a name="understanding-version-numbers-for-cloned-solutions-and-patches"></a>Kloonattujen ratkaisujen ja korjaustiedostojen ymmärtäminen  
 Ratkaisuversion muoto on: pääversio.aliversio.koontiversio.tarkistusversio. Korjaustiedoston koonti- tai tarkistusversion numeron on oltava suurempi kuin vastaava numero pääratkaisussa. Siinä ei voi olla suurempi pää- vai aliversio. Esimerkiksi perusratkaisun version 3.1.5.7 korjaustiedosto voi olla versio 3.1.5.8 tai 3.1.7.0 muttei 3.2.0.0. Kloonatun ratkaisun versionumeron on oltava suurempi tai yhtä suuri kuin perusratkaisun versionumero. Esimerkiksi perusratkaisun version 3.1.5.7 kloonattu ratkaisu voi olla versio 3.2.0.0 tai 3.1.5.7. Käyttöliittymässä voit määrittää kloonatun ratkaisun pää- ja aliversioiden arvot ja korjaustiedoston koonti- tai tarkistusversion arvot.  
  
## <a name="create-a-segmented-solution-with-the-entity-assets-you-want"></a>Luo segmentoitu ratkaisu haluamillasi entiteettien resursseilla  
 Aloita segmentoidun ratkaisun luominen luomalla ei-hallittu ratkaisu ja lisäämällä nykyisiä resursseja. Voit lisätä useita mukautettuja tai järjestelmäentiteettejä. Valitse jokaiselle entiteetille resurssit, jotka haluat lisätä ratkaisuun. Ohjatun asennuksen avulla voit lisätä entiteetin prosessit vaihteittain.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Luo uusi ratkaisu Valitsemalla **Uusi**. Kirjoita tiedot pakollisiin kenttiin. Valitse **Tallenna ja sulje**.  
  
3.  Avaa luomasi ratkaisu. Valitse **Lisää aiemmin luotu**-pudotusvalikosta **Entiteetti**.  
  
4.  Valitse ratkaisuun lisättävät entiteetit **Valitse ratkaisun osat** -valintaikkunassa. Valitse **OK**.  
  
5.  Ohjattu toiminto avautuu. Lisää valitut entiteetit ratkaisuun seuraamalla ohjatun toiminnon ohjeita.  
  
6.  Valitse **Julkaise**, jotta muutokset tulevat voimaan.  
  
 Seuraavassa kuvassa on esimerkki segmentoidun ratkaisun luomisesta valitsemalla entiteettien resurssit `Account`-, `Case`- ja `Contact`-entiteeteistä.  
  
 Valitse ensin **Entiteetti**-komponentti.  

 > [!div class="mx-imgBorder"] 
 > ![Lisää olemassa olevat resurssit.](media/solution-segmentation-add-existing-resources-admin.png "Lisää olemassa olevat resurssit.")  
  
 Valitse tämän jälkeen ratkaisun osat  
  
 ![Valitse ratkaisun osia.](media/solution-segmentation-select-components-admin.png "Valitse ratkaisun osia.")  
  
 Seuraa ohjatun toiminnon ohjeita. Vaiheessa 1 valitse ensimmäisen entiteetin resurssit aakkosjärjestyksessä. Oheisen kuvan mukaan ensimmäinen entiteetti on `Account`.  
  
 ![Ohjatun toiminnon aloittaminen.](media/solution-segmentation-wizard-starts-admin.png "Ohjatun toiminnon aloittaminen.")  
  
 Avaa **Kentät**-välilehti ja valitse **Tilinumero**-kenttä.  
  
 ![Tilin entiteettiresurssien valitseminen.](media/solution-segmentation-select-account-assets-admin.png "Tilin entiteettiresurssien valitseminen.")  
  
 Vaiheessa 2 lisää kaikki resurssit **Palvelupyyntö**-entiteetille, .  
  
 ![Palvelupyyntö-kohteen resurssien valitseminen.](media/solution-segmentation-select-case-assets-admin.png "Palvelupyyntö-kohteen resurssien valitseminen.")  
  
 Vaiheessa 3 lisää **Merkkipäivä**-kenttä **Yhteyshenkilö**-entiteetille.  
  
 ![Tilin yhteyshenkilöentiteettiresurssien valitseminen.](media/solution-segmentation-select-contact-assets-admin.png "Tilin yhteyshenkilöentiteettiresurssien valitseminen.")  
  
 Tämän seurauksena luotu segmentoitu ratkaisu sisältää kolme entiteettiä `Account`, `Case` ja `Contact`. Jokaisessa entiteetissä on vain valitut resurssit.  
  
 > [!div class="mx-imgBorder"] 
 > ![entiteetillinen ratkaisu.](media/solution-segmentation-solution-entities-admin.png "entiteetillinen ratkaisu.")  
  
## <a name="create-a-solution-patch"></a>Luo ratkaisun korjaustiedosto  
 Korjaustiedosto sisältää pääratkaisun muutoksia, esimerkiksi lisättyjä tai muokattuja komponentteja ja resursseja. Sinun ei tarvitse sisällyttää pääratkaisun komponentteja, ellet aio muokata niitä.  
  
 #### <a name="create-a-patch-for-an-unmanaged-solution"></a>Korjaustiedoston luominen ei-hallittua ratkaisua varten  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse luettelosta hallitsematon ratkaisu, jolle korjaustiedosto luodaan. Valitse **Kloonaa korjaustiedosto**. Avautuvassa valintaikkunassa on perusratkaisun nimi ja korjaustiedoston versionumero. Valitse **Tallenna**.  
  
3.  Etsi ruudukosta äsken luotu korjaustiedosto ja avaa se. Lisää haluamasi komponentit ja resurssit ohjatun toiminnon ohjeiden avulla, samoin kuin perusratkaisun kohdalla tehtiin.  
  
4.  Valitse **Julkaise**, jotta muutokset tulevat voimaan.  
  
 Seuraavissa kuvissa on esimerkki korjaustiedoston luomisesta olemassa olevalle ratkaisulle. Valitse ensin **Kloonaa korjaustiedosto** (supistetussa näkymässä **Kloonaa korjaustiedosto** kuvake näkyy oheisen kuvan mukaisesti kahtena pienenä neliönä).  
  
 > [!div class="mx-imgBorder"] 
 > ![paikkauskuvakkeen kloonaus.](media/solution-segmentation-click-patch-icon-admin.png "paikkauskuvakkeen kloonaus.")  
  
 **Kloonaa korjaustiedoston** -valintaikkunassa näet, että korjaustiedoston versionumero perustuu pääratkaisun versionumeroon, mutta koontiversion numero on kasvanut yhdellä. Jokaisen myöhemmän korjaustiedoston koonti- tai tarkistusversion numero on edeltävän korjaustiedoston vastaavaa numeroa suurempi.  
  
 ![Käytä kloonaamisen paikkaus -valintaikkunaa.](media/solution-segmentation-clone-patch-dialog-admin.png "Käytä kloonaamisen paikkaus -valintaikkunaa.")  
  
 Seuraavassa näyttökuvassa on perusratkaisu **SegmentedSolutionExample**, versio **1.0.1.0**, ja korjaustiedoston **SegmentedSolutionExample_Patch** versio **1.0.2.0**.  
  
 > [!div class="mx-imgBorder"] 
 > ![Ruudukko, jossa on ratkaisuja ja korjaukset.](media/solution-segmentation-solution-patch-grid-admin.png "Ruudukko, jossa on ratkaisuja ja korjaukset.")  
  
 Lisäsimme uuteen mukautettuun entiteettiin korjaustiedoston `Book` ja kaikki `Book`-entiteetin resurssit korjaustiedostoon.  
  
 ![Lisää korjaustiedostoon mukautettu entiteetti.](media/solution-segmentation-add-book-patch-admin.png "Lisää korjaustiedostoon mukautettu entiteetti.")  
  
## <a name="clone-a-solution"></a>Kloonaa ratkaisu  
 Kun kloonaat ei-hallitun ratkaisun, kaikki ratkaisulle luodut korjaustiedostot kootaan alkuperäisen ratkaisun uuteen versioon.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse luettelosta ei-hallittu ratkaisu, jonka haluat kloonata. Valitse **Kloonausratkaisu**. Avautuvassa valintaikkunassa on perusratkaisun nimi ja uuden version numero. Valitse **Tallenna**.  
  
3.  Valitse **Julkaise**, jotta muutokset tulevat voimaan.  
  
 Saman esimerkin mukaan näet seuraavaksi uuden ratkaisun versionumeron **Kloonaa ratkaisu** -valintaikkunassa.  
  
 ![Käytä Kloonaa ratkaisu -valintaikkunaa.](media/solution-segmentation-clone-solution-dialog-admin.png "Käytä Kloonaa ratkaisu -valintaikkunaa.")  
  
 Kloonauksen jälkeen uusi ratkaisuversio sisältää kolme alkuperäistä entiteettiä (`Account`, `Case` ja `Contact`) ja mukautetun entiteetin `Book` , joka lisättiin korjaustiedostoon. Jokaisessa entiteetissä on vain esimerkissä lisätyt resurssit.  
  
 > [!div class="mx-imgBorder"] 
 > ![Kloonattu ratkaisu, jossa on koottu korjaustiedosto.](media/solution-segmentation-solution-rolled-up-patch-admin.png "Kloonattu ratkaisu, jossa on koottu korjaustiedosto.")  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Ratkaisujen yleiskatsaus](solutions-overview.md) [Ratkaisupäivitysten yksinkertaistaminen korjaustiedostoja luomalla]

