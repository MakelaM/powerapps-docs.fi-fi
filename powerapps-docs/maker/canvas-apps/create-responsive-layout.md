---
title: Luo pohjaan perustuvat sovellukset reagoiva asettelut | Microsoft Docs
description: Lisätietoja korkeus, leveys, X ja Y-ominaisuudet määritetään ohjausobjektien pohjaan perustuvat sovellukset
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/28/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 776a542d8e790cc9ae3591b6cda9f08d0d347ef7
ms.sourcegitcommit: 38f91423933749ca19557f29e86cd8f5ad06e1eb
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/05/2019
ms.locfileid: "59042774"
---
# <a name="create-responsive-layouts-in-canvas-apps"></a>Luo reagoiva asettelut pohjaan perustuvat sovellukset

Ennen kuin luot powerappsissa pohjaan perustuvan sovelluksen, voit määrittää mukauttaa sovellusta puhelimella tai tabletilla. Tämä valinta määrittää kokoa ja muotoa, jonka luot sovelluksen pohjan.

Kun valinta, voit tehdä joitakin vaihtoehtoja, jos valitset **tiedoston** > **sovellusasetukset** > **näytön koko + suunta**. Voit valita pysty- tai vaakasuunnassa ja näyttökokoon (vain tablet). Voit myös lukita tai kuvasuhteen lukituksen ja tue laitteen (tai ei).

Vaihtoehdot käsitteisiin jokaisen suunnittelet näytön asetteluja teet vaihtoehdon. Jos sovellus suoritetaan laitteessa, jonka eri koko tai verkossa, koko asettelun skaalautuu Sovita näyttöön, jossa sovellus on käynnissä. Jos sovellus, joka on suunniteltu puhelimella toimii suuri selainikkunassa, esimerkiksi sovelluksen skaalautuu korvaamaan ja näyttää sen tilaa Ylikokoinen. Sovellus ei voi hyödyntää muita kuvapistettä useita ohjausobjekteja tai enemmän sisältöä.

Jos luot reagoiva asettelu, ohjausobjektit voivat vastata eri laitteille tai ikkunan koon, joten eri kokemuksia voit luonnolliseen. Jotta reagoiva asettelu, säätää joitakin asetuksia ja lausekkeiden kaikkialla sovelluksessasi. 

## <a name="disable-scale-to-fit"></a>Sovita käytöstä

Voit määrittää jokaisesta näytöstä niin, että sen asettelu sopeutuu todellinen tilaan, jossa sovellus on käynnissä.

Sovelluksen poistaminen käytöstä reagoinnin aktivoimalla **Sovita** asetus, joka on oletusarvon mukaan käytössä. Kun otat tämän asetuksen käytöstä, voit myös poistaa käytöstä **lukitse kuvasuhde** koska enää suunnittelet näytön muodon. (Voit edelleen määrittää tukeeko sovelluksesi laitteen kierron.)

![Poista käytöstä asteikon mukaan-asetus](media/create-responsive-layout/scale-to-fit-off.png)

Jotta sovelluksesi reagoiva, sinun on tehtävä lisätoimia, mutta tämä muutos on ensimmäinen vaihe että reagoinnin on mahdollista.

## <a name="understand-app-and-screen-dimensions"></a>Tutustu sovelluksen ja näytön dimensiot

Jotta sovelluksesi asetteluja näytön dimensioiden muutokset vastata, kirjoittaa kaavoja, jotka käyttävät **leveys** ja **korkeus** näytön ominaisuuksiin. Näytä nämä ominaisuudet, Avaa sovellus PowerApps Studio ja valitse sitten näyttöön. Nämä ominaisuudet oletusarvon kaavat näkyvät **lisäasetukset** välilehti oikeanpuoleisessa ruudussa.

**Leveys** = `Max(App.Width, App.DesignWidth)`

**Korkeus** = `Max(App.Height, App.DesignHeight)`

