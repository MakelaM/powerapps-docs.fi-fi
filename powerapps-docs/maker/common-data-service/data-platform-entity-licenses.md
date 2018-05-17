---
title: Entiteettien käyttöoikeusvaatimukset| Microsoft Docs
description: Selitys Common Data Service (CDS) for Appsin sisältämien entiteettien käyttöoikeusvaatimuksista.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 716e1c2b7e670d8a54e1106cd557bb509323ba8d
ms.sourcegitcommit: b3b6118790d6b7b4285dbcb5736e55f6e450125c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/15/2018
---
# <a name="license-requirements-for-entities"></a>Entiteettien käyttöoikeusvaatimukset
Sovellusten tekijät voivat käyttää useimpia Common Data Service (CDC) for Appsin sisältämiä entiteettejä (mukaan lukien mukautetut entiteetit ja Common Data Modelin mukaiset entiteetit) sovellusten ja työnkulkujen luomiseen käyttäjille, joilla on pelkästään PowerApps Plan 1 tai Microsoft Flow Plan 1. Joissakin tapauksissa monimutkaisia liiketoimintalogiikkaa tai Dynamics 365 -tuotteisiin sidoksissa olevat entiteetit vaativat, että sovelluksen käyttäjällä on tietty käyttöoikeus. Lisätietoja käytettävissä olevista sopimuksista löytyy [PowerAppsin hinnoittelusivulta](https://powerapps.microsoft.com/pricing).

> [!NOTE]
> Sovellukset ja työnkulut, jotka käyttävät näitä entiteettejä, edellyttävät sovelluksen ja työnkulun käyttäjältä asianmukaista käyttöoikeutta, &mdash;eivät sovelluksen tai työnkulun tekijältä tai kehittäjältä.

## <a name="entities-with-complex-business-logic"></a>Entiteetit, joilla on monimutkainen liiketoimintalogiikka
Seuraavia monimutkaisia, palvelimen logiikkaa sisältävät entiteetit vaativat näitä entiteettejä käyttävien sovellusten tai työnkulkujen käyttäjillä PowerApps Plan 2- tai Microsoft Flow Plan 2 -sopimuksen:

* Koodilaajennukset (lisätietoja on artikkelissa [Laajennusten kehittäminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Reaaliaikainen työnkulut (lisätietoja on artikkelissa [Työnkulkuprosessit](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!NOTE]
    >  Vain työnkulkuja, jotka on muunnettu reaaliaikaisiksi työnkuluiksi, pidetään reaaliaikaisina ja synkronoituina. Työnkulkuja, jotka suoritetaan taustalla, voidaan silti käyttää asianmukaisen PowerApps-palvelupaketin osana, eivätkä ne vaadi muita käyttöoikeuksia.

Jos haluat tietää, onko entiteeteissäsi monitasoista liiketoimintalogiikkaa, tarkista laajennuksen kokoonpanojen ja ympäristössäsi määriteltyjen työnkulkujen luettelo.

## <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Käyttöoikeusvaatimusvaikutukset monitasoista liiketoimintalogiikkaa lisättäessä
Sovellusten tekijät voivat lisätä koodilaajennuksia ja reaaliaikaisia työnkulkuja sisältäviä entiteettejä CDC for Appsiin, mutta tämä saattaa muuta jo kehitettyjen sovellusten käyttäjien käyttöoikeusvaatimuksia. Sovellusten tekijöiden tulee olla varovaisia lisätessään monitasoista liiketoimintalogiikkaa entiteettiin ja tarkistaa ensin, mitkä sovellukset käyttävät entiteettiä ja onko kyseisten sovellusten käyttäjillä tarvittavat käyttöoikeudet.

## <a name="entities-restricted-to-dynamics-365-licenses"></a>Dynamics 365 -käyttöoikeuksiin rajoitetut entiteetit
Tietyt entiteetit, jotka on sidottu Dynamics 365 -tuotteiden toiminnallisuuteen, vaativat, että sovellusten käyttäjillä on vastaava tuotteen käyttöoikeus, jos he haluavat luoda, päivittää tai poistaa tietueita entiteettien sisältä. Katso lista rajoitetuista entiteeteistä kohdasta [Rajoitetut entiteetit, jotka vaativat Dynamics 365 -käyttöoikeuksia](data-platform-restricted-entities.md).

## <a name="licensing-example"></a>Esimerkki käyttöoikeuksista
Paula ja Iisakki luovat sovelluksia PowerAppsissa ja käyttävät CDC for Appsia tietojen tallentamiseen.

Paula luo kaksi pohjaan perustuvaa sovellusta:

* Sovellus 1 &ndash; käyttää Contact-entiteettiä sekä muokattua entiteettiä, joka tallentaa liittyvät tiedot
* Sovellus 2 &ndash; käyttää Contact-entiteettiä ja Incident-entiteettiä, joka on rajoitettu entiteetti

Iisakki luo kaksi mallipohjaista sovellusta:

* Sovellus 3 &ndash; käyttää Contact-entiteettiä sekä muokattua entiteettiä, joka tallentaa liittyvät tiedot
* Sovellus 4 &ndash; käyttää Contact-entiteettiä ja Incident-entiteettiä, joka on rajoitettu entiteetti

Paula ja Iisakki tarvitsevat seuraavat käyttöoikeudet:
* Paula tarvitsee PowerApps Plan 1 -käyttöoikeuden luodakseen pohjaan perustuvia sovelluksia CDC for Appsia käyttäen. Jos hänen täytyy luoda tietokanta tai luoda muokattu entiteetti, hän tarvitsee PowerApps Plan 2 -käyttöoikeuden.

* Iisakki tarvitsee PowerApps Plan 2 -käyttöoikeuden luodakseen mallipohjaisia sovelluksia.

Sovellusten käyttäjät tarvitsevat seuraavat käyttöoikeudet:
* Sovelluksen 1 käyttäjät tarvitsevat vain PowerApps Plan 1- tai Plan 2 -käyttöoikeuden, sillä sovellus ei sisällä monitasoista liiketoimintalogiikkaa sisältäviä tai rajoitettuja entiteettejä.

* Sovelluksen 2 käyttäjät tarvitsevat Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365 tai Dynamics 365 Customer Engagement -sopimuksen), koska sovellus sisältää rajoitetun entiteetin.

* Sovelluksen 3 käyttäjät tarvitsevat PowerApps Plan 2 -käyttöoikeuden, koska sovellus on mallipohjainen.

* Sovelluksen 4 käyttäjät tarvitsevat Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365 tai Dynamics 365 Customer Engagement -sopimuksen), koska sovellus sisältää rajoitetun entiteetin.

    Dynamics 365 for Customer Service -sopimus sisältää PowerApps Plan 2 -käyttöoikeuden, joka antaa käyttäjien käyttää mallipohjaisia sovelluksia.

Seuraavaksi katsotaan, mitä tapahtuu, kun Iisakki lisää reaaliaikaisen työnkulun mukautettuun entiteettiin, jota sekä Paula että Iisakki käyttävät sovelluksissaan.

Paula ja Iisakki tarvitsevat seuraavat käyttöoikeudet:
* Paula tarvitsee yhä PowerApps Plan 1 -käyttöoikeuden luodakseen pohjaan perustuvia sovelluksia CDC for Appsia käyttäen.

* Iisakki tarvitsee yhä PowerApps Plan 2 -käyttöoikeuden luodakseen mallipohjaisia sovelluksia.

Sovellusten käyttäjät tarvitsevat seuraavat käyttöoikeudet:
* Sovelluksen 1 käyttäjät tarvitsevat nyt PowerApps 2 -käyttöoikeuden, sillä sovellus sisältää entiteetin, jossa on reaaliaikainen työnkulku.

* Sovelluksen 2 käyttäjät tarvitsevat yhä Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365 tai Dynamics 365 Customer Engagement -sopimuksen), koska sovellus sisältää rajoitetun entiteetin. 

* Sovelluksen 3 käyttäjät tarvitsevat yhä PowerApps Plan 2 -käyttöoikeuden, koska sovellus on mallipohjainen.

* Sovelluksen 4 käyttäjät tarvitsevat yhä Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365 tai Dynamics 365 Customer Engagement -sopimuksen), koska sovellus sisältää rajoitetun entiteetin.

    Dynamics 365 for Customer Service -sopimus sisältää PowerApps Plan 2 -käyttöoikeuden, joka antaa käyttäjien käyttää mallipohjaisia sovelluksia.

Ainoa sovellus, johon tämä muutos vaikuttaa, on sovellus 1, joka vaati aikaisemmin PowerApps Plan 1 -käyttöoikeuden ja nyt vaatii PowerApps Plan 2 -käyttöoikeuden, koska se sisältää entiteetin, joka käyttää monitasoista liiketoimintalogiikkaa. 

## <a name="licensing"></a>Käyttöoikeudet
Katso lisätietoja PowerAppsin ja Dynamics 365 -käyttöoikeuksista kohdasta [Käyttöoikeuksien yleiskuvaus](../../administrator/pricing-billing-skus.md).
