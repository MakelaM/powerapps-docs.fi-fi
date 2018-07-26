---
title: Mukautetun entiteetin luomisen pikaopas | Microsoft Docs
description: Tämän pikaoppaan avulla opit luomaan mukautetun entiteetin PowerAppsissa.
author: Mattp123
ms.service: powerapps
ms.component: cds
ms.topic: quickstart
ms.date: 05/01/2018
ms.author: matp
ms.openlocfilehash: a7fed26dafcf0b1d73ae6ba362964de5e9fd1ad5
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218713"
---
# <a name="quickstart-create-a-custom-entity"></a>Pikaopas: Mukautetun entiteetin luominen
PowerAppsissa *entiteetti* määrittää tiedot, joita haluat seurata sellaisten tietueiden muodossa, jotka yleensä sisältävät ominaisuuksia, kuten yrityksen nimi, sijainti, tuotteet, sähköposti ja puhelinnumero. Voit sitten näyttää tiedot kehittämällä sovelluksen, joka viittaa entiteettiin. PowerApps tarjoaa vakioentiteetit tyypillisiin organisaation skenaarioihin (kuten tapaamisten seuranta), mutta haluat ehkä myös luoda mukautettuja entiteettejä omalle organisaatiollesi ominaisten tietojen tallentamiseen.

Tämän pikaoppaan avulla opit luomaan mukautetun entiteetin nimeltä Tuotearvostelu, jonka avulla voit luoda sovelluksen, joka näyttää luokitukset ja kommentit yrityksesi myymille tuotteille.

