---
title: Luo reagoivia asetteluja kangas sovelluksissa | Microsoft Docs
description: Viite tietoja korkeus-, Leveys-, X-ja yn-ominaisuuksien määrittämisestä pohjaan perustuvien sovellusten ohjaus objekteissa
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm-msft
ms.date: 9/20/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: eee82691b288f21749fe58adbf02ab5ffc3bd8b4
ms.sourcegitcommit: 7016ff837eff2cb0985fc71edab95cbf99335677
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/20/2019
ms.locfileid: "71159869"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-responsive-layouts-in-canvas-apps"></a>Luo reagoivia asetteluja kangas sovelluksissa

Ennen kuin rakennat pohjaan sopivan sovelluksen Powerappsissa, voit määrittää, räätälöidäänkö sovellus puhelimelle vai tabletille. Tämä valinta määrittää sen piirto alustan koon ja muodon, jolle sovellus luodaan.

Kun olet tehnyt tämän valinnan, voit tehdä muutaman vaihto ehdon, jos valitset **tiedosto** > **sovelluksen asetukset** > **näytön koko + suunta**. Voit valita pysty-tai vaaka suunnan ja näytön koon (vain tabletti). Voit myös lukita kuva suhteen tai poistaa sen lukituksen ja tukea laitteen kiertoa (tai ei).

Nämä valinnat ovat jokaisen muun valinnan perustana, jota teet, kun suunnittelet näytön asetteluja. Jos sovelluksesi toimii eri kokoisena tai verkossa olevalla laitteella, koko ulkoasu skaalautuu siten, että se sopii siihen näyttöön, jossa sovellus on käynnissä. Jos puhelinta varten suunniteltu sovellus toimii suuressa selain ikkunassa, esimerkiksi sovellus skaalautuu ja näyttää ylimitoitettuja sen tilaa varten. Sovellus ei voi hyödyntää lisä pikseleitä näyttämällä enempää ohjaus objektien tai enemmän sisältöä.

Jos luot reagoivaa ulkoasua, ohjaus objekteilla voidaan vastata eri laitteisiin tai ikkunoiden kokoon, jolloin erilaiset kokemukset tuntuvat luonnollisemmalta. Jos haluat saavuttaa reagoivaa ulkoasua, säädät joitakin asetuksia ja kirjoitus lausekkeita koko sovelluksessa. 

## <a name="disable-scale-to-fit"></a>Poista skaalaus käytöstä

Voit määrittää jokaisen näytön niin, että sen ulkoasu mukautuu todelliseen tilaan, jossa sovellus on käynnissä.

Otat reagoivuuden käyttöön sammuttamalla sovelluksen **asteikon Sovita** -asetukseen, joka on oletus arvon mukaan käytössä. Kun poistat tämän asetuksen käytöstä, poistat myös **lukitus kuva suhteen** käytöstä, koska et enää pysty suunnittelemaan tiettyä näyttö muotoa. (Voit edelleen määrittää, tukeeko sovelluksesi laitteen kiertoa.)

![Poista skaalaus käytöstä asetuksen mukaiseksi](media/create-responsive-layout/scale-to-fit-off.png)

Jos haluat tehdä sovelluksestasi reagoivamman, sinun on ryhdyttävä lisä toimiin, mutta tämä muutos on ensimmäinen askel reagoivuuden tekemiseen.

## <a name="understand-app-and-screen-dimensions"></a>Tutustu sovelluksen ja näytön ulottuvuuksiin

Jos haluat, että sovelluksesi asettelut reagoivat näytön mittojen muutoksiin, kirjoitamme kaavoja, jotka käyttävät näytön **Leveys** -ja **Korkeus** -ominaisuuksia. Voit näyttää nämä ominaisuudet avaamalla sovelluksen PowerApps Studio ja valitsemalla sitten näytön. Näiden ominaisuuksien oletus kaavat näkyvät oikeanpuoleisen ruudun **lisä asetukset** -väli lehdellä.

**Width** = `Max(App.Width; App.DesignWidth)`

**Korkeus** = `Max(App.Height; App.DesignHeight)`

