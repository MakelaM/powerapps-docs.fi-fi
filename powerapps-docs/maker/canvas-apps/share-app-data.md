---
title: Sovelluksen käyttämien Excel-tiedostojen jakaminen | Microsoft Docs
description: Excel-tiedostojen jakaminen Dropboxissa, OneDrivessa ja Google Drivessa. Käyttäjät voivat muokata ja tarkastella tiedostoja ja kansioita.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/16/2016
ms.author: jamesol
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3348db5897b0c58d7addef775d2a871809fc491b
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995211"
---
# <a name="share-excel-data-used-by-your-app"></a>Sovelluksesi käyttämien Excel-tietojen jakaminen
Voit jakaa Excel-tietoja sovelluksesi käyttäjien kanssa [pilvipalvelussa](connections/cloud-storage-blob-connections.md), kuten Onedrivessa.

Voit esimerkiksi luoda sovelluksen, joka näyttää yrityksesi teknisen tukiryhmän nimet ja puhelinnumerot. Tiedot on tallennettu Excel-laskentataulukkoon, jonka tallennat Dropboxissa olevaan kansioon. Sen jälkeen voit jakaa tämän kansion sovelluksen käyttäjien kanssa niin, että he voivat nähdä nimet ja puhelinnumerot.

Sinun täytyy jakaa tiedot niin, että käyttäjät voivat suorittaa ja jopa muokata sovellustasi. Käyttäjät, joilla ei ole annettu jakamisoikeuksia, eivät näe Excel-tiedoston tietoja.

Tässä ohjeaiheessa kerrotaan, miten voit jakaa Excel-laskentataulukossa olevia tietoja Dropboxissa, OneDrivessa ja Google Drivessa. Kun haluat luoda sovelluksen, joka näyttää tietoja Excel-tiedostosta, katso lisätietoja kohdasta [Sovelluksen luominen tietojoukosta](get-started-create-from-data.md).

## <a name="share-data-in-dropbox"></a>Tietojen jakaminen Dropboxissa
1. Kirjaudu sisään Dropboxiin käyttämällä samaa tiliä, jota käytit luodessasi yhteyden PowerAppsista Dropboxiin.
2. Valitse Excel-tiedoston sisältävä kansio ja valitse sitten **Jaa**:  
   
    ![Jaa-komento](./media/share-app-data/dropbox-share.png)
3. Kirjoita valintaikkunaan sähköpostiosoitteet, joilla sovelluksesi käyttäjät kirjautuvat Dropboxiin.  
   
    ![Jakaminen Dropboxissa](./media/share-app-data/dropbox-perms.png)
4. Jos sovelluksesi käyttäjät lisäävät, muokkaavat tai poistavat sovelluksesi tietoja, valitse **voit muokata**. Muussa tapauksessa valitse **voit tarkastella**.
5. Valitse **Jaa**.

Lisätietoja on kohdassa [Dropbox-kansioiden jakaminen](https://www.dropbox.com/en/help/19).

## <a name="share-data-in-onedrive"></a>Tietojen jakaminen OneDrivessa
1. Kirjaudu sisään OneDriveen käyttämällä samaa tiliä, jota käytit luodessasi yhteyden PowerAppsista OneDriveen.
2. Valitse tiedoston sisältävä kansio ja valitse sitten **Jaa**:  
   
    ![Jaa-komento](./media/share-app-data/onedrive-share.png)
   
    > [!NOTE]
   > OneDrive for Businessissa jaetaan itse tiedosto, ei tiedoston sisältävää kansiota.
3. Valitse valintaikkunassa **sähköpostin**.
   
    ![Jakaminen sähköpostitse](./media/share-app-data/onedrive-email.png)
4. Määritä sähköpostiosoitteet, joilla sovelluksesi käyttäjät kirjautuvat OneDriveen, ja valitse sitten **Jaa**.  
   
    ![Käyttäjän määrittäminen](./media/share-app-data/onedrive-perms.png)

Lisätietoja on artikkelissa [OneDrive-tiedostojen ja -kansioiden jakaminen](https://support.office.com/article/Share-OneDrive-files-and-folders-and-change-permissions-9fcc2f7d-de0c-4cec-93b0-a82024800c07).

## <a name="share-data-in-google-drive"></a>Tietojen jakaminen Google Drivessa
1. Kirjaudu sisään Google Driveen käyttämällä samaa tiliä, jota käytit luodessasi yhteyden PowerAppsista Google Driveen.
2. Napsauta Excel-tiedoston sisältävää kansiota hiiren kakkospainikkeella ja valitse sitten **Jaa**.  
   
    ![Jaa-komento](./media/share-app-data/googledrive-share.png)
3. Kirjoita valintaikkunaan sähköpostiosoitteet, joilla sovelluksesi käyttäjät kirjautuvat Google Driveen:  
   
    ![Käyttäjän määrittäminen](./media/share-app-data/googledrive-perms.png)
4. Jos sovelluksesi käyttäjät lisäävät, muokkaavat tai poistavat sovelluksesi tietoja, valitse käyttöoikeusluettelon vaihtoehto **voit muokata**. Muussa tapauksessa valitse **voit tarkastella**.
5. Valitse **Valmis**.

Lisätietoja on artikkelissa [Google Drive -tiedostojen ja -kansioiden jakaminen](https://support.google.com/drive/answer/2494822).

### <a name="known-limitations"></a>Tunnetut rajoitukset
[Tutustu näihin rajoituksiin](connections/cloud-storage-blob-connections.md#known-limitations), niin saat lisätietoja siitä, miten voit jakaa Excel-tietoja organisaatiossasi.

