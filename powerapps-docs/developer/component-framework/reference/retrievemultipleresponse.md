---
title: Retrievemultikeresponse | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 08ea66d3-b4af-44af-a3ae-cb2ebad043e8
ms.openlocfilehash: 0e5b2cad047bcf91b0c63e27c4a7ceb35c1ed538
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72341307"
---
# <a name="retrievemultipleresponse"></a>Retrievemultikeresponse

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="properties"></a>Ominaisuudet

### <a name="entities"></a>entiteetit

JSON-objektien matriisi, jossa kukin objekti edustaa noudetun entiteettitietueen, joka sisältää määritteitä ja niiden arvoja.

**Tyyppi**: `Entity[]`

### <a name="nextlink"></a>nextLink

Jos noudettavien tietueiden määrä on suurempi kuin pyynnön `maxPageSize`-parametrissa määritetty arvo, tämä määrite palauttaa URL-osoitteen, joka palauttaa seuraavan tietue joukon.

**Tyyppi**: `string`


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[PowerApps Component Framework-ohjelmointi raja pinnan viite](../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../overview.md)