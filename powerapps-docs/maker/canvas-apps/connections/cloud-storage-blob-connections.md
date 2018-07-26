---
title: Pilvitallennusyhteyden yleiskatsaus | Microsoft Docs
description: Ohjeet pilvitallennustiliin yhdistämiseen ja Excel-tietojen näyttämiseen sovelluksessasi
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 07/12/2016
ms.author: lanced
ms.reviewer: anneta
ms.openlocfilehash: 8e6aa988344c1ac04c2ff11eaa9d828cc8b929bc
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195653"
---
# <a name="connect-to-cloud-storage-from-powerapps"></a>Pilvitallennustiliin yhdistäminen PowerAppsista
PowerApps tarjoaa useita pilvitallennusyhteyksiä. Voit tallentaa Excel-tiedoston ja käyttää sen tietoja kaikkialla sovelluksessasi käyttämällä näitä yhteyksiä. Näitä yhteyksiä ovat muun muassa seuraavat:  

| **Azure Blob** | **Box** | **Dropbox** | **Google Drive** | **OneDrive** | **OneDrive<br>for Business** |
| --- | --- | --- | --- | --- | --- |
| ![Kuvake](./media/cloud-storage-blob-connections/blobicon.png) |![API:n kuvake][boxicon] |![API:n kuvake][dropboxicon] |![API:n kuvake][googledriveicon] |![API:n kuvake][onedriveicon] |![API:n kuvake][onedriveforbusinessicon] |

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

* Excel-tiedosto, jossa tiedot on [muotoiltu taulukoksi](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664):
  
  1. Avaa Excel-tiedosto ja valitse mikä tahansa solu tiedoissa, joita haluat käyttää.
  2. Valitse **Lisää**-välilehdeltä **Taulukko**.
  3. Valitse **Tallenna taulukkona** -valintaikkunasta **Taulukossa on otsikot** -valintaruutu ja valitse sitten **OK**.
  4. Tallenna muutokset.

## <a name="connect-to-the-cloud-storage-connection"></a>Yhdistäminen pilvitallennusyhteyteen
1. Mene osoitteeseen [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), laajenna **Hallinta** ja valitse **Yhteydet**:  
   
    ![Valitse yhteydet](./media/cloud-storage-blob-connections/connections.png)
2. Valitse **Uusi yhteys** ja sen jälkeen pilvitallennuspalvelusi yhteys. Valitse esimerkiksi **OneDrive**.
3. Sinua kehotetaan antamaan pilvitallennustilisi käyttäjänimi ja salasana. Anna ne ja valitse **Kirjaudu sisään**:  
    ![Anna käyttäjänimi ja salasana](./media/cloud-storage-blob-connections/signin.png)
   
    Kun olet kirjautunut sisään, yhteys on käytettävissä sovelluksissasi.
4. Napsauta tai napauta nauhan **Näkymä**-välilehden kohtaa **Tietolähteet**. Napsauta tai napauta oikeanpuoleisessa ruudussa **Lisää tietolähde**, napsauta tai napauta pilvitallennusyhteyttäsi ja valitse sitten Excel-taulukko.
5. Valitse **Yhdistä**.
   
    Taulukko luetteloidaan tietolähteeksi:
   
    ![Valitse Excel-taulukko](./media/cloud-storage-blob-connections/selecttable.png)
   
    > [!NOTE]
   > Muista, että Excel-tietojen täytyy olla taulukoksi muotoiltuja.

## <a name="using-the-excel-data-in-your-app"></a>Excel-tietojen käyttäminen sovelluksessasi
1. Valitse **Lisää**-valikosta **Valikoima** ja valitse valikoimaohjausobjekti **With text**.
2. Määritä valikoiman **[Items](../controls/properties-core.md)**-ominaisuus Excel-taulukkoon. Jos Excel-taulukon nimi on esimerkiksi **Taulukko1**, aseta ominaisuudeksi Taulukko1:  
   
    ![Items-ominaisuus](./media/cloud-storage-blob-connections/itemsproperty.png)  
   
    Valikoima päivittyy automaattisesti Excel-taulukon tiedoilla.
