---
title: Koodi komponenttien lisääminen kenttään tai entiteettiin | Microsoft Docs
description: Koodi komponenttien tuonti prosessi
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.openlocfilehash: 63ecdde21328219b70af04b9b65edbb3073f3025
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72347034"
---
# <a name="add-code-components-to-a-field-or-entity-in-model-driven-apps"></a>Koodi komponenttien lisääminen kenttään tai entiteettiin mallipohjaisissa sovelluksissa

Koodi komponenttien avulla voit muuntaa kenttiä, jotka sisältävät perinteisesti tekstiä Visualisointeihin. Koodi komponenttien avulla voit myös muuntaa tieto joukkoja, kuten näkymää, näyttämään visualisoinnin hahmontamisena tietueiden luettelon sijaan. koodi komponentit voivat näkyä visualisoinneissa lomakkeissa, koonti näytöissä, näkymissä ja Homepage-ruudukoissa. 


   > [!div class="mx-imgBorder"] 
   > ![Mukautetun liuku säätimen ohjaus]objektin(../../maker/model-driven-apps/media/slider-control.PNG "liuku säädin kentälle")

## <a name="add-a-code-component-to-a-field"></a>Koodi osan lisääminen kenttään

Tämän toiminto sarjan vaiheiden jälkeen voit muuttaa **budjetti summa** -kentän oletus nimi-ja teksti ruutu-kenttää mahdollisuus-entiteetin liuku säädin koodi-komponentiksi. Voit samanlaisten vaiheiden avulla korvata aiemmin luodun kentän koodi komponentilla tai määrittää koodi osan mukautettua kenttää varten.

1. Avaa ratkaisunhallinta.

2. Laajenna **entiteetit**, Laajenna haluamasi entiteetti, kuten **mahdollisuus** -entiteetti, valitse **lomakkeet**ja avaa sitten lomake, kuten **päälomake** .

3. Kaksoisnapsauta lomake-editorissa kenttää, johon haluat lisätä koodi komponentin, kuten **budjetin summa** -kentän mahdollisuuden päälomakkeessa. Vaihtoehtoisesti voit luoda mukautetun kentän.

4. Valitse **kentän ominaisuudet** -sivulla **ohjaus painikkeet** -väli lehti ja valitse sitten **Lisää ohjaus objekti**.

5. Valitse Lisää ohjaus objekti-sivulla haluamasi komponentti, kuten **lineaarinen liuku säädin** -osa, ja valitse sitten **Lisää**.

   > [!div class="mx-imgBorder"] 
   > ![Lisää lineaarinen liuku säädin-ohjaus objektin](../../maker/model-driven-apps/media/add-slider.PNG "lineaarinen liuku säädin")

6. Valitse asiakas, jossa haluat komponentin näkyvän.

   - **Verkko**. Jos haluat, että koodi komponentti on käytettävissä miltä tahansa verkko selaimesta, Valitse komponentin viereinen verkko asetus. Huomaa, että www-asetuksen asettaminen sisältää komponentin hahmontamisen verkko selaimissa tieto koneissa, Macissa ja mobiililaitteissa.

   - **Puhelin**. Jos haluat, että koodi komponentti on käytettävissä puhelimissa, joissa on käytössä Dynamics 365, Valitse komponentti-kohdan vieressä oleva Puhelin-vaihto ehto.

   - **Tabletti**. Jos haluat, että koodi komponentti on käytettävissä tablet-laitteissa, joissa on käytössä Dynamics 365 tableteille, valitse Tablet-asetus osan vierestä.

   > [!div class="mx-imgBorder"] 
   > ![Valitse asiakas sovellukset, jotta voit tarkastella mukautettua ohjaus objektia].(../../maker/model-driven-apps/media/choose-client.png "Valitse asiakas sovellukset, jotta voit tarkastella mukautettua ohjaus objektia") 

