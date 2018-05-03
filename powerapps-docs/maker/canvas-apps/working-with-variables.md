---
title: Tutustu muuttujiin | Microsoft Docs
description: Viitetietoja työskentelyyn tilan, kontekstimuuttujien ja kokoelmien parissa
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 07/06/2017
ms.author: gregli
ms.openlocfilehash: 74ab73d78e87c25adf0cd300bb8a6321a578d749
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="understand-variables-in-powerapps"></a>Tutustu PowerAppsin muuttujiin
Jos olet joskus käyttänyt jotakin toista ohjelmointityökalua, kuten Visual Basicia tai JavaScriptiä, ihmettelet ehkä, **missä muuttujat ovat.** PowerApps on hieman erilainen ja edellyttää erilaista käyttötapaa. Muuttujien etsimisen sijaan mieti, **mitä tekisit Excelissä.**

Muissa työkaluissa olet ehkä eksplisiittisesti suorittanut laskutoimituksen ja tallentanut tuloksen muuttujaan. PowerApps ja Excel laskevat kuitenkin kaavat automaattisesti uudelleen syötetietojen muuttuessa, joten muuttujia ei yleensä tarvitse luoda ja päivittää. Noudattamalla tätä lähestymistapaa, aina kun mahdollista, voit helpommin luoda, ymmärtää ja ylläpitää sovelluksia.

Joudut joissakin tapauksissa käyttämään muuttujia PowerAppsissa, joka laajentaa Excelin mallin lisäämällä [toimintakaavioita](working-with-formulas-in-depth.md). Nämä kaavat suoritetaan, esimerkiksi kun käyttäjä valitsee painikkeen. Toimintakaaviossa kannattaa usein määrittää muuttuja, jota käytetään muissa kaavoissa.

Yleensä kannattaa välttää muuttujien käyttämistä. Toisinaan kuitenkin vain muuttuja pystyy mahdollistamaan halutun ominaisuuden.

## <a name="translate-excel-into-powerapps"></a>Excel vs. PowerApps
### <a name="excel"></a>Excel
Muistellaan, miten Excel toimii. Solu voi sisältää arvon, kuten luvun tai merkkijonon, tai kaavan, joka perustuu muiden solujen arvoihin. Sen jälkeen, kun käyttäjä on lisännyt eri arvon soluun, Excel laskee automaattisesti uudestaan kaavat, jotka ovat riippuvaisia uudesta arvosta. Tätä varten ei tarvitse tehdä mitään ohjelmointia.

![](media/working-with-variables/excel-recalc.png)

Excelissä ei ole muuttujia. Kaavan sisältävän solun arvo muuttuu siihen syötettyjen tietojen mukaan, mutta kaavan tulosta ei voi muistaa eikä tallentaa soluun tai minnekään muualle. Jos muutat solun arvoa, koko laskentataulukko saattaa muuttua, jolloin aiemmin lasketut arvot menetetään.  Excel-käyttäjä voi kopioida ja liittää soluja, mutta tämä on käyttäjän manuaalisessa hallinnassa eikä ole mahdollista tehdä kaavoilla.

### <a name="powerapps"></a>PowerApps
Sovellukset, jotka luot PowerAppsissa, toimivat hyvin samalla tavalla kuin Excel. Sen sijaan, että päivität solut, voit lisätä ohjausobjekteja mihin tahansa näytön kohtaan ja nimetä ne kaavoissa käyttämistä varten.

Voit esimerkiksi toistaa Excelin toiminnan sovelluksessa lisäämällä **[selite](controls/control-text-box.md)**-ohjausobjektin nimeltä **TextBox1** ja kaksi **[tekstinsyöte](controls/control-text-input.md)**-ohjausobjektia nimeltä **TextInput1** ja **TextInput2**. Jos sitten määrität **TextBox1**-ohjausobjektin **[teksti](controls/properties-core.md)**-ominaisuudeksi **TextInput1 + TextInput2**, se näyttää aina ohjausobjekteissa **TextInput1** ja **TextInput2** olevien numeroiden summan automaattisesti.

![](media/working-with-variables/recalc1.png)

