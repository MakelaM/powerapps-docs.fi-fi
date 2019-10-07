---
title: SQL Server -yhteyden yleiskatsaus | Microsoft Docs
description: Vaiheittaiset ohjeet yhteyden muodostamiseen Azure SQL- tai paikalliseen SQL Server -tietokantaan
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 07/12/2016
ms.author: lanced
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ca79c60e90c330f21af6ed8a12b98c3667535bb8
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987412"
---
# <a name="connect-to-sql-server-from-powerapps"></a>SQL Server -yhteyden luominen PowerAppsista
![SQL-palvelimen kuvake](./media/connection-azure-sqldatabase/sqlicon.png)

Muodosta yhteys SQL Serveriin Azuressa tai paikallisessa tietokannassa, jotta voit näyttää siitä peräisin olevia tietoja PowerAppsissa.

## <a name="prerequisites"></a>Edellytykset

* [Rekisteröidy](../../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
* Kerää seuraavat tiedot tietokantaan, joka sisältää vähintään yhden taulukon, jossa on perusavain:
  
  * tietokannan nimi
  * sen palvelimen nimi, jossa tietokanta sijaitsee
  * kelvollinen käyttäjänimi ja salasana tietokantaan yhdistämistä varten
  * tietokantaan yhdistämiseen tarvittava todennustyyppi.
    
    Jos sinulla ei ole näitä tietoja, pyydä niitä haluamasi tietokannan järjestelmänvalvojalta.
* Jos käytät paikallista tietokantaa, tunnista [tietoyhdyskäytävä](../gateway-management.md), joka jaettiin kanssasi (tai luo sellainen).
  
    > [!NOTE]
  > Yhdyskäytäviä ja paikallisia yhteyksiä voi luoda ja käyttää vain käyttäjän [oletusympäristössä](../working-with-environments.md).

## <a name="generate-an-app-automatically"></a>Luo sovellus automaattisesti
1. Napsauta tai napauta PowerApps Studiossa **Tiedosto**-valikon (lähellä vasenta reunaa) kohtaa **Uusi**.
   
    ![Tiedosto-valikon Uusi-vaihtoehto](./media/connection-azure-sqldatabase/file-new.png)
2. Napsauta tai napauta **Aloita tiedoillasi** -kohdassa liitinrivin lopussa olevaa oikealle osoittavaa nuolta.
3. Jos sinulla on jo yhteys tietokantaan, jota haluat käyttää, napsauta tai napauta sitä ja hyppää tämän toimintosarjan vaiheeseen 7.
4. Napsauta tai napauta kohtaa **Uusi yhteys** ja napsauta tai napauta sitten kohtaa **SQL Server**.
   
    ![Lisää SQL Server -yhteys](./media/connection-azure-sqldatabase/add-sql-connection.png)
5. Suorita jompikumpi seuraavista vaiheista:
   
   * Määritä **Yhdistä suoraan (pilvipalvelut)** ja kirjoita tai liitä palvelimen nimi sekä haluamasi tietokannan nimi, käyttäjänimi ja salasana.
     
       ![Muodosta yhteys tietokantaan Azuressa](./media/connection-azure-sqldatabase/connect-azure.png)
   * Määritä **Yhdistä käyttämällä paikallista tietoyhdyskäytävää**, kirjoita tai liitä palvelimen nimi sekä haluamasi tietokannan nimi, käyttäjänimi ja salasana. Määritä lisäksi todennustyyppi ja yhdyskäytävä.
     
       ![Muodosta yhteys paikalliseen tietokantaan](./media/connection-azure-sqldatabase/connect-onprem.png)
     
       > [!NOTE]
     > Jos sinulla ei ole yhdyskäytävää, [asenna sellainen](../gateway-reference.md) ja napsauta tai napauta **Päivitä yhdyskäytäväluettelo**.
6. Napsauta tai napauta **Yhdistä**.
7. Napsauta tai napauta vaihtoehtoa kohdassa **Valitse tietojoukko**, napsauta tai napauta vaihtoehtoa kohdassa **Valitse taulukko** ja valitse sitten **Yhdistä**.
   
    PowerApps luo sovelluksen, joka näyttää tiedot kolmessa näytössä. Heuristiikka ehdottaa, millaisia tietoja näytetään, mutta sinun on ehkä mukautettava käyttöliittymää omia tarpeitasi vastaavaksi.
8. Mukauta sovellusta käyttämällä tekniikoita, jotka ovat samanlaisia kuin kohdassa [Sovelluksen luominen Excelistä](../get-started-create-from-data.md) kuvataan, alkaen sovelluksen asettelun muuttamisesta.

## <a name="build-an-app-from-scratch"></a>Luo sovellus alusta alkaen
1. Kirjaudu osoitteeseen [powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samalla tilillä, jota käytit PowerAppsiin rekisteröitymiseen.
2. Napsauta tai napauta vasemmassa siirtymispalkissa kohtaa **Yhteydet**:  
   
    ![Yhteyksien hallinta](./media/connection-azure-sqldatabase/manage-connections.png)
3. Napsauta tai napauta oikeassa yläkulmassa kohtaa **Uusi yhteys** ja napsauta tai napauta sitten kohtaa **SQL Server**.
4. Suorita jompikumpi seuraavista vaiheista:
   
   * Määritä **Yhdistä suoraan (pilvipalvelut)** ja kirjoita tai liitä palvelimen nimi sekä haluamasi tietokannan nimi, käyttäjänimi ja salasana.
     
       ![Muodosta yhteys tietokantaan Azuressa](./media/connection-azure-sqldatabase/connect-azure-portal.png)
   * Määritä **Yhdistä käyttämällä paikallista tietoyhdyskäytävää**, kirjoita tai liitä palvelimen nimi sekä haluamasi tietokannan nimi, käyttäjänimi ja salasana. Määritä lisäksi todennustyyppi ja yhdyskäytävä.
     
       ![Muodosta yhteys tietokantaan Azuressa](./media/connection-azure-sqldatabase/connect-onprem-portal.png)
     
       > [!NOTE]
     > Jos sinulla ei ole yhdyskäytävää, [asenna sellainen](../gateway-reference.md) ja päivitä luettelo napsauttamalla tai napauttamalla myötäpäivään-kuvaketta.
5. Luo yhteys napsauttamalla tai napauttamalla **Luo**.
6. Luo sovellus käyttämällä tekniikoita, jotka ovat samanlaisia kuin kohdassa [Luo sovellus alusta alkaen](../get-started-create-from-blank.md) on kuvattu.

## <a name="update-an-existing-app"></a>Päivitä olemassa oleva sovellus
1. Avaa PowerApps Studiossa sovellus, jonka haluat päivittää.
2. Napsauta tai napauta kohtaa **Tietolähteet** valintanauhan **Näkymä**-välilehdessä.
3. Napsauta tai napauta oikean ruudun kohtaa **Lisää tietolähde**.
   
    ![Tietolähteen lisääminen](./media/connection-azure-sqldatabase/add-data-source.png)
4. Napsauta tai napauta kohtaa **Uusi yhteys**, napsauta tai napauta kohtaa **SQL Server** ja napsauta tai napauta kohtaa **Yhdistä**.
5. Suorita jompikumpi seuraavista vaiheista:
   
   * Määritä **Yhdistä suoraan (pilvipalvelut)** ja kirjoita tai liitä palvelimen nimi sekä haluamasi tietokannan nimi, käyttäjänimi ja salasana.
     
       ![Muodosta yhteys tietokantaan Azuressa](./media/connection-azure-sqldatabase/connect-azure-fromblank.png)
   * Määritä **Yhdistä käyttämällä paikallista tietoyhdyskäytävää**, kirjoita tai liitä palvelimen nimi sekä haluamasi tietokannan nimi, käyttäjänimi ja salasana. Määritä lisäksi todennustyyppi ja yhdyskäytävä.
     
       ![Muodosta yhteys tietokantaan Azuressa](./media/connection-azure-sqldatabase/connect-onprem-fromblank.png)
     
       > [!NOTE]
     > Jos sinulla ei ole yhdyskäytävää, [asenna sellainen](../gateway-reference.md) ja päivitä luettelo napsauttamalla tai napauttamalla ympyräkuvaketta.
6. Napsauta tai napauta **Yhdistä**.
7. Napsauta tai napauta haluamaasi vaihtoehtoa kohdassa **Valitse tietojoukko**.
8. Valitse kohdasta **Valitse taulukko** yksi tai useampi valintaruutu ja napsauta tai napauta kohtaa **Yhdistä**.

## <a name="next-steps"></a>Seuraavat vaiheet
* Opi [näyttämään tietolähteen tietoja](../add-gallery.md).
* Opi [tarkastelemaan tietoja ja luomaan tai päivittämään tietueita](../add-form.md).
* Tutustu muuntyyppisiin [tietolähteisiin](../connections-list.md), joihin voit muodostaa yhteyden.  
* [Tutustu taulukoihin ja tietueisiin](../working-with-tables.md), joiden tietolähteet ovat taulukkomuotoisia.

<!--NotAvailableYet
## View the available functions ##
This connection includes the following functions:

| Function Name |  Description |
| --- | --- |
|[GetItems](connection-azure-sqldatabase.md#getitems) | Retrieves rows from a SQL table |
|[PostItem](connection-azure-sqldatabase.md#postitem) | Inserts a new row into a SQL table |
|[GetItem](connection-azure-sqldatabase.md#getitem) | Retrieves a single row from a SQL table |
|[DeleteItem](connection-azure-sqldatabase.md#deleteitem) | Deletes a row from a SQL table |
|[PatchItem](connection-azure-sqldatabase.md#patchitem) | Updates an existing row in a SQL table |
|[GetTables](connection-azure-sqldatabase.md#gettables) | Retrieves tables from a SQL database |

### GetItems
Get rows: Retrieves rows from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|$skip|integer|no|Number of entries to skip (default = 0)|
|$top|integer|no|Maximum number of entries to retrieve (default = 256)|
|$filter|string|no|An ODATA filter query to restrict the number of entries|
|$orderby|string|no|An ODATA orderBy query for specifying the order of entries|

### PostItem
Insert row: Inserts a new row into a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|item| |yes|Row to insert into the specified table in SQL|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|value|array|No | |


### GetItem
Get row: Retrieves a single row from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to retrieve|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|ItemInternalId|string|No | |


### DeleteItem
Delete row: Deletes a row from a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to delete|

#### Output properties
None.

### PatchItem
Update row: Updates an existing row in a SQL table

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|table|string|yes|Name of SQL table|
|id|string|yes|Unique identifier of the row to update|
|item| |yes|Row with updated values|

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|ItemInternalId|string|No | &nbsp; |


### GetTables
Get tables: Retrieves tables from a SQL database

#### Input properties
None.

#### Output properties

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|value|array|No | Can output the Name and DisplayName properties |

### ExecuteProcedure
Execute stored procedure: Executes a stored procedure in SQL

#### Input properties

| Name| Data Type|Required|Description|
| ---|---|---|---|
|procedure|string|yes|Procedure name|
|parameters| |yes|Input parameters|

#### Output properties
Result of the stored procedure execution.

| Property Name | Data Type | Required | Description |
|---|---|---|---|
|OutputParameters|object|No | Output parameter values |
|ReturnCode|integer|No | Return code of a procedure |
|ResultSets|object|No | Result sets|

-->
