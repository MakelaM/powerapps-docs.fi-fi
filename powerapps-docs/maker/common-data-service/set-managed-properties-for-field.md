---
title: Kenttien hallittujen ominaisuuksien määrittäminen PowerAppsissa | MicrosoftDocs
description: Lue ohjeet kenttien hallittujen ominaisuuksien määrittämiseen
ms.custom: ''
ms.date: 06/19/2018
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
ms.assetid: 4ddcfcf3-5604-4b93-a5ee-589d4fb97fa4
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: be3b04bbc324520904c765506e32d6027927e214
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39681163"
---
# <a name="set-managed-properties-for-fields"></a>Kenttien hallittujen ominaisuuksien määrittäminen PowerAppsissa

<a name="BKMK_SettingManagedProperties"></a>   

 Hallittuja ominaisuuksia käytetään vain, kun sisällytät kentät hallittuun ratkaisuun ja tuot sen toiseen ympäristöön. Näiden asetusten avulla ratkaisun tekijä voi jossain määrin hallita sitä, minkälaisen mukauttamisen hän sallii kentälle hallitun ratkaisunsa asentaville käyttäjille. Jos haluat määrittää kentän hallitut ominaisuudet, valitse valikkoriviltä **Hallitut ominaisuudet**.  
  
 **Voi mukauttaa** -asetus koskee kaikkia muita asetuksia. Jos asetuksen arvo on `False`, mitkään muut asetukset eivät ole käytössä. Kun sen arvo on `True`, voit määrittää muut mukautusasetukset.  
  
 Jos kenttää voi mukauttaa, voit määrittää seuraavien asetusten arvoksi `True` tai `False`.  
  
- **Näyttönimeä voi muokata**  
  
- **Voi muuttaa vaatimustasoa**  
  
- **Voi muuttaa lisäominaisuuksia**.  
  
 Nämä asetukset ovat itsestäänselviä. Jos määrität kaikkien yksittäisten asetusten arvoksi `False`, voit myös määrittää **Voi muuttaa lisäominaisuuksia** -asetuksen arvoksi `False`.  

 ## <a name="next-steps"></a>Seuraavat vaiheet

 [Luo ja muokkaa kenttiä](create-edit-fields.md)