---
ms.openlocfilehash: dff813dcdf6d025ba47e29699e2047f79cf85600
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67225476"
---
Kun otat osuvuushaun käyttöön, [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] -esiintymässä olevat, osallistuvien entiteettien ja määritteiden tiedot alkavat synkronoitua ja tallentua [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -hakuindeksiin.  
  
 Osuvuushaku ei ole käytössä oletusarvoisesti. Järjestelmänvalvojan on otettava toiminto käyttöön [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] -esiintymässä. Kun osuvuushaku on otettu käyttöön, järjestelmänvalvojilla ja mukauttajilla on täydet käyttöoikeudet tietoihin, jotka synkronoidaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -hakuindeksiin.  
  
 Järjestelmämukauttajat voivat käyttää **Mukautustyökalut** -valikossa olevaa **Määritä osuvuushaku** -valintaikkunaa ottaakseen tietyt entiteetit käyttöön hauissa ja sitten määrittää käyttöön otettujen entiteettien Pikahakunäkymät, jotta he voivat valita haettavissa olevat määritteet. Tietojen muutokset synkronoidaan jatkuvasti [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] -kohteen ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -haun välillä suojatun yhteyden kautta.  Määrityksen tiedot salataan ja pakolliset salaisuudet tallennetaan kohteeseen [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)].  
  
 Seuraavissa osioissa esitellään Azure-komponentit ja -palvelut, joita käytetään osuvuushaun toiminnoissa.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc_privacy_note_azure_trust_center.md)]  
  
 [Azure-hakupalvelut](https://azure.microsoft.com/services/search/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -hakuindeksi tarjoaa laadukkaita hakutuloksia ja nopeita vasteaikoja.  [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -haku lisää tehokkaita ja kehittyneitä seuraavan sukupolven hakuominaisuuksia kohteeseen [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)].  Tämä on ulkoinen, varattu hakupalvelu [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] varten, jonka tarjoaa [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)]. Kaikki uudet [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -hakuindeksit salataan levossa.  Jos olet antanut suostumuksesi ennen 24.1.2018, sinun tulee indeksoida tietosi uudelleen peruuttamalla suostumuksesi osuvuushakuun, odottamalla tunnin ja sitten antamalla suostumuksesi taas.  
  
 [Azure SQL -tietokanta](https://azure.microsoft.com/services/sql-database/)  
  
 Osuvuushaku käyttää [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] seuraavien tietojen tallentamiseen:  
  
-   Organisaatioon ja vastaavaan indeksiin liittyvät määritystiedot  
  
-   Hakupalveluun ja -indeksiin liittyvät metatiedot  
  
-   Osoittimet järjestelmän metatietoihin ja tietoihin, kun muutoksia synkronoidaan  
  
-   Valtuutustietoja parannetun rivitason suojauksen käyttöönottoa varten  
  
[Azuren tapahtumatoiminnot](https://azure.microsoft.com/services/event-hubs/)  
  
[!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)] -osaa käytetään viestien välittämiseen kohteiden [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] välillä ja synkronointiprosessin hallitsemien työkohteiden ylläpitämiseen. Jokainen viesti tallentaa tietoja, kuten organisaation tunnuksen ja entiteetin nimen, joita käytetään tietojen synkronointiin.  
  
[Azure Service Fabric -klusteri](https://azure.microsoft.com/services/service-fabric/)  
  
Service Fabric -suorituspalvelun hallitsemissa näennäiskoneissa käyttöönotetut mikropalvelut hoitavat kaikki tietojen prosessointiin ja indeksointiin liittyvät palvelut. Service Fabric -klusteri hoitaa myös hakuohjelmointirajapintojen ja tietojen synkronointiprosessin isännöinnin.  
  
Service Fabric syntyi Microsoftin vuosien mittaisesta kokemuksesta tärkeiden pilvipalveluiden tuottajana ja on nyt ollut täydessä toiminnassa jo yli viiden vuoden ajan. Se on perustavanlaatuinen teknologia, joka toimii pohjana [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] -ydininfrastruktuurillemme ja pyörittää muun muassa seuraavia palveluitamme: [!INCLUDE[pn_skype_for_business](pn-skype-for-business.md)], [!INCLUDE[pn_intune](pn-intune.md)], [!INCLUDE[pn_azure_event_hubs](pn-azure-event-hubs.md)], [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Data Factory [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] DocumentDB, [!INCLUDE[pn_Azure_SQL_Database_long](pn-azure-sql-database-long.md)] ja [!INCLUDE[pn_cortana](pn-cortana.md)] — joka voidaan skaalata käsittelemään yli 500 miljoonaa arviota sekunnissa.  
  
[Azure Virtual Machine Scale Sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Virtual Machine Scale Setsit ovat joustavia ja suunniteltu tukemaan hyperskaalautuvia kuormituksia. [!INCLUDE[pn_azure_service_fabric](pn_azure_service_fabric.md)] -klusterin toimii Virtual Machine Scale Setsien voimalla. Mikropalvelut tietojen prosessointiin ja indeksointiin isännöidään skaalausjoukoissa ja ovat Service Fabric -suorituspalvelun hallinnoimia.  
  
[Azure Key Vault](https://azure.microsoft.com/services/key-vault/)  
  
[!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] -palvelua käytetään varmenteiden, avaimien ja muiden hakuprosessissa käytettävien salaisuuksien suojattuun hallintaan.  
  
[Azure-tallennus (Blob-objektisäilö)](https://azure.microsoft.com/services/storage/blobs/?b=16.38)  
  
Asiakastietojen muutoksia säilytetään enintään 2 päivää [!INCLUDE[pn_azure_blob_storage](pn_azure_blob_storage.md)] -palvelussa.  Nämä blob-objektit salataan hyödyntämällä [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennuksen SDK:n uusinta ominaisuutta, joka tarjoaa sekä symmetrisen että asymmetrisen salauksen tuen sekä integroinnin [!INCLUDE[pn_azure_key_vault](pn-azure-key-vault.md)] -ratkaisun kanssa. [!INCLUDE[pn_crm_8_2_0_online_subsequent](pn-crm-8-2-0-online-subsequent.md)] -palvelun avulla sähköpostiviestien ja tapaamisten huomautuksista ja liitteistä löytyvät asiakirjat synkronoidaan myös blob-objektisäilöön.  
  
[Azure Active Directory-palvelu](https://azure.microsoft.com/services/active-directory/)  
  
[!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -palvelua käytetään todentamiseen [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)]- ja [!INCLUDE[pn_Windows_Azure](pn-windows-azure.md)] -palveluiden välillä.  
  
[Azuren kuormituksentasain](https://azure.microsoft.com/services/load-balancer/)  
  
[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]n kuormituksentasain jakaa saapuvan liikenteen pilvipalveluiden hyvässä toimintakunnossa oleviin palveluesiintymiin tai virtuaalikoneisiin, jotka on määritetty kuormituksentasainjoukossa. Osuvuushaku käyttää sitä lopetuspisteiden kuormituksen tasaamiseen käyttöönotoissa.  
  
[Azure-näennäisverkot](https://azure.microsoft.com/documentation/articles/virtual-networks-overview/)  
  
Service Fabric -klusterin näennäiskoneet, jotka toimivat yhdessä tai useammassa aliverkossa, yhdistää [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-näennäisverkko. Tämän näennäisverkon sisällä olevat suojauskäytännöt, DNS-asetukset, reititystaulukot ja IP-osoitteet ovat täysin näennäisverkon hallinnassa. Verkon käyttöoikeusryhmien avulla sovelletaan suojaussääntöjä näennäisverkossa. Nämä säännöt sallivat tai estävät verkkoliikenteen näennäisverkossa toimivien näennäiskoneiden välillä.