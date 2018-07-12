---
title: Käynnistä työnkulku sovelluksessa | Microsoft Docs
description: Luo työnkulku, joka suorittaa yhden tai useamman tehtävän sovelluksessa ilmenneen tapahtuman jälkeen, kuten käyttäjän painettua painiketta.
documentationcenter: ''
author: stepsic-microsoft-com
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 06/05/2017
ms.author: sharik
ms.openlocfilehash: 7079dc6194361cc700ccaad6c02ca0bcf8a9f9d6
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37895910"
---
# <a name="start-a-flow-in-an-app"></a>Käynnistä työnkulku sovelluksessa
Microsoft Flow’n avulla voit luoda logiikan, joka suorittaa yhden tai useamman tehtävän, kun sovelluksessa ilmenee tapahtuma. Voit esimerkiksi määrittää painikkeen siten, että kun käyttäjä valitsee sen, kohde luodaan SharePoint-luetteloon, sähköpostiviesti tai kokouspyyntö lähetetään, tiedosto lisätään pilveen tai jokaisen näistä. Voit määrittää minkä tahansa ohjausobjektin sovelluksessa aloittamaan työnkulun, joka jatkaa suorittamista, vaikka sulkisit PowerAppsin.

## <a name="prerequisites"></a>Edellytykset

* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin.
* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md).

## <a name="create-a-flow"></a>Luo työnkulku
1. Kirjaudu [powerapps.com](http://web.powerapps.com):iin ja valitse sitten vasemmassa siirtymispalkissa **Työnkulut**.

2. Valitse **Omat työnkulut** -sivulla **Luo tyhjästä**.

    ![Vaihtoehto työnkulun luomiseen ilman mallia](./media/using-logic-flows/create-from-blank.png)

    **PowerApps** lisätään oletusarvoisena käynnistimenä.

    ![PowerApps käynnistimenä, joka käynnistää työnkulun](./media/using-logic-flows/set-trigger.png)

3. Valitse **Uusi vaihe** ja valitse sitten **Lisää toiminto**.

    ![Toiminnon lisäämisvaihtoehto](./media/using-logic-flows/add-action.png)

4. Määritä toiminto työnkululle ruudussa, jossa lukee **Hae kaikki palvelut ja toiminnot**, kuten tässä esimerkissä:

   1. Kirjoita valintaruutuun **SharePoint** ja valitse sitten kohdassa **Toiminnot** olevasta luettelosta **SharePoint – Luo kohde**.

       ![SharePoint-kohteen luontivaihtoehto](./media/using-logic-flows/create-sharepoint-item.png)

   2. Jos näyttöön tulee kehote, anna tunnistetiedot yhteyden muodostamiseksi SharePointiin.

   3. Kirjoita tai liitä luettelon sisältävän SharePoint Online -sivuston URL-osoite **Sivuston osoite** -ruutuun.

       > [!NOTE]
      > Määritä sivuston URL-osoite, joka ei sisällä luetteloa.

   4. Valitse **Luettelon nimi** -ruudusta luettelo, jota haluat käyttää.

   5. Napsauta tai napauta **Otsikko**-ruutua ja valitse sitten **Lisää dynaaminen sisältö**.

       ![Lisää Otsikko-kenttään Kysy PowerAppsissa -parametri](./media/using-logic-flows/ask-in-powerapps.png)

   6. Valitse parametrien luettelossa **Kysy PowerAppsissa**.

       ![Lisää parametri](./media/using-logic-flows/add-parameter.png)

5. (valinnainen) Määritä vähintään yksi lisätoiminto, kuten hyväksymissähköpostin lähettäminen määrittämääsi osoitteeseen tai liittyvän tapahtuman luominen toiseen tietolähteeseen.

6. Kirjoita tai liitä työnkulun nimi kohtaan näytön yläreunan lähellä ja valitse sitten **Luo työnkulku**.

    ![Nimeä ja tallenna työnkulku](./media/using-logic-flows/name-flow.png)

## <a name="add-a-flow-to-an-app"></a>Lisää työnkulku sovellukseen
1. Valitse PowerAppsissa **Tiedosto**-valikosta **Uusi**.

2. Valitse **Tyhjä sovellus** -ruudusta **Puhelinasettelu**.

3. Lisää **[Tekstisyöte](controls/control-text-input.md)**-ohjausobjekti ja anna sille nimi **RecordTitle**.

4. Lisää **[Painike](controls/control-button.md)**-ohjausobjekti ja siirrä se ohjausobjektin **RecordTitle** alle.

5. Kun **[Painike](controls/control-button.md)**-ohjausobjekti on valittuna, valitse **Toiminnot**-välilehdestä **Työnkulut**.

    ![Työnkulut-valinta Toiminto-välilehdessä](./media/using-logic-flows/action-tab.png)

6. Valitse avautuvassa ruudussa työnkulku, jonka loit edellisessä toimenpiteessä.

    > [!NOTE]
   > Jos luomasi työnkulku ei ole käytettävissä, vahvista onko PowerApps määritetty ympäristöön, jossa loit työnkulun.

    ![Lisää työnkulku mukautusruudusta](./media/using-logic-flows/add-flow-from-pane.png)

7. Kirjoita tai liitä kaavariville **RecordTitle.Text)** automaattisesti lisätyn kaavan loppuun.

    ![OnSelect-ominaisuus, joka sisältää työnkulun](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>Testaa työnkulku
1. Avaa esikatselu painamalla F5 (tai valitsemalla nuoli oikean yläkulman läheltä).

    ![OnSelect-ominaisuus, joka sisältää työnkulun](./media/using-logic-flows/open-preview.png)

2. Kirjoita tai liitä tekstiä kohtaan **RecordTitle** ja napsauta tai napauta sitten **[Painike](controls/control-button.md)**-ohjausobjektia.

    SharePoint-kohde luodaan määrittämääsi luetteloon tekstillä, jonka määritit otsikoksi. Jos luettelo oli avoinna, kun työnkulku suoritettiin, saatat joutua päivittämään selainikkunan, jotta muutokset tulevat näkyviin.
