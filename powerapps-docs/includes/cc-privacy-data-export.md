Kun käytät tietojen vientipalvelua ja aktivoit tietojen vientiprofiilin [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]:ssä, profiiliin lisättyjen entiteettien tiedot lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]en. Ensimmäinen synkronointi sisältää kaikki vientiprofiiliin lisättyjen entiteettien tiedot, mutta tämän jälkeen synkronointi sisältää vain uudet muutokset, joita lähetetään jatkuvasti tietojen vientipalveluun. Tietojen vientipalveluun lähetetyt tiedot tallennetaan väliaikaisesti [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] -palveluväylään ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilaan, käsitellään [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -palvelurakenteessa, ja lopuksi tiedot synkronoidaan (lisäykset, päivitykset ja poistot) [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tilauksessa määritetyn tietokannan kanssa. Kun tiedot on synkronoitu, ne poistetaan [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] -palveluväylästä ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilasta. Jos tietojen synkronoinnin aikana tapahtuu virhe, lyhyet tiedot (entiteettityyppi, tietuetunnus ja synkronoinnin aikaleima) tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilaan, jotta käyttäjä voi ladata luettelon tietueista, joita ei päivitetty.  
  
 Järjestelmänvalvoja voi milloin tahansa poistaa tietojen vientiprofiilin aktivoinnin tietojen synkronoinnin lopettamiseksi. Lisäksi järjestelmänvalvoja voi poistaa vientiprofiilin, jolloin poistetaan kaikki epäonnistuneiden tietueiden lokit ja tietojen vientipalveluratkaisun asennus. Tämän jälkeen tietojen vientipalvelua ei voi enää käyttää.  
  
 Tietojen synkronointia suoritetaan jatkuvasti [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]:n ja tietojen vientipalvelun välillä suojatun yhteyden kautta. Tiedot salataan, koska ne liikkuvat jatkuvasti [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]:n ja tietojen vientipalvelun välillä.  
  
 Seuraavissa osissa esitellään tietojen vientipalveluun liittyvät Azure-komponentit ja -palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure-palvelurakenne](https://azure.microsoft.com/services/service-fabric/)  
  
 Azure-palvelurakenne tarjoaa ohjelmointirajapinnan ja tietojenkäsittelyn [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-näennäiskoneet [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]:stä saatujen tietueiden synkronointi-ilmoitusten käsittelyyn ja niiden lisäämiseen ja päivittämiseen kohdetietokantaan tai poistamiseen kohdetietokannasta. Suorituksenaikaisen [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -palvelurakenteen hallinnoimilla näennäispalvelimilla käyttöönotetut mikropalvelut hoitavat kaikki tietojen synkronointiin liittyvät tietojenkäsittelypalvelut.  
  
 [Azuren palveluväylä](https://azure.microsoft.com/services/service-bus/)  
  
 Tämä tarjoaa palveluväylän, johon [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] lisää synkronoinnin ilmoitusviestit, jotka [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -palvelurakenteen tietojenkäsittelysolmut käsittelevät. Jokaisessa viestissä on tietoja, kuten organisaation tunnus ja tietue, johon tiedot synkronoidaan. Azuren palveluväylän tietoja ei ole salattu levon aikana, mutta ne ovat vain tietojen vientipalvelun käytettävissä.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/services/storage/)  
  
 Tiedot tallennetaan väliaikaisesti [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)] -tallennustilaan, jos tietoja on liian paljon viestiin tallennettavaksi tai jos synkronointiviestin käsittelyssä ilmenee lyhytaikaisia virheitä. Blob-objektit salataan hyödyntämällä [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilan SDK:n uusinta ominaisuutta, joka tarjoaa sekä symmetrisen että asymmetrisen salauksen tuen sekä integroinnin [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)]in kanssa.  
  
 [Azure SQL](https://azure.microsoft.com/services/sql-database/)  
  
 [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] tallentaa tietojen vientiprofiilin määritykset ja tietojen synkronoinnin mittarit.