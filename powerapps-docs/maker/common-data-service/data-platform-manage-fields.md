---
title: Entiteetin mukautettujen kenttien hallinta | Microsoft Docs
description: 'Common Data Service (CDS) sovelluksille -ratkaisun entiteetin mukautettujen kenttien luomisen, lukemisen, päivittämisen ja poistamisen ohjeet.'
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="manage-custom-fields-in-an-entity"></a>Entiteetin mukautettujen kenttien hallinta
Voit luoda ja päivittää yhden mukautetun kentän tai useita mukautettuja kenttiä entiteetissä. Kun luot mukautetun kentän, määrität ominaisuusjoukon, kuten kentän nimen, sen näyttönimen ja kentän tietojen tyypin. Lisätietoja on kohdassa [Entiteettimääritteen metatiedot](../../developer/common-data-service/entity-attribute-metadata.md).

> [!NOTE]
> Jokaisessa entiteetissä on järjestelmäkenttiä, kuten kenttiä, jotka osoittavat tietueen edellisen päivitysajankohdan ja edellisen päivittäjän. Lisäksi vakioentiteeteillä on vakiokenttiä (oletuskenttiä). Järjestelmäkenttiä tai vakiokenttiä ei voi muokata tai poistaa. Jos luot mukautetun kentän, sen tulisi sisältää toimintoja näiden vakiokenttien lisäksi.

## <a name="create-a-field"></a>Kentän luominen
1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Entiteetit**-kohtaa vasemmanpuoleisessa siirtymisruudussa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/entitylist.png "Entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaan entiteettiä tai [luo uusi entiteetti](data-platform-create-entity.md)

3. Lisää uusi kenttä entiteettiin valitsemalla **Lisää kenttä**.

4. Anna Uusi kenttä -paneelissa kentän **näyttönimi**. **Nimi** täytetään automaattisesti. Sitä käytetään kentän yksilöllisenä nimenä. **Näyttönimeä** käytetään, kun tämä kenttä esitellään käyttäjille. **Nimeä** käytetään sovelluksen luomisen yhteydessä lausekkeissa ja kaavoissa.

    > [!NOTE]
    > Sovelluksessa näkyviä **Näyttönimi**-kenttiä voidaan muuttaa milloin tahansa. **Nimi**-kenttää ei voi muuttaa entiteetin tallentamisen jälkeen, koska tämä saattaa johtaa sovelluksen toimintahäiriöön.

    > [!div class="mx-imgBorder"] 
    > ![Uusi kenttä](./media/data-platform-cds-create-entity/newfieldpanel.png "Uusi kenttä -paneeli")

5. Valitse kentän **tietotyyppi**. Se ohjaa tietojen tallennustapaa sekä näkyvyyttä sovelluksissa. Esimerkiksi teksti tallennetaan eri tavalla kuin desimaaliluku tai URL-osoite. Lisätietoja käytettävissä olevista tietotyypeistä on kohdassa [Entiteettimääritteen metatiedot](../../developer/common-data-service/entity-attribute-metadata.md).

    Määritä pyydettäessä kyseisen tietotyypin lisätiedot. Näkyvissä ovat eri kentät tietotyypin perusteella. Jos olet luomassa kenttää, jonka tyyppi on Asetusjoukko tai Monivalinta-asetusjoukko, voit valita **Uusi asetusjoukko** -kohdan ja luoda uuden asetusjoukon kentän luomisen yhteydessä. Lisätietoja on kohdassa [Asetusjoukon luominen](custom-picklists.md)

    > [!div class="mx-imgBorder"] 
    > ![Uusi kenttä](./media/data-platform-cds-create-entity/newfieldpanel-2.png "Uusi kenttä -paneeli")


7. Valitse **Pakollinen**-kohdan valintaruutu, jos haluat suositella tätä kenttää pakolliseksi sovelluksissa. Ei vahvaa täytäntöönpanoa Common Data Service -sovelluksen kaikkiin yhteyksiin. Jos haluat varmistaa, että kenttä on täytetty, luo [liiketoimintasääntö](data-platform-create-business-rule.md)

8. Valitse **Haettavissa**-kohdan valintaruutu, jos haluat, että tämä kenttä on käytettävissä näkymissä, kaavioissa, koontinäytöissä ja erikoishaussa. Useimmissa tapauksissa tämä valintaruutu valitaan.

9. Napsauta tai napauta **Valmis**-kohtaa, jos haluat sulkea Kenttä-paneelin ja palata entiteettiin. Voit toistaa vaiheet 3–9 jokaisen lisäkentän kohdalla.
   
    > [!IMPORTANT]
    > Kenttä tallennetaan ja luodaan vasta, kun entiteetin muutokset on tallennettu.

