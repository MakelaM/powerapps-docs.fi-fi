---
title: Kuvien tallentaminen Excel-tiedostoon | Microsoft Docs
description: Kuvan tallentaminen Excel-taulukkoon pilvipalvelutilille
documentationcenter: ''
author: AFTOwen
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 06/15/2016
ms.author: anneta
ms.openlocfilehash: c9a70a362071558e415b3077e8ff536088edd2db
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-save-images-in-an-excel-file-and-then-add-these-images-to-your-app"></a>Kuvien tallentaminen Excel-tiedostoon ja näiden kuvien käyttäminen sovelluksessasi

Tässä opetusohjelmassa me:

* Luomme Excel-tiedoston ja muotoilemme sen taulukoksi
* Luomme yhteyden OneDrive for Businessiin. Minkä tahansa pilvitallennustili toimii. Tässä esittelyssä käytetään OneDrive for Businessia.
* Luo sovellus käyttäen kynäsyöte-ohjausobjektia
* Tallenna kuvat, jotka on luotu kynäsyöte-ohjausobjektissa, Excel-tiedostoon
* Näytä sovelluksessasi kuvia Excel-tiedostosta

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]
* Opi [lisäämään tietolähde](add-data-connection.md)

## <a name="create-the-excel-file-as-a-table"></a>Luo Excel-tiedoston taulukkona

1. Nimeä tyhjässä Excel-tiedostossa sarake nimellä **Image [image]**.
2. Luo taulukko suorittamalla seuraavat vaiheet:    
   
   1. Valitse mikä tahansa tietoyksikkö mille tahansa riville ja sarakkeeseen. Valitse esimerkiksi **Kuva**.
   2. Valitse **Lisää**-valintanauhasta **Taulukko**.
   3. Valitse valintaikkunassa **Taulukossani on otsikot** ja valitse **OK**.
      
      Excel-tiedostosi on nyt taulukkomuodossa. [Muotoile tiedot taulukoksi](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370) tarjoaa lisätietoja taulukon muotoilusta Excelissä.
   4. Anna taulukolle nimi **Piirustukset**:  
      
      ![Anna taulukon uudeksi nimeksi Piirustukset](./media/tutorial-working-with-images-in-excel/drawings-table.png)
3. Excel-tiedoston nimeksi **SavePen.xlsx**, ja Tallenna tiedosto pilvipalveluun tallennustilisi (OneDrive for Business, Dropbox ja niin edelleen).

## <a name="create-an-app-with-the-pen-control"></a>Luo sovellus, jossa on kynä-ohjausobjekti
1. Luo PowerAppsissa [tyhjä sovellus](get-started-create-from-blank.md).
2. Lisää sovelluksessasi pilvitallennuspalvelu [tietolähteeksi](add-data-connection.md). Kun tietolähde on lisätty, lisää **SavePen.xlsx** yhteytenä ja valitse sitten **Piirustukset**-taulukko:  
   ![Yhdistä](./media/tutorial-working-with-images-in-excel/savepen.png)  
   
   Nyt Piirustukset-taulukko on luetteloitu tietolähteeksi.
3. Valitse **Lisää**-valikosta **Teksti** ja valitse sitten **Kynäsyöte**. Nimeä se uudelleen nimellä **MyPen**:  
   
   ![Nimeä uudelleen](./media/tutorial-working-with-images-in-excel/rename-mypen.png)
4. Lisää **painike**-ohjausobjekti (**Lisää**-valikko) ja määritä sen **OnSelect**-ominaisuudeksi seuraava kaava:  
   `Patch(Drawings, Defaults(Drawings), {Image:MyPen.Image})`
5. Lisää **Kuvavalikoima**-ohjausobjekti (**Lisää**-valikko > **Valikoima**) ja määritä sen **Items**-ominaisuudeksi `Drawings`. Valikoima-ohjausobjektin **Image**-ominaisuudeksi asetetaan automaattisesti `ThisItem.Image`.
   
   Näyttösi tulisi näyttää seuraavankaltaiselta:  
   
   ![Mallinäyttö](./media/tutorial-working-with-images-in-excel/screen.png)  
