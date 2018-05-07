---
title: Enable- ja Disable-funktiot | Microsoft Docs
description: Powerappsin Enable- ja Disable-funktioiden viitetiedot, mukaan lukien syntaksi ja esimerkit
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 11/07/2015
ms.author: gregli
ms.openlocfilehash: 3b9801e804284cb52d389aa0c57d1247a008dd0d
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="enable-and-disable-functions-in-powerapps"></a>PowerAppsin Enable- ja Disable-funktiot
Kytkee [signaalin](signals.md) päälle tai pois.

## <a name="overview"></a>Yleiskatsaus
Jotkin signaalit muuttuvat usein, jolloin sovelluksen täytyy suorittaa uusia laskutoimituksia.  Nopeat muutokset pitkällä aikavälillä voivat kuluttaa paljon laitteen akkua. Voit käyttää näitä funktioita signaalin manuaaliseen kytkemiseen päälle tai pois.

Kun signaalia ei käytetä, se kytketään automaattisesti pois päältä.

## <a name="description"></a>Kuvaus
**Enable**- ja **Disable**-funktiot kytkevät signaalin päälle tai pois tässä järjestyksessä.

Nämä funktiot toimivat tällä hetkellä vain **[Sijainti](signals.md)**-signaalin kanssa.

Funktioilla ei ole paluuarvoa. Niitä voidaan käyttää vain [toimintakaavoissa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Enable**( *Signaali* )<br>**Disable**( *Signaali* )

* *Signaali* - Pakollinen.  Päälle tai pois kytkettävä signaali.

