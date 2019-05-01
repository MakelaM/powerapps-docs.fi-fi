---
ms.openlocfilehash: 3840a097743111f6ae89e65426a366207f8364d9
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61570588"
---
Ottamalla käyttöön Oppimispolku-ominaisuuden, staattisen html:n, voit ottaa käyttöön kuvien ja komentosarjojen tallentamisen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-sisältöverkkoon (CDN). Lisäksi kaikki näytettävä dynaaminen sisältö tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis -välimuistiin, jota käytetään esivälimuistiin tallentamisessa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL-tietokannasta.  
  
 Järjestelmänvalvoja voi ottaa käyttöön Oppimispolku-ominaisuuden tai poistaa sen käytöstä [!INCLUDE[pn_crm_online_shortest](pn-crm-online-shortest.md)] -esiintymässä käyttämällä Ota avustava ohje käyttöön -asetusta [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] organisaatiossa.  
  
 Seuraavissa osioissa esitellään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja palvelut, joita käytetään oppimispolun toiminnoissa.  
  
> [!NOTE]
>  Jos haluat lisätietoja muista Azure-palveluista, siirry [Microsoft Azuren luottamuskeskukseen](https://azure.microsoft.com/en-us/support/trust-center/).  
  
 [Pilvipalvelut](https://azure.microsoft.com/en-us/services/cloud-services/)  
  
 **Oppimispolku-suorituspalvelu (verkkorooli)**  
  
 Tämä on verkkosovellus, joka lähettää sisällön käyttäjille.  
  
 **Oppimispolku-palvelu (työntekijän rooli)**  
  
 Työntekijän roolissa olevat henkilöt ovat vastuussa tietojen käsittelystä [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] SQL -tietokannasta ja niiden tallentamisessa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis -välimuistiin.  
  
 [Azure SQL -tietokanta](https://azure.microsoft.com/en-us/services/sql-database/)  
  
 Oppimispolku tallentaa SQL-tietokannan avulla seuraavia asioita:  
  
-   Sisältö  
  
-   Sisällön metatiedot  
  
-   Järjestelmän metatiedot  
  
 [Azure Blob -säilö](https://azure.microsoft.com/en-us/services/storage/)  
  
 HTML, kuvat, [!INCLUDE[pn_JavaScript](pn-javascript.md)], ja CSS tallennetaan kaikki [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-säilöön.  
  
 [Azure-sisältöverkko (CDN)](https://azure.microsoft.com/en-us/services/cdn/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-sisältöverkkoa staattisen sisällön, kuten HTML:n, kuvien, [!INCLUDE[pn_JavaScript](pn-javascript.md)]in ja CSS:n, lähettämiseen kyselyn suorituspalveluun.  
  
 [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -palvelua verkkopalveluiden todentamiseen erityisesti suunnitteluohjelmaa varten. Tällä hetkellä suunnitteluohjelmaa ei näytetä asiakkaille ja kumppaneille. Ja siksi todennus on vain [!INCLUDE[cc_Microsoft](cc-microsoft.md)]-toimialueella.  
  
 [Azure Redis -välimuisti](https://azure.microsoft.com/en-us/services/cache/)  
  
 Oppimispolku käyttää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Redis -välimuistia käyttäjille lähetettävän dynaamisen sisällön tallentamisessa välimuistiin.  
  
 [Azure-liikennehallinta](https://azure.microsoft.com/en-us/services/traffic-manager/)  
  
 Liikennehallinnan avulla oppimispolku parantaa tärkeiden sovellusten saatavuutta valvomalla [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]- tai ulkoisia sivustoja ja palveluita ja ohjaamalla käyttäjät automaattisesti uuteen sijaintiin, kun virhe havaitaan.  
  
 [Azure Resource Manager](https://azure.microsoft.com/en-us/features/resource-manager/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Resource Managerin avulla oppimispolku ottaa käyttöön CDN:n, Redis-välimuistin, SQL-tietokannan ja pilvipalvelut resurssiryhminä niin, että ne ovat yhtenäisessä tilassa ja voidaan ottaa käyttöön useita kertoja.