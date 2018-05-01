---
title: Pikaopas mukautetun entiteetin poistamiseen ja tietojen poistamiseen | Microsoft Docs
description: Pikaopas mukautetun entiteetin poistamiseen ja kaikkien tietojen poistamiseen
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 399d3e8bac215df7612ac12d922dfe644dc59f96
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-delete-a-custom-entity"></a>Pikaopas: Mukautetun kohteen poistaminen
Voit poistaa mukautettuja entiteettejä mutta et vakioentiteettejä.

1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

    ![Entiteetin tiedot] ja (./media/data-platform-cds-create-entity/entitylist.png "entiteettiluettelo")

2. Napsauta tai napauta entiteettiluettelossa olevaa poistettavaa entiteettiä ja napsauta tai napauta sitten komentopalkin kohtaa **Poista entiteetti**.
3. Poista entiteetti napsauttamalla tai napauttamalla esiin tulevassa valintaikkunassa kohtaa **Poista**.

>[!NOTE]
>Kun poistat entiteetin, poistat sekä entiteetin määritelmän että kaikki entiteetin sisältämät tiedot. Entiteettejä ja niissä olevia tietoja ei voi palauttaa, jos ne on poistettu.

>[!NOTE]
>Sovelluksen tai työnkulun toiminta saattaa häiriytyä, jos poistat entiteetin, jota tässä sovelluksessa käytetään.

>[!NOTE]
>Jos entiteetissä A on [hakukenttiä](data-platform-entity-lookup.md) entiteettiin B, sinun on ehkä poistettava entiteetti B, ennen kuin voit poistaa entiteetin A.

