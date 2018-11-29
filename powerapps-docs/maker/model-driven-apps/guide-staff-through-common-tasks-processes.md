---
title: Liiketoimintasääntöjä ja työnkulkuja sisältävän mukautetun liiketoimintalogiikan käyttäminen mallipohjaisissa sovelluksissa | MicrosoftDocs
description: 'Lue, miten voit käyttää sovelluksessa erilaisia liiketoimintalogiikkoja'
ms.custom: ''
ms.date: 08/02/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 0b4e6602-5701-4859-81cc-6f6fe50901b2
caps.latest.revision: 44
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="apply-custom-business-logic-with-business-rules-and-flows-in-model-driven-apps"></a>Liiketoimintasääntöjä ja työnkulkuja sisältävän mukautetun liiketoimintalogiikan käyttäminen mallipohjaisissa sovelluksissa

Liiketoimintaprosessien yhdenmukaistamisen määrittäminen ja pakottaminen on yksi tärkeimmistä syistä siihen, että ihmiset käyttävät malliin perustuvia sovelluksia. Yhdenmukaisten prosessien avulla varmistat, että henkilöt voivat keskittyä mallipohjaisen sovelluksen avulla töihinsä manuaalisten vaiheiden suorittamisen muistamisen sijaan. 

## <a name="business-rules"></a>Liiketoimintasäännöt

Liiketoimintasäännöt on yksinkertainen käyttöliittymä, jossa voi ottaa käyttöön ja ylläpitää nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä. Liiketoimintasäännön *vaikutusalue* määrittää, missä liiketoimintasääntö suoritetaan:

|||  
|-|-|  
|**Jos valitset tämän...**|**Vaikutusalueeksi määritetään...**|  
|**Entiteetti**|Kaikki lomakkeet ja palvelin|  
|**Kaikki lomakkeet**|Kaikki lomakkeet|  
|Tietty lomake (esimerkiksi **Asiakas**-lomake)|Kyseinen lomake| 

Lisätietoja lomakkeen liiketoimintasäännön luomisesta mallipohjaisessa sovelluksessa on kohdassa [Liiketoimintasääntöjen luomisen käyttämään logiikkaa mallipohjaisen sovelluksen lomakkeessa](create-business-rules-recommendations-apply-logic-form.md)

> [!NOTE]
> Lisätietoa entiteetin liiketoimintasäännön määrittämisestä siten, että sittä käytetään palvelintasolla sekä *kaaviosovelluksissa* että *mallipohjaisissa sovelluksissa* on kohdassa [Entiteetin liiketoimintasäännön luominen](/powerapps/maker/common-data-service/data-platform-create-business-rule).

## <a name="flows"></a>Työnkulut  
  
Microsoft Flow sisältää useita erilaisia prosesseja, joista jokainen on suunniteltu eri tarkoitukseen:  

-   Automaattiset työnkulut. Luo työnkulku, joka suorittaa vähintään yhden tehtävän automaattisesti sen jälkeen, kun tapahtuma on käynnistänyt sen. Lisätietoja: [Työnkulun luominen](/flow/get-started-logic-flow)
    
-   Painikkeen työnkulut. Suorita toistettavat tehtävät yksinkertaisesti napauttamalla painiketta mobiililaitteessa. Lisätietoja: [Painikkeiden työnkulkujen esittely](/flow/introduction-to-button-flows)
  
-   Ajoitetut työnkulut. Luo työnkulku, joka suorittaa vähintään yhden tehtävän aikataulun mukaan, esimerkiksi kerran päivässä, tiettynä päivänä tai tietyn ajan kuluttua. Lisätietoja: [Työnkulkujen suorittaminen aikataulussa](/flow/run-scheduled-tasks)
  
-   Liiketoimintaprosessit.  Luo liiketoimintaprosessi ja varmista sen avulla, että käyttäjät kirjoittavat tietoja yhdenmukaisesti ja suorittavat samat vaiheet aina, kun he käyttävät sovellusta. Lisätietoja: [Liiketoimintaprosessien yleiskatsaus](/flow/business-process-flows-overview)

-   Työnkulut ja toiminnot. Dynamics 365 Customer Engagementin mukauttajat voivat jo tuntea perinteisen CDS sovelluksille -ratkaisun prosessit. Ne ovat työnkulkuja ja toimintoja. Lisätietoja: [Työnkulun prosessien käyttäminen](/flow/workflow-processes) ja [Toimintojen yleiskatsaus](/flow/actions)
  
## <a name="next-step"></a>Seuraava vaihe

[Liiketoimintasääntöjen luominen käyttämään logiikkaa mallipohjaisen sovelluksen lomakkeessa](create-business-rules-recommendations-apply-logic-form.md)

### <a name="see-also"></a>Katso myös

[Liiketoimintalogiikan käyttäminen Common Data Service sovelluksille -ratkaisussa](../common-data-service/cds-processes.md)