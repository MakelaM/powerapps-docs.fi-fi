---
title: 'Kehittäjät: Parhaat käytännöt ja ohjeita Common Data Servicelle | Microsoft Docs'
description: Parhaat käytännöt ja ohjeet kehittäjille PowerAppsin Common Data Servicessa.
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 01/07/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: c89042e1f94e6f891bfdc255c38f72929c27cb1e
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61528362"
---
# <a name="best-practices-and-guidance-for-the-common-data-service"></a>Parhaat käytännöt ja ohjeita Common Data Servicelle

Common Data Service on laajennettava ympäristö, jonka avulla kehittäjät voivat luoda erittäin mukautettuja ja räätälöityjä kokemuksia. Kun sovelluskehittäjä mukauttaa, laajentaa tai integroi Common Data Servicella, hänen tulee tuntea vakiintuneet ohjeet ja parhaat käytännöt. 

Tässä osiossa on tietoja ongelmista, jotka olemme tunnistaneet, ja niiden vaikutuksesta. Saat myös ohjeita niiden ratkaisemiseksi. Selitämme taustaa sille, miksi asiat tulee tehdä tietyllä tavalla, jolloin voit välttää mahdollisia ongelmia tulevaisuudessa. Tästä voi olla hyötyä ympäristösi käytettävyydelle, tuettavuudelle ja suorituskyvylle. Ohjedokumentaatio tukee nykyisiä tietoja, jotka ovat kehittäjien ja hallinnoijien oppaissa.

# <a name="targeted-customization-types"></a>Kohteena olevat mukauttamistyypit
Dokumentaatio kohdentaa seuraaviin mukauttamistyyppeihin:

- Mukautetut työnkulkuaktiviteetit ja laajennukset
- Common Data Servicen tietojen käyttäminen
- Common Data Servicea laajentavat integroinnit

# <a name="sections"></a>Osat
Kussakin ohjeartikkelissa on useimmat tai kaikki seuraavat osiot:

- Otsikko - ohjeen kuvaus
- Luokka - ainakin yksi alue, johon ohjeen noudattamatta jättäminen vaikuttaa
- Vaikutuspotentiaali - ympäristöön vaikuttavan riskin taso (suuri, normaali tai pieni), jos ohjeita ei noudateta
- Oireet - mahdolliset merkit siitä, että ohjeita ei ole noudatettu
- Ohjeet - suosituksia, jotka voivat sisältää myös esimerkkejä
- Ongelmallinen kuviot - ohjeen noudattamatta jättämisen kuvaus tai esimerkkejä
- Lisätiedot - tietoja laajempaa kuvaa varten
- Katso myös - viittaukset lisätietoihin jostakin artikkelissa mainitusta

# <a name="categories"></a>Luokat
Kukin ohjeartikkeli on luokiteltu ainakin yhteen seuraavista luokista:

- Käyttö – tietyn ohjelmointirajapinnan, kuvion tai määrityksen virheellinen käyttö
- Rakenne – mukautuksen rakennevirheet
- Suorituskyky – mukauttaminen tai kuvio, joka saattaa tuottaa negatiivisen vaikutuksen suorituskykyyn, kuten muistinhallintaan, suorittimen käyttöasteeseen, verkkoliikenteeseen tai käyttökokemukseen
- Suojaus – mukautuksen mahdolliset haavoittuvuudet, joita voidaan hyödyntää käytönaikaisessa ympäristössä
- Päivitysvalmius – mukauttaminen tai kuvio, joka voi kasvattaa epäonnistuneen versiopäivityksen riskiä
- Verkkosiirtyminen – mukauttaminen tai kuvio, joka voi kasvattaa epäonnistuneen verkkosiirtymisen riskiä
- Ylläpidettävyys – mukauttaminen, joka tarpeettomasti kasvattaa kehittäjältä vaadittavia toimia muutosten tekemiseen, tarvittavien muutosten taajuuteen tai regressioiden lisääntymismahdollisuuteen
- Tuettavuus – mukauttaminen tai kuvio, joka ei kuulu julkaistuihin tuettavuusilmoituksiin, kuten poistettujen ohjelmointirajapintojen käyttö tai kiellettyjen tekniikoiden toteutus
