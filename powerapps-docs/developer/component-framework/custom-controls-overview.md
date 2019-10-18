---
title: Mitä koodi komponentit ovat? | MicrosoftDocs
description: Powerappsin komponentti kehyksen avulla voit luoda koodi komponentteja, joiden avulla käyttäjät voivat tarkastella ja käsitellä tietoja lomakkeissa, näkymissä ja koonti näytöissä.
manager: kvivek
ms.date: 09/05/2019
ms.service: powerapps
ms.topic: article
ms.assetid: 135481cd-4583-4e49-8f58-02f32a9b054a
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: 08a2043dfb92634837c367e664306d9c100632d6
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72346965"
---
# <a name="what-are-code-components"></a>Mitä ovat koodi komponentit

Koodi komponentit ovat ratkaisun osien tyyppejä, mikä tarkoittaa sitä, että ne voidaan sisällyttää ratkaisun tiedostoon ja asentaa eri ympäristöihin. Lisä tietoja: [Pakkaa ja Jaa laajennuksia ratkaisujen avulla](https://docs.microsoft.com/dynamics365/customer-engagement/developer/package-distribute-extensions-use-solutions).

Lisää koodi komponentteja sisällyttämällä ne ratkaisuun ja tuomalla ne sitten Common Data Service. Kun komponentit ovat Common Data Service, järjestelmänvalvojat ja järjestelmän mukauttajat voivat määrittää kenttiä, aliruudukoita, näkymiä ja koonti näytön aliruudukoita, joita käytetään oletus komponenttien sijaan. Voit myös lisätä nämä koodi komponentit pohjaan ja sovelluksiin. 

Koodi komponentit koostuvat kolmesta elementistä:

1. [Luettelo](#manifest)
2. [Komponentin toteutus Kirjasto](#component-implementation-library)
3. [Resources](#resources)

## <a name="manifest"></a>Luettelo

Luettelotiedosto on metatietotiedosto, joka määrittää osan. Se on XML-tiedosto, joka kuvaa seuraavaa:

- Komponentin nimi.
- Tieto tyyppi, joka voidaan määrittää, joko kenttä tai tieto joukko.
- Ominaisuudet, jotka voidaan määrittää sovelluksessa, kun osa lisätään.
- Luettelo resurssi tiedostoista, joita komponentti tarvitsee. 
- Component toteutus Libraryn typescript-funktio, joka palauttaa objektin, joka käyttää vaadittua komponentti liittymää.

Kun käyttäjä määrittää koodi komponentin, luettelo tiedoston tiedot suodattaessaan käytettävissä olevat osat niin, että vain kelvolliset kontekstin osat ovat käytettävissä määritystä varten. Komponentin luettelo tiedostossa määritetyt ominaisuudet hahmonnetaan määritys kenttinä, jotta komponentin määrittävä käyttäjä voi määrittää arvot. Nämä ominaisuus arvot ovat tämän jälkeen komponentin käytettävissä suorituksen aikana. Lisä tietoja: [luettelon rakenne viittaus](manifest-schema-reference/index.md)

## <a name="component-implementation-library"></a>Komponentin toteutus Kirjasto

Komponentti kirjaston toteuttaminen on yksi tärkeimmistä vaiheista, kun kehität koodi komponentteja PowerApps Component Frameworkin avulla. Kehittäjät voivat käyttää komponentti kirjastoa käyttäen TypeScript-kohdetta. Jokaisella koodi osalla on oltava Kirjasto, joka sisältää-nimisen funktio-määrityksen, joka palauttaa objektin, joka toteuttaa koodi komponentti liittymässä kuvatut menetelmät. 

Objekti toteuttaa seuraavat menetelmät:

- [init](reference/control/init.md) (pakollinen)
- [Updateview](reference/control/updateview.md) (pakollinen)
- [Gettuotokset](reference/control/getoutputs.md) (valinnainen)
- [tuhoa](reference/control/destroy.md) (pakollinen)

Nämä menetelmät ohjaavat koodi komponentin elin kaarta.

### <a name="page-load"></a>Sivun lataaminen

Kun sivu latautuu, sovellus vaatii toimiakseen objektin. Käyttämällä luettelo tiedoston tietoja koodi hakee objektin soittamalla:

```js
var obj =  new <"namespace on manifest">.<"constructor on manifest">();
```

Jos luettelon nimi tila-ja konstruktorin arvot ovat `SampleNameSpace` ja `LinearInputComponent`, objektin esiintymän muodostus koodi on seuraava:

```js
var controlObj = new SampleNameSpace.LinearInputComponent();
```

Kun sivu on valmis, se alustaa komponentin kutsumalla [init](reference/control/init.md) -menetelmää parametrina.

```js
controlObj.init(context,notifyOutputChanged,state,container);
```

|Parametri|Kuvaus|
|---|---|
|kontekstissa| Sisältää kaikki tiedot siitä, miten komponentti on määritetty ja kaikki parametrit, joita voidaan käyttää osassa yhdessä [Powerapps Component Framework-ohjelmointi raja pintojen](reference/index.md)kanssa. @No__t_0 voidaan käyttää esimerkiksi syöte-ominaisuuden käyttämiseen.|
|notifyOutputChanged |Hälyttää kehikon, kun koodi komponentilla on uusia tuotoksia valmiina noudettavissa asynkronisesti.|
|tila|Sisältää komponentti tietoja edellisen sivun kuormituksesta nykyisessä istunnossa, jos komponentti on nimenomaisesti tallentanut sen aiemmin käyttäen [Setcontrolstate](reference/mode/setcontrolstate.md) -menetelmää.|
|säilön|HTML-div-elementti, johon kehittäjät ja sovelluksen tekijät voivat liittää komponentin määrittävän käyttö liittymän HTML-elementit.|

### <a name="user-changes-data"></a>Käyttäjä muuttaa tietoja

Kun sivu latautuu, osa näyttää tiedot, kunnes käyttäjä on vuoro vaikutuksessa komponentin kanssa tietojen muuttamiseksi. Kun tämä tapahtuu, sinun on kutsuttava menetelmää, joka välitettiin muodossa *notifyoutputchanged* parametri [init](reference/control/init.md) -menetelmässä. Kun käytät tätä menetelmää, ympäristö reagoi sitten kutsumalla [Gettuotokset](reference/control/getoutputs.md) -menetelmää. [Gettuotokset](reference/control/getoutputs.md) -menetelmä palauttaa arvot, jotka ovat käyttäjän tekemiä muutoksia. Kenttä komponentissa tämä on tavallisesti komponentin uusi arvo.

### <a name="app-changes-data"></a>Sovellus muuttaa tietoja

Jos ympäristö muuttaa tietoja, se kutsuu komponentin [Updateview](reference/control/updateview.md) -menetelmää ja välittää uuden Context-objektin parametrina. Tämä menetelmä tulee ottaa käyttöön, jotta komponentissa näytettävät arvot voidaan päivittää.

### <a name="page-close"></a>Sivun sulkeminen

Aina, kun käyttäjä astuu sivun ulkopuolelle, koodi komponentti menettää vaikutus alueen, ja kaikki kyseisellä sivulla varatut muisti kohteet tyhjennetään. Jotkin selaimen toteutus mekanismiin perustuvat menetelmät saattavat kuitenkin jäädä ja kuluttaa muistia. Nämä ovat yleensä tapahtumakäsittelijöitä. Jos käyttäjä haluaa tallentaa nämä tiedot, hänen tulee ottaa käyttöön [Setcontrolstate](reference/mode/setcontrolstate.md) -menetelmä, jotta tiedot annetaan seuraavan kerran saman istunnon aikana.

Kehittäjien tulee ottaa käyttöön [tuhota](reference/control/destroy.md) -menetelmä, jota kutsutaan, kun sivu suljetaan, poistaaksesi kaikki siivous koodit, kuten tapahtumakäsittelijät.

## <a name="resources"></a>Resursseja

Kullakin koodi osalla tulee olla resurssi tiedosto visualisoinnin muodostamista varten. Voit määrittää resurssi tiedoston luettelossa. Luettelo tiedoston resurssi solmu viittaa resursseihin, joita komponentti edellyttää visualisoinnin toteutukseen. Lisä tietoja: [Resources-alkio](manifest-schema-reference/resources.md)

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Luo ja Rakenna koodi komponentti](create-custom-controls-using-pcf.md)
