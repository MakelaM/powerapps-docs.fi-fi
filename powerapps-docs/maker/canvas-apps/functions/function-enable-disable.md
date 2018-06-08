---
title: Enable- ja Disable-funktiot | Microsoft Docs
description: PowerAppsin Enable- ja Disable-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: b35d819730715917f3092ca803b9a38ea9173edc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825115"
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