Nämä kaavat viittaavat sovelluksen **Width**-, **Height**-, **Designwidth**-ja **designheight** -ominaisuuksiin. Sovelluksen **Leveys** -ja **Korkeus** -ominaisuudet vastaavat laitteen tai selain ikkunan mittoja, joissa sovelluksesi on käynnissä. Jos käyttäjä muuttaa selain ikkunan kokoa (tai kääntää laitetta, jos olet poistanut **lukituksen suunnan**), näiden ominaisuuksien arvot muuttuvat dynaamisesti. Näytön **leveyden** ja **korkeuden** ominaisuuksien kaavat arvioidaan uudelleen, kun nämä arvot muuttuvat.

**Designwidth** -ja **designheight** -ominaisuudet tulevat dimensioista, jotka määrität **sovelluksen asetusten** **näytön koko + suunta** -ruudussa. Jos esimerkiksi valitset Puhelin asettelu pystysuunnassa, **Designwidth** on 640 ja **designheight** on 1136.

Koska niitä käytetään näytön **Leveys** -ja **Korkeus** -ominaisuuksien kaavoissa, voit ajatella **Designwidth** -ja **designheight** -mittoja vähimmäisdimensioina, joita varten suunnittelet sovelluksen. Jos sovelluksesi käytettävissä oleva alue on jopa pienempi kuin nämä vähimmäisulottuvuudet, näytön **leveyden** ja **korkeuden** ominaisuuksien kaavat varmistavat, että niiden arvot eivät ole pienempiä kuin vähimmäisarvot. Tässä tapa uksessa käyttäjän on vieritettävä näkymää, jotta näet kaiken näytön sisällön.

Kun olet vakiinnuttamaan sovelluksesi **Designwidth** -ja **designheight**-ominaisuudet, sinun ei tarvitse (useimmissa tapa uksissa) muuttaa oletus kaavoja kunkin näytön **Leveys** -ja **Korkeus** -ominaisuuksille. Myöhemmin tässä ohje aiheessa käsitellään tapa uksia, joissa saatat haluta mukauttaa näitä kaavoja.

## <a name="use-formulas-for-dynamic-layout"></a>Kaavojen käyttäminen dynaamisessa asettelulla

Voit luoda reagoivan rakenteen etsimällä ja muuttamalla kunkin ohjaus objektin kokoa kaavojen avulla absoluuttisten (vakio) koordinaatti arvojen sijaan. Nämä kaavat ilmaisevat kunkin ohjaus objektin sijainnin ja koon yleisen näytön koon tai muiden näytön ohjaus objektien suhteen.

> [!IMPORTANT]
> Kun kirjoitat kaavoja ohjaus objektin **X**-, **yn**-, **Width** -ja **Height** -ominaisuuksille, kaavat korvataan kiinteillä arvoilla, jos vedät ohjaus objektin sitten piirto alusta editorissa. Kun alat käyttää kaavoja dynaamisen rakenteen saavuttamiseksi, Vältä vetämällä ohjaus objektia.

Yksinkertaisin tapa uksessa yksi ohjaus objekti täyttää koko näytön. Voit luoda tämän vaikutuksen määrittämällä ohjaus objektin ominaisuudet näille arvoille:

| Ominaisuus      | Value            |
|--------|---------------|
| **X**      | `0`             |
| **Y**      | `0`             |
| **Leveys**  | `Parent.Width`  |
| **Korkeus** | `Parent.Height` |

Nämä kaavat käyttävät **pääoperaattoria** . Suoraan näytölle sijoitetun ohjaus objektin **pääkohde** viittaa näyttöön. Näiden ominaisuus arvojen avulla ohjaus objekti näkyy näytön vasemmassa yläkulmassa (0, 0) ja sen **Leveys** ja **Korkeus** ovat samat kuin näytössä.

Myöhemmin tässä ohje aiheessa käytät näitä periaatteita (ja **pääoperaattoria** ) muiden säilöjen, kuten valikoimien, ryhmä ohjaus objektien ja komponenttien, sisällä olevien ohjaus objektien sijaintiin.

Vaihtoehtoisesti ohjaus objekti voi täyttää vain näytön yläosan. Jos haluat luoda tämän tehosteen, valitse **Korkeus** -ominaisuudeksi **Parent. Height** /2 ja jätä muut kaavat ennalleen.