7. Valitse kynä kuvake **pienin**-, **suurin**-ja **Vaihe**-kohdan vieressä, aseta ominaisuus asetus ja valitse sitten **OK**.  
   
   > [!div class="mx-imgBorder"] 
   > ![Mukautettujen ohjaus objektien ominaisuuksien lisääminen](../../maker/model-driven-apps/media/ccf-add-properties.png "mukautettujen ohjaus objektien ominaisuuksien") lisääminen

   - **Vähimmäisarvo** Valitse pienin hyväksytty arvo. Voit sitoa staattista arvoa, jonka syötät tai sidot arvon aiemmin luotuun kenttään. Tässä esimerkissä **sidonta staattiseen arvoon** on **Valuutta** , ja pienin arvo, joka voidaan syöttää, on *nolla*.  
  
       - **Sido staattiseen arvoon**. Valitse tieto tyyppi, kuten kokonaisluku (koko. ei mitään), valuutta, liuku luku (FP) tai desimaalimuoto. Anna seuraavaksi luku, joka edustaa kentän pienintä hyväksyttyä arvoa.  
  
       - **Sido kentän arvoihin**. Valitse luettelosta kenttä, jota käytetään pienin hyväksytty-arvona.  
  
   - **Enintään**. Valitse kentän suurin hyväksytty arvo. Kuten pienin-arvo, voit sitoa staattista arvoa, jonka syötät tai sidot arvon aiemmin luotuun kenttään edellä kuvatulla tavalla. Tässä esimerkissä **sidonta staattiseen arvoon** on **Valuutta** , ja enimmäisarvo, joka voidaan syöttää, on **1 000 000 000**.  
  
   - **Vaihe**. Tämä edustaa yksikköä, joka kasvaa tai pienentää nykyistä arvoa lisättäessä tai vähentämällä. Voit esimerkiksi valita budjetti summasta 100 dollarin increment\depienit.  
  
   - **Piilota oletus ohjaus objekti**. Jos valitset tämän vaihto ehdon, komponentti tai tiedot eivät näy missään niistä asiakkaista, jotka eivät tue koodi komponenttia.   
  
8. Valitse **OK**, jos haluat sulkea kentän ominaisuudet-sivun.  
  
9. Jos haluat aktivoida mukauttamisen, valitse entiteettilomakkeessa **Tallenna**ja valitse sitten **Julkaise**.  
  
10. Sulje lomake-editori valitsemalla **Tallenna ja sulje** .  
  
## <a name="add-code-component-to-an-entity"></a>Koodi osan lisääminen entiteettiin

Lisää koodi komponentti, kuten tieto joukko komponentti tai yksinkertainen taulukko-osa ruudukkoon tai näkymään, noudattamalla seuraavia vaiheita:

  - Siirry **asetuksiin > mukautukset** -kohtaan ja valitse **Mukauta järjestelmää**.
  - Napsauta **entiteetit** -väli lehden vieressä olevaa nuolta ja valitse entiteetti, johon haluat lisätä koodi komponentin. 
  - Napsauta **ohjaus painikkeet** -väli lehteä ja valitse **Lisää ohjaus objekti**.
  - Valitse Lisää ohjaus objekti-sivulla haluamasi komponentti, kuten yksinkertainen taulukko komponentti, ja valitse sitten **Lisää**.
  - Valitse asiakas, jossa haluat komponentin näkyvän.


## <a name="see-the-code-component-in-action"></a>Tarkastele toiminto koodi komponenttia  

 Avaa tietue, joka sisältää koodi komponentin sisältävän kentän, kuten edellisen esimerkin mahdollisuus-lomakkeen, ja Katso, miten kenttää muutetaan. Kenttää hahmonnetaan nyt liuku säädin komponentiksi teksti kentän sijaan.  

> [!div class="mx-imgBorder"] 
> ![Liuku säätimen ohjaus objektin]hahmonnettu lomake-(../../maker/model-driven-apps/media/slider-control.PNG "ohjaus objektin") muodossa  

### <a name="see-also"></a>Katso myös

[Komponenttien toteuttaminen TypeScript-kohteessa](implementing-controls-using-typescript.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](overview.md)