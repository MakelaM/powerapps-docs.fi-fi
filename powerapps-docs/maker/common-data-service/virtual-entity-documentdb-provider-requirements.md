---
title: 'Esikatselutoiminto: Azure Cosmos DB for SQL API -tietojen tarjoajan käyttäminen Common Data Service -ratkaisun avulla | MicrosoftDocs'
description: Tietoja Azure Cosmos DB for SQL API -tietojen tarjoajan määrittämisestä virtuaalientiteettien kanssa käyttöä varten.
keywords: SQL API
ms.date: 06/27/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: d0031ffc-8754-4a12-b8c1-e08edc49ff73
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="preview-feature-azure-cosmos-db-sql-api-data-provider-requirements"></a>Esikatselutoiminto: Azure Cosmos DB SQL API -tietojen tarjoajan vaatimukset

Tässä ohjeaiheessa kerrotaan Azure Cosmos DB for SQL API -tietojen tarjoajan vaatimukset sekä Azure Cosmos DB for SQL API -tietojen tarjoajan ja virtuaalisten entiteettien määrittäminen sekä käyttämisen suositellut parhaat käytännöt.. 

> [!IMPORTANT]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-expect-changes.md)]
> - [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-no-ms-support.md)]


## <a name="what-is-azure-cosmos-db"></a>Mikä on Azure Cosmos DB?

