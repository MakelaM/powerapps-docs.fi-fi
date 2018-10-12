---
title: Segmentoitujen ratkaisujen ja korjaustiedostojen käyttäminen ratkaisupäivitysten helpottamiseksi PowerAppsissa | MicrosoftDocs
description: Opi käyttämään ratkaisun segmentointia ratkaisujesi päivittämiseksi
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
- powerapps
author: Mattp123
ms.assetid: 5c05f683-e1bd-4885-be23-b6973128773f
caps.latest.revision: 15
ms.author: matp
manager: kvivek
ms.openlocfilehash: 274e2914d65b6bcb644821c044adb3b0246a75fc
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677515"
---
# <a name="use-segmented-solutions-and-patches-to-export-selected-entity-assets"></a>Segmentoitujen ratkaisujen ja korjaustiedostojen käyttäminen valittujen entiteettiresurssien vientiä varten

Ratkaisun segmentoinnin avulla voit hallita tarkemmin, mitä jaat ratkaisuissa ja ratkaisun korjaustiedostoissa. Ratkaisun segmentoinnin avulla voit viedä ratkaisuja valituilla entiteettiresursseilla, kuten entiteettikentillä, lomakkeilla ja näkymillä sen sijaan, että veisit koko entiteettejä kaikilla resursseilla. Ratkaisujen käyttöliittymällä voit luoda segmentoituja ratkaisuja ja korjaustiedostoja kirjoittamatta lainkaan koodia.  
  
 Sen lisäksi, että voit hallita tarkemmin ratkaisun sisältöä, pystyt myös hallitsemaan, mitä korjaustiedosto sisältää. Voit luoda korjaustiedoston pääratkaisua varten ja viedä sen pienenä päivityksenä perusratkaisuun. Kun kloonaat ratkaisun, järjestelmä kokoaa kaikki liittyvät korjaukset perusratkaisuun ja luo uuden version.  
  
 Kun käsittelet korjaustiedostoja ja kloonattuja ratkaisuja, ota huomioon seuraavat tiedot:  
  
-   Korjaustiedosto on pienimuotoinen täydentävä päivitys pääratkaisuun. Korjaustiedosto voi lisätä tai päivittää osia ja resursseja pääratkaisussa, kun se asennetaan kohdejärjestelmään, mutta se ei voi poistaa mitään osia tai resursseja pääratkaisusta.  
  
-   Korjaustiedostolla voi olla vain yksi pääratkaisu, mutta pääratkaisulla voi olla yksi tai useampi korjaustiedosto.  
  
-   Korjaustiedosto luodaan hallitsemattomalle ratkaisulle. Et voi luoda korjaustiedostoa hallitulle ratkaisulle.  
  
-   Kun viet korjaustiedoston kohdejärjestelmään, se tulee viedä hallittuna korjaustiedostona. Älä käytä hallitsemattomia korjaustiedostoja tuotantoympäristössä.  
  
-   Pääratkaisun on oltava kohdejärjestelmässä korjaustiedoston asentamiseksi.  
  
-   Voit poistaa tai päivittää korjaustiedoston.  
  
-   Jos poistat pääratkaisun, myös kaikki alikorjaustiedostot poistetaan. Järjestelmä antaa varoitussanoman siitä, että poistamista ei voi kumota. Poistaminen suoritetaan yksittäisessä tapahtumassa. Jos jotakin korjaustiedostoa tai pääratkaisua ei voida poistaa, koko tapahtuma peruutetaan.  
  
-   Kun olet luonut ensimmäisen korjaustiedoston pääratkaisulle, ratkaisu lukitaan etkä voi tehdä muutoksia tähän ratkaisuun tai viedä sitä. Jos kuitenkin poistat kaikki sen alikorjaustiedostot, pääratkaisun lukitus poistetaan.  
  
-   Kun kloonaat perusratkaisun, kaikki alikorjaustiedostot kootaan perusratkaisuun ja siitä tulee uusi versio. Voit lisätä, muokata tai poistaa osia ja resursseja kloonatussa ratkaisussa.  
  
-   Kloonattu ratkaisu korvaa perusratkaisun, kun se asennetaan hallittuna ratkaisuna kohdejärjestelmään. Kloonattua ratkaisua käytetään yleensä edeltävän ratkaisun merkittävän päivityksen toimittamiseen.  
  
