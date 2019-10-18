---
title: Retreeverord | Microsoft Docs
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
ms.assetid: dddeecc9-5067-420d-8bd7-4c914218e969
ms.openlocfilehash: 9c77bf9975bd1f1f115df9385061c008975cc184
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72341698"
---
# <a name="retrieverecord"></a>retrieveRecord

[!INCLUDE [retrieverecord-description](includes/retrieverecord-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.webAPI.retrieveRecord(entityLogicalName, id, options).then(successCallback, errorCallback);`

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
<td>Noudettavan tietueen entiteetin looginen nimi. Esimerkki: &quot;account &quot;.</td>
</tr>
<tr>
<td>Tunnus</td>
<td>Merkkijono</td>
<td>Kyllä</td>
<td>Noudettavan entiteettitietueen GUID.</td>
</tr>
<tr>
<td>asetukset</td>
<td>Merkkijono</td>
<td>Ei</td>
<td><p>Tietojen noutamiseen käytettävä OData-järjestelmä kyselyn asetukset, <b>$Select</b> ja <b>$Expand</b>.</p>
<ul><li><b>$Select</b> järjestelmä kysely-asetuksen avulla voit rajoittaa palautettuja ominaisuuksia sisällyttämällä pilkuilla erotellun luettelon ominaisuuksien nimistä. Tämä on tärkeä suoritus kyky parhaiden käytäntöjen kannalta. Jos ominaisuuksia ei määritetä <b>$Select</b>avulla, kaikki ominaisuudet palautetaan.</li>
<li><b>$Expand</b> järjestelmä kysely-asetuksen avulla voit määrittää, mitä tietoja liittyvistä entiteeteistä palautetaan. Jos sisällytät vain siirtymis ominaisuuden nimen, saat kaikki liittyvien tietueiden ominaisuudet. Voit rajoittaa liittyville tietueille palautettuja ominaisuuksia käyttämällä <b>$Select</b> järjestelmä kysely-asetusta sulkeissa siirtymisen ominaisuuden nimen jälkeen. Käytä tätä sekä <i>Yksiarvoiseen</i> että <i>kokoelma-arvoiseen</i> siirtymis ominaisuuteen.</li>
</ul>
<p>Voit määrittää kysely asetukset, jotka alkavat <code>?</code>. Voit myös määrittää useita kysely asetuksia käyttämällä <code>&amp;</code> erottamaan kysely asetukset. Esimerkki:</p>
<code>?$select=name&amp;$expand=primarycontactid($select=contactid,fullname)</code>
<p>Myöhemmin tässä aiheessa on esimerkkejä siitä, miten voit määrittää <code>options</code> parametrin eri palautus tilanteita varten.</td>
</tr>
<tr>
<td>Suckscallback</td>
<td>Funktio</td>
<td>Ei</td>
<td><p>Toiminto, joka kutsutaan, kun tietue noudetaan. JSON-objekti, jolla on palautetut ominaisuudet ja arvot, välitetään funktiolle.</p>
</td>
</tr>
<tr>
<td>Virhetakaisinkutsu</td>
<td>Funktio</td>
<td>Ei</td>
<td>Toiminto, joka kutsutaan, kun toiminto epäonnistuu.</td>
</tr>
</table>

## <a name="return-value"></a>Palautusarvo

Tyyppi: [lupaus](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) <[entiteetti](../entity.md) >



### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Www-ohjelmointi raja pinta](../webapi.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)