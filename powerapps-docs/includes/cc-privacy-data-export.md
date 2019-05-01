---
ms.openlocfilehash: e9b0446c2fb09cad33f5a3ae4bb69103f7d07d70
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61572689"
---
Kun käytät tietojen vientipalvelua ja aktivoit tietojen vientiprofiilin [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] -palvelussa, profiiliin lisättyjen entiteettien tiedot lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-palveluun. Ensimmäinen synkronointi sisältää kaikki vientiprofiiliin lisättyjen entiteettien tiedot, mutta seuraavat synkronoinnit sisältävät vain uudet muutokset, joita lähetetään jatkuvasti tietojen vientipalveluun. Tietojen vientipalveluun lähetetyt tiedot tallennetaan väliaikaisesti [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] -palveluun ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennukseen, käsitellään [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -palvelussa, ja lopuksi tiedot synkronoidaan (lisätään, päivitetään tai poistetaan) [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tilauksessa määritetyn kohdetietokannan kanssa. Kun tiedot on synkronoitu, ne poistetaan [!INCLUDE[pn_azure_service_bus](pn_azure_service_bus.md)] -palvelusta ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennuksesta. Jos tietojen synkronoinnin aikana tapahtuu virhe, lyhyet tiedot (entiteettityyppi, tietuetunnus ja synkronoinnin aikaleima) tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennukseen, jotta käyttäjä voi ladata luettelon tietueista, joita ei päivitetty.  
  
 Järjestelmänvalvoja voi milloin tahansa poistaa tietojen vientiprofiilin käytöstä tietojen synkronoinnin lopettamiseksi. Lisäksi järjestelmänvalvoja voi poistaa vientiprofiilin epäonnistuneiden tietueiden lokien poistamiseksi. Hän voi myös poistaa tietojen vientipalveluratkaisun asennuksen tietojen vientipalvelun käytön lopettamiseksi.  
  
 Tietojen synkronointia suoritetaan jatkuvasti [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-palvelun ja tietojen vientipalvelun välillä suojatun yhteyden kautta. Tiedot salataan, koska ne liikkuvat jatkuvasti [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-palvelun ja tietojen vientipalvelun välillä.  
  
 Seuraavissa osioissa esitellään tietojen vientipalveluun liittyvät Azure-komponentit ja -palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/)  
  
 Tämä tarjoaa ohjelmointirajapinnan ja tietojenkäsittelyn [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-näennäiskoneet [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)]-palvelusta saatujen tietueiden synkronointi-ilmoitusten käsittelyyn ja tietuetietojen lisäämiseen, päivittämiseen tai poistamiseen kohdetietokannassa. [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -suorituspalvelun hallitsemissa näennäiskoneissa käyttöönotetut mikropalvelut hoitavat kaikki tietojen synkronointiin liittyvät tietojenkäsittelypalvelut.  
  
 [Azuren palveluväylä](https://azure.microsoft.com/services/service-bus/)  
  
 Tämä tarjoaa viestiväylän, johon [!INCLUDE[pn_crm_shortest](pn-crm-shortest.md)] lisää synkronoinnin ilmoitusviestit, jotka [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -palvelun tietojenkäsittelysolmut käsittelevät. Jokaisessa viestissä on tietoja, kuten organisaation tunnus ja tietue, johon tiedot synkronoidaan. Azuren palveluväylän lepääviä tietoja ei salata, mutta niitä voi käyttää vain tietojen vientipalvelun kautta.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/services/storage/)  
  
 Tiedot tallennetaan väliaikaisesti [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)]ön, jos tietueen synkronointi-ilmoituksen tietoja on liian paljon viestiin tallennettavaksi tai jos synkronointi-ilmoituksen käsittelyssä ilmenee lyhytaikaisia virheitä. Nämä blob-objektit salataan hyödyntämällä [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennuksen SDK:n uusinta ominaisuutta, joka tarjoaa sekä symmetrisen että asymmetrisen salauksen tuen sekä integroinnin [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] -ratkaisun kanssa.  
  
 [Azure SQL](https://azure.microsoft.com/services/sql-database/)  
  
 [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] tallentaa tietojen vientiprofiilin määritykset ja tietojen synkronoinnin mittarit.