Kun otat Dynamics 365:n Asiakaskuuntelu-ominaisuuden käyttöön ja julkaiset kyselyn Dynamics 365:stä, kyselyn määritys lähetetään Azureen ja tallennetaan Azure-tallennustilaan. Kun vastaaja lähettää kyselyn (avaamalla hänelle sähköpostitse lähetetyn kyselykutsulinkin), kyselyvastaukset tallentuvat väliaikaisesti Azuren palveluväylään, jonka jälkeen Dynamics 365 poimii ja tallentaa ne. Kun vastaukset on tallennettu Dynamics 365:een, ne poistetaan Azuresta.  
  
 Huomaa, että kyselyyn (kyselyn elementteihin, kuten kysymyksiin ja vastauksiin) voi lisätä Dynamics 365 -tietoja, kuten asiakkaan nimen, tuotteen nimen ja palvelupyynnön numeron, kun vastaajalle lähetettävää kyselyä muodostetaan. Kun kyselykutsulinkki luodaan, Dynamics 365 -tiedot voidaan lähettää Dynamics 365:stä ja tallentaa Azuren SQL-tietokantaan. Vastineena saadaan kyselykutsulinkissä käytettävä tunnus. Kun kysely avataan kyselykutsulinkistä, tunnuksen avulla saadaan näkyviin kyselyn Dynamics 365 -tiedot. Sähköpostitse vastaajalle lähetettävän kyselykutsulinkin tunnukset tallennetaan vastaajan sähköpostijärjestelmään.  
  
 Järjestelmänvalvoja voi ottaa Dynamics 365:n Asiakaskuuntelu-ominaisuuden käyttöön asentamalla sen ratkaisuna Dynamics 365 -organisaatioon. Järjestelmänvalvoja voi myös poistaa ominaisuuden käytöstä poistamalla tämän ratkaisun asennuksen Dynamics 365 -organisaatiosta.  
  
 Seuraavissa osissa esitellään Dynamics 365:n Asiakaskuuntelu-toimintoon liittyvät Azure-komponentit ja -palvelut.  
  
 Huomautus:Katso lisätietoja muista Azure-palveluista Microsoft Azure Trust Centerissä ([https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)).  
  
 **Pilvipalvelut** ([https://azure.microsoft.com/services/cloud-services/](https://azure.microsoft.com/services/cloud-services/))  
  
 **Suunnittelupalvelu (WWW-rooli)**  
  
 Suunnittelupalvelu tuo käyttöön lukuisia verkkopalveluja Dynamics 365 -organisaation ja Dynamics 365:n Asiakaskuuntelu-toiminnon Azure-komponenttien välistä tiedonsiirtoa varten.  Se käyttää esimerkiksi Azure Blob -säilöä kyselyjen julkaisemiseen ja tallentamiseen.  Palvelu hakee kyselyvastaukset Azuren palveluväyläjonosta ja palauttaa ne Dynamics 365 -organisaatiolle jatkokäsittelyä varten.  Kaikki pyynnöt todennetaan Azure Active Directoryn avulla.  
  
 **Kyselyn suoritusaika (WWW-rooli)**  
  
 Tämä verkkosovellus lähettää kyselyt vastaajille.  Lähetetyt kyselyvastaukset tallentuvat väliaikaisesti Azuren palveluväyläjonoon, kunnes Dynamics 365:n asynkroninen palvelu hakee ne käsiteltäviksi.  
  
 **Vastausten käsittelijä (työrooli)**  
  
 Tämä työrooli muodostaa kyselyjen raakadatasta vastauksia, jotka kelpaavat Dynamics 365:ssä luotaviksi.  
  
 **Työntökäsittelijä (työrooli)**   Tämä työrooli käsittelee kelvolliset kyselyvastaukset ja päivittää ne Dynamics 365 -entiteettitietueiksi. 
 
 **Azure Key Vault** ([https://azure.microsoft.com/services/key-vault/](https://azure.microsoft.com/services/key-vault/))  
  
 Kaikki pilvipalvelut tallentavat määritystiedot Azure Key Vaultiin.  Azuren SQL-tietokantaan tallennetut organisaation ja vuokraajan asetukset.  
  
 **Azure SQL Database** ([https://azure.microsoft.com/services/sql-database/](https://azure.microsoft.com/services/sql-database/))  
  
 Dynamics 365:n Asiakaskuuntelu tallentaa SQL Azure -tietokantaan:  
  
-   johdetut tiedot  
  
-   kyselyn metatiedot  
  
-   organisaation (vuokraajan) tiedot.  
  
 **Azure Blob Storage** ([https://azure.microsoft.com/services/storage/](https://azure.microsoft.com/services/storage/))  
  
 Kyselyjen määrityksiä ja osittain annettuja (tallennettuja) vastauksia säilytetään Azure Blob -säilössä.  
  
 **Azure Content Delivery Network (CDN)** ([https://azure.microsoft.com/services/cdn/](https://azure.microsoft.com/services/cdn/))  
  
 Dynamics 365:n Asiakaskuuntelu-ratkaisu lähettää Azure Content Delivery Network -sisältöjakeluverkon kautta staattisen sisällön (esimerkiksi asiakkaan logot ja muut ladatut kuvat, JavaScript- ja CSS-sisällöt) kyselyn suorituspalveluun.  
  
 **Azure Active Directory** ([https://azure.microsoft.com/services/active-directory/](https://azure.microsoft.com/services/active-directory/))  
  
 Dynamics 365:n Asiakaskuuntelu-ratkaisu todentaa verkkopalvelujen käyttöoikeudet Azure Active Directory -palvelun avulla.  
  
 **Azure Service Bus** ([https://azure.microsoft.com/services/service-bus/](https://azure.microsoft.com/services/service-bus/))  
  
 Viestit, jotka luodaan kyselyn aikana tai vastauksia lähetettäessä, tallentuvat väliaikaisesti organisaation (vuokraajan) Azure Service Bus -palveluväyläjonoon, kunnes Azure-työntekijärooli työntää kyselyvastaukset organisaation Dynamics 365 -ilmentymään ja siirtää ne jatkokäsiteltäväksi Dynamics 365 -entiteettitietueina.
