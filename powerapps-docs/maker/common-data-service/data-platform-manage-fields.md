---
title: Mukautettujen kenttien hallinta entiteetin pika-aloituksessa | Microsoft Docs
description: Luo, lue, päivitä ja poista entiteetin mukautettuja kenttiä pika-aloituksessa.
services: powerapps
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: 2175b684d88d1823fd2672f672e776ca1e26f164
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="quickstart-manage-custom-fields"></a>Pika-aloitus: mukautettuja kenttien hallinta
Kaikissa entiteeteissä voi luoda ja päivittää yhden tai useamman mukautetun entiteetin. Mukautetun kentän luomisen yhteydessä määritetään joukko ominaisuuksia, kuten kentän nimi, näyttönimi ja kentän sisältämien tietojen tyyppi. Lisätietoja on kohdassa [Entiteetin määritteiden metatiedot](../../developer/common-data-service/entity-attribute-metadata.md).

> [!NOTE]
> Jokaisessa entiteetissä on [järjestelmäkenttiä], joista ilmenee esimerkiksi tietueen viimeisin päivitysajankohta ja päivittäjä. Lisäksi [vakioentiteeteissä](data-platform-intro.md#system-fields) on vakiokenttiä (oletuskenttiä). Järjestelmä- ja vakiokenttiä ei voi muokata tai poistaa. Jos luot mukautetun kentän, sen on tarjottava näistä sisäänrakennetuista kentistä poikkeavia lisätoimintoja.

## <a name="create-a-field"></a>Kentän luominen

1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

    ![Entiteetin tiedot] ja (./media/data-platform-cds-create-entity/entitylist.png "entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaa entiteettiä tai [Luo uusi entiteetti](data-platform-create-entity.md).

3. Lisää uusi kenttä entiteettiin napsauttamalla kohtaa **Lisää kenttä**.

4. Anna Uusi kenttä -ruudussa kentälle **Näyttönimi**. **Nimi**-kenttä täyttyy automaattisesti, ja sitä käytetään kentän yksilöivänä nimenä. **Näyttönimi** näkyy kentän käyttäjille, ja **Nimi**-kentän nimeä käytetään sovelluksen luomiseen liittyvissä lausekkeissa ja kaavoissa.

    > [!NOTE]
    > **Näyttönimi**-kenttiä voi milloin tahansa muokata, niin että sovelluksissa näkyvä nimi vaihtuu. **Nimi**-kenttää ei voi muokata entiteetin tallentamisen jälkeen, sillä se saattaa aiheuttaa olemassa olevan sovelluksen vioittumisen.

    ![Uusi kenttä] ja (./media/data-platform-cds-create-entity/newfieldpanel.png "Uusi kenttäpaneeli")

5. Valitse kentän **tietotyyppi**. Se määrittää tietojen tallennustavan ja sen, miten tiedot näytetään sovelluksissa. Esimerkiksi teksti tallennetaan eri tavoin kuin desimaaliluku tai URL-osoite. Lisätietoja käytettävissä olevista tietotyypeistä on kohdassa [Entiteetin määritteiden metatiedot](../../developer/common-data-service/entity-attribute-metadata.md).

    Anna pyydettäessä valitsemaasi tietotyyppiin liittyviä lisätietoja. Esiin tulee eri kenttiä tietotyypistä riippuen. Jos olet luomassa kentän, jonka tyyppi on asetusjoukko tai monivalinta-asetusjoukko, voit valita vaihtoehdon **Uusi asetusjoukko** ja luoda uuden asetusjoukon kentän luomisen yhteydessä. Lisätietoja on kohdassa [Asetusjoukon luominen](custom-picklists.md).

    ![Uusi kenttä] ja (./media/data-platform-cds-create-entity/newfieldpanel-2.png "Uusi kenttäpaneeli")


7. Valitse **Pakollinen**-kohdan valintaruutu, jos haluat suositella tätä kenttää sovelluksissa pakolliseksi. Se ei kuitenkaan tarkoita, että pakollisuus toteutetaan tiukasti kaikkien Common Data Service -yhteyksien kautta. Jos haluat varmistaa, että kenttä varmasti täytetään, luo [liiketoimintasääntö](data-platform-create-business-rule.md).

8. Valitse **Haettavissa**-kohdan valintaruutu, jos haluat, että tämä kenttä on käytettävissä näkymissä, kaavioissa, koontinäytöissä ja erikoishaussa. Yleensä tämä valintaruutu kannattaa valita.

9. Sulje kenttäpaneeli ja palaa entiteettiin napsauttamalla tai napauttamalla **Valmis**-painiketta. Voit toistaa vaiheet 3–9 jokaisen lisäkentän kohdalla.
   
    > [!IMPORTANT]
    > Kenttää ei ole tallennettu tai luotu, ennen kuin tallennat entiteetin muutokset.

10. Viimeistele muutokset ja tallenna ne Common Data Service -palveluun napsauttamalla tai napauttamalla **Tallenna entiteetti** -kohtaa.

    Saat ilmoituksen, kun toiminto on suoritettu onnistuneesti. Jos toiminto epäonnistuu, virheilmoitus kertoo ilmenneet ongelmat ja niiden korjauskeinot.

## <a name="create-a-calculated-or-roll-up-field"></a>Lasketun kentän tai koontikentän luominen

Laskettujen kenttien avulla voit automatisoida organisaation liiketoimintaprosessien manuaalisia laskutoimituksia. Esimerkiksi myyntihenkilö saattaa haluta tietää liiketoimintamahdollisuuden painotetun tuoton, joka lasketaan kertomalla liiketoimintamahdollisuuden tuottoarvio sen todennäköisyydellä. Tai ehkä hän haluaa, että kaikkiin yli 500 euron tilauksiin sovelletaan automaattisesti alennusta. Laskettu kenttä voi sisältää yksinkertaisia laskutoimituksia tai monenlaisia ehdollisia toimintoja, kuten ”suurempi kuin” tai ”tai muuten”. Laskettuja kenttiä voi luoda seuraavilla tietotyypeillä:

* Yksi tekstirivi
* Asetusjoukko
* Kaksi vaihtoehtoa
* Kokonaisluku
* Desimaaliluku
* Valuutta
* Päivämäärä ja aika

Lisätietoja tuetuista lauseketyypeistä ja esimerkkejä on kohdassa [Laskettujen kenttien määrittely](/dynamics365/customer-engagement/customize/define-calculated-fields).


## <a name="update-or-delete-a-field"></a>Päivitä tai poista kenttä
1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio, napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa ja valitse entiteetti.
2. Napauta tai napsauta valitun entiteetin kenttäluettelossa olevaa kenttää ja toimi jollain seuraavista tavoista:
   
   * Muuta vähintään yhtä kentän ominaisuutta.
   * Poista kenttä napsauttamalla tai napauttamalla kentän oikean reunan lähellä olevaa kolmea pistettä (...) ja valitsemalla sitten **Poista**.

3. Lähetä muutoksesi valitsemalla **Tallenna entiteetti**.
   
    > [!IMPORTANT]
    > Menetät kaikki muutokset, jos et tallenna niitä, ennen kuin avaat uuden sivun tai suljet selaimen.

    Saat ilmoituksen, kun toiminto on suoritettu onnistuneesti. Jos toiminto epäonnistuu, virheilmoitus kertoo ilmenneet ongelmat ja niiden korjauskeinot.

## <a name="best-practices-and-restrictions"></a>Parhaat käytännöt ja rajoitukset
Pidä seuraavat asiat mielessä, kun luot ja muokkaat kenttiä:

* Järjestelmäkenttiä ja niiden arvoja ei voi muokata tai poistaa.
* Vakioentiteetissä ei voi muokata eikä poistaa vakiokenttää (oletuskenttä), lisätä tietoja vaativaa kenttää eikä tehdä muita muutoksia, jotka saattavat vioittaa kyseistä entiteettiä käyttävää sovellusta.
* Mukautetussa entiteetissä kannattaa varmistaa, etteivät muutokset vioita mitään kyseistä entiteettiä käyttävää sovellusta.
* Jokaiselle mukautetulle kentälle on annettava kyseisessä entiteetissä ainutkertainen nimi. Kenttää ei voi nimetä uudelleen kentän luomisen jälkeen.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Entiteettien välisen suhteen määrittely](data-platform-entity-lookup.md)
* [Liiketoimintasäännön luominen](data-platform-create-business-rule.md)
* [Sovelluksen luominen entiteettien avulla](../canvas-apps/data-platform-create-app.md)
* [Sovelluksen luominen alusta alkaen käyttämällä Common Data Service -tietokantaa](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Tietosuojailmoitus
Microsoft PowerApps Common Data Model kerää ja tallentaa mukautettuja entiteettejä ja kenttien nimiä diagnostiikkajärjestelmäämme.  Näiden tietojen avulla parannamme asiakkaille tarjottavaa yleistä tietomallia. Tekijöiden luomat entiteettien ja kenttien nimet auttavat meitä ymmärtämään Microsoft PowerApps -yhteisössä yleisiä skenaarioita ja havaitsemaan palvelun vakioentiteettitarjonnan puutteita, kuten organisaatioihin liittyviä rakenteita. Microsoft ei avaa eikä käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja eikä niitä replikoida tietokannan luomisalueen ulkopuolelle. Huomaa kuitenkin, että mukautetut entiteettien nimet ja kentät saatetaan replikoida monelle alueelle ja poistetaan tietojen säilytyskäytäntöjemme mukaisesti. Microsoft on sitoutunut takaamaan käyttäjien tietosuojan [luottamuskeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) kuvaillulla tavalla.

