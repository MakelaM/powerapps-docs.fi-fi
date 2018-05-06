---
title: Pikaopas tietojen lisäämiseen Common Data Servicessä olevaan entiteettiin Power Queryllä | Microsoft Docs
description: Tämän pikaoppaan vaiheittaisissa ohjeissa neuvotaan, miten Common Data Service for Appsissa olevaan uuteen tai olemassa olevaan entiteettiin lisätään tietoja toisesta tiedonlähteestä Power Query -apuohjelman avulla.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: anneta
ms.openlocfilehash: 77906602fad6708857a6c34f44d1bc3c7c258f6c
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2018
---
# <a name="quickstart-add-data-to-an-entity-in-the-common-data-service-by-using-power-query"></a>Pikaopas: Tietojen lisääminen Common Data Servicessä olevaan entiteettiin Power Queryn avulla
Tässä toimenpiteessä luot entiteetin [Common Data Service for Appsissa](data-platform-intro.md) ja täytät entiteetin Power Queryn avulla OData-syötteen tiedoilla. Voit integroida tietoja samalla tavalla muun muassa seuraavista verkon ja lähiverkon lähteistä:

* SQL Server
* Salesforce
* IBM DB2
* Access
* Excel
* WWW-ohjelmointirajapinnat
* OData-syötteet
* Tekstitiedostot

Voit myös suodattaa, muuntaa ja yhdistää tietoja, ennen kuin lisäät ne uuteen tai olemassa olevaan entiteettiin.

Jos sinulla ei ole PowerApps-käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Edellytykset
Jotta voit noudattaa tämän aiheen ohjeita, siirry entiteettien luomisen mahdollistavaan [ympäristöön](../canvas-apps/working-with-environments.md).

## <a name="specify-the-source-data"></a>Lähdetietojen määritys

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com) ja napsauta tai napauta vasemmassa reunassa olevan **Tiedot**-kohdan alaspäin osoittavaa nuolta.

    ![PowerAppsin aloitussivu](./media/data-platform-cds-newentity-pq/sign-in.png)

1. Valitse esiin tulevasta luettelosta **Tietojen integrointi** ja sitten valintaikkunan oikeassa yläkulmassa **Uusi projekti**.

1. Valitse tietolähteiden luettelosta **OData**.

    ![Valitse OAuth-yhdistin](./media/data-platform-cds-newentity-pq/choose-odata.png)

1. Kirjoita tai kopioi ja liitä **Yhteysasetukset**-kohtaan seuraava URL-osoite ja valitse sitten **Seuraava**:<br>
`http://services.odata.org/V4/Northwind/Northwind.svc/`

1. Valitse taulukkoluettelosta **Customers**-valintaruutu ja napsauta tai napauta sitten **Seuraava**-painiketta.

    ![Valitse Customers-taulukko](./media/data-platform-cds-newentity-pq/select-table.png)

1. (valinnainen) Muokkaa rakenne omiin tarpeisiin sopivaksi. Voit esimerkiksi valita haluamasi sarakkeet, muuntaa taulukkoa monella tapaa, lisätä hakemiston tai ehdollisen sarakkeen tai tehdä muita muutoksia.

1. Napsauta tai napauta oikeassa alakulmassa **Seuraava**.

## <a name="specify-the-target-entity"></a>Määritä kohde-entiteetti
1. Valitse **Latausasetukset**-osiossa **Lataa uuteen entiteettiin**.

    ![Määritä uuden entiteetin nimi](./media/data-platform-cds-newentity-pq/new-entity-name.png)

    Voit antaa uudelle entiteetille eri nimen tai näyttönimen. Jätä tällä kertaa kuitenkin oletusarvot, jotta voit noudattaa tämän oppaan ohjeita tarkasti.

1. Valitse **Ensisijainen nimikenttä** -luettelosta **ContactName** ja napsauta tai napauta sitten oikeassa alakulmassa **Seuraava**-painiketta.

    Voit määrittää eri ensisijaisen nimikentän, yhdistää eri lähdetaulukon sarakkeen jokaiseen luotavan entiteetin kenttään tai valita molemmat vaihtoehdot. Jätä oletusarvoiset sarakkeiden yhdistämismääritykset, jos noudatat tätä opasta tarkasti.

1. Kun **Lataustila** on **Valmis**, valitse oikeassa alakulmassa **Valmis**.

1. Valitse **Tiedot**-kohdasta (lähellä vasenta reunaa) **Entiteetit**, niin esiin ilmestyy tietokannassasi olevien entiteettien luettelo.

    OData-syötteestä luomasi **Customers**-entiteetti näkyy mukautettuna entiteettinä.

    ![Vakioentiteettien ja mukautettujen entiteettien luettelo](./media/data-platform-cds-newentity-pq/entity-list.png)

> [!WARNING]
> Jos lisäät Power Queryn avulla tietoja olemassa olevaan entiteettiin, kaikki kyseisen entiteetin tiedot korvataan.

Jos valitset **Lataa olemassa olevaan entiteettiin**, voit määrittää entiteetin johon **Customers**-taulukon tiedot lisätään. Voit esimerkiksi lisätä tiedot **Accounts**-entiteettiin, jota Common Data Service käyttää lähettämiseen. Kohdassa **Lähdesarake** voit määrittää lisäksi, että **Customers**-taulukon **ContactName**-sarakkeen tiedot lisätään **Accounts**-entiteetin **Name**-sarakkeeseen.

![Määritä uuden entiteetin nimi](./media/data-platform-cds-newentity-pq/existing-entity.png)

Olemme innoissamme tästä toiminnosta ja kuulemme mielellään palautteesi. Lähetä meille tähän ominaisuuteen liittyviä [ehdotuksia ja palautetta](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1)!

Jos saat [käyttöoikeuksiin liittyvän virheilmoituksen](data-platform-cds-newentity-troubleshooting-mashup.md), ota yhteyttä järjestelmänvalvojaasi.