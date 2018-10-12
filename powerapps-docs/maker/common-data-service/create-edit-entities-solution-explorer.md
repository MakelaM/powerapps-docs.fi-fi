---
title: Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla | MicrosoftDocs
description: Lue, kuinka voit luoda entiteetin ratkaisunhallinnan avulla
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
ms.openlocfilehash: 48025088da85bf0685ba1a46efa4f3a989a20a58
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674107"
---
# <a name="create-and-edit-entities-using-solution-explorer"></a>Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla

PowerApps-portaalin avulla voit luoda helposti entiteetin yleisimpiä tapauksia varten, mutta et saa kaikkia ominaisuuksia käyttöön tällä tavoin. Jos sinun on täytettävä vaatimukset, jotka kuvataan artikkelissa [Entiteettien luominen ja muokkaaminen Common Data Service for Appsissa](create-edit-entities.md), voit tehdä sen luomalla tai muokkaamalla entiteettejä ratkaisunhallinnan avulla.

## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Luomasi entiteetin nimeen sisältyy mukautusetuliite. Etuliite määräytyy käytössäsi olevan ratkaisun julkaisijan mukaan. Jos mukautusetuliitteellä on sinulle merkitystä, varmista, että käytät hallitsematonta ratkaisua, jossa mukautusetuliite on se, jota haluat käyttää kyseiselle entiteetille. Lisätietoja: [Ratkaisun julkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entities"></a>Entiteettien tarkasteleminen

Valitse ratkaisunhallinnan **Osat**-solmussa **Entiteetit**-solmu.

![Entiteettien tarkasteleminen ratkaisunhallinnassa](media/view-entities-solution-explorer.png)

## <a name="create-an-entity"></a>Entiteetin luominen

