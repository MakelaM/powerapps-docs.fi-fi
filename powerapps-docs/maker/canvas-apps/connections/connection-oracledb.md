---
title: Yhteyden muodostaminen Oracle Database -tietokantaan | Microsoft Docs
description: Opi muodostamaan yhteys Oracle Database -tietokantaan ja käyttämään sitä sovellusten luomiseen PowerAppsissa.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/14/2017
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: f431373b2c36a84b54a3241ad2d49af019c37419
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42858423"
---
# <a name="connect-to-an-oracle-database-from-powerapps"></a>Yhteyden muodostaminen PowerAppsista Oracle-tietokantaan
Luetteloi taulukoita ja luo, lue ja poista taulukon rivejä Oracle-tietokannassa sen jälkeen, kun olet luonut yhteyden ja luonut sovelluksen PowerAppsissa. Oracle Database -tietokantayhteys tukee suodatuksen, lajittelun ja muiden funktioiden täyttä delegointia mutta ei käynnistimiä tai tallennettuja toimintosarjoja.

## <a name="prerequisites"></a>Edellytykset
* Oracle 9 ja uudemmat
* Oracle-asiakasohjelmisto 8.1.7 ja uudemmat
* Paikallisen tietoyhdyskäytävän asennus
* Oraclen asiakas-SDK:n asennus

### <a name="install-an-on-premises-data-gateway"></a>Paikallisen tietoyhdyskäytävän asentaminen
Asenna yhdyskäytävä noudattamalla [tämän opetusohjelman](../gateway-management.md) vaiheita.

Paikallinen tietoyhdyskäytävä toimii siltana tarjoten nopean ja turvallisen tiedonsiirron paikallisten tietojen (eli tietojen, jotka eivät sijaitse pilvipalvelussa) ja Power BI-, Microsoft Flow-, Logic Apps- ja PowerApps-palveluiden välillä. Voit käyttää samaa yhdyskäytävää useiden palveluiden ja tietolähteiden kanssa. Lisätietoja on artikkelissa [Tutustu yhdyskäytäviin](../gateway-reference.md).

### <a name="install-oracle-client"></a>Oracle-asiakasohjelman asentaminen
Asenna [64-bit ODAC 12c Release 4 (12.1.0.2.4) for Windows x64](http://www.oracle.com/technetwork/database/windows/downloads/index-090165.html) samaan tietokoneeseen, johon paikallinen tietoyhdyskäytävä on asennettu. Jos et toimi näin ja yrität luoda tai käyttää yhteyttä, näkyviin tulee virhe, kuten tunnettujen ongelmien luettelossa kuvataan.

## <a name="create-an-app-from-a-table-in-an-oracle-database"></a>Sovelluksen luominen Oracle-tietokannan taulukosta
1. Napsauta tai napauta PowerApps Studion **Tiedosto-valikon** (lähellä vasenta reunaa) kohtaa **Uusi**.
   
   ![Uusi asetus](./media/connection-oracledb/new-app.png)
2. Napsauta tai napauta kohdan **Aloita tiedoillasi** nuolta.
   
      Näkyviin tulee luettelo yhteyksistä, jotka sinulla jo on.
3. Napsauta tai napauta **Uusi yhteys**.
   
   ![Uusi yhteys](./media/connection-oracledb/new-connection.png)
4. Napsauta tai napauta yhteysluettelossa **Oracle-tietokanta**.
   
   ![Uusi tietokanta](./media/connection-oracledb/oracle-db.png)
5. Määritä Oracle-palvelimen nimi, käyttäjänimi ja salasana.
   
    Määritä palvelin tässä muodossa, jos SID vaaditaan:<br>
    *ServerName*/*SID*
   
   ![Yhteysparametrit](./media/connection-oracledb/connection-params.png)
6. Napsauta tai napauta yhdyskäytävää, jota haluat käyttää, tai asenna se.
   
    Jos yhdyskäytäväsi ei tule näkyviin asentamisen jälkeen, valitse **Päivitä yhdyskäytäväluettelo**.
   
   ![Uusi yhdyskäytävä](./media/connection-oracledb/choose-gateway.png)
7. Luo yhteys napsauttamalla tai napauttamalla **Luo**.
   
   ![Uusi](./media/connection-oracledb/create-button.png)
8. Napsauta tai napauta tietojoukkoa **oletus**.
   
   ![Uusi](./media/connection-oracledb/choose-dataset.png)
9. Napsauta tai napauta taulukkoluettelossa taulukkoa, jota haluat käyttää.
   
   ![Uusi](./media/connection-oracledb/choose-table.png)
10. Luo sovellus valitsemalla **Yhdistä**.
    
    ![Uusi](./media/connection-oracledb/connect-button.png)

PowerApps luo sovelluksen, jossa on kolme näyttöä ja jossa näytetään valitun taulukon tiedot:

* **BrowseScreen1**, jossa luetellaan kaikki taulukon merkinnät.
* **DetailScreen1**, joka antaa lisätietoja yksittäisestä merkinnästä.
* **EditScreen1**, jossa käyttäjät voivat päivittää tai luoda merkinnän.

![Uusi](./media/connection-oracledb/afd-app.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* Tallenna juuri luomasi sovellus painamalla Ctrl+S.
* Jos haluat mukauttaa **BrowseScreen1**-näyttöä (joka näytetään oletuksena), katso [Asettelun mukauttaminen](../customize-layout-sharepoint.md).
* Jos haluat mukauttaa **DetailsScreen1**- tai **EditScreen1**-näyttöjä, katso [Lomakkeen mukauttaminen](../customize-forms-sharepoint.md).

## <a name="known-issues-tips-and-troubleshooting"></a>Tunnetut ongelmat, vihjeet ja vianmääritys
1. Yhdyskäytävään ei saada yhteyttä.
   
    Tämä virhesanoma tulee näyttöön, jos paikallinen tietoyhdyskäytävä ei voi muodostaa yhteyttä pilvipalveluun. Tarkista yhdyskäytäväsi tila kirjautumalla sisään osoitteessa powerapps.microsoft.com, napsauttamalla tai napauttamalla **Yhdyskäytävät** ja napsauttamalla tai napauttamalla yhdyskäytävää, jota haluat käyttää.
   
    Varmista, että yhdyskäytäväsi on käynnissä ja että se voi muodostaa yhteyden Internetiin. Vältä yhdyskäytävän asentamista tietokoneeseen, joka saatetaan sammuttaa tai kytkeä lepotilaan. Yritä myös käynnistää paikallinen tietoyhdyskäytäväpalvelu (PBIEgwService) uudelleen.
2. System.Data.OracleClient vaatii Oracle-asiakasohjelmiston version 8.1.7 tai uudemman.
   
    Tämä virhesanoma tulee näkyviin, jos Oraclen asiakas-SDK:ta ei ole asennettu paikallisen tietoyhdyskäytävän kanssa samaan tietokoneeseen. Ratkaise ongelma [asentamalla virallinen palvelu](https://go.microsoft.com/fwlink/p/?LinkID=272376).
3. Taulukko [Tablename] ei määritä avainsarakkeita.
   
    Tämä virhesanoma tulee näkyviin, jos yrität yhdistää taulukkoon, jossa ei ole Oracle Database -tietokantayhteyden edellyttämää perusavainta.
4. Kirjoittamishetkellä tallennettuja toimintosarjoja, yhdistelmäavaimia sisältäviä taulukoita ja sisäkkäisiä objektityyppejä sisältäviä taulukoita ei tueta.

