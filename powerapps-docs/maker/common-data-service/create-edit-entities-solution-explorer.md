---
title: Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla | MicrosoftDocs
description: Tietoja entiteetin luomisesta ratkaisunhallinnan avulla
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
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-and-edit-entities-using-solution-explorer"></a>Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla

Voit helposti luoda entiteetin useimmissa tavallisissa tilanteissa PowerApps-portaalin avulla. Kaikkia ominaisuuksia ei kuitenkaan ole otettu käyttöön. Jos kohdassa [Entiteettien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-entities.md) mainitut vaatimukset on täytettävä, saavutat ne luomalla tai muokkaamalla entiteettejä ratkaisunhallinnan avulla.

## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luomasi entiteetin nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle entiteetille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entities"></a>Entiteettien tarkasteleminen

Valitse ratkaisunhallinnan **Osat**-solmussa **Entiteetit**-solmu.

![Ratkaisunhallinnan entiteettien tarkasteleminen](media/view-entities-solution-explorer.png)

## <a name="create-an-entity"></a>Entiteetin luominen

Valitse [entiteettien tarkastelemisen](#view-entities) yhteydessä **Uusi** ja avaa uusi entiteettilomake.

![ratkaisunhallinnan uusi entiteettilomake](media/new-entity-form-solution-explorer.png)

Uudessa entiteettilomakkeessa on kaksi välilehteä. **Yleiset**-välilehti sisältää entiteetin asetukset. **Ensisijainen kenttä** -välilehti sisältää asetukset yhdestä tekstirivin kentästä, joka jokaisella entiteetillä on. Se määrittää tekstin, joka näkyy, jos entiteetin hakukentässä avaava linkki on olemassa.

Seuraavassa on lisätietoja kustakin osasta:
- [Ensisijaisen kentän määrittäminen](#configure-the-primary-field)
- [Pakollisten kenttien määrittäminen](#configure-required-fields)

> [!NOTE]
> Voit tehdä entiteetistä myös mukautetun aktiviteetin. Tämä valinta muuttaa joitakin asetuksen oletusarvoja. Lisätietoja: [Mukautetun aktiviteetin entiteetin luominen](#create-custom-activity-entity)

Kun olet määrittänut entiteetin pakolliset asetukset, valitse ![Tallenna-komento](media/save-entity-icon-solution-explorer.png) ja luo mukautettu entiteetti.

### <a name="configure-the-primary-field"></a>Ensisijaisen kentän määrittäminen

**Ensisijainen kenttä** -välilehdessä voi yleensä hyväksyä ensisijaisen kentän oletusarvot, mutta käytettävissä ovat seuraavat asetukset:

|Kenttä   |Kuvaus  |
|---------|---------|
|**Näyttönimi**|Anna lokalisoitava otsikko, joka näytetään tässä kentässä lomakkeissa ja luetteloissa. Oletusarvo on **Nimi**.|
|**Nimi**|Määritä tälle kentälle järjestelmässä käytettävä nimi. Oletusarvo on `<customization prefix>_name`|
|**Enimmäispituus**|Anna kentän arvoille enimmäispituus. Oletusarvo on 100.|

> [!NOTE]
> Näitä asetuksia ei käytetä, jos entiteetti on aktiivinen entiteetti. Lisätietoja: [Mukautetun aktiviteetin entiteetin luominen](#create-custom-activity-entity)

### <a name="configure-required-fields"></a>Pakollisten kenttien määrittäminen

Jotkin asetukset on määritettävä **Yleiset**-välilehdessä, ennen kuin voit tallentaa entiteetin.

|Kenttä   |Kuvaus  |
|---------|---------|
|**Näyttönimi**|Tämä on sovelluksessa näkyvä entiteetin yksikkönimi.<br />Sen voi muuttaa myöhemmin.|
|**Monikkonimi**|Tämä on sovelluksessa näkyvä entiteetin monikollinen nimi.<br />Sen voi muuttaa myöhemmin.|
|**Nimi**|Kenttä täytetään valmiiksi tähän kirjoitetun näyttönimen perusteella. Se sisältää ratkaisunjulkaisijan mukautuksen etuliitteen.|
|**Omistus**|Voit valita asetukseksi käyttäjän tai ryhmän omistama tai organisaation omistama. Lisätietoja: [Entiteetin omistus](types-of-entities.md#entity-ownership)|

## <a name="edit-an-entity"></a>Entiteetin muokkaaminen

Valitse [entiteettien tarkastelemisen](#view-entities) yhteydessä muokattava entiteetti tai jatka juuri tallentamasi uuden entiteetin muokkaamista.

> [!NOTE]
> Hallitun ratkaisun osana olevien vakioentiteettien ja mukautettujen entiteettien muutoksissa voi olla rajoituksia. Jos asetus ei ole käytettävissä tai se on poistettu käytöstä, et voi tehdä muutoksia.

#### <a name="set-once-options"></a>Kerran määritettävät asetukset

Seuraavat asetukset voidaan määrittää kerran. Niitä ei voi muuttaa määrittämisen jälkeen. Nämä asetukset tarvitsee määrittää vasta sitten, kun tarvitset niitä.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

#### <a name="options-that-you-can-change"></a>Asetukset, joita voi muuttaa

Seuraavat ominaisuudet voi muuttaa milloin tahansa.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)]

Voit tehdä myös seuraavat muutokset:
- [Kenttien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-fields.md)
- [Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)
- [Luo ja suunnittele lomakkeita](../model-driven-apps/create-design-forms.md)
- [Luomalla liiketoimintaprosessin voidaan yhdenmukaistaa prosessit](/flow/create-business-process-flow)

## <a name="delete-an-entity"></a>Entiteetin poistaminen

Koska sinulla on järjestelmänvalvojan käyttöoikeusrooli, voit poistaa mukautettuja entiteettejä, joka ei sisälly hallittuun ratkaisuun.  
  
> [!IMPORTANT]
>  Kun poistat mukautetun entiteetin, sen tiedot sisältävät tietokantataulut poistetaan ja kaikki niiden sisältämät tiedot menetetään. Myös kaikki mukautetun entiteetin kanssa ylätason suhteen omaavat liittyvät tietueet poistetaan. Lisätietoja ylätason suhteista on kohdassa [Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md).  
  
> [!NOTE]
> Poistetun entiteetin tiedot voidaan palauttaa vain palauttamalla tietokanta hetkeen ennen entiteetin poistamista. Lisätietoja: [Ilmentymien varmuuskopiointi ja palautus](/dynamics365/customer-engagement/admin/backup-restore-instances)

Valitse [entiteettien tarkastelemisen](#view-entities) yhteydessä työkalurivin ![Poista komento](media/delete.gif) -komento.

Käytä valikkorivin poistokomentoa entiteetin tarkastelemisen yhteydessä.

![Poista-komento](media/delete-custom-entity-solution-explorer.png)

> [!WARNING]
> Jos tietoja sisältävä entiteetti poistetaan, kaikki tiedot poistetaan myös. Nämä tiedot voidaan hakea vain tietokannan varmuuskopion avulla.

> [!NOTE]
> Jos entiteetin riippuvuuksia löytyy, saat **Osaa ei voi poistaa** -virhesanoman, joka sisältää **Tiedot**-linkin. Sen avulla saat lisätietoja siitä, miksi entiteettiä ei voi poistaa. Yleensä tämä johtuu riippuvuudesta, joka on poistettava. 
>
> Entiteetin poistamisen esteenä voi olla useita riippuvuuksia. Tämä virhesanoma saattaa näyttää vain ensimmäisen riippuvuuden. Lisätietoja muista riippuvuuksien etsimisen tavoista on kohdassa [Entiteetin riippuvuuksien tunnistaminen](#identify-entity-dependencies)



### <a name="identify-entity-dependencies"></a>Entiteetin riippuvuuksien tunnistaminen

Voit tunnistaa entiteetin poistamisen estävät riippuvuudet, ennen kuin yrität poistaa entiteetin. 

1. Valitse ratkaisunhallinnassa entiteetti ja valitse sitten komentopalkissa **Näytä riippuvuudet**.

![Näytä riippuvuudet -komento](media/entity-show-dependencies.png)

2. Sirry näyttöön tulevassa valintaikkunassa oikealla olevan luettelon **Riippuvuustyyppi**-sarakkeen kohdalle.

![Julkaistu riippuvuustyyppi](media/published-entity-dependency.png)

**Julkaistut** riippuvuudet estävät entiteetin poistamisen. **Sisäiset** riippuvuudet tulee ratkaista järjestelmän avulla.  

3. Poista nämä julkaistut riippuvuudet. Tämän jälkeen entiteetin poistamisen tulisi olla mahdollista.

 > [!NOTE]
 > Hyvin yleinen riippuvuus on se, että toisessa entiteettilomakkeessa on poistettavan entiteetin hakukenttä. Riippuvuuden voi ratkaista poistamalla hakukentän lomakkeesta.

## <a name="create-custom-activity-entity"></a>MUkautetun aktiviteettientiteetin luominen

Jos haluat luoda entiteetin aktiviteettientiteettinä, noudata tässä ohjeaiheessa kerrottuja ohjeita muuten, mutta valitse **Määritä aktiviteettientiteetiksi**.

![Aktiviteettientiteetiksi määrittäminen](media/create-activity-entity-solution-explorer.png)

Aktiviteettientiteetti on erityinen entiteetti, joka seuraa toimintoja, joista voidaan tehdä merkintä kalenteriin. Lisätietoja: [Aktiviteettientiteetit](types-of-entities.md#activity-entities).

Kun määrität tämän asetuksen, jotkin entiteetin ominaisuuksista eivät ole yhteensopivia. Aktiviteettientiteetin on noudatettava vakiotoimintatapoja, joita kaikki aktiviteettientiteetit käyttävät.

Ensisijaisen kentän **nimeksi** ja **näyttönimeksi** määritetään **Aihe**. Arvoa ei voi muuttaa.

Seuraavia oletusarvoisesti määritettäviä asetuksia ei voi muuttaa:

 - **Palaute**
 - **Muistiinpanot (myös liitteet)**
 - **Yhteydet**
 - **Jonot**
 - **Dynamics 365 for Outlookin offline-ominaisuudet**

Seuraavia asetuksia ei voi määrittää:

- **Alueet, joissa tämä entiteetti näkyy**
- **Aktiviteetit**
- **Lähetetään sähköpostia**
- **Yhdistäminen**
- **Yhden tietueen seuranta**
- **Useiden tietueiden seuranta**

## <a name="create-a-virtual-entity"></a>Virtuaalisen entiteetin luominen

Joitakin asetuksia käytetään vain virtuaalisen entiteetin luomisen yhteydessä.

|Asetus   |Kuvaus  |
|---------|---------|
|**Virtuaalinen entiteetti**|Määrittää, onko kyseessä virtuaalinen entiteetti.|
|**Tietolähde**|Entiteetin tietolähde.|

Lisätietoja: [Ulkoisten tietolähteiden tietoja sisältävien virtuaalisten entiteettien luominen ja muokkaaminen](create-edit-virtual-entities.md)

### <a name="see-also"></a>Katso myös
[Entiteettien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa](create-edit-entities.md)<br />
[Opetusohjelma: Osia sisältävän mukautetun entiteetin luominen PowerAppsissa](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Ratkaisun luominen](create-solution.md)
