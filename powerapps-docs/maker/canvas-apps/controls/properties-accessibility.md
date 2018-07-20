---
title: Helppokäyttöominaisuudet | Microsoft Docs
description: Tietoja ominaisuuksista, kuten TabIndex ja työvaluvihje
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/26/2017
ms.author: fikaradz
ms.openlocfilehash: 59cc231dfc461a2301de90a7a995ec2ec82790cb
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39022926"
---
# <a name="accessibility-properties-in-powerapps"></a>PowerAppsin helppokäyttöominaisuudet
Ominaisuuksia, jotka on määritetty auttamaan toimintarajoitteisia ihmisiä käyttämään ohjausobjekteja.

### <a name="properties"></a>Ominaisuudet
**AccessibleLabel** – Näytönlukuohjelmien käyttämä selite. Jos kuvan, kuvakkeen tai muodon ohjausobjektin kohdalla on tyhjä arvo, ohjausobjekti piilotetaan näytönlukijalta ja sitä käsitellään muotoiluna.

**TabIndex** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

Oletusarvo on nolla, ja se määrittää oletusmuotoisen sarkainjärjestyksen ohjausobjektin XY-koordinaattien perusteella.  Jos asetuksiin määritetään nollaa korkeampi arvo, ohjausobjektin sarkain siirtyy kaikkien oletusarvoilla määritettyjen ohjausobjektien edelle.  Kun esimerkiksi TabIndex-arvolla 2 asetettua ohjausobjektia selataan, se edeltää ohjausobjektia, jonka TabIndex-arvo on 3 tai enemmän.

Huomaa, että Lomake- ja Valikoima-ohjausobjekti ja muut säilöt selaavat aina kaikki säilön elementit, ennen kuin siirtyvät säilön ulkopuolella oleviin ohjausobjekteihin.  Säilön sarkainjärjestys määräytyy alemman tason ohjausobjektin pienimmän TabIndex-arvon mukaan.

Jos TabIndex-arvoksi asetetaan -1, sarkainpääsy ohjausobjektiin estetään; jos arvoa käytetään kuvaan, kuvakkeeseen tai muotoon, kyseisestä elementistä tulee ei-interaktiivinen.