## <a name="understanding-version-numbers-for-cloned-solutions-and-patches"></a>Kloonattujen ratkaisujen ja korjaustiedostojen versionumerot  
 Ratkaisun versio on seuraavassa muodossa: pääversio.aliversio.koontiversio.tarkistusversio. Korjaustiedostolla on oltava suurempi koontiversion tai tarkistusversion numero kuin pääratkaisuilla. Sen sijaan sillä ei voi olla suurempaa pääversion tai aliversion numeroa. Jos esimerkiksi perusratkaisun versio on 3.1.5.7, korjaustiedoston versio voi olla 3.1.5.8 tai 3.1.7.0, mutta ei 3.2.0.0. Kloonatun ratkaisun versionumeron on oltava suurempi tai yhtä suuri kuin perusratkaisun versionumero. Jos esimerkiksi perusratkaisun versio on 3.1.5.7, kloonatun ratkaisun versio voi olla 3.2.0.0 tai 3.1.5.7. Käyttöliittymässä voit määrittää vain kloonatun ratkaisun pääversion ja aliversion arvot sekä korjaustiedoston koontiversion tai tarkistusversion arvot.  
  
## <a name="create-a-segmented-solution-with-the-entity-assets-you-want"></a>Luo segmentoitu ratkaisu haluamillasi entiteettiresursseilla  
 Voit luoda segmentoidun ratkaisun luomalla ensin hallitsemattoman ratkaisun ja lisäämällä olemassa olevat resurssit. Voit lisätä useita järjestelmän entiteettejä tai mukautettuja entiteettejä ja lisätä kullekin entiteetille resurssit, jotka haluat sisällyttää ratkaisuun. Ohjatun toiminnon kaltainen määritys opastaa sinut entiteettiresurssien lisäysprosessin läpi.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse **Uusi** ja luo ratkaisu. Anna tiedot pakollisiin kenttiin. Valitse **Tallenna ja sulje**.  
  
3.  Avaa juuri luomasi ratkaisu. Valitse avattavasta **Lisää olemassa oleva** -luettelosta **Entiteetti**.  
  
4.  Valitse **Valitse ratkaisun osat** -valintaikkunassa vähintään yksi entiteetti, jonka haluat lisätä ratkaisuun. Valitse **OK**.  
  
5.  Ohjattu toiminto avautuu. Lisää kunkin valitun entiteetin resurssit ratkaisuun noudattamalla ohjatun toiminnon vaiheita.  
  
6.  Valitse **Julkaise**, jotta muutokset tulevat voimaan.  
  
 Seuraavissa kuvissa on esimerkki segmentoidun ratkaisun luomisesta valitsemalla entiteettiresurssit entiteeteistä `Account`, `Case` ja `Contact`.  
  
 Aloita valitsemalla **Entiteetti**-osa.  
  
 ![Lisää olemassa olevia resursseja.](media/solution-segmentation-add-existing-resources-admin.png "Lisää olemassa olevia resursseja.")  
  
 Valitse sitten ratkaisun osat.  
  
 ![Valitse ratkaisun osat.](media/solution-segmentation-select-components-admin.png "Valitse ratkaisun osat.")  
  
 Noudata ohjattua toimintoa. Vaihe 1: valitse aakkosjärjestyksessä resurssit ensimmäiselle entiteetille, entiteetti `Account`, kuten kuvassa näkyy.  
  
 ![Käynnistä ohjattu toiminto.](media/solution-segmentation-wizard-starts-admin.png "Käynnistä ohjattu toiminto.")  
  
 Avaa **Kentät**-välilehti ja valitse **Tilinumero**-kenttä.  
  
 ![Valitse Tili-entiteetin resurssit.](media/solution-segmentation-select-account-assets-admin.png "Valitse Tili-entiteetin resurssit.")  
  
 Vaihe 2: lisää kaikki resurssit **Tapaus**-entiteetille.  
  
 ![Valitse Tapaus-entiteetin resurssit.](media/solution-segmentation-select-case-assets-admin.png "Valitse Tapaus-entiteetin resurssit.")  
  
 Vaihe 3: lisää **Vuosipäivä**-kenttä **Yhteyshenkilö**-entiteetille.  
  
 ![Valitse Yhteyshenkilö-entiteetin resurssit.](media/solution-segmentation-select-contact-assets-admin.png "Valitse Yhteyshenkilö-entiteetin resurssit.")  
  
 Näin luodaan segmentoitu ratkaisu, joka sisältää kolme entiteettiä: `Account`, `Case` ja `Contact`. Jokainen entiteetti sisältää vain valitut resurssit.  
  
 ![Ratkaisu ja entiteetit. ](media/solution-segmentation-solution-entities-admin.png "Ratkaisu ja entiteetit.")  
  