Jos haluat toisen ohjaus objektin täyttävän saman näytön alaosan, voit käyttää sen kaavoja vähintään kahdella muulla tavalla. Yksinkertaisuuden vuoksi tätä lähestymis tapaa voidaan käyttää:

| Ohjausobjekti | Ominaisuus | Kaava           |
|-|----------|-------------------|
| **Ylärajan** | **X**        | `0`                 |
| **Ylärajan** | **Y**        | `0`                 |
| **Ylärajan** | **Leveys**    | `Parent.Width`      |
| **Ylärajan** | **Korkeus**   | `Parent.Height / 2` |
| **Pienempi** | **X**        | `0`                 |
| **Pienempi** | **Y**        | `Parent.Height / 2` |
| **Pienempi** | **Leveys**    | `Parent.Width`      |
| **Pienempi** | **Korkeus**   | `Parent.Height / 2` |

![Ylempi ja alempi ohjaus objekti](media/create-responsive-layout/dynamic-layout.png)

Tämä määritys saavuttaa haluamasi vaikutuksen, mutta sinun on muokattava kutakin kaavaa, jos olet muuttanut mielesi ohjaus objektien suhteellisista koosta. Voit esimerkiksi päättää, että ylimmän ohjaus objektin tulee miehittää vain ylimmät kolmannes näytöstä, jolloin alin ohjaus objekti täyttää alemmat kaksi kolmasosaa. 

Jotta voit luoda tämän tehosteen, sinun on päivitettävä ylemmän ohjaus objektin **Korkeus** **-ominaisuus** sekä **alemman** ohjaus objektin **y:n** ja **korkeuden** ominaisuudet. Harkitse sen sijaan **alemman** ohjaus objektin kaavojen kirjoittamista **ylemmän** ohjaus objektin (ja itsensä) suhteen, kuten tässä esimerkissä:


| Ohjausobjekti | Ominaisuus | Kaava           |
|-|----------|-------------------|
| **Ylärajan** | **X**        | `0`                 |
| **Ylärajan** | **Y**        | `0`                 |
| **Ylärajan** | **Leveys**    | `Parent.Width`      |
| **Ylärajan** | **Korkeus**   | `Parent.Height / 2` |
| **Pienempi** | **X**        | `0`                       |
| **Pienempi** | **Y**        | `Upper.Y + Upper.Height`  |
| **Pienempi** | **Leveys**    | `Parent.Width`            |
| **Pienempi** | **Korkeus**   | `Parent.Height - Lower.Y` |

![Ylemmän ja alemman ohjaus objektin suhteellinen mitoitus](media/create-responsive-layout/dynamic-layout2.png)

Kun nämä kaavat ovat paikoillaan, sinun on muutettava **ylemmän** ohjaus objektin **Korkeus** -ominaisuutta vain ilmaisemaan eri murto-osa näytön korkeudesta. **Alemman** ohjaus objektin siirtäminen ja koon muuttaminen muuttuu automaattisesti tiliksi.

Voit käyttää näitä kaava malleja ilmaisemaan yleisiä rakenne suhteita ohjaus objektin, nimetyn **C**: n ja sen pääkohteen tai rinnakkaiskohteen ohjaus objektin välillä, jonka nimi on **D**.

