---
title: Enable- ja Disable-funktiot | Microsoft Docs
description: PowerAppsin Enable- ja Disable-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 1b5395459dd5833d054755dadca37bc9b39785c9
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39019062"
---
# <a name="enable-and-disable-functions-in-powerapps"></a>PowerAppsin Enable- ja Disable-funktiot
Kytkevät [signaalin](signals.md) päälle tai pois.

## <a name="overview"></a>Yleiskatsaus
Jotkin signaalit muuttuvat usein, jolloin sovelluksen täytyy suorittaa uusia laskutoimituksia.  Nopeat muutokset pitkällä aikavälillä voivat kuluttaa paljon laitteen akkua. Voit käyttää näitä funktioita signaalin manuaaliseen kytkemiseen päälle tai pois.

Kun signaalia ei käytetä, se kytketään automaattisesti pois päältä.

## <a name="description"></a>Kuvaus
**Enable**- ja **Disable**-funktiot kytkevät signaalin päälle tai pois, tässä järjestyksessä.

Nämä funktiot toimivat tällä hetkellä vain **[Sijainti](signals.md)**-signaalin kanssa.

Funktioilla ei ole paluuarvoa. Niitä voidaan käyttää vain [toimintakaavoissa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Enable**( *Signal* )<br>**Disable**( *Signal* )

* *Signal* – Pakollinen.  Päälle tai pois kytkettävä signaali.

