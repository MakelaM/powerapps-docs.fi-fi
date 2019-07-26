---
ms.openlocfilehash: f331670a2fd6b051c91a7fe2bfa607c54c9ab41a
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67225240"
---
Ottamalla käyttöön asetuksen [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] sallit tiedonkulun kohteesta [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] tiettyihin [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palveluihin tiettyjen markkinointiprosessien suorittamiseksi. Näihin palveluihin viitataan yhteisesti nimellä [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palvelut.

Asiakassiirtymää varten [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]-sovelluksen on lähetettävä asiakassiirtymä, sähköposti, lähetyslomake ja markkinointisivun määritykset näihin [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palveluihin, jotka suoritetaan kohteessa [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]. Markkinoinnin sivut lähetetään edelleen asiakkaan omaan Portal-esiintymään kohteelle [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)].

Lähetettyjen sähköpostiviestien mukauttamiseksi [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] on otettava käyttöön kahdensuuntainen tiedonkulku kohteen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] kanssa. Alla on lisätietoja [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]-palvelusta. Tiedonkulku kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] sisältää yhteystietojen synkronointi ja tilien synkronoinnin kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]. [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palvelut käyttävät näitä tietoja sähköpostisisällön mukauttamiseen. Sisältyvät tiedot määräytyvät yksinomaan sähköpostin määrityksen mukaan.

Liidin pistemäärämallien ja markkinointisegmenttien uudelleenlaskentaa varten [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] lähettää liidin pistemäärän määritykset ja segmentin määritykset kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] ja hyödyntää profiileja ja vuorovaikutuksia kohteessa [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] näissä laskutoimituksissa.

Jotta tietoja voidaan tarjota [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palvelujen keräämiin sähköposti- ja Internet-vuorovaikutuksiin, kerätyt tiedot siirretään [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palveluista kohteisiin [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] ja [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)].

Jos lisäksi [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] tapahtumien hallinnan integrointi on käytössä, [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] synkronoi tapahtumat kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (suoraan [!INCLUDE[pn-crm-online-shortest](../includes/pn-crm-online-shortest.md)] yhdistimen kautta) sekä tapahtuman rekisteröinnit ja kirjautumiset ([!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] palvelujen kautta vuorovaikutuksina).

Kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] liittyvä tiedonkulku on seuraavanlainen:
- Entiteettitiedot välillä [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] - [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] käyttäen kohteen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] tavallista saapuvan liikenteen yhdistintä, jotta sisältöä voidaan tarjota sähköpostin mukauttamiseen, liidien pisteyttämiseen ja segmentointiin (pääasiassa yhteystiedot ja tilit, lopulta myös liidit ja tapahtumat)
- Entiteettitiedot kohteesta [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palvelujen kautta kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)], jotta tunnisteita voidaan tarjota vuorovaikutuksia ja tietoja varten (asiakassiirtymä, markkinointisähköpostit, markkinointisivut)
- Vuorovaikutukset [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palvelusta kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (sähköpostin seuranta, sivuston seuranta, asiakassiirtymän edistyminen)
- Vuorovaikutukset kohteesta [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palvelujen kautta kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] (tapahtuman rekisteröinnit ja kirjautumiset)
- [!INCLUDE[pn-insights](../includes/pn-insights.md)] (vuorovaikutukset ja KPI:t) kohteesta [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)]-palvelujen kautta kohteeseen [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] (pääasiassa asiakassiirtymän ja sähköpostin lähetyksen edistyminen sekä liidien pistetulokset)
- [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] sovellukset (segmentointi ja pienoissovellukset) kohteesta [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] suoraan kohteen [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] eristettyihin käyttöliittymäelementteihin

### <a name="marketing-services"></a>Markkinointipalvelut

[!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] käyttää näitä [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palveluja:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] DocumentDB
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tallennus

> [!NOTE]
> Katso lisätietoja muusta [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palvelutarjonnasta kohdasta [!INCLUDE[cc_privacy_note_azure_trust_center](../includes/cc_privacy_note_azure_trust_center.md)] (<https://azure.microsoft.com/support/trust-center/>).

### [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]

Käyttämällä kohdetta [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] aktivoit asiakkaan tietojen siirtämisen kohteeseen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] jatkokäsittelyä varten. [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] käyttö saattaa edellyttää tiettyjen tietosuojalakien noudattamista. Jos sinulla on kysyttävää, ota yhteyttä asianmukaiseen edustajaan organisaatiossasi.

Tällä hetkellä [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] on julkinen esiversio, joten se ei sisällä samaa tietosuoja- ja turvallisuustasoa kuin [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] tai [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] Customer Engagement. [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] perustuu natiivisti [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palveluihin, ja siihen sovelletaan kunkin [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palvelun vastaavia sääntöjen noudattamisen ja suojauksen standardeja. Lisätietoja saat [!INCLUDE[cc-microsoft](../includes/cc-microsoft.md)] luottamuskeskuksesta: [https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)

[!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] käyttää näitä [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palveluja:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] HDInsight (Spark, Phoenix, HBase)
- [!INCLUDE[pn-ms-azure-sql-database](../includes/pn-ms-azure-sql-database.md)]
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Secret Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Event Hub
- [!INCLUDE[pn-azure-stream-analytics](../includes/pn-azure-stream-analytics.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Redis -välimuisti
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Monitoring
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Metrics
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Websites
- [!INCLUDE[pn_azure_service_bus](../includes/pn_azure_service_bus.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tallennus
