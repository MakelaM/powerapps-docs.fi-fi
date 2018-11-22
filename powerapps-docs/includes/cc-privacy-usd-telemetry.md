Auta [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] -ratkaisun parantamisessa -ominaisuus lähettää [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] -käytön tietoja, kuten käyttöjärjestelmä- ja selaintiedot sekä [!INCLUDE[pn_unified_service_desk](../includes/pn-unified-service-desk.md)]in sovelluskohtaiset tiedot ja [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] versiotiedot tietokoneesta, johon asiakasohjelma on asennettu. [!INCLUDE[pn_unified_service_desk](pn-unified-service-desk.md)] lähettää tiedot [!INCLUDE[cc_Microsoft](cc-microsoft.md)]ille käyttämällä suojattua yhteyttä Organisaatiotoiminnot-sovellukseen ja tallentamalla ne [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-taulukkosäilöön.
  
> [!NOTE]
>  Organisaationäkemysten avulla [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisaation järjestelmänvalvoja saa nopean yleiskuvauksen siitä, miten organisaatiota käytetään. Järjestelmänvalvoja voi katsoa aktiivisimmat käyttäjät, käynnistettyjen SDK-pyyntöjen määrän sekä SDK-käyttäjien tarkastelemien kohteiden määrän.
  
 Auta Unified Service Desk -ratkaisun parantamisessa -toimintoon liittyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut on lueteltu alla.  
  
> [!NOTE]
>  Katso lisätietoja muista [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-palveluista [Microsoft Azure Trust Centerissä](https://azure.microsoft.com/en-us/support/trust-center/).  
  
 [Pilvipalvelut](https://azure.microsoft.com/en-us/services/cloud-services/)OrgInsights Data REST -ohjelmointirajapinta (verkkorooli)  
  
 Tämä verkkorooli hyväksyy pyynnöt kaavioista, jotka näyttävät tiedot organisaationäkemyksissä. Ohjelmointirajapinta lukee koostetut tiedot [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-taulukoista ja palauttaa ne.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/en-us/services/storage/blobs/)  
  
 Valvonta-agentti (joka on käytössä jokaisessa skaalausryhmän tietokoneessa) kerää [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisaation raakatelemetriatiedot ja lataa ne Bond-muodossa (binaarimuodossa) [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -tallennustilaan.  
  
 [Azure-taulukkosäilö](https://azure.microsoft.com/en-us/services/storage/tables/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -tallennustilan raakatelemetriatiedot koostetaan ja tallennetaan Azure-taulukkotallennustilaan, jota pilvipalvelu lukee.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Organisaationäkemykset käyttävät [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -palvelua WWW-palvelujen todentamiseen.  
  
 [Azuren palveluväylä](https://azure.microsoft.com/en-us/services/service-bus/)  
  
 Valvonta-agentti luo viestit ja siirtää ne jonoon aina, kun se lataa tietoja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -tallennustilaan. CMA-putki poimii nämä viestit ladattuihin koostetietoihin.