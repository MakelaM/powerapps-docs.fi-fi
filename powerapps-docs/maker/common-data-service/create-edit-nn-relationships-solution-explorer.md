---
title: 'N:N (monta moneen) -entiteettisuhteiden luominen Common Data Service -palvelussa ratkaisunhallinnan avulla | MicrosoftDocs'
description: Monta moneen -suhteiden luominen
ms.custom: ''
ms.date: 05/29/2018
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
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-nn-many-to-many-entity-relationships-in-common-data-service-using-solution-explorer"></a>N:N (monta moneen) -entiteettisuhteiden luominen Common Data Service -palvelussa ratkaisunhallinnan avulla

Ratkaisunhallinta on eräs tapa luoda Common Data Service -palvelun N:N (monta moneen) -suhteita ja muokata niitä.

[PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. Lisätietoja:
- [Monta moneen (N:N) -entiteettisuhteiden luominen](create-edit-nn-relationships.md)
- [Monta-moneen-entiteettisuhteiden luominen Common Data Service -palvelussa PowerApps-portaalin avulla](create-edit-nn-relationships-portal.md)

  
## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luomasi mukautetun suhteen nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle entiteetille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entity-relationships"></a>Entiteettisuhteiden tarkasteleminen

Laajenna ratkaisunhallinnassa **Entiteetit**-kohta ja valitse entiteetti. Valitse entiteetin  **N:N-suhteet**.

![N:N-entiteettisuhteiden tarkasteleminen](media/view-nn-entity-relationships-solution-explorer.png)

## <a name="create-relationships"></a>Suhteiden luominen

Valitse [entiteettisuhteiden tarkastelemisen](#view-entity-relationships) yhteydessä komentopalkista **Uusi monta moneen -suhde**.

> [!NOTE]
> Jos komento eivät ole käytettävissä, entiteettiin ei voi luoda mukautettua suhdetta.

![Uusi monta moneen -suhteen lomake](media/new-nn-entity-relationship-form-solution-explorer.png)

Valitse **Muu entiteetti** -ryhmän **Entiteetin nimi** -kentässä entiteetti, johon haluat luoda suhteen. Tämä täyttää **Nimi**- ja **Suhteen entiteetin nimi** -kenttiin arvot **Suhteen määritys** -ryhmässä.

Valitse ![Tallenna entiteettisuhde -painike](media/save-entity-icon-solution-explorer.png), kun haluat tallentaa entiteetin ja jatkaa muokkaamista. Lisätietoja: [Suhteiden muokkaaminen](#edit-relationships)

> [!NOTE]
> Jos **Nimi**- tai **Suhteen entiteetin nimi** -arvot on jo määritetty järjestelmään, tallennuksen yhteydessä näyttöön tulee virhesanoma. Muokkaa arvoja niin, että ne ovat yksilöllisiä, ja yritä uudelleen.

## <a name="edit-relationships"></a>Suhteiden muokkaaminen

Valitse [entiteettisuhteiden tarkastelemisen](#view-entity-relationships) yhteydessä muokattava entiteetti. 

> [!NOTE]
> Hallitun ratkaisun julkaisija voi estää heidän ratkaisunsa osana olevien suhteiden mukautukset.

Seuraavia entiteettisuhteen ominaisuuksia voi muokata suhteen luomisen jälkeen.

> [!IMPORTANT]
> Kun olet muokannut näitä ominaisuuksia, mukautukset on julkaistava ennen kuin ne otetaan käyttöön mallipohjaisissa sovelluksissa.

### <a name="edit-display-options"></a>Näyttöasetusten muokkaaminen

Voit muokata sekä **nykyisen entiteetin** että **muun entiteetin** näyttöasetuskenttiä. Ne ohjaavat liittyvien entiteettien näyttöä mallipohjaisissa sovelluksissa.

|Kenttä|Kuvaus|
|--|--|
|**Näyttöasetus**|Liittyvien entiteettien luettelon näyttötapa. Lisätietoja: [Näyttöasetukset](#display-options)|
|**Mukautettu otsikko**|Määritä lokalisoitava teksti, jota käytetään monikkonimen sijaan, kun valitset **näyttöasetukseksi** **Käytä mukautettua otsikkoa**.|
|**Näyttöalue**|Valitse jokin käytettävissä olevista ryhmittelyistä tämän luettelon näyttöä varten. Käytettävissä olevat asetukset ovat: **Tiedot** (*yleiselle* ryhmälle), **Markkinointi**, **Myynti** ja **Palvelu**. |
|**Näyttöjärjestys**|Määrittää, missä kohdassa näyttöaluetta siirtymiskohde näytetään. Sallittujen lukujen alue alkaa luvusta 10 000. Siirtymiskohteet, joilla on matalampi arvo, ovat korkeampiarvoisten suhteiden yläpuolella.|

<!-- TODO: Not sure whether Display Area or Display Order are still used anymore. Might only be used in the Outlook client?-->

#### <a name="display-options"></a>Näyttöasetukset

Nämä ovat käytettävissä olevat näyttöasetukset:

|Asetus|Kuvaus|
|--|--|
|**Älä näytä**|Älä näytä tämän suhteen liittyviä entiteettejä.|
|**Käytä mukautettua otsikkoa**|Kun tämä asetus valitaan, **Mukautettu otsikko** -kenttä otetaan käyttöön ja voit määrittää monikkonimen sijaan käytettävän lokalisoitavan tekstin.|
|**Käytä monikollista nimeä**|Käytä liittyvälle entiteetille määritettyä monikollista näyttönimeä.|

### <a name="searchable"></a>Etsittävissä

Voit piilottaa suhteen **erikoishaulta** mallipohjaisissa sovelluksissa määrittämällä **Haettavissa**-kentän arvoksi **Ei**.

## <a name="delete-relationships"></a>Suhteiden poistaminen

Valitse [suhteiden tarkastelemisen](#view-entity-relationships) yhteydessä poistettava entiteettisuhde ja valitse sitten ![Poista komento](media/delete.gif) -komento.

Suhteen poistaminen poistaa myös luodun suhteen entiteetin. Kaikki suhdetta käyttäviin entiteetteihin liittyvät tiedot menetetään.

### <a name="see-also"></a>Katso myös

[Monta moneen (N:N) -entiteettisuhteiden luominen](create-edit-nn-relationships.md)<br />
[Monta-moneen-entiteettisuhteiden luominen Common Data Service -palvelussa PowerApps-portaalin avulla](create-edit-nn-relationships-portal.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteen luominen ja muokkaaminen](create-edit-1n-relationships.md)
