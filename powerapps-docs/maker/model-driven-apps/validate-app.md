---
title: Malliin perustuvan sovelluksen vahvistaminen ja julkaiseminen sovellusten suunnitteluohjelmalla| MicrosoftDocs
description: Opi vahvistamaan ja julkaisemaan malliin perustuva sovellus
keywords: ''
ms.date: 06/08/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 5a9ec120-9ddc-4d92-b48c-0fee8c57d3c3
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: 10
topic-status: Drafting
ms.openlocfilehash: e3802ef423e7012974c24311c36b78cd56f8ed06
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677544"
---
# <a name="validate-and-publish-a-model-driven-app-using-the-app-designer"></a>Malliin perustuvan sovelluksen vahvistaminen ja julkaiseminen sovellusten suunnitteluohjelmalla

Vahvista sovellus tarkistaaksesi sen riippuvuussuhteet, joita sovelluksen käyttö edellyttää, mutta joita ei ole vielä lisätty sovellukseen. Onnistuneen vahvistuksen jälkeen julkaiset sovelluksen. 
  
Jos olet esimerkiksi lisännyt sovellukseen asiakaspalvelun suorituskyvyn koontinäytön, joka käyttää kaavioita, kuten Yhdistelmä (prioriteetin mukaan) tai Palvelupyynnön ratkaisutrendi (päivän mukaan), joita et ole vielä lisännyt. Kun vahvistat tämän sovelluksen, saat luettelon kaikista puuttuvista pakollisista resursseista.  
  
Kun vahvistat sovelluksen, sovellusten suunnitteluohjelman pohja näyttää tiedot puuttuvista resursseista.  
  
1.  Valitse sovellusten suunnitteluohjelmassa **Vahvista**.  
  
     Ilmoituspalkki tule näkyviin ja näyttää, onko sovelluksessa virheitä tai varoituksia. Ilmoituspalkkia näyttää varoituksia, jos esimerkiksi entiteetissä ei ole lomakkeita tai näkymiä tai sovellus ei sisällä mitään osia. Virhe saattaa tulla näkyviin, jos sovellukselle ei ole määritetty sivustokarttaa. Voit julkaista sovelluksen ilman varoitusten korjaamista, mutta virheet on korjattava ennen kuin voit julkaista sovelluksen.  
  
     ![Ilmoituspalkki, joka näyttää varoitukset sovelluksessa](media/app-designer-warning-notification.png "Ilmoituspalkki, joka näyttää varoitukset sovelluksessa")  
  
     Sovellusten suunnitteluohjelma näyttää varoitusmerkin ja lukumäärän riippuvuuksista jokaiselle artefaktille tai resurssiruudulle, josta puuttuu pakollinen resurssi.  
  
     ![Puuttuvan osan varoitus sovellusten suunnitteluohjelman ruudussa](media/warning--button-on-app-designer-tile.png "Puuttuvan osan varoitus sovellusten suunnitteluohjelman ruudussa")  
  
2.  Voit lisätä tarvittavat resurssit valitsemalla **Pakollinen**-välilehden pohjan oikeassa reunassa. **Pakollinen**-välilehti näkyy, kun vähintään yksi pakollinen resurssi puuttuu sovelluksesta.  
  
     Välilehti näyttää luettelon pakollisista osista.  
  
     ![Pakollinen-välilehti, jossa näkyy luettelo sovelluksen puuttuvista osista](media/app-designer-required-components-tab.png "Pakollinen-välilehti, jossa näkyy luettelo sovelluksen puuttuvista osista")  
  
3.  Valitse lisättävät resurssit ja valitse **Lisää riippuvuussuhteet**. Kun lisäät vaaditun resurssin, kyseisessä ruudussa näkyvä lukema pienenee.  
  
    > [!NOTE]
    >  Jos sovelluksen eri osissa vaaditaan yhteistä resurssia (esimerkiksi lomake vaaditaan sekä koontinäyttöä että entiteettiä varten) ja lisäät kyseisen resurssin vain kerran koontinäytön riippuvuuspuusta, riippuvuuden lukema pienenee vain koontinäytön ruudussa, mutta ei entiteetin ruudussa. Riippuvuussuhde on kuitenkin ratkaistu kummallekin.  
    >   
    >  Valitse **Hae uusimmat riippuvuudet** ![Hae uusimmat riippuvuudet -painike sovellusten suunnitteluohjelmassa](media/app-designer-get-latest-dependencies.png "Hae uusimmat riippuvuudet -painike sovellusten suunnitteluohjelmassa") tai valitse **Vahvista** uudelleen, jotta saat uusimmat riippuvuudet. Nämä painikkeet näkyvät vasta, kun olet tallentanut sovelluksen.  
  
     Valitse **Piilota riippuvuudet**, jos et halua lisätä ehdotettuja vaadittuja osia. Kaikki ratkaisemattomat varoitukset tulevat uudelleen näkyviin, kun avaat sovelluksen sovellusten suunnitteluohjelmassa ja valitset **Vahvista** tai **Hae uusimmat riippuvuudet** ![Hae uusimmat riippuvuudet -painike sovellusten suunnitteluohjelmassa](media/app-designer-get-latest-dependencies.png "Hae uusimmat riippuvuudet -painike sovellusten suunnitteluohjelmassa").  
  
    > [!NOTE]
    >  Jos piilota riippuvuudet nyt ja haluat viedä tämän sovelluksen myöhemmin, kaikki nämä riippuvuudet tulevat näkyviin uudelleen.  
  
## <a name="publish-an-app-using-the-app-designer"></a>Sovelluksen julkaiseminen sovellusten suunnitteluohjelmalla

Julkaise sovellus, jotta se on käyttäjien käytettävissä.  
  
 Kun olet lisännyt osat sekä vahvistanut ja tallentanut sovelluksen, valitse komentopalkissa **Julkaise**. Voit myös julkaista sovelluksen [Omat sovellukset](advanced-navigation.md#my-apps) -sivun sovellusruudusta. **Muokattavat sovellukset** -näkymässä, julkaistavan sovelluksen sovellusruudun oikeassa alakulmassa, valitse **Lisäasetukset**-painike (**...** ) ja valitse sitten **Julkaise**.  
  
 Sovelluksen tilaksi muuttuu Julkaistu. Näet tämän sovellusten suunnitteluohjelman oikeassa yläkulmassa. Sovellus siirtyy **Muokattavat sovellukset** -näkymästä **Julkaistut sovellukset** -näkymään ja julkaisupäivämäärä näkyy sovellusruudussa.  
  
> [!NOTE]
> - Jos sovelluksessasi on vahvistusvirhe, virhe näkyy ilmoituspalkissa. Et voi julkaista sovellusta, ennen kuin olet ratkaissut tämän ongelman.  
> - Et voi julkaista sovellusta, ennen kuin tallennat sen.  

## <a name="next-steps"></a>Seuraavat vaiheet  
[Mallipohjaisen sovelluksen jakaminen PowerAppsilla](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app) <br/>
 [Suorita mallipohjainen sovellus mobiililaitteella](https://docs.microsoft.com/powerapps/user/run-app-client-model-driven)   
 
