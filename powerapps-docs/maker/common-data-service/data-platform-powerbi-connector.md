---
title: PowerBI-raportin luominen | Microsoft Docs
description: Tietoihin yhdistäminen Power BI Desktopista Common Data Service for Apps -liittimen avulla.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
ms.openlocfilehash: d8323eb103751a1be78aeea0093b9d6651ddc3e2
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34445850"
---
# <a name="create-a-power-bi-report"></a>Luo Power BI -raportti
Common Data Service for Appsin avulla voit yhdistää suoraan tietoihisi Power BI Desktopin avulla, jolloin voit luoda raportteja ja julkaista ne Power BI:ssä. Power BI -raportteja voidaan käyttää koontinäytöissä, jakaa muille käyttäjille ja käyttää eri ympäristöissä Power BI -mobiilisovelluksissa.

![Power BI Desktop](./media/data-platform-cds-powerbi-connector/PBIDesktop.png "Power BI Desktop")

## <a name="prerequisites"></a>Edellytykset

Jos haluat käyttää Power BI:tä Common Data Service for Appsissa, tarvitset seuraavat:

* Lataa ja asenna Power BI Desktop, joka on ilmainen paikallisessa tietokoneessa suoritettava sovellus. Voit ladata Power BI Desktopin [täältä](https://powerbi.microsoft.com/desktop/).
* Common Data Service for Apps-ympäristö ja tekijän oikeudet portaalin käyttämiseksi ja lukuoikeudet entiteettien tietojen käyttämiseksi.

## <a name="finding-your-common-data-service-for-apps-environment-url"></a>Common Data Service for Apps -ympäristön URL-osoitteen löytäminen

1. Avaa [PowerApps](https://web.powerapps.com) ja valitse ympäristö, johon muodostat yhteyden. Napsauta **asetuskuvaketta** oikeassa yläkulmassa ja valitse **Kehittyneet mukautukset**

    ![CDS for Apps -ympäristö](./media/data-platform-cds-powerbi-connector/CDSEnv1.png "CDS for Apps -ympäristö")

2. Valitse Kehittäjien resurssit -osiossa **Resurssit**, jolloin avautuu uusi välilehti.

    ![CDS for Apps -ympäristö](./media/data-platform-cds-powerbi-connector/CDSEnv2.png "CDS for Apps -ympäristö")

3. Kopioi URL-osoitteen päätaso uuteen välilehteen. Se on ympäristösi yksilöivä URL-osoite. URL-osoite on muotoa **https://yourenvironmentid.crm.dynamics.com/**. Älä kopioi loppua URL-osoitteesta. Pidä se ulottuvillasi, jotta voit käyttää sitä luodessasi Power BI -raporttia.

    ![CDS for Apps -ympäristö](./media/data-platform-cds-powerbi-connector/CDSEnv3.png "CDS for Apps -ympäristö")

## <a name="connecting-to-common-data-service-for-apps-from-power-bi-desktop"></a>Common Data Service for Appsiin yhdistäminen Power BI Desktopista

1. Käynnistä **Power BI Desktop**. Jos kyseessä on ensimmäinen kerta, saatat nähdä aloitusnäytön tai saada suoraan tyhjän pohjan. Valitse kummassakin tapauksessa **Nouda tiedot** ja sitten **Lisää**, jolloin avautuu Power BI Desktopissa käytettävissä olevien tietolähteiden täydellinen luettelo.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport1.png "Power BI Desktop")

2. Valitse **Online-palvelut** ja **Common Data Service for Apps (beeta)** liitinluettelosta. Napsauta **Yhdistä**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport2.png "Power BI Desktop")

3. Liitä **Common Data Service for Apps -ympäristön URL-osoite** **Palvelimen URL-osoite** -kenttään ja valitse **OK**. Jos tämä on ensimmäinen kerta, sinua kehotetaan kirjautumaan samoilla tunnistetiedoilla, joilla yhdistät PowerAppsiin ja Common Data Service for Appsiin.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport3.png "Power BI Desktop")

