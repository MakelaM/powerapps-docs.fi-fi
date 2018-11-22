Kun otat Tuotesuositukset-ominaisuuden käyttöön ja luot suositusmallin [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]:ssä, määritettyihin koritietoentiteetteihin ja niiden suodattimiin perustuvat tapahtumien historiatiedot lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]en, käsitellään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]ssa ja tallennetaan väliaikaisesti [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennukseen. Lopulta tiedot lähetetään Azuren suositusten ohjelmointirajapintaan automaattianalyysipalveluiden mallin luomista varten. Kun malli on luotu Azuren suositusten ohjelmointirajapinnan kanssa, tiedot poistetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennuksesta. Huomaa, että vain tunnukset (tilin tunnus, tuotetunnus ja tapahtumatunnus) lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]en suositusmallin luomista varten.

Järjestelmänvalvoja voi ottaa Tuotesuositukset-ominaisuuden käyttöön [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] -organisaation **Asetukset** &gt; **Hallinto** &gt; **Järjestelmäasetukset** &gt; **Esiversio** -välilehdessä. Tiedot lähetetään Azuren suositusten ohjelmointirajapintaan vain, kun suositusmalli muodostetaan. Järjestelmänvalvoja voi poistaa aiemmin luodun mallin poistaakseen Azuren suositusten ohjelmointirajapinnan kanssa jaetut tiedot. Lisäksi järjestelmänvalvoja voi estää uusien suositusmallien luonnin poistamalla yhteyden Azuren suositusten ohjelmointirajapintaan.

Seuraavissa osissa esitellään Tuotesuositukset-toimintoihin liittyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut.

[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]

[Azure Logic -sovellukset](https://azure.microsoft.com/services/app-service/logic/)

Sovellukset tuottavat hallitun tietoputken, jonka avulla tuoteluettelo ja tapahtumatiedot synkronoidaan suositusten ohjelmointirajapinnan kanssa suositusmalliversion luomista varten. Tämä putki suoritetaan monivuokraajapalveluna, jossa on useita Dynamics 365:n ja suositusten ohjelmointirajapinnan välistä viestiliikennettä hoitavia API-sovelluksia. Logic-sovellukset käynnistetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:ssä minimaalisilla tiedoilla, esimerkiksi malliversion tunnuksen ja [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -organisaation URL-osoitteen avulla. 

[Azure API -sovellukset](https://azure.microsoft.com/services/app-service/api/)

Nämä ovat verkkosovelluksia, jotka käynnistävät verkkotyöt, jotka lukevat tiedot [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -organisaatiosta ja lähettävät tiedot suositusten ohjelmointirajapintaan suositusmallin luomista varten. Saatavilla on kolme API-sovellusta ja niitä vastaavaa verkkotyötä: yksi tuotetietojen lukemiseen, yksi tapahtumatietojen lukemiseen ja yksi suositusmallin luomiseen. API-sovellukset käyttävät verkkotöitä varsinaiseen tietojen käsittelyyn taustalla, ja ne kirjoittavat tulostiedot [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön. Tiedot tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön väliaikaisesti. Mallin luomisen jälkeen tiedot poistetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennustilasta.

[Azure-taulukko](https://azure.microsoft.com/services/storage/tables/)

[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-taulukkoa käytetään malliversion ja organisaation kontekstin tietojen vaihtamiseen API-sovelluksen ja verkkotyön välillä.

[Azure Blob -säilö](https://azure.microsoft.com/services/storage/) 

Verkkotyöt tallentavat tiedot väliaikaisesti [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön ja poistavat tiedot, kun Logic-sovelluksen putken suoritus on valmis.

[Azuren suositusten ohjelmointirajapinta](https://www.microsoft.com/cognitive-services/en-us/recommendations-api) Azuren suositusten ohjelmointirajapintaan lähetetään mahdollisimman vähän tietoja (tuotetunnukset, tapahtumatunnukset ja tilitunnukset) suositusmallin luomista varten. Suositusten ohjelmointirajapinnan palvelu tallentaa tiedot, kunnes vastaava malliversio on luotu.
