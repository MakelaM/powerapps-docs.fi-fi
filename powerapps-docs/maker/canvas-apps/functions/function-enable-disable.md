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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f3932d21683b83008e95f03ba2aae646d2b8e491
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551073"
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

