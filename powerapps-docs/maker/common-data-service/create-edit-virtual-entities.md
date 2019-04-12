---
title: Virtuaalisten entiteettien luominen ja muokkaaminen Common Data Servicen avulla | MicrosoftDocs
description: Tietoja virtuaalisten entiteettien luomisesta
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 44834893-0bf6-4a64-8f06-7583fe08330d
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-virtual-entities-that-contain-data-from-an-external-data-source"></a>Virtuaalisten entiteettien, jotka sisältävät ulkoisen tietolähteen tietoja, luominen ja muokkaaminen

Virtuaalinen entiteetti on Common Data Servicen mukautettu entiteetti, jonka kentät sisältävät tietoja ulkoisesta tietolähteestä. Virtuaaliset entiteetit näkyvät sovelluksen käyttäjille tavallisina entiteettitietueina, mutta ne sisältävät tietoja, jotka on noudettu ulkoisesta tietokannasta (esimerkiksi Azure SQL Databasesta). Virtuaalisiin entiteetteihin perustuvat tietueet ovat käytettävissä kaikissa asiakasohjelmissa, Common Data Servicen verkkopalvelun avulla kehitetyt mukautetut asiakasohjelmat mukaan lukien.  
  
Menneisyydessä voidakseen integroida eri tietolähteitä niitä varten piti kehittää yhdysohjelma tietojen liikuttamiseen tai luoda mukautettu laajennus joko asiakas- tai palvelinpuolelle. Kuitenkin virtuaalientiteetteihin voi yhdistää suoraan ulkoisen tietolähteen suorituksen yhteydessä niin, että ulkoisesta lähteestä vaaditut tiedot ovat käytettävissä ympäristössä ilman tarvetta tietojen replikointiin.  

Virtuaalientiteetit koostuvat kolmesta tärkeimästä osasta *tietopalvelu*, *tietolähde* tietue ja *näennäisentiteetti*. Tietojen toimittaja koostuu laajennuksista ja tietojen lähde-entiteetistä. Tietojen lähde on entiteettitietue Common Data Servicessä, joka sisältää metatiedot, joka vastaa yhteyden parametrien rakennetta. Kukin näennäisentiteetti viittaa tietolähteeseen kohdemäärityksessä.  
  
Common Data Service sisältää OData-tietojen toimittajan, jonka avulla voi yhteyden muodostaa OData v4 -verkkopalveluun, joka käyttää ulkoisia tietoja. 
  
Sovelluskehittäjät voivat myös muodostaa omat tietopalvelut. Tietopalvelut asennetaan ympäristöön ratkaisuna. Lisätietoja: [Sovelluskehittäjän dokumentaatio: Virtuaalientiteettien käytön aloittaminen](../../developer/common-data-service/virtual-entities/get-started-ve.md)
  
 ![Virtuaalisen entiteetin kaavio](media/virtual-entity-diagram.png "Virtuaalisen entiteetin kaavio")  
  
<a name="benefits"></a> 
  
## <a name="virtual-entity-benefits"></a>Näennäisentiteettiin edut  
  
- Sovelluskehittäjät voivat ottaa käyttöön ulkoisia tietoja lukevia laajennuksia käyttämällä Common Data Servicen verkkopalveluita ja laajennusten rekisteröintityökalua.  
- Järjestelmän mukauttajat valitsevat PowerAppsin ratkaisunhallinnan tietolähdetietueen määrittämistä ja virtuaalientiteettien luomista varten. Niitä voidaan käyttää ulkoisten tietojen näkemiseen kirjoittamatta yhtään koodia.  
- Loppukäyttäjät tarkastelevat kenttien, ruudukkojen, hakutulosten sekä Fetch XML -pohjaisten raporttien ja koontinäyttöjen tietoja virtuaalisen entiteetin luomissa tietueissa.  
  
<a name="AddDataSource"></a> 
  