Nämä kaavat viittaavat **leveys**, **korkeus**, **DesignWidth**, ja **DesignHeight** sovelluksen ominaisuudet. Sovelluksen **leveys** ja **korkeus** ominaisuudet vastaavat dimensioita laitteessa tai selaimessa ikkunan, jossa sovellus on käynnissä. Jos käyttäjä muuttaa selainikkuna (tai pyörii laitteen, jos olet poistanut käytöstä **lukitse kuvasuhde**), näiden ominaisuuksien arvoja dynaamisesti. Näytön kaavat **leveys** ja **korkeus** ominaisuudet ovat arvioitaessa uudelleen, kun nämä arvot muuttuvat.

**DesignWidth** ja **DesignHeight** ominaisuudet tulevat dimensioista, jotka määrität **näytön koko + suunta** ruudussa **sovelluksen asetukset** . Jos valitset puhelinasettelun pystysuunta, esimerkiksi **DesignWidth** on 640, ja **DesignHeight** on 1136.

Kun niitä käytetään näytön kaavoissa **leveys** ja **korkeus** ominaisuuksia, voit ajatella **DesignWidth** ja **DesignHeight** kuin pienin dimensioita, jolle Suunnittele sovellus. Jos sovelluksesi käytettävissä todellinen alue on pienempi kuin pienin nämä mitat, näytön kaavoja **leveys** ja **korkeus** ominaisuudet varmistaa, että niiden arvojen ei tule mikä tahansa pienempi kuin enimmäisarvot. Käyttäjä on tässä tapauksessa siirry tarkastella kaikkia näytön sisällön.

Kun olet muodostanut sovelluksesi **DesignWidth** ja **DesignHeight**, eivät (useimmissa tapauksissa) täytyy muuttaa kunkin näytön oletusarvon kaavoja **leveys** ja **Korkeus** ominaisuudet. Myöhemmin tässä aiheessa käsitellään tapauksia, jossa haluat ehkä mukauttaa nämä kaavat.

## <a name="use-formulas-for-dynamic-layout"></a>Käyttää kaavoja dynaamisen asettelun

Jos haluat luoda reagoivan rakenteen, Etsi ja kunkin ohjausobjektin kokoa sijaan absoluuttinen () koordinaatti vakioarvot kaavojen avulla. Nämä kaavat express kunkin ohjausobjektin sijainti ja koko näytön kokoa tai suhteessa muita ohjausobjekteja.

> [!IMPORTANT]
> Kun kirjoitat kaavoja **X**, **Y**, **leveys** ja **korkeus** ohjausobjektin ominaisuuksia, kaavojen korvataan kanssa vakioarvot, jos vedät ohjausobjektin myöhemmin kangas-editorissa. Kun käynnistät kaavojen avulla voit saavuttaa dynaamisen asettelun, vältä vetämällä ohjausobjekteja.

Yksinkertaisin tapauksessa yksi ohjausobjekti täyttää koko näytön. Luo tämä tehoste, Määritä ohjausobjektin ominaisuuksia nämä arvot:

| Ominaisuus      | Value            |
|--------|---------------|
| **X**      | 0             |
| **Y**      | 0             |
| **Leveys**  | `Parent.Width`  |
| **Korkeus** | `Parent.Height` |

Nämä kaavat käyttävät **pääkohde** operaattori. Näyttö, sijoitettu ohjausobjektin **pääkohde** näytön viittaa. Ominaisuusarvoja, jossa ohjausobjekti näkyy vasemmassa yläkulmassa näytön (0, 0) ja sama **leveys** ja **korkeus** kuin näytön.

Tämän aiheen näitä periaatteita sovellat (ja **pääkohde** operaattorin) sijaintia ohjausobjektien muut säilöt, kuten valikoimat, ryhmän ohjausobjekteja ja komponentteja.

Vaihtoehtoisesti ohjausobjektin lisätä vain näytön yläosassa. Luo tämä tehoste **korkeus** ominaisuudeksi **Parent.Height** / 2, ja jätä muissa kaavoissa ennallaan.

