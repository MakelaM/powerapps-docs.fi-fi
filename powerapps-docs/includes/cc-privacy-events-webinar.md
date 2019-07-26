---
ms.openlocfilehash: fa4a17c2a3131f49f8a702388bdb405661855c10
ms.sourcegitcommit: 483c777a1537ccab6a2a2da6a5d1fe4470dd0e7e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/19/2019
ms.locfileid: "61550015"
---
Kun hyväksyt tapahtuman hallinnan ehdot ja määräykset, verkkoseminaarin integrointiominaisuus aktivoidaan. Verkkoseminaarin integrointiominaisuus hyödyntää verkkoseminaarien palveluntarjoajakumppania tapahtuman tai istunnon toteuttamiseksi verkkoseminaarina. Käyttääksesi verkkoseminaarien palveluntarjoajan palveluja, sinulla on oltava tili heidän palvelussaan. Ainoa heti käyttövalmis verkkoseminaarien palveluntarjoajakumppani on tällä hetkellä ON24. Käytettäessä verkkoseminaarin integrointiominaisuutta verkkoseminaarin toteuttamiseen tarvittavia tietoja käsitellään ja tallennetaan [!INCLUDE[pn-azure-service-fabric](../includes/pn-azure-service-fabric.md)]-palvelussa, ja ne lähetetään sitten ON24:lle. Nämä tiedot sisältävät verkkoseminaarin osallistujien rekisteröintitiedot, kuten nimet, sähköpostiosoitteet ja yritysten nimet. Lisäksi ON24 lähettää verkkoseminaarin arvoja, kuten verkkoseminaarin katseluajan, kohteeseen [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] [!INCLUDE[pn-azure-service-fabric](../includes/pn-azure-service-fabric.md)] -palvelun kautta.

Sinun ei tarvitse aktivoida verkkoseminaarin integrointiominaisuutta muiden tapahtumanhallintaratkaisujen käyttämiseksi. Järjestelmänvalvoja voi poistaa käytöstä verkkoseminaarin integrointiominaisuuden poistamalla tunnistetiedot verkkoseminaarin määrityksistä.

Verkkoseminaarin integrointiominaisuus käyttää seuraavia [!INCLUDE[pn-windows-azure](../includes/pn-windows-azure.md)]-osia ja -palveluja:

- [!INCLUDE[pn_azure_key_vault](../includes/pn_azure_key_vault.md)] ([!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Mikä on Azure Key Vault?](https://docs.microsoft.com/azure/key-vault/key-vault-whatis))
  - Tarjoaa salausavaimen asiakkaan ON24-tilin tunnistetietojen salaukseen ja salauksen purkamiseen
- [!INCLUDE[pn-azure-service-fabric](../includes/pn-azure-service-fabric.md)] ([!INCLUDE[proc-more-information](../includes/proc-more-information.md)] [Azure Service Fabricin yleiskatsaus](https://docs.microsoft.com/azure/service-fabric/service-fabric-overview))
  - Käsittelee ja lähettää rekisteröintitiedot ja verkkoseminaaritilin tunnistetiedot ON24:lle
  - Hakee verkkoseminaarin arvot ON24:stä kohteeseen [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] -Tallentaa asiakkaan ON24-tilin tunnistetiedot (mukautettu salaus)