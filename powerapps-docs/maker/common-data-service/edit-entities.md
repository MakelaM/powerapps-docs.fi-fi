---
title: Entiteetin muokkaaminen PowerAppsilla | MicrosoftDocs
description: 'Opettele eri tavat, joilla entiteetin voi muokata'
ms.custom: ''
ms.date: 05/15/2018
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
ms.assetid: 8b00780c-74f0-4e3a-b570-b9289d0d5383
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="edit-an-entity"></a>Entiteetin muokkaaminen

Voit muokata mitä tahansa luomaasi entiteettiä. Vakioentiteeteillä tai hallituilla mukautetuilla entiteeteillä voi olla muutoksia koskevia rajoituksia.  
  
> [!NOTE]
> **Vakioentiteetit** ovat yleisiä entiteettejä, jotka kuuluvat ympäristöön. Ne eivät ole **järjestelmäentiteettejä** tai **mukautettuja** entiteettejä. Järjestelmään hallitun ratkaisun tuonnin avulla lisätyt entiteetit ovat *hallittuja mukautettuja entiteettejä*. Kullekin entiteetille määritetyt hallitut ominaisuudet määrittävät, miten paljon entiteettiä voi muokata. Ominaisuudet, joita ei voi muokata, poistetaan käytöstä. 

Entiteettiä voi muokata kahdella seuraavalla tavalla suunnitteluohjelmassa:

|Suunnittelija|Kuvaus|
|--|--|
|[PowerApps-portaali](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Tarjoaa helpon ja nopean käyttökokemuksen, mutta jotkin erityisasetukset eivät ole käytettävissä.|
|Ratkaisunhallinta|Tämä ei ole niin helppo tapa, mutta tarjoaa enemmän joustavuutta vähemmän yleisille vaatimuksille.|

Sekä PowerApps-portaalissa että ratkaisunhallinnassa voidaan tehdä seuraavat toiminnot:

- **Muokkaa entiteettikenttiä**. Lisätietoja: [Kenttien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-fields.md)
  
- **Muokkaa entiteettisuhteita**. Lisätietoja: [Suhteiden luominen ja niiden muokkaaminen entiteettien välillä](create-edit-entity-relationships.md)

- **Avaimet**. [Tietueisiin viittaavien vaihtoehtoisten avainten määrittäminen](define-alternate-keys-reference-records.md)
  
Voit tehdä muutoksia myös entiteettiä tukeviin tietueisiin.  

- **Liiketoimintasäännöt** Lisätietoja: [Liiketoimintasääntöjen ja suositusten luonti käyttämällä lomakkeen logiikkaa](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

- **Näkymät**. Lisätietoja: [Näkymän luominen tai muokkaaminen](../model-driven-apps/create-edit-views.md)
  
- **Lomakkeet**. Lisätietoja: [Lomakkeiden luominen ja suunnittelu](../model-driven-apps/create-design-forms.md)

- **Koontinäytöt**. Lisätietoja: [Koontinäyttöjen luominen tai muokkaaminen](../model-driven-apps/create-edit-dashboards.md)

- **Kaaviot**. [Järjestelmäkaavion luominen tai muokkaaminen](../model-driven-apps/create-edit-system-chart.md)

## <a name="edit-using-powerapps-portal-designer"></a>Muokkaaminen PowerApps-portaalin suunnitteluohjelman avulla

PowerApps-portaalin suunnitteluohjelmassa on vain seuraavat kolme muokattavaa entiteetin ominaisuutta:
 - Näyttönimi
 - Monikollinen näyttönimi
 - Kuvaus

Valitse suunnitteluohjelmassa muokattava entiteetti ja avaa entiteetin suunnitteluohjelma napsauttamalla. Voit muokata entiteetin ominaisuuksia valitsemalla **Asetukset**-komennon. Sen jälkeen näyttöön tulee **Muokkaa entiteettiä** -lomake alla esitetyllä tavalla:

![Entiteetin ominaisuuksien muokkaaminen](media/edit-entity-properties-powerapps-portal-designer.png)

> [!NOTE]
>  Useiden vakioentiteettien nimiä voidaan käyttää myös sovelluksen muissa teksteissä. Lisätietoja niiden kohtien etsimisestä, joissa tekstiä on käytetty, ja tekstin muuttamisesta on ohjeaiheessa [Vakioentiteettisanomien muokkaaminen](edit-system-entity-messages.md).

Kaikki muut entiteettiasetusten muutokset on tehtävä ratkaisunhallinnassa.

## <a name="edit-using-solution-explorer"></a>Muokkaaminen ratkaisunhallinnan avulla

Kun entiteettiä muokataan ratkaisunhallinnan avulla, siihen lisättävä hallitsematon ratkaisu on etsittävä.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
<a name="BKMK_ChangeEntityName"></a> 
  
## <a name="change-the-name-of-an-entity"></a>Entiteetin nimen muuttaminen  

Käytä sovelluksen entiteetin nimen muuttamisessa **Näyttönimi**- ja **Monikkonimi**-ominaisuuksia. 

> [!NOTE]
>  Useiden vakioentiteettien nimiä voidaan käyttää myös sovelluksen muissa teksteissä. Lisätietoja niiden kohtien etsimisestä, joissa tekstiä on käytetty, ja tekstin muuttamisesta on ohjeaiheessa [Vakioentiteettisanomien muokkaaminen](edit-system-entity-messages.md).
  
<a name="BKMK_ChangeEntityIcon"></a>   

###  <a name="change-the-icons-used-for-custom-entities"></a>Mukautettujen entiteettien kuvakkeiden muuttaminen  

Oletusarvoisesti kaikilla WWW-sovelluksen mukautetuilla entiteeteillä on sama kuvake. Voit luoda kuvan WWWresursseja kuvakkeille, jotka haluat mukautetuille entiteeteille. Lisätietoja: [Mukautettujen entiteettien kuvakkeiden muuttaminen](../model-driven-apps/change-custom-entity-icons.md).  
  
<a name="BKMK_EnableOptions"></a>  
 
###  <a name="entity-options-that-can-only-be-enabled"></a>Entiteetin asetukset, jotka voi ainoastaan ottaa käyttöön  

Seuraavassa taulukossa luetellaan entiteetin vaihtoehdot, jotka voi ottaa käyttöön, mutta joita ei voi poistaa käytöstä kohteiden käyttöönoton jälkeen.  

[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)] 
  
<a name="BKMK_EnableDisableOptions"></a>  
 
###  <a name="enable-or-disable-entity-options"></a>Entiteetin asetusten ottaminen käyttöön tai poistaminen käytöstä  

Seuraavassa taulukossa luetellaan entiteetin asetukset, jotka voi ottaa käyttöön tai poistaa käytöstä milloin tahansa.  

[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)] 

### <a name="see-also"></a>Katso myös

[Entiteetin luominen](create-edit-entities.md)<br />
[Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-entities-solution-explorer.md)