Jos haluat toisen ohjausobjektin täyttämään alaosassa puolet samassa näytössä, voi tehdä vähintään kaksi lähestymistapoja sen kaavojen luomisesta. Yksinkertaisuuden vuoksi voi kestää tätä lähestymistapaa:

| Ohjausobjekti | Ominaisuus | Kaava           |
|-|----------|-------------------|
| **Upper** | **X**        | 0                 |
| **Upper** | **Y**        | 0                 |
| **Upper** | **Leveys**    | `Parent.Width`      |
| **Upper** | **Korkeus**   | `Parent.Height / 2` |
| **Lower** | **X**        | 0                 |
| **Lower** | **Y**        | `Parent.Height / 2` |
| **Lower** | **Leveys**    | `Parent.Width`      |
| **Lower** | **Korkeus**   | `Parent.Height / 2` |

![Ylempi ja Pienennä ohjausobjekti](media/create-responsive-layout/dynamic-layout.png)

Tämä määritys päästä siitä, että haluat, mutta on muokattava kukin kaava, jos voit muuttaa ohjausobjektien suhteellista kokoa. Voit esimerkiksi päättää, että yläreunan ohjausobjektin tulee vallata vain yläreunan kolmannes näytön täyttämisen pienempi kahden kolmasosan alas-ohjausobjektin kanssa. 

Luomiseen, jotka vaikuttavat on päivitettävä **korkeus** -ominaisuuden **Upper** ohjausobjektin ja **Y** ja **korkeus** ominaisuudet **Pienempi** ohjausobjektin. Harkitse sen sijaan, kaavojen kirjoittamisesta **pienempi** sekä hallita **Upper** ohjausobjektin (ja itse), kuten seuraavassa esimerkissä:


| Ohjausobjekti | Ominaisuus | Kaava           |
|-|----------|-------------------|
| **Upper** | **X**        | 0                 |
| **Upper** | **Y**        | 0                 |
| **Upper** | **Leveys**    | `Parent.Width`      |
| **Upper** | **Korkeus**   | `Parent.Height / 2` |
| **Lower** | **X**        | 0                       |
| **Lower** | **Y**        | `Upper.Y + Upper.Height`  |
| **Lower** | **Leveys**    | `Parent.Width`            |
| **Lower** | **Korkeus**   | `Parent.Height - Lower.Y` |

![Ylempi ja alemman suhteellisen koon muuttaminen](media/create-responsive-layout/dynamic-layout2.png)

Nämä kaavat paikassa, sinun on vain muutos **korkeus** -ominaisuuden **Upper** ohjausobjektin express eri murtoluvun näytön korkeus. **Pienempi** ohjausobjekti siirtää ja koko muuttuu, jotta muutos otetaan automaattisesti.

Voit määrittää nämä kaavan mallit ilmaisemisen common asettelu välisiä ohjausobjekti nimeltä **C**, ja sen pääkohde tai rinnakkaiskohde ohjausobjekti nimeltä **D**.

| C- ja sen ylätason suhde | Ominaisuus | Kaava | Kuva |
|--|--|--|--|
| **C** täyttää ylätason leveyden jossa *N* | **X**| *N* | ![Esimerkki ylemmän tason C täyttöä leveys](media/create-responsive-layout/c1.png) |
|  | **Leveys** | `Parent.Width - (N * 2)` |  |
| **C** täyttää ylä-ja korkeus reunukseen *N* | **Y** | *N* | ![Esimerkki ylemmän tason C täyttöä korkeus](media/create-responsive-layout/c2.png) |
|  | **Korkeus** | `Parent.Height - (N * 2)` |  |
| **C** ylä-ja oikeaan reunaan reunukseen paikkaa *N* | **X** | `Parent.Width - (C.Width + N)` | ![Esimerkki C tasaaminen reunan ylemmän tason mukaan](media/create-responsive-layout/c3.png) |
| **C** alareunan ylätason reunukseen paikkaa *N* | **Y** | `Parent.Height - (C.Height + N)` | ![Esimerkki C tasaaminen reunan ylemmän tason mukaan](media/create-responsive-layout/c4.png) |
| **C** keskitetty vaakasuunnassa pääkohde | **X** | `(Parent.Width - C.Width) / 2` | ![Esimerkki keskitetty vaakasuunnassa ylemmän tason C](media/create-responsive-layout/c5.png) |
| **C** keskitetty pystysuunnassa pääkohde | **Y** | `(Parent.Height - C.Height) / 2` | ![Esimerkki keskitetty pystysuunnassa ylemmän tason C](media/create-responsive-layout/c6.png) |