| Suhde C:n ja sen pääkohteen välillä | Ominaisuus | Kaava | Kuva |
|--|--|--|--|
| **C** täyttää Pääobjektin leveyden, ja sen reunus on *N* | **X**| `N` | ![Esimerkki C-kohteen täyttö leveydestä](media/create-responsive-layout/c1.png) |
|  | **Leveys** | `Parent.Width - (N * 2)` |  |
| **C** täyttää pääkohteen korkeuden ja *N* reunuksen | **Y** | `N` | ![Esimerkki pääkohteen C täyttö korkeudesta](media/create-responsive-layout/c2.png) |
|  | **Korkeus** | `Parent.Height - (N * 2)` |  |
| **C** -linjassa pääkohteen oikean reunan kanssa, *n* -reuna | **X** | `Parent.Width - (C.Width + N)` | ![Esimerkki C-tasaamisesta pääkohteen reunan kanssa](media/create-responsive-layout/c3.png) |
| **C** -linjassa pääkohteen alareunan kanssa, *n* reuna | **Y** | `Parent.Height - (C.Height + N)` | ![Esimerkki C-tasaamisesta pääkohteen reunan kanssa](media/create-responsive-layout/c4.png) |
| **C** keskitetty vaaka suunnassa pääkohteelle | **X** | `(Parent.Width - C.Width) / 2` | ![Esimerkki C keskitetty vaaka suunnassa pääkohteelle](media/create-responsive-layout/c5.png) |
| **C** keskitetty pystysuunnassa pääkohteelle | **Y** | `(Parent.Height - C.Height) / 2` | ![Esimerkki C keskitetty pystysuunnassa pääkohteelle](media/create-responsive-layout/c6.png) |

| Suhde C:n ja D:n välillä | Ominaisuus | Kaava | Kuva |
|--|--|--|--|
| **C** vaaka suunnassa linjassa **d** ja sama leveys kuin **d** | **X** | `D.X` | ![Esimerkki mallista](media/create-responsive-layout/d1.png) |
|  | **Leveys**    | `D.Width` |  |
| **C** pystysuunnassa linjassa **d** ja sama korkeus kuin **d**  | **Y** | `D.Y` | ![Esimerkki mallista](media/create-responsive-layout/d2.png) |
|  | **Korkeus** | `D.Height` |  |
| Oikean reunan **C** -tasattu oikean reunan **D** kanssa | **X** | `D.X + D.Width - C.Width` | ![Esimerkki mallista](media/create-responsive-layout/d3.png) |
| **C** -reunan alareuna on tasattu alareunan **D** kanssa | **Y** | `D.Y + D.Height - C.Height` | ![Esimerkki mallista](media/create-responsive-layout/d4.png) |
| **C** keskitetty vaaka suunnassa suhteessa **D** | **X** | `D.X + (D.Width - C.Width) / 2`  | ![Esimerkki mallista](media/create-responsive-layout/d5.png) |
| **C** keskitetty pystysuunnassa suhteessa **D** | **Y** | `D.Y + (D.Height - C.Height) /2` | ![Esimerkki mallista](media/create-responsive-layout/d6.png) |
| **C** **-kohdan oikealla puolella, jonka** aukko on N | **X** | `D.X + D.Width + N` | ![Esimerkki mallista](media/create-responsive-layout/d7.png) |
| **C** on sijoitettu alle **D** , jonka rako on *N*             | **Y** | `D.Y + D.Height + N` | ![Esimerkki mallista](media/create-responsive-layout/d8.png) |
| **C** täyttää tilaa pääkohteen **D** ja oikean reunan välillä | **X** | `D.X + D.Width` | ![Esimerkki mallista](media/create-responsive-layout/d9.png) |
|  | **Leveys** | `Parent.Width - C.X` |  |
| **C** täyttää tilaa pääkohteen **D** ja alareunan välillä | Y | `D.Y + D.Height` | ![Esimerkki mallista](media/create-responsive-layout/d10.png) |

## <a name="hierarchical-layout"></a>Hierarkkinen ulkoasu

Kun rakennat näyttöjä, jotka sisältävät enemmän ohjaus objektia, niistä tulee entistä kätevämpää (tai jopa tarpeellista) ohjaus objektien sijaintiin suhteessa pääohjaus objektiin sen sijaan, että ne olisivat suhteessa näyttöön tai rinnakkaiset-ohjaus objektiin. Voit helpottaa kaavojen kirjoittamista ja ylläpitämistä järjestämällä ohjaus objektesi hierarkkiseen rakenteeseen.

### <a name="galleries"></a>Galleriat

Jos käytät valikoimaa sovelluksessasi, sinun on säädettävä ohjaus objekteista valikoiman mallissa. Voit sijoittaa nämä ohjaus objektin kirjoittamalla kaavoja, jotka käyttävät **pääoperaattoria** , joka viittaa valikoima malliin. Käytä valikoima-mallin ohjaus objektien kaavoissa **Parent. TemplateHeight** -ja **Parent. templatewidth** -ominaisuuksia. Älä käytä **pääkohdetta. Width** ja **Parent. Height**, jotka viittaavat valikoiman yleiseen kokoon.

