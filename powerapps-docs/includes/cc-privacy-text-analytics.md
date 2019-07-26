---
ms.openlocfilehash: 80997689e9d4ebca8eb4809cc3e94dab549482b5
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67224718"
---
Ottamalla tekstianalyysi-ominaisuuden käyttöön otat käyttöön myös riippuvaiset ominaisuudet, [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] joilla hyödynnetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] kognitiivisten palveluiden tekstianalyysin ohjelmointirajapintaa tarjoamaan merkityksellisiä tietoja. Näitä riippuvaisia ominaisuuksia ovat:  
  
-   Tietämysehdotukset  
  
-   Palvelupyynnön aiheen analyysi  
  
-   Vastaavien pyyntöjen ehdotukset  
  
 Järjestelmänvalvoja voi ottaa tekstianalyysi-toiminnon käyttöön kohdassa **Asetusten** > **hallinnan** > **järjestelmäasetusten**  >  **esikatselu** -välilehdellä [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] organisaatiossa.  
  
 Ottamalla tekstianalyysi-toiminnon käyttöön, kun määrität tekstianalyysipohjaisia tietämysehdotuksia[!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], palvelupyyntö ja siihen liittyvä entiteettidata lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan poimimaan avainsanoja tai lauseita. Mitään tietoja ei tallenneta [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapinnan avulla. Vain määritetyt kentät tietoartikkelin määrityksissä lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan poimimaan ehdot. Järjestelmänvalvoja tai mukauttaja voi deaktivoida tietoartikkelin määrityksen ja lopettaa ohjelmointirajapinnan kutsut [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan. Myös mukauttajat voivat poistaa tekstianalyysipohjaiset ehdotukset siirtymällä takaisin kenttään perustuviin ehdotuksiin Palvelupyynnön entiteettilomake -määrityksessä.  
  
 Ottamalla tekstianalyysi-toiminnon käyttöön kun määrität palvelupyyntöanalyysia[!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], palvelupyyntö ja siihen liittyvä entiteettidata lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan aiheen määrittämiseksi. Mitään tietoja ei tallenneta [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapinnan avulla. Vain määritetyt kentät aiheen mallin määrityksissä lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan poimimaan aiheet. Järjestelmänvalvoja tai mukauttaja voi deaktivoida aiheen mallin lopettaaksesi kutsut [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan.  
  
 Ottamalla tekstianalyysi-ominaisuuden käyttöön kun määrität samanlaisia palvelupyyntöehdotuksia [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], edistynyt tekstianalyysi -valinta on käytössä samanlaisuussäännössä, ja palvelupyyntö sekä siihen liittyvä entiteettidata lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan poimimaan avainsanoja tai lauseita. Vain samanlaisuussäännössä määritetyt tekstikentät lähetetään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan. Mitään tietoja ei tallenneta [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapinnan avulla. Järjestelmänvalvoja tai mukauttaja voi deaktivoida samanlaisuussäännön lopettaaksesi kutsut [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin ohjelmointirajapintaan.  
  
 Seuraavissa osioissa esitellään tietojen vientipalveluun liittyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut, jotka liittyvät tekstianalyysipohjaisiin ominaisuuksiin.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Azure API -sovellus](https://azure.microsoft.com/services/app-service/api/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Ohjelmointirajapintasovellus käynnistää verkkoyöt, jotka lukevat tietoja [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] organisaatiosta ja lähettävät tietoja Tekstianalyysin ohjelmointirajapintaan aiheiden analyysia varten. [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] API-sovellus käyttää verkkotyötä tekemään todellista tietojenkäsittelyä taustalla ja kirjoittamaan datatulosteita [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-säilöön. Tiedot tallennetaan väliaikaisesti tähän [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-säilöön. Lopuksi tiedot poistetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] säiliöstä, kun aiheen määritys on tehty.  
  
 [Azure-ajoitustoiminto](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Ajoitusta käytetään käynnistämään verkkotyö ajastetusti aiheen analyysin suorittamiseksi. Vain aiheen malliin rakennettu aikataulu jaetaan ajoitustoiminnon kanssa.  
  
 [Azuren taulukot](https://azure.microsoft.com/services/storage/)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Taulukkoa käytetään mallin versio ja organisaation konteksti välisessä kommunikaatiossa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] ohjelmointirajapintasovelluksen ja verkkotyön välillä.  
  
 [Azure Blob -säiliö](https://azure.microsoft.com/services/storage/)  
  
 Verkkotyöt tallennetaan tilapäisesti [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob-säilöön ja poistetaan, kun Logic App -putki on käsitelty.  
  
 [Azure-tekstianalyysin API](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api)  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Tekstianalyysin API:lle lähetetään tiedot, jotka on määritetty aktiivisissa tietohakukentissä tai aiheen mallin määrityksissä tai samanlaisuussäännön määrityksissä. Esimerkiksi palvelupyyntöjen entiteettikentät, kuten otsikko ja kuvaus sekä niihin liittyvien huomautusten ja toimintojen kuvauskentät on määritetty tietojen hakukentän määrityksissä.  
  
 [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]Osuvuushaku  
  
 Voit käyttää Osuvuushakua, jos järjestelmänvalvoja on ottanut sen käyttöön, ja käyttää sitä samankaltaisia tietueiden etsimiseen. Tekstiä vastaavat kentät ja tarkka vastaavuus -kenttä, joita käytetään samanlaisuussäännössä, käytetään Osuvuushaun ohjelmointirajapinnan käynnistämiseen. Lue [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] Osuvuushaku tietojen käsittelyssä.