---
title: Ratkaisun tasojen tarkasteleminen | MicrosoftDocs
description: Lisätietoja ratkaisun tasojen käyttämisestä
keywords: null
ms.date: 04/18/2019
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

<!--note from editor: Best practice is that H1 title and title in metadata are different.    -->

# <a name="view-solution-layers"></a>Ratkaisun tasojen tarkasteleminen
Ratkaisun tasojen avulla voi tarkastella kaikkia osan muutoksia, jotka tapahtuvat ajan kuluessa ratkaisun muutosten vuoksi. Ratkaisun tasolla voi porautua tietyn osan muutetun tai muuttumattoman ominaisuuden tietoihin ja tarkastella niitä. 

Ratkaisun tasot: 
-   Voit tarkastella järjestystä, jossa ratkaisu on muuttanut osaa. 
-   Voit tarkastella osan kaikkia ominaisuuksia tietyssä ratkaisussa. Voit tarkastella myös osaan tehtyjä muutoksia. 
-   Ratkaisun tasojen avulla voi tehdä vianmäärityksen riippuvuudesta tai ratkaisun tasoihin liittyvistä ongelmista, kun ratkaisun muutoksesta kertovassa kohdassa esitellyn osan muutostiedot näytetään.

## <a name="view-the-solution-layers-for-a-component"></a>Osan ratkaisun tasojen tarkasteleminen
Voit käyttää ratkaisun tasoja ratkaisunhallinnan **Osat**-luettelosta tai **Riippuvuuden tiedot** -valintaikkunasta. 

<!--note from editor: In step 2 below, does the page display a name at top? If so, use the same capitalization in text. -->

1. Jos haluat tarkastella ratkaisutasoja **Komponentti**-luettelossa, avaa [ratkaisun hallinta](../model-driven-apps/advanced-navigation.md#solution-explorer). Valitse **Komponentit**-luettelosta komponentti, esimerkiksi **Asiakkuus**, ja valitse sitten työkaluriviltä **ratkaisun tasot**. 

   > [!div class="mx-imgBorder"] 
   > ![Ratkaisun tasot -painike](media/solution-layers-toolbar.png "Ratkaisun tasot -painike")

2. Ratkaisun taso -sivu tulee näkyviin. Se näyttää komponentin jokaisen tason, kuten **Asiakkuus**-entiteetti, joka esitetään tässä. Uusin taso näkyy ylimpänä. Valitse ratkaisun taso, jos haluat tarkastella sen tietoja. 

   > [!div class="mx-imgBorder"] 
   > ![Ratkaisun tasojen luettelo](media/solution-layers-list.png "Ratkaisun tasojen luettelo")

3. **Ratkaisun taso** -valintaikkunan **Muutetut ominaisuudet** -välilehti sisältää vain ne ominaisuudet, joita on muokattu ratkaisun tietyn tason osana. 

   > [!div class="mx-imgBorder"] 
   > ![Ratkaisun tasojen muuttuneet ominaisuudet](media/solution-layers-change-prop.png "Ratkaisun tasojen muuttuneet ominaisuudet")

4. Valitse **Kaikki ominaisuudet** -välilehti, jos haluat tarkastella ratkaisun tason kaikkia ominaisuuksia, esimerkiksi muutettuja ja muuttamattomia ominaisuuksia. 

   > [!div class="mx-imgBorder"] 
   > ![Ratkaisun tasojen kaikki ominaisuudet](media/solution-layers-all-prop.png "Ratkaisun tasojen kaikki ominaisuudet")

### <a name="see-also"></a>Katso myös
[Ratkaisujen yleiskatsaus](solutions-overview.md)