10. Napsauta tai napauta **Tallenna entiteetti**, jos haluat tehdä muutokset loppuun ja tallentaa ne Common Data Service -sovellukseen.

    Saat ilmoituksen, kun toiminto on valmis. Jos toiminto ei onnistu, virhesanoma sisältää virheet ja niiden korjausehdotukset.

## <a name="create-a-calculated-or-roll-up-field"></a>Laskennallisen kentän tai koontikentän luominen
Laskennalliset kentät mahdollistavat liiketoimintaprosessien manuaalisten laskutoimitusten automatisoinnin. Myyjä voi esimerkiksi haluta tietää mahdollisuuden painotetun tuoton, joka perustuu mahdollisuuden arvioituun tuottoon kerrottuna todennäköisyydellä. Tai he haluavat kohdistaa automaattisesti alennuksen, jos tilauksen arvo on suurempi kuin 500 €. Laskennallinen kenttä sisältää arvoja, jotka saadaan tuloksena yksinkertaisista laskutoimituksista tai ehdollisista operaattoreista, kuten esimerkiksi suurempi kuin- tai jos-muuten-rakenne. Laskennallisia kenttiä voi luoda seuraavien tietotyyppien avulla:

* Yksi tekstirivi
* Asetusjoukko
* Kaksi asetusta
* Kokonaisluku
* Desimaaliluku
* Valuutta
* Päivämäärä ja aika

Lisätietoja tuetuista lausekkeista ja esimerkeistä on kohdassa [Laskennallisten kenttien määrittäminen](/dynamics365/customer-engagement/customize/define-calculated-fields)

## <a name="update-or-delete-a-field"></a>Kentän päivittäminen tai poistaminen
1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Entiteetit**-kohtaa vasemmanpuoleisessa siirtymisruudussa. Napsauta tai napauta sitten entiteettiä.
2. Napsauta tai napauta entiteetin kenttäluettelossa kenttää ja noudata seuraavia ohjeita:
   
   * Muuta vähintään yksi kentän ominaisuus.
   * Poista kenttä napsauttamalla tai napauttamalla kentän oikeanpuoleisen reunan lähellä olevaa kolmea pistettä (...). Napsauta tai napauta sitten **Poista**-kohtaa.

3. Napsauta tai napauta **Tallenna entiteetti** -kohtaa, kun haluat lähettää muutokset.
   
    > [!IMPORTANT]
    > Muutokset menetetään, jos niitä ei tallenneta ennen toisen sivun avaamista selaimessa tai selaimen sulkemista.

    Saat ilmoituksen, kun toiminto on valmis. Jos toiminto ei onnistu, virhesanoma sisältää virheet ja niiden korjausehdotukset.

## <a name="best-practices-and-restrictions"></a>Parhaat käytännöt ja rajoitukset
Kun luot ja muokkaan kenttiä, pidä seuraavat seikat mielessä:

* Järjestelmäkenttiä tai niiden arvoja ei voi muokata tai poistaa.
* Et voi muokata tai poistaa vakioentiteetin vakiokenttää (oletuskenttää), lisätä tietoja vaativaa kenttää tai tehdä muutoksia, jotka voivat aiheuttaa toimintahäiriön entiteetistä riippuvaisesta sovelluksesta.
* Varmista, että mukautettuun entiteettiin tehdyt muutokset eivät aiheuta entiteetistä riippuvaiseen sovellukseen toimintahäiriöitä.
* Anna jokaiselle mukautetulle kentälle nimi, joka on yksilöllinen entiteetissä. Kenttää ei voi nimetä uudelleen luomisen jälkeen.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Entiteettien välisten suhteiden määrittäminen](data-platform-entity-lookup.md)
* [Liiketoimintasäännön luominen](data-platform-create-business-rule.md)
* [Sovelluksen luominen entiteettien avulla](../canvas-apps/data-platform-create-app.md)
* [Sovelluksen luominen alusta Common Data Service sovelluksille -tietokannan avulla](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Tietosuojatiedot
Microsoft PowerAppsin Common Data Model -ratkaisun avulla kerätään ja tallennetaan mukautettuja entiteettejä ja kenttänimiä diagnostiikkajärjestelmiin.  Näiden tietojen avulla parannamme asiakkaiden käytössä olevaa Common Data Model -ratkaisua. Entiteettien ja kenttien nimet, joita tekijät luovat, auttavat meitä ymmärtämään Microsoft PowerApps -yhteisön yleisiä skenaarioita ja saamaan selville palvelun entiteetin vakiokattavuuden puutteita, kuten organisaation liittyvissä malleissa. Microsoft ei käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja eikä replikoi niitä sen alueen ulkopuolelle, jossa tietokanta on valmisteltu. Huomaa kuitenkin, että mukautetun entiteetin ja kenttien nimet voidaan replikoida alueilla. Ne poistetaan tietojen säilytyskäytäntöjen mukaisesti. Microsoft pyrkii takaamaan tietoturvasi [valvontakeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) esitetyllä tavalla.

