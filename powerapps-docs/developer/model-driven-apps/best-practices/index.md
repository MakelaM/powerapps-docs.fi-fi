---
title: 'Kehittäjät: Mallipohjaisten sovellusten parhaat käytännöt ja ohjeet | Microsoft Docs'
description: Mallipohjaisten sovellusten parhaat käytännöt ja ohjeet kehittäjille PowerAppsissa.
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
ms.date: 12/12/2018
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 152b7bc5e61a579bc06c02f60079ecfc7b05512b
ms.sourcegitcommit: 11486fb4c16095e3fef785126003cac3e3e06c0d
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/14/2019
ms.locfileid: "54271380"
---
# <a name="best-practices-and-guidance-for-model-driven-apps"></a>Mallipohjaisten sovellusten parhaat käytännöt ja ohjeet

Mallipohjaiset sovellukset on komponenttikeskeinen sovelluskehityksen lähestymistapa, jonka sovelluskehittäjä voi laajentaa, jos haluat käyttää paljon räätälöidympää kokemusta. Kun mallipohjaisia sovelluksia, sovelluskehittäjä tulee olla tietoisia vakiintuneet ohjeita ja parhaita käytäntöjä. 

Tässä osiossa on tietoja ongelmista, jotka olemme tunnistaneet, ja niiden vaikutuksesta sekä saat ohjeita niiden ratkaisemiseksi. Selitämme taustaa sille, miksi asiat tulee tehdä tietyllä tavalla, jolloin voit välttää mahdollisia ongelmia tulevaisuudessa. Tästä voi olla hyötyä ympäristösi käytettävyydelle, tuettavuudelle ja suorituskyvylle. Ohjedokumentaatio tukee nykyisiä tietoja, jotka ovat kehittäjien ja hallinnoijien oppaissa.

# <a name="targeted-customization-types"></a>Kohteena olevat mukauttamistyypit
Dokumentaatio kohdentaa seuraavia mukauttamistyyppejä:

- Mallin perustuvan sovelluksen rakenne
- Entiteettilomakkeen rakenne
- Asiakkaan komentosarjat
- WWW-resurssit

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