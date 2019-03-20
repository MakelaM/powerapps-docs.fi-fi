---
title: Luo pohjaan perustuvat sovellukset komponentti | Microsoft Docs
description: Johdanto komponentteja pohjaan perustuvat sovellukset
author: yifwang
ms.service: powerapps
ms.topic: article
ms.date: 12/12/2018
ms.author: yifwang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 369304ded3fdc9fcd69459da9875e6080d5d860c
ms.sourcegitcommit: 2e2cfbaa29cbfdbe48bd5563e65edcfc57a69b9d
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/15/2019
ms.locfileid: "57989630"
---
# <a name="create-a-component-for-canvas-apps"></a>Luo pohjaan perustuvat sovellukset komponentti

> [!IMPORTANT]
> Tämä ominaisuus on edelleen kokeellinen ja käytöstä oletusarvon mukaan. Jos haluat lisätietoja, katso [kokeelliseen ja esikatselu](working-with-experimental.md).

Osat ovat pohjaan perustuvat sovellukset Uudelleenkäytettävä osat, jotta voidaan luoda mukautetut ohjausobjektit sovelluksessa tai sovellusten välillä. Kehittyneitä ominaisuuksia, kuten mukautettuja ominaisuuksia, ota käyttöön osat monimutkaisia ominaisuuksia. Tässä artikkelissa esitellään osa käsitteet ja joitakin esimerkkejä.

Osat ovat hyödyllisiä rakentamiseen suurempi, joissa on samanlainen ohjausobjektin kuviot. Jos päivität osa-määritys, kaikki esiintymät sovelluksessa tekemiesi muutosten mukaisesti. Voit myös parantaa suorituskykyä käyttämällä yhden tai useamman osia, koska ei kopioida ja liittää ohjausobjekteja, jotka kaksoiskappaleet tietojen. Osia myös helpottaa yhteistyöpalvelujen kehittämistä ja standardoit ulkoasu ja tuntuma organisaatiossasi.

## <a name="prerequisite"></a>Edellytys

Avaa **sovellusasetukset** -näytössä **lisäasetukset**, ja ottaa käyttöön sekä varmistaa, että **Improved sovelluksen hahmontaminen** on käytössä.

## <a name="component-canvas"></a>Osa kangas

Voit luoda osan **osat** valikosta **Lisää** välilehti tai seuraava graafinen näkyy vasemmassa siirtymispalkissa. Tässä luettelossa osia, jotka on määritetty sovelluksen lajitteluperuste luontiaika.

![Osa Luettelonäkymä](./media/create-component/list-view.png)

Riippumatta siitä, mitä teet lähestymistapaa tyhjä pohja tulee, jossa voit lisätä ohjausobjekteja osa määritysasetuksena. Jos muokkaat piirtoalustalla osaa, päivittää samaa komponenttia sovelluksen muihin näyttöihin ja muiden sovellusten esiintymiä.

Jos valitset näyttö, voit valita osaa komponenttien vasemmassa siirtymispalkissa luettelosta tai **osat** valikosta **Lisää** välilehti. Kun valitset osaa, Lisää esiintymää komponentti näyttöön, kuten lisäät ohjausobjektin.

## <a name="scope"></a>Vaikutusalue

Ajattele osaa encapsulated musta ruutuna ominaisuuksia kuin liittymä. Et pysty käyttämään ohjausobjekteja osa osan ulkopuolella ja ei voi viitata mitään osa sisällä osan ulkopuolella. Jos yrität, näyttöön tulee virhesanoma. Vaikutusalueen rajoitukset säilyttää osan tiedot-sopimuksen yksinkertainen ja koossa pysyviin, ja se auttaa Ota käyttöön saumaton osa-päivitykset, erityisesti sovellusten välillä. Voit päivittää tietoja sopimuksen on osa luomalla yhden tai useamman mukautettuja ominaisuuksia.

## <a name="variables"></a>Muuttujat

Osat eivät tue **UpdateContext** funktiota, mutta voit luoda ja päivittää muuttujien osaa käyttämällä **määrittää** funktio. Näiden muuttujien vaikutusaluetta osaan, mutta voit käyttää niitä osa ulkopuolella hyödyntämällä mukautetun tulosteominaisuudet.

## <a name="import-and-export"></a>Tuo ja vie

Jos viet osaa, voit luoda voit tuoda eri paikalliseen tiedostoon. Jos sovellus on muokattu samassa osaa, sinua pyydetään päätä, haluatko korvata muokattu tai Peruuta tuonti. Tätä kirjoitettaessa ei voi tallentaa osat pilveen tai jakaa niitä ympäristössä.

