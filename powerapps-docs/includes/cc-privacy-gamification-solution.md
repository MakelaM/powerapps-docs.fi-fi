Kun [!INCLUDE[pn_gamification](pn-gamification.md)] -ratkaisu asennetaan ja otetaan käyttöön, käyttöönoton suorittaneen käyttäjän tilin tunnisteet (kuten etunimi, sukunimi ja sähköpostiosoite) tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -ratkaisuun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]ssa isännöidyn [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] -palvelun todennusta varten. Tämä koskee kaikkia käyttäjiä, jotka järjestelmänvalvoja on ottanut käyttöön [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] -palvelussa. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-ratkaisu lähettää järjestelmänvalvojan määrittämät tunnuslukutiedot (KPI) [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]en, ja nämä tiedot tallennetaan rakenteiseen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilaan sekä blob-tallennustilaan.  Jokaisen käyttäjän avatar, mukautetut palkinnot ja yrityksen logo tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]en, mutta tietoja ei palauteta [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]:ään.  
  
Huomaa, että järjestelmänvalvojat ja valtuutetut käyttäjät voivat käyttää [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-tietoja, kuten puheluita, mahdollisuuksia ja varattua myyntituottoa pelien tunnuslukujen määrittämiseen. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-palvelu ei suorita [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-kutsuja ja vastaa vain tietoihin (kuten tunnuslukuja käyttäviin peleihin), jotka virtaavat takaisin [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]:ään.  
  
Järjestelmänvalvoja voi ottaa käyttöön myös julkaistavan [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] TV -suoratoiston. Pelin valvoja, joka määrittää [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] TV -suoratoiston ja ottaa julkisen suoratoiston käyttöön, sallii TV-suoratoiston kaikille internetin käyttäjille, joilla on suoratoiston linkki.  
  
Järjestelmänvalvoja voi myös poistaa [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-ominaisuuden käytöstä poistamalla tämän ratkaisun asennuksen [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] -organisaatiosta.  
  
Seuraavissa osissa esitellään [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]in käyttämät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut.  
  
[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
[Pilvipalvelut](https://azure.microsoft.com/services/cloud-services/)  
  
 **Suunnittelupalvelu (WWW-rooli)**  
  
Tämä tuo käyttöön lukuisia verkkopalveluja [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisaation ja [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]in [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponenttien välistä viestintää varten. Esimerkiksi Gamification-tiedot tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Storage -tallennustilaan.  Pelin laskenta käyttää [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)] -jonoa ja palauttaa tiedot pisteytettäviksi ja näytettäviksi palvelussa.  Asiakkaiden ja käyttäjien lataamat kuvat tallennetaan [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)] -tallennustilaan. Kaikki pyynnöt todennetaan [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -palvelun kautta.  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
Kaikki palvelut tallentavat määritystiedot [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] -säilöön.  
  
[Azure SQL Database](https://azure.microsoft.com/services/sql-database/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] tallentaa seuraavat tiedot [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Databaseen:  
  
- tunnusluvut (KPI)  
  
- pelien laskennat  
  
- organisaation (vuokraajan) tiedot.  
  
[Azure Blob Storage](https://azure.microsoft.com/services/storage/)  
  
Avatarit, yrityksen logot ja muut asiakkaiden lataamat kuvat tallennetaan [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)] -tallennustilaan.  
  
[Azure Content Delivery Network (CDN)](https://azure.microsoft.com/services/cdn/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Content Delivery Network -sisällönjakeluverkkoa toimittamaan staattista sisältöä, kuten kuvia (myös palvelimeen ladattuja kuvia kuten asiakkaiden logoja) sekä [!INCLUDE[pn_JavaScript](pn-javascript.md)]- ja CSS-koodia.  
  
[Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] käyttää [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)]-palvelua käyttäjien todentamiseen ja heidän oikeuksiensa määrittämiseen.