## <a name="prerequisites"></a>Edellytykset
Tämän pikaoppaan noudattamista varten tarvitaan seuraavat kohteet:
* PowerAppsin palvelupaketin 2 tai Microsoft Flow -palvelupaketin 2 käyttöoikeus. Vaihtoehtoisesti voit rekisteröityä [ilmaisen PowerAppsin palvelupaketin 2 kokeiluversion](https://web.powerapps.com/signup?redirect=marketing&email=) käyttäjäksi.
* Järjestelmänvalvoja- tai Järjestelmämukauttaja-käyttöoikeusrooli Common Data Servicessä sovelluksille.

## <a name="sign-in-to-powerapps"></a>PowerAppsiin kirjautuminen
Kirjaudu sisään PowerAppsiin osoitteessa [https://web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-an-entity"></a>Entiteetin luominen
1. Laajenna siirtymisruudussa **Tiedot** napsauttamalla tai napauttamalla sitä ja valitse sitten **Entiteetit**.

    ![Luettelo entiteeteistä ja niiden tiedot](./media/data-platform-cds-create-entity/entitylist.png "Entiteettiluettelo")

2. Valitse komentopalkissa **Uusi entiteetti**.

    Ennen kuin luot entiteetin, tutustu [entiteettiviitteeseen](../../developer/common-data-service/reference/about-entity-reference.md), jossa on kuvailtu käytettävissä olevat vakioentiteetit. Nämä entiteetit kattavat kaikki tyypilliset skenaariot. Jos jokin näistä entiteeteistä vastaa tarpeitasi sellaisenaan tai vähäisten muokkausten jälkeen, säästät aikaa käyttämällä kyseistä entiteettiä. 

3. Kirjoita **Uusi entiteetti** -paneelin **Näyttönimi**-ruudussa **Tuotearvostelu** ja lisää halutessasi kuvaus (kuvaukset ovat hyödyllisiä muille henkilöille, jotka mahdollisesti käyttävät entiteettiä). Paneelin muut kentät täytetään automaattisesti, alla olevan mukaisesti. Kun olet valmis, valitse **Seuraava**.

   * **Monikkomuotoinen näyttönimi** – Tämä kenttä täytetään automaattisesti, kun kirjoitat näyttönimen. Voit muuttaa nimen tarvittaessa. Monikkomuotoinen näyttönimi on entiteetin nimi Common Data Service WebAPIssa, jota käytetään käsitellessä entiteettiä PowerAppsissa ja Flow’ssa.
   * **Nimeä** – tämä kenttä täytetään myös automaattisesti, kun kirjoitat näyttönimen. Etuliite määritettiin luotaessa ympäristöä. Sitä käytetään varmistamaan, että luomasi entiteetit voidaan viedä ja tuoda muihin ympäristöihin ilman yhteensopimattomuutta muiden entiteettien nimien kanssa. Voit muuttaa etuliitteen päivittämällä etuliitteen Publisherissa Common Data Servicen oletusratkaisulle. Jos muutat entiteetin nimeä tallentamisen jälkeen, nykyiset sovellukset voivat lakata toimimasta.
     
     ![Uusi entiteetti](./media/data-platform-cds-create-entity/newentitypanel.png "Uusi entiteetti -paneeli")

4. Avaa **Ensisijainen nimi** -paneeli napauttamalla tai napsauttamalla entiteetin tietosivulla **Ensisijainen nimi** -kenttää ja korvaa sitten **Näyttönimi**-ruudussa näkyvä **Ensisijainen nimi** nimellä **Tuotearvostelu**. Korvaa **Nimi**-ruudussa **PrimaryName** nimellä **ProductReview** ja valitse sitten **Valmis**.
 
    Jokainen entiteetti sisältää oletusarvoisesti Ensisijainen nimi -kentän, jota hakukentät käyttävät muodostettaessa suhteita muihin entiteetteihin. Ensisijainen nimi -kenttää käytetään yleensä entiteettiin tallennettujen tietojen nimen tai ensisijaisen kuvauksen tallentamiseen. Ensisijainen nimi -kentän nimi ja näyttönimi voidaan päivittää ennen entiteetin ensimmäistä tallennuskertaa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/newentitydetails.png "Uuden entiteetin tiedot")

5. Jos haluat lisätä kentän entiteettiin, toimi seuraavasti:
 
    a. Avaa **Kentän ominaisuudet** -paneeli valitsemalla komentopalkissa **Lisää kenttä**.

    b. Kirjoita **Näyttönimi** -ruutuun **Arvostelun päivämäärä**.

    c. Valitse avattavasta **Tietotyyppi**-luettelosta **Vain päivämäärä**.

    d. Valitse **Pakollinen**-valintaruudun valinta.
    
    e. Valitse **Valmis**.
     
    Lisätietoja on artikkelissa [Entiteetin kenttien hallinta](data-platform-manage-fields.md).

    ![Uusi kenttä](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Uusi kenttäpaneeli")

6. Lisää kolme kenttää seuraavilla määrityksillä toistamalla edelliset vaiheet:
   * **Näyttönimi** = Tuotteen luokitus; **Tietotyyppi** = Kokonaisluku; Valitse **Pakollinen**-valintaruudun valinta
   * **Näyttönimi** = Arvostelijan nimi; **Tietotyyppi** = Teksti
   * **Näyttönimi** = Arvostelijan kommentti; **Tietotyyppi** = Teksti

     Kun olet valmis, sinulla pitäisi olla viisi kenttää entiteetin tietosivulla.

     ![Kenttäluettelo](./media/data-platform-cds-create-entity/addedfields.png "Luettelo kentistä")

     Huomaa, että kaikilla entiteeteillä on vain luku -järjestelmäkenttiä. Oletusarvoisesti järjestelmäkenttiä ei näytetä kenttäluettelossa, vaikka ne ovat olemassa entiteetissä. Jos haluat nähdä kaikki kentät, voit muuttaa suodatinta komentopalkissa asetuksesta **Oletus** asetukseksi **Kaikki**. Lisätietoja entiteettiin liittyvistä metatiedoista on artikkelissa [Entiteettien metatiedot](../../developer/common-data-service/entity-metadata.md).

7. Tallenna entiteetti valitsemalla **Tallenna entiteetti** ja anna se käyttöön sovelluksiin.

    Tuotearvostelu-entiteetin pitäisi näkyä tietokannan entiteettiluettelossa. Jos et näe sitä, voit muuttaa suodatinta komentopalkissa asetuksesta **Oletus** asetukseksi **Kaikki**.

    ![Suodatin](./media/data-platform-cds-create-entity/filter.png "Suodattimen valinta")

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän pikaoppaan avulla olet oppinut luomaan mukautetun entiteetin nimeltä Tuotearvostelu, jonka avulla voit luoda sovelluksen, joka näyttää luokitukset ja kommentit jokaiselle valitun yrityksen myymälle tuotteelle. Seuraavaksi opit määrittämään entiteettien välisiä suhteita (tässä tapauksessa Tuote-vakioentiteetin ja mukautetun Tuotearvostelu-entiteetin välillä), jotta voit yhdistää eri tuotteet niiden arvosteluihin ja kommentteihin.

> [!div class="nextstepaction"]
> [Luo suhde](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>Tietosuojailmoitus
Microsoft PowerAppsin yleisen tietomallin avulla Microsoft kerää ja tallentaa mukautettuja entiteettien ja kenttien nimiä diagnostiikkajärjestelmiimme. Näiden tietojen avulla parannamme asiakkaille tarjottavaa yleistä tietomallia. Sovellustekijöiden antamat entiteettien ja kenttien nimet auttavat meitä ymmärtämään Microsoft PowerApps -yhteisössä yleisiä skenaarioita ja havaitsemaan palvelun vakioentiteettitarjonnan puutteita, kuten organisaatioihin liittyviä rakenteita. Microsoft ei käytä näihin entiteetteihin liittyvissä tietokantataulukoissa olevia tietoja, eikä jäljennä niitä tietokannan käyttöoikeusalueen ulkopuolelle. Huomaa kuitenkin, että mukautetut entiteettien nimet ja kentät voidaan replikoida monelle alueelle ja poistetaan tietojen säilytyskäytäntöjemme mukaisesti. Microsoft on sitoutunut takaamaan käyttäjien tietosuojan [luottamuskeskuksessamme](https://www.microsoft.com/trustcenter/Privacy/default.aspx) kuvaillulla tavalla.
