---
title: Pikaopas mukautetun entiteetin luomiseen| Microsoft Docs
description: Pikaopas mukautetun, toiseen entiteettiin perustuvan entiteetin luomiseen tai luomiseen alusta.
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
ms.openlocfilehash: e22a18bacb258ca46c8f36d647f9ebcc45282929
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2018
---
# <a name="quickstart-create-a-custom-entity"></a>Pikaopas: Mukautetun entiteetin luominen
Voit luoda mukautetun entiteetin organisaatiokohtaisten tietojen tallentamiseen. Voit sitten näyttää tiedot kehittämällä sovelluksen, joka viittaa entiteettiin. Luotuasi entiteetin voit [luoda siihen kenttiä tai muokata niitä](data-platform-manage-fields.md) ja [luoda yhteyksiä entiteettien välille](data-platform-entity-lookup.md).

Näissä ohjeissa näytetään, miten voit luoda mukautetun entiteetin manuaalisesti. Voit myös luoda entiteetin olemassa oleviin tietoihin perustuen Power Queryllä. Lisätietoja on artikkelissa [Luo uusi entiteetti Power Queryllä](data-platform-cds-newentity-pq.md)

> [!NOTE]
> Katso [entiteettiviitettä](../../developer/common-data-service/reference/about-entity-reference.md) ennen entiteetin luomista. Nämä entiteetit kattavat tyypilliset tilanteet, kuten tilit ja yhteyshenkilöt. Jos jokin näistä entiteeteistä vastaa tarpeitasi sellaisenaan tai vähäisten muokkausten jälkeen, säästät aikaa käyttämällä kyseistä entiteettiä.

## <a name="create-an-entity"></a>Luo kohde
1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

    ![Entiteetin tiedot] ja (./media/data-platform-cds-create-entity/entitylist.png "entiteettiluettelo")

2. Napsauta tai napauta komentopalkissa **Uusi entiteetti**.
3. Kirjoita **Näyttönimi**-kenttään nimi, joka on helposti tunnistettavissa ja viittaa tähän entiteettiin tulevaisuudessa. Tätä käytetään myös lomakkeissa, kaavioissa ja muissa objekteissa, jotka on luotu käyttäen tätä entiteettiä. Kahden muun kentän tiedot täytetään myös:

    * Monikkomuotoinen näyttönimi – käytetään tämän entiteetin kanssa PowerAppsista tai Flow’sta ja entiteetin nimenä Common Data Service WebAPIn kautta. Monikkomuotoinen nimi luodaan automaattisesti, mutta sitä voidaan muuttaa.
    * Nimi – tämä on entiteetin yksilöllinen nimi, se ei voi sisältää erikoismerkkejä tai välilyöntejä ja sen täytyy olla yksilöllinen. Nimi sisältää myös etuliitteen, joka määritettiin, kun ympäristö luotiin. Sitä käytetään varmistamaan, että luomasi entiteetit voidaan viedä ja tuoda muihin ympäristöihin ilman yhteensopimattomuutta muiden entiteettien nimien kanssa. Tämä etuliite voidaan muuttaa päivittämällä se Publisherissa Common Data Servicen oletusratkaisulle.

    > [!NOTE]
    > **Näyttönimi**-kenttiä voi milloin tahansa muokata, niin että sovelluksissa näkyvä nimi vaihtuu. **Nimi**-kenttää ei voi muokata entiteetin tallentamisen jälkeen, sillä se saattaa aiheuttaa olemassa olevan sovelluksen vioittumisen.

    ![Uusi entiteetti](./media/data-platform-cds-create-entity/newentitypanel.png "Uusi entiteetti -paneeli")

4. Kun valitset **Seuraava**, entiteetin tietosivu avautuu. Oletusarvoisesti jokainen entiteetti alkaa Ensisijainen nimi -kentällä. Tätä kenttää käytetään luotaessa hakuja tässä entiteetissä. Sitä käytetään yleensä entiteettiin tallennettujen tietojen nimen tai ensisijaisen kuvauksen tallentamiseen.

    > [!NOTE]
    > **Ensisijainen nimi** -kentän nimi ja näyttönimi voidaan päivittää ennen entiteetin ensimmäistä tallennuskertaa. Jos esimerkiksi haluat kutsua tätä kenttää nimellä ”Opiskelijan nimi” nimen ”Ensisijainen nimi” sijasta

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/newentitydetails.png "Uuden entiteetin tiedot")

5. Valinnainen: Lisää tekstikenttä entiteettiin napsauttamalla kohtaa **Lisää kenttä**. Kirjoita uuden kentän paneeliin kentälle **Näyttönimi** ja valitse tietotyyppi. Lisätietoja on artikkelissa [Entiteetin kenttien hallinta](data-platform-manage-fields.md).

    ![Uusi kenttä] ja (./media/data-platform-cds-create-entity/newfieldpanel-2.png "Uusi kenttäpaneeli")


6. Valitse **Valmis**, kun haluat lisätä kentän, ja lisää kenttiä toistamalla vaihe 5.
7. Tallenna entiteetti valitsemalla **Tallenna entiteetti** ja anna se käyttöön sovelluksiin.

    Entiteetti näkyy tietokannassa entiteettien luettelossa. Jos haluat nähdä luomasi entiteetit, voit muuttaa komentopalkin suodattimen oletusarvon mukautetuksi arvoksi

## <a name="system-fields"></a>Järjestelmäkentät
Kaikissa entiteeteissä on järjestelmäkentät. Nämä kentät ovat vain luettavissa. Tämän vuoksi et voi muuttaa tai poistaa näitä kenttiä, eikä niille osoiteta arvoja. Oletusarvoisesti järjestelmäkenttiä ei näytetä kenttäluettelossa, vaikka ne ovat olemassa entiteetissä. Jos haluat nähdä kaikki kentät, voit muuttaa suodatinta komentopalkissa asetuksesta **Oletus** asetukseksi **Kaikki**.

Lisätietoja entiteettiin liittyvistä metatiedoista on kohdassa [Kohteiden metatiedot](../../developer/common-data-service/entity-metadata.md)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Entiteetin kenttien hallinta](data-platform-manage-fields.md)
* [Entiteettien yhteyksien määrittely](data-platform-entity-lookup.md)
* [Sovelluksen luominen käyttämällä Common Data Service -tietokantaa](../canvas-apps/data-platform-create-app.md)
* [Sovelluksen luominen alusta alkaen käyttämällä Common Data Service -tietokantaa](../canvas-apps/data-platform-create-app-scratch.md)

## <a name="privacy-notice"></a>Tietosuojailmoitus
Microsoft PowerApps Common Data Model kerää ja tallentaa mukautettuja entiteettejä ja kenttien nimiä diagnostiikkajärjestelmäämme.  Näiden tietojen avulla parannamme asiakkaille tarjottavaa yleistä tietomallia. Tekijöiden antamat entiteettien ja kenttien nimet auttavat meitä ymmärtämään Microsoft PowerApps -yhteisössä yleisiä skenaarioita. Samalla ne auttavat meitä havaitsemaan palvelun vakioentiteettitarjonnan puutteita, kuten organisaatioihin liittyviä rakenteita. Microsoft ei avaa eikä käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja, eikä niitä replikoida tietokannan luomisalueen ulkopuolelle. Huomaa kuitenkin, että mukautettujen entiteettien ja kenttien nimet voidaan replikoida eri alueille ja poistetaan Microsoftin tietojen säilytyskäytäntöjen mukaisesti. Microsoft on sitoutunut takaamaan käyttäjien tietosuojan [luottamuskeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) kuvaillulla tavalla.

