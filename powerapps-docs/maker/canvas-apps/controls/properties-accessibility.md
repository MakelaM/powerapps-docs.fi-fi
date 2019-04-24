---
title: Helppokäyttötoimintojen ominaisuudet pohjaan perustuvien sovellusten | Microsoft Docs
description: Tietoja ominaisuuksista, kuten TabIndex ja työkaluvihje
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 01/26/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5fa8b6fecdf690114cbf6a0945f2dfec66b067c3
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61560411"
---
# <a name="accessibility-properties-for-canvas-apps"></a>Pohjaan perustuvat sovellukset Helppokäyttöisyysasetukset

Ominaisuuksia, jotka on määritetty auttamaan toimintarajoitteisia ihmisiä käyttämään ohjausobjekteja.

## <a name="properties"></a>Ominaisuudet

**AccessibleLabel** – Näytönlukuohjelmien käyttämä selite. Jos kuvan, kuvakkeen tai muodon ohjausobjektin kohdalla on tyhjä arvo, ohjausobjekti piilotetaan näytönlukijalta ja sitä käsitellään muotoiluna.

**Live** – miten näytönlukuohjelmat tulee ilmoittavat sisällön muutokset. Käytettävissä vain **[nimen](control-text-box.md)** ohjausobjektin.

* Kun **käytöstä**, näytönlukuohjelma ei muutoksia.
* Kun **Polite**, näytönlukuohjelma on valmis, ennen kuin muutokset, joka suoritettaessa näytönlukuohjelma oli puhumalla esittelyssä puhumalla.
* Kun **Assertive**, näytönlukuohjelma keskeyttää itse koskevista muutoksista, joka suoritettaessa näytönlukuohjelma oli puhumalla.

Lue, miten [ilmoittavat dynaamisia muutoksia live-alueiden kanssa](../accessible-apps-live-regions.md).

**TabIndex** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

Oletusarvo on nolla, ja se määrittää oletusmuotoisen sarkainjärjestyksen ohjausobjektin XY-koordinaattien perusteella.  Jos asetuksiin määritetään nollaa korkeampi arvo, ohjausobjektin sarkain siirtyy kaikkien oletusarvoilla määritettyjen ohjausobjektien edelle.  Kun esimerkiksi TabIndex-arvolla 2 asetettua ohjausobjektia selataan, se edeltää ohjausobjektia, jonka TabIndex-arvo on 3 tai enemmän.

Huomaa, että Lomake- ja Valikoima-ohjausobjekti ja muut säilöt selaavat aina kaikki säilön elementit, ennen kuin siirtyvät säilön ulkopuolella oleviin ohjausobjekteihin.  Säilön sarkainjärjestys määräytyy alemman tason ohjausobjektin pienimmän TabIndex-arvon mukaan.

Jos TabIndex-arvoksi asetetaan -1, sarkainpääsy ohjausobjektiin estetään; jos arvoa käytetään kuvaan, kuvakkeeseen tai muotoon, kyseisestä elementistä tulee ei-interaktiivinen.
