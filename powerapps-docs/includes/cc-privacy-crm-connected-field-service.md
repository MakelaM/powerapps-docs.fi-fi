---
ms.openlocfilehash: ce9db35844f46e9779055ec30dcba0f9459c3a16
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61570892"
---
Kun asennat [!INCLUDE[pn_connected_field_service_msdyn365](pn-connected-field-service-msdyn365.md)] -sovelluksen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tilauksen tietojen antamisen yhteydessä, vaaditut [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-resurssit (lueteltu alla) otetaan käyttöön ja [!INCLUDE[pn_dynamics_crm_online](pn-dynamics-crm-online.md)] -esiintymä lähettää tiedot (kuten komennot ja rekisteröinnit) [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]lle. Näin otetaan käyttöön skenaariot, joissa on käytössä IoT ja jotka rekisteröivät laitteet ja lähettävät komennot rekisteröityihin laitteisiin ja vastaanottavat niitä. Järjestelmänvalvoja voi poistaa toiminnot poistamalla Connected Field Service -sovelluksen asennuksen, ja siirtyä sitten [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-portaaliin, jossa hän voi hallita liittyviä [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-palveluja, joita ei enää tarvita.  
  
 Seuraavissa osioissa esitellään Connected Field Service -toimintoihin liittyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Palveluväylän jono](https://azure.microsoft.com/documentation/articles/service-bus-dotnet-get-started-with-queues/)  
  
 Tämä mahdollistaa jonon [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]- ja [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-sovelluksen välisille saapuville ja lähteville viesteille (komennoille). Kun IoT-ilmoitus lähetetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovellukseen tai [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovelluksesta lähetetään komento IoT-keskittimeen, jono muodostuu tähän.  
  
 [Logic Apps](https://azure.microsoft.com/services/logic-apps/)  
  
 Tämä tarjoaa orkestrointipalvelun, joka käyttää [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -yhdistintä ja jonon yhdistintä. [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -yhdistimiä käytetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovelluksessa käytettävien entiteettien muodostamisessa ja jonon yhdistimiä jonoon liittyvissä kyselyissä.  
  
 [Stream Analytics](https://azure.microsoft.com/services/stream-analytics/)  
  
 Tämä tarjoaa täysin hallinnoidun reaaliaikaisen tapahtumien käsittelyohjelman, jonka avulla voit avata merkitykselliset tiedot. Stream Analyticsin avulla reaaliaikaisen analyysin laskennat on helppo määrittää esimerkiksi laitteista, sensoreista, verkkosivustoista, yhteisöpalveluista, sovelluksista ja infrastruktuurijärjestelmistä saataville tiedoille. Tämä toimii suppilona, jonka avulla valitut IoT-ilmoitukset lähetetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovellukseen.  
  
 [IoT-keskitin](https://azure.microsoft.com/services/iot-hub/)  
  
 Connected Field Services käyttää IoT-keskitintä rekisteröityjen laitteiden ja resurssien tilojen hallinnassa. Lisäksi IoT-keskitin lähettää komennot ja ilmoitukset liitettyihin laitteisiin sekä seuraa viestien toimitusta ja vastaanottokuittauksia. Laiteviestit lähetetään kestävällä tavalla ajoittain liitettynä oleviin laitteisiin.  
  
 **Simulaattori**  
  
 Tämä on testi-WWW-sovellus, joka emuloi komentoja IoT-keskittimeen lähettävää tai komentoja sieltä vastaanottavaa laitetta.  
  
 [Azuren SQL-tietokanta](https://azure.microsoft.com/services/sql-database/)  
  
 Connected Field Service käyttää SQL [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]a laitteen sykeviestien tallennuksessa. Power BI käyttää niitä myöhemmin näyttäessään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -sovelluksen laitteiden tilan.  
  
 [Azure Blob -säilö](https://azure.microsoft.com/services/storage/)  
  
 Stream Analyticsin käyttämät kyselyt tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön.