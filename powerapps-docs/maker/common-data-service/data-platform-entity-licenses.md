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
ms.openlocfilehash: 4350f7141adf0fbce3e74271d6aff48c18c857e2
ms.sourcegitcommit: 2bcc36916f0c591466eb3e007c2d30b99f2315c6
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/09/2018
ms.locfileid: "40009255"
---
# <a name="license-requirements-for-entities"></a>Entiteettien käyttöoikeusvaatimukset
Sovellusten tekijät voivat käyttää useimpia Common Data Service (CDC) for Appsin sisältämiä entiteettejä (mukaan lukien mukautetut entiteetit ja Common Data Modelin mukaiset entiteetit) sovellusten ja työnkulkujen luomiseen käyttäjille, joilla on PowerApps Plan 1 tai Microsoft Flow Plan 1. Joissakin tapauksissa entiteetit sisältävät monimutkaista liiketoimintalogiikkaa tai ovat sidoksissa Dynamics 365 -sovelluksiin, jotka vaativat, että sovelluksen käyttäjillä on tietty käyttöoikeus. 


|Entiteetti    |Kuvaus    |Vaatimus    |
|---------|---------|---------|
|Entiteetit, joilla on monimutkainen liiketoimintalogiikka   | Nämä ovat entiteettejä, jotka käyttävät monimutkaista palvelinpuolen liiketoimintalogiikkaa. Esimerkiksi mikä tahansa entiteetti, joka käyttää reaaliaikaista työnkulkua tai koodin laajennusta.       |  [Powerappsin palvelupaketti 2](https://powerapps.microsoft.com/pricing/) tai [Työnkulkupalvelupaketti 2](https://flow.microsoft.com/pricing/)        |
|Rajoitetut entiteetit  |  Nämä ovat entiteettejä, jotka eivät ole vakiona Common Data Service for Appsissa, mutta sisältyvät Dynamics 365 customer engagement -sovellukseen tai kolmannen osapuolen ratkaisuun. Esimerkiksi knowledge article-, goal- ja entitlement-entiteetit.     |  [Dynamics 365 -palvelupaketti](https://dynamics.microsoft.com/pricing/)      | 


> [!NOTE]
> Sovellukset ja työnkulut, jotka käyttävät näitä entiteettejä, edellyttävät sovelluksen ja työnkulun käyttäjältä asianmukaista käyttöoikeutta, eivät sovelluksen tai työnkulun tekijältä tai kehittäjältä.

## <a name="entities-with-complex-business-logic"></a>Entiteetit, joilla on monimutkainen liiketoimintalogiikka
Seuraavia monimutkaisia, palvelimen logiikkaa sisältävät entiteetit vaativat näitä entiteettejä käyttävien sovellusten tai työnkulkujen käyttäjillä PowerApps Plan 2- tai Microsoft Flow Plan 2 -sopimuksen:

* Koodilaajennukset (lisätietoja on artikkelissa [Laajennusten kehittäminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Reaaliaikainen työnkulut (lisätietoja on artikkelissa [Työnkulkuprosessit](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!NOTE]
    >  Vain työnkulkuja, jotka on muunnettu reaaliaikaisiksi työnkuluiksi, pidetään reaaliaikaisina ja synkronoituina. Työnkulkuja, jotka suoritetaan taustalla, voidaan silti käyttää asianmukaisen PowerApps-palvelupaketin osana, eivätkä ne vaadi muita käyttöoikeuksia.

Jos haluat tietää, onko entiteeteissäsi monitasoista liiketoimintalogiikkaa, tarkista laajennuksen kokoonpanojen ja ympäristössäsi määriteltyjen työnkulkujen luettelo. Niiden entiteettien luettelo, jotka saattavat sisältää palvelinpuolen logiikkaa Dynamics 365 -sovelluksen asentamisen jälkeen, on kohdassa [Monimutkaiset entiteetit, jotka vaativat PowerAppsin palvelupaketin 2 käyttöoikeuksia](data-platform-complex-entities.md)  

### <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Käyttöoikeusvaatimusvaikutukset monitasoista liiketoimintalogiikkaa lisättäessä
Sovellusten tekijät voivat lisätä koodilaajennuksia ja reaaliaikaisia työnkulkuja sisältäviä entiteettejä CDC for Appsiin, mutta tämä saattaa muuta jo kehitettyjen sovellusten käyttäjien käyttöoikeusvaatimuksia. Sovellusten tekijöiden tulee olla varovaisia lisätessään monitasoista liiketoimintalogiikkaa entiteettiin ja tarkistaa ensin, mitkä sovellukset käyttävät entiteettiä ja onko kyseisten sovellusten käyttäjillä tarvittavat käyttöoikeudet.

## <a name="restricted-entities"></a>Rajoitetut entiteetit
Tietyt entiteetit, jotka on sidottu Dynamics 365 -sovellusten toiminnallisuuteen, vaativat, että sovellusten käyttäjillä on vastaava sovelluksen käyttöoikeus, jos he haluavat luoda, päivittää tai poistaa tietueita entiteettien sisältä. Katso lista rajoitetuista entiteeteistä kohdasta [Rajoitetut entiteetit, jotka vaativat Dynamics 365 -käyttöoikeuksia](data-platform-restricted-entities.md).

## <a name="licensing-examples"></a>Esimerkkejä käyttöoikeuksista
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

## <a name="more-about-licensing"></a>Lisätietoja käyttöoikeuksista
Katso lisätietoja PowerAppsin ja Dynamics 365 -käyttöoikeuksista kohdasta [Käyttöoikeuksien yleiskuvaus](../../administrator/pricing-billing-skus.md).
