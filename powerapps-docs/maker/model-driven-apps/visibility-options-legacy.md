---
title: Mallipohjaisen sovelluksen lomakkeen elementtien näyttäminen tai piilottaminen PowerAppsin avulla | MicrosoftDocs
description: 'Tietoja siitä, miten voit näyttää tai piilottaa osia, kuten välilehtiä, osia tai kenttiä'
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 7b9e8dc2-229c-455f-ae18-49e8d879ff71
caps.latest.revision: 63
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="show-or-hide-model-driven-app-form-elements"></a>Mallipohjaisen sovelluksen lomakkeen elementtien näyttäminen tai piilottaminen

 Monet lomake-elementtityypit voidaan oletusarvoisesti joko näyttää tai piilottaa. Tämä vaihtoehto on myös välilehdissä, osissa, iFrame-kehyksissä ja verkkoresursseissa. Näiden elementtien näkyvyyttä voidaan hallita lomakkeen komentosarjoilla tai liiketoimintasäännöillä. Tällä tavoin voidaan luoda dynaaminen lomake, joka muodostaa lomakkeen tilan mukaan mukautuvan käyttöliittymän.  
  
> [!NOTE]
>  Lomake-elementtien piilottaminen ei ole suositeltava tapa suojata lomake. Käyttäjillä on useita tapoja, joilla he voivat tarkastella piilotettuja elementtejä käyttävän lomakkeen kaikkia elementtejä ja tietoja. 
  
 Sen sijaan että suunnittelisit lomakkeita, joissa asetusten näkyvyyttä hallitaan komentosarjoilla, harkitse, vastaisiko liiketoimintaprosessi, dialogi tai toisen lomakkeen käyttö paremmin tarpeitasi. Jos käytät komentosarjoja, varmista, että mahdollisesti piilotettava elementti piilotetaan oletusarvoisesti. Näytä se vain niissä komentosarjoissa, joissa logiikka edellyttää sitä. Tällä tavoin se ei näy esityksissä, jotka eivät tue komentosarjoja.  

## <a name="next-steps"></a>Seuraavat vaiheet

[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)
