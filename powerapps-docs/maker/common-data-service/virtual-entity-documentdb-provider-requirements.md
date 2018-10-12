---
title: 'Esikatselutoiminto: Azure Cosmos DB for SQL API Data Providerin käyttö Common Data Service for Appsin kanssa | MicrosoftDocs'
description: Lue ohjeet Azure Cosmos DB for SQL API Data Providerin määrittämiseen virtuaalientiteettien kanssa käytettäväksi.
keywords: SQL-ohjelmointirajapinta
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
caps.latest.revision: ''
topic-status: Drafting
ms.openlocfilehash: fa45376dff85205a0dfbf28334c678293528d00e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680515"
---
# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>Esikatselutoiminto: Azure Cosmos DB SQL API Data Providerin vaatimukset

Tässä ohjeartikkelissa kuvataan Azure Cosmos DB for SQL API Data Providerin vaatimukset. Lisäksi artikkelissa annetaan sen määritysohjeet ja kuvataan parhaita käytäntöjä Azure Cosmos DB for SQL API Data Providerin käytölle virtuaalientiteettien kanssa. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Mikä Azure Cosmos DB on?

Azure Cosmos DB on Microsoftin maailmanlaajuisesti hajautettu monimallinen tietokantapalvelu toiminnan kannalta elintärkeille sovelluksille. Se tarjoaa monipuoliset ja tutut SQL-kyselytoiminnot ja johdonmukaisesti pienet viipeet rakenteettomien JSON-tietojen käytölle. Lisätiedot: [Azure Cosmos DB:n esittely: SQL-ohjelmointirajapinta](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction)

## <a name="requirements"></a>Vaatimukset

- Tarvitset Azure-tilauksen, johon sisältyy Azure Cosmos DB.
- Tarvitset Azure Cosmos DB SQL -ohjelmointirajapintakokoelman.
- Azure Cosmos DB -tietokannan täytyy olla SQL-tietokanta. 

## <a name="data-type-mapping"></a>Tietotyyppien yhdistäminen

Oletetaan, että sinulla on Azure Cosmos DB -tiedosto kokoelmassa nimeltä *Orders*, jolla on seuraava JSON-rakenne.

![Kuvassa on esimerkki SQL-ohjelmointirajapintatiedoston JSON-rakenteesta.](media/documentdbexample.png)

Tästä taulukosta näet SQL-ohjelmointirajapintatiedoston tietotyyppien yhdistämismääritykset Common Data Service for Appsin *Orders*-kokoelmassa.

|SQL-ohjelmointirajapintatiedot|CDS for Apps|
|--|--|
|`id`|Perusavain|
|`name`|Yksi tekstirivi|
|`quantity`|Kokonaisluku|
|`orderid`|Yksi tekstirivi|
|`ordertype`|Asetusjoukko|
|`amount`|Desimaaliluku tai valuutta|
|`delivered`|Kaksi vaihtoehtoa|
|`datetimeoffset`|Päivämäärä ja aika|

> [!NOTE]
> - SQL-ohjelmointirajapinta luo määritteet, joissa on alaviivaetuliite (_).
> - Määritteet, jotka on määritetty vapaaehtoisiksi SQL-ohjelmointirajapintatiedostossa ja jotka on yhdistetty CDS for Appsissa **Pakollinen**-asetuksella, aiheuttavat virheen suorituksen yhteydessä.
> - Id attribute -arvojen täytyy olla GUID-tunnuksia.
> - Jos haluat lisätietoja päivämäärien käytöstä SQL-ohjelmointirajapinnassa, tutustu ohjeartikkeliin [Päivämäärien käyttö Azure Cosmos DB:ssä](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/).

## <a name="supported-sql-query-filtering"></a>Tuettu SQL-kyselysuodatus

SQL-kyselysuodatus tukee seuraavia operaattoreita: 

- Vertailuoperaattorit: `<`, `>`, `<=`, `>=` ja `!=`
- Loogiset operaattorit: `and` ja `or` 
- Joukko-operaattorit: `in` ja `not in`
- Merkkijono-operaattori: `like`, `contains`, b`egins with` ja `ends with`.

