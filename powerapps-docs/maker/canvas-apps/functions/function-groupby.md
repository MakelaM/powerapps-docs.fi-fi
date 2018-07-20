---
title: GroupBy- ja Ungroup-funktiot | Microsoft Docs
description: PowerAppsin GroupBy- ja Ungroup-funktioiden viitetietoja, kuten syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: 1c54b905c4942ab824d10acbb32dbc5d7a4a98a7
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39021408"
---
# <a name="groupby-and-ungroup-functions-in-powerapps"></a>GroupBy- ja Ungroup-funktiot PowerAppsissa
[Taulukon](../working-with-tables.md) [tietueiden](../working-with-tables.md#records) ryhmittely ja ryhmittelyn purku.

## <a name="description"></a>Kuvaus
**GroupBy**-funktio palauttaa taulukon, jossa tietueet on ryhmitelty yhteen yhden tai useamman [sarakkeen](../working-with-tables.md#columns) arvojen perusteella. Saman ryhmän tietueet sijoitetaan yhteen tietueeseen. Lisäksi luodaan uusi sarake, joka sisältää sisäkkäisen taulukon jäljelle jääneistä sarakkeista.   

**Ungroup**-funktio kääntää **GroupBy**-prosessin. Tämä funktio palauttaa taulukon, jossa kaikki yhteen ryhmitellyt tietueet on katkaistu erillisiksi tietueiksi.

Voit ryhmitellä tietueet **GroupBy**-funktiolla, muokata sen palauttamaa taulukkoa ja purkaa muokatun taulukon ryhmittelyn **Ungroup**-funktiolla. Voit esimerkiksi poistaa tietueryhmän seuraavalla tavalla:

* Käytä **GroupBy**-funktiota.
* Poista koko tietueryhmä **[Filter](function-filter-lookup.md)**-funktion avulla.
* Käytä **Ungroup**-funktiota.  

Voit myös koostaa tulokset ryhmittelyn perusteella:

* Käytä **GroupBy**-funktiota.
* Lisää uusi ryhmitellyistä taulukoista koostettu sarake yhdistämällä **[AddColumns](function-table-shaping.md)**-funktio **[Sum](function-aggregates.md)**- ja **[Average](function-aggregates.md)**-funktioihin sekä muihin koontifunktioihin.
* Poista ryhmitelty taulukko **[DropColumns](function-table-shaping.md)**-funktiolla.

**Ungroup** yrittää säilyttää **GroupBy**-funktiolla syötettyjen tietueiden alkuperäisen järjestyksen.  Tämä ei ole aina mahdollista (esimerkiksi jos alkuperäisessä taulukossa on *tyhjiä* tietueita).

PowerAppsissa taulukko on arvo, samaan tapaan kuin merkkijono tai luku. Voit määrittää taulukon funktion argumenttina ja funktio voi palauttaa taulukon. **GroupBy** ja **Ungroup** eivät muokkaa taulukkoa. Ne kohtelevat taulukkoa argumenttina ja palauttavat eri taulukon. Lisätietoja on kohdassa [taulukoiden käsitteleminen](../working-with-tables.md).

## <a name="syntax"></a>Syntaksi
**GroupBy**( *Taulukko*, *SarakkeenNimi1* [, *SarakkeenNimi2*, ... ], *RyhmitteleSarakkeenNimi* )

* *Taulukko* – pakollinen. Ryhmiteltävä taulukko.
* *SarakkeenNimet* – pakollinen.  Sarakkeiden nimet *Taulukossa*, jonka perusteella tietueet ryhmitellään.  Näistä sarakkeista tulee sarakkeita lopputuloksena saatavaan taulukkoon.
* *RyhmitteleSarakkeenNimi* – pakollinen.  Sarakenimi, johon tallennetaan tietuetiedot, jotka eivät sisälly kohtaan *SarakkeenNimet*.
  
    > [!NOTE]
  > Jos SharePoint- ja Excel-tietolähteiden sarakkeennimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **"\_x0020\_"**. Voit esimerkiksi määrittää **Sarakkeen nimeksi** **”Sarakkeen_x0020_Nimi”**.

**Ungroup**( *Taulukko*, *RyhmitteleSarakkeenNimi* )

* *Taulukko* – pakollinen. Taulukko, jonka ryhmitys puretaan.
* *RyhmitteleSarakkeenNimi* – pakollinen. Sarake, joka sisältää tietueen asetustiedot **GroupBy**-funktiolla.
  
    > [!NOTE]
  > Jos SharePoint- ja Excel-tietolähteiden sarakkeennimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **"\_x0020\_"**. Voit esimerkiksi määrittää **Sarakkeen nimeksi** **”Sarakkeen_x0020_Nimi”**.

## <a name="examples"></a>Esimerkkejä
### <a name="create-a-collection"></a>Kokoelman luominen
1. Lisää painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuus niin, että painikkeessa lukee **Alkuperäinen**.
2. Määritä **Alkuperäinen**-painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **ClearCollect(KaupunkienVäkiluvut, {Kaupunki:"Lontoo", Maa:"Yhdistynyt kuningaskunta", Väkiluku:8615000}, {Kaupunki:"Berliini", Maa:"Saksa", Väkiluku:3562000}, {Kaupunki:"Madrid", Maa:"Espanja", Väkiluku:3165000}, {Kaupunki:"Rooma", Maa:"Italia", Väkiluku:2874000}, {Kaupunki:"Pariisi", Maa:"Ranska", Väkiluku:2273000}, {Kaupunki:"Hampuri", Maa:"Saksa", Väkiluku:1760000}, {Maa:"Barcelona", Maa:"Espanja", Väkiluku:1602000}, {Kaupunki:"München", Maa:"Saksa", Väkiluku:1494000}, {Kaupunki:"Milano", Maa:"Italia", Väkiluku:1344000})**
3. Paina F5, valitse **Alkuperäinen**-painike ja paina sitten Esc.
   
    Juuri luomasi [kokoelman](../working-with-data-sources.md#collections) nimi on **KaupunkienVäkiluvut**, ja se sisältää nämä tiedot:
   
    ![](media/function-groupby/cities.png)
4. Näytä tämä kokoelma valitsemalla **Tiedosto**-valikosta **Kokoelmat** ja valitse sitten **KaupunkienVäkiluvut**-kokoelma.  Kokoelman viisi ensimmäistä tietuetta näytetään:
   
    ![](media/function-groupby/citypopulations-collection.png)

### <a name="group-records"></a>Tietueiden ryhmittely
1. Lisää toinen painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuuden arvoksi **"Group"**.
2. Määritä painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **ClearCollect( KaupungitMaittain, GroupBy( KaupunkienVäkiluvut, "Maa", "Kaupungit" ) )**
3. Paina F5, valitse **Group**-painike ja paina sitten Esc.
   
    Juuri luomasi kokoelman nimi on **KaupungitMaittain**. Kokoelmassa edellisen kokoelman tietueet on ryhmitelty **Maa**-sarakkeen mukaan.
   
    ![](media/function-groupby/cities-grouped.png)
4. Voit näyttää kokoelman viisi ensimmäistä tietuetta valitsemalla **Tiedosto**-valikosta **Kokoelmat**.
   
    ![](media/function-groupby/citiesbycountry-collection.png)
5. Näytä eri maiden kaupunkien väkiluvut valitsemalla **Kaupungit**-sarakkeessa oleva taulukkokuvake kyseisen maan kohdalta (esimerkiksi Saksa):
   
    ![](media/function-groupby/population-germany.png)

### <a name="filter-and-ungroup-records"></a>Suodata ja pura tietueiden ryhmittely
1. Lisää painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuus niin, että painikkeessa lukee **"Suodata"**.
2. Määritä painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **ClearCollect (KaupungitMaittainSuodatettu, Filter(KaupungitMaittain, "e" in Maa))**
3. Paina F5, valitse lisäämäsi painike ja paina Esc-näppäintä.
   
    Loit juuri kolmannen kokoelman nimeltä **KaupungitMaittainSuodatettu**, joka sisältää vain ne maat, joiden nimessä ”e” (eli ei Saksaa tai Italiaa).
   
    ![](media/function-groupby/cities-grouped-hase.png)
4. Lisää vielä yksi painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuus niin, että painikkeessa lukee **"Pura ryhmittely"**.
5. Määritä painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **ClearCollect( KaupunkienVäkiluvutRyhmittelemätön, Ungroup( KaupungitMaittainSuodatettu, "Kaupungit" ) )**
   
    Jonka tuloksena saadaan:
   
    ![](media/function-groupby/cities-hase.png)

### <a name="aggregate-results"></a>Koontitulokset
Ryhmitetyn taulukon avulla voidaan myös koostaa tuloksia.  Tässä esimerkissä lasketaan yhteen maiden suurimpien kaupunkien väkiluvut.

1. Lisää painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuus niin, että painikkeessa lukee **"Summa"**.
2. Määritä **"Summa"**-painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **ClearCollect( KaupunkienVäkiluvutSumma, AddColumns( KaupungitMaittain, "Kaupunkien väkilukujen summa", Sum( Kaupungit, Väkiluku ) ) )**
   
    Jonka tuloksena saadaan:
   
    ![](media/function-groupby/cities-sum.png)
   
    **[AddColumns](function-table-shaping.md)** aloittaa **KaupungitMaittain**-kokoelmasta ja lisää uuden sarakkeen **Kaupunkien väkilukujen summa**.  Sarakkeen arvot lasketaan riveittäin perustuen kaavaan **Sum( Kaupungit, Väkiluku)**.  **AddColumns** antaa **Kaupungit**-sarakkeen arvon (taulukko) jokaiselle riville, ja **[Sum](function-aggregates.md)** laskee yhteen jokaisen alataulukon rivin **väkiluvun**.
3. Kun meillä on nyt haluamamme summa, voimme käyttää **[DropColumns](function-table-shaping.md)**-funktiota alataulukoiden poistamiseen.  Muokkaa **[OnSelect](../controls/properties-core.md)**-ominaisuutta käyttämään seuraavaa kaavaa:
   
    **ClearCollect( KaupunkienVäkiluvutVainSumma, DropColumns( KaupunkienVäkiluvutSumma, "Kaupungit" ) )**
   
    Jonka tuloksena saadaan:
   
    ![](media/function-groupby/cities-sum-drop-cities.png)
   
    Huomaa, ettei tätä taulukkoa tarvinnut purkaa.

