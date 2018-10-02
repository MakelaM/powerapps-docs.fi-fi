---
title: Entiteettien käyttöoikeusvaatimukset | Microsoft Docs
description: Selitys Common Data Service (CDS) sovelluksille -ratkaisun entiteettien käyttöoikeusvaatimuksista.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/01/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="license-requirements-for-entities"></a>Entiteettien käyttöoikeusvaatimukset
Sovellusten tekijät voivat käyttää suurinta osaa Common Data Service (CDS) sovelluksille -ratkaisun käytettävissä olevista entiteeteistä (myös mukautettuja entiteettejä ja Common Data Model -sovelluksen osana olevia entiteettejä), kun he luovat sovelluksia ja työnkulkuja käyttäjille, joilla on PowerApps-palvelupaketin 1 tai Microsoft Flow -palvelupaketin 1 käyttöoikeus. Joissakin tapauksissa monimutkaista liiketoimintalogiikkaa sisältävät entiteetit on sidottu Dynamics 365 -sovelluksiin, jotka vaativat sovelluksen käyttäjiltä tietyn käyttöoikeuden. 


|Entiteetti    |Kuvaus    |Tarve    |
|---------|---------|---------|
|Entiteetit, jotka sisältävät monimutkaista liiketoimintalogiikkaa   | Nämä ovat entiteettejä, joissa käytetään monimutkaista palvelinpään liiketoimintalogiikkaa. Esimerkki on entiteetti, jossa käytetään reaaliaikaista työnkulkua tai koodilaajennusta.       |  [PowerApps-palvelupaketti 2](https://powerapps.microsoft.com/pricing/) tai [Flow-palvelupaketti 2](https://flow.microsoft.com/pricing/)        |
|Rajoitetut entiteetit  |  Nämä ovat entiteettejä, jotka eivät ole Common Data Service sovelluksille -ratkaisun vakioentiteettejä, mutta jotka sisältyvät Dynamics 365 Customer Engagement -sovellukseen tai kolmannen osapuolen sovellukseen. Esimerkkejä ovat tietoartikkeli, tavoite ja oikeuksien entiteetit.     |  [Dynamics 365 -palvelupaketti](https://dynamics.microsoft.com/pricing/)      | 


> [!NOTE]
> Sovellukset ja työnkulut, jotka käyttävät näitä entiteettejä, vaativat käyttäjältä soveltuvat käyttöoikeudet. Sovelluksen ja työnkulun tekijällä ja kehittäjällä ei tarvitse olla käyttöoikeuksia.

## <a name="entities-with-complex-business-logic"></a>Entiteetit, jotka sisältävät monimutkaista liiketoimintalogiikkaa
Entiteetit, jotka sisältävät seuraavaa monimutkaista palvelinpään logiikkaa, vaativat näitä entiteettejä käyttäviltä sovelluksen tai työnkulun käyttäjiltä PowerApps-palvelupaketin 2 tai Microsoft Flow -palvelupaketin 2 käyttöoikeudet:

* Koodilaajennukset (lisätietoja on kohdassa [Laajennuskehitys](https://docs.microsoft.com/dynamics365/customer-engagement/developer/plugin-development))
* Reaaliaikaiset työnkulut (lisätietoja on kohdassa [Työnkulkuprosessit](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes))

    > [!NOTE]
    >  Vain työnkulkuja, jotka on muunnettu reaaliaikaisiksi työnkuluiksi, käsitellään reaaliaikaisina ja synkronisina. Taustalla suoritettavia työnkulkuja voi yhä käyttää soveltuvan PowerApps-palvelupaketin kanssa. Ne eivät vaadi lisäkäyttöoikeuksia.

Ympäristöön määritettyjen laajennuskokoonpanojen ja työnkulkujen luettelossa on lisätietoja entiteetteihin lisätystä monimutkaisesta liiketoimintalogiikasta. Lisätietoja entiteeteistä, jotka voivat sisältää palvelunpään logiikkaa Dynamics 365 -sovelluksen asentamisen jälkeen, on kohdassa [Monimutkaiset entiteetit, jotka vaativat PowerApps-palvelupaketin 2 käyttöoikeudet](data-platform-complex-entities.md)  

### <a name="impacting-license-requirements-when-adding-complex-business-logic"></a>Käyttöoikeusvaatimukset, joihin monimutkaisen liiketoimintalogiikan lisääminen vaikuttaa
Sovellusten tekijät voivat lisätä koodilaajennuksia ja reaaliaikaisia työnkulkuja entiteetteihin CDS sovelluksille -ratkaisussa. Kun niin tehdään, käyttöönotettujen sovellusten käyttäjien käyttöoikeusvaatimukset voivat muuttua. Sovellusten tekijöiden tulee olla varovaisia, kun he lisäävät monimutkaista liiketoimintalogiikkaa entiteettiin. Tekijöiden tulee ensin tarkistaa, mitkä sovellukset käyttävät entiteettiä ja onko kyseisten sovellusten käyttäjillä vaaditut käyttöoikeudet.

## <a name="restricted-entities"></a>Rajoitetut entiteetit
Tietyt Dynamics 365 -sovellusten toimintoihin sidotut entiteetit vaativat sovellusten käyttäjiltä kyseisen sovelluksen käyttöoikeudet, jos käyttäjät haluavat luoda, päivittää tai poistaa tietueita entiteeteissä. Täydellinen rajoitettujen entiteettien luettelo on kohdassa [Rajoitetut entiteetit, jotka vaativat Dynamics 365 -käyttöoikeudet](data-platform-restricted-entities.md).

## <a name="licensing-examples"></a>Esimerkkejä käyttöoikeuksista
Barb ja Isaac luovat sovelluksia tietojen tallentamiseksi PowerAppsissa CDS sovelluksille -ratkaisun avulla.

Barb luo kaksi kaaviosovellusta:

* Sovellus 1 &ndash; käyttää Yhteyshenkilö-entiteettiä ja mukautettua entiteettiä, jotka tallentavat liittyvät tiedot
* Sovellus 2 &ndash; käyttää Yhteyshenkilö-entiteettiä ja Tapaus-entiteettiä, joka on rajoitettu entiteetti

Isaac luo mallipohjaisia sovelluksia:

* Sovellus 3 &ndash; käyttää Yhteyshenkilö-entiteettiä ja mukautettua entiteettiä, jotka tallentavat liittyvät tiedot
* Sovellus 4 &ndash; käyttää Yhteyshenkilö-entiteettiä ja Tapaus-entiteettiä, joka on rajoitettu entiteetti

Barb ja Isaac tarvitsevat seuraavat käyttöoikeudet:
* Barb tarvitsee PowerApps-palvelupaketin 1 käyttöoikeuden kaaviosovellusten luomiseksi CDS sovelluksille -ratkaisulla Jos hänen on luotava tietokanta tai mukautettu entiteetti, hän tarvitsee PowerApps-palvelupaketin 2 käyttöoikeuden.

* Isaac tarvitsee PowerApps-palvelupaketin 2 käyttöoikeuden mallipohjaisten sovellusten luomista varten.

Sovellusten käyttäjät tarvitsevat seuraavat käyttöoikeudet:
* Sovelluksen 1 käyttäjä tarvitsee vain PowerApps-palvelupaketin 1 tai palvelupaketin 2 käyttöoikeuden, koska sovelluksessa ei ole entiteettejä, jotka sisältävät monimutkaista liiketoimintalogiikkaa tai rajoitettuja entiteettejä.

* Sovelluksen 2 käyttäjät tarvitsevat Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365- tai Dynamics 365 Customer Engagement Plan -käyttöoikeuden), koska sovellus sisältää rajoitetun entiteetin.

* Sovelluksen 3 käyttäjät tarvitsevat PowerApps-palvelupaketin 2 käyttöoikeuden, koska se on mallipohjainen sovellus.

* Sovelluksen 4 käyttäjät tarvitsevat Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365- tai Dynamics 365 Customer Engagement Plan -käyttöoikeuden), koska sovellus sisältää rajoitetun entiteetin.

    Dynamics 365 for Customer Service -palvelupaketti sisältää PowerApps-palvelupaketin 2 käyttöoikeuden, jonka avulla käyttäjät voivat suorittaa mallipohjaisia sovelluksia.

Katsotaan, mitä tapahtuu, kun Isaac lisää reaaliaikaisen työnkulun mukautettuun entiteettiin, jota on käytössä sekä Barbin että Isaacin sovelluksessa.

Barb ja Isaac tarvitsevat seuraavat käyttöoikeudet:
* Barb tarvitsee yhä PowerApps-palvelupaketin 1 käyttöoikeuden kaaviosovellusten luomiseksi CDS sovelluksille -ratkaisulla

* Isaac tarvitsee yhä PowerApps-palvelupaketin 2 käyttöoikeuden mallipohjaisten sovellusten luomista varten.

Sovellusten käyttäjät tarvitsevat seuraavat käyttöoikeudet:
* Sovelluksen 1 käyttäjät tarvitsevat nyt PowerApps-palvelupaketin 2 käyttöoikeuden, koska sovellus sisältää entiteetin, jolla on reaaliaikainen työnkulku.

* Sovelluksen 2 käyttäjät tarvitsevat yhä Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365- tai Dynamics 365 Customer Engagement Plan -käyttöoikeuden), koska sovellus sisältää rajoitetun entiteetin. 

* Sovelluksen 3 käyttäjät tarvitsevat yhä PowerApps-palvelupaketin 2 käyttöoikeuden, koska se on mallipohjainen sovellus.

* Sovelluksen 4 käyttäjät tarvitsevat yhä Dynamics 365 for Customer Service, Enterprise edition -käyttöoikeuden (tai Dynamics 365- tai Dynamics 365 Customer Engagement Plan -käyttöoikeuden), koska sovellus sisältää rajoitetun entiteetin.

    Dynamics 365 for Customer Service -palvelupaketti sisältää PowerApps-palvelupaketin 2 käyttöoikeuden, jonka avulla käyttäjät voivat suorittaa mallipohjaisia sovelluksia.

Ainoa sovellus, johon tämä muutos vaikuttaa, on sovellus 1. Aikaisemmin sen käyttäminen edellytti PowerApps-palvelupaketin 1 käyttöoikeutta, mutta nyt edellytyksenä on PowerApps-palvelupaketin 2 käyttöoikeus, koska se sisältää entiteetin, jolla on monimutkaista liiketoimintalogiikkaa. 

## <a name="more-about-licensing"></a>Lisätietoja käyttöoikeuksista
Lisätietoja PowerApps- ja Dynamics 365 -käyttöoikeuksista on kohdassa [Käyttöoikeuksien yleiskatsaus](../../administrator/pricing-billing-skus.md).
