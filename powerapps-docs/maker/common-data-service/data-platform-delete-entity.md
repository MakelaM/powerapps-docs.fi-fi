---
title: Mukautetun entiteetin poistaminen | Microsoft Docs
description: Vaiheittaiset ohjeet mukautetun entiteetin poistamiseen ja kaikkien PowerAppsin tietojen tyhjentämiseen
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
ms.openlocfilehash: b17da30916b06b5b76b16cc6bf9758b988549f6f
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218644"
---
# <a name="delete-a-custom-entity"></a>Poista mukautettu entiteetti
Voit poistaa mukautettuja entiteettejä, mutta et vakioentiteettejä.

1. Suurenna [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/entitylist.png "entiteettiluettelo")

2. Napsauta tai napauta entiteettiluettelossa olevaa poistettavaa entiteettiä ja napsauta tai napauta sitten komentopalkin kohtaa **Poista entiteetti**.

3. Poista entiteetti napsauttamalla tai napauttamalla esiin tulevassa valintaikkunassa kohtaa **Poista**.

>[!NOTE]
>Kun poistat entiteetin, poistat sekä entiteetin määritelmän että kaikki entiteetin sisältämät tiedot. Entiteettejä ja niissä olevia tietoja ei voi palauttaa, jos ne on poistettu.

>[!NOTE]
>Sovelluksen tai työnkulun toiminta saattaa häiriytyä, jos poistat entiteetin, jota tässä sovelluksessa käytetään.

>[!NOTE]
>Jos entiteetissä A on [hakukenttiä](data-platform-entity-lookup.md) entiteettiin B, sinun on ehkä poistettava entiteetti B, ennen kuin voit poistaa entiteetin A.

