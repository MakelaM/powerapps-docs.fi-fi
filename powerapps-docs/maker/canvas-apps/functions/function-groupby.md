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
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5752781cf99a538d76e9dd9197aa4f8b8abce53e
ms.sourcegitcommit: ba5542ff1c815299baa16304c6e0b5fed936e776
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/15/2019
ms.locfileid: "54308566"
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
**GroupBy**( *Table*, *ColumnName1* [, *ColumnName2*, ... ], *GroupColumnName* )

* *Table* – Pakollinen. Ryhmiteltävä taulukko.
* *ColumnName(s)* – Pakollinen.  Sarakkeiden nimet *Taulukossa*, jonka perusteella tietueet ryhmitellään.  Näistä sarakkeista tulee sarakkeita lopputuloksena saatavaan taulukkoon.
* *GroupColumnName* – Pakollinen.  Sarakenimi, johon tallennetaan tietuetiedot, jotka eivät sisälly kohtaan *ColumnName(s)*.
  
    > [!NOTE]
  > Jos SharePoint- ja Excel-tietolähteiden sarakkeennimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **"\_x0020\_"**. Voit esimerkiksi määrittää **Column Name** -arvoksi **"Sarakkeen_x0020_Nimi"**.

**Ungroup**( *Table*, *GroupColumnName* )

* *Table* – Pakollinen. Taulukko, jonka ryhmitys puretaan.
* *GroupColumnName* – Pakollinen. Sarake, joka sisältää tietueen asetustiedot **GroupBy**-funktiolla.
  
    > [!NOTE]
  > Jos SharePoint- ja Excel-tietolähteiden sarakkeennimissä käytetään välilyöntejä, merkitse jokaisen välilyönnin tilalle **"\_x0020\_"**. Voit esimerkiksi määrittää **Column Name** -arvoksi **"Sarakkeen_x0020_Nimi"**.

## <a name="examples"></a>Esimerkkejä
### <a name="create-a-collection"></a>Kokoelman luominen
1. Lisää painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuus niin, että painikkeessa lukee **Alkuperäinen**.
2. Määritä **Alkuperäinen**-painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:

```powerapps-dot   
ClearCollect( CityPopulations, 
    { City: "London",    Country: "United Kingdom", Population: 8615000}, 
    { City: "Berlin",    Country: "Germany",        Population: 3562000}, 
    { City: "Madrid",    Country: "Spain",          Population: 3165000}, 
    { City: "Rome",      Country: "Italy",          Population: 2874000}, 
    { City: "Paris",     Country: "France",         Population: 2273000}, 
    { City: "Hamburg",   Country: "Germany",        Population: 1760000}, 
    { City: "Barcelona", Country: "Spain",          Population: 1602000}, 
    { City: "Munich",    Country: "Germany",        Population: 1494000}, 
    { City: "Milan",     Country: "Italy",          Population: 1344000}
)
```

3. Pidä Alt-näppäintä painettuna ja valitse **Alkuperäinen**-painike.
   
    Juuri luomasi [kokoelman](../working-with-data-sources.md#collections) nimi on **KaupunkienVäkiluvut**, ja se sisältää nämä tiedot:
   
    ![](media/function-groupby/cities.png)
4. Näytä tämä kokoelma valitsemalla **Tiedosto**-valikosta **Kokoelmat** ja valitse sitten **KaupunkienVäkiluvut**-kokoelma.  Kokoelman viisi ensimmäistä tietuetta näytetään:
   
    ![](media/function-groupby/citypopulations-collection.png)

### <a name="group-records"></a>Tietueiden ryhmittely
1. Lisää toinen painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuuden arvoksi **"Group"**.
2. Määritä painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **ClearCollect( KaupungitMaittain, GroupBy( KaupunkienVäkiluvut, "Maa", "Kaupungit" ) )**
3. Pidä Alt-näppäintä painettuna ja valitse **Ryhmä**-painike.
   
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
3. Pidä Alt-näppäintä painettuna ja valitse lisäämäsi painike.
   
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

    Kun meillä on nyt haluamamme summa, voimme käyttää **[DropColumns](function-table-shaping.md)**-funktiota alataulukoiden poistamiseen.
  
3. Lisää painike ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuus niin, että painikkeessa lukee **"SumOnly"**.
4. Määritä **"SumOnly"**-painikkeen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **ClearCollect( KaupunkienVäkiluvutVainSumma, DropColumns( KaupunkienVäkiluvutSumma, "Kaupungit" ) )**
   
    Jonka tuloksena saadaan:
   
    ![](media/function-groupby/cities-sum-drop-cities.png)
   
    Huomaa, ettei tätä taulukkoa tarvinnut purkaa.

