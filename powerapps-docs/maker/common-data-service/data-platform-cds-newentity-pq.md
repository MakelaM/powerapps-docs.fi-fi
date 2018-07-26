---
title: Tietojen lisääminen Common Data Service for Appsissa olevaan entiteettiin Power Queryn avulla | Microsoft Docs
description: Vaiheittaiset ohjeet tietojen lisäämiseen Common Data Service (CDS) for Appsissa olevaan uuteen tai olemassa olevaan entiteettiin toisesta tietolähteestä Power Queryn avulla.
author: AFTOwen
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 03/21/2018
ms.author: anneta
ms.openlocfilehash: c5da71198f33661766d8fc214816c2e714736360
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218759"
---
# <a name="add-data-to-an-entity-in-common-data-service-for-apps-by-using-power-query"></a>Tietojen lisääminen Common Data Service for Appsissa olevaan entiteettiin Power Queryn avulla
Tässä toimenpiteessä luot entiteetin [Common Data Service (CDS) for Appsissa](data-platform-intro.md) ja täytät entiteetin OData-syötteen tiedoilla Power Queryn avulla. Voit integroida tietoja samalla tavalla muun muassa seuraavista verkon ja lähiverkon lähteistä:

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

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja napsauta tai napauta vasemmassa reunassa olevan **Tiedot**-kohdan alaspäin osoittavaa nuolta.

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