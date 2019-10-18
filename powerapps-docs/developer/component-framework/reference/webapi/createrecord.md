---
title: createRecord | Microsoft Docs
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
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 9179f03b-9d26-4253-9535-13ab544d58ac
ms.openlocfilehash: f3a2b860f17d7efaaf8efebcf2418aef04478947
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340824"
---
# <a name="createrecord"></a>createRecord

[!INCLUDE [createrecord-description](includes/createrecord-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.webAPI.createRecord(entityLogicalName, data).then(successCallback, errorCallback);`

## <a name="parameters"></a>Parametrit

<table style="width:100%">
<tr>
<th>Nimi</th>
<th>Tyyppi</th>
<th>Pakollinen</th>
<th>Kuvaus</th>
</tr>
<tr>
<td>Entitlogicalname</td>
<td>Merkkijono</td>
<td>Kyllä</td>
<td>Luotavan entiteetin looginen nimi. Esimerkki: &quot;account &quot;.</td>
</tr>
<tr>
<td>tieto</td>
<td>Objekti</td>
<td>Kyllä</td>
<td><p>JSON-objekti, joka määrittää uuden entiteettitietueen attribuutit ja arvot.</p>
<p>Jäljempänä tässä aiheessa on esimerkkejä siitä, miten voit määrittää <code>data</code>-objektin eri luonti tilanteita varten.</td>
</tr>
<tr>
<td>Suckscallback</td>
<td>Funktio</td>
<td>Ei</td>
<td><p>Toiminto, joka kutsutaan, kun tietue luodaan. Uuden tietueen tunnistamiseen välitetään objekti, jolla on seuraavat ominaisuudet:</p>
<ul>
<li><b>EntityType</b>: merkki jono. Uuden tietueen entiteetin looginen nimi.</li>
<li><b>tunnus</b>: merkki jono. Uuden tietueen GUID-arvo.</li>
</ul></td>
</tr>
<tr>
<td>Virhetakaisinkutsu</td>
<td>Funktio</td>
<td>Ei</td>
<td>Toiminto, joka kutsutaan, kun toiminto epäonnistuu. Objekti, jolla on seuraavat ominaisuudet, välitetään:
<ul>
<li><b>errorCode</b>: luku. Virhe koodi.</li>
<li><b>sanoma</b>: merkki jono. Ongelmasta kertova virhe sanoma.</li>
</ul></td>
</tr>
</table>

## <a name="return-value"></a>Palautusarvo

Tyyppi: [Promise](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) <[EntityReference](../entityreference.md) >

Description: on Success-funktio palauttaa tehdä lupaustyyppiselle-objektin, joka sisältää aiemmin määritetyn **suctuscallback** -parametrin kuva uksessa määritetyt attribuutit.

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Www-ohjelmointi raja pinta](../webapi.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)