---
title: Virtuaalientiteetti OData v4 -tietopalvelun käyttäminen Common Data Servicen kanssa | MicrosoftDocs
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
ms.assetid: null
caps.latest.revision: null
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="odata-v4-data-provider-configuration-requirements-and-best-practices"></a> OData v4 -tietojen tarjoajan määritys, vaatimukset ja parhaat käytännöt

Tässä ohjeaiheessa kerrotaan, miten OData v4 -tietojen tarjoaja ja OData v4 -tietojen tarjoajan vaatimukset ja parhaat käytännöt määritetään, kun OData v4 -tietojen tarjoajaa käytetään muodostettaessa yhteys OData v4 -verkkopalveluun. 

## <a name="odata-v4-data-provider-best-practices"></a>OData v4 -tietojen tarjoajan parhaat käytännöt

- Common Data Service edellyttää, että kaikilla entiteeteillä on ID-määrite. ID on sama kuin yksilöivä tunnus. Arvon on oltava guid.  Voit yhdistää ID-kentät vain sellaisiin ulkoisiin kenttiin, joiden tietotyyppi on `Edm.Guid`.  Et voi liittää tietotyyppiä `Edm.Int32` yksilöllisen tunnuksen tietotyypin kenttään Common Data Service -ratkaisussa.
-  OData-entiteetit, joilla on tyhjä arvo -ominaisuuksia, on määritettävä vastaamaan virtuaalisen entiteetin yhdistettyä kenttää. Esimerkiksi OData-entiteetin ominaisuuden, jonka tyhjä arvo = epätosi, on oltava yhdistetty kenttä Common Data Servicessä ja **Kenttävaatimus**-määritteeksi on annettava **Pakollinen**. 
- Voit hakea useita kyselyjä esimerkiksi ladatessasi tietoja ruudukkoon, jos ohjaat ulkoisesta tietolähteestä palautettavan tietojoukon kokoa käyttämällä kyselyparametrien valintaa ja suodatusta.
- Jos tämä ei ole käytössä, järjestelmänvalvoja voi ottaa laajennuksen seurannan käyttöön. Kun tämä on käytössä, kaikki OData-päätepisteen virheet kerätään laajennuksen seurantalokiin. Lisätietoja: [Järjestelmänvalvojan opas: Järjestelmäasetukset-valintaikkuna – Mukauttaminen-välilehti](/dynamics365/customer-engagement/admin/system-settings-dialog-box-customization-tab) 

## <a name="data-type-mapping"></a>Tietotyyppien yhdistämismääritys

Seuraavassa taulukossa ovat OData Entity Data Model (EDM) -tietotyyppien yhdistämismääritykset ja Common Data Service tietotyypit.. 

|OData-tietotyyppi|Common Data Service:n tietotyyppi  |
|---------|---------|
|`Edm.Boolean`|Kaksi asetusta|
|`Edm.DateTime`|Päivämäärä ja aika|
|`Edm.DateTimeOffset`|Päivämäärä ja aika|
|`Edm.Decimal`|Desimaaliluku tai valuutta|
|`Edm.Double`|Liukuluku|
|`Edm.Guid`|Yksilöllinen tunnus|
|`Edm.Int32`|Kokonaisluku|
|`Edm.Int64`|Kokonaisluku|
|`Edm.String`|Yksi tekstirivi tai useita tekstirivejä|


### <a name="odata-edm-data-types-that-are-not-supported-for-mapping-with-virtual-entities"></a>OData EDM -tietotyypit, joita ei tueta virtuaalisten entiteettien vastaavuusmäärityksissä 

- `Edm.Binary`
- `Edm.Time` 
- `Edm.Float`
- `Edm.Single` 
- `Edm.Int16` 
- `Edm.Byte` 
- `Edm.SByte`

 
## <a name="add-a-data-source-using-the-odata-v4-data-provider"></a>Tietolähteen lisääminen OData v4 -tietojen tarjoajan avulla

