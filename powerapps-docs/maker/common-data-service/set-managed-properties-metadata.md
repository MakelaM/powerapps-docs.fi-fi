---
title: Hallittujen ominaisuuksien määrittäminen Common Data Service for Appsin metatiedoissa | MicrosoftDocs
description: Opi määrittämään hallittuja ominaisuuksia ratkaisun metatietokohteille
ms.custom: ''
ms.date: 05/30/2018
ms.reviewer: ''
ms.service: crm-online
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
ms.openlocfilehash: 46727f5a46e3fd518da52fac7d08a6e43992c00d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39676472"
---
# <a name="set-managed-properties-in-common-data-service-for-apps-metadata"></a>Hallittujen ominaisuuksien määrittäminen Common Data Service for Appsin metatiedoissa 

Hallitut ominaisuudet ovat voimassa vain, kun sisällytät metatietoja hallittuun ratkaisuun ja tuot sen toiseen ympäristöön. Näiden asetusten avulla ratkaisun tekijä voi jossain määrin hallita sitä, minkä tasoisen mukauttamisen hän sallii hallitun ratkaisunsa asentaville käyttäjille. 

> [!TIP]
> On yleensä hyvä ajatus antaa ihmisten laajentaa metatietoja ratkaisussasi, joka käyttää yritystietoja. Näin he voivat mukauttaa ratkaisuasi tarpeidensa mukaan samalla tavalla kuin vakioentiteettejä.
>
>Mukautusmahdollisuuksia kannattaa yleensä rajoittaa niille metatiedoille, jotka mahdollistavat ratkaisuasi tukevia toimintoja, mutta jotka eivät sisällä yritystietoja.

Hallittujen ominaisuuksien määrittäminen on tehtävä ratkaisunhallinnassa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="entity-managed-properties"></a>Entiteetin hallitut ominaisuudet

Valitse entiteetti [entiteettinäkymästä](create-edit-entities-solution-explorer.md#view-entities) ja valitse sitten **Hallitut ominaisuudet** valikkoriviltä.  Tämä avaa **Hallittujen ominaisuuksien määrittäminen** -valintaikkunan.

![Määritä entiteetin hallitut ominaisuudet](media/set-managed-properties.png)
  
Entiteeteissä on enemmän hallittuja ominaisuuksia kuin missään muissa ratkaisun osissa. Jos entiteettiä voidaan mukauttaa, voit määrittää seuraavat vaihtoehdot:  

|Vaihtoehto|Kuvaus|
|--|--|
|**Voi mukauttaa** |Hallinnoi kaikkia muita asetuksia. Jos asetuksen arvo on `False`, mitkään muut asetukset eivät ole käytössä. Kun sen arvo on `True`, voit määrittää muut mukautusasetukset. Kun sen arvo on `False`, kaikki muut asetukset ovat false-tilassa.|
|**Näyttönimeä voi muokata**|Määrittää, voinko entiteetin näyttönimeä muokata.|
|**Voi muuttaa lisäominaisuuksia** |Koskee kaikkea, mitä ei ole määritetty muissa vaihtoehdoissa.|
|**Uusia lomakkeita voidaan luoda**|Määrittää, voidaanko uusia lomakkeita luoda entiteetille.|
|**Uusia kaavioita voidaan luoda**|Määrittää, voidaanko uusia kaavioita luoda entiteetille.|
|**Uusia näkymiä voidaan luoda** |Määrittää, voidaanko uusia näkymiä luoda entiteetille.|
|**Voi muuttaa hierarkkista suhdetta**|Määrittää, voiko hierarkkisia suhdeasetuksia muuttaa. Lisätietoja: [Hierarkkisten tietojen määrittäminen ja kyselyjen tekeminen](define-query-hierarchical-data.md)|
|**Voidaanko muutosten seuranta ottaa käyttöön** |Määrittää, voidaanko entiteetin **Muutosten seuranta** -ominaisuus muuttaa.|
|**Voi ottaa käyttöön synkronoinnin ulkoisiin hakuindekseihin** |Määrittää, voidaanko entiteetti määrittää käyttämään osuvuushakua. Lisätietoja: [Määritä osuvuushaku hakutulosten ja suorituskyvyn parantamiseksi](/dynamics365/customer-engagement/admin/configure-relevance-search-organization) |

## <a name="field-managed-properties"></a>Kentän hallitut ominaisuudet

Saat lisätietoja kenttien muokkaamisesta kohdasta [Common Data Service for Appsin kenttien luominen ja muokkaaminen PowerAppsin ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md).

Valitse [kenttänäkymästä](create-edit-field-solution-explorer.md#view-fields) mukautettu kenttä hallitsemattomalle ratkaisulle ja valitse sitten **Lisää toimintoja** >  **Hallitut ominaisuudet** valikkoriviltä.

![Näytä kentän hallitut ominaisuudet](media/view-field-managed-properties-solution-explorer.png)  
  
Tämä avaa **Hallittujen ominaisuuksien määrittäminen** -valintaikkunan.

![Määritä kentän hallitut ominaisuudet](media/set-field-managed-property.png)

**Voi mukauttaa** -asetus koskee kaikkia muita asetuksia. Jos asetuksen arvo on **False**, mitkään muut asetukset eivät ole käytössä. Kun sen arvo on **True**, voit määrittää muut mukautusasetukset.  
  
Jos kenttää voi mukauttaa, voit määrittää seuraavien asetusten arvoksi **True** tai **False**.  
  
- **Näyttönimeä voi muokata**
- **Voi muuttaa vaatimustasoa** 
- **Voit muuttaa lisäominaisuuksia** : Tämä ominaisuus ohjaa kaikkia muita mukautuksia, joilla ei ole tiettyä hallittua ominaisuutta.

Jos kaikki yksittäiset asetukset asetetaan **False**-tilaan, se vastaa **Voi mukauttaa** -asetusta **False**.  

Ota valinnat käyttöön ja sulje valintaikkuna valitsemalla **Määritä**.

> [!NOTE]
> Jos kenttä on **Päivämäärä ja aika** -kenttä, myös **Voi muuttaa päivämäärän ja ajan toimintaa** -ominaisuus on käytettävissä. Lisätietoja: [Päivämäärä ja aika -kentän toiminta ja muoto](behavior-format-date-time-field.md)

## <a name="relationship-managed-properties"></a>Suhteen hallitut ominaisuudet

Valitse entiteetin suhdenäkymästä suhde hallitsemattomasta ratkaisusta ja valitse sitten **Lisää toimintoja** > **Hallitut ominaisuudet** valikkoriviltä.
  
Suhteissa ainoa hallittu ominaisuus on **Voi mukauttaa**. Tämä yksittäinen asetus hallitsee kaikkia muutoksia, joita voi tehdä entiteettisuhteeseen. 


### <a name="see-also"></a>Katso myös

[Hallitut ominaisuudet](solutions-overview.md#managed-properties)<br />
[Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-entities-solution-explorer.md)<br />
[Common Data Service for Appsin kenttien luominen ja muokkaaminen PowerAppsin ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md)<br />
[1:N (yksi moneen)- tai N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md)<br />
[N:N (monta-moneen) -entiteettisuhteiden luominen Common Data Service for Appsissa ratkaisunhallinnan avulla](create-edit-nn-relationships-solution-explorer.md)