---
title: Mukautetun entiteetin luominen | Microsoft Docs
description: Tietoja mukautetun entiteetin luomisesta PowerAppsissa.
author: Mattp123
ms.service: powerapps
ms.component: cds
ms.topic: quickstart
ms.date: 05/01/2018
ms.author: matp
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-custom-entity"></a>Mukautetun entiteetin luominen
PowerAppsissa *entiteetti* määrittää tiedot, joita tietueiden lomakkeessa seurataan. Ne ovat yleensä ominaisuuksia, kuten yrityksen nimi, sijainti, tuotteet, sähköposti ja puhelin. Tämän jälkeen tiedot voi tuoda esille entiteettiin viittaavan kehitettävän sovelluksen avulla. PowerApps sisältää valmiita vakioentiteettejä, jotka kattavat organisaation tavalliset skenaariot (kuten tapaamisten seurannan). Usein on kuitenkin luotava mukautettuja entiteettejä, joihin tallennetaan organisaatiokohtaisia tietoja.

Tässä ohjeaiheessa on tietoja Tuotearvio-nimisen mukautetun entiteetin luomisesta. Entiteetin avulla luodaan sovellus, joka näyttää yrityksen myymien tuotteiden luokittelut ja kommentit.

## <a name="prerequisites"></a>Edellytykset
Voidaksesi noudattaa tätä menettelyä, tarvitset järjestelmänvalvojan tai järjestelmän mukauttajan oikeudet Common Data Servicessä.

## <a name="sign-in-to-powerapps"></a>Kirjaudu sisään PowerApps -sovellukseen
Kirjaudu sisään PowerApps -sovellukseen osoitteessa [https://web.powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).

## <a name="create-an-entity"></a>Entiteetin luominen
1. Napsauta tai napauta siirtymisruudussa **Tiedot**-kohtaa, jolloin se laajenee. Napsauta tai napauta sitten **Entiteetit**-kohtaa.

    ![Entiteettiluettelo ja entiteettien tiedot](./media/data-platform-cds-create-entity/entitylist.png "Entiteettiluettelo")

2. valitse komentopalkissa **Uusi entiteetti**.

    Tarkista ennen entiteetin luomista [entiteettiviittaus](../../developer/common-data-service/reference/about-entity-reference.md) ja käytettävissä olevien vakioentiteettien kuvaus. Nämä entiteetit kattavat tavalliset skenaariot. Jos jokin näistä entiteeteistä vastaa vaatimuksiasi sellaisenaan tai pienten muutosten jälkeen, voit aloittaa käyttämällä kyseistä entiteettiä. Näin säästät aikaa. 

3. Tee **Uusi entiteetti** -paneelissa seuraavat toimet:

    a. Anna **Näyttönimi**-ruutuun **Tuotearvio**.

    Huomaa, että seuraavat kentät täytetään automaattisesti, kun annat näyttönimen:

    * **Monikollinen näyttönimi** - Tämä ruutu täytetään automaattisesti, kun annat näyttönimen. Voit kuitenkin muuttaa arvoa halutessasi. Monikollinen näyttönimi on Common Data Service -sovelluksen WebAPI. Sitä käytetään, kun tämä entiteetti on käytössä PowerApps- tai Flow-sovelluksessa.
    * **Nimi** - Tämä ruutu täytetään myös automaattisesti, kun annat näyttönimen. Etuliite määritettiin, kun ympäristö luotiin. Se varmistaa, että luotuja entiteettejä voidaan viedä muihin ympäristöihin ja tuoda niistä ilman, että entiteettien nimet ovat ristiriidassa toistensa kanssa. Voit muuttaa tätä etuliitettä päivittämällä Common Data Service -oletusratkaisun julkaisijan etuliitteen. Et voi muuttaa nimeä entiteetin tallentamisen jälkeen. Näin vältetään olemassa olevien sovellusten toimintahäiriöt.

       > [!NOTE]
       > Jotta entiteetin nimi toimisi [Dynamics 365 for Customer Service upotetussa tietoartikkelihaussa](/dynamics365/customer-engagement/customer-service/set-up-knowledge-management-embedded-knowledge-search), entiteetin nimen enimmäispituus on 24 merkkiä, mihin sisältyy myös julkaisijan etuliite.

    b. Korvaa **Ensisijainen kenttä** -osan **Näyttönimi**-ruudussa **Nimi** termillä **Tuotteen tarkistus**. 

    Jokainen entiteetti sisältää oletusarvoisesti **Ensisijainen kenttä** -arvon. Hakukentät käyttävät sitä, kun entiteettien välisiä suhteita luodaan. Yleensä ensisijaisen kenttään tallennetaan entiteettiin tallennettujen tietojen nimi tai ensisijainen kuvaus. Voit päivittää ensisijaisen kentän nimen ja näyttönimen ennen entiteetin ensimmäistä tallennuskertaa.

    Huomaa myös, että ensisijaisella kentällä on myös oma **Nimi**-ruutu, joka toimii samalla tavalla kuin yllä kuvattu entiteetin nimi. Ensisijainen kentän nimi täytetään automaattisesti, kun näyttönimi syötetään, kun se käyttää samaa etuliitettä kuin entiteetti, eikä sitä voi muuttaa sen jälkeen, kun entiteetti on luotu.

    c. Avaa **Lisäasetukset**-osa ja laajenna **Kuvaus**-haitarivalikko. Voit halutessasi kirjoittaa kohteen kuvauksen, jos haluat (kuvaukset ovat hyödyllisiä, jos muut käyttäjät käyttävät tätä entiteettiä). 
    
    d. Kun olet valmis, valitse **Luo**.
     
    ![Uusi entiteetti](./media/data-platform-cds-create-entity/newentitypanel.png "Uusi entiteetti -paneeli")

4. Huomioi entiteetin tiedot -sivulla, että entiteettiä valmistellaan nyt taustalla. Kun valmistelu on valmis, entiteetti tallennetaan ja sitä voi käyttää sovelluksissa. Entiteettiin voi lisätä kenttiä, suhteita ja avaimia milloin tahansa (vaikka valmistelu on vielä kesken), mutta näkymiä, lomakkeita, kaavioita, koontinäyttöjä ja liiketoimintasääntöjä voidaan lisätä entiteetteihin vain, kun valmistelu on valmis.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/newentitydetails.png "Uuden entiteetin tiedot")

