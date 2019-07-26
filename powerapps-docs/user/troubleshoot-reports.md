---
title: Sellaisten tietojen vian määritys, joita ei näytetä raportissa | Microsoft Docs
description: Sellaisten tietojen vian määritys, joita ei näytetä raportissa
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 06/27/2019
ms.author: mkaur
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 1156aa8fb5fbc3ae51c21b8aa41606df6dbc2e86
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420762"
---
# <a name="troubleshoot-problems-with-data-not-displaying-in-a-report"></a>Sellaisten tietojen vian määritys, joita ei näytetä raportissa

On olemassa useita mahdollisia syitä siihen, miksi raportin tiedot eivät näy:  
  
- **Riittämättömät käyttö oikeudet**. Jos sinulla ei ole käyttö oikeutta Common Data Service tarkastella tietuetta, sitä ei näytetä raportissa.  
  
- **Tietoja ei ole annettu.** Tietoja syöttävä henkilö on saattanut jättää kentät tyhjiksi.  
  
- **Tiedot eivät vastaa raportin ehtoja.** Monet raportit sisältävät oletus suodattimen, joka näyttää vain aktiiviset tietueet, tai olet saattanut valita ehtoja, joilla ei ole vastaavaa tietuetta. Kokeile muuttaa raportti suodatinta. Lisä tietoja [on kohdassa raportin oletus suodattimen muokkaaminen](edit-report-filter.md)  
  
- **Tarkastelet ehkä raportin väli muistissa olevaa kopiota.** Oletus arvon mukaan Common Data Service raporttien tiedot vedetään tieto kannasta aina, kun suoritat raportin. Järjestelmänvalvoja on saattanut kuitenkin muuttaa raporttia suoritettavaksi väli muistista. Jos tiedot, jotka annoit viime aikoina, eivät sisälly raporttiin, sinulla voi olla väli muistista raportin vanhempi versio. Jos haluat päivittää raportin, valitse raportti-työkalu riviltä **Päivitä** -painike.  
  
- **Sinulla ei ehkä ole käyttö oikeutta lukea aliraportin tietueita.** Jos sinulla ei ole käyttö oikeutta lukea aliraporttiin sisältyviä tietue tyyppejä, näyttöön tulee virhe sanoma, jonka mukaan aliraporttia ei voitu näyttää.  
  
- **Microsoft Internet Explorerin tieto suoja-asetukset saattavat estää vaaditut eväs teet.** Jos kaavio raporteissa näkyy kaavion sijaan punainen kirjain X, tieto suoja-asetuksesi saattavat estää eväs teen, joka vaaditaan kaavio-ohjaus objektille. Korjaa tämä ongelma selaimessa ottamalla eväs teet käyttöön Reporting Servicesiä suorittavalle palvelimelle.  
  

### <a name="see-also"></a>Katso myös
[Raporttien käsitteleminen](work-with-reports.md) 

[Luo raportti ohjatulla raportin luonti toiminnolla](create-report-with-wizard.md)

[Lisää olemassa oleva raportti](add-existing-report.md)

[Muokkaa raportti suodatinta](edit-report-filter.md)

