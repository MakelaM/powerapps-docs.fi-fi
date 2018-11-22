Kun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -organisaation oppimispolun laatimistyökalu otetaan käyttöön, vaaditut käyttöoikeudet omaavien käyttäjien luoma oppimispolun sisältö (julkaistu tai luonnostilassa oleva) tallennetaan [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] -sovellukseen. Kun toiminto otetaan käyttöön, [!INCLUDE[pn_azure_cloud_services](pn-azure-cloud-services.md)] voi myös siepata seuraavat [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -organisaatioon liittyvät tiedot:  
  
-   Vuokraajan organisaatioluettelo  
  
-   Loppukäyttäjien [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -asiakasohjelma ja käytettävissä oleva selain- ja käyttöjärjestelmämääritys  
  
-   Loppukäyttäjien käyttötiedot, kuten oppimispoluilla käytetty aika ja tallennetut napsautukset  
  
-   Loppukäyttäjän koostetut tiedot – sijainti, käyttöoikeusrooli, käyttäjän kieli  
  
-   Loppukäyttäjän koostetut tiedot – sijainti, käyttöoikeusrooli, käyttäjän kieli  
  
-   Loppukäyttäjien sanallinen palaute  
  
 Järjestelmänvalvoja voi ottaa käyttöön (ja myös poistaa käytöstä) oppimispolun laatimistyökalun **Yleinen**-välilehdessä **Järjestelmäasetukset**-valintaikkunassa.  
  
 Seuraavissa osissa esitellään oppimispolun laatimistoimintoon liittyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Pilvipalvelut](https://azure.microsoft.com/en-us/services/cloud-services/)  
  
 **WWW-palvelu**  
  
 WWW-palvelut palvelevat ohjausobjekteja, jotka on hahmonnettu asiakasohjelmassa oppimispolun suorituspalvelun avulla. WWW-palvelu tukee myös suunnitteluohjelman ohjelmointirajapintaa, jota oppimispolun laatimistyökalu käyttää. Palvelu tallentaa ohjausobjektit [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] sovellukseen.  
  
 **Kääntäjä (työrooli)**  
  
 Kääntäjän rooli hallitsee ohjausobjektin julkaisua julkaisuryhmään. Kääntäjä tallentaa julkaisutyöhön liittyvät viestit jonon avulla. Tulosten tallennuspaikka on [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)].  
  
 [Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)  
  
 Oppimispolku tallentaa seuraavat kohteet [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] -tietokannan avulla:  
  
-   Oppimispolun avulla luodut ohjausobjektit.  
  
-   Määritykseen liittyvä oppimispolun laatimistyökalu.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Oppimispolku todentaa WWW-palvelun [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -sovelluksen avulla.  
  
 [Azure-liikenteenhallinta](https://azure.microsoft.com/en-us/services/traffic-manager/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-liikenteenhallintaa WWW-palvelun kuormituksen tasapainotuksessa. Tämä varmistaa käytettävyyden ja suorituskyvyn säilymisen.  
  
 [Azure-tallennuksen jono](https://azure.microsoft.com/en-us/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennuksen jonoa käytetään WWW-palvelun ja kääntäjän roolien välisen tietoliikenteen koordinoimisessa.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/en-us/services/storage/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)] -sovellusta staattisen sisällön (asiakkaan [!INCLUDE[pn_JavaScript](pn-javascript.md)], kuvat, CSS-sisältö) tallentamisessa.  
  
 [Azure-sisältöverkko (CDN)](https://azure.microsoft.com/en-us/services/cdn/)  
  
 CDN:n avulla asiakkaan staattinen sisältö ([!INCLUDE[pn_JavaScript](pn-javascript.md)], kuvat ja CSS-tiedostot) tallennetaan välimuistiin yleisen CDN-verkon käyttöä varten.