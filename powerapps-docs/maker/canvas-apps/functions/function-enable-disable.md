---
title: Enable- ja Disable-funktiot | Microsoft Docs
description: PowerAppsin Enable- ja Disable-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2015
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1b58b57ae880f54fc7fccb5aa4c49f0e2fcad6d0
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992774"
---
# <a name="enable-and-disable-functions-in-powerapps"></a>PowerAppsin Enable- ja Disable-funktiot
Kytkevät [signaalin](signals.md) päälle tai pois.

## <a name="overview"></a>Yleiskatsaus
Jotkin signaalit muuttuvat usein, jolloin sovelluksen täytyy suorittaa uusia laskutoimituksia.  Nopeat muutokset pitkällä aikavälillä voivat kuluttaa paljon laitteen akkua. Voit käyttää näitä funktioita signaalin manuaaliseen kytkemiseen päälle tai pois.

Kun signaalia ei käytetä, se kytketään automaattisesti pois päältä.

## <a name="description"></a>Kuvaus
**Enable**- ja **Disable**-funktiot kytkevät signaalin päälle tai pois, tässä järjestyksessä.

Nämä funktiot toimivat tällä hetkellä vain **[Sijainti](signals.md)** -signaalin kanssa.

Funktioilla ei ole paluuarvoa. Niitä voidaan käyttää vain [toimintakaavoissa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Enable**( *Signal* )<br>**Disable**( *Signal* )

* *Signal* – Pakollinen.  Päälle tai pois kytkettävä signaali.

