---
title: Mallipohjaisen sovelluksen näkymien hallitut ominaisuudet PowerAppsissa | MicrosoftDocs
description: Opi määrittämään näkymän hallittuja ominaisuuksia
ms.custom: ''
ms.date: 06/12/2018
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
ms.assetid: a9014576-8fb2-4f28-b8bb-5d2d49d76e12
caps.latest.revision: 25
ms.author: matp
manager: kvivek
ms.openlocfilehash: 9f33212ae81de0418dfc3695d5ae3c8e5acf36da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677192"
---
# <a name="model-driven-app-managed-properties-for-views"></a>Mallipohjaisen sovelluksen näkymien hallitut ominaisuudet

<a name="BKMK_ManagedProperties"></a>   
 
 Jos luot mukautetun julkisen näkymän PowerAppsissa ja haluat sisällyttää sen jaettavaan hallittuun ratkaisuun, voit halutessasi rajoittaa tapoja, joilla ratkaisusi käyttäjät voivat mukauttaa näkymää.  
  
 Useimmissa näkymissä **Mukautettava** hallittu ominaisuuden arvo on oletusarvoisesti True, jotta ihmiset voivat mukauttaa niitä. Ellei sinulla ole hyvää syytä muuttaa tätä, suosittelemme, että sallit käyttäjien mukauttaa näkymiä sovelluksessasi.  
  
## <a name="set-managed-properties-for-a-view"></a>Näkymän hallittujen ominaisuuksien määrittäminen  
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer), laajenna **Entiteetit**-osio ja valitse haluamasi entiteetti. Valitse sitten **Näkymät**.  
  
2.  Valitse mukautettu julkinen näkymä.  
  
3.  Valitse valikkoriviltä **Lisää toimintoja** > **Hallitut ominaisuudet**.  

    ![hallitut ominaisuudet -valikko](media/managed-properties.png)
  
4.  Määritä **Mukautettava**- tai **Voidaan poistaa** -asetukseksi **True** tai **False**.  

    ![Hallittujen ominaisuuksien määrittäminen](media/set-managed-properties.png)
  
> [!NOTE]
> Asetus ei astu voimaan, ennen kuin viet ratkaisun, joka sisältää näkymän hallitun ratkaisun ja asennat sen eri ympäristöön.  

## <a name="next-steps"></a>Seuraavat vaiheet
[Tutustu näkymiin](create-edit-views.md)
