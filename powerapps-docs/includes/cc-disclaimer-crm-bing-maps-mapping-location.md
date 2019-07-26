---
ms.openlocfilehash: f1c11fd086a91db6dc0d0629549166bbba547dee
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67226493"
---
## <a name="mapping-functions-for-dynamics-365-customer-engagement-plan"></a>Dynamics 365 Customer Engagement -sopimuksen kartoitustoiminnot 
 Kenttäpalvelussa ja projektipalvelujen automatisoinnissa on keskeisiä toimintoja, jotka ovat riippuvaisia sijainnista. Tällaisia ovat esimerkiksi palvelutilien (jotka määrittävät, missä palvelut tai tehtävät tapahtuvat) sijainti tai resurssien (palvelut tai tehtävät suorittavien ihmisten) alku- ja loppusijainti.  Jotta järjestelmä voisi näyttää nämä sijainnit kartalla tai laskea etäisyydet tiettyjen pisteiden välillä, on tarpeen käyttää kartoituspalvelua (joka on tässä tapauksessa Bing Maps).  
  
 Alla esitetään Bing Maps -palveluun lähetettyjen tietojen ja palvelun vastausten työnkulku:  
  
|Dynamics 365:stä lähetetyt tiedot|Bing Mapsin vastaus|Huomautus|  
|-----------------------|-----------------------|----------|  
|Osoite (asiakas tai resurssi)|Osoitteen (sijainnin) leveysaste ja pituusaste|Tätä kutsutaan osoitteen geokoodaukseksi.|  
|Sijaintijoukko (leveysaste ja pituusaste)|Sijaintien välinen etäisyys|Tätä toimintoa voidaan käyttää optimaalisten reittien etsimiseen resursseille tai matka-aikojen laskemiseen.|  
|Sijaintijoukko (leveysaste ja pituusaste)|Karttanäkymä, jossa sijainnit näkyvät kartalla nastoina|Tätä toimintoa käytetään asiakkaiden ja resurssien tarkastelemiseen karttanäkymässä.|  
  
> [!NOTE]
>  Bing Maps -palveluun ei lähetetä muita tietoja yllä esitettyjen lisäksi.
