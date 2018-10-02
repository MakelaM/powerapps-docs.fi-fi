---
title: 'Yhteenveto 1:N (yksi moneen)- tai N:1 (monta yhteen) -entiteettisuhteiden luomisesta PowerAppsissa | MicrosoftDocs'
description: Tietoja yksi moneen- tai monta yhteen -entiteettisuhteiden luomisesta
ms.custom: ''
ms.date: 05/27/2018
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
ms.assetid: 52c00707-b2bc-4950-abec-89baefd94f6e
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-one-to-many-or-many-to-one-entity-relationships-overview"></a>Yksi moneen- tai monta yhteen -entiteettisuhteiden luomisen yhteenveto

Määritä, miten Common Data Service sovelluksille -ratkaisun 1:N (yksi moneen)- tai N:1 (monta yhteen) -suhteiden kaksi entiteettiä liittyvät toisiinsa. 
  
Arvioi ennen mukautetun entiteettisuhteen luomista, vastaako jokin aiemmin luotu entiteettisuhde vaatimuksiasi. <br />Lisätietoja: [Luodaanko uusia metatietoja vai käytetäänkö olemassa olevia metatietoja?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

1:N (yksi moneen)- tai N:1 (monta yhteen) -suhteita voi luoda ja muokata kahden seuraavan suunnitteluohjelman avulla:

|Suunnittelija| Kuvaus|
|--|--|
|[PowerApps-portaali](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Tarjoaa helpon ja nopean käyttökokemuksen, mutta jotkin erityisasetukset eivät ole käytettävissä.<br />Lisätietoja: [1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen PowerApps-portaalissa](create-edit-1n-relationships-portal.md)|
|Ratkaisunhallinta|Tämä ei ole niin helppo tapa, mutta tarjoaa enemmän joustavuutta vähemmän yleisille vaatimuksille. <br />Lisätietoja: [1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md) |

> [!NOTE]
> Voit luoda myös uuden entiteettisuhteen ympäristössä seuraavasti:
> - Valitse mallipohjaisissa sovelluksissa **Uusi kenttä** lomake-editorissa ja luo *hakukenttä*. <br />Lisätietoja: [Kentän lisääminen lomakkeeseen](../model-driven-apps/add-field-form.md)
> - Luo liittyvälle entiteetille uusi hakukenttä. <br />Lisätietoja: [Kenttien luominen ja muokkaaminen](create-edit-fields.md)
> - Tuo ratkaisu, joka sisältää entiteettisuhteen määrityksen. <br />Lisätietoja: [Ratkaisujen tuominen. päivittäminen ja vieminen](import-update-export-solutions.md)
> - Luo uusia entiteettejä Power Queryn avulla ja anna niiden tiedot. <br />Lisätietoja: [Tietojen lisääminen Common Data Service sovelluksille -ratkaisun entiteettiin Power Queryn avulla](data-platform-cds-newentity-pq.md).
> - Sovelluskehittäjä voi käyttää [WWW-palveluita](../../developer/common-data-service/use-web-services.md#metadata-services) ohjelman kirjoittamisessa entiteettisuhteiden luomista ja päivittämistä varten. <br />Lisätietoja: [Entiteettisuhteen metatietojen mukauttaminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)

Tämän ohjeaiheen tietojen avulla voit valita käytettävän suunnitteluohjelman. 

Käytä PowerApps-portaalia 1:N (yksi moneen)- tai N:1 (monta yhteen) -entiteettisuhteiden luomiseen ja muokkaamiseen, jos seuraavia vaatimuksia ei tarvitse ottaa huomioon:

- Kenttien yhdistämismääritysten määrittäminen
- Siirtymisruudun asetusten määrittäminen mallipohjaiselle sovellukselle
- Suhteen toimintatapojen määrittäminen
- Määritä, piilotetaanko suhde erikoishaussa.
- Hierarkkinen suhteen tekeminen


## <a name="community-tools"></a>Yhteisön työvälineet

**[Entiteettisuhteen kaavion tekijä](https://www.xrmtoolbox.com/plugins/JourneyIntoCRM.XrmToolbox.ERDPlugin/)** on työkalu, jonka XrmToolbox-yhteisö kehitti CDS sovelluksille -ratkaisua varten. Lisätietoja yhteisön kehittämistä työkaluista on kohdassa [Common Data Service sovelluksille -ratkaisun sovelluskehittäjän työkalut](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools).

> [!NOTE]
> Yhteisön työkalut eivät ole Microsoftin tuotteita eivätkä laajenna tuen yhteisön työkaluille. Jos sinulla on kysymyksiä työkalusta, ota yhteyttä julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com).

### <a name="see-also"></a>Katso myös

[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen PowerApps-portaalissa](create-edit-1n-relationships-portal.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md)<br />
[Sovelluskehittäjän dokumentaatio: Entiteettisuhteen metatietojen mukauttaminen](/dynamics365/customer-engagement/developer/customize-entity-relationship-metadata)<br />
[Sovelluskehittäjän dokumentaatio: Entiteettisuhteen kelpoisuus](/dynamics365/customer-engagement/developer/entity-relationship-eligibility)


