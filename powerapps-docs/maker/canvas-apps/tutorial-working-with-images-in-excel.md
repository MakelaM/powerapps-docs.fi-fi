---
title: Kuvien tallentaminen Excel-tiedostoon | Microsoft Docs
description: Kuvan tallentaminen Excel-taulukkoon pilvipalvelutilille
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/15/2016
ms.author: anneta
ms.openlocfilehash: 5c84da8bb0873fd42f5d352ae463f013113d8fcd
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023869"
---
# <a name="how-to-save-images-in-an-excel-file-and-then-add-these-images-to-your-app"></a>Kuvien tallentaminen Excel-tiedostoon ja lisääminen sovellukseen

Tässä opetusohjelmassa me:

* Luomme Excel-tiedoston ja muotoilemme sen taulukoksi
* Luomme yhteyden OneDrive for Businessiin. Minkä tahansa pilvitallennustili toimii. Tässä esittelyssä käytetään OneDrive for Businessia.
* Luo sovellus kynäsyöte-ohjausobjektilla
* Tallenna kynäsyöte-ohjausobjektissa luodut kuvat Excel-tiedostoon
* Näytä sovelluksessa kuvia Excel-tiedostosta

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]
* Opi [lisäämään tietolähde](add-data-connection.md)

## <a name="create-the-excel-file-as-a-table"></a>Luo Excel-tiedosto taulukkomuodossa

1. Anna tyhjässä Excel-tiedostossa olevalle sarakkeelle nimeksi **Kuva [kuva]**.
2. Luo taulukko seuraavien ohjeiden mukaisesti:    
   
   1. Valitse mikä tahansa tietoyksikkö mille tahansa riville ja sarakkeeseen. Valitse esimerkiksi **Kuva**.
   2. Valitse **Lisää**-valintanauhasta **Taulukko**.
   3. Valitse valintaikkunassa **Taulukossani on otsikot** ja valitse **OK**.
      
      Excel-tiedostosi on nyt taulukkomuodossa. Lisää tietoa Excel-taulukkojen muotoilusta on kohdassa [Muotoile tiedot taulukoksi](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370).
   4. Anna taulukolle nimi **Piirustukset**:  
      
      ![Anna taulukon uudeksi nimeksi Piirustukset](./media/tutorial-working-with-images-in-excel/drawings-table.png)
3. Anna Excel-tiedoston nimeksi **SavePen.xlsx** ja tallenna se pilvitallennustilillesi (OneDrive for Business, Dropbox ja niin edelleen).

## <a name="create-an-app-with-the-pen-control"></a>Luo sovellus, jossa on kynä-ohjausobjekti
1. Luo PowerAppsissa [tyhjä sovellus](get-started-create-from-blank.md).
2. Lisää sovelluksessasi pilvitallennuspalvelu [tietolähteeksi](add-data-connection.md). Kun tietolähde on lisätty, lisää **SavePen.xlsx** yhteytenä ja valitse sen jälkeen **Piirustukset**-taulukko:  
   ![Yhdistä](./media/tutorial-working-with-images-in-excel/savepen.png)  
   
   Piirustukset-taulukko on nyt lisätty tietolähdeluetteloon.
3. Valitse **Lisää**-valikosta ensin **Teksti** ja sen jälkeen **Kynäsyöte**. Anna sen uudeksi nimeksi **MyPen**:  
   
   ![Nimeä uudelleen](./media/tutorial-working-with-images-in-excel/rename-mypen.png)
4. Lisää **Painike**-ohjausobjekti (**Lisää**-valikko) ja määritä sen **OnSelect**-ominaisuus seuraavalla kaavalla:  
   `Patch(Drawings, Defaults(Drawings), {Image:MyPen.Image})`
5. Lisää **Kuvavalikoima**-ohjausobjekti (**Lisää**-valikko > **Valikoima**) ja määritä sen **Kohteet**-ominaisuudeksi `Drawings`. Valikoima-ohjausobjektin **Kuva**-ominaisuudeksi asetetaan automaattisesti `ThisItem.Image`.
   
   Näyttösi kuuluu näyttää seuraavankaltaiselta:  
   
   ![Esimerkki näytöstä](./media/tutorial-working-with-images-in-excel/screen.png)  