4. Siirtymistoiminto näyttää kaikki ympäristössäsi käytettävissä olevat entiteetit ryhmiteltyinä kolmeen kansioon. Laajenna **Common Data Model** -kansio.

    * Common Data Model – nämä ovat vakioentiteettejä, joita käytetään yleisesti ja jotka ovat käytettävissä kaikissa ympäristöissä Common Data Modelin osana.
    * Mukautetut entiteetit – nämä ovat entiteettejä, jotka olet luonut tai tuonut ympäristöösi.
    * Järjestelmä – sisältää kaikki entiteetit ympäristössäsi, mukaan lukien Common Data Model ja mukautetut entiteetit.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport4.png "Power BI Desktop")

5. Valitse **Tili**-entiteetti, niin näet esikatselun tiedoistasi oikealla olevassa ruudussa, ja valitse **Lataa**.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport5.png "Power BI Desktop")

6. Entiteettisi on nyt ladattu raporttiin, ja voit alkaa luoda raportteja, tai lisää muita entiteettejä toistamalla tämä prosessi.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport6.png "Power BI Desktop")

7. Valitse **Nimi**-kenttä kenttäpaneelista ja lisää uusi visualisointi raporttipohjaasi. Voit nyt toistaa tämän prosessin ja luoda raporttisi muuttamalla visualisointeja.

    ![Power BI Desktop](./media/data-platform-cds-powerbi-connector/CreateReport7.png "Power BI Desktop")


## <a name="using-option-sets"></a>Asetusjoukkojen käyttäminen

Entiteeteissä käytetään asetusjoukkoja, joiden avulla käyttäjä saa avattavan luettelon arvoista sovelluksissa ja työnkuluissa. Kun Power BI -liitintä käytetään, asetusjoukkokentät esitetään kahtena sarakkeena sekä yksilöivän arvon että näyttöarvon näyttämiseksi.

Esimerkiksi jos entiteetissäsi olisi ApprovalStatus-niminen asetusjoukko, Power BI:ssä näkyisi kaksi kenttää:

* ApprovalStatus – Tämä näyttää yksilöivän kokonaislukuarvon kullekin asetusjoukon kohteelle. Siitä on apua käytettäessä suodattimia, jotka eivät muutu, jos teet myöhemmin muutoksia näyttönimeen.
* ApprovalStatus_display – Tämä näyttää kohteen kutsumanimen, ja sitä käytetään yleisimmin, kun asetus esitetään taulukossa tai kaaviossa.

    |ApprovalStatus|ApprovalStatus_Display|
    |---------|---------|
    1|Lähetetty
    2|Tarkistettavana
    3|Hyväksytty
    4|Hylätty

## <a name="navigating-relationships"></a>Suhteissa liikkuminen

Common Data Service for Apps -palvelun suhteet edellyttävät, että luot Power BI Desktopissa suhteen kahden entiteetin välille käyttämällä GUID-tunnusta. Se on järjestelmän luoma yksilöivä tunnus, joka varmistaa, että suhteet luodaan tietueille, jotka saattavat olla monitulkintaisia tai kaksoiskappaleita muista kentistä. Lue lisää Power BI Desktopin suhteiden hallinnasta [täältä](https://docs.microsoft.com/power-bi/desktop-create-and-manage-relationships).

Vaikka osa suhteista voidaan luoda automaattisesti, voit silti tarkistaa ja varmistaa oikeiden suhteiden muodostamisen raporttia luotaessa:

* Entiteetin hakukenttä sisältää tietueen GUID-tunnuksen liittyvässä entiteetissä.
* Liittyvässä entiteetissä on kenttä muodossa ”[EntityName]id”, joka sisältää GUID-tunnuksen, esimerkiksi Accountid tai MyCustomEntityid
* Power BI Desktopin suhteiden hallintaominaisuuden avulla voit luoda uuden suhteen hakukentän ja liittyvän entiteetin tunnuskentän välille.


## <a name="next-steps"></a>Seuraavat vaiheet
* [Entiteetin kenttien hallinta](data-platform-manage-fields.md)
* [Entiteettien välisten suhteiden määrittely](data-platform-entity-lookup.md)


