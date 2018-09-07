---
title: Kuvien lisääminen Exceliin | Microsoft Docs
description: Vaiheittaiset ohjeet kuvatiedostojen ja kynäpiirustusten lisäämiseen Exceliin pilvipalvelutilillä
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/25/2016
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 89b05b5e1e8073b082e73564f744b7b85fc70426
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42863938"
---
# <a name="add-images-to-excel-from-powerapps"></a>Kuvien lisääminen PowerAppsista Exceliin
Luo automaattisesti sovellus, jossa käyttäjät voivat näyttää, lisätä tai poistaa kuvia tiedostoista tai piirustuksia **Kynä**-ohjausobjektista. Sovellus perustuu Excel-tiedostoon, joka luodaan ja ladataan pilvipalvelutilille.

## <a name="prerequisites"></a>Edellytykset

* Käyttäjä tuntee [ohjausobjektien lisäämisen ja määrittämisen](add-configure-controls.md).
* Käyttäjä tuntee [Excel-tietojen määrittämisen taulukoksi](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370?ui=en-US&rs=en-US&ad=US).
* [PowerApps-yhteys](add-data-connection.md) pilvitallennustiliin (kuten Dropbox, OneDrive tai Google Drive), jossa voit säilyttää Excel-tiedostoa.

## <a name="create-the-data-source-and-the-app"></a>Tietolähteen ja sovelluksen luominen
1. Lisää **Kuvateksti** ja **Kuva [kuva]** kahteen tyhjään Excel-soluun, jotka ovat vierekkäin (esimerkiksi A1 ja B1) ja joiden alla on kaksi tyhjää solua.
2. Muotoile päivittämäsi solut ja niiden alla olevat solut taulukoksi ja anna taulukolle nimi (esimerkiksi **Kuvat**).
   
    ![Taulukon luominen](./media/add-images-to-excel/create-table.png)
3. Tallenna tiedosto (esimerkiksi nimellä **ImageDemo**) ja lataa se pilvitallennustilillesi.
4. Napsauta tai napauta **Uusi** PowerAppsin **Tiedosto**-valikossa (vasemmassa reunassa, jos et ole vielä avannut sovellusta) ja valitse sitten pilvitallennustilisi ruudusta **Puhelinasettelu**.
   
    ![Valitse pilvitallennustilisi](./media/add-images-to-excel/select-account.png)
5. Napsauta luomaasi tiedostoa kohdassa **Valitse Excel-tiedosto**.
   
    ![Valitse työkirjasi](./media/add-images-to-excel/select-workbook.png)
6. Napsauta tai napauta luomaasi taulukkoa kohdassa **Valitse taulukko** ja valitse sitten **Yhdistä**.
   
    ![Valitse taulukkosi](./media/add-images-to-excel/select-table.png)
7. Jos pikaesittely tulee näkyviin, katso se tai napsauta tai napauta **Ohita**.
   
    ![Pikaesittelyn ensimmäinen näyttö](./media/add-images-to-excel/quick-tour.png)

## <a name="add-an-image-from-a-file"></a>Kuvan lisääminen tiedostosta
1. Avaa esikatselutila painamalla F5 (tai napsauttamalla tai napauttamalla lähellä oikeaa yläkulmaa olevaa toista-painiketta) ja napsauta tai napauta oikeassa yläkulmassa olevaa plus-kuvaketta.
   
    ![Plus-kuvake](./media/add-images-to-excel/plus-icon.png)
2. Valitse **Kuvateksti**-ruutu, kirjoita tai liitä lyhyt kuvaus kuvatiedostosta, jonka haluat lisätä ja määritä tiedosto napsauttamalla tai napauttamalla alla olevaa kuvaa.
3. Etsi **Avaa**-valintaikkunasta tiedosto, jonka haluat lisätä, napsauta tai napauta sitä ja valitse sitten **Avaa**.
   
    ![Lisää kuvateksti ja kuva](./media/add-images-to-excel/add-image.png)
4. Tallenna muutokset napsauttamalla tai napauttamalla oikeassa yläkulmassa olevaa valintamerkkikuvaketta.
   
    ![Muutosten tallentaminen](./media/add-images-to-excel/checkmark-icon.png)
5. Voit lisätä niin monta kuvaa kuin haluat toistamalla viimeiset kolme vaihetta. Palaa oletustyötilaan painamalla Esc.
6. (valinnainen) Poista toinen **Selite**-ohjausobjekteista, jotka näyttävät kuvan kuvatekstin.

## <a name="add-a-drawing"></a>Piirustuksen lisääminen
1. Avaa **EditScreen1** napsauttamalla tai napauttamalla sitä vasemmassa siirtymispalkissa ja valitse kuvakortti napsauttamalla tai napauttamalla sitä.
   
    ![Valitse kuvakortti](./media/add-images-to-excel/select-card.png)
2. Napsauta tai napauta kuvakortin kortinvalitsinta oikeanpuoleisessa ruudussa ja napsauta tai napauta sitten **Lisää huomautuksia**.
   
    ![Lisää huomautuksia](./media/add-images-to-excel/add-notes.png)
3. Avaa **BrowseScreen1** napsauttamalla tai napauttamalla sitä vasemmassa siirtymispalkissa ja avaa esikatselutila.
4. Lisää kuvateksti ja piirrä kuva **Kynä**-ohjausobjektilla napsauttamalla tai napauttamalla oikeassa yläkulmassa olevaa plus-kuvaketta.
   
    ![Piirrä kuva](./media/add-images-to-excel/draw-picture.png)
5. Tallenna muutokset napsauttamalla tai napauttamalla oikeassa yläkulmassa olevaa valintamerkkikuvaketta.
   
    ![Muutosten tallentaminen](./media/add-images-to-excel/checkmark-icon.png)
6. Voit lisätä niin monta kuvaa kuin haluat toistamalla viimeiset kaksi vaihetta. Palaa oletustyötilaan painamalla Esc.

