---
ms.openlocfilehash: 1f6d0eb19a8127e42f1d6a8da8d8c3a452782be0
ms.sourcegitcommit: 982cab99d84663656a8f73d48c6fae03e7517321
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/28/2019
ms.locfileid: "67456930"
---
Kun otat käyttöön suhdeanalyysin, joka on upotettu älykäs toiminto, palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] asiakastiedot, mukaan lukien tiedot, joista käyttäjät voidaan tunnistaa, lähetetään ja tallennetaan palveluun [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)]. Se on Azuressa ylläpidettävä palvelu. Tiedot lähetetään, jotta palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] käyttäjien ja asiakkaiden välisten suhteiden suorituskykyilmaisimet voidaan laskea. Tiedot tallennetaan väliaikaisesti myös palveluun [!INCLUDE[pn_azure_service_fabric](pn-azure-service-fabric.md)] ja niitä käsitellään lisätulosten saamiseksi (esimerkiksi suhteiden tilasta ja trendeistä). Nämä tiedot palautetaan sitten palveluun [!INCLUDE[pn_customerinsight_short](pn-customer-insights-short.md)] ja myöhemmin myös palveluun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)].  
  
 Järjestelmänvalvoja voi ottaa suhdeanalyysitoiminnon käyttöön asentamalla sen ratkaisuksi organisaation palveluun [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]. Lisäksi järjestelmänvalvoja voi myös poistaa tämän toiminnon käytöstä poistamalla sen asennuksen organisaation palvelusta [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)].  
  
 Kun otat palvelun [!INCLUDE[pn_Exchange](pn-exchange.md)] tiedot käyttöön tietolähteenä, lähetät palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] asiakastiedot, mukaan lukien tiedot, joista käyttäjät voidaan tunnistaa, palvelusta [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)] palveluun [!INCLUDE[pn_Exchange_Online](pn-exchange-online.md)]. Näin voidaan kerätä lisätietoja, joiden avulla lasketaan suorituskykyilmaisimia ja joita käytetään muissa analyyseissa.  Jos haluat ottaa tämän toiminnon täysin käyttöön, myös palvelun [!INCLUDE[pn_Office_365](pn-office-365.md)][!INCLUDE[pn_Exchange](pn-exchange.md)] järjestelmänvalvojan täytyy hyväksyä erillinen lupalauseke sovelluksessa [!INCLUDE[pn_Exchange](pn-exchange.md)].  Kun molemmat järjestelmänvalvojat ovat antaneet suostumuksensa soveltuvissa tuotteissa, [!INCLUDE[pn_Exchange](pn-exchange.md)] tarjoaa sähköpostien ja kokousten metatiedot. Ne tallennetaan palveluun [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)] ja niitä käytetään suorituskykyilmaisimien laskemisen parantamiseen sekä mahdollisesti muihin analyyseihin, joista palvelun [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)] järjestelmänvalvoja päättää. Kun poistat palvelun [!INCLUDE[pn_Exchange](pn-exchange.md)] käytöstä tietolähteenä suhdeanalyysitoiminnossa, palvelun [!INCLUDE[pn_Exchange](pn-exchange.md)] tietoja ei poisteta palvelusta [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)].  Palvelun [!INCLUDE[pn_Exchange](pn-exchange.md)] tiedot voi poistaa palvelusta [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)] VAIN suoraan palvelussa [!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)].  
  
 Palvelun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] komponentit ja palvelut, jotka liittyvät suhdeanalyysitoimintoon, eritellään seuraavissa osioissa.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 **[!INCLUDE[pn_customerinsight_full](pn-customer-insights-full.md)]**  
  
 [!INCLUDE[pn_customerinsight_short](pn-customer-insights-short.md)] on palvelu, jota ylläpidetään palvelussa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], tallentaa palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] tiedot, mukaan lukien tiedot, joiden avulla asiakkaat voidaan tunnistaa, jotta suhdeanalyysitoiminnon tulokset voidaan laskea. Palvelun [!INCLUDE[pn_customerinsight_short](pn-customer-insights-short.md)] esikatseluversiota koskevat [nämä esikatselutoimintojen lisäkäyttöehdot](http://go.microsoft.com/fwlink/p/?LinkId=511446).  
  
 [Lue lisätietoja Customer Insights -esikatselusta](https://azure.microsoft.com/services/customer-insights/).  
  
 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)  
  
 [!INCLUDE[pn_azure_service_fabric](pn-azure-service-fabric.md)] on palvelu, joka tallentaa palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] tiedot, mukaan lukien tiedot, joiden avulla asiakkaat voidaan tunnistaa, jotta suhdeanalyysitoiminnon tulokset voidaan laskea.