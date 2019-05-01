---
ms.openlocfilehash: 943aa1eb128341b960270d21a53cec47003bcec4
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61571881"
---
Auta parantamaan [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)]iä -toiminto lähettää [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)]in käyttötietoja, kuten käyttöjärjestelmän tietoja, selaintietoja, [!INCLUDE[pn_unified_service_desk](../includes/pn-unified-service-desk.md)]in sovelluskohtaisia tietoja ja [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)]in versiotiedon siitä tietokoneesta, johon asiakasohjelma asennetaan. [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] lähettää tiedot suojatun Organisaatiotoiminnot-yhteyden kautta [!INCLUDE[cc_Microsoft](cc-microsoft.md)]ille ja tallentaa ne [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-taulukkosäilöön.
  
> [!NOTE]
>  Organisaatiotoimintojen avulla [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisaation järjestelmänvalvoja saa nopean yleiskuvan siitä, miten organisaatiota käytetään. Järjestelmänvalvoja voi katsoa aktiivisimmat käyttäjät, käynnistettyjen SDK-pyyntöjen määrän ja SDK-käyttäjien tarkastelemien kohteiden määrän.
  
 Auta parantamaan Unified Service Deskiä -toimintoon liittyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut on lueteltu alla.  
  
> [!NOTE]
>  Katso lisätietoja muista [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-palvelutarjouksista [Microsoft Azure -luottamuskeskuksesta](https://azure.microsoft.com/en-us/support/trust-center/).  
  
 [Pilvipalvelut](https://azure.microsoft.com/en-us/services/cloud-services/) OrgInsights Data REST -ohjelmointirajapinta (verkkorooli)  
  
 Tämä verkkorooli hyväksyy pyynnöt kaavioista, jotka näyttävät tiedot organisaatiotoiminnoissa. Ohjelmointirajapinta lukee koostetut tiedot [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-taulukoista ja palauttaa ne.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/en-us/services/storage/blobs/)  
  
 Valvonta-agentti (joka on käytössä jokaisessa skaalausryhmän tietokoneessa) kerää [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisaation raakatelemetriatiedot ja lataa ne Bond-muodossa (binaarimuodossa) [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön.  
  
 [Azure-taulukkosäilö](https://azure.microsoft.com/en-us/services/storage/tables/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilön raakatelemetriatiedot koostetaan ja tallennetaan Azure-taulukkosäilöön, jota pilvipalvelu lukee.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Organisaatiotoiminnot käyttävät [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]a verkkopalvelujen todentamiseen.  
  
 [Azuren palveluväylä](https://azure.microsoft.com/en-us/services/service-bus/)  
  
 Valvonta-agentti luo viestit ja siirtää ne jonoon aina, kun se lataa tietoja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön. CMA-putki poimii nämä viestit ja koostaa ladatut tiedot.