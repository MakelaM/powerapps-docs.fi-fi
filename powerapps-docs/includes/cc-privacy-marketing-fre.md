Ottamalla käyttöön [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksen hyväksyt tietojen siirron [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] -sovelluksesta tiettyihin [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palveluihin, jotta voit suorittaa joitakin markkinoinnin prosesseja. Näitä palveluja kutsutaan yhdessä ”[!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluiksi”.

Asiakassiirtymien käsittelemiseksi [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksen on lähetettävä asiakassiirtymä, sähköpostiosoite, lähetyslomake ja markkinointisivun määritelmät näihin [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluihin, joita suoritetaan [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]issa. Markkinointisivut lähetetään edelleen asiakkaan omaan [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] -portaalitoimintojen esiintymään.

Voit mukauttaa lähetettyjä sähköpostiviestejä ottamalla [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]-sovelluksessa käyttöön tiedonsiirron [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]in kanssa. Alla on lisätietoja [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palvelusta. Tiedonsiirto [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun sisältää yhteyshenkilöiden ja tilien synkronoinnin [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun. [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palvelut käyttävät näitä tietoja sähköpostiviestien sisällön mukauttamiseen. Käytettävät tiedot riippuvat yksinomaan sähköpostiviestin määritelmästä.

Jotta voisit laskea liidien pisteytysmallit sekä markkinointisegmentit uudelleen, [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksen pitää lähettää liidien pisteytysmallin ja segmentin määritelmät [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun ja käyttää profiileita ja vuorovaikutuksia [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palvelun laskelmissa.

[!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluiden rekisteröimien sähköposti- ja internetvuorovaikutusten analysoimiseksi vuorovaikutusten tiedot lähetetään [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluista sekä [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)]- että [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -sovellukseen.

Jos lisäksi [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksen tapahtumien hallinnan integrointi on otettu käyttöön, [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] synkronoi tapahtumat [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun (suoraan [!INCLUDE[pn-crm-online-shortest](../includes/pn-crm-online-shortest.md)] -yhdistimen kautta) ja tapahtumien rekisteröitymiset ja sisäänkuittaukset ([!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluiden kautta vuorovaikutuksina).

[!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun liittyvä tiedonkulku toimii seuraavasti:
- Entiteetin tiedot [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksesta [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun käyttäen [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]in tavallista sisään tulevan tiedon yhdistintä sisällön tuottamiseksi sähköpostiviestien mukauttamiseen, liidien pisteytykseen ja segmentointiin (pääasiassa yhteyshenkilöt ja tilit, myöhemmin myös liidit ja tapahtumat).
- Entiteetin tiedot [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksesta [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluiden kautta [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun vuorovaikutusten ja tietonäkymien tunnisteiden muodostamiseksi (asiakassiirtymät, markkinointisähköpostiviestit ja markkinointisivut)
- Vuorovaikutukset [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluista [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun (sähköpostin seuranta, verkkosivuston seuranta, asiakassiirtymän edistyminen)
- Vuorovaikutukset [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksesta [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluiden kautta [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun (tapahtumien rekisteröitymiset ja sisäänkuittaukset)
- [!INCLUDE[pn-insights](../includes/pn-insights.md)] (vuorovaikutukset ja tunnusluvut) [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palvelusta [!INCLUDE[pn-marketing-app-module](../includes/pn-marketing-app-module.md)] -palveluiden kautta [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovellukseen (pääasiassa asiakassiirtymien ja sähköpostiviestien lähetyksen edistyminen sekä liidipisteytyksen tulokset)
- [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -sovellukset (segmentoinnit ja pienoissovellukset)[!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palvelusta suoraan [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovelluksen lomakkeiden kiinteisiin ja eristettyihin käyttöliittymäelementteihin

### <a name="marketing-services"></a>Marketing-palvelut

[!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] käyttää seuraavia [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palveluita:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] DocumentDB
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tallennustila

> [!NOTE]
> Lisätietoja muista [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] -tuotteista on kohdassa [!INCLUDE[cc_privacy_note_azure_trust_center](../includes/cc_privacy_note_azure_trust_center.md)] (<https://azure.microsoft.com/support/trust-center/>).

### [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)]

Käyttämällä [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] -sovellusta aktivoit asiakastietojen siirron [!INCLUDE[pn-customer-insights-full](../includes/pn-customer-insights-full.md)] -palveluun jatkokäsittelyä varten. [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] -palvelun käyttösi saattaa edellyttää erityisten tietosuojalakien noudattamista. Osoita mahdolliset kysymykset oman organisaatiosi edustajalle.

Tällä hetkellä [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] on julkinen esiversio, eikä se tarjoa saman tason tietosuojaa ja tietoturvaa kuin [!INCLUDE[pn-marketing-business-app-module-name](../includes/pn-marketing-business-app-module-name.md)] tai [!INCLUDE[pn-microsoftcrm](../includes/pn-microsoftcrm.md)] Customer Engagement. [!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] pohjautuu sisäisesti [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] -palveluihin, ja kuhunkin käytettävään [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] -palveluun sovelletaan sen palvelun sääntöjenmukaisuuden ja tietoturvan standardeja. Lisätietoja löydät [!INCLUDE[cc-microsoft](../includes/cc-microsoft.md)] Trust Centeristä: [https://azure.microsoft.com/support/trust-center/](https://azure.microsoft.com/support/trust-center/)

[!INCLUDE[pn-customer-insights-short](../includes/pn-customer-insights-short.md)] käyttää seuraavia [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-palveluita:

- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Data Lake Analytics
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] HDInsight (Spark, Phoenix, HBase)
- [!INCLUDE[pn-ms-azure-sql-database](../includes/pn-ms-azure-sql-database.md)]
- [!INCLUDE[pn-azure-key-vault](../includes/pn-azure-key-vault.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Secret Store
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Tapahtumakeskus
- [!INCLUDE[pn-azure-stream-analytics](../includes/pn-azure-stream-analytics.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Redis -välimuisti
- [!INCLUDE[pn_azure_service_fabric](../includes/pn_azure_service_fabric.md)]
- [!INCLUDE[pn-microsoft-azure-active-directory](../includes/pn-microsoft-azure-active-directory.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-seuranta
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] Metrics
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-verkkosivustot
- [!INCLUDE[pn_azure_service_bus](../includes/pn_azure_service_bus.md)]
- [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)]-tallennustila