Huomaa, että kun **TextBox1**-ohjausobjekti on valittuna, sen **[Teksti](controls/properties-core.md)**-kaava näkyy kaavarivillä näytön yläreunassa.  Tässä on kaava **TextInput1 + TextInput2**.  Tämä kaava luo riippuvuussuhteen näiden ohjausobjektien välille, samalla tavalla kuin riippuvuuksia luodaan Excel-työkirjan solujen välille.  Muutetaan **TextInput1**-arvo:

![](media/working-with-variables/recalc2.png)

**TextBox1**-kaava on laskettu automaattisesti uudelleen, ja näemme uuden arvon.

PowerAppsissa voidaan käyttää kaavoja määrittämään ohjausobjektin ensisijaisen arvon lisäksi myös ominaisuuksia, kuten muotoilun. Seuraavassa esimerkissä kaava selitteen **[Väri](controls/properties-color-border.md)**-ominaisuudelle näyttää negatiiviset arvot punaisella automaattisesti. **[Jos](functions/function-if.md)**-funktio näyttää hyvin tutulta Excelistä:
<br>**If( Value(TextBox1.Text) < 0, Red, Black )**

![](media/working-with-variables/recalc-color1.png)

Jos laskutoimituksen tulos kohdassa **TextBox1.Text** on negatiivinen, numero näkyy punaisena:

![](media/working-with-variables/recalc-color2.png)

Voit käyttää kaavoja moniin erilaisiin skenaarioihin:

