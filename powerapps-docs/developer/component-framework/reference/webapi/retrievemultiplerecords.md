---
title: Retrievemulticerords | Microsoft Docs
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
ms.assetid: 824a53f9-c743-435a-9de2-8128846f3191
ms.openlocfilehash: d708596e9b8e12ead8f84d31d3b35fb5b27843f8
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72340801"
---
# <a name="retrievemultiplerecords"></a>retrieveMultipleRecords

[!INCLUDE [retrievemultiplerecords-description](includes/retrievemultiplerecords-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.webAPI.retrieveMultipleRecords(entityLogicalName, options, maxPageSize).then(successCallback, errorCallback);`

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
<td>Noudettavien tietueiden entiteetin looginen nimi. Esimerkki: &quot;account &quot;.</td>
</tr>
<tr>
<td>asetukset</td>
<td>Merkkijono</td>
<td>Ei</td>
<td><p>OData-järjestelmä kyselyn asetukset tai FetchXML-kysely tietojen noutamista varten. </p> 
<ul>
<li>Seuraavia järjestelmä kysely asetuksia tuetaan: <b>$Select</b>, <b>$Top</b>, <b>$Filter</b>, <b>$Expand</b>ja <b>$orderBy</b>.</li>
<li>Jos haluat määrittää FetchXML-kyselyn, Määritä kysely <code>fetchXml</code>-määritteen avulla.</li>
</ul>
<p>Huom.: sinun on aina käytettävä <b>$Select</b> järjestelmä kysely-asetusta, jos haluat rajoittaa entiteettitietueelle palautettuja ominaisuuksia sisällyttämällä pilkuilla erotellun luettelon ominaisuuksien nimistä. Tämä on tärkeä suoritus kyky parhaiden käytäntöjen kannalta. Jos ominaisuuksia ei määritetä <b>$Select</b>avulla, kaikki ominaisuudet palautetaan.</li>
<p>Voit määrittää kysely asetukset, jotka alkavat <code>?</code>. Voit myös määrittää useita järjestelmä kyselyn asetuksia käyttämällä <code>&amp;</code> erottamaan kysely asetukset.
<p>Jäljempänä tässä aiheessa on esimerkkejä siitä, miten voit määrittää <code>options</code>-parametrin eri noudettavien useiden mallien noutamista varten.</td>
</tr>
<tr>
<td>maxPageSize</td>
<td>Numero</td>
<td>Ei</td>
<td><p>Määritä positiivinen luku, joka ilmaisee sivua kohden palautettavien entiteettitietueiden määrän. Jos et määritä tätä parametria, oletus arvo välitetään muodossa 5000.</p>
<p>Jos noudettavien tietueiden määrä on suurempi kuin määritetty <code>maxPageSize</code>-arvo, palautetun tehdä lupaustyyppiselle-objektin <code>nextLink</code> määrite sisältää linkin, jonka avulla noudetaan seuraava entiteettien joukko. </td>
</tr>
<tr>
<td>Suckscallback</td>
<td>Funktio</td>
<td>Ei</td>
<td><p>Toiminto, joka kutsutaan, kun entiteettitietueita noudetaan. Funktiolle välitetään objekti, jolla on seuraavat attribuutit:</p>
<ul>
<li><b>entiteetit</b>: JSON-objektien matriisi, jossa kukin objekti edustaa noudetun entiteetin tietuetta, joka sisältää määritteitä ja niiden arvoja <code>key: value</code> pareina. Entiteettitietueen tunnus noudetaan oletusarvoisesti.</li>
<li><b>Nextlink</b>: merkki jono. Jos noudettavien tietueiden määrä on suurempi kuin pyynnön <code>maxPageSize</code>-parametrissa määritetty arvo, tämä määrite palauttaa URL-osoitteen, joka palauttaa seuraavan tietue joukon.</li>
</ul>
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

Tyyppi: [lupaus](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) <RetrieveMultipleResponse>

Kuvaus: `RetrieveMultipleResponse` palauttaa lupauksen, joka sisältää matriisin noudetut entiteettitietueita sisältävien JSON-objektien taulukon ja **Nextlink** -määritteen ja URL-osoitteen, joka osoittaa seuraavaan tietue joukkoon, jos sivutus (`maxPageSize`) on määritetty pyynnössä, ja palautettu tietueiden määrä ylittää sivutus arvon. Sillä on seuraavat parametrit:

|parametri|Palautusarvo|Kuvaus|
|----|------|-------|
|entiteetit|`Entity[]`|JSON-objektien matriisi, jossa kukin objekti edustaa noudetun entiteettitietueen, joka sisältää määritteitä ja niiden arvoja.|
|nextLink|`string`|Jos noudettavien tietueiden määrä on suurempi kuin pyynnössä maxPageSize-parametrissa määritetty arvo, tämä määrite palauttaa URL-osoitteen, joka palauttaa seuraavan tietue joukon.|


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Www-ohjelmointi raja pinta](../webapi.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)