## <a name="create-a-solution-patch"></a>Ratkaisun korjaustiedoston luominen  
 Korjaustiedosto sisältää muutoksia pääratkaisuun, esimerkiksi osia ja resursseja lisäämällä tai muokkaamalla. Sinun ei tarvitse sisällyttää pääratkaisun osia, ellet halua muokata niitä.  
  
 #### <a name="create-a-patch-for-an-unmanaged-solution"></a>Luo korjaustiedosto hallitsemattomalle ratkaisulle  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse luettelosta hallitsematon ratkaisu, jolle korjaustiedosto luodaan. Valitse **Kloonaa korjaustiedosto**. Näyttöön tulee valintaikkuna, joka sisältää perusratkaisun nimen ja korjaustiedoston versionumeron. Valitse **Tallenna**.  
  
3.  Etsi ja avaa juuri luotu korjaustiedosto ruudukosta. Lisää haluamasi osat ja resurssit ohjatun toiminnon avulla, aivan kuten perusratkaisun kanssa.  
  
4.  Valitse **Julkaise**, jotta muutokset tulevat voimaan.  
  
 Seuraavissa kuvissa on esimerkki korjaustiedoston luomisesta nykyiselle ratkaisulle. Aloita valitsemalla **Kloonaa korjaustiedosto** (pienennetyssä näkymässä **Kloonaa korjaustiedosto** -kuvaketta esittää kaksi pientä neliötä, kuten alla).  
  
 ![Kloonaa korjaustiedosto -kuvake.](media/solution-segmentation-click-patch-icon-admin.png "Kloonaa korjaustiedosto -kuvake.")  
  
 **Kloonaa korjaustiedosto** -valintaikkunassa näet, että korjaustiedoston versionumero perustuu pääratkaisun versionumeroon, mutta koontiversion numero on kasvanut yhdellä. Jokaisella tulevalla korjaustiedostolla on suurempi koontiversion tai tarkistusversion numero kuin edeltävällä korjaustiedostolla.  
  
 ![Käytä Kloonaa korjaustiedostoon -valintaikkunaa.](media/solution-segmentation-clone-patch-dialog-admin.png "Käytä Kloonaa korjaustiedostoon -valintaikkunaa.")  
  
 Seuraavassa näyttökuvassa esitetään perusratkaisun **SegmentedSolutionExample** versio **1.0.1.0** ja korjaustiedoston **SegmentedSolutionExample_Patch** versio **1.0.2.0**.  
  
 ![Ruudukko, jossa ratkaisut ja korjaustiedostot.](media/solution-segmentation-solution-patch-grid-admin.png "Ruudukko, jossa ratkaisut ja korjaustiedostot.")  
  
 Olemme lisänneet korjaustiedostoon uuden mukautetun entiteetin nimeltä `Book` ja kaikki entiteetin `Book` resurssit.  
  
 ![Lisää mukautettu entiteetti korjaustiedostoon.](media/solution-segmentation-add-book-patch-admin.png "Lisää mukautettu entiteetti korjaustiedostoon.")  
  
## <a name="clone-a-solution"></a>Kloonaa ratkaisu  
 Kun kloonaat hallitsemattoman ratkaisun, kaikki tähän ratkaisuun liittyvät korjaukset kootaan alkuperäisen ratkaisun uuteen versioon.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse luettelosta hallitsematon ratkaisu, jonka haluat kloonata. Valitse **Kloonaa ratkaisu**. Näyttöön tulee valintaikkuna, joka sisältää perusratkaisun nimen ja uuden versionumeron. Valitse **Tallenna**.  
  
3.  Valitse **Julkaise**, jotta muutokset tulevat voimaan.  
  
 Kun jatkat eteenpäin esimerkissä, näet **Kloonaa ratkaisu** -valintaikkunan, jossa on uusi ratkaisun versionumero.  
  
 ![Käytä Kloonaa ratkaisuun -valintaikkunaa.](media/solution-segmentation-clone-solution-dialog-admin.png "Käytä Kloonaa ratkaisuun -valintaikkunaa.")  
  
 Kloonaamisen jälkeen uusi ratkaisuversio sisältää kolme alkuperäistä entiteettiä (`Account`, `Case` ja `Contact`) sekä mukautetun entiteetin nimeltä `Book`, joka on lisätty korjaustiedostoon. Jokainen entiteetti sisältää vain esimerkissä lisätyt resurssit.  
  
 ![Kloonattu ratkaisu, jossa on koottu korjaustiedosto.](media/solution-segmentation-solution-rolled-up-patch-admin.png "Kloonattu ratkaisu, jossa on koottu korjaustiedosto.")  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Ratkaisujen yleiskatsaus](solutions-overview.md) [Yksinkertaista ratkaisupäivityksiä luomalla korjaustiedostoja]

