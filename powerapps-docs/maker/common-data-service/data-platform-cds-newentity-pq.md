---
title: Tietojen lisääminen Common Data Servicen entiteettiin Power Queryn avulla | Microsoft Docs
description: Vaiheittaiset ohjeet Power Queryn käyttämisestä tietojen lisäämisessä Common Data Servicen uuteen tai olemassa olevaan entiteettiin toisesta tietolähteestä.
author: mllopis
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 03/21/2018
ms.author: millopis
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="add-data-to-an-entity-in-common-data-service-by-using-power-query"></a>Tietojen lisääminen Common Data Servicen entiteettiin Power Queryn avulla
Tämän toimintosarjan avulla luodaan entiteetti [Common Data Servicessä](data-platform-intro.md) ja täytetään entiteetin tiedot OData-syötteestä Power Queryn avulla. Voit integroida tiedot esimerkiksi näistä online-lähteistä ja paikallisista lähteistä käyttämällä samoja tekniikoita:

* SQL Server
* Salesforce
* IBM DB2
* Käyttö
* Excel
* Web-ohjelmointirajapinnat
* OData-syötteet
* Tekstitiedostot

Voit myös suodattaa, muuntaa ja yhdistää tietoja ennen kuin ne ladataan uuteen tai olemassa olevaan entiteettiin.

Jos sinulla ei ole PowerAppsin käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Edellytykset
Voit seurata tätä ohjeaihetta, jos vaihdat [ympäristöön](../canvas-apps/working-with-environments.md), jossa voit luoda entiteettejä.

## <a name="specify-the-source-data"></a>Lähdetietojen määrittäminen

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja napsauta tai napauta **Tiedot**-kohdan alanuolta lähellä vasemmanpuoleista reunaa.

    ![PowerApps-kotisivu](./media/data-platform-cds-newentity-pq/sign-in.png)

1. Napsauta tai napauta näyttöön tulevassa luettelossa **Tietojen integrointi** -kohtaa. Napsauta tai napauta sitten ikkunan oikeassa yläkulmassa olevaa **Uusi projekti** -kohtaa.

1. Napsauta tai napauta tietolähdeluettelossa **OData**-kohtaa.

    ![OAuth-yhdysohjelman valitseminen](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. Kirjoita **Yhteysasetukset**-kohtaan tämä URL-osoite tai liitä se ja valitse **Seuraava**:<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. Valitse taulukkoluettelossa **Asiakkaat**-valintaruutu ja napsauta tai napauta **Seuraava**-kohtaa.

    ![Asiakkaat-taulukon valitseminen](./media/data-platform-cds-newentity-pq/select-table.png)

1. (valinnainen) Muokkaa rakennetta tarpeitasi vastaaviksi valitsemalla sisällytettävät sarakkeet, muuntamalla taulukkoa yhdellä tai usealla tavalla, lisäämällä indeksi tai ehdollinen sarake tai tekemällä muita muutoksia.

1. Napsauta tai napauta oikeassa alakulmassa olevaa **Seuraava**-kohtaa.

## <a name="specify-the-target-entity"></a>Kohde-entiteetin määrittäminen
1. Valitse **Lataa asetukset** -kohdassa **Lataa uuteen entiteettiin**.

    ![Uuden entiteetin nimen määrittäminen](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    Voit antaa uudelle entiteetille eri nimen tai näyttönimen. Jätä kuitenkin oletusarvot tämän opetusohjelman arvojen mukaisiksi.

1. Napsauta tai napauta **Ensisijainen nimi -kenttä** -luettelossa **Yhteyshenkilön nimi** ja napsauta tai napauta sitten oikeassa alakulmassa oleva **Seuraava**.

    Voit määrittää toisen ensisijaisen nimen kentälle, määrittää lähdetaulukon toisen sarakkeen entiteetin jokaiseen kenttään, jotka luot, tai molemmat. Jos haluat noudattaa täysin tätä opetusohjelmaa, jätä sarakkeen oletusvastaavuus.

1. Kun **Latauksen tila** on **Valmis**, valitse oikeassa alakulmassa oleva **Valmis**.

1. Valitse **Tiedot**-kohdassa (lähellä vasemmanpuoleista reunaa) **Entiteetit**, jolloin näyttöön tulee tietokannan entiteettien luettelo.

    OData-syötteestä luotu **Asiakkaat**-entiteetti näkyy mukautettuna entiteettinä.

    ![Vakioentiteettien ja mukautettujen entiteettien luettelo](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> Jos lisäät tietoja olemassa olevaan entiteettiin Power Queryn avulla, entiteetin kaikki tiedot korvataan.

Jos valitset **Lataa olemassa olevaan entiteettiin** -kohdan, voit määrittää entiteetin, johon tiedot lisätään **Asiakkaat**-taulukosta. Voit esimerkiksi lisätä tietoja **Asiakas**-entiteettiin, jonka mukana toimitetaan Common Data Service. Voit määrittää **Lähdesarake**-kohdassa, että **Yhteyshenkilön nimi**-sarakkeen tiedot **Asiakkaat**-taulukosta on lisättävä **Nimi**-sarakkeeseen **Asiakkaat**-entiteetissä.

![Uuden entiteetin nimen määrittäminen](./media/data-platform-cds-newentity-pq/existing-entity.png)

Olemme innoissamme näistä toiminnoista ja odotamme kuulevamme palautteesi. [Lähetä meille näitä toimintoja koskevia ehdotuksia ja palautetta](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1)!

Jos näyttöön tulee [oikeuksia koskeva virhesanoma](data-platform-cds-newentity-troubleshooting-mashup.md), ota yhteyttä järjestelmänvalvojaan.