| C- ja D välinen suhde | Ominaisuus | Kaava | Kuva |
|--|--|--|--|
| **C** tasattu vaakasuunnassa kanssa **D** ja leveys on sama kuin **D** | **X** | `D.X` | ![Esimerkiksi malli](media/create-responsive-layout/d1.png) |
|  | **Leveys**    | `D.Width` |  |
| **C** pystysuunnassa tasattu kanssa **D** ja samankorkuisiksi kuin **D**  | **Y** | `D.Y` | ![Esimerkiksi malli](media/create-responsive-layout/d2.png) |
|  | **Korkeus** | `D.Height` |  |
| Oikean reunan **C** oikeassa reunassa paikkaa **D** | **X** | `D.X + D.Width - C.Width` | ![Esimerkiksi malli](media/create-responsive-layout/d3.png) |
| Alhaalla reunan **C** alareunan paikkaa **D** | **Y** | `D.Y + D.Height - C.Height` | ![Esimerkiksi malli](media/create-responsive-layout/d4.png) |
| **C** keskitetty vaakasuunnassa liittyen **D** | **X** | `D.X + (D.Width - C.Width) / 2`  | ![Esimerkiksi malli](media/create-responsive-layout/d5.png) |
| **C** keskitetty pystysuunnassa liittyen **D** | **Y** | `D.Y + (D.Height - C.Height) /2` | ![Esimerkiksi malli](media/create-responsive-layout/d6.png) |
| **C** sijoittaa oikealla **D** kanssa N väli | **X** | `D.X + D.Width - N` | ![Esimerkiksi malli](media/create-responsive-layout/d7.png) |
| **C** sijoittaa alla **D** kanssa väli *N*             | **Y** | `D.Y + D.Height + N` | ![Esimerkiksi malli](media/create-responsive-layout/d8.png) |
| **C** täyttää väli **D** ja oikean reunan pääkohde | **X** | `D.X + D.Width` | ![Esimerkiksi malli](media/create-responsive-layout/d9.png) |
|  | **Leveys** | `Parent.Width - C.X` |  |
| **C** täyttää väli **D** ja alhaalla reunan pääkohde | Y | `D.Y + D.Height` | ![Esimerkiksi malli](media/create-responsive-layout/d10.png) |

## <a name="hierarchical-layout"></a>Hierarkkisia asettelu

Kun olet muodostanut näyttöjä, jotka sisältävät useita ohjausobjekteja, siitä tulee kätevämpää (tai tarpeen jopa) sijainti ohjausobjekteja pääohjausobjektiin suhteessa sen sijaan, suhteessa näytön tai ohjausobjektin rinnakkaiskohde. Järjestämällä ohjausobjektien hierarkkinen rakenne tietoja, voit tehdä kaavojen helpompi kirjoittaa ja Ylläpidä.

### <a name="galleries"></a>Valikoimat