* Käyttämällä laitteen GPS:ää kartan ohjausobjekti voi näyttää nykyisen sijaintisi kaavalla, joka käyttää signaaleja **Location.Latitude** ja **Location.Longitude**.  Kun siirryt, kartta seuraa sijaintiasi automaattisesti.
* Muut käyttäjät voivat päivittää [tietolähteitä](working-with-data-sources.md).  Muut ryhmän jäsenet voivat esimerkiksi päivittää SharePoint-luettelon kohteita.  Kun päivität tietolähteen, riippuvat kaavat lasketaan automaattisesti uudelleen vastaamaan päivitettyjä tietoja. Jos viemme tätä esimerkkiä eteenpäin, haluat ehkä määrittää valikoiman **[Kohteet](controls/properties-core.md)**-ominaisuuden kaavaksi **Filter( SharePointList )**, joka näyttää automaattisesti vastikään suodatettujen [tietueiden](working-with-tables.md#records) sarjan.

### <a name="benefits"></a>Edut
Sovellusten tekemisellä kaavojen avulla on monia etuja:

* Jos tunnet Excelin, tunnet PowerAppsin. Mallin ja kaavan kieli on sama.
* Jos olet käyttänyt muita ohjelmointityökaluja, mieti, kuinka paljon koodia vaadittaisiin näiden esimerkkien suorittamiseen.  Visual Basicissa joutuisit kirjoittamaan tapahtumakäsittelijän muutostapahtumalle jokaiselle tekstinsyötteen ohjausobjektille.  Koodi, joka suorittaa jokaisen laskutoimituksen, on ylimääräinen ja saattaa joutua epätahtiin, tai joutuisit kirjoittamaan yleisen aliohjelman.  PowerAppsissa sait kaiken tehtyä yksittäisellä yhden rivin kaavalla.
* Saat selville, mistä **TextBox1**-teksti on peräisin katsomalla vain **[teksti](controls/properties-core.md)**-ominaisuuden kaavaa.  Tämän ohjausobjektin tekstiin ei voi vaikuttaa millään muulla tavalla.  Perinteisessä ohjelmointityökalussa kaikki tapahtumakäsittelijät tai aliohjelmat voivat muuttaa otsikon arvoa ohjelman missä tahansa kohdassa.  Muuttujan muuttamisen ajan ja paikan jäljittäminen saattaa tällöin vaikeutua.
* Jos käyttäjä tekee muutoksen liukusäätimeen ja muuttaa sitten mieltään, liukusäädin on mahdollista palauttaa sen alkuperäiseen arvoon.  Mitään muutosta ei ole havaittavissa: sovellus näyttää samat ohjausobjektin arvot kuin aiemminkin.  Kokeiluista ja entä jos -testailuista ei ole seuraamuksia samalla tavalla kuin Excelissä.  

Yleisesti ottaen, jos voit saavuttaa tehosteen käyttämällä kaavaa, se kannattaa. Anna PowerApps-kaavan tehdä työ puolestasi.  

## <a name="know-when-to-use-variables"></a>Milloin muuttujia kannattaa käyttää
Muutetaan yksinkertainen lisäystoiminto siten, että se toimii kuin perinteinen laskin, joka näyttää juoksevan summan. Jos valitset **Lisää**-painikkeen, lisäät luvun juoksevaan summaan. Jos valitset **Tyhjennä**-painikkeen, palautat juoksevan summan nollaksi.

![](media/working-with-variables/button-changes-state.png)

Laskurimme käyttää jotain, mikä puuttuu Excelistä: painike. Tässä sovelluksessa ei voi käyttää vain kaavoja juoksevan summan laskemiseen, koska sen arvo vaihtelee useiden käyttäjän valitsemien toimintojen mukaan. Juokseva summa on sen sijaan tallennettava ja päivitettävä manuaalisesti. Useimmat ohjelmointityökalut tallentavat nämä tiedot *muuttujaan*.    

Joskus tarvitset muuttujan sovellukseen, jotta se toimisi haluamallasi tavalla.  Tehtävä ei ole helppo:

* Juokseva summa täytyy päivittää manuaalisesti. Automaattinen uudelleenlaskenta ei tee sitä puolestasi.
* Juoksevaa summaa ei enää voida laskea muiden ohjausobjektien arvojen perusteella. Tämä vaihtelee sen mukaan, miten monta kertaa käyttäjä valitsi **Lisää**-painikkeen ja mikä arvo tekstisyötteen ohjausobjektissa oli kullakin kerralla. Lisäsikö käyttäjä luvun 77 ja valitsi **Lisää** kahdesti, vai määrittikö hän luvut 24 ja 130 kullekin lisäykselle? Eroa ei ole, kun summa on saavuttanut luvun 154.
* Muutokset summaan voivat olla peräisin eri poluilta. Tässä esimerkissä sekä **Lisää**- että **Tyhjennä**-painikkeilla voidaan päivittää summa. Jos sovellus ei toimi odotetulla tavalla, kumpi painike aiheuttaa ongelman?

## <a name="create-a-global-variable"></a>Luo yleinen muuttuja
Jotta voimme luoda laskimen, tarvitsemme muuttujan, joka sisältää juoksevan summan. PowerApps-muuttujat, joiden kanssa on helpointa toimia, ovat *yleisiä muuttujia*.  

Näin yleiset muuttujat toimivat:

* Yleisen muuttujan arvo asetetaan **[Joukko](functions/function-set.md)**-funktiolla.  **Set( MyVar, 1 )** asettaa yleisen muuttujan **MyVar** arvoon **1**.
* Yleistä muuttujaa käytetään viittaamalla nimeen, jota käytetään **Joukko**-funktion kanssa.  Tässä tapauksessa **MyVar** palauttaa arvon **1**.
* Yleiset muuttujat voivat sisältää mitä tahansa arvoja, mukaan lukien merkkijonoja, lukuja, tietueita ja [taulukkoja](working-with-tables.md).

Rakennetaan laskuri uudelleen käyttämällä yleistä muuttujaa:

1. Lisää tekstisyötteen ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **Set( RunningTotal, RunningTotal + Text1 )**
   
    Kun käyttäjä valitsee ensimmäisen kerran **Lisää**-painikkeen ja **[Joukko](functions/function-set.md)**-funktio kutsutaan, luodaan **RunningTotal**, jonka oletusarvo on *tyhjä*.  Lisäksi sitä käsitellään nollana.
   
    ![](media/working-with-variables/global-variable-1.png)
4. Jotta juokseva summa määritetään **nollaksi** aina, kun käyttäjä valitsee **Tyhjennä**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **Set( RunningTotal, 0 )**
   
    ![](media/working-with-variables/global-variable-2.png)
5. Lisää **[Selite](controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **RunningTotal**.
   
    Tämä kaava lasketaan automaattisesti uudelleen, ja se näyttää käyttäjälle **RunningTotal**-arvon sen muuttuessa sen mukaan, mitä painikkeita käyttäjä valitsee.
   
    ![](media/working-with-variables/global-variable-3.png)
6. Esikatsele sovellusta, ja edellä kuvaamamme laskuri on valmis.  Kirjoita numero tekstiruutuun ja paina **Lisää**-painiketta muutaman kerran.  Kun olet valmis, palaa muokkausominaisuuteen Esc-näppäimellä.  
   
    ![](media/working-with-variables/global-variable-4.png)
7. Jos haluat nähdä yleisen muuttujan arvon, valitse **Tiedosto**-valikko ja sitten **Muuttujat** vasemmanpuoleisesta ruudusta.
   
    ![](media/working-with-variables/global-variable-file-1.png)
8. Jos haluat nähdä kaikki paikat, joissa muuttuja on määritetty ja sitä käytetään, valitse se.
   
    ![](media/working-with-variables/global-variable-file-2.png)

## <a name="types-of-variables"></a>Muuttujien tyypit
PowerAppsissa on kolme muuttujatyyppiä:

| Muuttujan tyyppi | Vaikutusalue | Kuvaus | Funktiot |
| --- | --- | --- | --- |
| Yleiset muuttujat |Sovellus |Helpoin käyttää.  Sisältää esim. luvun, tekstimerkkijonon, totuusarvon, tietueen tai taulukon, johon voidaan viitata missä tahansa sovelluksen kohdassa. |[**Joukko**](functions/function-set.md) |
| Kontekstimuuttujat |Näyttö |Sopii hyvin arvojen välittämiseen näyttöön, kuten parametrit toimintosarjassa muissa kielissä.  Voidaan viitata vain yhdestä näytöstä. |[**UpdateContext**](functions/function-navigate.md) |
| Kokoelmat |Sovellus |Sisältää taulukon, johon voidaan viitata mistä tahansa sovelluksen kohdasta.  Sallii taulukon sisällön muokkaamisen sen sijaan, että se määritettäisiin kokonaisena. Voidaan tallentaa paikalliseen laitteeseen myöhempää käyttöä varten. |[**Kerää**](functions/function-savedata-loaddata.md)<br>jne. |

Kaikki muuttujat luodaan implisiittisesti, kun niitä käytetään funktiossa **Joukko**, **UpdateContext**, **Siirry** tai **Kerää**.  Eksplisiittistä muuttujien määrittelyä ei tehdä, kuten muissa ohjelmointityökaluissa.  Muuttujien tyypit myös johdetaan implisiittisesti arvoista, jotka on sijoitettu niihin.

Kaikki muuttujat säilytetään muistissa, kun sovellus on käynnissä.  Kun sovellus sulkeutuu, muuttujien sisältämät arvot menetetään.  Voit tallentaa muuttujan sisällön tietolähteeseen **Ohjelmakorjaus**- tai **Kerää**-funktiolla, tai kokoelmien ollessa kyseessä voit tallentaa paikallisen laitteen **SaveData**-funktiolla.  Kun sovellusta ladataan ensimmäistä kertaa, kaikilla muuttujilla on *tyhjä* arvo.

Muuttujan arvo luetaan sen nimestä.  Jos esimerkiksi määritykseksi on kerran annettu **Set( MyColor, Red )**, voit käyttää arvoa **MyVar** missä tahansa, missä väriarvoa voidaan käyttää, niin se korvataan arvolla **Punainen**.  Yleisellä muuttujalla tai kokoelmalla voi olla sama nimi kuin kontekstimuuttujalla.  Tässä tapauksessa kontekstimuuttuja on käsittelyjärjestyksessä etusijalla.  Voit edelleen viitata yleiseen muuttujaan tai kokoelmaan käyttämällä [selvitysoperaattoria](functions/operators.md#disambiguation-operator) **@[MyColor]**.

## <a name="create-a-context-variable"></a>Kontekstimuuttujan luominen
Katsotaan seuraavaksi, miten laskin luodaan käyttäen kontekstimuuttujaa yleisen muuttujan sijasta.    

Näin kontekstimuuttujat toimivat:

* Voit luoda ja määrittää kontekstimuuttujia käyttämällä **[UpdateContext](functions/function-updatecontext.md)**-funktiota.  Jos kontekstimuuttuja ei vielä ole olemassa ensimmäisen päivityksen aikana, se luodaan *tyhjällä* oletusarvolla.
* Kontekstimuuttujat luodaan ja niitä päivitetään tietueiden kanssa. Muissa ohjelmointityökaluissa voidaan yleisesti käyttää merkkiä ”=” vastaamaan varausta, kuten ”x = 1”.  Kontekstimuuttujien yhteydessä on käytössä **{x: 1}**. Kun käytät kontekstimuuttujaa, käytä suoraan sen nimeä.  
* Voit myös määrittää kontekstimuuttujan, kun näyttö tulee näkyviin käyttämällä **[Siirry](functions/function-navigate.md)**-funktiota. Jos kuvittelet näytön olevan eräänlainen toimintosarja tai aliohjelma, tämä muistuttaa parametrin välittämistä muissa ohjelmointityökaluissa.
* Paitsi **[Siirry](functions/function-navigate.md)**-funktio, kontekstimuuttujat on rajoitettu yhden näytön kontekstiin, jossa ne saavat nimensä.  Niitä ei voi käyttää tai määrittää tämän kontekstin ulkopuolella.
* Kontekstimuuttujat voivat sisältää mitä tahansa arvoja, mukaan lukien merkkijonoja, lukuja, tietueita ja [taulukkoja](working-with-tables.md).

Rakennetaan laskuri uudelleen käyttämällä kontekstimuuttujaa:

1. Lisää tekstisyötteen ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **Set( RunningTotal, RunningTotal + Text1 )**
   
    Kun käyttäjä valitsee ensimmäisen kerran **Lisää**-painikkeen ja **[UpdateContext](functions/function-updatecontext.md)** kutsutaan, luodaan **RunningTotal**, jonka oletusarvo on *tyhjä*.  Lisäksi sitä käsitellään nollana.
   
    ![](media/working-with-variables/context-variable-1.png)
4. Jotta juokseva summa määritetään **nollaksi** aina, kun käyttäjä valitsee **Tyhjennä**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **UpdateContext ({RunningTotal: 0})**
   
    **[UpdateContext](functions/function-updatecontext.md)**-funktiota käytetään kaavan **UpdateContext( { RunningTotal: 0 } )** kanssa.
   
    ![](media/working-with-variables/context-variable-2.png)
5. Lisää **[Selite](controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **RunningTotal**.
   
    Tämä kaava lasketaan automaattisesti uudelleen, ja se näyttää käyttäjälle **RunningTotal**-arvon sen muuttuessa sen mukaan, mitä painikkeita käyttäjä valitsee.
   
    ![](media/working-with-variables/context-variable-3.png)
6. Esikatsele sovellusta, ja edellä kuvaamamme laskuri on valmis.  Kirjoita numero tekstiruutuun ja paina **Lisää**-painiketta muutaman kerran.  Kun olet valmis, palaa muokkausominaisuuteen Esc-näppäimellä.  
   
    ![](media/working-with-variables/context-variable-4.png)
7. Voit määrittää kontekstimuuttujan arvon siirtyessäsi näyttöön.  Tästä on hyötyä välitettäessä kontekstia tai parametreja näytöstä toiseen.  Huomaat tämän lisäämällä uuden näytön ja lisäämällä painikkeen, jonka **OnSelect**-ominaisuuden arvo on:
   
    **Siirtyminen (ei mitään, Screen1 {RunningTotal:-1000})**
   
    ![](media/working-with-variables/context-variable-5.png)
   
    Tämän painikkeen valitseminen kohdassa **Screen2** (mikä on mahdollista luomisen aikana, jos valitset painikkeen loppuvaiheessa) näyttää **Screen1**:n ja myös määrittää kontekstimuuttujan **RunningTotal** arvoksi –1000.
   
    ![](media/working-with-variables/context-variable-6.png)
8. Jos haluat nähdä kontekstimuuttujan arvon, valitse **Tiedosto**-valikko ja sitten **Muuttujat** vasemmanpuoleisesta ruudusta.
   
    ![](media/working-with-variables/context-variable-file-1.png)
9. Jos haluat nähdä, missä kontekstimuuttuja määritetään ja missä sitä käytetään, valitse sen.
   
    ![](media/working-with-variables/context-variable-file-2.png)

## <a name="create-a-collection"></a>Luo kokoelma
Tutustutaan lopuksi laskimen lisäämiseen kokoelman avulla.  Koska kokoelma sisältää taulukon, jota on helppo muokata, teemme tästä laskimesta sellaisen, että se säilyttää ”paperinauhan” kustakin annetusta arvosta.

Näin kokoelmat toimivat:

* Luo ja määritä kokoelmia **[ClearCollect](functions/function-clear-collect-clearcollect.md)**-funktiolla.  Voit vaihtoehtoisesti käyttää **[Kerää](functions/function-clear-collect-clearcollect.md)**-funktiota, mutta periaatteessa se edellyttää toista muuttujaa vanhan muuttujan korvaamisen sijasta.  
* Kokoelma on eräänlainen tietolähde ja näin ollen taulukko. Voit käyttää kokoelman yhtä arvoa **[Ensimmäinen](functions/function-first-last.md)**-funktion avulla ja poimia yhden kentän tuloksena saatavasta tietueesta. Jos käytit yksittäistä arvoa **[ClearCollect](functions/function-clear-collect-clearcollect.md)**-funktion kanssa, tämä on **Arvo**-kenttä, kuten tässä esimerkissä:<br>**First(** *VariableName* **).Value**

Luodaan seuraavaksi laskin uudelleen kokoelman avulla:

1. Lisää **[tekstisyötteen](controls/control-text-input.md)** ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **Collect( PaperTape, TextInput1.Text )**
   
    Tämä kaava lisää uuden arvon kokoelman loppuun.  Koska lisäämme yksittäisen arvon, **Kerää** lisää sen automaattisesti yhden sarakkeen taulukkoon, jossa on sarake nimeltä **Arvo**, jota käytämme myöhemmin.
   
    ![](media/working-with-variables/papertape-1.png)
4. Jotta paperinauha tyhjenee käyttäjän valitessa **Tyhjennä**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **Clear( PaperTape )**
   
    ![](media/working-with-variables/papertape-2.png)
5. Näytä juokseva summa lisäämällä otsikko, ja määritä sen **[Teksti](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **Sum( PaperTape, Value )**
   
    ![](media/working-with-variables/papertape-3.png)
6. Suorita laskin painamalla F5-näppäintä, mikä avaa esikatselun, lisää lukuja tekstisyötteen ohjausobjektiin ja valitse painikkeet.
   
    ![](media/working-with-variables/papertape-run-1.png)
7. Palaa oletustyötilaan painamalla Esc-näppäintä.
8. Näytä paperinauha lisäämällä **Arvotaulukko**-ohjausobjekti ja määritä sen **[Kohteet](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **PaperTape**
   
    Joudut myös valitsemaan sarakkeet, jotka näkyvät oikeanpuoleisessa ruudussa. Näytä tässä tapauksessa **Arvo**-sarake:
   
    ![](media/working-with-variables/papertape-4.png)
9. Näytä kokoelman arvot valitsemalla **Tiedosto**-valikosta **Kokoelmat**.
   
    ![](media/working-with-variables/papertape-file.png)
10. Tallenna ja nouda kokoelma lisäämällä kaksi muuta painikeohjausobjektia ja määrittämällä niiden tekstiksi **Lataus** ja **Tallenna**.  Määritä **Lataus**-tekstin **OnSelect**-ominaisuudeksi:
    
     **Clear( PaperTape ); LoadData( PaperTape, "StoredPaperTape", true )**
    
     Joudumme ensin tyhjentämään kokoelman, koska **LoadData** liittää tallennetut arvot kokoelman loppuun.
    
     ![](media/working-with-variables/papertape-5.png)
11. Määritä **Tallenna**-tekstin **OnSelect**-ominaisuudeksi:
    
     **SaveData( PaperTape, "StoredPaperTape" )**
    
     ![](media/working-with-variables/papertape-6.png)
12. Esikatsele uudelleen painamalla F5-näppäintä, kirjoita luvut tekstisyötteen ohjausobjektiin ja valitse painikkeet.  Valitse **Tallenna**-painike.  Sulje ja lataa sovellus uudelleen ja lataa kokoelma uudelleen valitsemalla **Lataus**-painike.  
    
    > [!NOTE]
    > **SaveData** ja **LoadData** eivät toimi verkkoselainta käytettäessä. Käytössä on oltava Studio asennettuna Windowsiin tai jokin mobiililaitteille tarkoitettu toisto-ohjelma.  

