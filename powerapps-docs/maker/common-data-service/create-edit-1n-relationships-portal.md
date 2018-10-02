---
title: Yksi moneen- ja monta yhteen -entiteettisuhteiden luominen ja muokkaaminen PowerApps-portaalin avulla | MicrosoftDocs
description: Tietoja yksi moneen- ja monta moneen -entiteettisuhteiden luomisesta PowerApps-portaalin avulla
ms.custom: ''
ms.date: 06/11/2018
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
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-one-to-many-or-many-to-one-entity-relationships-using-powerapps-portal"></a>Yksi moneen- ja monta yhteen -entiteettisuhteiden luominen ja muokkaaminen PowerApps-portaalin avulla

[PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla on helppo luoda ja muokata 1:n (yksi moneen)- ja N:1 (monta yhteen) -suhteita Common Data Service sovelluksille -ratkaisussa.

Portaalin avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. Lisätietoja: 
- [1:N (yksi moneen)- ja N:1 (monta yhteen) -suhteen luominen ja muokkaaminen](create-edit-1n-relationships.md)
- [1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md).

## <a name="view-entity-relationships"></a>Entiteettisuhteiden tarkasteleminen

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

## <a name="create-relationships"></a>Suhteiden luominen

Valitse [entiteettisuhteiden tarkastelemisen](#view-entity-relationships) yhteydessä komentopalkista **Lisää suhde** ja valitse joko **Monta yhteen** tai **Yksi moneen**.

![Tietuetyypin valitseminen](media/add-relationship-menu-portal.png)

> [!NOTE]
> Lisätietoja **Monta moneen** -suhteesta on kohdassa [NN: (monta moneen) -suhteiden luominen](create-edit-nn-relationships.md)

<!-- This may change going forward, but this is the way it is now. #2534972 -->
> [!Important]
> Portaalissa käytetään erilaisia termejä kuin ratkaisunhallinnassa. Ehdot ovat käänteisiä. Ratkaisunhallinnan **liittyvä entiteetti** on portaalissa **ensisijainen entiteetti**. Vastaavasti ratkaisunhallinnan **ensisijainen entiteetti** on portaalissa **liittyvä entiteetti**.

Valinnastasi riippuen näytössä on jompikumpi seuraavista:

<!-- These are the correct screenshots from the UI as of 6/11/18 -->
|Tyyppi|Paneeli|
|--|--|
|**Monta yhteen**|![Monta yhteen -suhteen paneeli](media/many-to-one-relationship-panel.png)|
|**Yksi moneen**|![Yksi moneen -suhteen paneeli](media/one-to-many-relationship-panel.png)|

Valitse kahden entiteetin välille luotavan suhteen arvoksi joko **liittyvä entiteetti** tai **ensisijainen entiteetti**. 

> [!NOTE]
> *Ensisijaiselle* entiteetille luodaan hakukenttä, olipa valinta kumpi tahansa.

Kun olet valinnut entiteetin, voit muokata suhteen tietoja. Tässä esimerkissä yhdelle asiakkaalle voidaan liittää useita yhteyshenkilön entiteettitietueita.

<!-- These are the correct screenshots from the UI as of 6/11/18 -->
![Yksi moneen -suhteen asiakas ja yhteyshenkilö](media/One-to-many-account-contact.png)

Voit muokata annettuja oletusarvoja ennen tallentamista. Voit tarkastella **suhteen nimen** ja **hakukentän kuvauksen** arvoja valitsemalla **Lisää vaihtoehtoja**

|Kenttä|Kuvaus|
|--|--|
|**Hakukentän näyttönimi**|Liittyvälle entiteetille luotavan hakukentän lokalisoitava teksti.<br />Tätä voi muokata myöhemmin.|
|**Hakukentän nimi**|Liittyvälle entiteetille luotavan hakukentän nimi.|
|**Suhteen nimi**|Luotavan suhteen nimi.|
|**Hakukentän kuvaus**|Hakukentän kuvaus. Mallipohjaisissa sovelluksissa tämä näkyy työkaluvihjeenä silloin, kun käyttäjän hiiri on kentän kohdalla. <br />Tätä voi muokata myöhemmin.|

Voit jatkaa entiteetin muokkaamista. Valitse **Tallenna entiteetti**, kun haluat luoda määrittämäsi suhteen.

## <a name="edit-relationships"></a>Suhteiden muokkaaminen

Valitse [entiteettisuhteiden tarkastelemisen](#view-entity-relationships) yhteydessä muokattava suhde.

> [!NOTE]
> Jokainen suhde löytyy ensisijaisesta entiteetistä tai liittyvästä entiteetistä **monta yhteen**- tai **Yksi moneen** -suhteena. Se on sama suhde, vaikka sitä voikin muokata kummassakin paikassa.
>
> Hallitun ratkaisun julkaisija voi estää heidän ratkaisunsa osana olevien suhteiden jotkin mukautukset.

Voit muokata vain **Hakukentän näyttönimi**- ja **Hakukentän kuvaus** -kenttiä. Niitä voi muokata myös liittyvän entiteetin hakukentän ominaisuuksissa. Lisätietoja: [Kentän muokkaaminen](create-edit-field-portal.md#edit-a-field)

## <a name="delete-relationships"></a>Suhteiden poistaminen

Valitse [entiteettisuhteiden tarkastelemisen](#view-entity-relationships) yhteydessä poistettava suhde.

![Entiteettisuhteen poistaminen](media/delete-entity-relationship-portal.png)

Voit käyttää komentopalkin tai rivin pikavalikon **Poista suhde** -komentoa, kun valitset kolme pistettä (**...**).

Suhteen poistamisen yhteydessä poistetaan myös liittyvän entiteetin hakukenttä.

> [!NOTE]
> Suhdetta, jolla on riippuvuuksia, ei voi poistaa. Jos olet lisännyt esimerkiksi hakukentän liittyvän entiteetin lomakkeesta, kenttä on poistettava lomakkeesta ennen suhteen poistamista.

### <a name="see-also"></a>Katso myös

[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -suhteen luominen ja muokkaaminen](create-edit-1n-relationships.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md)<br />
[Kentän muokkaaminen](create-edit-field-portal.md#edit-a-field)