## <a name="add-a-data-source-to-use-for-virtual-entities"></a>Lisää tietolähde käyttämään virtuaalientiteettiä 
 
 Kehittäjät voivat luoda mukautettuja laajennuksia, jota käytetään virtuaalisen entiteetin tietolähteenä.  Vaihtoehtoisesti voit käyttää annettua OData v4 -tietojen tarjoajaa. Lisätietoja: [OData v4 -tietojen tarjoajan määritys, vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Administration** > **Virtuaalisten entiteettien tietolähteet**.  
1. Valitse Toiminnot-työkalurivillä  **Uusi**.  
1. Valitse seuraavista tietolähteistä **Valitse tietopalvelu**-valintaikkunassa ja valitse sitten **OK**.
 
    |Tietojen tarjoaja|Kuvaus|
    |--|--|
    |*Mukautettujen tietojen tarjoaja*|Jos olet tuonut tietopalvelulaajennuksen, tietopalvelu tulee näkyviin tähän. Lisätietoja on kohdassa [Sovelluskehittäjän dokumentaatio: Virtuaalientiteettien käytön aloittaminen](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)|
    |**OData v4 -tietojen tarjoaja**|Common Data Service sisältää OData-tietojen tarjoajan, jota voi käyttää OData v4 -verkkopalveluissa. Lisätietoja on kohdassa [OData v4 -tietojen tarjoajan määritys, vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)|

  
### <a name="add-a-secured-field-to-a-data-source"></a>Suojatun kentän lisääminen tietolähteeseen

Voit luoda tietolähteelle kenttiä samalla tavalla kuin mille tahansa entiteetille. Ota salatuille tai arkaluontoisille tiedoille käyttöön tietolähteen salainen määrite tietolähteen mukautetun kentässä. Voit esimerkiksi suojata kentän, joka sisältää tietokannan yhteysmerkkijonon. 

> [!NOTE]
> Tietolähteen salainen määrite on käytettävissä vain tietolähdelomakkeeseen lisätyissä kentissä.

> [!div class="mx-imgBorder"] 
> ![Tietolähteen salainen määrite](media/datasourcesecret.png)
  
<a name="createVirtualEntity"></a> 
  
## <a name="create-a-virtual-entity"></a>Virtuaalikohteen luominen
  
Voit luoda virtuaalisen entiteetin samalla tavalla kuin minkä tahansa muun entiteetin Common Data Servicessä. Voit luoda myös joitakin ylimääräisiä määritteitä tässä kuvatulla tavalla. Virtuaaliset entiteetit on luotava ratkaisunhallinnan avulla.

> [!NOTE]
>  Vaikka voit luoda virtuaalisen entiteetin valitsemalla tietolähteeksi **Ei mitään**, virtuaalisen entiteetin hankkiminen edellyttää, että tietolähde määritetään. Lisätietoja on kohdassa [Tietolähteen lisääminen virtuaalisissa entiteeteissä käyttämistä varten](#AddDataSource)

### <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luomasi virtuaalisen entiteetin nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle virtuaaliselle entiteetille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="create-a-virtual-entity"></a>Virtuaalikohteen luominen
  
1. Luo uusi entiteetti ratkaisunhallinnassa. Valitse vasemmasta siirtymisruudusta **Entiteetit** ja valitse **Uusi**.  
2. **Yleiset** -välilehdessä **entiteetin määritykset** valitse **näennäisentiteetti** ja valitse sitten **Tietolähde** -pudotusvalikosta tietolähde, jonka haluat.  

    > [!div class="mx-imgBorder"] 
    > ![Virtuaalisen entiteetin asetus entiteetin määrityksessä](media/virtual-entity-click-option.png)  
  
1. Entiteetin määrityksessä täytä seuraavat pakolliset kentät.
  
    |Kenttä|Kuvaus|
    |--|--|
    |**Ulkoinen nimi**|Anna sen ulkoisen tietolähteen taulukon nimi, johon tämä entiteetti on yhdistetty.|
    |**Ulkoinen kokoelman nimi**|Anna sen ulkoisen tietolähteen taulukon monikkonimi, johon tämä entiteetti on yhdistetty.|
      
    Seuraavassa on esimerkki virtuaalientiteetistä, jonka nimi on *elokuva*, joka käyttää Cosmos Azure-tietokannan tietojen tarjoajaa tiedostoihin pääsemiseksi.  
      
    > [!div class="mx-imgBorder"] 
    > ![Virtuaalisen entiteetin määritys Azure Cosmos DB -tietojen tarjoajan avulla](media/virtual-entity-definition.PNG)  
      
    > [!IMPORTANT]
    > Virtuaalientiteettien kanssa ei voi käyttää useita vaihtoehtoja, kuten ryhmien käyttöoikeuksia, työjonoja ja pikaluontia. Lisätietoja on kohdassa [Huomioon otettavia seikkoja virtuaalisten entiteettien käyttämisen yhteydessä](#considerations)  
      
    Täytä pakollisista ja valinnaisista lisäominaisuudet, kuten näyttäminen ja monikkomuotoinen nimi, tarpeen mukaan. Lisätietoja näistä ominaisuuksista on artikkelissa [Entiteettien luominen ja muokkaaminen](create-edit-entities.md).  
  
1. Luo ja Lisää yksi tai useampi kenttä virtuaalientiteettiin. Standardikenttäominaisuuksien lisäksi, joita tarvitsee voidakseen luoda mukautetun kentän, voi näitä valinnaisia ominaisuuksia käyttää kaikille mukautetuille kentille, joita luodaan virtuaalista entiteettieä varten.

    |Kenttä|Kuvaus|
    |--|--|
    |**Ulkoinen nimi**|Tämä on yleensä yksilöllinen nimi, jolla tunnistetaan kentässä näytettävät tiedot.|
    |**Ulkoisen tyypin nimi**|Jos luotu kenttätyyppi on OptionSet: Tämä ominaisuus on yhdistetty asetusjoukon ulkoisen palvelun arvojoukon ulkoiseen nimeen.  Yleensä tämä voi olla luettelointi tai merkkijonon arvoluokan nimi. Ulkoista tyyppinimi voidaan käyttää, kun täydellinen nimi on pakollinen.  Esimerkiksi *tyyppinimi* ja OData, jolla on kyselyn parametreja, vaativat täydellisen nimen, kuten [*Tyyppinimi*].[*Arvo*].|
    |**Ulkoinen arvo**|Jos luotu kenttätyyppi on OptionSet: Tämä ominaisuus on yhdistetty asetusjoukon nimikkeen ulkoisen tietolähteen vastaavaan arvoon.  Tämä annettu arvo käytetään määrittämään, mikä asetusjoukkokohde näytetään sovelluksessa.  |

    Täytä lisäominaisuudet tarpeen mukaan. Lisätietoja näistä ominaisuuksista on artikkelissa [Kenttien luominen ja muokkaaminen](create-edit-fields.md).  
  
1. Valitse **Tallenna ja sulje** - **kentän** ominaisuudet -sivulla.  
1. Valitse ratkaisunhallintatyökaluriviltä **Tallenna**.  
1. Valitse ratkaisunhallintatyökaluriviltä **Julkaise**.  
1. Sulje ratkaisunhallinta.  

<a name="considerations"></a>
   
## <a name="considerations-when-you-use-virtual-entities"></a>Kun käyttää virtuaalientiteettejä, huomioon otettavia seikkoja  

Virtuaalientiteeteillä on rajoitukset.  
  
- Kaikki virtuaaliset entiteetit ovat vain luku -tilassa.  
- Aiemmin luotuja entiteettejä ei voi muuntaa virtuaalisiksi entiteeteiksi.  
- Virtuaalientiteeteissä on oletusarvoisesti vain Nimi- ja Tunnus-kenttä.  Mitään muita järjestelmän hallitsemia kenttiä, Tila tai Luotu/Muokattu, ei tueta.
- Virtuaalientiteetit eivät tue mukautettuja kenttiä, joiden tietotyyppi on valuutta, kuva tai asiakas.
- Virtuaalientiteetit eivät tue seurannan.  
- Päivityskokoelmissa tai laskettujen kentissä virtuaalientiteettien kenttiä ei voi käyttää.
- Virtuaalientiteetti ei voi olla entiteetin aktiviteetin tyyppi.  
- Virtuaalisissa entiteeteissä ei voi ottaa käyttöön useita entiteettitaulukon riveihin vaikuttavia ominaisuuksia.  Esimerkkejä ovat jonot, tietämyksenhallinta, SLA-sopimukset, kaksoiskappaleiden tunnistus, muutosten seuranta, Mobile Offline -ominaisuus, kenttien suojaus, osuvuushaku, Dynamics 365:n verkkoportaalin ratkaisujen portaalit ja virtuaalientiteettien väliset N:N-suhteet.  
- Organisaatiot omistavat virtuaaliset entiteetit. Niissä ei tueta rivitason Common Data Servicen suojaukseen liittyviä käsitteitä. Suosittelemme, että ulkoisen tietolähde oma suojausmalli otetaan käyttöön.  
- On suositeltavaa käyttää kohteena yksi tietolähde Erikoishaussa kun käyttää virtuaalientiteettejä. Esimerkiksi sellaisen Erikoishaku-toiminnon luontia, joka luo lopulta liitoksen Common Data Servicen alkuperäisien tietojen ja virtuaalientiteetin ulkoisien tietojen välille, ei suositella.  
- Päivityksen yhteydessä tarkistettavat kentän metatietojen ominaisuudet eivät koske virtuaalisia entiteettejä. Esimerkiksi virtuaalisen entiteetin Kokonaisluku-kenttä voidaan määrittää niin, että pienin mahdollinen arvo on nolla. Koska arvo saadaan ulkopuolisesta tietolähteestä, kysely kuitenkin palauttaa nollaa pienemmät arvot, kun arvot haetaan virtuaalisesta entiteetistä.  Vähimmäisarvon ominaisuutta ei oteta huomioon kyselyssä.  Arvot on kuitenkin suodatettava, jotta saadaan haluttu nollaa suurempi arvo.
- Virtuaaliset entiteetit eivät tue muutosten seurantaa. Niitä ei voi synkronoida käyttämällä Common Data Service -toimintoa, kuten tietojen vientipalvelua.
  
### <a name="see-also"></a>Katso myös  

[OData v4 -tietojen tarjoajan vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)</br> 
[Entiteettien luominen ja muokkaaminen](create-edit-entities.md)</br>
[Kenttien luominen ja muokkaaminen](create-edit-fields.md)
