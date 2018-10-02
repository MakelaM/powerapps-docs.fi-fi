---
title: PowerBI-raportin luominen | Microsoft Docs
description: Tietojen käyttäminen PowerBI Desktop -sovelluksessa Common Data Service sovelluksiin -yhdysohjelman avulla.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-power-bi-report"></a>Power BI -raportin luominen
Common Data Service sovelluksille mahdollistaa tietojen käyttämisen suoraan Power BI Desktop -sovelluksen avulla raporttien luomiseksi ja niiden julkaisemiseksi Power BI:ssä. Power BI:ssä raportteja voi käyttää koontinäytöissä ja niitä voi jakaa muille käyttäjille. Niitä voi käyttää myös Power BI:n mobiilisovelluksissa eri ympäristöissä.

![Power BI Desktop](./media/data-platform-cds-powerbi-connector/PBIDesktop.png "Power BI Desktop")

## <a name="prerequisites"></a>Edellytykset

Jos haluat käyttää Power BI:tä Common Data Service sovelluksille -ratkaisussa, tee seuraavat toiminnot:

* Lataa ja asenna Power BI Desktop. Se on ilmainen paikallisesti käytettävä sovellus. Voit ladata Power BI Desktop -sovelluksen [täältä](https://powerbi.microsoft.com/desktop/).
* Common Data Service sovelluksille -ympäristö ja tekijän oikeudet, joiden avulla voi käyttää portaalia. Lukuoikeudet, joiden avulla voi käyttää entiteettien tietoja.

## <a name="finding-your-common-data-service-for-apps-environment-url"></a>Common Data Service sovelluksille -ympäristön URL-osoitteen löytäminen

1. Avaa [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja valitse ympäristö, johon muodostat yhteyden. Valitse oikeassa yläkulmassa oleva **asetusratas** ja valitse sitten **Lisämukautukset**

    ![CDS sovelluksille -ympäristö](./media/data-platform-cds-powerbi-connector/CDSEnv1.png "CDS sovelluksille -ympäristö")

2. Valitse Sovelluskehittäjän resurssit -osassa **Resurssit**, jolloin näyttöön avautuu uusi välilehti.

    ![CDS sovelluksille -ympäristö](./media/data-platform-cds-powerbi-connector/CDSEnv2.png "CDS sovelluksille -ympäristö")

3. Kopioi URL-osoitteen juuri uuteen välilehteen. Tämä on ympäristön yksilöllinen URL-osoite. URL-osoitteen muoto on **https://yourenvironmentid.crm.dynamics.com/**. Varmista, että et kopioi URL-osoitteen loppuosaa. Talleta osoite niin, että saat sen käyttöösi, kun luot PowerBI-raportin.

    ![CDS sovelluksille -ympäristö](./media/data-platform-cds-powerbi-connector/CDSEnv3.png "CDS sovelluksille -ympäristö")

## <a name="connecting-to-common-data-service-for-apps-from-power-bi-desktop"></a>Yhteyden muodostaminen Common Data Service sovelluksille -ratkaisuun Power BI Desktop -sovelluksesta

1. Käynnistä **Power BI Desktop**. Jos käynnistät sen ensimmäisen kerran, näyttöön tulee aloitusnäyttö tai tyhjä kaavio. Valitse kummassakin tapauksessa **Hae tiedot** ja valitse sitten **Lisää**. Näyttöön tulee Power BI Desktop -sovelluksen käytettävissä olevien tietolähteiden täydellinen luettelo.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport1.png "Power BI Desktop")

2. Valitse yhdysohjelmaluettelosta **Online-palvelut** ja **Common Data Service sovelluksille (beetaversio)**. Valitse **Yhdistä**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport2.png "Power BI Desktop")

3. Liitä **Common Data Service sovelluksille -ympäristön URL-osoite** **Palvelimen URL-osoite** -kenttään ja valitse **Ok**. Jos tämä on ensimmäinen kerta, kun teet näin, näyttöön tulevat PowerAppsissä ja Common Data Service sovelluksille -ratkaisussa käytettävät tunnistetiedot.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport3.png "Power BI Desktop")

