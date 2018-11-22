Ottamalla käyttöön Tekstianalyysi-ominaisuuden otat käyttöön [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:n riippuvia ominaisuuksia, jotka hyödyntävät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n kognitiivisten palvelujen tekstianalyysin ohjelmointirajapintaa edistyneiden näkemyksien tuottamiseksi. Riippuvat ominaisuudet:  
  
-   tietoehdotukset  
  
-   palvelupyynnön aiheen analyysi  
  
-   Samankaltaisten palvelupyyntöjen ehdotukset  
  
 Järjestelmänvalvoja voi ottaa Tekstianalyysi-ominaisuuden käyttöön [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] -organisaation **Asetukset** > **Hallinto** > **Järjestelmäasetukset** >  **Esiversio** -välilehdessä.  
  
 Kun sinulla on Tekstianalyysi-ominaisuus käytössä ja määrität tekstianalyysipohjaisia tietoehdotuksia [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]:ssä, palvelupyyntö ja sen liittyvien entiteettien tiedot lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan avainsanojen ja ilmausten purkamista varten. Mitään tietoja ei tallenneta [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan. Vain tietopankin artikkelin määrityksessä määritetyt kentät lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan termien purkamista varten. Järjestelmänvalvoja tai mukauttaja voi poistaa tietopankin artikkelin määrityksen aktivoinnin, jolloin API-kutsut [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan lopetetaan. Mukauttaja voi myös lopettaa tekstianalyysiin perustuvien ehdotuksien käytön ottamalla Kenttään perustuvat ehdotukset -asetuksen käyttöön palvelupyyntöentiteetin lomakkeen määrityksissä.  
  
 Kun sinulla on Tekstianalyysi-ominaisuus käytössä ja määrität palvelupyynnön aiheen analyysin [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]:ssä, palvelupyyntö ja sen liittyvien entiteettien tiedot lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan aiheen määritystä varten. Mitään tietoja ei tallenneta [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan. Vain aiheen mallin määrityksiin määritetyt kentät lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan aiheiden purkamista varten. Järjestelmänvalvoja tai mukauttaja voi poistaa aiheen mallin aktivoinnin, jolloin [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapinnan kutsut lopetetaan.  
  
 Kun sinulla on Tekstianalyysi-ominaisuus käytössä ja määrität samanlaisten palvelupyyntöjen ehdotuksia [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]:ssä, palvelupyyntö ja sen liittyvien entiteettien tiedot lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan avainsanojen ja ilmausten purkamista varten, jos Samanlaisuussääntö-kohdassa on otettu käyttöön Kehittynyt tekstianalyysi -valinta. Vain tekstikentät, jotka on määritetty samanlaisuussäännössä, lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan. Mitään tietoja ei tallenneta [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan. Järjestelmänvalvoja tai mukauttaja voi poistaa samanlaisuussäännön aktivoinnin, jolloin [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapinnan kutsut lopetetaan.  
  
 Seuraavissa osissa esitellään Tekstianalyysi-ominaisuuteen perustuvat [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Azure API -sovellus](https://azure.microsoft.com/services/app-service/api/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API käynnistää verkkotöitä, jotka lukevat tietoja [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -organisaatiosta ja lähettävät ne tekstianalyysin ohjelmointirajapintaan aiheanalyysia varten. [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API -sovellus käyttää verkkotöitä varsinaiseen tietojen käsittelyyn taustalla, ja se kirjoittaa tulostiedot [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -tallennustilaan. Tiedot tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -tallennustilaan väliaikaisesti. Aiheen määrittämisen jälkeen tiedot poistetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilasta.  
  
 [Azuren aikataulutus](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n aikataulutusta käytetään käynnistämään verkkotyö ajoitetusti aiheanalyysin suorittamiseksi. Vain aiheen mallin luontiaikataulu jaetaan aikataulutuksen kanssa.  
  
 [Azure-taulukko](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-taulukkoa käytetään malliversion ja organisaation kontekstin tietojen vaihtamiseen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API -sovelluksen ja verkkotyön välillä.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/services/storage/)  
  
 Verkkotyöt tallentavat tiedot väliaikaisesti [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön ja poistavat tiedot, kun Logic-sovelluksen putken suoritus on valmis.  
  
 [Azuren tekstianalyysin ohjelmointirajapinta](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n tekstianalyysin ohjelmointirajapintaan lähetetään tietoja tietohaun, aihemallin tai samanlaisuussäännön määrityksien kenttien perusteella. Esimerkiksi Tietohaun kenttä -määrityksissä on määritetty palvelupyyntöentiteettikentät, kuten otsikko, kuvaus sekä liittyvien muistiinpanojen ja aktiviteettien kuvauskenttä.  
  
 [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -osuvuushaku  
  
 Jos järjestelmänvalvojasi on ottanut osuvuushaun käyttöön, voit etsiä sen avulla palvelupyynnön kanssa samanlaisia tietueita. Samanlaisuussäännössä käytettyjä tekstiosuvuuskenttiä ja tarkkojen osumien kenttiä käytetään käynnistämään osuvuushaun ohjelmointirajapinta. Tietojen käsittelystä saat tarkempia tietoja [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -osuvuushaun teknisistä ohjeista.