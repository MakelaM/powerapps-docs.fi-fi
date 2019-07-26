---
ms.openlocfilehash: ac90bfc27e03047cf422c44c83f550608d67b57e
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67212842"
---
Kun otat käyttöön palvelun [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] portaalitiedot, palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] tiedot, esimerkiksi asiakkaan nimi, tuotteen nimi, tapausnumero ja mitkä tahansa mukautetun entiteetin tiedot, voidaan näyttää ulkoisessa palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] portaalissa. Kaikki portaalissa näytettävät tiedot tallennetaan Microsoft [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -verkkosovellusten välimuistiin sekä paikallisen kiintolevyn tiedostoihin, jotta portaalin hakutoimintoa voidaan käyttää.

Vuokraajan järjestelmänvalvoja ottaa palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] portaalit käyttöön määrittämällä ne palvelussa [!INCLUDE[pn_dyn_365_admin_center](../includes/pn-dyn-365-admin-center.md)]. Tässä yhteydessä valittuun palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] esiintymään asennetaan myös paketti (joka sisältää ratkaisut ja tiedot). Vuokraajan järjestelmänvalvoja tai palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] käyttäjä, joka on määritetty portaalin järjestelmänvalvojaksi, voi sitten määrittää portaalissa näytettävät tiedot. Vuokraajan järjestelmänvalvoja voi poistaa portaalin toiminnot käytöstä peruuttamalla portaalilisäosan tilauksen palvelussa [!INCLUDE[pn_Office_365](pn-office-365.md)].

Palvelun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] tärkeät komponentit ja palvelut, jotka liittyvät portaalitoimintoihin, on lueteltu alla:
- [Azure-verkko sovellukset](https://azure.microsoft.com/services/app-service/web/): [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]Verkko sovelluksia käytetään portaalin isännöintiin kohteessa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)].
- [Azure Traffic Manager](https://azure.microsoft.com/services/traffic-manager/): [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]Traffic Manageria käytetään varmistamaan palvelun suuren käytettävyyden ohjaamalla käyttäjä verkko sovelluksiin, jotka ovat käynnissä. 
- [Azuren palvelu väylä](https://azure.microsoft.com/services/service-bus/): [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)](Aiheet/tila ukset) käytetään portaalien väli muistin mitätöinti. [!INCLUDE[pn_azure_service_bus](pn-azure-service-bus.md)] tallentaa väliaikaisesti viestit, jotka käynnistyvät, kun mikä tahansa portaaliin liittyvä tietue muuttuu palvelussa [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], ja jotka lähetetään verkkosovelluksiin hoitamaan välimuisti mitätöinti. 
- [Azure-Key Vault](https://azure.microsoft.com/services/key-vault/): Kaikki palvelut tallentavat määritystiedot kohteeseen [!INCLUDE[pn_azure_key_vault](pn_azure_key_vault.md)].
- [Azure-tallennus tila](https://azure.microsoft.com/services/storage/): Organisaatioon, vuokraajaan ja portaaliin liittyvät tiedot tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] säilöön.
- [Azure Active Directory](https://azure.microsoft.com/services/active-directory/): Kaikki verkko palvelut käyttävät [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] todentamista.
