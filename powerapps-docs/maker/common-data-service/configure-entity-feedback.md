---
title: Entiteetin palautteen määrittäminen PowerAppsissa | MicrosoftDocs
description: Opi määrittämään palaute entiteetille
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
ms.openlocfilehash: efb1cf167353d5928564b42aeb7a49f43cf272d6
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676699"
---
# <a name="configure-an-entity-for-feedbackratings"></a>Määritä entiteetti palautetta/luokituksia varten

Ota käyttöön palautteen entiteetit ja anna asiakkaiden tai työntekijöiden kirjoittaa palautetta mistä tahansa entiteetin tietueesta tai luokitella entiteetin tietueet määritettyjen luokitusten avulla.  

Tätä ominaisuutta käytetään yleisesti järjestelmässä, joka tallentaa tietoja asiakkaista portaalin tai kyselyn kautta. Palveluun tai tuotteeseen liittyviä tietoja voidaan käyttää niitä edustavien entiteettien kanssa.

Työntekijät voivat käyttää palauteominaisuutta myös yhteisiin hankkeisiin liittyvän palautteen antamiseen.

> [!NOTE]
> Sinulla on oltava järjestelmänvalvojan tai järjestelmämukauttajan käyttöoikeusrooli tai vastaavat oikeudet, jotta voit suorittaa nämä vaiheet.
  
## <a name="enable-feedback"></a>Ota käyttöön palaute  
  
Muokkaa entiteetti käyttämään **Palautetta**. Lisätietoja: [Entiteetin muokkaaminen](edit-entities.md)
  
## <a name="add-a-subgrid-for-feedback-on-the-entity-form"></a>Lisää palautteen aliruudukko entiteettilomakkeeseen  

Oletusarvon mukaan käyttäjien on siirryttävä sen tietueen tietueluetteloon, jota varten palautetta halutaan antaa. Voit helpottaa käyttäjien palautteen antamista lisäämällä palautteen aliruudukon entiteetin lomakkeeseen.  

<!-- This is the closest I could find to a topic about adding an subgrid to a form. --> Lisätietoja: [Aliruudukon ominaisuuksien yleiskatsaus](../model-driven-apps/sub-grid-properties-legacy.md)

## <a name="add-a-rollup-field--to-the-entity-form-to-show-the-ratings"></a>Lisää entiteettilomakkeeseen koostekenttä luokitusten näyttämiseksi  

Riippuen siitä, miten haluat laskea entiteetin luokituksen, voit luoda koostekentän, joka näyttää laskee luokituksen ja lisää sen entiteetin lomakkeeseen. Lisätietoja: [Määritä koostekentät arvojen koostamista varten](define-rollup-fields.md)
  
### <a name="see-also"></a>Katso myös  
 [Anna palautetta tai luokituksia Dynamics 365 -tietueille](/dynamics365/customer-engagement/basics/submit-feedback-ratings)