> [!NOTE]
> Like-operaattorin käyttö vastaa seuraavien operaattoreiden käyttöä: `contains`/`begins with`/`ends with`. SQL-ohjelmointirajapinta ei tue malliargumentteja, jotka kuvataan ohjeartikkelissa [Like (Transact-SQL)](/sql/t-sql/language-elements/like-transact-sql). Azure Cosmos DB for SQL API Data Provider voi kääntää yhden erikoistapauksen `Like('[aA]%')` muotoon `BeginsWith('a')` tai `BeginsWith('A')`. Muista, että SQL-ohjelmointirajapinnassa merkkijonojen vertailussa huomioidaan kirjainkoko.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>Tietolähteen lisääminen Azure Cosmos DB for SQL API Data Providerilla

1. Siirry [AppSourceen](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview), valitse **HANKI SE NYT** ja lisää sovellus ympäristöösi versiolla 9x tai tätä uudemmalla versiolla toimimalla ohjeiden mukaisesti.
2. Kun ratkaisu on asennettu, kirjaudu ympäristöön ja valitse **Asetukset** > **Hallinta** > **Virtuaalisen entiteetin tietolähteet**.
3. Valitse Toiminnot-työkaluriviltä **UUSI**. Valitse sitten **Valitse tietojen tarjoaja** -valintaikkunassa **Azure Cosmos DB for SQL API Data Provider** ja valitse sitten **OK**.
![Valitse Azure Cosmos DB for SQL API Data Provider.](media/createdatasource.png)
1. Anna seuraavat tiedot. Valitse sitten **TALLENNA JA SULJE**.

    |Kenttä|Kuvaus|
    |--|--|
    |**Nimi**|Anna tietolähteelle kuvaava nimi.|
    |**Kokoelman nimi**|Anna tähän sen Azure Cosmos DB -tietokantakokoelman tunnus, joka sisältää tiedot, jotka haluat näyttää virtuaalientiteetissä.  |
    |**Valtuutusavain**|Tämä on Azure Cosmos DB -tilin perusavain tai toissijainen avain. Voit tarkistaa avaimen Azure-hallintaportaalin **Avaimet**-asetuksesta Azure Cosmos DB -tilisi alta.|
    |**Uri**|Tämä on sen resurssiryhmän URI-osoite, jossa Azure Cosmos DB -kokoelma sijaitsee. URI-osoite on muotoilultaan seuraavankaltainen: `https://contoso/documents.azure.com:443`. Voit tarkistaa URI-osoitteen Azure-hallintaportaalin **Avaimet**-asetuksesta Azure Cosmos DB -tilisi alta. |
    |**Aikakatkaisu sekunteina**|Anna Azure Cosmos DB -palvelun vastauksen odotukseen käytettävä aika sekunteina (tämän ajan jälkeen tietopyyntö aikakatkaistaan). Jos annat arvoksi esimerkiksi 30, odotusaika ennen aikakatkaisua on enintään 30 sekuntia. Oletusaikakatkaisuarvo on 120 sekuntia.|

    ![Luo tietolähde SQL API Data Providerilla.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>Parhaat käytännöt ja rajoitukset

- Ota huomioon seuraavat seikat, kun käytät Azure Cosmos DB:tä tietolähteenä:
   - Kunkin Azure Cosmos DB -tietolähteen voi yhdistää vain yhteen virtuaalientiteettiin.
   - Voit yhdistää useita tietolähteitä samaan kokoelmaan Azure Cosmos DB:ssä.
- Et voi segmentoida kokoelman tietoja entiteetin perusteella.
- Azure Cosmos DB -tietokannat eivät edellytä rakennetta, mutta Azure Cosmos DB:n tiedot täytyy kuitenkin jäsentää ennustettavan mallin avulla. 
- Vaikka Azure Cosmos DB for SQL API Data Provider toteuttaa kyselyiden kääntämisen projektio-, suodatus- ja lajitteluoperaattoreille, se ei tue liitostoimintoja.
- Voit suodattaa vain yhden sarakkeen perusteella SQL-ohjelmointirajapinnan avulla.

## <a name="see-also"></a>Katso myös

[Ulkoisen tietolähteen tietoja sisältävien virtuaalientiteettien luominen ja muokkaaminen](create-edit-virtual-entities.md)