Azure Cosmos DB on Microsoftin maailmanlaajuisesti käytössä oleva usean mallin tietokannan palvelu keskeisiä sovelluksia varten. Se sisältää monipuolisia ja tuttuja SQL-kyselyominaisuudet ja yhdenmukaiset lyhyet viiveet rakenteettomille JSON-tiedoille. Lisätietoja: [Johdanto Azure Cosmos DB -tietokantaan: SQL-ohjelmointirajapinta](https://docs.microsoft.com/azure/cosmos-db/sql-api-introduction)

## <a name="requirements"></a>Vaatimukset

- Azure-tilaus sisältää Azure Cosmos DB -tietokannan.
- Azure Cosmos DB SQL API -kokoelma.
- Azure Cosmos DB -tietokannan tyypin on oltava SQL. 

## <a name="data-type-mapping"></a>Tietotyyppien yhdistämismääritys

Oletetaan, että sinulla on Azure Cosmos DB -asiakirja kokoelmassa, jonka nimi on *Tilaukset*. Kokoelmalla on seuraava JSON-rakenne.

![Esimerkki-JSON SQL API -asiakirjaa varten.](media/documentdbexample.png)

Seuraavassa taulukossa esitetään SQL API -asiakirjojen tietotyyppien yhdistämismääritykset *Tilaukset*-kokoelmassa Common Data Service sovelluksille -ratkaisun kanssa.

|SQL API -tiedot|CSD sovelluksille|
|--|--|
|`id`|Ensisijainen avain|
|`name`|Yksi tekstirivi|
|`quantity`|Kokonaisluku|
|`orderid`|Yksi tekstirivi|
|`ordertype`|Asetusjoukko|
|`amount`|Desimaaliluku tai valuutta|
|`delivered`|Kaksi asetusta|
|`datetimeoffset`|Päivämäärä ja aika|

> [!NOTE]
> - SQL API luo määritteet, joiden etuliite on alaviiva (_).
> - Määritteet, jotka määritetään valinnaisiksi SQL API -asiakirjassa ja jotka yhdistetään CDS sovelluksille -ratkaisuun **Yritys on pakollinen** -arvona, aiheuttavat suorituksenaikaisen virheen.
> - id-määritteen arvojen on oltava GUID-tunnuksia.
> - Lisätietoja päivämäärien käyttämisestä SQL API:ssa on kohdassa [Päivämäärien käsitteleminen Azure Cosmos DB -tietokannassa](https://azure.microsoft.com/blog/working-with-dates-in-azure-documentdb-4/).

## <a name="supported-sql-query-filtering"></a>Tuettu SQL-kyselyn suodattaminen

SQL-kyselyn suodattaminen tukee seuraavia operaattoreita. 

- Vertailuoperaattorit:`<`,`>`,`<=`, `>=`,`!=`
- Loogiset operaattorit: `and`, `or` 
- Set-operaattorit: `in`, `not in`
- String-operaattorit: `like`, `contains`, b`egins with`, `ends with`

> [!NOTE]
> Like-operaattorin käyttö käännetään operaattoreita `contains`/`begins with`/`ends with` vastaavaksi. SQL API ei tue malliargumentteja, kuten aiheessa [Like (Transact SQL)](/sql/t-sql/language-elements/like-transact-sql) kerrotaan. Azure Cosmos DB for SQL API -tietojen tarjoaja voi kääntää yhden eritystapauksen `Like('[aA]%')` kohteeksi `BeginsWith('a')` TAI kohteeksi `BeginsWith('A')`. Huomaa, että kirjainkoolla on merkitystä SQL API :n merkkijonovertailussa.

## <a name="add-a-data-source-using-the-azure-cosmos-db-for-sql-api-data-provider"></a>Tietolähteen lisääminen Azure Cosmos DB for SQL API -tietojen tarjoajan avulla

1. Siirry [AppSourceen](https://appsource.microsoft.com/product/dynamics-365/mscrm.documentdb_data_provider?tab=Overview) ja valitse **LATAA SE NYT**. Seuraa ohjeita ja lisää sovellus ympäristöösi 9x-version avulla tai uudempaan ilmentymään.
2. Kun ratkaisu on asennettu, kirjaudu sisään ympäristöön ja siirry kohtaan **Asetukset** > **Hallinta** > **Virtuaalisen entiteetin tietolähteet**.
3. Valitse Toiminnot-työkaluriviltä **UUSI**. Valitse **Valitse tietojen tarjoaja** -valintaikkunassa **Azure Cosmos DB for SQL API -tietojen tarjoaja** ja valitse sitten **OK**.
![Valitse Azure Cosmos DB for SQL API -tietojen tarjoaja.](media/createdatasource.png)
1. Syötä seuraavat tiedot ja valitse sitten **TALLENNA JA SULJE**.

    |Kenttä|Kuvaus|
    |--|--|
    |**Nimi**|Kirjoita tietolähteen kuvaava nimi.|
    |**Kokoelman nimi**|Sen virtuaalientiteetin sisältävän Azure Cosmos DB -tietokantakokoelman tunnus, jonka tiedot haluat esittää.  |
    |**Valtuutusavain**|Azure Cosmos DB -tilin ensisijainen tai toissijainen avain. Voit etsiä avaimen Azure-hallintaportaalin Azure Cosmos DB -tilin **Avaimet**-asetuksesta.|
    |**URI**|Sen resurssiryhmän URI, jossa Azure Cosmos DB -kokoelma sijaitsee. URI-osoite on muodostettu samalla tavalla kuin `https://contoso/documents.azure.com:443`. Voit etsiä URI:n Azure-hallintaportaalin Azure Cosmos DB -tilin **Avaimet**-asetuksesta. |
    |**Aikakatkaisu sekunteina**|Anna Azure Cosmos DB -palvelun vastauksen odotusaika sekunteina. Tämän jälkeen tietopyyntö aikakatkaistaan. Voit esimerkiksi antaa arvoksi 30, jolloin odotusaika on enintään 30 sekuntia ennen aikakatkaisua. Oletusaikakatkaisu on 120 sekuntia.|

    > [!div class="mx-imgBorder"] 
    > ![Luo tietolähde SQL API -tietojen tarjoajan avulla.](media/cosmosdb-datasource.png)

## <a name="best-practices-and-limitations"></a>Parhaat käytännöt ja rajoitukset

- Ota seuraavat asiat huomioon, kun käytät Azure Cosmos DB -tietokantaa tietolähteenä:
   - Kukin Azure Cosmos DB -tietolähde voidaan liittää vain yhteen virtuaalientiteettiin.
   - Voit yhdistää useita tietolähteitä samaan kokoelmaan Azure Cosmos DB -tietokannassa.
- Et voi segmentoida tietoja kokoelmassa entiteetin mukaan.
- Azure Cosmos DB -tietokannat eivät edellytä rakennetta, mutta Azure Cosmos DB -tietokannan tietojen rakenne on määritettävä ennustettavan rakenteen avulla. 
- Vaikka Azure Cosmos DB for SQL API -tietojen tarjoaja ottaa käyttöön ennuste-, suodatus- ja lajitteluoperaattorien kyselyn käännöksen, se ei tue liitosoperaattoreita.
- Suodatuksen voi tehdä vain yhden sarakkeen perusteella SQL API:ssa.

## <a name="see-also"></a>Katso myös

[Virtuaalisten entiteettien, jotka sisältävät ulkoisen tietolähteen tietoja, luominen ja muokkaaminen](create-edit-virtual-entities.md)