Jos käytät valikoiman sovelluksessa, sinun tulee Asettele ohjausobjekteille valikoiman mallipohjaa. Voit sijoittaa nämä ohjausobjektit kirjoitettaessa kaavoja, jotka käyttävät mukaan **pääkohde** operaattoria, joka viittaa valikoiman mallipohja. Valikoiman mallipohja ohjausobjekteille, kaavojen avulla **Parent.TemplateHeight** ja **Parent.TemplateWidth** ominaisuudet; Älä käytä **Parent.Width** ja  **Parent.Height**, jotka viittaavat valikoiman kokoa.

![Mallin leveys ja korkeus pystysuuntainen valikoima](media/create-responsive-layout/gallery-vertical.png)

### <a name="enhanced-group-control"></a>Parannettu ryhmän hallintaa

Voit käyttää kokeellista ominaisuutta, parannettu **ryhmän** ohjausobjektin parent-ohjausobjektina. Jos haluat ottaa tämän ominaisuuden käyttöön, valitse **tiedoston** > **sovellusasetukset** > **lisäasetukset**.

Harkitse otsikon näytön yläreunassa esimerkki. On yleistä, että otsikko, jossa on otsikko ja useita kuvakkeita, jolla käyttäjät voivat käyttää. Voit luoda otsikon käyttämällä parannetun **ryhmän** ohjausobjekti, joka sisältää **nimen** ohjausobjektin ja kaksi **kuvake** ohjausobjekteja:

![Käyttäen ryhmän ylä-Esimerkki](media/create-responsive-layout/header-group.png)

Määritä näiden ohjausobjektien ominaisuudet Nämä arvot:

| Ominaisuus | Otsikko | Valikko | Sulje | Otsikko |
|--|--|--|--|--|
| **X** | 0  | 0 | `Parent.Width - Close.Width` | `Menu.X + Menu.Width` |
| **Y** | 0 | 0 | 0 | 0 |
| **Leveys**  | `Parent.Width` | `Parent.Height` | `Parent.Height` | `Close.X - Title.X` |
| **Korkeus** | 64 | `Parent.Height` | `Parent.Height` | `Parent.Height` |

Varten **otsikon** ohjausobjektin `Parent` näytön viittaa. Muiden `Parent` viittaa **otsikon** ohjausobjektin.

Nämä kaavat on kirjoitettu, voit muuttaa kokoa tai sijaintia **otsikon** ohjausobjektin muuttamalla sen ominaisuudet, kaavoja. Koko ja sijainti aliohjausobjektien säädetään automaattisesti vastaavasti.

### <a name="components"></a>Osat

Jos käytät toista kokeellinen ominaisuutta nimeltä osia, voit luoda rakenneosia ja käyttää niitä uudelleen kaikkialla sovelluksessasi. Kuten **ryhmän** ohjausobjektin ohjausobjekteja, jotka voit sijoittaa komponentti tulee pohjaaminen niiden sijainti ja koko kaavoja `Parent.Width` ja `Parent.Height`, jotka viittaavat osa kokoa. Lisätietoja: [Luo osa](create-component.md).

## <a name="adapting-layout-for-device-size-and-orientation"></a>Laitteen kokoa ja suuntaa mukauttamiseksi asettelu

Tähän mennessä olet oppinut luomaan käytettävissä olevan tilan vastaus kunkin ohjausobjektin koon muuttaminen, kun pitäminen ohjausobjekteja tasattu toisiinsa kaavojen avulla. Mutta ehkä haluat tai muutokset suurempi asettelu vastauksena eri laitetta koon ja suuntia. Kun laite on vaakasuuntainen pystysuuntaisesta, kiertää esimerkiksi, haluat ehkä vaihtaa vaaka yksi pystysuuntainen asettelu. Suurempi laitteessa voit näyttää enemmän sisältöä tai järjestää sen enemmän kiinnostavia asettelun. Pienempi-laite joudut ehkä jakaa sisältöä ylöspäin useita näyttöjä.

### <a name="device-orientation"></a>Laitteen suunta

