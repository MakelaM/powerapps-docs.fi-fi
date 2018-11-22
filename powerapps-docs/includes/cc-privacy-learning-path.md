Jos otat käyttöön Oppimispolku-ominaisuuden staattisen html-sisällön, kuvia ja komentosarjoja voi tallentaa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n sisällön jakeluverkkoon (CDN). Lisäksi kaikki näytettävä dynaaminen sisältö tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis-välimuistiin, jota käytetään sisällön esitallennukseen välimuistiin [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Database -tietokannasta.  
  
 Järjestelmänvalvoja voi ottaa Oppimispolku-ominaisuuden käyttöön tai poistaa sen käytöstä [!INCLUDE[pn_crm_online_shortest](pn-crm-online-shortest.md)] -ilmentymässä käyttämällä Ota avustava ohje käyttöön -asetusta [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] -organisaatiossa.  
  
 Seuraavissa osissa esitellään Oppimispolku-toimintoihin liittyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut.  
  
> [!NOTE]
>  Katso lisätietoja muista Azure-palveluista [Microsoft Azure Trust Centerissä](https://azure.microsoft.com/en-us/support/trust-center/).  
  
 [Pilvipalvelut](https://azure.microsoft.com/en-us/services/cloud-services/)  
  
 **Oppimispolun suorituspalvelu (WWW-rooli)**  
  
 Tämä verkkosovellus tarjoaa sisällön käyttäjille.  
  
 **Oppimispolun palvelu (työrooli)**  
  
 Työrooli vastaa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL Database -tietokannasta saatujen tietojen käsittelystä ja niiden tallentamisesta välimuistiin [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis-välimuistiin.  
  
 [Azure SQL Database](https://azure.microsoft.com/en-us/services/sql-database/)  
  
 Oppimispolku käyttää SQL-tietokantaa seuraavien kohteiden tallentamiseen:  
  
-   Sisältö  
  
-   Sisällön metatiedot  
  
-   Järjestelmän metatiedot  
  
 [Azure Blob -säilö](https://azure.microsoft.com/en-us/services/storage/)  
  
 HTML-sisältö, kuvat, [!INCLUDE[pn_JavaScript](pn-javascript.md)] ja CSS tallennetaan kaikki [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön.  
  
 [Azuren sisällön jakeluverkko (CDN)](https://azure.microsoft.com/en-us/services/cdn/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n sisällön jakeluverkkoa staattisen sisällön, kuten HTML-sisällön, kuvien, [!INCLUDE[pn_JavaScript](pn-javascript.md)]in ja CSS:n, toimittamiseen kyselyn suorituspalvelulle.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -palvelua WWW-palvelujen todentamiseen erityisesti suunnittelijaa varten. Tällä hetkellä suunnittelija ei näy asiakkaille ja kumppaneille. Siksi todennus tapahtuu ainoastaan [!INCLUDE[cc_Microsoft](cc-microsoft.md)]-toimialueen sisällä.  
  
 [Azure Redis -välimuisti](https://azure.microsoft.com/en-us/services/cache/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis-välimuistia käyttäjille tarjottavan dynaamisen sisällön välimuistiin tallentamiseen.  
  
 [Azure-liikenteenhallinta](https://azure.microsoft.com/en-us/services/traffic-manager/)  
  
 Oppimispolku käyttää Traffic Manager -palvelua tärkeiden sovellusten käytettävyyden parantamiseen. Palvelu valvoo [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]a tai ulkoisia sivustoja ja palveluita sekä ohjaa käyttäjät automaattisesti uuteen sijaintiin vikatilanteessa.  
  
 [Azure Resource Manager](https://azure.microsoft.com/en-us/features/resource-manager/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Resource Manager -palvelua CDN:n, Redis-välimuistin, SQL Database -tietokannan ja pilvipalveluiden käyttöönottoon resurssiryhminä niin, että niiden tila on yhdenmukainen ja että ne voidaan ottaa käyttöön toistuvasti.