Tässä toimintosarjassa on esitetty, miten voit käyttää virtuaalisen entiteetin tietolähteenä valmista OData-tietojen tarjoajaa.   
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Administration** > **Virtuaalisten entiteettien tietolähteet**.  
1. Valitse Toiminnot-työkaluriviltä **Uusi**.  
1. Valitse seuraavista tietolähteistä **Valitse tietojen tarjoaja** -valintaikkunassa ja valitse sitten **OK**.  
  
    - **OData v4 -tietojen tarjoaja**. Common Data Service sisältää Odata-v4 -tietojen toimittajan, jonka avulla voidaan muodostaa yhteys tietolähteiden tietoihin, jotka tukevat OData v4 avoin standardia.  
    - *Mukautettujen tietojen tarjoaja*. Jos olet tuonut tietopalvelulaajennuksen, tietopalvelu tulee näkyviin tähän. Lisätietoja:  [Sovelluskehittäjän dokumentaatio: Virtuaalientiteettien käytön aloittaminen](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)  
    
1. Täytä seuraavat kentät **Uusi tietolähde ominaisuudet** -sivulla ja tallenna tietue.  
  
    - **Nimi**. Kirjoita tietolähteen kuvaava nimi.  
    - **Uri**. Jos käytössäsi on OData-tietojen tarjoaja, kirjoita OData-verkkopalvelun uri-arvo. Esimerkiksi käytettäessä OData-palvelua muodostamaan yhteyden azuren isännöimään WWW-palveluun, URI-osoite voi näyttää tällaiselta *`http://contosodataservice.azurewebsites.net/odata/`*.  
    - **Aikakatkaisu sekunteina**. Anna verkkopalvelun vastauksen odotusaika sekunteina. Tämän jälkeen tietopyyntö aikakatkaistaan. Voit esimerkiksi antaa arvoksi 30, jolloin odotusaika on enintään 30 sekuntia ennen aikakatkaisua.  
    - **Sivutustila**. Määritä, käytetäänkö kyselyn tulosten sivutuksessa asiakas- vai palvelinpuolen sivutusta. Oletusarvo on asiakaspuolen sivutus. Palvelinpuolen sivutuksessa palvelin ohjaa tulosten sivutusta $skiptoken-parametrin avulla. Parametri lisätään kyselymerkkijonoon. Lisätietoja: [Tunnusjärjestelmän kyselyvaihtoehdon ohittaminen ($skiptoken)](https://msdn.microsoft.com/library/dd942121.aspx)  
        -  **Palauta sidottu määrä**. Palauttaa tulosjoukon tietueiden kokonaismäärän. Tätä asetusta käytetään, kun seuraava sivu -toiminto otetaan käyttöön palautettaessa tietoja ruudukkoon. Käytä epätosi-arvoa, jos OData-päätepiste ei tue ODatan $inlinecount-parametria. Oletusarvo on epätosi.
    - **Pyyntöparametrit**. Vaihtoehtoisesti voit lisätä oman otsikon tai kyselyn kyselymerkkijonon parametrit, joiden avulla voidaan muodostaa yhteys OData verkkopalveluun, kuten todennusparametrit ulkoisen palveluun. Valitse että **kyselymerkkijonon** avulla tila voidaan vaihdella ylätunniste- ja kyselyn kyselymerkkijonon parametrin ja arvo välillä. Enintään 10 ylätunniste- tai kyselymerkkijonoa voidaan lisätä. 
        > [!div class="mx-imgBorder"] 
        > ![Virtuaalisen entiteetin tietolähteen tietue](media/virtual-entity-data-source.png) 


## <a name="see-also"></a>Katso myös  

[Virtuaalisten entiteettien, jotka sisältävät ulkoisen tietolähteen tietoja, luominen ja muokkaaminen](create-edit-virtual-entities.md) <br/>
[TechNet-blogi: Vuorovaikutus ulkoisten järjestelmien tietojen kanssa uusien virtuaalisten entiteettien avulla](https://blogs.technet.microsoft.com/lystavlen/2017/09/08/virtual-entities/)