4. Navigator näyttää kaikki ympäristössä käytettävissä olevat entiteetit kolmeen kansioon ryhmiteltyinä. Laajenna **Common Data Model** -kansio.

    * Common Data Model - nämä ovat vakioentiteettejä, joita käytetään yleisesti. Ne ovat käytettävissä kaikissa ympäristöissä Common Data Model -ratkaisun osana.
    * Mukautetut entiteetit - nämä ovat ympäristössä luotuja tai sinne tuotuja entiteettejä.
    * Järjestelmä - sisältää ympäristön kaikki entiteetit, myös Common Data Model -entiteetit ja mukautetut entiteetit.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport4.png "Power BI Desktop")

5. Valitse **Asiakas**-entiteetti ja tarkastele tietojen esikatselua oikeassa ruudussa. Valitse **Lataa**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport5.png "Power BI Desktop")

6. Entiteetti on nyt ladattu raporttiin ja voit alkaa luoda raportteja. Halutessasi voit toistaa tämän prosessin ja lisätä entiteettejä.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport6.png "Power BI Desktop")

7. Valitse Kenttä-paneelissa **Nimi**-kenttä ja lisää raporttikaavioon uusi visualisointi. Voit nyt toistaa tämän prosessin ja luoda raportin muuttamalla visualisointeja.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport7.png "Power BI Desktop")


## <a name="using-option-sets"></a>Asetusjoukkojen käyttäminen

Asetusjoukot mahdollistavat sovellusten ja työnkulkujen entiteeteissä avattavien luetteloiden arvojen käyttämisen. Kun käytössä on Power BI -yhdistinvalintajoukko, kentät näytetään kaksisarakkeisina. Kentissä on näkyvissä sekä yksilöivä arvo että näyttöarvo.

Jos esimerkiksi ApprovalStatus-nimisellä entiteetillä on asetusjoukko, Power BI:ssä on näkyvissä seuraavat kaksi kenttää:

* ApprovalStatus - Näyttää yksilöllisen kokonaisarvon asetusjoukon jokaiselle nimikkeelle. Tämä on hyödyllistä suodattimien käyttämisen yhteydessä, koska tällöin näyttönimien muuttaminen ei vaikuta suodattimiin.
* ApprovalStatus_display - Näyttää nimikkeen näyttönimen kutsumanimen. Tätä käytetään yleensä silloin, kun asetus esitetään taulukossa tai kaaviossa.

    |ApproalStatus|ApprovalStatus_Display|
    |---------|---------|
    1|Lähetetty
    2|Tarkistettavana
    3|Hyväksytty
    4|Hylätty

## <a name="navigating-relationships"></a>Suhteissa siirtyminen

Common Data Service sovelluksille -ratkaisun suhteet edellyttävät, että PowerBI Desktop -sovelluksen ja kahden GUID-kenttää käyttävän entiteetin välille luodaan suhde. GUID on järjestelmän luoma yksilöllinen tunnus, joka varmistaa, että suhteet luodaan luontitietueille, joissa voi olla sekaannuksia tai kaksoiskappaleita muiden kenttien kanssa. Lisätietoja Power BI Desktop -sovelluksen suhteiden hallinnasta on [täällä](https://docs.microsoft.com/power-bi/desktop-create-and-manage-relationships).

Vaikka jotkin suhteet voidaan luoda automaattisesti, voit silti tarkistaa ne ja varmistaa, että raportin luomisen yhteydessä luodaan oikeat suhteet:

* Entiteetin hakukenttä sisältää liittyvän entiteetin tietueen GUID-tunnuksen.
* Liittyvän entiteetin kenttä on muodossa [EntityName]id. Se sisältää GUID-tunnuksen, joka voi olla esimerkiksi Accountid tai MyCustomEntityid
* PowerBI Desktop -sovelluksen suhteiden hallintatoiminnon avulla voit luoda uusia suhteita hakukentän ja liittyvän entiteetin tunnuskentän välille.


## <a name="next-steps"></a>Seuraavat vaiheet
* [Entiteetin kenttien hallinta](data-platform-manage-fields.md)
* [Entiteettien välisten suhteiden määrittäminen](data-platform-entity-lookup.md)