5. Noudata **Kentät**-välilehden edellisessä vaiheessa nimeämäsi **Ensisijaisen kentän** tietoja. Napsauttamalla tai napauttamalla **Ensisijainen kenttä** -kenttää voit avata **Ensisijaisen kenttä** -paneelin, jos haluat tehdä kenttään lisämukautuksia. Huomaa, että **Nimi**-kenttää ei voi enää muuttaa, koska entiteetti on jo tallennettu.

5. Voit lisätä entiteettiin kentän seuraavasti:
 
    a. Napsauta tai napauta komentopalkissa **Lisää kenttä** -kohtaa, jolloin **Kentän ominaisuudet** -paneeli avautuu.

    b. Anna **Näyttönimi**-ruutuun **arvion päivämäärä**.

    c. Valitse avattavasta **Tietotyyppi**-luettelosta **Vain päivämäärä**.

    d. Napsauta tai napauta **Pakollinen**-valintaruutua.
    
    e. Napsauta tai napauta **Valmis**-kohtaa.
     
    Lisätietoja on kohdassa [Entiteetin kenttien hallinta](data-platform-manage-fields.md).

    > [!div class="mx-imgBorder"] 
    > ![Uusi kenttä](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Uusi kenttä -paneeli")

6. Toista edellinen vaihe ja lisää kolme kenttää, joiden määritykset ovat seuraavat:
    * **Näyttönimi** = Tuoteluokitus; **Tietotyyppi** = Kokonaisluku; napsauta tai napauta **Pakollinen**-valintaruutua
    * **Näyttönimi** = Tarkistajan nimi; **Tietotyyppi** = Teksti
    * **Näyttönimi** = Tarkistajan kommentti; **Tietotyyppi** = Teksti

    Kun olet valmis, entiteetin tietojen sivun luettelossa tulisi olla viisi kenttää.

    ![Kenttäluettelo](./media/data-platform-cds-create-entity/addedfields.png "Kenttien luettelo")

    Huomaa, että kaikki entiteetit ovat vain luku -järjestelmäkenttiä. Oletusarvon mukaan järjestelmäkentät eivät näy kenttäluettelossa, vaikka ne näkyvät entiteetissä. Voit tarkastella kaikkia kenttiä, jos muutat komentopalkissa suodattimen **Oletus**-arvon **Kaikki**-arvoksi. Lisätietoja entiteetin liittyvistä metatiedoista on kohdassa [Entiteetin metatiedot](../../developer/common-data-service/entity-metadata.md).

7. Tallenna entiteettiin tehdyt uusimmat muutokset valitsemalla **Tallenna entiteetti**.

    Tuotearvio-entiteetin tulisi näkyä tietokannan entiteettiluettelossa. Jos et näe sitä, muuta komentopalkissa suodattimen **Oletus**-arvo **Mukautettu**-arvoksi.

    > [!div class="mx-imgBorder"] 
    > ![Suodatin](./media/data-platform-cds-create-entity/filter.png "suodattimen valinta")

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä ohjeaiheessa on tietoja Tuotearvio-nimisen mukautetun entiteetin luomisesta. Entiteetin avulla luodaan sovellus, joka näyttää tietyn yrityksen jokaisen myydyn tuotteen luokittelut ja kommentit. Seuraavaksi opitaan, miten entiteettien väliset suhteet määritetään (tässä tapauksessa Tuote-vakioentiteetin ja mukautetun Tuotearvio-entiteetin suhde), jotta voit liittää kunkin tuotteen oikeisiin arvioihin ja kommentteihin.

> [!div class="nextstepaction"]
> [Suhteen luominen](data-platform-entity-lookup.md)

## <a name="privacy-notice"></a>Tietosuojatiedot
Microsoft PowerApps Common Data Model -ratkaisun avulla Microsoft kerää ja tallentaa mukautettuja entiteettejä ja kenttänimiä diagnostiikkajärjestelmiin. Näiden tietojen avulla parannamme asiakkaiden käytössä olevaa Common Data Model -ratkaisua. Entiteettien ja kenttien nimet, joita tekijät luovat, auttavat meitä ymmärtämään Microsoft PowerApps -yhteisön yleisiä skenaarioita ja saamaan selville palvelun entiteetin vakiokattavuuden puutteita, kuten organisaation liittyvissä malleissa. Microsoft ei käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja eikä replikoi niitä sen alueen ulkopuolelle, jossa tietokanta on valmisteltu. Huomaa kuitenkin, että mukautetun entiteetin ja kenttien nimet voidaan replikoida alueilla. Ne poistetaan tietojen säilytyskäytäntöjen mukaisesti. Microsoft pyrkii takaamaan tietoturvasi [valvontakeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) esitetyllä tavalla.