Oletus-kaavoja näytölle **leveys** ja **korkeus** ominaisuudet kuin tämä aihe on kuvattu, eivät välttämättä hyvä kokemuksen tarjoamiseksi Jos käyttäjä kiertää laite. Sovelluksen, joka on suunniteltu puhelinta pystysuunnassa on esimerkiksi **DesignWidth** 640- ja **DesignHeight** -1136. Samaa sovellusta puhelimessa vaakasuunnassa on tämän ominaisuuden:

- Näytön **leveys** asetuksena on `Max(App.Width, App.DesignWidth)`. Sovelluksen **leveys** (1136) on suurempi kuin sen **DesignWidth** (640), joten kaavan tulos 1136.
- Näytön **korkeus** asetuksena on `Max(App.Height, App.DesignHeight)`. Sovelluksen **korkeus** (640) on pienempi kuin sen **DesignHeight** (1136), joten kaavan tulos 1136.

Vaikeaa **korkeus** 1136- ja laitteen korkeuteen (tässä Tämä suunta) 640, käyttäjän on Vieritä näytön pystysuunnassa näyttämään kaikki sen sisältö, mikä ei ehkä käyttökokemus, joka halutaan.

Näytön mukauttamiseksi **leveys** ja **korkeus** ominaisuudet laitteen-asentoon, voit määrittää nämä kaavat:

**Leveys** = `Max(App.Width, If(App.Width < App.Height, App.DesignWidth, App.DesignHeight))`

**Korkeus** = `Max(App.Height, If(App.Width < App.Height, App.DesignHeight, App.DesignWidth))`

Nämä kaavat Vaihda sovelluksen **DesignWidth** ja **DesignHeight** perusteella, onko laitteen leveys on pienempi kuin sen korkeutta (pystysuunnassa) tai suurempi kuin sen korkeutta (vaakasuunnassa) .

Kun säädät näytön **leveys** ja **korkeus** kaavoja, voit myös halutessasi järjestää käyttämään tilaa paremmin näytön ohjausobjektit. Jos kaksi ohjausobjekteihin kattaa puolet näytöstä, voit pinon ne pystysuunnassa pysty mutta järjestää ne rinnakkain vaakanäkymässä.

> [!NOTE]
> Vaakasuunnassa **Upper** ja **pienempi** ohjausobjektit näkyvät vasemman ja oikean ohjausobjekteja.

| Ohjausobjekti | Ominaisuus | Kaava |
|--|----------|---|
| **Upper** | **X** | 0 |
| **Upper** | **Y** | 0 |
| **Upper** | **Leveys** | `If(Parent.Width < Parent.Height, Parent.Width, Parent.Width / 2)` |
| **Upper** | **Korkeus**   | `If(Parent.Width < Parent.Height, Parent.Height / 2, Parent.Height)` |
| **Lower** | X | `If(Parent.Width < Parent.Height, 0, Upper.X + Upper.Width)`  |
| **Lower** | Y | `If(Parent.Width < Parent.Height, Upper.Y + Upper.Height, 0)` |
| **Lower** | **Leveys** | `Parent.Width - Lower.X` |
| **Lower** | **Korkeus** | `Parent.Height - Lower.Y` |

![lausekkeita mukauttamiseksi pystysuuntaisia](media/create-responsive-layout/portrait.png)

![lausekkeita mukauttamiseksi vaakasuunnassa](media/create-responsive-layout/landscape.png)

### <a name="known-limitations"></a>Tunnetut rajoitukset

Luontiympäristö pohjan ei vastaa luotu koon muuttaminen kaavat. Testattava reagoiva toiminta Tallenna ja julkaise sovelluksesi ja avaa se laitteissa tai selainikkunat eri kokoja ja suuntia.

Jos kirjoitat lausekkeita tai kaavat **X**, **Y**, **leveys**, ja **korkeus** ominaisuuksia ohjausobjektin, ne korvata lausekkeita tai kaavoja, jos myöhemmin Vedä ohjausobjekti eri sijaintia tai muuttaa ohjausobjektin kokoa vetämällä sen reunaa.
