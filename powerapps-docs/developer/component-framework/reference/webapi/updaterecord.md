---
title: Updacerecord | Microsoft Docs
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
ms.assetid: 179ced61-ff0f-45ef-aa14-835ce99532cf
ms.openlocfilehash: 96037bcd8ca43448e928abef714ae031222d8e98
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340686"
---
# <a name="updaterecord"></a>updateRecord

[!INCLUDE [updaterecord-description](includes/updaterecord-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.webAPI.updateRecord(entityLogicalName, id, data).then(successCallback, errorCallback);`

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
<td>Päivitettävän tietueen entiteetin looginen nimi. Esimerkki: &quot;account &quot;.</td>
</tr>
<tr>
<td>Tunnus</td>
<td>Merkkijono</td>
<td>Kyllä</td>
<td>Päivitettävän entiteettitietueen GUID.</td>
</tr>
<tr>
<td>tieto</td>
<td>Objekti</td>
<td>Kyllä</td>
<td><p>JSON-objekti, joka sisältää <code>key: value</code> paria, jossa <code>key</code> on entiteetin ominaisuus ja <code>value</code> on päivitettävän ominaisuuden arvo.</p>
<p>Jäljempänä tässä aiheessa on esimerkkejä siitä, miten voit määrittää <code>data</code>-objektin eri päivitys tilanteita varten.</td>
</tr>
<tr>
<td>Suckscallback</td>
<td>Funktio</td>
<td>Ei</td>
<td><p>Toiminto, joka kutsutaan, kun tietue päivitetään. Päivitetyn tietueen tunnistamiseen välitetään objekti, jolla on seuraavat ominaisuudet:</p>
<ul>
<li><b>EntityType</b>: merkki jono. Päivitetyn tietueen entiteettityyppi.</li>
<li><b>tunnus</b>: merkki jono. Päivitetyn tietueen GUID-arvo.</li>
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

Tyyppi: [Promise] ((dateformatttinginfo. MD) <[EntityReference](../entityreference.md) >

Description: on Success-funktio palauttaa tehdä lupaustyyppiselle-objektin, joka sisältää aiemmin määritetyn **suctuscallback** -parametrin kuva uksessa määritetyt attribuutit.


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Www-ohjelmointi raja pinta](../webapi.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)