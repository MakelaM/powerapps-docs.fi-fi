---
title: Malliin perustuvan sovelluksen lomake-elementtien näyttäminen tai piilottaminen PowerAppsissa | MicrosoftDocs
description: Lue ohjeet välilehtien, osioiden ja kenttien kaltaisten elementtien näyttämiseen ja piilottamiseen
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
ms.openlocfilehash: 86fafe70ae3bc04eff5e85a4baf3682c32427149
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681277"
---
# <a name="show-or-hide-model-driven-app-form-elements"></a>Malliin perustuvan sovelluksen lomake-elementtien näyttäminen tai piilottaminen

 Monet erilaiset lomake-elementit voidaan näyttää tai piilottaa oletusarvoisesti. Välilehdet, osiot, kentät, iFrame-kehykset ja verkkoresurssit tukevat tätä. Voit hallita näiden elementtien näkyvyyttä lomakekomentosarjoilla tai liiketoimintasäännöillä. Näin voit luoda dynaamisen lomakkeen, jolla voit tarjota lomakkeeseen soveltuvan käyttöliittymän.  
  
> [!NOTE]
>  Emme suosittele suojauksen toteuttamista lomakkeen elementtejä piilottamalla. Käyttäjät voivat tarkastella lomakkeen kaikkia elementtejä ja tietoja usein eri tavoin, vaikka elementit olisi piilotettu. 
  
 Sen sijaan, että suunnittelet lomakkeita, joissa asetusten ja toimintojen näkyvyyttä hallitaan komentosarjoilla, sinun kannattaa harkita, soveltuuko liiketoimintaprosessi, valintaikkuna tai toiseen lomakkeeseen siirtyminen paremmin tarpeisiisi. Jos käytät komentosarjoja, varmista, että kaikki mahdollisesti piilotettavat elementit piilotetaan oletusarvoisesti. Näytä ne komentosarjoilla vain, kun logiikka kutsuu niitä. Tällä tavalla niitä ei näytetä esityksissä, jotka eivät tue komentosarjoja.  

## <a name="next-steps"></a>Seuraavat vaiheet

[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)