![Tuo ja vie](./media/create-component/import.png)

## <a name="custom-properties"></a>Mukautettuja ominaisuuksia

Osaa voi vastaanottaa syötearvot ja lähettää tietoja, jos luot yhden tai useamman mukautettuja ominaisuuksia. Näissä skenaarioissa edistyneisiin ja sinua ymmärtämään kaavojen ja sidonnan sopimukset.

Syötteen-ominaisuus on, miten osaa vastaanottaa tietoja voi käyttää osa. Syöteominaisuudet näkyvät **ominaisuudet** välilehti oikeanpuoleisessa ruudussa, jos osa esiintymä on valittuna. Voit määrittää syöteominaisuudet lausekkeita tai kaavoja, kuten määrität vakio-ominaisuudet muita ohjausobjekteja. Muut ohjausobjektit on syötteen ominaisuuksia, kuten **oletus** ominaisuus **Tekstisyöte** ohjausobjektin.

Tulosteominaisuudet voi lähettää tietoja tai osa-tilassa. Esimerkiksi **valittu** ominaisuus **valikoiman** ohjausobjekti on output-ominaisuus. Kun luot output-ominaisuus, voit määrittää, mitä muita ohjausobjekteja voi viitata osa-tilaan.

Tässä ohjeartikkelissa kerrotaan näistä käsitteistä.

## <a name="create-an-example-component"></a>Luo Esimerkki-komponentti

Tässä esimerkissä luodaan, joka muistuttaa seuraavaa kuvaa tai, jossa voit muuttaa tekstiä ja käyttää useita näyttöjä, sovellusten tai molempiin valikon osa:

![Lopullinen valikoima](./media/create-component/menu-instance.png)

1. PowerApps Studio luo tyhjän sovelluksen.

1. Vasemmassa siirtymispalkissa osien luetteloa, ja valitse sitten **uusi osa**.

    ![Osien luetteloa](./media/create-component/component-list.png)

1. Kun hiiren osoitin uusi päällä, valitse kolme pistettä (...), valitse **nimeä**, ja kirjoita tai liitä sitten **MenuComponent**.

1. Oikeanpuoleisessa ruudussa, määritä leveydeksi komponentin **150** ja korkeus kasvaa **250**, ja valitse sitten **uuden mukautetun ominaisuuden**.

    ![Uuden ominaisuuden](./media/create-component/new-property.png)

1. - **Näyttönimi**, **ominaisuuden nimi**, ja **kuvaus** ruutuihin, kirjoita tai liitä **kohteita**.

    ![Näyttönimi, ominaisuuden nimi, kuvaus ruudut](./media/create-component/property-names.png)

    Kun ominaisuuden nimeä ei ole välilyöntejä koska viittaat osa tämän niminen kaavan kirjoittamisen (esimerkiksi **ComponentName.PropertyName**).

    Näytä nimi näkyy **ominaisuudet** välilehti oikeanpuoleisessa ruudussa, jos valitset osa. Kuvaava näyttönimi auttaa ja muut tekijät ymmärtävät tämän ominaisuuden. **Kuvaus** näkyy työkaluvihjeen, jos tämän ominaisuuden näyttönimi osoitin **ominaisuudet** välilehti.

1. - **Tietotyyppi** luettelosta **taulukon**, ja valitse sitten **Luo**.

    ![Ominaisuuden tietotyyppi](./media/create-component/property-data-type.png)

    **Kohteet** asetuksena on oletusarvo, jonka määritit tietotyypin mukaan, mutta voit määrittää sen arvon, joka tarpeisiisi. Jos tietotyyppi on määritetty **taulukon** tai **tietueen**, haluat ehkä muuttaa arvoa **kohteet** ominaisuuden vastaamaan data-rakenteen, jonka haluat syöte osaan. Tässä tapauksessa muuttaa sen merkkijonojen luettelo.

    Voit määrittää ominaisuuden arvoa kaavarivillä, jos ominaisuuden nimi- **ominaisuudet** välilehti oikeanpuoleisessa ruudussa.

    ![Mukautetun syötteen ominaisuuden ominaisuudet-välilehdestä](./media/create-component/properties-tab.png)

    Kuten seuraava graafinen osoittaa, voit myös muokata ominaisuuden arvoa **lisäasetukset** välilehti oikeanpuoleisessa ruudussa.

