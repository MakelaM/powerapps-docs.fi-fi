---
title: Delesecord | Microsoft Docs
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
ms.assetid: 5c9968bf-d535-425c-b1f1-0db6b7822de1
ms.openlocfilehash: f6c8dd6ea7d156e28ab3ae54d7fe37dad6c4546a
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340755"
---
# <a name="deleterecord"></a>deleteRecord

[!INCLUDE [deleterecord-description](includes/deleterecord-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.webAPI.deleteRecord(entityLogicalName, id).then(successCallback, errorCallback);`

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
<td>Poistettavan tietueen entiteetin looginen nimi. Esimerkki: &quot;account &quot;. </td>
</tr>
<tr>
<td>Tunnus</td>
<td>Merkkijono</td>
<td>Kyllä</td>
<td>Poistettavan entiteettitietueen GUID.</td>
</tr>
<tr>
<td>Suckscallback</td>
<td>Funktio</td>
<td>Ei</td>
<td><p>Toiminto, joka kutsutaan, kun tietue poistetaan. Poistetun tietueen tunnistamiseen välitetään objekti, jolla on seuraavat ominaisuudet:</p>
<ul>
<li><b>EntityType</b>: merkki jono. Tietueen entiteettityyppi.</li>
<li><b>tunnus</b>: merkki jono. Tietueen GUID-arvo.</li>
<li><b>nimi</b>: merkki jono. Tietueen nimi.</li>
</ul></td>
</tr>
<tr>
<td>Virhetakaisinkutsu</td>
<td>Funktio</td>
<td>Ei</td>
<td>Toiminto, joka kutsutaan, kun toiminto epäonnistuu.</td>
</tr>
</table>

## <a name="return-value"></a>Palautusarvo

Tyyppi: [Promise](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) <[EntityReference](../entityreference.md) >

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Www-ohjelmointi raja pinta](../webapi.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)