![Pystysuuntainen valikoima, joka näyttää mallin leveyden ja korkeuden](media/create-responsive-layout/gallery-vertical.png)

### <a name="container-control"></a>Säiliön ohjaus objekti

Voit käyttää kokeellinen ominaisuus, **Container** -ohjaus objekti, pääohjaus objekti. Jos haluat ottaa tämän ominaisuuden käyttöön, valitse **tiedosto** > **sovelluksen asetusten** > **lisä asetukset**.

Harkitse esimerkin otsikkoa näytön yläreunassa. On tavallista, että otsikossa on otsikko ja useita kuvakkeita, joiden avulla käyttäjät voivat toimia. Voit luoda tällaisen otsikon käyttämällä **säilö** -ohjaus objektia, joka sisältää **Selite** -ohjaus objektin ja kaksi **kuvake** ohjaus objektia:

![Otsikko esimerkki ryhmän avulla](media/create-responsive-layout/header-group.png)

Voit määrittää näiden ohjaus objektien ominaisuudet seuraaviin arvoihin:

| Ominaisuus | Otsikko | Valikko | Sulje | Otsikko |
|--|--|--|--|--|
| **X** | `0`  | `0` | `Parent.Width - Close.Width` | `Menu.X + Menu.Width` |
| **Y** | `0` | `0` | `0` | `0` |
| **Leveys**  | `Parent.Width` | `Parent.Height` | `Parent.Height` | `Close.X - Title.X` |
| **Korkeus** | `64` | `Parent.Height` | `Parent.Height` | `Parent.Height` |

Viittaa **otsikko** - `Parent` ohjaus objektiin näytössä. Toisille `Parent` viittaa **otsikko** -ohjaus objektiin.

Kun olet kirjoittanut Nämä kaavat, voit muuttaa **otsikko** -ohjaus objektin kokoa tai sijaintia muuttamalla sen ominaisuuksien kaavoja. Aliohjausobjektien koot ja sijainnit mukauttavat automaattisesti vastaavasti.

### <a name="components"></a>Osat

Jos käytät jotakin muuta kokeellista toimintoa nimeltä Components, voit luoda rakenne osia ja käyttää niitä uudelleen koko sovelluksessasi. Kuten **Container** -ohjaus objektin yhteydessä, komponentissa sijoittamiesi ohjaus objektien sijainti ja koko perustuvat `Parent.Width` `Parent.Height`kaavoihin, jotka viittaavat komponentin kokoon. Lisätietoja: [Luo komponentti](create-component.md).

## <a name="adapting-layout-for-device-size-and-orientation"></a>Laitteen koon ja suunnan rakenteen mukauttaminen

Tähän mennessä olet oppinut käyttämään kaavoja kunkin ohjaus objektin koon muuttamiseen vasta uksena käytettävissä olevaan tilaan ja pitämällä ohjaus objektin tasattuina suhteessa toisiinsa. Saatat kuitenkin haluta tai tarvetta tehdä merkittävämpiä muutoksia vasta uksena eri laite kokoihin ja-suunta viivoihin. Kun laite käännetään esimerkiksi pystysuuntaisesta vaaka suunnassa, haluat ehkä vaihtaa pystysuuntaisesta asettelusta vaakasuuntaiseksi. Suuremmalla laitteella voit esittää enemmän sisältöä tai järjestää sen uudelleen niin, että se tarjoaa entistä miellyttävämpiä asetteluja. Pienemmällä laitteella saatat joutua jakamaan sisältöä useissa näytöissä.

### <a name="device-orientation"></a>Laitteen suunta

Näytön **Leveys** -ja **Korkeus** -ominaisuuksien oletus kaavat, kuten tässä aiemmin kuvatussa aiheessa, eivät välttämättä tarjoa hyviä käyttö kokemuksia, jos käyttäjä kääntää laitetta. Esimerkiksi pystysuunnassa puhelinta varten suunnitellulla sovelluksella on **Designwidth** -arvo 640 ja **designheight** -arvo 1136. Sama sovellus puhelimessa vaaka suunnassa sisältää seuraavat ominaisuus arvot:

- Näytön **leveyden** ominaisuudeksi on määritetty `Max(App.Width; App.DesignWidth)`. Sovelluksen **Leveys** (1136) on suurempi kuin sen **designwidth** (640), joten kaavan arvoksi on määritetty 1136.
- Näytön **Korkeus** -ominaisuudeksi on määritetty `Max(App.Height; App.DesignHeight)`. Sovelluksen **Korkeus** (640) on pienempi kuin sen **designheight** (1136), joten kaavan arvoksi on määritetty 1136.

Kun näytön **Korkeus** on 1136 ja laitteen korkeus (tässä suunnassa) on 640, käyttäjän on vieritettävä näyttöä pystysuunnassa näyttämään koko sisältö, mikä ei ehkä ole haluamasi kokemus.

Jos haluat muuttaa näytön **leveyden** ja **korkeuden** ominaisuuksia laitteen suunnan mukaan, voit käyttää näitä kaavoja:

**Width** = `Max(App.Width; If(App.Width < App.Height; App.DesignWidth; App.DesignHeight))`

**Korkeus** = `Max(App.Height; If(App.Width < App.Height; App.DesignHeight; App.DesignWidth))`

Nämä kaavat vaihtavat sovelluksen **Designwidth** -ja **designheight** -arvoja sen mukaan, onko laitteen leveys pienempi kuin sen korkeus (pystysuuntainen) vai suurempi kuin sen korkeus (vaaka suunta).

Kun olet säätänyt näytön **leveyden** ja **korkeuden** kaavoja, haluat ehkä myös järjestää näytön ohjaus objektin uudelleen, jotta käytettävissä olevaa tilaa olisi parempi käyttää. Jos esimerkiksi jokainen kahdesta ohjaus objektista vie puolet näytöstä, voit pinota ne pystysuunnassa pystysuunnassa, mutta järjestää ne vierekkäin vaaka suunnassa.

Näytön **Orientation** -ominaisuuden avulla voit määrittää, onko näyttö suuntautunut pysty-vai vaaka suunnassa.

> [!NOTE]
> Vaakasuuntaisessa **ylhäällä** ja **alhaalla** olevat ohjaus painikkeet näkyvät vasemmalla ja oikealla ohjaus objekteilla.

| Ohjausobjekti | Ominaisuus | Kaava |
|--|----------|---|
| **Ylärajan** | **X** | `0` |
| **Ylärajan** | **Y** | `0` |
| **Ylärajan** | **Leveys** | `If(Parent.Orientation = Layout.Vertical; Parent.Width; Parent.Width / 2)` |
| **Ylärajan** | **Korkeus**   | `If(Parent.Orientation = Layout.Vertical; Parent.Height / 2; Parent.Height)` |
| **Pienempi** | X | `If(Parent.Orientation = Layout.Vertical; 0; Upper.X + Upper.Width)`  |
| **Pienempi** | Y | `If(Parent.Orientation = Layout.Vertical; Upper.Y + Upper.Height; 0)` |
| **Pienempi** | **Leveys** | `Parent.Width - Lower.X` |
| **Pienempi** | **Korkeus** | `Parent.Height - Lower.Y` |

![pystysuuntaisen suunnan sovittamisen lausekkeet](media/create-responsive-layout/portrait.png)

![vaakasuuntaiseksi sovittamisen lausekkeet](media/create-responsive-layout/landscape.png)

### <a name="screen-sizes-and-breakpoints"></a>Näytön koot ja keskeytys kohdat

Voit säätää ulkoasua laitteen koon perusteella. Näytön **koko** -ominaisuus luokittelee nykyisen laitteen koon. Koko on positiivinen kokonaisluku; ScreenSize-tyyppi sisältää nimetyt vakiot, jotka helpottavat luettavuutta. Tässä taulukossa luetellaan vakiot:

