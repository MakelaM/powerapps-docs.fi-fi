Kun otat käyttöön Osuvuushaku-toiminnon, [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] -ilmentymän osallistuvien entiteettien ja määritteiden synkronointi ja tallentaminen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-hakuindeksiin aloitetaan.  
  
 Osuvuushaku on oletusarvoisesti poissa käytöstä. Järjestelmänvalvojan on otettava ominaisuus käyttöön [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] -ilmentymässä. Kun osuvuushaku on käytössä, järjestelmänvalvojat ja järjestelmän mukauttajat voivat hallita täysin, mitä tietoja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-hakuindeksiin synkronoidaan.  
  
 Järjestelmän mukauttajat voivat valita **mukautustyökalujen** **Määritä osuvuushaku** -valintaikkunassa tietyt entiteetit hakuun ja määrittää sitten pikahakunäkymät näille entiteeteille haettavissa olevien määritteiden valintaa varten. Tietojen muutokset synkronoidaan jatkuvasti [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]:n ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-haun välillä käyttämällä suojattua yhteyttä.  Määritystiedot salataan ja edellytetyt salaiset tiedot tallennetaan [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] -säilöön.  
  
 Seuraavissa osissa esitellään Osuvuushaku-toimintoon liittyvät Azure-komponentit ja -palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure-hakupalvelut](https://azure.microsoft.com/services/search/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-hakuindeksin avulla tuotetaan laadukkaita hakutuloksia nopeasti.  [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-haku lisää [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]en tehokkaat ja hienostuneet uuden sukupolven hakuominaisuudet.  Tämä on [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]n ulkopuolinen hakupalvelu, jonka [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)] tarjoaa käyttöön. Kaikki uudet [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n hakuindeksit salataan levossa.  Jos suostumus on annettu aiemmin kuin 24.1.2018, tiedot on indeksoitava uudelleen. Se edellyttää, että suostumuksen antaminen osuvuushaulle peruutetaan. Tämän jälkeen odotetaan tunti ja annetaan suostumus uudelleen.  
  
 [Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
 Osuvuushaku käyttää [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] -tietokantaa seuraavien tietojen tallentamiseen:  
  
-   määritystiedot, jotka liittyvät organisaatioon ja vastaavaan indeksiin  
  
-   metatiedot, jotka liittävät hakupalvelun ja indeksit toisiinsa  
  
-   osoittimet järjestelmän metatietoihin ja tietoihin synkronoinnin muuttuessa  
  
-   valtuutustiedot rivitason suojauksen parantamiseksi.  
  
[Azure Tapahtumatoiminnot](https://azure.microsoft.com/services/event-hubs/)  
  
[!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)] -komponenttia käytetään [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]n ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n välisessä viestinnässä ja synkronointiprosessin hallinnoimien työkohteiden ylläpidossa. Kukin viesti tallentaa tiedot (esimerkiksi organisaatiotunnuksen ja entiteetin nimen), joita käytetään tietojen synkronointiin.  
  
[Azure Service Fabric Cluster](https://azure.microsoft.com/services/service-fabric/)  
  
Tietojen käsittelyn ja indeksoinnin hoitavat mikropalvelut, jotka on otettu käyttöön suorituksenaikaisen palvelurakenteen hallinnoimissa näennäiskoneissa. Myös haun ohjelmointirajapintoja ja tietojen synkronointiprosessia isännöidään palvelurakenneklusterissa.  
  
Palvelurakenne syntyi Microsoftin vuosien mittaisen tehtävänmukaisten pilvipalveluiden toimittamisen kokemuksen tuloksena, ja sitä on nyt käytetty tuotannossa yli viisi vuotta. Se on perusteknologiaa, jonka avulla [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n perusinfrastruktuuri suoritetaan. Palveluiden tehostamisessa käytetään seuraavia ohjelmia: [!INCLUDE[pn_skype_for_business](pn-skype-for-business.md)], [!INCLUDE[pn_intune](pn-intune.md)], [!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)], [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Data Factory, [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] DocumentDB, [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] ja [!INCLUDE[pn_cortana](pn-cortana.md)], joka voi tehdä yli 500 miljoonaa arviointia sekunnissa.  
  
[Azure-näennäiskoneiden skaalausjoukot](https://azure.microsoft.com/services/virtual-machine-scale-sets/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-näennäiskoneiden skaalausjoukot ovat joustavia ja suunniteltu tukemaan nopeasti skaalautuvia työmääriä. [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -klusterit suoritetaan näennäiskoneiden skaalausjoukoissa. Tietojen käsittelyn ja indeksoinnin mikropalveluita isännöidään skaalausjoukoissa ja hallitaan suorituksenaikaisessa palvelurakenteessa.  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
[!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] -säilöä käytetään varmenteiden, avaimien ja muiden hakuprosessissa käytettävien salattavien kohteiden suojattuun hallintaan.  
  
[Azure-tallennustila (Blob-tallennustila)](https://azure.microsoft.com/services/storage/blobs/?b=16.38)  
  
Muutokset asiakastietoihin tallennetaan enintään kahden päivän ajaksi [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)] -tallennustilaan.  Blob-objektit salataan hyödyntämällä [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilan SDK:n uusinta ominaisuutta, joka tarjoaa sekä symmetrisen että asymmetrisen salauksen tuen sekä integroinnin [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)]in kanssa. Muistiinpanojen ja liitteiden sähköpostiviestien ja tapaamisten asiakirjat synkronoidaan myös Blob-tallennustilaan [!INCLUDE[pn_crm_8_2_0_online_subsequent](pn-crm-8-2-0-online-subsequent.md)] -sovelluksen avulla.  
  
[Azure Active Directory -palvelu](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -palvelua käytetään todennukseen [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]n ja [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)] -palvelujen välillä.  
  
[Azuren kuormituksen tasaus](https://azure.microsoft.com/services/load-balancer/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n kuormituksen tasausta käytetään jakamaan saapuvaa liikennettä pilvipalveluiden toimiville palveluesiintymille tai kuormituksen tasapainotuksen joukossa määritetyille näennäiskoneille. Osuvuushaku käyttää tätä ominaisuutta tasatessaan kuormitusta käyttöönoton päätepisteissä.  
  
[Azure-näennäisverkot](https://azure.microsoft.com/documentation/articles/virtual-networks-overview/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-näennäisverkko yhdistää palvelurakenneklusterin yhdessä tai useammassa aliverkossa suoritettavat näennäiskoneet. Suojauskäytäntöjä, DNS-asetuksia, reititystauluja ja IP-osoitteita hallitaan täysin tämän näennäisverkon sisällä. Näennäisverkossa suojaussäännöt otetaan käyttöön verkon suojausryhmien avulla. Nämä säännöt joko sallivat tai estävät verkkoliikenteen näennäisverkon näennäiskoneisiin.