6. Paina F5 tai valitse Esikatsele (![](./media/tutorial-working-with-images-in-excel/preview.png)). Piirrä jotain MyPen-kuvaan ja valitse sitten painike. Piirroksesi näkyy valikoima-ohjausobjektin ensimmäisessä kuvassa. Lisää jotain muuta piirrokseesi ja valitse painike. Valikoima-ohjausobjektin toisessa kuvassa näkyy, mitä piirsit.
   
   Sulje esikatseluikkuna.
7. Siirry pilvitallennustiliisi. Uusi **SavePen_images** kansio on luotu automaattisesti. Voit joutua päivittämään, ennen kuin näet uuden kansion. Tämä kansio sisältää tallennetut kuvasi ja niiden tiedostonimien tunnukset.
   
    Avaa SavePen.xlsx. Kuva-sarake sisältää näiden uusien kuvien polut.

## <a name="add-the-image-in-an-excel-file-to-your-app"></a>Lisää Excel-tiedostossa oleva kuva sovellukseesi
Toisessa esimerkissä voit tallentaa kuvia pilvitallennustilille ja käyttää tämän jälkeen Excel-taulukkoa kuvien näyttämiseen sovelluksessasi.

Tässä esimerkissä käytämme [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip)-pakettia, joka sisältää joitakin .jpeg-tiedostoja.

> [!NOTE]
> Kun näytetään kuvia Excel-tiedostosta, näiden kuvien polussa on käytettävä vinoviivaa. Kun PowerApps tallentaa kuvat Excel-taulukkoon (samoin kuin edellä), polussa käytetään kenoviivoja. Voit siis käyttää myös **SavePen_kuvia** edellisestä esimerkistä. Jos toimit niin, muuta polut Excel-taulukossa käyttämään vinoviivaa kenoviivojen asemasta. Muussa tapauksessa kuvat eivät näy.  

1. Lataa [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) ja poimi **Assets**-kansio pilvipalvelun tallennustilan tiliisi.
2. Luo Excel-laskentataulukossa taulukko, joka näyttää seuraavalta:
   
    ![Jackets-taulukko](./media/tutorial-working-with-images-in-excel/jackets.png)
3. Anna taulukolle nimi **Jackets**. Anna Excel-tiedoston nimeksi **Assets.xlsx**. Voit myös antaa **Assets**-kansion uudeksi nimeksi **Assets_images**.
4. Lataa sovelluksessasi **Jackets**-taulukko tietolähteeksi.  
5. Lisää **Vain kuva** -ohjausobjekti (**Lisää**-välilehti > **Valikoima**) ja aseta sen **Items**-ominaisuudeksi `Jackets`:  
   
    ![Items-ominaisuus](./media/tutorial-working-with-images-in-excel/items-jackets.png)
   
    Valikoimaan päivitetään automaattisesti kuvat:  
   
    ![Jacket-kuvat](./media/tutorial-working-with-images-in-excel/images.png)

Kun määrität Items-ominaisuuden, sarake, jonka nimi on **PowerAppsId**, lisätään automaattisesti Excel-taulukkoon.

Excel-taulukon kuvan polku voi olla myös kuvan URL-osoite. Lataa [Flooring Estimates](http://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) -mallitiedosto pilvitallennuspalveluusi, lisää `FlooringEstimates` taulukko tietolähteeksi sovellukseesi ja määritä sitten valikoiman ohjausobjektiksi `FlooringEstimates`. Kuvat päivitetään automaattisesti valikoimaan.

## <a name="learn-more"></a>Lue lisätietoja
[Kuvan, videon tai äänen lisääminen](add-images-pictures-audio-video.md)  
[Tietojen näyttäminen viiva-, ympyrä- tai palkkikaaviona sovelluksessasi](use-line-pie-bar-chart.md)  
[Tutustu taulukkoihin ja tietueisiin PowerAppsissa](working-with-tables.md)

