---
ms.openlocfilehash: 3fb3961dc88033a44c60c4b6f09124c7c38a11bf
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67212776"
---
Kun otat käyttöön Voice of the Customer for Dynamics 365:n ja julkaiset kyselyn Dynamics 365:stä, kyselyn määritys lähetetään Azureen ja tallennetaan Azure-tallennukseen. Kun vastaaja lähettää kyselyn (avaamalla kyselyyn kutsulinkin, joka on lähetetty sähköpostitse), kyselyn vastaukset tallennetaan väliaikaisesti Azuren palveluväylään, josta ne noudetaan ja tallennetaan Dynamics 365:een. Kun vastaukset on tallennettu Dynamics 365:een, ne poistetaan Azuresta.  
  
 Huomaa, että kyselyyn voidaan sisällyttää Dynamics 365 -tietoja, kuten asiakkaan nimi, tuotteen nimi, tapauksen numero jne. (kyselyn elementteihin, kuten kysymyksiin ja vastauksiin), kun kysely laaditaan vastaanottajalle. Kun kyselyn kutsulinkki on luotu, nämä Dynamics 365 -tiedot lähetetään Dynamics 365:stä ja tallennetaan Azuren SQL-tietokantaan vastaan kyselyn kutsulinkissä käytettyä tunnistetta vastaan. Tätä tunnistetta käytetään näyttämään Dynamics 365 -tiedot kyselyssä, kun kysely avataan kutsulinkin avulla. Vastaanottajalle sähköpostitse lähetetyn kyselylinkin tunnisteet tallennetaan vastaanottajan sähköpostijärjestelmään.  
  
 Järjestelmänvalvoja voi ottaa käyttöön Voice of the Customer for Dynamics 365 -ominaisuuden asentamalla sen ratkaisuna Dynamics 365 -organisaatioon. Lisäksi järjestelmänvalvoja voi poistaa tämän toiminnon käytöstä poistamalla ratkaisun asennuksen Dynamics 365 -organisaatiosta.  
  
 Seuraavissa osioissa esitellään Voice of the Customer for Dynamics 365 -toimintoon liittyvät osat ja palvelut.  
  
 Huomautus Lisä tietoja Azuren lisä palvelu tarjonnasta on Microsoft Azure valvonta keskuksessa ([https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)).  
  
 **Pilvipalvelut** ([https://azure.microsoft.com/services/cloud-services/](https://azure.microsoft.com/services/cloud-services/))  
  
 **Suunnittelupalvelu (verkkorooli)**  
  
 Tämä tarjoaa useita verkkopalveluita viestintään Dynamics 365 -organisaation ja useiden Voice of the Customer for Dynamics 365:n Azure-osien välillä.  Esimerkiksi kyselyt julkaistaan ja tallennetaan Azure Blob -säilöön.  Kyselyn vastaukset noudetaan Azuren palveluväyläjonosta ja palautetaan pysyvästi Dynamics 365 -organisaatioon.  Kaikki pyynnöt todennetaan Azure Active Directoryn avulla.  
  
 **Kyselyn suorituspalvelu (verkkorooli)**  
  
 Tämä on verkkosovellus, joka lähettää kyselyt vastaajille.  Lähetetyt kyselyn vastaukset tallennetaan väliaikaisesti Azuren palveluväyläjonoon, ennen kuin ne käsitellään asynkronisessa Dynamics 365 -palvelussa.  
  
 **Vastauksen käsittelijä (työntekijärooli)**  
  
 Tämä työntekijärooli on vastuussa kyselyvastausten raakaversioiden muuntamisesta käyttökelpoiseen muotoon Dynamics 365:ssä.  
  
 **Työnkäsittelijän (työntekijän rooli)**   Tämä työntekijä rooli on vastuussa kelvollisten kysely vastausten käsittelystä ja päivittämisestä Dynamics 365-entiteettitietueiksi. 
 
 **Azure Key Vault** ([https://azure.microsoft.com/services/key-vault/](https://azure.microsoft.com/services/key-vault/))  
  
 Kaikki pilvipalvelut tallentavat määritystiedot Azure Key Vaultiin.  Organisaation ja vuokraajan tiedot tallennetaan SQL Azureen.  
  
 **Azuren SQL-tietokanta** ([https://azure.microsoft.com/services/sql-database/](https://azure.microsoft.com/services/sql-database/))  
  
 Voice of the Customer for Dynamics 365 käyttää SQL Azurea seuraavien tietojen tallentamiseen:  
  
-   Putkessa olevat tiedot  
  
-   Kyselyn metatiedot  
  
-   Organisaation (vuokraajan) tiedot  
  
 **Azure Blob -säilö** ([https://azure.microsoft.com/services/storage/](https://azure.microsoft.com/services/storage/))  
  
 Kyselyn määritelmät ja osittain valmiit (tallennetut) vastaukset tallennetaan Azure Blob -säilöön.  
  
 **Azure-sisältöverkko (CDN)** ([https://azure.microsoft.com/services/cdn/](https://azure.microsoft.com/services/cdn/))  
  
 Voice of the Customer for Dynamics 365 -ratkaisu käyttää Azure-sisältöverkkoa toimittaakseen kyselyn suorituspalveluun staattista sisältöä, kuten kuvia (mukaan lukien lähetetyt kuvat ja asiakkaan logot), JavaScriptiä ja CSS:ää.  
  
 **Azure Active Directory** ([https://azure.microsoft.com/services/active-directory/](https://azure.microsoft.com/services/active-directory/))  
  
 Voice of the Customer for Dynamics 365 -ratkaisu käyttää Azure Active Directory -palvelua verkkopalvelujen todentamiseen.  
  
 **Azuren palveluväylä** ([https://azure.microsoft.com/services/service-bus/](https://azure.microsoft.com/services/service-bus/))  
  
 Kyselyn avaamisessa/lähetyksessä luodut sanomat tallennetaan tilapäisesti organisaation (vuokraajan) Azuren palveluväyläjonoon, kunnes Azuren työntekijärooli toimittaa kyselyn vastaukset organisaation Dynamics 365 -esiintymään ja määrittää ne Dynamics 365 -entiteettitietueiksi.
