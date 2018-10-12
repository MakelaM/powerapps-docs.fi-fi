---
title: PowerAppsin yrityskäyttöönoton hallinnointi | MicrosoftDocs
description: Tutustu PowerAppsin yrityskäyttöönoton hallinnointia käsittelevään raporttiin.
ms.custom: ''
ms.date: 08/09/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
ms.assetid: 83200632-a36b-4401-ba41-952e5b43f939
caps.latest.revision: 31
author: jimholtz
ms.author: jimholtz
manager: kvivek
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: ce8daad960834c2965e2a5432ccaf2a3f515e503
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42857490"
---
# <a name="administering-a-powerapps-enterprise-deployment"></a>PowerAppsin yrityskäyttöönoton hallinnointi

PowerApps on erittäin tuottava sovelluskehitysympäristö Microsoftilta.  Microsoft luo ympäristön avulla omia 1. osapuolen sovelluksia, kuten Dynamics 365 for Sales, Service, Field Service, Marketing ja Talent.  Tämä tarkoittaa sitä, että nämä sovellukset on alun perin kehitetty kyseisessä ympäristössä.   Yritysasiakkaat voivat myös luoda omia mukautettuja toimialasovelluksia samalla tekniikalla.  Yksittäiset käyttäjät ja ryhmät organisaatiossa voivat myös luoda omia tai ryhmän tuottavuussovelluksia käyttämättä koodia tai hyödyntäen koodia vain vähän. 

Tutustu seuraavaan ladattavaan raporttiin: [PowerAppsin yrityskäyttöönoton hallinnointi](https://aka.ms/powerappsadminwhitepaper)

Raportti on tarkoitettu yrityssovelluksen järjestelmänvalvojalle, joka vastaa PowerApps-ympäristössä kehitettyjen sovellusten suunnittelusta, suojaamisesta, käyttöönottamisesta ja tukemisesta.  Raportin tavoitteena on auttaa ymmärtämään, mitä ympäristössä tällä hetkellä on, miten kehitettäviä ja käyttöönotettavia sovelluksia voi suunnitella ennakoivasti ja miten hallitaan käyttöönottojen päivittäisiä hallintatehtäviä.
Tässä raportissa käsitellään keskeiset käsitteet, ympäristön arkkitehtuuri ja tarvittavat päätökset.  Autamme aina mahdollisuuksien mukaan parhaiden toimintatapojen kehittämisessä organisaatiollesi, jotta voit varmistaa onnistuneet käyttöönotot ja erinomaisen tuottavuuden ympäristön käyttäjille.

PowerApps-ympäristö on osa suurempaa Microsoft Power -ympäristöä, joka sisältää myös PowerBI- ja Microsoft Flow -palvelut. Siinä hyödynnetään Common Data Servicen yleistä infrastruktuuria sovelluksissa ja tietoliittimissä. Nämä ominaisuudet on kehitetty Microsoft Azure -pilvipalvelujen pohjalta ja niissä hyödynnetään pilvipalveluja.  PowerApps-ympäristössä luodut sovellukset voivat sisältää myös Azure-pilvipalveluja sovellusten skaalaamiseksi yksittäisen henkilön tuottavuudesta yrityksen elintärkeisiin toimialasovelluksiin.

![Microsoft Power -ympäristö](media/ms-power-platform.png "Microsoft Power-ympäristö")
