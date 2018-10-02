---
title: Mukautetun entiteetin poistaminen | Microsoft Docs
description: PowerAppsissa tapahtuvan mukautetun entiteetin poistamisen ja kaikkien tietojen tyhjentämisen vaiheittaiset ohjeet
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="delete-a-custom-entity"></a>Mukautetun kohteen poistaminen
Mukautettuja entiteettejä voi poistaa, mutta vakioentiteettejä ei.

1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Entiteetit**-kohtaa vasemmanpuoleisessa siirtymisruudussa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/entitylist.png "Entiteettiluettelo")

2. Napsauta tai napauta poistettavaa entiteettiä entiteettiluettelossa. Napsauta tai napauta sitten komentopalkin **Poista entiteetti** -asetusta.

3. Napsauta tai napauta näyttöön avautuvassa valintaikkunassa **Poista**, jolloin entiteetti poistetaan.

>[!NOTE]
>Kun poistat entiteetin, voit poistaa sekä entiteetin määrityksen että kaikki sen sisältämät tiedot. Entiteettejä ja niiden tietoja ei voi palauttaa poistamisen jälkeen.

>[!NOTE]
>Jos sovelluksessa käytössä oleva entiteetti poistetaan, sovellukseen tai työnkulkuun voi tulla toimintahäiriöitä.

>[!NOTE]
>Jos entiteetillä A on [valintakenttiä](data-platform-entity-lookup.md) entiteettiin B, ennen entiteetin A poistamista on ehkä poistettava entiteetti B.

