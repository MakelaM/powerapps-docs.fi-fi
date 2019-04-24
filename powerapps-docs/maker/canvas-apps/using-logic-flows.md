---
title: Käynnistä työnkulku pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Luo työnkulku, joka suorittaa yhden tai useamman tehtävän pohjaan perustuvassa sovelluksessa ilmenneen tapahtuman jälkeen, kuten käyttäjän painettua painiketta.
author: stepsic-microsoft-com
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 12/07/2018
ms.author: stepsic
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5439399a22b47fcf4195cf878208e0e0bd4e0764
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61532107"
---
# <a name="start-a-flow-in-a-canvas-app"></a>Käynnistä työnkulku pohjaan perustuvassa sovelluksessa

Microsoft Flow’n avulla voit luoda logiikan, joka suorittaa yhden tai useamman tehtävän, kun pohjaan perustuvassa sovelluksessa ilmenee tapahtuma. Voit esimerkiksi määrittää painikkeen siten, että kun käyttäjä valitsee sen, kohde luodaan SharePoint-luetteloon, sähköpostiviesti tai kokouspyyntö lähetetään, tiedosto lisätään pilveen tai jokaisen näistä. Voit määrittää minkä tahansa ohjausobjektin sovelluksessa aloittamaan työnkulun, joka jatkaa suorittamista, vaikka sulkisit PowerAppsin.

> [!NOTE]
> Kun käyttäjä suorittaa työnkulku sovellukseen, että käyttäjällä on oltava oikeuksia suorittaa tehtäviä, jotka on määritetty työnkulussa. Muussa tapauksessa työnkulku epäonnistuu.

## <a name="prerequisites"></a>Edellytykset

- [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin.
- Lue, miten [ohjausobjekti määritetään](add-configure-controls.md).

## <a name="create-a-flow"></a>Työnkulun luominen

1. Kirjaudu sisään [PowerAppsiin](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

1. Valitse vasemmassa siirtymispalkissa **liiketoimintalogiikkaa**, ja valitse sitten **työnkulut**.

1. Vasemmassa yläkulmassa **omat työnkulut** sivulla **uusi**, ja valitse sitten **Luo tyhjästä**.

    ![Vaihtoehto työnkulun luomiseen ilman mallia](./media/using-logic-flows/create-from-blank.png)

1. Valitse näkyviin tulevan sivun alareunan **Hae sadoista yhteyksiä ja käynnistimet**.

1. Kirjoita hakuruutuun **Powerappsin**, ja valitse sitten **Powerappsin** kuvake.

    ![PowerApps-käynnistimen](./media/using-logic-flows/set-trigger.png)
    
1. Seuraavalla sivulla, valitse PowerApps-kuvake uudelleen ja valitse sitten **uusi vaihe**.

1. Boxissa, jossa lukee **Hae liittimet ja toiminnot**, Määritä toiminto työnkululle tämän esimerkin mukaisesti:

   1. Tyyppi **SharePoint** ruutuun ja valitse sitten **Luo kohde** alla olevaa **toiminnot**.

       ![SharePoint-kohteen luontivaihtoehto](./media/using-logic-flows/create-sharepoint-item.png)

   1. Jos näyttöön tulee kehote, anna tunnistetiedot yhteyden muodostamiseksi SharePointiin.

   1. Kirjoita tai liitä luettelon sisältävän SharePoint Online -sivuston URL-osoite **Sivuston osoite** -ruutuun.

       > [!NOTE]
       > Luettelon nimi ei liitetään URL-osoite.

   1. Tässä **Luettelonimi** ruutuun, Määritä luettelo, jota haluat käyttää.
   
       ![Määritä luettelo](./media/using-logic-flows/list-fields.png)

   1. Valitse tekstisyötteen ruutu kentän luetteloon (kuten **otsikko**), valitse **Näytä lisää** dynaamisen sisällön ruudussa ja valitse sitten **Kysy powerappsissa**. 

       ![Lisää Otsikko-kenttään Kysy PowerAppsissa -parametri](./media/using-logic-flows/ask-in-powerapps.png)

1. (valinnainen) Määritä vähintään yksi lisätoimia, kuten hyväksymissähköpostin lähettäminen määrittämääsi osoitteeseen tai liittyvän tapahtuman luominen toiseen tietolähteeseen.

1. Vasemman yläkulman alueelta, kirjoita tai liitä työnkulun nimi ja valitse sitten **Tallenna** oikeassa yläkulmassa.

## <a name="add-a-flow-to-an-app"></a>Lisää työnkulku sovellukseen
1. Valitse vasemmassa siirtymispalkissa **Luo**.

1. Osoita **pohjaan perustuva sovellus tyhjästä** ruudun ja valitse sitten **Tee tämä sovellus**.

1. Lisää **[Tekstisyöte](controls/control-text-input.md)**-ohjausobjekti ja anna sille nimi **RecordTitle**.

1. Lisää **[Painike](controls/control-button.md)**-ohjausobjekti ja siirrä se ohjausobjektin **RecordTitle** alle.

1. Kun **[Painike](controls/control-button.md)**-ohjausobjekti on valittuna, valitse **Toiminnot**-välilehdestä **Työnkulut**.

    ![Työnkulut-valinta Toiminto-välilehdessä](./media/using-logic-flows/action-tab.png)

1. Valitse avautuvassa ruudussa työnkulku, jonka loit edellisessä toimenpiteessä.

    > [!NOTE]
   > Jos luomasi työnkulku ei ole käytettävissä, vahvista onko PowerApps määritetty ympäristöön, jossa loit työnkulun.

    ![Lisää työnkulku mukautusruudusta](./media/using-logic-flows/add-flow-from-pane.png)

1. Kirjoita tai liitä kaavariville **RecordTitle.Text)** automaattisesti lisätyn kaavan loppuun.

    ![OnSelect-ominaisuus, joka sisältää työnkulun](./media/using-logic-flows/onselect-with-flow.png)

## <a name="test-the-flow"></a>Testaa työnkulku
1. Kaksoisnapsauta **Tekstisyöte** ohjausobjektissa ja kirjoita tai liitä se tekstiä.

1. Pidät Alt-näppäintä ja valitse **[painike](controls/control-button.md)** ohjausobjektin.

    SharePoint-kohde on luotu määrittämääsi luetteloon tekstillä määritit otsikoksi. Jos luettelo oli avoinna, kun työnkulku suoritettiin, saatat joutua päivittämään selainikkunan, jotta muutokset tulevat näkyviin.
