---
title: Näkymien mallipohjaisen sovelluksen hallitut ominaisuudet PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten voit määrittää näkymän hallitut ominaisuudet'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-managed-properties-for-views"></a>Näkymien mallipohjaisen sovelluksen hallitut ominaisuudet

<a name="BKMK_ManagedProperties"></a>   
 
 Jos luot PowerAppsissa mukautetun julkisen näkymän, jonka haluat sisällyttää hallittuun ratkaisuun, jonka jaat, voit halutessasi rajoittaa kenen tahansa ratkaisusi asentavan mahdollisuuksia näkymän mukauttamiseen.  
  
 Oletusarvon mukaan useimmissa näkymissä niiden **Muokattava** hallitun ominaisuuden arvo on true, jotta ihmiset voivat mukauttaa niitä. Ellei sinulla ole hyvä syy muuttaa tätä ominaisuutta, on suositeltavaa, että sallit käyttäjien mukauttaa sovelluksesi näkymiä.  
  
## <a name="set-managed-properties-for-a-view"></a>Näkymien hallittujen ominaisuuksien määrittäminen  
  
1.  Avaa [sovelluksenhallinta](advanced-navigation.md#solution-explorer), laajenna **Entiteetit**, valitse haluamasi entiteetti ja valitse sitten **Näkymät**.  
  
2.  Valitse muokattu julkinen näkymä.  
  
3.  Valitse pikavalikossa **Lisää toimintoja** > **Hallitut ominaisuudet**.  

    > [!div class="mx-imgBorder"] 
    > ![hallitut ominaisuudet -valikko](media/managed-properties.png)
  
4.  Määritä **Mukautettavissa**- tai **Voi poistaa** -asetuksen arvoksi **Tosi** tai **Epätosi**.  

    > [!div class="mx-imgBorder"] 
    > ![Hallittujen ominaisuuksien määrittäminen](media/set-managed-properties.png)
  
> [!NOTE]
> Asetus ei tule voimaan, ennen kuin viet näkymän sisältävän ratkaisun hallittuna ratkaisuna ja asennat sen eri ympäristöön.  

## <a name="next-steps"></a>Seuraavat vaiheet
[Tietoja näkymistä](create-edit-views.md)