| Vakio              | Value | Tyypillinen laite tyyppi (oletus sovellus asetusten avulla) |
|-----------------------|-------|--------------------------------------------------|
| ScreenSize. Small      | 1     | Puhelin                                            |
| ScreenSize. Medium     | 2     | Tabletti, pystysuunnassa                          |
| ScreenSize. Large      | 3     | Tabletti, vaaka suunnassa                        |
| ScreenSize. Extraalarge | 4     | Pöytä tieto kone                                 |

Näiden kokojen avulla voit tehdä päätöksiä sovelluksesi rakenteesta. Jos esimerkiksi haluat, että ohjaus objekti piilotetaan puhelimen kokoisella laitteella, mutta se näkyy muussa tapa uksessa, voit määrittää ohjaus objektin **näkyvissä** -ominaisuudeksi tämän kaavan:

`Parent.Size >= ScreenSize.Medium`

Tämän kaavan arvo on **True** , kun koko on keskisuuri tai suurempi ja muussa tapa uksessa **Epätosi** .

Jos haluat, että ohjaus objekti miehittää eri osan näytön leveydestä näytön koon mukaan, valitse ohjaus objektin **Width** -ominaisuudeksi Tämä kaava:

```powerapps-comma
Parent.Width *  
    Switch(Parent.Size;  
        ScreenSize.Small; 0,5;  
        ScreenSize.Medium; 0,3;  
        0,25)
```
Tämä kaava määrittää ohjaus objektin leveyden puolet näytön leveydestä pienessä näytössä, kolme kymmenesosaa näytön leveydestä keskikokoisella näytöllä ja neljänneksen näytön leveydestä kaikissa muissa näytöissä.

## <a name="custom-breakpoints"></a>Mukautetut keskeytys kohdat

Näytön **koko** -ominaisuus lasketaan vertaamalla näytön **Width** -ominaisuutta sovelluksen **siderbreakpoints** -ominaisuuden arvoihin. Tämä ominaisuus on yksisarakkeinen numero taulukko, joka ilmaisee, mitkä leveyden keskeytys kohdat erottavat nimetyt näyttö koot:

Tabletia tai verkkoa varten luodussa sovelluksessa sovelluksen **siwisbreakpoints** -ominaisuuden oletus arvo on **[600; 900; 1200]** . Puhelimille luodussa sovelluksessa arvo on **[1200; 1800; 2400]** . (Puhelin sovellusten arvot kaksinkertaistetaan, koska tällaiset sovellukset käyttävät koordinaatteja, jotka tuplasivat tehokkaasti muissa sovelluksissa käytettävät koordinaatit.)

![Sovelluksen. Siperbreakpoints-ominaisuuden oletus arvot](media/create-responsive-layout/default-breakpoints.png)

Voit mukauttaa sovelluksesi keskeytys kohtia muuttamalla sovelluksen **siperbreakpoints** -ominaisuuden arvoja. Valitse **sovellus** puunäkymästä, valitse ominaisuus luettelosta **sisibreakpoints** ja muokkaa sitten arvoja kaava rivillä. Voit luoda niin monta keskeytys kohtaa kuin sovelluksesi tarvitsee, mutta vain koot 1 – 4 vastaavat nimettyjä näytön kokoja. Kaavoissa voit katsoa, mitä kokoja on, kuin Extraalarge, niiden luku arvojen (5, 6 ja niin edelleen) mukaan.

Voit myös määrittää vähemmän keskeytys kohtia. Sovelluksesi voi esimerkiksi tarvita vain kolmea kokoa (kaksi keskeytys kohtaa), joten mahdolliset näytön koot ovat pienet, keskikokoiset ja suuret.

## <a name="known-limitations"></a>Tunnetut rajoitukset

Sisällön tuottamisen piirto alusta ei reagoi luotuihin koon muuttamisen kaavoihin. Jos haluat testata reagoivaa toimintaa, Tallenna ja julkaise sovelluksesi ja avaa se laitteissa tai eri kokojen ja suuntausten selain ikkunoissa.

Jos kirjoitat lausekkeita tai kaavoja ohjaus objektin **X**-, **Ky**-, **Width**-ja **Height** -ominaisuuksissa, korvaat kyseiset lausekkeet tai kaavat, jos myöhemmin vedät ohjaus objektin eri sijaintiin tai muutat ohjaus objektin kokoa vetämällä sen reuna.