3. Valitse valikoiman toinen tai kolmas **Label**-ohjausobjekti. Toisen ja kolmannen selitteen **Text**-ominaisuuden arvoksi määritetään oletusarvoisesti automaattisesti `ThisItem.something`. Voit määrittää nämä selitteet mihin tahansa taulukon sarakkeeseen.
   
    Seuraavassa esimerkissä toiseksi selitteeksi on määritetty `ThisItem.Name` ja kolmanneksi selitteeksi on määritetty `ThisItem.Notes`:  
   
    ![Toinen selite](./media/cloud-storage-blob-connections/items-secondtextbox.png)  
   
    ![Kolmas selite](./media/cloud-storage-blob-connections/items-thirdtextbox.png)  
   
    Mallituloste:  
    ![Toinen ja kolmas selite](./media/cloud-storage-blob-connections/secondthirdtextboxes.png)
   
> [!NOTE]
> Ensimmäinen laatikko on todellisuudessa Image-ohjausobjekti. Jos Excel-taulukossa ei ole kuvaa, voit poistaa Image-ohjausobjektin ja korvata sen selitteellä. [Ohjausobjektien lisääminen ja määrittäminen](../add-configure-controls.md) -artikkelista on hyötyä tässä vaiheessa.

[Tutustu taulukkoihin ja tietueisiin](../working-with-tables.md) tarjoaa lisätietoja ja esimerkkejä.  

## <a name="sharing-your-app"></a>Sovelluksen jakaminen
Voit jakaa [sovelluksia](../share-app.md), [resursseja](../share-app-resources.md), kuten liittimiä, ja [tietoja](../share-app-data.md) muiden organisaation jäsenten kanssa.

Jos jaat kansion Dropboxissa, jaetun kansion täytyy olla liitettynä käyttäjän Dropbox-tiliin.

Liittimillä on [tiettyjä rajoituksia](#sharing-excel-tables) Excel-tiedostoihin liittyen.

## <a name="known-limitations"></a>Tunnetut rajoitukset
Jos yrität käyttää Excel-yhteyttä sovelluksessasi ja näkyviin tulee **Tietotyyppiä ei tueta** tai **Ei muotoiltu taulukoksi**, [muotoile tiedot taulukoksi](https://support.office.com/article/Create-an-Excel-table-in-a-worksheet-E81AA349-B006-4F8A-9806-5AF9DF0AC664).

Jos Excel-tiedoissa on laskettu sarake, et voi käyttää sitä sovelluksen luomiseen eikä kyseisiä tietoja voi lisätä olemassa olevaan sovellukseen.

### <a name="sharing-excel-tables"></a>Excel-taulukoiden jakaminen
Voit jakaa tietoja Excel-tiedostossa seuraavasti:

* OneDrive for Businessissa voit jakaa itse tiedoston.
* OneDrivessa voit jakaa kansion, joka sisältää tiedoston, ja määrittää median tiedostopolut, ei URL-osoitteita.
* Dropboxissa tai Google Drivessa voit jakaa tiedoston tai kansion.

## <a name="helpful-links"></a>Hyödyllisiä linkkejä
Kaikki [käytettävissä olevat yhteydet](../connections-list.md).  
Lue, miten [lisäät yhteyksiä](../add-manage-connections.md) ja [tietolähteitä](../add-data-connection.md) sovelluksiisi.  
[Tutustu taulukkoihin ja tietueisiin](../working-with-tables.md), joiden tietolähteet ovat taulukkomuotoisia.  
Muita valikoimiin liittyviä resursseja ovat esimerkiksi [Kohdeluettelon näyttäminen](../add-gallery.md) ja [Kuvien ja tekstin näyttäminen valikoimassa](../show-images-text-gallery-sort-filter.md).

<!--Icon references-->
[boxicon]: ./media/cloud-storage-blob-connections/boxicon.png
[dropboxicon]: ./media/cloud-storage-blob-connections/dropboxicon.png
[googledriveicon]: ./media/cloud-storage-blob-connections/googledriveicon.png
[onedriveicon]: ./media/cloud-storage-blob-connections/onedriveicon.png
[onedriveforbusinessicon]: ./media/cloud-storage-blob-connections/onedriveforbusinessicon.png
