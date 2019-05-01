---
ms.openlocfilehash: 252f09737dbf55309a64ef5d02d479fde0e61c0e
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61571884"
---
Kun otat käyttöön sähköpostin seurannan (se on upotettu älykäs toiminto) ja **Seuraa**-asetuksella merkitty sähköposti lähetetään palvelusta [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)], tiedot vastaanottajien toimista sähköpostille kerätään ja tallennetaan palveluun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Tämän avulla voidaan laskea seurattujen sähköpostien vastaanottajien toimien suorituskykyilmaisimet ja toimet seuratuille sähköposteille.  
  
 Järjestelmänvalvoja voi ottaa sähköpostin seurannan käyttöön valmistelemalla toiminnon upotetun älykkään toiminnon **Sähköpostin seuranta** -välilehdessä. Järjestelmänvalvojat voivat myös poistaa sähköpostin seurannan käytöstä organisaatiossa **Älykkään toiminnon määritykset** -solmun **Asetukset**-kohdassa.  
  
 Kun tiedosto on poissa käytöstä, palvelusta [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] lähetettyjä sähköpostiviestejä ei voi seurata käyttöliittymässä tai ohjelmallisesti. Lisäksi vastaanottajien toimintojen tietoja ei enää kerätä lähetetyistä sähköpostiviesteistä, jotka oli merkitty **Seuraa**-asetuksella. Kaikki aiemmin kerätyt tiedot säilyvät kuitenkin palvelussa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]. Ne ovat taas käytettävissä, jos tämä toiminto otetaan käyttöön uudelleen organisaatiossa. Tietoja säilytetään 90 päivän ajan sen jälkeen, kun asiakas irtisanoo Microsoft-tilauksensa. Palvelun [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] käyttäjät voivat myös poistaa upotetun älykkään toiminnon sähköpostin seurantatoiminnon käytöstä yhteyshenkilö- tai liidikohtaisesti. Tämä on mahdollista muokkaamalla **yhteysasetusten** **Seuraa sähköpostia** -asetusta.  
  
 Palvelun [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] komponentit ja palvelut, jotka liittyvät sähköpostin seurantatoimintoon, on eritelty alla.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 **[!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)]**  
  
 Sähköpostin seurantatoiminto tallentaa sähköpostien toimien blob-objektit tilapäisesti palvelun [!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)] avulla.