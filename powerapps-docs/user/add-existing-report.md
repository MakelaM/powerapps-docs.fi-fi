---
title: Raportin lisääminen Powerappsin ulkopuolelta | Microsoft Docs
description: Raportin lisääminen Powerappsin ulkopuolelta
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
ms.openlocfilehash: 24faa77b454cf3324e4b7277c94c6cd364aec9a9
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420164"
---
# <a name="add-a-report-from-outside-powerapps"></a>Raportin lisääminen Powerappsin ulkopuolelta

Jos olet luonut mukautetun raportin järjestelmän ulkopuolella, voit helposti lisätä sen Powerappsiin.

Lisä tietoja mukautetun raportin luomisesta on kohdassa [Reporting and Analytics Guide](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/analytics/get-started-writing-reports).

1. Valitse vasemmassa siirtymis ruudussa raportit-alue. 
2. Valitse komento palkissa **Uusi**.
  
   **Lisää toisessa sovelluksessa luodun tiedoston**  
  
   1. Valitse **lähde** -osassa **raportin tyyppi** -ruudusta **olemassa oleva tiedosto**.  
   
     > [!div class="mx-imgBorder"]
     > ![Lisää olemassa oleva raportti](media/add_existing_report.png "Lisää olemassa oleva raportti")
  
   2. Kirjoita **tiedoston sijainti** -ruutuun lisättävän tiedoston polku ja tiedosto nimi tai Etsi tiedosto valitsemalla **Selaa** . 
   
      Voit ladata palvelimeen monia muita tiedosto tyyppejä, kuten Excel-tiedoston, mutta jotta tämä voidaan suorittaa samalla tavalla kuin SQL Server Reporting Services raportti tai Ohjattu raportin luominen, tiedoston on oltava. RDL-tiedosto. Lisä tietoja on kohdassa [raportin kirjoitus ympäristö SQL Server Data Tools avulla](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/analytics/report-writing-environment-using-sql-server-data-tools).
  
      -TAI  
  
   **Lisää linkki verkko sivuun**  
  
   1.  Valitse **lähde** -osiossa **raportin tyyppi** -ruudussa **Linkitä verkko sivuun**.  
  
   2.  Kirjoita verkko **sivun URL-osoite** -ruutuun verkko sivun URL-osoite.  
  
3. Määritä raportin ominaisuudet.
  
   1.  Määritä **tiedot** -osiossa merkityksellinen nimi ja kuvaus raportille.  
  
   2.  **Pääraportin** teksti ruutu näyttää nykyisen raportin pääraportin, jos sellainen on olemassa.  
  
   3. **Luokkia**. Valitse **Valitse tai muuta tämän kentän arvot** ![kolme pistettä painiketta](media/ellipsis-button.png "") ja määritä sitten tähän raporttiin sisällytettävät luokat.  
  
   4. **Liittyvät tietue tyypit**. Jos haluat raportin näkyvän tiettyjen tietue tyyppien sivulla olevien raporttien luettelossa, valitse **Valitse tai muuta tämän kentän arvot** ![kolme pistettä painiketta](media/ellipsis-button.png "") ja valitse sitten tietue tyypit.  
  
   5. **Näytä kohteessa**. Jos haluat määrittää, missä raporttien tulee olla näkyvissä, valitse **Valitse tai muuta tämän kentän arvot** ![kolme pistettä painiketta](media/ellipsis-button.png "") ja valitse sitten yksi tai useampi vaihto ehto.  
  
        Jos arvoja ei ole valittu, raportti ei näy loppu käyttäjille.  
  
4. Valitse **Tallenna** tai **Tallenna ja sulje**.  




### <a name="see-also"></a>Katso myös
[Raporttien käsitteleminen](work-with-reports.md) 

[Luo raportti ohjatulla raportin luonti toiminnolla](create-report-with-wizard.md)

[Muokkaa raportti suodatinta](edit-report-filter.md)

[Sellaisten tietojen vian määritys, joita ei näytetä raportissa](troubleshoot-reports.md)
