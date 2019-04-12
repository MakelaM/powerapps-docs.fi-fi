---
title: Hallittujen ominaisuuksien määrittäminen Common Data Servicen metatiedoissa | MicrosoftDocs
description: Tietoja metatietojen kohteiden hallittujen ominaisuuksien määrittämisestä ratkaisussa
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: edaa7d4a-a95f-4d66-a9d9-2ad6051332f7
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-managed-properties-in-common-data-service-metadata"></a>Hallittujen ominaisuuksien määrittäminen Common Data Servicen metatiedoissa 

Hallitut ominaisuudet ovat käytössä vain, kun hallitussa ratkaisussa on metatietoja ja se tuodaan toiseen ympäristöön. Näiden asetusten avulla ratkaisun tekijä pystyy jonkin verran hallitsemaan sitä, kuinka paljon hallittua ratkaisua käyttävät henkilöt voivat tehdä mukautuksia. 

> [!TIP]
> Yleensä kannattaa antaa henkilöille metatietojen laajentamisen oikeudet ratkaisussa, joka käsittelee liiketoimintatietoja. Tällöin he voivat räätälöidä ratkaisua tarpeitaan vastaavaksi samalla tavalla kuin vakioentiteettejä.
>
>Niiden metatietojen mukautuksia kannattaa rajoittaa, jotka tarjoavat ratkaisua tukevia toimintoja, mutta jotka eivät sisällä liiketoimintatietoja.

Hallittujen ominaisuuksien määrittäminen on tehtävä ratkaisunhallinnan avulla.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="entity-managed-properties"></a>Entiteetin hallitut ominaisuudet

Valitse [entiteettien tarkastelemisen](create-edit-entities-solution-explorer.md#view-entities) yhteydessä entiteetti ja valitse sitten valikkoriviltä **Hallitut ominaisuudet**.  Näyttöön tulee **Määritä hallitut ominaisuudet** -valintaikkuna.

![Entiteetin hallittujen ominaisuuksien määrittäminen](media/set-managed-properties.png)
  
Entiteeteillä on useampia hallittuja ominaisuuksia kuin muun tyyppisillä osilla. Jos entiteetin voi mukauttaa, voit määrittää seuraavat asetukset:  

|Asetus|Kuvaus|
|--|--|
|**On mukautettavissa** |Ohjaa kaikkia muita asetuksia. Jos asetukseksi on valittu `False`, muita asetuksia ei voi käyttää. Kun asetukseksi on valittu `True`, voit määrittää muita mukautettuja asetuksia. Kun arvo on `False`, se vastaa kaikkien muiden asetusten määrittämistä epätosiksi.|
|**Näyttönimeä voi muokata**|Määrittää, voiko entiteetin näyttönimeä muokata.|
|**Voi muuttaa lisäominaisuuksia** |Koskee kaikkia asetuksia, joita muut asetukset eivät kata.|
|**Uusia lomakkeita voi luoda**|Määrittää, voiko entiteetille luoda uusia lomakkeita.|
|**Uusia kaavioita voi luoda**|Määrittää, voiko entiteetille luoda uusia kaavioita.|
|**Uusia näkymiä voi luoda** |Määrittää, voiko entiteetille luoda uusia näkymiä.|
|**Hierarkkista suhdetta voi muuttaa**|Määrittää, voiko hierarkkisten suhteiden asetuksia muuttaa. Lisätietoja: [Hierarkkisesti järjestettyjen tietojen määrittäminen ja kysely](define-query-hierarchical-data.md)|
|**Voiko muutoksien seuranta olla käytössä** |Määrittää, voiko entiteetin **Muuta seurantaa** -ominaisuutta muuttaa.|
|**Voi ottaa käyttöön synkronoinnin ulkoiseen hakuindeksiin** |Määrittää, voiko entiteetin määrittää niin, että osuvuushaku on käytössä. Lisätietoja: [Hakutulosten tehostaminen ja parantaminen osuvuushaun määrittämisen avulla](/dynamics365/customer-engagement/admin/configure-relevance-search-organization) |

## <a name="field-managed-properties"></a>Kentän hallitut ominaisuudet

Lisätietoja kenttien muokkaamisesta on kohdassa [Common Data Servicen kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md).

Valitse [kenttien tarkastelemisen](create-edit-field-solution-explorer.md#view-fields) yhteydessä hallitsemattoman ratkaisun mukautettu kenttä ja valitse sitten valikkoriviltä **Lisää toimintoja** >  **Hallitut ominaisuudet**.

![Kentän hallittujen ominaisuuksien tarkasteleminen](media/view-field-managed-properties-solution-explorer.png)  
  
Näyttöön tulee **Määritä hallitut ominaisuudet** -valintaikkuna.

![Kentän hallittujen ominaisuuksien määrittäminen](media/set-field-managed-property.png)

**Voi mukauttaa** -asetus hallitsee kaikkia muita asetuksia. Jos asetukseksi on valittu **Epätosi**, muita asetuksia ei voi käyttää. Kun asetukseksi on valittu **Tosi**, voit määrittää muita mukautettuja asetuksia.  
  
Jos kenttää voi mukauttaa, määritä seuraavien asetuksen arvoiksi **Tosi** tai **Epätosi**.  
  
- **Näyttönimeä voi muokata**
- **Voi muuttaa vaatimustasoa** 
- **Voi muuttaa lisäominaisuuksia** : Tämä ominaisuus hallitsee mukautuksia, joilla ei ole erityistä hallittua ominaisuutta.

Kaikkien yksittäisten asetusten arvon määrittäminen **Epätosi**-arvoksi on sama kuin **Voi mukauttaa** -kohdan arvon määrittäminen arvoksi **Epätosi**.  

Tee valinnat ja sulje valintaikkuna valitsemalla **Määritä**.

> [!NOTE]
> Jos kenttä on **päivämäärän ja ajan** kenttä, **Voi muuttaa päivämäärien ja kellonaikojen toimintatapaa** -lisäominaisuus on käytettävissä. Lisätietoja. [Päivämäärä ja aika -kentän toimintatapa ja muoto](behavior-format-date-time-field.md)

## <a name="relationship-managed-properties"></a>Suhteen hallitut ominaisuudet

Valitse entiteettisuhteiden tarkastelemisen yhteydessä hallitsemattoman ratkaisun suhde ja valitse sitten valikkoriviltä **Lisää toimintoja** > **Hallitut ominaisuudet**.
  
Suhteilla on vain yksi hallittu ominaisuus: **Voidaan mukauttaa**. Tämä asetus hallitsee kaikkia muutoksia, joita entiteettisuhteelle voidaan tehdä. 


### <a name="see-also"></a>Katso myös

[Hallitut ominaisuudet](solutions-overview.md#managed-properties)<br />
[Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-entities-solution-explorer.md)<br />
[Common Data Servicen kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md)<br />
[N:N (monta moneen) -entiteettisuhteiden luominen Common Data Servicessä ratkaisunhallinnan avulla](create-edit-nn-relationships-solution-explorer.md)
