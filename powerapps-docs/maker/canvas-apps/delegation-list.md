---
title: Delegoitavat tietolähteet | Microsoft Docs
description: Luettelo kaikista tuetuista delegoitavista tietolähteistä
services: ''
suite: powerapps
documentationcenter: na
author: archnair
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 08/15/2017
ms.author: archanan
ms.openlocfilehash: e073c0a8c471dc8b863894e2d229b15b66b3ce60
ms.sourcegitcommit: 6afca7cb4234d3a60111c5950e7855106ff97e56
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/23/2018
---
# <a name="delegable-data-sources"></a>Delegoitavat tietolähteet
[Tutustu delegointiin](delegation-overview.md) -artikkelin mukaisesti delegointi on toimintaa, jossa PowerApps delegoi tiedonkäsittelyn tietolähteelle sen sijaan, että se siirtäisi tiedot sovellukseen käsiteltäväksi paikallisesti.

Delegointia tuetaan vain taulukkomuotoisissa tietolähteissä. Luettelossa esitetään taulukkomuotoiset tietolähteet ja tieto siitä, tukevatko ne delegointia. Tietoja tästä on seuraavassa osiossa.

* Common Data Service – **Kyllä**
* SharePoint – **Kyllä**
* SQL Server – **Kyllä**
* Dynamics 365 – **Kyllä**
* Salesforce – **Kyllä**
* Dynamics 365 for Operations – Ei vielä
* Dynamics 365 for Financials – Ei vielä
* Dynamics NAV – Ei vielä
* Google Sheets – Ei vielä

Lisää taulukkomuotoisia tietolähteitä ja delegoinnin tukea niitä varten lisätään säännöllisesti.

Tässä asiakirjassa luetellaan nykyinen delegoinnin tukitila kunkin tietolähteen kohdalla.

## <a name="prerequisites"></a>Edellytykset

* Perehdy [Tutustu delegointiin](delegation-overview.md) -artikkeliin

## <a name="list-of-data-sources-and-supported-delegation"></a>Luettelo tietolähteistä ja tuetusta delegoinnista
Tätä tietolähteiden ja delegoitavien funktioiden ja predikaattien luetteloa päivitetään säännöllisesti, jotta se edustaa PowerAppsin nykyistä delegoinnin tukitasoa.

### <a name="top-level-delegable-functions"></a>Ylimmän tason delegoitavat funktiot
| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Average |Ei |Ei |Kyllä |Ei |Ei |
| Filter |Kyllä |Kyllä |Kyllä |Kyllä |Kyllä |
| LookUp |Kyllä |Kyllä |Kyllä |Kyllä |Kyllä |
| Max |Ei |Ei |Kyllä |Ei |Ei |
| Min |Ei |Ei |Kyllä |Ei |Ei |
| Haku |Kyllä<sup>1</sup> |Ei |Kyllä |Kyllä |Kyllä |
| Sort |Kyllä |Kyllä |Kyllä |Kyllä |Kyllä |
| SortByColumns |Kyllä |Kyllä |Kyllä |Kyllä |Kyllä |
| Sum |Ei |Ei |Kyllä |Ei |Ei |

<sup>1</sup>Vain merkkijonokentille

### <a name="filter-and-lookup-delegable-predicates"></a>Suodatuksen ja Haun delegoitavat predikaatit
| &nbsp; | Common Data Service | SharePoint | SQL Server | Dynamics 365 | Salesforce |
| --- | --- | --- | --- | --- | --- |
| Ei |Kyllä |Ei |Kyllä |Kyllä |Kyllä |
| IsBlank |Ei |Ei |Kyllä |Kyllä |Ei |
| TrimEnds |Ei |Ei |Kyllä |Ei |Ei |
| Len |Ei |Ei |Kyllä |Ei |Ei |
| +, - |Ei |Ei |Kyllä |Ei |Ei |
| <, <=, =, <>, >, >= |Kyllä |Kyllä (vain =) |Kyllä |Kyllä |Kyllä |
| And (&&), Or (&#124;&#124;), Not (!) |Kyllä<sup>2</sup> |Kyllä (paitsi Not(!)) |Kyllä |Kyllä |Kyllä |
| In |Ei |Ei |Kyllä |Ei |Kyllä |
| StartsWith |Ei |Kyllä |Ei |Ei |Ei |

<sup>2</sup>Vain operaattoreille. And-/Or-/Not-funktiota ei delegoida.
