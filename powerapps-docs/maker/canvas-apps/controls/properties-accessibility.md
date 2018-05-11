---
title: Helppokäyttöominaisuudet | Microsoft Docs
description: Tietoja ominaisuuksista, kuten TabIndex ja työvaluvihje
documentationcenter: na
author: fikaradz
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: canvas
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: 94d15ff14ccd57ccc392eae47b6c10d6cec50bb1
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="accessibility-properties-in-powerapps"></a>PowerAppsin helppokäyttöominaisuudet
Ominaisuuksia, jotka on määritetty auttamaan toimintarajoitteisia ihmisiä käyttämään ohjausobjekteja.

### <a name="properties"></a>Ominaisuudet
**AccessibleLabel** – Näytönlukuohjelmien käyttämä selite. Jos kuvan, kuvakkeen tai muodon ohjausobjektin kohdalla on tyhjä arvo, ohjausobjekti piilotetaan näytönlukijalta ja sitä käsitellään muotoiluna.

**TabIndex** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

Oletusarvo on nolla, ja se määrittää oletusmuotoisen sarkainjärjestyksen ohjausobjektin XY-koordinaattien perusteella.  Jos asetuksiin määritetään nollaa korkeampi arvo, ohjausobjektin sarkain siirtyy kaikkien oletusarvoilla määritettyjen ohjausobjektien edelle.  Kun esimerkiksi TabIndex-arvolla 2 asetettua ohjausobjektia selataan, se edeltää ohjausobjektia, jonka TabIndex-arvo on 3 tai enemmän.

Huomaa, että Lomake- ja Valikoima - ohjausobjekti ja muut säilöt selaavat aina kaikki säilön elementit, ennen kuin siirtyvät säilön ulkopuolella oleviin ohjausobjekteihin.  Säilön sarkainjärjestys määräytyy alemman tason ohjausobjektin pienimmän TabIndex-arvon mukaan.

Jos TabIndex-arvoksi asetetaan -1, sarkainpääsy ohjausobjektiin estetään; jos arvoa käytetään kuvaan, kuvakkeeseen tai muotoon, kyseisestä elementistä tulee ei-interaktiivinen.
