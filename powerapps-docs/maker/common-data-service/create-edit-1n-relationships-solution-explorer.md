---
title: '1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla | MicrosoftDocs'
description: Tietoja yksi moneen- ja monta moneen -entiteettisuhteiden luomisesta PowerApps-ratkaisunhallinnan avulla
ms.custom: ''
ms.date: 10/28/2018
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

# <a name="create-and-edit-1n-one-to-many-or-n1-many-to-one-entity-relationships-using-solution-explorer"></a>1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla 

Ratkaisunhallinnan avulla voi luoda 1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteita ja muokata niitä Common Data Servicessä.

[PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. Lisätietoja: 
- [1:N (yksi moneen)- tai N:1 (monta yhteen) -suhteen luominen](create-edit-1n-relationships.md)
- [1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen PowerApps-portaalissa](create-edit-1n-relationships-portal.md)
  
## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luomasi mukautetun suhteen nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle entiteetille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-entity-relationships"></a>Entiteettisuhteiden tarkasteleminen

Laajenna ratkaisunhallinnassa **Entiteetit**-kohta ja valitse entiteetti. Valitse entiteetille joko **1:N-suhteet** tai **N:1‑suhteet**

![Entiteettisuhteiden tarkasteleminen](media/view-1n-entity-relationships-solution-explorer.png)

## <a name="create-relationships"></a>Suhteiden luominen

Valitse [entiteettisuhteiden tarkastelemisen](#view-entity-relationships) yhteydessä komentopalkista **Uusi yksi moneen -suhde** tai **Uusi monta yhteen -suhde**.

> [!NOTE]
> Jos komennot eivät ole käytettävissä, entiteettiin ei voi luoda mukautettua suhdetta.

Kumpikin asetus avaa lomakkeen, joka näyttää seuraavalta. Ero on se, että määritettynä on joko **Ensisijainen entiteetti**- tai **Liittyvä entiteetti** -kenttä.

![Uusi yksi moneen -suhteen lomake](media/new-1n-entity-relationship-form-solution-explorer.png)

- **1:N-suhteen** **Ensisijainen entiteetti** -kohdaksi määritetään nykyinen entiteetti
- **N:1-suhteen** **Liittyvä entiteetti** -kohdaksi määritetään nykyinen entiteetti

Seuraavat kentät on määritettävä, jotta entiteettisuhteen voi tallentaa:

|Pakollinen kenttä|Kuvaus|
|--|--|
|**Ensisijainen kohde**|Tämä entiteetti on liittyvälle entiteetille luodun hakukentän kohdetyyppi.|
|**Oheiskohde**|Tähän entiteettiin on lisätty hakukenttä, jotta entiteettitietueet voidaan liittää ensisijaiseen entiteettitietueeseen.|
|**Nimi**|Suhteen nimi. Arvo luodaan ensisijaisen ja liittyvän entiteetin arvojen perusteella. Tämän kentän etuliitteeksi tulee ratkaisujulkaisijan mukautettu etuliite.|
|**Hakukentän näyttönimi**|Liittyvälle entiteetille luotavan hakukentän lokalisoitava teksti. Tämä on yleensä sama kuin ensisijaisen entiteetin näyttönimi. <br /> Sen voi muuttaa myöhemmin.|
|**Hakukentän nimi**|Liittyvälle entiteetille luotavan hakukentän nimi. Arvo luodaan **hakukentän näyttönimen** perusteella. Tämän kentän etuliitteeksi tulee ratkaisujulkaisijan mukautettu etuliite.|

Valitse ![Tallenna entiteettisuhde -painike](media/save-entity-icon-solution-explorer.png), kun haluat tallentaa entiteetin ja jatkaa muokkaamista. Lisätietoja: [Suhteiden muokkaaminen](#edit-relationships)

> [!NOTE]
> Jos **Nimi**- tai **Hakukentän nimi** -arvot on jo määritetty järjestelmään, tallennuksen yhteydessä näyttöön tulee virhesanoma. Muokkaa arvoja niin, että ne ovat yksilöllisiä, ja yritä uudelleen.

## <a name="edit-relationships"></a>Suhteiden muokkaaminen

Valitse [entiteettisuhteiden tarkastelemisen](#view-entity-relationships) yhteydessä muokattava entiteetti. Seuraavia entiteettisuhteen ominaisuuksia voi muokata suhteen luomisen jälkeen.

> [!NOTE]
> Hallitun ratkaisun julkaisija voi estää heidän ratkaisunsa osana olevien suhteiden jotkin mukautukset.

### <a name="entity-relationship-properties"></a>Entiteettisuhteen ominaisuudet

Nämä ominaisuudet koskevat suhdetta.

|Kenttä|Kuvaus|
|--|--|
|**Etsittävissä**|Määrittää, näkyykö tämä suhde mallipohjaisen sovellusten Erikoishaku-kohdassa. Valitse **Ei**, jos tämä suhde ei ole yritykselle tärkeä.|
|**Hierarkkinen**|Tämä asetus otetaan käyttöön vain itseen viittaavissa suhteissa. Määrittää, käytetäänkö entiteettiä sen hierarkian määrittämisessä.<br />**Tärkeää**: Kun tämän ominaisuuden koontikentät määritetään, prosessit ja näkymät voidaan määrittää tästä ominaisuudesta riippuvaisiksi. Jos myöhemmin muutat tätä arvoa, hierarkiasta riippuvaiset ominaisuudet eivät toimi. <br />Lisätietoja: [Hierarkkisesti järjestettyjen tietojen määrittäminen ja kysely](define-query-hierarchical-data.md)|

### <a name="lookup-field"></a>Hakukenttä

Nämä ovat liittyvälle entiteetille luodut hakukentän ominaisuudet. Ominaisuuksia voi muokata tässä tai suoraan hakukenttää muokkaamalla. Joitakin kentän ominaisuuksia ei voi muokata suhteesta. Lisätietoja: [Kentän muokkaaminen](create-edit-field-solution-explorer.md#edit-a-field)

|Kenttä|Kuvaus|
|--|--|
|**Näyttönimi**|Liittyvälle entiteetille luotavan hakukentän lokalisoitava teksti.|
|**Kenttävaatimus**|Määrittää, onko kentässä oltava tietoja, ennen kuin mallipohjaisen sovelluksen lomake voidaan tallentaa. Lisätietoja: [Kenttävaatimuksen asetukset](create-edit-field-solution-explorer.md#field-requirement-options)|
|**Kuvaus**|Anna käyttäjälle kentän käyttämistä koskevat ohjeet. Nämä kuvaukset näkyvät käyttäjälle työkaluvihjeinä mallipohjaisissa sovelluksissa, kun käyttäjä pitää hiiren osoitinta kentän otsikon päällä.|

### <a name="navigation-pane-item-for-primary-entity"></a>Ensisijaisen kohteen siirtymisruudun kohde

Ensisijaisesta entiteetistä voi siirtyä liittyviin tietueisiin. Näitä tietoja käytetään mallipohjaisissa sovelluksissa liittyvien entiteettitietueiden näytön hallinnassa. Näitä asetuksia voi myös muokata lomake-editorin avulla.

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

### <a name="relationship-behavior"></a>Suhteen käyttäytyminen

Tässä voit määrittää liittyvien entiteettien vakiotoimintatavat. Nämä tiedot ovat tärkeitä, koska niiden avulla varmistetaan tietojen yhtenäisyys. Tietojen avulla voi myös automatisoida yrityksen liiketoimintaprosesseja.

Tarkastellaan esimerkkiä.  
  
Oletetaan, että sinulla on uusi myyjä ja haluat delegoida hänelle osan toiselle myyjälle delegoiduista mahdollisuuksista. Jokaisella mahdollisuustietueella voi olla useampi tehtäväaktiviteetti. Haluat löytää uudelleendelegoitavat mahdollisuudet helposti ja delegoida ne uudelle myyjälle. Mutta mitä tapahtuu tehtäväaktiviteeteille, jotka on liitetty mahdollisuuksiin? Haluatko avata kunkin tehtävän ja päättää, delegoidaanko nekin uudelle myyjälle? Luultavasti et. Sen sijaan voit antaa suhteen soveltaa automaattisesti vakiosääntöjä. Näitä sääntöjä sovelletaan vain uudelleendelegoitavien mahdollisuuksien tehtävätietueisiin. Vaihtoehtosi ovat:  
  
- Uudelleendelegoi kaikki aktiiviset tehtävät.  
- Uudelleendelegoi kaikki tehtävät. 
- Älä uudelleendelegoi tehtäviä.  
- Uudelleendelegoi kaikki tehtävät, jotka on delegoitu mahdollisuuden edelliselle omistajalle.  
  
Suhde voi ohjata, kuinka ensisijaisen entiteetin tietueelle suoritetut toiminnot laskeutuvat liitetyn entiteetin tietueille.   

Useita erilaisia toimintatapoja voidaan ottaa käyttöön tiettyjen toimintojen yhteydessä.

#### <a name="behaviors"></a>Toimintatavat

Seuraavassa ovat määritettävissä olevat toimintatavat.

|Toimintatapa|Kuvaus|
|--|--|
|**Limittäisyys**|Suorita toiminto kaikille aktiivisen liittyvän entiteetin tietueille.|
|**Kaikki limittäin**|Suorita toiminto kaikille liittyvän entiteetin tietueille.|
|**Ei mitään limittäin**|Älä tee mitään.|
|**Poista linkki**|Poista kaikkien liittyvien tietueiden hakuarvo.|
|**Rajoita**|Estä ensisijaisen entiteetin tietueiden poistaminen, kun niillä on liittyviä entiteettitietueita.|
|**Käyttäjän limittäin**|Suorita toiminto kaikille liittyville entiteetin tietueille, joilla on sama omistaja kuin pääentiteetin tietueella.|

#### <a name="actions"></a>Toiminnot

Seuraavat toiminnot voivat käynnistää tiettyjä toimintatapoja:

|Kenttä|Kuvaus|Asetukset|
|--|--|--|
|**Delegoi**|Mitä tapahtuu, kun ensisijainen entiteettitietue delegoidaan jollekin toiselle?|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Määritä ylätaso uudelleen**|Mitä tapahtuu, kun ylätason suhteen liittyvän entiteetin hakuarvoa muutetaan?<br />Lisätietoja: [Ylätason entiteettisuhteet](#parental-entity-relationships)|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Jaa**|Mitä tapahtuu, kun ensisijaisen entiteetin tietue jaetaan?|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Poista**|Mitä tapahtuu, kun ensisijaisen entiteetin tietue poistetaan?|Kaikki limittäin<br />Poista linkki<br />Rajoita|
|**Poista jako**|Mitä tapahtuu, kun ensisijaisen entiteettitietueen jako poistetaan?|Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|
|**Yhdistäminen**|Mitä tapahtuu, kun ensisijainen entiteettitietue yhdistetään?|Kaikki limittäin<br />Ei mitään limittäin|
|**Koostenäkymä**|Mikä on tähän suhteeseen liitetyn koostenäkymän haluttu toimintatapa? |Kaikki limittäin<br />Limittäisyys<br />Käyttäjän omistamien limittäminen<br />Ei mitään limittäin|

<!-- TODO: I find no official docs related to rollup views, but plenty of hits online: https://www.google.com/search?q=Dynamics+365++%27rollup+view%27 -->



#### <a name="type-of-behavior-options"></a>Toimintatyypin asetukset

Määritä **Toimintatyyppi**-kentän avulla, käytetäänkö vakiotoimintajoukkoa vai määritetäänkö toimintatavat erikseen. 

|Asetus|Kuvaus|
|--|--|
|**Ylätaso**|**Delegoi**: Kaikki limittäin<br />**Määritä ylätaso uudelleen**: Kaikki limittäin<br />**Jaa**: Kaikki limittäin<br />**Poista**: Kaikki limittäin<br />**Poista jako**: Kaikki limittäin<br />**Yhdistä**: Ei mitään limittäin<br />**Koostenäkymä**: Ei mitään limittäin \| Kaikki limittäin<br />|
|**Viittaus**|**Delegoi**: Ei mitään limittäin<br />**Määritä ylätaso uudelleen**: Ei mitään limittäin<br />**Jaa**: Ei mitään limittäin<br />**Poista**: Poista linkki<br />**Poista jako**: Ei mitään limittäin<br />**Yhdistä**: Ei mitään limittäin<br />**Koostenäkymä**: Ei mitään limittäin \| Kaikki limittäin<br />|
|**Viittaus, poiston rajoitus**|**Delegoi**: Ei mitään limittäin<br />**Määritä ylätaso uudelleen**: Ei mitään limittäin<br />**Jaa**: Ei mitään limittäin<br />**Poista**: Rajoitus<br />**Poista jako**: Ei mitään limittäin<br />**Yhdistä**: Ei mitään limittäin<br />**Koostenäkymä**: Ei mitään limittäin \| Kaikki limittäin<br />|
|**Limittäisyys määritettävissä**|Voit määrittää haluamasi toimintatavan kullekin toiminnolle käytettävissä olevista asetuksista riippuen|

> [!NOTE]
> Et ehkä voi käyttää **Ylätaso**-asetusta, jos jompikumpi entiteeteistä on jo mukana ylätason entiteettisuhteessa. Lisätietoja: [Ylätason entiteettisuhteet](#parental-entity-relationships)
> 
> Jos käytät **Limittäisyys määritettävissä** -kohtaa toimintatapojen määrittämiseen toiminnoille niin, että ne vastaavat toiseen **toimintatyyppiin** liitettyjä toimintoja, **toimintatyypiksi** määritetään automaattisesti vastaava tyyppi suhteen tallentamisen yhteydessä.  



## <a name="delete-relationships"></a>Suhteiden poistaminen

Valitse [suhteiden tarkastelemisen](#view-entity-relationships) yhteydessä poistettava entiteettisuhde ja valitse sitten ![Poista komento](media/delete.gif) -komento.

Suhteen poistamisen yhteydessä poistetaan myös liittyvän entiteetin hakukenttä.

> [!NOTE]
> Suhdetta, jolla on riippuvuuksia, ei voi poistaa. Jos olet lisännyt esimerkiksi hakukentän liittyvän entiteetin lomakkeesta, kenttä on poistettava lomakkeesta ennen suhteen poistamista.

## <a name="parental-entity-relationships"></a>Ylätason entiteettisuhteet

Jokaisella entiteettiparilla, jolla voi olla 1:N-suhde, voi olla useita 1:N-suhteita entiteettien välillä. Yleensä kuitenkin vain yhtä näistä suhteista pidetään ylätason entiteettisuhteena.

Ylätason entiteettisuhde on mikä tahansa 1:N-entiteettisuhde, jossa seuraavan taulukon **ylätason** sarakkeen yhden limittäisyysasetuksen arvo on tosi.

|Toiminto|Ylätaso|Ei ylätasoa|  
|------------|--------------|------------------|  
|**Delegoi**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  
|**Poista**|Kaikki limittäin|Poista linkki<br />Rajoita|  
|**Määritä ylätaso uudelleen**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  
|**Jaa**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  
|**Poista jako**|Kaikki limittäin<br />Käyttäjän omistamien limittäminen<br />Limittäisyys|Ei mitään limittäin|  

Jos luot esimerkiksi uuden mukautetun entiteetin ja lisäät 1:N-entiteettisuhteen ja asiakkaan entiteetin, jossa mukautettu entiteetti on liittyvä entiteetti, voit määrittää kyseisen entiteettisuhteen toiminnot niin, että ne käyttävät **Ylätaso**-sarakkeen asetuksia. Jos lisäät myöhemmin toisen 1:N-entiteettisuhteen niin, että mukautettu entiteetti on viittaava entiteetti, voit määrittää toiminnot vain **Ei ylätasoa** -sarakkeen asetusten käyttöä varten.

Yleensä tämä tarkoittaa sitä, että jokaisella entiteettiparilla on vain yksi ylätason suhde. Joissakin tapauksissa liittyvän entiteetin haku voi sallia suhteelle useita entiteettityyppejä.

Entiteetillä voi esimerkiksi olla Asiakas-haku, joka voi viitata joko yhteyshenkilö- tai asiakasentiteettiin. Käytettävissä on kaksi erilaista ylätason 1:N-entiteettisuhdetta.

Aktiviteettientiteetillä on samanlainen entiteettien ylätason entiteettisuhteiden joukko, joka voidaan liittää Liittyy-hakukentän avulla.

<a name="BKMK_RelationshipBehaviorLimitations"></a>   

### <a name="limitations-on-behaviors-you-can-set"></a>Rajoituksia asetettaviin toimintatapoihin
  
Ylätason suhteiden vuoksi entiteettisuhteiden määrittämisessä on tiettyjä rajoituksia, jotka on hyvä pitää mielessä.  
  
- Mukautettu entiteetti ei voi olla ensisijainen entiteetti sellaisessa suhteessa, jossa on siihen liittyvä limittäinen järjestelmäentiteetti. Tämän vuoksi ensisijaisen, mukautetun entiteetin ja siihen liittyvän järjestelmäentiteetin välillä ei voi olla suhdetta, jossa jokin toiminnon määritys on **Kaikki limittäin**, **Limittäin aktiivinen** tai **Käyttäjän limittäin**.  
- Uuden suhteen toimintojen määritys ei voi olla **Kaikki limittäin** eikä **Limittäin aktiivinen** tai **Käyttäjän limittäin**, jos suhteen liittyvä entiteetti on jo liittyvänä entiteettinä jossakin toisessa suhteessa, jonka toimintojen määritys on **Kaikki limittäin**, **Limittäin aktiivinen** tai **Käyttäjän limittäin**. Näin vältetään sellaisten suhteiden muodostuminen, joissa on monta ylätasoa.  

### <a name="see-also"></a>Katso myös

[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -suhteen luominen ja muokkaaminen](create-edit-1n-relationships.md)<br />
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen PowerApps-portaalissa](create-edit-1n-relationships-portal.md)<br />
[NN: (monta moneen) -suhteen luominen](create-edit-nn-relationships.md)

