---
ms.openlocfilehash: 509ad3f5b1b94378b2c6fd7661510b7aef0e3a23
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61570593"
---
Kun otat oppimispolun laatimisen käyttöön organisaatiolle palvelussa [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], käyttäjien luoma (oikeilla käyttöoikeuksilla) oppimispolkusisältö (julkaistu tai luonnosvaiheessa oleva) tallennetaan palveluun [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)]. Kun otat toiminnon käyttöön, [!INCLUDE[pn_azure_cloud_services](pn-azure-cloud-services.md)] voi tallentaa myös seuraavat organisaatioon liittyvät tiedot palvelussa [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:  
  
-   vuokraajan organisaatioiden luettelo  
  
-   loppukäyttäjien asiakasohjelmaversiot ([!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]) ja soveltuvat selain- ja käyttöjärjestelmätiedot  
  
-   loppukäyttäjien käyttötiedot, esimerkiksi oppimispolussa käytetty aika tai tallennetut napsautukset  
  
-   koostetut loppukäyttäjien käyttötiedot, esimerkiksi sijainti, käyttöoikeusrooli ja kieli  
  
-   koostetut loppukäyttäjien käyttötiedot, esimerkiksi sijainti, käyttöoikeusrooli ja kieli  
  
-   sanatarkka palaute loppukäyttäjiltä.  
  
 Järjestelmänvalvoja voi ottaa oppimispolun laatimisen käyttöön (ja myöhemmin poistaa sen käytöstä) **järjestelmäasetusten** valintaikkunan **Yleinen**-välilehdessä.  
  
 Seuraavissa osioissa esitellään oppimispolun laadintaan liittyvät palvelun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]komponentit ja palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Pilvipalvelut](https://azure.microsoft.com/en-us/services/cloud-services/)  
  
 **Verkkopalvelu**  
  
 Verkkopalvelu tarjoaa ohjausobjektit, jotka oppimispolun suorituspalvelu näyttää. Verkkopalvelu tukee myös suunnitteluohjelman ohjelmointirajapintaa, jota oppimispolun laadinta käyttää. Palvelu tallentaa nämä ohjausobjektit palveluun [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)].  
  
 **Kääntäjä (työntekijän rooli)**  
  
 Kääntäjärooli hallitsee ohjausobjektin julkaisua julkaisuryhmään. Kääntäjää tallentaa viestit julkaisutyöstä jonoon. Tulokset tallennetaan palveluun [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)].  
  
 [Azure SQL -tietokanta](https://azure.microsoft.com/en-us/services/sql-database/)  
  
 Oppimispolku tallentaa palvelun [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] avulla  
  
-   oppimispolun luomat ohjausobjektit  
  
-   oppimispolun laadintaan liittyvät määritykset.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Oppimispolku todentaa verkkopalvelun palvelun [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] avulla.  
  
 [Azure-liikennehallinta](https://azure.microsoft.com/en-us/services/traffic-manager/)  
  
 Oppimispolku käyttää palvelun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] liikennehallintaa, jolla se tasapainottaa verkkopalvelun kuormituksen käytettävyyden ja suorituskyvyn takaamiseksi.  
  
 [Azure-tallennusjono](https://azure.microsoft.com/en-us/services/storage/)  
  
 Palvelun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] tallennusjonon avulla koordinoidaan viestintää verkkopalvelun ja kääntäjäroolien välillä.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/en-us/services/storage/)  
  
 Oppimispolku tallentaa staattisen sisällön (asiakaspään [!INCLUDE[pn_JavaScript](pn-javascript.md)], kuvat, CSS-sisältö) palvelun [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)] avulla.  
  
 [Azure-sisältöverkko (CDN)](https://azure.microsoft.com/en-us/services/cdn/)  
  
 Asiakaspään staattinen sisältö ([!INCLUDE[pn_JavaScript](pn-javascript.md)], kuvat ja CSS-tiedostot) tallennetaan välimuistiin CDN:n avulla, jotta ne voidaan tarjota maailmanlaajuisen CDN-verkon kautta.