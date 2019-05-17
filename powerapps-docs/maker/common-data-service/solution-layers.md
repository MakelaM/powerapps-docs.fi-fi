---
title: Ratkaisun tasojen tarkasteleminen | MicrosoftDocs
description: Lisätietoja ratkaisun tasojen käyttämisestä
keywords: null
ms.date: 04/10/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
  - powerapps
ms.assetid: null
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="view-solution-layers"></a>Ratkaisun tasojen tarkasteleminen
Ratkaisun tasojen avulla voi tarkastella kaikkia osan muutoksia, jotka tapahtuvat ajan kuluessa ratkaisun muutosten vuoksi. Ratkaisun tasolla voi porautua tietyn osan muutetun tai muuttumattoman ominaisuuden tietoihin ja tarkastella niitä. 

Ratkaisun tasojen avulla voi tehdä seuraavaa: 
-   Voit tarkastella järjestystä, jossa ratkaisu on muuttanut osaa. 
-   Voit tarkastella osan kaikkia ominaisuuksia tietyssä ratkaisussa. Voit tarkastella myös osaan tehtyjä muutoksia. 
-   Ratkaisun tasojen avulla voi tehdä vianmäärityksen riippuvuudesta tai ratkaisun tasoihin liittyvistä ongelmista, kun ratkaisun muutoksesta kertovassa kohdassa esitellyn osan muutostiedot näytetään.

## <a name="view-the-solution-layers-for-a-component"></a>Osan ratkaisun tasojen tarkasteleminen
Voit käyttää ratkaisun tasoja ratkaisunhallinnan **Osat**-luettelosta tai **Riippuvuuden tiedot** -valintaikkunasta. 

1. Jos haluat tarkastella ratkaisun osia **Osat**-luettelosta, [avaa ratkaisunhallinta](../model-driven-apps/advanced-navigation.md#solution-explorer), valitse **Osat**-luettelosta osa, esimerkiksi **Asiakas**, ja valitse sitten työkalurivin **Ratkaisun tasot**. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-toolbar.png "Ratkaisun tasot -painike")

2. Näyttöön avautuu Ratkaisun tasot -sivu, jolla näkyvät osan kaikki tasot, kuten tässä näytetty asiakasentiteetti. Uusin taso näkyy ylimpänä. Valitse ratkaisun taso, jos haluat tarkastella sen tietoja. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-list.png "Ratkaisun tasot -luettelo")

3. **Ratkaisun taso** -valintaikkunan **Muutetut ominaisuudet** -välilehti sisältää vain ne ominaisuudet, joita on muokattu ratkaisun tietyn tason osana. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-change-prop.png "Ratkaisun tason muutetut ominaisuudet")

4. Valitse **Kaikki ominaisuudet** -välilehti, jos haluat tarkastella ratkaisun tason kaikkia ominaisuuksia, esimerkiksi muutettuja ja muuttamattomia ominaisuuksia. 

   > [!div class="mx-imgBorder"] 
   > ![](media/solution-layers-all-prop.png "Ratkaisun tason kaikki ominaisuudet")

## <a name="see-also"></a>Katso myös
[Ratkaisujen yleiskatsaus](solutions-overview.md)