Kun otat Dynamics 365 Mobile Offline -sovelluksen käyttöön, offline-käytössä oleviin entiteetteihin perustuvat Dynamics 365 (online) -tiedot ladataan Azure-pilvipalvelun avulla SQL Azure -tietokantaan. Kun käyttäjä ottaa yhteyden tähän Azure Cloud -palveluun mobiilisovelluksesta, jossa on offline-ominaisuus, tiedot ladataan SQL Azure -tietokannasta mobiililaitteen paikalliseen tietokantaan. Tietojen siirtämiseen Azure-pilvipalvelun SQL Azure -tietokannan ja offline-ominaisuuden sisältävän Dynamics 365 Mobile -sovelluksen välillä käytetään suojattua SSL-yhteyttä. Näin asiakastiedot tallennetaan sekä SQL Azure -tietokantaan että mobiililaitteeseen.  
  
 Järjestelmänvalvoja määrittää käyttöoikeusroolien ja Dynamics 365 Mobilen profiilin mukautuksen avulla, onko organisaatioon kuuluvilla käyttäjillä oikeus siirtyä offline-tilaan Microsoft Dynamics 365 Mobile Offline -sovelluksella. Dynamics 365 -järjestelmänvalvojat voivat määrittää offline-synkronoinnin kautta ladattavat entiteetit Asetus – Mobile Offline -valintaikkunan Synkronointisuodattimet-asetuksen avulla.  
  
 Huomaa, että käyttäjän laitteelle tallennettuja tietoja hallitsee käyttäjä, ei Microsoft. Järjestelmänvalvojalla on purettavien tietojen täydet hallintaoikeudet käyttöoikeusroolitasolla ja entiteettitasolla. Tiedot eivät ole enää purkamisen jälkeen suojatussa Dynamics 365 Online -ympäristössä.  
  
 Luettelo Mobile offline -toimintoon liittyvistä Azure-komponentit ja -palveluista on jäljempänä.  
  
 **Huomautus:** Katso lisätietoja muista Azure-palveluista [Microsoft Azure Trust Centerissä](https://azure.microsoft.com/en-us/support/trust-center/).  
  
 **Pilvipalvelut (verkkorooli)**  
  
 Mobile Offline hyödyntää kahta pilvipalvelua. Toista palvelua käytetään valmistelussa ja toista tietojen synkronoinnissa.  
  
 Valmistelupalvelu sisältää yhden verkkoroolin, joka lukee Dynamics 365:stä saapuvat palveluväylän jonon eri tapahtumien viestit. Nämä viestit voivat koskea esimerkiksi valmistelua tai valmistelun peruutusta. Tämän jälkeen se käsittelee viestit luomalla organisaation tietokannat tai poistamalla ne ja lähettämällä toistuvat työkohteet (viestit) tietojen synkronoinnin palveluväylän jonoon. Tämän prosessin aikana se lukee ja kirjoittaa määritystiedot joko CSCFG-tiedostosta tai Dynamics 365 SW -ohjelmointirajapinnasta.  
  
 Tietojen synkronointipalvelulla on kaksi verkkoroolia. Toinen pitää rakenteen ja väliaikaisen tietokannan tiedot synkronoituina Dynamics 365 -organisaation metatietojen ja tietojen kanssa. Samalla toinen rooli suorittaa synkronointipalvelinta ja käsittelee asiakkaan synkronointipalveluita. Ensimmäinen verkkorooli käsittelee eri organisaatioiden tietojen synkronoinnin palveluväylän jonon viestit ja ottaa sitten yhteyden Dynamics 365:een noutaakseen metatietojen ja tietojen muutokset, ennen kuin ne vahvistetaan väliaikaista tietokantaa varten. Se myös määrittää synkronointipalvelimen sekä järjestelmään saapuvat ja sieltä lähtevät organisaatiot ja niiden asiakasmallit. Toinen verkkorooli käyttää synkronointipalvelinta (hallitsematon koodi) järjestelmänvalvojan ja synkronoinnin päätepisteiden isännöintiin. Toinen WWW-rooli käyttää järjestelmänvalvojan päätepistettä määritystietojen lähettämisessä. Ulkoiset asiakkaat (Dynamics 365 Mobile -sovellus) käyttävät synkronoinnin päätepistettä tietojen synkronoinnissa. Kuten valmistelupalvelussakin, nämä roolit lukevat/kirjoittavat määritystietoja joko CSCFG-tiedostosta tai Dynamics 365 SW -ohjelmointirajapinnasta.  
  
 **Jono**  
  
 Mobile Offline käyttää Azuren jonoja Dynamics 365:n ja Azuren välisessä viestien vaihdossa. Sen avulla ylläpidetään pilvipalveluiden käsittelemiä työkohteita. Jokainen viesti sisältää tietoja, kuten organisaation tunnuksen, sen entiteetin nimen, johon tiedot synkronoidaan, ja organisaation OData-päätepisteen yhteysmerkkijonon.  
  
 **SQL-tietokanta**  
  
 Mobile Offline tallentaa Azuren SQL -tietokantaan:  
  
-   Dynamics 365 -organisaatioista replikoidut tiedot ja palveluasiakkaan synkronointipyynnöt  
  
-   määritystiedot, kuten organisaation tietokannan yhteysmerkkijonot.  
  
 **Tallennustila**  
  
 Mobile Offline käyttää Azure Blob storage pilvipalvelun luomien loki- ja seurantatiedostojen tallentamiseen.  
  
 **Active Directory -palvelu**  
  
 Mobile Offline käyttää Azure Active Directory -palvelua muiden palveluiden, kuten Dynamics 365:n, SW-ohjelmointirajapinnan tai Azure-hallinnan ohjelmointirajapintojen todentamiseen.  
  
 **Azure DNS**  
  
 Mobile Offline korjaa pilvipalvelujen päätepisteet käyttämällä Azure DNS:ää asiakkaiden pyyntöjen uudelleenohjaamiseen organisaatioiden nimien perusteella.  
  
 **Azure-näennäisverkko**  
  
 Azure-näennäisverkko (VNet) on oman verkon esitys pilvipalvelussa. Dynamics 365 -tuotetiimi voi hallita Azure-verkkoasetuksia ja määrittää DHCP-osoitelohkot, DNS-asetukset, suojauskäytännöt ja reitityksen.  
  
 **Azuren kuormituksen tasaus**  
  
 Azuren kuormituksen tasaus parantaa sovellusten käytettävyyttä ja verkon suorituskykyä. Se on taso 4 (TCP, UDP) -tyyppinen kuormituksen tasapainottaja, joka jakaa saapuvaa liikennettä pilvipalveluiden toimiville palveluesiintymille tai kuormituksen tasapainotuksen joukossa määritetyille näennäiskoneille. Sitä käytetään tasattaessa kuormitusta käyttöönoton päätepisteissä.