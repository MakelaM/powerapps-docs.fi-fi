Kun asennat [!INCLUDE[pn_connected_field_service_msdyn365](pn-connected-field-service-msdyn365.md)], -sovelluksen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -tilauksen tietojen antamisen yhteydessä, pakolliset [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -resurssit (esitelty yllä) otetaan käyttöön ja [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] -ilmentymä lähettää tiedot (kuten komennot ja rekisteröinnit) [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]lle. Näin otetaan käyttöön skenaariot, joissa on käytössä IoT ja jotka rekisteröivät laitteet ja lähettävät komennot rekisteröityihin laitteisiin ja vastaanottavat niitä. Järjestelmänvalvoja voi poistaa Connected Field Service -sovelluksen asennuksen, poistaa toiminnot ja siirtyä sitten [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-portaaliin. Portaalissa järjestelmänvalvoja voi hallita liittyviä [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-palveluita, joita ei enää tarvita.  
  
 Seuraavissa osissa esitellään Connected Field Service -toiminnoissa käytettävät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Palveluväylän jono](https://azure.microsoft.com/documentation/articles/service-bus-dotnet-get-started-with-queues/)  
  
 Tämä mahdollistaa jonon [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]- ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-sovelluksen välisille saapuville ja lähteville viesteille (komennoille). Kun IoT-hälytys lähetetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovellukseen tai [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovelluksesta lähetetään komento IoT-keskukseen, jono muodostuu tähän.  
  
 [Logic Apps](https://azure.microsoft.com/services/logic-apps/)  
  
 Sisältää orkestrointipalvelun, joka käyttää [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -yhdysohjelmaa ja jonon yhdysohjelmaa. [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -yhdysohjelmia käytetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovelluksessa käytettävien entiteettien muodostamisessa ja jonon yhdysohjelmia jonoon liittyvissä kyselyissä.  
  
 [Stream analytics](https://azure.microsoft.com/services/stream-analytics/)  
  
 Sisältää täysin hallinnoidun reaaliaikaisen tapahtumien käsittelyohjelman, jonka avulla voit poistaa kattavien merkityksellisten tietojen lukituksen. Stream Analytics -sovelluksen avulla reaaliaikaisen analyysin laskennat on helppo määrittää esimerkiksi laitteista, sensoreista, verkkosivustoista, yhteisöpalvelusta, sovelluksista, infrastruktuurijärjestelmistä saatavalle tiedolle. Tämä toimii suppilona, jonka avulla valitut IoT-hälytykset lähetetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:ään.  
  
 [IoT-keskus](https://azure.microsoft.com/services/iot-hub/)  
  
 Connected Field Services käyttää IoT-keskusta rekisteröityjen laitteiden ja resurssien tilojen hallinnassa. Lisäksi IoT-keskus lähettää komennot ja ilmoitukset liitettyihin laitteisiin sekä seuraa sanomien toimitusta ja kuittausten vastaanottoja. Laitesanomat lähetetään kestävällä tavalla ajoittain liitettynä oleviin laitteisiin.  
  
 **Simulaattori**  
  
 Tämä on testi-WWW-sovellus, joka emuloi komentoja IoT-keskukseen lähettävää tai komentoja sieltä vastaanottavaa laitetta.  
  
 [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
 Connected Field Service käyttää SQL [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]a laitteen sykesanomien tallennuksessa. PowerBI käyttää niitä myöhemmin näyttäessään[!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:n laitteiden tilan.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/services/storage/)  
  
 Stream Analytics -sovelluksen käyttämät kyselyt tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön.