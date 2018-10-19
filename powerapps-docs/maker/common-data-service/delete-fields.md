---
title: Kenttien poistaminen PowerAppsissa | MicrosoftDocs
description: Kenttien poistaminen
ms.custom: ''
ms.date: 06/20/2018
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
ms.assetid: 578ac950-da16-4ec6-a0a4-25f3aaa3b96e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="delete-fields"></a>Kenttien poistaminen

<a name="BKMK_DeletingFields"></a>   
 
 Koska sinulla on järjestelmänvalvojan käyttöoikeusrooli, voit poistaa minkä tahansa mukautetun kentän, joka ei sisälly hallittuun ratkaisuun. Kun kenttä poistetaan, kaikki kenttään tallennetut tiedot menetetään. Poistetun kentät tiedot voidaan palauttaa vain palauttamalla tietokanta hetkeen ennen kentän poistamista.  
  
 Ennen mukautetun entiteetin poistamista sinun on poistettava muissa ratkaisun osissa mahdollisesti olevat riippuvuudet. Avaa kenttä, jonka jälkeen voit tarkastella mitä tahansa **riippuvaista osaa** valikkorivin **Näytä riippuvuudet** -painikkeella. Jos kenttää esimerkiksi käytetään lomakkeessa tai näkymässä, sinun on poistettava ensin viittaukset kenttään kyseisissä ratkaisun osissa.  
  
 Jos poistat valintakentän, sen 1:N-entiteettisuhde poistetaan automaattisesti.  

 ## <a name="next-steps"></a>Seuraavat vaiheet

 [Mukautetun entiteetin poistaminen](data-platform-delete-entity.md)
