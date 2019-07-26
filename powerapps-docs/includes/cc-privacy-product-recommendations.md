---
ms.openlocfilehash: 1cdcb40245aae9a23ecb6d3392e412f8a60b95ba
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67212303"
---
Kun otat käyttöön Tuotesuositukset-ominaisuuden ja luot suositusmallin kohteessa [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)], määritettyihin Basket Data -entiteetteihin ja niiden suodattimeen perustuvat historiatiedot lähetetään kohteeseen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] ja käsitellään kohteessa [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)], minkä jälkeen ne tallennetaan tilapäisesti [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennukseen ja lähetetään lopulta Azure Recommendations -ohjelmointirajapintaan koneoppimismallin luomiseksi. Kun malli on luotu Azure Recommendations -ohjelmointirajapinnalla, tiedot poistetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennuksesta. Huomaa, että vain tunnukset (tilin tunnus, tuotetunnus, tapahtumatunnus) lähetetään kohteeseen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] suositusmallin luomista varten.

Järjestelmänvalvoja voi ottaa Tuotesuositukset-ominaisuuden käyttöön kohdan **Asetukset**&gt;**Hallinta**&gt;**Järjestelmäasetukset** &gt; **Esikatselu**-välilehdellä [!INCLUDE[pn_microsoftcrm](pn-microsoftcrm.md)] organisaatiossa. Tiedot lähetetään Azure Recommendations -ohjelmointirajapintaan vain, kun suositusmalli on luotu. Järjestelmänvalvoja voi poistaa olemassa olevan mallin Azure Recommendations -ohjelmointirajapinnan kanssa jaettujen tietojen poistamiseksi. Lisäksi järjestelmänvalvoja voi poistaa yhteyden Azure Recommendations -ohjelmointirajapintaan tulevien suositusmallien estämiseksi.

Kohteen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] osat ja palvelut, jotka liittyvät Tuotesuositukset-ominaisuuteen, eritellään seuraavissa osioissa.

[!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]

[Azure Logic Apps](https://azure.microsoft.com/services/app-service/logic/)

Tämä tarjoaa koordinoidun tietoputken tuoteluettelon ja tapahtumatietojen synkronoimiseksi Recommendations-ohjelmointirajapinnan kanssa, jotta suositusmalliversio voidaan luoda. Tämä putki suoritetaan usean vuokraajan palveluna useilla ohjelmointirajapintasovelluksilla, jotka mahdollistavat tiedonsiirron Dynamics 365 -organisaation ja Recommendations-ohjelmointirajapinnan välillä. Logiikkasovellukset käynnistetään kohteesta [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] mahdollisimman vähäisellä kontekstilla, kuten malliversiotunnuksella ja [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] organisaation URL-osoitteella. 

[Azure-ohjelmointirajapintasovellukset](https://azure.microsoft.com/services/app-service/api/)

Nämä verkkosovellukset käynnistävät verkkotyöt, jotka lukevat tietoja [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] organisaatiosta ja lähettävät tietoja Recommendations-ohjelmointirajapintaan suositusmallin luomiseksi. Järjestelmässä on kolme ohjelmointirajapintasovellusta ja vastaavat verkkotyöt- yksi tuotetietojen lukemiseen, yksi tapahtumatietojen lukemiseen ja yksi suositusmallin luomiseen. API-sovellus käyttää verkkotyötä todellisen tietojenkäsittelyn suorittamiseen taustalla ja tietotulosten kirjoittamiseen [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön. Tiedot tallennetaan väliaikaisesti [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön. Lopuksi tiedot poistetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-tallennuksesta, kun malli on luotu.

[Azuren taulukot](https://azure.microsoft.com/services/storage/tables/)

[!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Taulukkoa käytetään mallin versio ja organisaation konteksti välisessä kommunikaatiossa ohjelmointirajapintasovelluksen ja verkkotyön välillä.

[Azure Blob -säilö](https://azure.microsoft.com/services/storage/) 

Verkkotyöt tallentavat tiedot tilapäisesti [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)] Blob -säilöön, josta ne poistetaan, kun Logic App -putki on käsitelty.

[Azure Recommendations -ohjelmointirajapinta](https://www.microsoft.com/cognitive-services/en-us/recommendations-api) Azure Recommendations -ohjelmointirajapinta lähetetään mahdollisimman vähäisillä tiedoilla, kuten tuotetunnuksilla, tapahtumatunnuksilla ja tilitunnuksilla suositusmallin luomiseksi. Tiedot tallennetaan Recommendations-ohjelmointirajapinnan palveluun, kunnes vastaava malliversio on olemassa.