1. Määrittää komponentin **kohteet** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    Table({Item:"SampleText"})
    ```

    ![Kaava](./media/create-component/set-component-items.png)

1. Lisää komponentti, tyhjä pystysuuntainen **valikoiman** ohjausobjektin.

1. Varmista, että ominaisuusluettelo näyttää **kohteet** ominaisuuden (sellaisena kuin se tekee oletusarvon mukaan), ja määritä sitten kyseisen ominaisuuden arvoksi seuraava lauseke:

    ```powerapps-dot
    MenuComponent.Items
    ```

    Tällä tavalla **kohteet** -ominaisuuden **valikoiman** ohjausobjekti lukee ja riippuu **kohteet** syöte osa-ominaisuuden.

1. Määritä **valikoiman** ohjausobjektin **BorderThickness** ominaisuudeksi **1** ja sen **TemplateSize** ominaisuudeksi **50**.

1. Mallin **valikoiman** ohjausobjekti, Lisää **nimen** ohjausobjektin.

    ![Lisää selite ja Aseta valikoiman reunan](./media/create-component/add-label.png)

Seuraavaksi osa lisätään näyttöön ja määritä merkkijonotaulukko näyttämään osan.

1. Vasemmassa siirtymispalkissa näyttöjä luettelo ja valitse sitten oletusnäytön.

    ![Oletusnäyttö](./media/create-component/default-screen.png)

1. Käyttöön **Lisää** välilehti, Avaa **osat** valikko ja valitse sitten **MenuComponent**.

    ![Lisää](./media/create-component/insert.png)

    Uusi komponenttia **MenuComponent_1** oletusarvon mukaan.

1. Määritä **kohteet** ominaisuuden **MenuComponent_1** tämä kaava:

    ```powerapps-dot
    Table({Item:"Home"}, {Item:"Admin"}, {Item:"About"}, {Item:"Help"})
    ```

    Tämän esiintymän muistuttaa seuraavaa kuvaa, mutta voit mukauttaa teksti ja muut ominaisuudet kunkin esiintymän.

    ![Lopullinen valikoima](./media/create-component/menu-instance.png)

Tähän mennessä olet luonut osan ja lisätä sen sovellukseen. Seuraavaksi luot output-ominaisuus, joka vastaa kohteen käyttäjä valitsee-valikosta.

1. Avaa osien luetteloa ja valitse sitten **MenuComponent**.

1. Valitse oikeanpuoleisessa ruudussa **ominaisuudet** välilehti ja valitse sitten **uuden mukautetun ominaisuuden**.

1. Tässä **näyttönimi**, **ominaisuuden nimi**, ja **kuvaus** ruutuihin, kirjoita tai liitä **valittu**.

1. Valitse **ominaisuuden tyyppi**, valitse **Output**, ja valitse sitten **Luo**.

1. Käyttöön **lisäasetukset** välilehdeltä arvoa **valittu** ominaisuudeksi Tämä lauseke säätäminen valikoima-nimi on numero tarvittaessa:

    ```powerapps-dot
    Gallery1.Selected.Item
    ```

    ![Lisäasetusten ruutuun](./media/create-component/advance.png)

1. Oletusarvon mukainen sovelluksen näytössä Lisää selite ja aseta sen **tekstin** ominaisuudeksi Tämä lauseke säätäminen komponentin nimi numero tarvittaessa:

    ```powerapps-dot
    MenuComponent_1.Selected
    ```

    Huomaa, että **MenuComponent_1** on oletusnimi esiintymän ei osa-määrityksen nimi. Mikä tahansa esiintymä voi nimetä uudelleen.

1. Kun pidät alhaalla Alt-näppäintä, valitse kunkin kohteen valikosta.

    **Nimen** ohjausobjektin kuvastaa valikkokohteen, jonka valitsit viimeksi.

## <a name="known-limitations"></a>Tunnetut rajoitukset

- Tätä kirjoitettaessa tietolähteitä ei tallenneta osia, joten lomakkeet ja taulukoihin, on poistettu käytöstä. 
- Jos luot muuttujan osaa, kyseisen muuttujan on rajoitettu vain osaa ja ei näy sovelluksen muuttujien käyttäminen.
- PowerApps ei tue kokoelmat osia.
- Osaa ei voi lisätä valikoimassa, lomakkeessa tai tietojen kortti.
- Osaa päätietokannan esiintymä on paikallinen pää- ja sisältäville sovellukseen. Jos muutat päätietokannan esiintymä, muutokset näkyvät vain kopioita osa sovelluksessa. Kopioi muissa sovelluksissa pysyy samana, ellei osa-kirjaston Tuo uudelleen. Kaikki kyseiset sovellukset päätietokannan esiintymät havaittu ja päivittää automaattisesti.
- Mediatiedostoja ei paketin, kun tuot osaa.