6. Paina F5 tai valitse Esikatsele (![](./media/tutorial-working-with-images-in-excel/preview.png)). Piirrä jotain MyPen-kuvaan ja valitse sen jälkeen painike. Piirroksesi näkyy Valikoima-ohjausobjektin ensimmäisessä kuvassa. Lisää jotain muuta piirrokseesi ja valitse painike. Valikoima-ohjausobjektin toisessa kuvassa näkyy, mitä piirsit.
   
   Sulje esikatseluikkuna.
7. Siirry pilvitallennustiliisi. Uusi **SavePen_images** kansio on luotu automaattisesti. Uuden kansion näyttäminen voi vaatia päivittämistä. Tämä kansio sisältää tallennetut kuvasi ja niiden tiedostonimien tunnukset.
   
    Avaa SavePen.xlsx. Kuva-sarake sisältää näiden uusien kuvien polut.

## <a name="add-the-image-in-an-excel-file-to-your-app"></a>Excel-tiedostossa olevan kuvan lisääminen sovellukseesi
Toisessa esimerkissä voit tallentaa kuvia pilvitallennustilille ja käyttää tämän jälkeen Excel-taulukkoa kuvien näyttämiseen sovelluksessasi.

Tässä esimerkissä käytämme [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip)-pakettia, joka sisältää joitakin .jpeg-tiedostoja.

> [!NOTE]
> Kun kuvia näytetään Excel-tiedostosta, kuvien polussa on käytettävä vinoviivaa. Kun PowerApps tallentaa kuvat Excel-taulukkoon (edellä kuvatulla tavalla), polussa käytetään kenoviivoja. Voit siis käyttää myös edellisessä esimerkissä kuvattua **SavePen_images**-kansiota. Jos toimit niin, muuta Excel-taulukon polussa olevat kenoviivat vinoviivoiksi. Muussa tapauksessa kuvat eivät näy.  

1. Lataa [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) ja poimi **Assets**-kansio pilvitallennustilillesi.
2. Luo Excel-laskentataulukossa taulukko, joka näyttää seuraavalta:
   
    ![Jackets-taulukko](./media/tutorial-working-with-images-in-excel/jackets.png)
3. Anna taulukolle nimi **Takit**. Anna Excel-tiedoston nimeksi **Assets.xlsx**. Voit myös antaa **Assets**-kansion uudeksi nimeksi **Assets_images**.
4. Lataa sovelluksessasi **Takit**-taulukko tietolähteeksi.  
5. Lisää **Vain kuva** -ohjausobjekti (**Lisää**-välilehti > **Valikoima**) ja aseta sen **Kohteet**-ominaisuudeksi `Jackets`:  
   
    ![Kohteet-ominaisuus](./media/tutorial-working-with-images-in-excel/items-jackets.png)
   
    Valikoimaan päivitetään automaattisesti kuvat:  
   
    ![Takkikuvat](./media/tutorial-working-with-images-in-excel/images.png)

Kun määrität Kohteet-ominaisuuden, sarake, jonka nimi on **PowerAppsId**, lisätään automaattisesti Excel-taulukkoon.

Excel-taulukon kuvan polku voi olla myös kuvan URL-osoite. Lataa [Flooring Estimates](http://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) -mallitiedosto pilvitallennuspalveluusi, lisää `FlooringEstimates` taulukko tietolähteeksi sovellukseesi ja määritä sitten valikoiman ohjausobjektiksi `FlooringEstimates`. Kuvat päivitetään automaattisesti valikoimaan.

## <a name="learn-more"></a>Lue lisätietoja
[Kuvan, videon tai äänen lisääminen](add-images-pictures-audio-video.md)  
[Tietojen näyttäminen viiva-, ympyrä- tai palkkikaaviona sovelluksessasi](use-line-pie-bar-chart.md)  
[Tutustu taulukkoihin ja tietueisiin PowerAppsissa](working-with-tables.md)

