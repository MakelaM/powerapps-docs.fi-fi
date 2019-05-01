---
ms.openlocfilehash: 747ea34b784b852261debe91f587d64ee3277804
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61570601"
---
Kun [!INCLUDE[pn_gamification](pn-gamification.md)]-ratkaisu asennetaan ja otetaan käyttöön, käyttöönoton suorittavan käyttäjän tilitunnisteet (kuten etunimi, sukunimi ja sähköpostiosoite) tallennetaan kohteeseen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], jotta valtuutus voidaan tehdä [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-palvelussa, joka sijaitsee kohteessa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Tämä koskee kaikkia käyttäjiä, jotka järjestelmänvalvoja on ottanut käyttöön [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-palvelussa. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-ratkaisu lähettää järjestelmänvalvojan määrittämät KPI-tiedot [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-palveluun, ja kyseiset tiedot tallennetaan kohteen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] rakenteiseen tallennustilaan sekä blob-säilöön.  Kunkin käyttäjän Avatar, mukautetut palkinnot ja yrityksen logo tallennetaan kohteeseen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], mutta tietoja ei palauteta kohteeseen [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)].  
  
Huomaa, että järjestelmänvalvojat ja valtuutetut käyttäjät voivat hyödyntää [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] tietoja, kuten puheluita, mahdollisuuksia ja varattua tuottoa pelien KPI:iden määrittämisessä. [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-palvelu ei muodosta kutsuja kohteeseen [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] ja se reagoi vain tietoihin (kuten peleihin, joissa KPI:itä käytetään) jotka kulkevat takaisin kohteeseen [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)].  
  
Järjestelmänvalvoja voi myös tehdä [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] TV -suoratoistosta julkisen. Pelinvalvojat, jotka määrittävät [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] TV -suoratoistoja ja ottavat käyttöön julkisen suoratoiston, sallivat TV-suoratoiston katselun kaikille Internet-käyttäjille, joilla on suoratoistolinkki.  
  
Järjestelmänvalvoja voi myös poistaa [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)]-toiminnon käytöstä poistamalla sen asennuksen [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)]-organisaatiosta.  
  
Palvelun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] osat ja palvelut, jotka liittyvät kohteeseen [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)], eritellään seuraavissa osioissa.  
  
[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
[Pilvipalvelut](https://azure.microsoft.com/services/cloud-services/)  
  
 **Suunnittelupalvelu (verkkorooli)**  
  
Tämä tarjoaa useita verkkopalveluita tiedonsiirtoon [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-organisaation ja monen vuokraajan [!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] osien välillä. Esimerkiksi pelillistämistiedot tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL -tallennukseen.  Pelin laskutoimitukset käyttävät [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)]-jonoa ja ne palautetaan pisteytettäväksi ja näytettäväksi palvelussa.  Asiakkaiden ja käyttäjien palvelimeen lataamat kuvat tallennetaan kohteeseen [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)]. Kaikki pyynnöt todennetaan kohteen [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] avulla.  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
Kaikki palvelut tallentavat määritystiedot kohteeseen [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
[Azuren SQL-tietokanta](https://azure.microsoft.com/services/sql-database/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] käyttää SQL [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -palvelua seuraavien tietojen tallentamiseen:  
  
- KPI-tiedot  
  
- Pelin laskutoimitukset  
  
- Organisaation (vuokraajan) tiedot  
  
[Azure Blob -säilö](https://azure.microsoft.com/services/storage/)  
  
Avatarit, yritysten logot ja muut asiakkaan palvelimeen lataamat kuvat tallennetaan kohteeseen [!INCLUDE[pn_azure_blob_storage](pn-azure-blob-storage.md)].  
  
[Azure-sisältöverkko (CDN)](https://azure.microsoft.com/services/cdn/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-sisältöverkkoa tarjotakseen suorituspalveluun staattista sisältöä, kuten kuvia (myös ladatut kuvat, kuten asiakkaan logot), [!INCLUDE[pn_JavaScript](pn-javascript.md)] ja CSS:ää.  
  
[Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_gamification_shortest](pn-gamification-shortest.md)] käyttää kohdetta [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] käyttäjien todentamiseen ja ympäristön käyttöoikeuden määrittämiseen.