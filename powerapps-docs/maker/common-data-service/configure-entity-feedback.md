---
title: Entiteetin määrittäminen palautetta varten PowerAppsin avulla | MicrosoftDocs
description: 'Lue lisää, miten voi ottaa käyttöön entiteetin palautteen'
ms.custom: ''
ms.date: 05/18/2018
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
ms.assetid: 5b25cf09-d43b-4165-9eaa-7549f4855e7c
caps.latest.revision: 13
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-an-entity-for-feedbackratings"></a>Entiteetin määrittäminen palautetta ja arviointeja varten

Voit antaa asiakkaille tai työntekijöille mahdollisuuden antaa palautetta mistä tahansa entiteettitietueesta tai antaa heidän arvioida entiteettitietueet määritetyllä arviointiasteikolla.  

Tämä ominaisuus on usein järjestelmän käytössä. Se sieppaa tietoja asiakkaista portaalin tai kyselyn avulla. Palvelua tai tuotetta koskevan tyytyväisyyden tietoja voidaan käyttää entiteeteissä, jotka edustavat tällaisia tietoja.

Myös työntekijät voivat antaa palautetta yhteistyöstä.

> [!NOTE]
> Sinulla on oltava järjestelmänvalvojan tai järjestelmän mukauttajan käyttöoikeusrooli tai vastaavat käyttöoikeudet, jotta voit suorittaa nämä vaiheet.
  
## <a name="enable-feedback"></a>Ota palaute käyttöön  
  
Muokkaa entiteettiä ja ota **palaute** käyttöön. Lisätietoja: [Entiteetin muokkaaminen](edit-entities.md)
  
## <a name="add-a-subgrid-for-feedback-on-the-entity-form"></a>Voit lisätä kohdelomakkeeseen aliruudukon palautetta varten  

Oletusarvoisesti käyttäjien täytyy mennä liittyvien tietueiden luetteloon jossa on tietue, johon haluat lisätä palautteen. Jotta käyttäjien on helpompaa lisätä palautetta, haluat ehkä lisätä Palaute-aliruudukon entiteetin lomakkeeseen, jossa otat palautteen käyttöön.  

<!-- This is the closest I could find to a topic about adding an subgrid to a form. --> Lisätietoja:  [Aliruudukon ominaisuuksien yleiskatsaus](../model-driven-apps/sub-grid-properties-legacy.md)

## <a name="add-a-rollup-field--to-the-entity-form-to-show-the-ratings"></a>Lisää koontikenttä entiteettilomakkeeseen ja näytä luokitukset  

Sen mukaan, kuinka haluat laskea entiteetin luokituksen, voit luoda koontikentän, joka laskee luokittelun, ja lisätä sen entiteetin lomakkeeseen, jolle olet ottanut palautteen käyttöön. Lisätietoja: [Arvot kokoavien koontikenttien määrittäminen](define-rollup-fields.md)
  
### <a name="see-also"></a>Katso myös  
 [Lähetä Dynamics 365 -tietueiden palautetta tai luokituksia](/dynamics365/customer-engagement/basics/submit-feedback-ratings)
