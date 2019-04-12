---
title: Entiteettien luominen ja muokkaaminen PowerApps-portaalin avulla | MicrosoftDocs
description: Tietoja entiteettien luomisesta ja muokkaamisesta PowerApps-portaalin avulla
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
author: Mattp123
ms.assetid: fa04f99d-a5f9-48cb-8bfb-f0f50718ccee
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-and-edit-entities-using-powerapps-portal"></a>Entiteettien luominen ja muokkaaminen PowerApps-portaalin avulla

[PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) on helppo luoda ja muokata Common Data Servicen entiteettejä.

Portaalin avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. Lisätietoja: 
- [Common Data Servicen entiteettien luominen ja muokkaaminen](create-edit-entities.md)
- [Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-entities-solution-explorer.md)

## <a name="view-entities"></a>Entiteettien tarkasteleminen

1. Valitse [PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) joko **Mallipohjainen**- tai **Kaavio**-suunnittelutila.
2. Valitse **Tiedot** > **Entiteetit**

![Entiteettien tarkasteleminen](media/view-entities-portal.png)

Voit suodattaa entiteetit, jotka näkyvät luettelossa seuraavien näkymien avulla: 

![Entiteettinäkymät](media/entity-views-portal.png)

 |Näkymä|Kuvaus|
 |--|--|
 |**Kaikki**| Näyttää kaikki entiteetit|
 |**Mukautettu**|Näyttää vain mukautetut entiteetit|
 |**Oletus**|Näyttää vain vakioentiteetit |

Voit myös valita **Ryhmä**-kohdan, jos haluat ryhmitellä entiteetit niihin liitettyjen **tunnisteiden** mukaan.

## <a name="create-an-entity"></a>Entiteetin luominen

Valitse [entiteettien tarkastelemisen](#view-entities) yhteydessä valikkoriviltä **Uusi entiteetti**. Näyttöön avautuu Uusi entiteetti -paneeli.

![Uusi entiteetti -paneeli](media/new-entity-panel.png)

Anna seuraavien kenttien tiedot

|Kenttä|Kuvaus|
|--|--|
|**Näyttönimi**|Tämä on sovelluksessa näkyvä entiteetin yksikkönimi. Sen voi muuttaa myöhemmin.|
|**Monikollinen näyttönimi**|Tämä on sovelluksessa näkyvä entiteetin monikollinen nimi. Sen voi muuttaa myöhemmin.|
|**Nimi**|Kenttä täytetään valmiiksi tähän kirjoitetun **näyttönimen** perusteella. Se sisältää Common Data Servicen ratkaisunjulkaisijan mukautuksen etuliitteen. Sitä ei voi muuttaa entiteetin tallentamisen jälkeen.|
|**Kuvaus**|Anna entiteetin tarkoitukselle merkityksellinen kuvaus.|

Valitse **Seuraava**, kun haluat jatkaa. Tällöin **Uusi entiteetti** -paneeli suljetaan ja näyttöön tulee kenttäluettelo.

**Ensisijainen nimi** -kenttä on tässä vaiheessa ainoa näkyvissä oleva kenttä. Valitse **Ensisijainen nimi** -kenttä, jos haluat muuttaa kentän **näyttönimen** tai **nimen**. Oletusarvot näkyvät alla:

![Ensisijainen nimi -paneeli](media/primary-name-panel.png)

Valitse **Tallenna entiteetti**, kun haluat luoda entiteetin, tai jatka entiteetin muokkaamista.

![Entiteetin tallentaminen](media/save-entity-portal.png)

## <a name="edit-an-entity"></a>Entiteetin muokkaaminen

Valitse [entiteettien tarkastelemisen](#view-entities) yhteydessä muokattava entiteetti.

Valitse valikosta Asetukset, jos haluat muokata entiteetin **näyttönimeä**, **monikollista näyttönimeä** tai **kuvausta**.

![Entiteetin asetukset](media/entity-settings-portal.png)

Tee muiden kohteiden valinnat välilehdissä.

### <a name="fields"></a>Kentät

Katso [Kenttien luominen ja muokkaaminen](create-edit-fields.md)

### <a name="relationships"></a>Suhteet

Katso [Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)

### <a name="business-rules"></a>Liiketoimintasäännöt

Katso [Liiketoimintasääntöjen ja suositusten luonti käyttämällä lomakkeen logiikkaa](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)

### <a name="views"></a>Näkymät

Katso [Julkisen näkymän luominen tai muokkaaminen](../model-driven-apps/create-edit-views.md)

### <a name="forms"></a>Lomakkeet

Katso [Lomakkeiden luominen ja suunnittelu](../model-driven-apps/create-design-forms.md)

### <a name="dashboards"></a>Koontinäytöt

Katso [Koontinäyttöjen luominen tai muokkaaminen](../model-driven-apps/create-edit-dashboards.md)

### <a name="charts"></a>Kaaviot

Katso [Järjestelmäkaavion luominen](../model-driven-apps/create-edit-system-chart.md)

### <a name="keys"></a>Avaimet

Katso [Tietueisiin viittaavien vaihtoehtoisten avainten määrittäminen](define-alternate-keys-reference-records.md)

### <a name="data"></a>Tiedot

Tarkastele entiteetin tietoja.
Valitse **Valitse näkymä** -valikko, jos haluat valita entiteetn käytettävissä olevista näkymistä tai näyttää kaikki kentät.

![Näkymän valitseminen](media/entity-data-select-view.png)

Voit katsella lisätietoja lomakkeen alaosassa olevien **Seuraava sivu**- ja **Edellinen sivu** -komentojen avulla.

## <a name="delete-an-entity"></a>Entiteetin poistaminen

Koska sinulla on järjestelmänvalvojan käyttöoikeusrooli, voit poistaa mukautettuja entiteettejä, joka ei sisälly hallittuun ratkaisuun.  
  
> [!IMPORTANT]
>  Kun poistat mukautetun entiteetin, sen tiedot sisältävät tietokantataulut poistetaan ja kaikki niiden sisältämät tiedot menetetään. Myös kaikki mukautetun entiteetin kanssa ylätason suhteen omaavat liittyvät tietueet poistetaan. Lisätietoja ylätason suhteista on kohdassa [Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md).  
  
> [!NOTE]
> Poistetun entiteetin tiedot voidaan palauttaa vain palauttamalla tietokanta hetkeen ennen entiteetin poistamista. Lisätietoja: [Ilmentymien varmuuskopiointi ja palautus](/dynamics365/customer-engagement/admin/backup-restore-instances)

Valitse [entiteettien tarkastelemisen](#view-entities) yhteydessä entiteetti ja valitse sitten valikosta tai pikavalikosta **Poista entiteetti**.

![Entiteetin poistaminen PowerApps-portaalin avulla](media/delete-entity-powerapps-portal.png)

Jos entiteetillä on riippuvuuksia, jotka estävät sen poistamisen, näyttöön tulee virhesanoma. Voit tunnistaa ja poistaa mahdolliset riippuvuudet ratkaisunhallinnan avulla. Lisätietoja [Entiteetin riippuvuuksien tunnistaminen](create-edit-entities-solution-explorer.md#identify-entity-dependencies)

### <a name="see-also"></a>Katso myös

[Common Data Servicen entiteettien luominen ja muokkaaminen](create-edit-entities.md)<br />
[Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-entities-solution-explorer.md)


