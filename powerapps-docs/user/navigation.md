---
title: Perussiirtyminen mallipohjaisessa sovelluksessa | MicrosoftDocs
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mkaur
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: a46698ddf454c9d0f563575a3553e874f3a7b109
ms.sourcegitcommit: 9a16bb75c856f7c84cd385811b7135ab2804ae69
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/03/2019
ms.locfileid: "71924537"
---
#  <a name="basic-navigation-in-a-model-driven-app"></a>Perussiirtyminen mallipohjaisessa sovelluksessa 

Siirtymispalkin avulla voit siirtyä työalueeseen, luoda uuden tietueen, hakea tai tehdä muita tehtäviä mallipohjaisessa sovelluksessa.

> [!div class="mx-imgBorder"]
> ![Mallipohjaisessa sovelluksessa siirtyminen](media/nav.png "Mallipohjaisessa sovelluksessa siirtyminen")

1. Sivustokartta on oletusarvon mukaan laajennettu ja pysyvä.
2. Kulloinenkin alialue näkyy aina korostettuna, niin että erotat, missä osassa sovellusta olet.
3. **Viimeaikaiset** ja **kiinnitetyt** kohteet ovat ylimpänä helposti käytettävissä. 
4. Alueenvaihtimen avulla voit vaihtaa sovelluksesta toiseen.
5. Kuvakkeilla on komentopalkissa omat värinsä, niin että komennot erottuvat toisistaan.
  
## <a name="get-back-to-recent-records-items-or-view"></a>Aiempiin tietueisiin, kohteisiin tai näkymään palaaminen
Käsittelet luultavasti useimmiten samoja tiettyjä tietueita. Saatat esimerkiksi käsitellä säännöllisesti samaa yhteyshenkilöä tai tiliä. Tai ehkä käsittelet samoja tietoluetteloita (näkymiä) kerta toisensa jälkeen. Sivustokartalta voit nopeasti palata viimeksi käytettyihin tietueisiin tai näkymiin. Voit myös kiinnittää tietueita ja näkymiä, jotta ne on helpompi löytää. 
  
1. Valitse **Sivustokartasta**vaihtoehto **Viimeisimmät**.
  
2. Valitse **Viimeisimmät**-kohdasta tietue, kohde tai näkymä, johon haluat palata. 

## <a name="pin-records-items-or-view"></a>Tietueiden, kohteiden tai näkymän kiinnitys

1. Valitse **Sivustokartasta** vaihtoehto **Viimeisimmät**, niin viimeksi avattujen kohteiden luettelo laajentuu.
2. Valitse Viimeisimmät-luettelon kohteen vieressä oleva kiinnityskuvake, niin kohde siirtyy kiinnitettyjen luetteloon.

   > [!div class="mx-imgBorder"]
   > ![Kiinnitetyt tietueet](media/pinnedrecords.png "Kiinnitetyt tietueet")

## <a name="unpin-records-items-or-view"></a>Tietueiden, kohteiden tai näkymän kiinnityksen poisto

1. Valitse **Sivustokartassa** vaihtoehto **Kiinnitetyt**, niin kiinnitettyjen kohteiden luettelo laajenee.
2. Valitse kohteen vieressä oleva kiinnityksen poistokuvake, niin kohde poistuu luettelosta.  

   > [!div class="mx-imgBorder"]
   > ![Tietueiden kiinnityksen poisto](media/unpinnedrecords.png "Tietueiden kiinnityksen poisto")

## <a name="record-set-navigation"></a>Tietuejoukossa siirtyminen 
Voit siirtyä useiden tietueiden halki käyttämällä valmiita näkymiä ja kyselyitä. Tietuepohjainen siirtyminen parantaa tuottavuutta, kun käyttäjät voivat siirtyä luettelossa tietueesta toiseen ja palata helposti menettämättä omaa käsittelyluetteloaan.

> [!div class="mx-imgBorder"]
> ![Tietuejoukossa siirtyminen](media/recordset.png "Tietuejoukossa siirtyminen")

## <a name="reference-panel"></a>Viitepaneeli
Viitepaneelin avulla saat työt tehtyä niin, ettei sinun tarvitse poistua työskentelyruudusta. Voit etsiä muita aiheeseen liittyviä kohteita (kuten tapauksia tai tiliin liittyviä mahdollisuuksia) tarkasteltavana olevan tietueen kontekstissa siirtymättä toiseen näyttöön.

> [!div class="mx-imgBorder"]
> ![Viitepaneeli](media/reference-panel.png "Viitepaneeli")

 Katso tämä video, niin saat lisätietoja viitepaneelista:

<div class="embeddedvideo"><iframe src="https://www.microsoft.com/en-us/videoplayer/embed/d8224c3f-6e20-4b8e-9d0d-b0f5602c7708" frameborder="0" allowfullscreen=""></iframe></div>

## <a name="notifications"></a>Notifications 

Lomakkeessa näkyy kolmenlaisia ilmoituksia: tiedottavia, varoituksia ja virheitä. Ilmoitukset ovat aina käytettävissä lomakkeen yläosassa, aivan otsikon yläpuolella.

Kun valitset virhe ilmoituksen, siirryt sen lomakkeen kenttään, jossa virhe ilmeni.

![Esimerkki ilmoituksista](media/notifications.png "Esimerkki ilmoituksista")

Jos ilmoituksia on vain yksi, näet yhden rivin.

![Esimerkki yksittäisistä ilmoituksista](media/single_notification.png "Esimerkki yksittäisistä ilmoituksista")

Jos ilmoituksia on enemmän kuin yksi, näet ilmoitusten määrän. Voit tarkastella kutakin viestiä valitsemalla nuolenkärjen.

![Esimerkki useista ilmoituksista](media/multiple_notification.png "Esimerkki useista ilmoituksista")

## <a name="grids"></a>Ruudukoissa

Unified Interface-liittymän ruudukoita on parannettu, jotta näytössä näkyvien tietojen määrää voidaan lisätä. Ruudukoissa on myös parannetut suodatus asetukset, jotka sisältävät viimeisimmän suodattimen ja lajittelu järjestyksen muistamisen. Yksityiskohtainen luettelo parannuksista on tässä blogikirjoituksessa, [parannetuilla toiminnoilla Unified Interface-ruudukoissa](https://powerapps.microsoft.com/en-us/blog/enhanced-functionality-in-unified-interface-grids).



