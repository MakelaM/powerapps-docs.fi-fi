---
title: Yhteyden muodostaminen pohjaan perustuvasta sovelluksesta SharePointiin | Microsoft Docs
description: Muodosta PowerAppsissa yhteys SharePointiin pohjaan perustuvan sovelluksen automaattista luontia varten tai luomiseen alusta alkaen.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 09/03/2016
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 170115f07da57878c553a1776fc26a9cd27a8258
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42844151"
---
# <a name="create-a-connection-to-sharepoint-from-powerapps"></a>Yhteyden luominen PowerAppsista SharePointiin
Luo yhteys joko SharePoint Onlineen tai paikalliseen SharePointiin, jotta voit luoda pohjaan perustuvan sovelluksen automaattisesti tai alusta alkaen.

Jos et tunne PowerAppsia, katso [PowerAppsin esittely](getting-started.md).

Kirjoittamishetkellä PowerApps tukee mukautettuja luetteloita, mutta ei kirjastoja. Lisäksi voit näyttää joitain tietotyyppejä sarakkeissa, kuten **Valinta** ja **Kuva**, mutta et voi päivittää kyseisiä tietoja. Katso lisätietoja kohdasta [Tunnetut ongelmat](connections/connection-sharepoint-online.md#known-issues).

## <a name="specify-a-sharepoint-connection"></a>SharePoint-yhteyden määrittäminen
1. Jos et ole vielä rekisteröitynyt, [rekisteröidy PowerAppsiin](../signup-for-powerapps.md).

2. Kirjaudu sisään osoitteeseen [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joilla rekisteröidyit.

3. Napsauta tai napauta vasemman siirtymispalkin kohtaa **Hallitse** ja napsauta tai napauta kohtaa **Yhteydet**.

    ![Tiedosto-valikon Uusi-vaihtoehto](./media/connect-to-sharepoint/manage-connections.png)

4. Napsauta tai napauta oikean yläkulman lähellä olevaa kohtaa **Uusi yhteys**.

    ![Uusi yhteys -painike](./media/connect-to-sharepoint/new-connection.png)

5. Napsauta tai napauta yhteysluettelosta kohtaa **SharePoint**.

    ![SharePoint-yhteyden lisääminen](./media/connect-to-sharepoint/add-sp-portal.png)

6. Noudata jommankumman tässä aiheessa esitetyn prosessin vaiheita:

   * [Yhdistäminen SharePoint Online -sivustoon](connect-to-sharepoint.md#connect-to-a-sharepoint-online-site).
   * [Yhdistäminen paikalliseen SharePoint -sivustoon](connect-to-sharepoint.md#connect-to-an-on-premises-sharepoint-site).

## <a name="connect-to-a-sharepoint-online-site"></a>Yhdistäminen SharePoint Online -sivustoon
1. Napsauta tai napauta kohtaa **Yhdistä suoraan (pilvipalvelut)** ja napsauta tai napauta **Lisää yhteys**.

    ![Valitse SharePoint Online](./media/connect-to-sharepoint/choose-online.png)

2. Siirry tämän aiheen lopussa olevaan kohtaan [Seuraavat vaiheet](connect-to-sharepoint.md#next-steps).

## <a name="connect-to-an-on-premises-sharepoint-site"></a>Yhdistäminen paikalliseen SharePoint -sivustoon
1. Napsauta tai napauta kohtaa **Yhdistä käyttäen paikallista tietoyhdyskäytävää**.

    ![Valitse SharePoint (paikallinen)](./media/connect-to-sharepoint/choose-onprem.png)

    > [!NOTE]
   > Yhdyskäytäviä ja paikallisia yhteyksiä voi luoda ja käyttää vain käyttäjän [oletusympäristössä](working-with-environments.md).

2. Anna käyttäjänimesi ja salasanasi.

    Jos tunnistetietoihisi kuuluu toimialuenimi, anna käyttäjänimi muodossa *Toimialue\Alias*.

    ![Tunnistetietojen määritys](./media/connect-to-sharepoint/specify-credentials.png)

3. Jos sinulla ei ole asennettuna paikallista tietoyhdyskäytävää, [asenna sellainen](gateway-reference.md) ja päivitä yhdyskäytäväluettelo napsauttamalla tai napauttamalla päivityskuvaketta.

    ![Yhdyskäytävän asentaminen](./media/connect-to-sharepoint/install-gateway.png)

4. Napsauta tai napauta kohdan **Valitse yhdyskäytävä** alla yhdyskäytävää, jota haluat käyttää, ja napsauta tai napauta **Lisää yhteys**.

    ![Yhdyskäytävän valinta](./media/connect-to-sharepoint/choose-gateway.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Luo sovellus automaattisesti](app-from-sharepoint.md) määrittämäsi luettelon perusteella. Sovelluksessa on oletuksena kolme näyttöä: yksi tietueiden selaamiseen, yksi yhden tietueen tietojen näyttämiseen ja yksi tietueen luomiseen tai päivittämiseen.
* [Sovelluksen luominen alusta alkaen](get-started-create-from-blank.md). Tämä aihe on kirjoitettu Excelille, mutta samat periaatteet pätevät SharePointiin.
