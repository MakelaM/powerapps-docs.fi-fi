---
title: Monta moneen -entiteettisuhteiden luominen Common Data Servicessä PowerApps-portaalin avulla | MicrosoftDocs
description: Monta moneen -suhteiden luominen
ms.custom: ''
ms.date: 06/11/2018
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

# <a name="create-many-to-many-entity-relationships-in-common-data-service-using-powerapps-portal"></a>Monta moneen -entiteettisuhteiden luominen Common Data Servicessä PowerApps-portaalin avulla

[PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla on helppo luoda ja muokata monta moneen -entiteettisuhteita Common Data Servicessä.

Portaalin avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. Lisätietoja: 
- [N:N (monta moneen ) -entiteettisuhteiden luominen](create-edit-nn-relationships.md)
- [N:N (monta moneen) -entiteettisuhteiden luominen Common Data Servicessä ratkaisunhallinnan avulla](create-edit-nn-relationships-solution-explorer.md)

## <a name="view-many-to-many-entity-relationships"></a>Monta moneen -entiteettisuhteiden tarkasteleminen

1. Valitse [PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) joko **Mallipohjainen**- tai **Kaavio**-suunnittelutila.
2. Valitse **Tiedot** > **Entiteetit** ja valitse entiteetti, jonka suhteita haluat tarkastella.
3. Kun **Suhteet**-välilehti on valittu, voit valita seuraavat näkymät: 

 |Näkymä|Kuvaus|
 |--|--|
 |**Kaikki**| Näyttää entiteetin kaikki suhteet|
 |**Mukautettu**|Näyttää vain entiteetin mukautetut suhteet|
 |**Oletus**|Näyttää vain entiteetin vakiosuhteet|
<!-- TODO: What is the actual difference between All and Default? -->

![Asiakkaan entiteettisuhteet](media/view-account-relationships-portal.png)

Monta moneen -suhteiden **suhdetyyppi** on **Monta moneen**.

> [!NOTE]
> Tarkasteltavalla entiteetillä ei ehkä ole **monta moneen** -suhteita.

## <a name="create-relationships"></a>Suhteiden luominen

Valitse [entiteettisuhteiden tarkastelemisen](#view-many-to-many-entity-relationships) yhteydessä komentopalkista **Lisää suhde** ja valitse **Monta moneen**.

![Tietuetyypin valitseminen](media/add-relationship-menu-portal.png)

Valitse **Monta moneen** -paneelissa entiteetti, jonka haluat liittää nykyiseen entiteettiin.

![Monta moneen -paneeli ja valittu asiakasentiteetti](media/many-to-many-panel-1.png)

Valitse **Lisää vaihtoehtoja**, jos haluat tarkastella **Suhteen nimi**- ja **Suhteen entiteetin nimi** -kenttiä.

![Monta moneen -paneeli ja valittu Lisää vaihtoehtoja -kohta](media/many-to-many-panel-2.png)

Näiden kenttien arvot luodaan valittujen entiteettien perusteella.

> [!NOTE]
> Jos luot useita **monta moneen** -suhteita samoille kahdelle entiteetille, sinun on muokattava luotuja **Suhteen nimi**- ja **Suhteen entiteetin nimi** -kenttiä niin, että ne ovat yksilöllisiä.

Valitse **OK**, jolloin **Monta moneen** -paneeli sulkeutuu. Suhde luodaan, kun tallennat entiteetin muutokset. 

Kun muutokset on tallennettu, [PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ei enää voi tehdä muutoksia. Voit muokata mallipohjaisten sovellusten suhteiden ominaisuuksia [ratkaisunhallinnan](create-edit-nn-relationships-solution-explorer.md) avulla.

## <a name="delete-relationships"></a>Suhteiden poistaminen

Valitse [entiteettisuhteiden tarkastelemisen](#view-many-to-many-entity-relationships) yhteydessä poistettava suhde.

![Entiteettisuhteen poistaminen](media/delete-entity-relationship-portal.png)

Voit käyttää komentopalkin tai rivin pikavalikon **Poista suhde** -komentoa, kun valitset kolme pistettä (**...**).

Monta moneen -suhteen poistaminen poistaa myös luodun suhteen entiteetin. Kaikki suhdetta käyttäviin entiteetteihin liittyvät tiedot menetetään.

### <a name="see-also"></a>Katso myös

[N:N (monta moneen ) -entiteettisuhteiden luominen](create-edit-nn-relationships.md)<br />
[N:N (monta moneen) -entiteettisuhteiden luominen Common Data Servicessä ratkaisunhallinnan avulla](create-edit-nn-relationships-solution-explorer.md)