Kun [tarkastelet entiteettejä](#view-entities), voit avata uuden entiteettilomakkeen valitsemalla vaihtoehdon **Uusi**.

![uusi entiteettilomake ratkaisunhallinnassa](media/new-entity-form-solution-explorer.png)

Uudessa entiteettilomakkeessa on kaksi välilehteä. **Yleiset**-välilehti on entiteettiasetuksia varten. **Ensisijainen kenttä** -välilehti on tarkoitettu asetuksille, jotka koskevat kunkin entiteetin erityistä yksittäistä tekstikentän riviä, joka määrittää näkyvän tekstin siinä tapauksessa, että hakukentässä on linkki entiteetin avaamiseksi.

Välilehden jokaista osiota koskevia lisätietoja annetaan seuraavissa kohdissa:
- [Ensisijaisen kentän määrittäminen](#configure-the-primary-field)
- [Pakollisten kenttien määrittäminen](#configure-required-fields)

> [!NOTE]
> Voit myös tehdä entiteetistä mukautetun toiminnon. Tämä valinta muuttaa joidenkin asetusten oletusarvoja. Lisätietoja: [Mukautetun toimintoentiteetin luominen](#create-custom-activity-entity)

Kun olet määrittänyt entiteetin tarvittavat asetukset, valitse ![Tallenna-komento](media/save-entity-icon-solution-explorer.png) mukautetun entiteetin luomiseksi.

### <a name="configure-the-primary-field"></a>Ensisijaisen kentän määrittäminen

**Ensisijainen kenttä** -välilehdellä voit tavallisesti hyväksyä ensisijaisen kentän oletusarvot, mutta voit halutessasi määrittää seuraavat asetukset:

|Kenttä   |Kuvaus  |
|---------|---------|
|**Näyttönimi**|Voit syöttää lokalisoitavan otsikon, joka näkyy tämän kentän otsikkona lomakkeissa ja luetteloissa. Oletusarvo on **Nimi**.|
|**Nimi**|Voit määrittää nimen, jota käytetään tämän kentän nimenä järjestelmässä. Oletusarvo on `<customization prefix>_name`|
|**Enimmäispituus**|Voit syöttää kentän arvojen enimmäispituuden. Oletusarvo on 100.|

> [!NOTE]
> Nämä asetukset eivät päde, jos entiteetti on toimintoentiteetti. Lisätietoja: [Mukautetun toimintoentiteetin luominen](#create-custom-activity-entity)

### <a name="configure-required-fields"></a>Pakollisten kenttien määrittäminen

Joitain **Yleiset**-välilehden asetuksia täytyy määrittää ennen kuin entiteetti voidaan tallentaa.

|Kenttä   |Kuvaus  |
|---------|---------|
|**Näyttönimi**|Tämä on entiteetin yksiköllinen nimi, joka näkyy sovelluksessa.<br />Se voidaan muuttaa myöhemmin.|
|**Monikkomuotoinen nimi**|Tämä on entiteetin monikkomuotoinen nimi, joka näkyy sovelluksessa.<br />Se voidaan muuttaa myöhemmin.|
|**Nimi**|Tämä kenttä täyttyy valmiiksi kirjoittamasi näyttönimen perusteella. Se sisältää ratkaisun julkaisijan mukautusetuliitteen.|
|**Omistajuus**|Voit valita entiteetin omistajaksi käyttäjän, ryhmän tai organisaation. Lisätietoja: [Entiteetin omistajuus](types-of-entities.md#entity-ownership)|

## <a name="edit-an-entity"></a>Entiteetin muokkaaminen

Kun [tarkastelet entiteettejä](#view-entities), valitse entiteetti, jota haluat muokata, tai jatka juuri tallentamasi uuden entiteetin muokkaamista.

> [!NOTE]
> Vakioentiteeteillä tai mukautetuilla entiteeteillä, jotka ovat osa hallittua ratkaisua, voi olla tehtävissä olevia muutoksia koskevia rajoituksia. Jos asetus ei ole käytettävissä tai se on poistettu käytöstä, kyseisen muutoksen tekeminen ei ole sallittua.

#### <a name="set-once-options"></a>Asetukset, jotka voidaan määrittää vain kerran

Seuraavat asetukset voidaan määrittää vain kerran, eikä niitä voida muuttaa määrittämisen jälkeen. Määritä nämä asetukset ainoastaan, kun tarvitset niitä.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

#### <a name="options-that-you-can-change"></a>Asetukset, joita voidaan muuttaa

Seuraavia ominaisuuksia voidaan muuttaa milloin tahansa.

<!-- 
Same data is presented in edit-entities.md
Both should point to this include
 -->
[!INCLUDE [cc_entity-changeable-options-table](../../includes/cc_entity-changeable-options-table.md)]

Voit myös tehdä seuraavat muutokset:
- [Kenttien luominen ja muokkaaminen Common Data Service for Appsissa](create-edit-fields.md)
- [Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)
- [Luo ja suunnittele lomakkeita](../model-driven-apps/create-design-forms.md)
- [Liiketoimintaprosessin työnkulun luominen prosessien yhdenmukaistamiseksi](/flow/create-business-process-flow)

## <a name="delete-an-entity"></a>Entiteetin poistaminen

Jos sinulla on järjestelmän järjestelmänvalvojan rooli, voit poistaa mukautettuja entiteettejä, jotka eivät ole osa hallittua ratkaisua.  
  
> [!IMPORTANT]
>  Kun poistat mukautetun entiteetin, kyseisen entiteetin tietoja sisältävät tietokantataulukot ja kaikki niiden sisältämät tiedot poistetaan. Lisäksi poistetaan kaikki liittyvät tietueet, joilla on ylätason suhde mukautettuun entiteettiin. Lisätietoja ylätason suhteista annetaan artikkelissa [Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md).  
  
> [!NOTE]
> Ainoa tapa palauttaa poistetun entiteetin tietoja on palauttaa tietokanta entiteetin poistamista edeltävästä kohdasta. Lisätietoja: [Esiintymien varmuuskopiointi ja palauttaminen](/dynamics365/customer-engagement/admin/backup-restore-instances)

Kun [tarkastelet entiteettejä](#view-entities), napsauta ![Poista-komentoa](media/delete.gif) työkalurivillä.

Käytä Poista-komentoa valikkopalkissa, kun tarkastelet entiteettiä.

![Poista-komento](media/delete-custom-entity-solution-explorer.png)

> [!WARNING]
> Tietoja sisältävän entiteetin poistaminen poistaa kaikki tiedot. Nämä tiedot voidaan noutaa vain tietokannan varmuuskopiosta.

> [!NOTE]
> Jos entiteetillä on riippuvuussuhteita, näkyviin tulee **Osaa ei voi poistaa** -virhesanoma, johon liittyvän **Tiedot**-linkin avulla voit löytää tietoja siitä, miksi entiteettiä ei voi poistaa. Useimmissa tapauksissa syynä on riippuvuussuhde, joka pitäisi poistaa. 
>
> Yksittäisen entiteetin poistamisen estäviä riippuvuuksia voi olla enemmän kuin yksi. Tämä virhesanoma saattaa näyttää niistä vain ensimmäisen. Kohdassa [Entiteetin riippuvuuksien tunnistaminen](#identify-entity-dependencies) esitetään vaihtoehtoinen tapa löytää riippuvuussuhteita.



### <a name="identify-entity-dependencies"></a>Entiteetin riippuvuuksien tunnistaminen

Voit tunnistaa entiteetin poistamisen estävät riippuvuussuhteet ennen kuin yrität poistaa entiteetin. 

1. Kun entiteetti on valittuna ratkaisunhallinnassa, napsauta **Näytä riippuvuudet** komentopalkissa.

![Näytä riippuvuudet -komento](media/entity-show-dependencies.png)

2. Vieritä näkyviin tulevassa ikkunassa luetteloa oikealle, jotta näet **Riippuvuustyyppi**-sarakkeen.

![Julkaistu riippuvuustyyppi](media/published-entity-dependency.png)

**Julkaistut** riippuvuudet estävät entiteetin poiston. Järjestelmä voi todennäköisesti lopettaa **sisäiset** riippuvuudet.  

3. Kun poistat julkaistut riippuvuudet, sinun pitäisi voida poistaa entiteetti.

 > [!NOTE]
 > Hyvin yleinen riippuvuus on sellainen, jossa toisessa entiteettilomakkeessa on hakukenttä, joka liittyy poistettavaan entiteettiin. Hakukentän poistaminen lomakkeesta lopettaa riippuvuuden.

## <a name="create-custom-activity-entity"></a>Mukautetun toimintoentiteetin luominen

Jos haluat luoda entiteetin toimintoentiteettinä, noudata tässä ohjeaiheessa annettuja ohjeita, mutta valitse **Määritä toimintoentiteettinä**.

![Määrittäminen toimintoentiteettinä](media/create-activity-entity-solution-explorer.png)

Toimintoentiteetti on erityinen entiteettityyppi, joka seuraa toimintoja, joista voidaan tehdä merkintä kalenteriin. Lisätietoja: [Toimintoentiteetit](types-of-entities.md#activity-entities).

Jos määrität tämän asetuksen, jotkin entiteetin ominaisuudet eivät ole yhteensopivia. Toimintoentiteetin on vastattava vakiotoimintamalleja, joita kaikki toimintoentiteetit käyttävät.

Ensisijaisen kentän **Nimi**- ja **Näyttönimi**-asetukseksi määritetään **Aihe**, eikä tätä asetusta voi muuttaa.

Seuraavat asetukset määritetään oletusarvoisesti, eikä niitä voi muuttaa:

 - **Palaute**
 - **Huomautukset (mukaan lukien liitteet)**
 - **Yhteydet**
 - **Jonot**
 - **Dynamics 365 for Outlookin offline-ominaisuus**

Seuraavia asetuksia ei voida määrittää:

- **Alueet, jotka näyttävät tämän entiteetin**
- **Toiminnot**
- **Sähköpostiviestin lähettäminen**
- **Yhdistäminen**
- **Yhden tietueen seuranta**
- **Useiden tietueiden seuranta**

## <a name="create-a-virtual-entity"></a>Virtuaalisen entiteetin luominen

Joitakin asetuksia käytetään vain, kun luodaan virtuaalinen entiteetti.

|Asetus   |Kuvaus  |
|---------|---------|
|**Virtuaalinen entiteetti**|Määrittää, onko entiteetti virtuaalinen entiteetti.|
|**Tietolähde**|Entiteetin tietolähde.|

Lisätietoja: [Ulkoisesta tietolähteestä peräisin olevia tietoja sisältävien virtuaalisten entiteettien luominen ja muokkaaminen](create-edit-virtual-entities.md)

### <a name="see-also"></a>Katso myös
[Entiteettien luominen ja muokkaaminen Common Data Service for Appsissa](create-edit-entities.md)<br />
[Opetusohjelma: Luo osia sisältävä mukautettu entiteetti PowerAppsissa](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Ratkaisun luominen](create-solution.md)