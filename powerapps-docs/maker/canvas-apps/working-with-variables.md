---
title: Muuttujien ymmärtäminen pohjaan perustuvissa sovelluksissa | Microsoft Docs
description: Viitetietoja työskentelyyn tilan, kontekstimuuttujien ja kokoelmien parissa pohjaan perustuvissa sovelluksissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 02/28/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6f46dcdf300c91be9fbc2f39e6b2a5418a4b82de
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61558983"
---
# <a name="understand-canvas-app-variables-in-powerapps"></a>Pohjaan perustuvan sovelluksen muuttujien ymmärtäminen PowerAppsissa

Jos olet käyttänyt toisenlaista ohjelmointityökalua, kuten Visual Basic tai JavaScriptiä, ihmettelet ehkä: **Missä muuttujat ovat?** PowerApps on hieman erilainen ja edellyttää erilaista käyttötapaa. Etsimisen muuttujan, kun rakennat pohjaan perustuvan sovelluksen, sijaan Mieti: **Mitä tekisit Excelissä?**

Muissa työkaluissa olet ehkä eksplisiittisesti suorittanut laskutoimituksen ja tallentanut tuloksen muuttujaan. PowerApps ja Excel laskevat kuitenkin kaavat automaattisesti uudelleen syötetietojen muuttuessa, joten muuttujia ei yleensä tarvitse luoda ja päivittää. Noudattamalla tätä lähestymistapaa aina kun mahdollista, voit helpommin luoda, ymmärtää ja ylläpitää sovelluksia.

Joudut joissakin tapauksissa käyttämään muuttujia PowerAppsissa, joka laajentaa Excelin mallia lisäämällä [toimintakaavioita](working-with-formulas-in-depth.md). Nämä kaavat suoritetaan esimerkiksi silloin, kun käyttäjä valitsee painikkeen. Toimintakaaviossa kannattaa usein määrittää muuttuja, jota käytetään muissa kaavoissa.

Yleensä kannattaa välttää muuttujien käyttämistä. Toisinaan kuitenkin vain muuttuja pystyy mahdollistamaan halutun ominaisuuden. Muuttujat luodaan implisiittisesti ja kirjoittaa, kun ne näkyvät toiminnot, jotka niiden arvojen asettamisyritysten. 

## <a name="translate-excel-into-powerapps"></a>Excel vs. PowerApps

### <a name="excel"></a>Excel

Muistellaan, miten Excel toimii. Solu voi sisältää arvon, kuten luvun tai merkkijonon, tai kaavan, joka perustuu muiden solujen arvoihin. Sen jälkeen, kun käyttäjä on lisännyt eri arvon soluun, Excel laskee automaattisesti uudestaan kaavat, jotka ovat riippuvaisia uudesta arvosta. Tätä varten ei tarvitse tehdä mitään ohjelmointia.

Seuraavassa esimerkissä solun **A3** asetetaan kaavan **A1 + A2**. Jos **A1** tai **A2** muutokset **A3** laskee automaattisesti muutoksen. Tämä ongelma edellyttää ei ole koodaamisen ulkopuolella itse kaavaa.

![Animaation kahden luvun Excelin summa lasketaan uudelleen](media/working-with-variables/excel-recalc.gif)

Excelissä ei ole muuttujia. Kaavan sisältävän solun arvo muuttuu siihen syötettyjen tietojen mukaan, mutta kaavan tulosta ei voi muistaa eikä tallentaa soluun tai minnekään muualle. Jos muutat solun arvoa, koko laskentataulukko saattaa muuttua, jolloin aiemmin lasketut arvot menetetään. Excel-käyttäjä voi kopioida ja liittää soluja, mutta tämä on käyttäjän manuaalisessa hallinnassa, eikä sitä ole mahdollista tehdä kaavoilla.

### <a name="powerapps"></a>PowerApps

Sovellukset, jotka luot PowerAppsissa, toimivat hyvin samalla tavalla kuin Excel. Sen sijaan, että päivität solut, voit lisätä ohjausobjekteja mihin tahansa näytön kohtaan ja nimetä ne kaavoissa käyttämistä varten.

Voit esimerkiksi toistaa Excelin toiminnan sovelluksessa lisäämällä **[nimen](controls/control-text-box.md)** ohjausobjekti nimeltä **Label1**, ja kaksi **[Text input](controls/control-text-input.md)** ohjausobjektia nimeltä **TextInput1** ja **TextInput2**. Jos sitten määrität **[tekstin](controls/properties-core.md)** ominaisuuden **Label1** - **TextInput1 + TextInput2**, se näkyy aina riippumatta lukujen summan, ovat **TextInput1** ja **TextInput2** automaattisesti.

![Powerappsin lukujen summan](media/working-with-variables/recalc1.png)

Huomaa, **Label1** ohjausobjekti on valittuna, sen **[tekstin](controls/properties-core.md)** kaavan kaavarivillä näytön yläreunassa. Tässä on kaava **TextInput1 + TextInput2**. Tämä kaava luo riippuvuussuhteen näiden ohjausobjektien välille, samalla tavalla kuin riippuvuuksia luodaan Excel-työkirjan solujen välille.  Muutetaanpa arvo **TextInput1**:

![Animaation summan kahden luvun powerappsissa](media/working-with-variables/recalc2.gif)

Kaava **Label1** on automaattisesti uudelleen, näemme uuden arvon.

PowerAppsissa voidaan käyttää kaavoja määrittämään ohjausobjektin ensisijaisen arvon lisäksi myös ominaisuuksia, kuten muotoilun. Seuraavassa esimerkissä kaava nimen **[Väri](controls/properties-color-border.md)**-ominaisuudelle näyttää negatiiviset arvot automaattisesti punaisella. **[If](functions/function-if.md)**-funktio näyttää hyvin tutulta Excelistä:

`If( Value(Label1.Text) < 0, Red, Black )`

![Animaation ehdollinen muotoilu](media/working-with-variables/recalc-color.gif)

Voit käyttää kaavoja moniin erilaisiin skenaarioihin:

* Käyttämällä laitteen GPS:ää kartan ohjausobjekti voi näyttää nykyisen sijaintisi kaavalla, joka käyttää signaaleja **Location.Latitude** ja **Location.Longitude**.  Kun siirryt, kartta seuraa sijaintiasi automaattisesti.
* Muut käyttäjät voivat päivittää [tietolähteitä](working-with-data-sources.md).  Muut ryhmän jäsenet voivat esimerkiksi päivittää SharePoint-luettelon kohteita.  Kun päivität tietolähteen, riippuvat kaavat lasketaan automaattisesti uudelleen vastaamaan päivitettyjä tietoja. Jos viemme tätä esimerkkiä eteenpäin, haluat ehkä määrittää valikoiman **[Kohteet](controls/properties-core.md)**-ominaisuuden kaavaksi **Filter( SharePointList )**, joka näyttää automaattisesti vastikään suodatettujen [tietueiden](working-with-tables.md#records) sarjan.

### <a name="benefits"></a>Edut

Sovellusten tekemisellä kaavojen avulla on monia etuja:

* Jos tunnet Excelin, tunnet PowerAppsin. Malli ja kaavan kieli ovat samat.
* Jos olet käyttänyt muita ohjelmointityökaluja, mieti, kuinka paljon koodia vaadittaisiin näiden esimerkkien suorittamiseen.  Visual Basicissa joutuisit kirjoittamaan tapahtumakäsittelijän muutostapahtumalle jokaiselle tekstinsyötteen ohjausobjektille.  Koodi, joka suorittaa jokaisen laskutoimituksen, on ylimääräinen ja saattaa joutua epätahtiin, tai joutuisit kirjoittamaan yleisen aliohjelman.  PowerAppsissa sait kaiken tehtyä yksittäisellä yhden rivin kaavalla.
* Mistä **Label1**käyttäjän teksti on peräisin, tiedät selville: kaavassa **[tekstin](controls/properties-core.md)** ominaisuus.  Tämän ohjausobjektin tekstiin ei voi vaikuttaa millään muulla tavalla.  Perinteisessä ohjelmointityökalussa kaikki tapahtumakäsittelijät tai aliohjelmat voivat muuttaa nimen arvoa ohjelman missä tahansa kohdassa.  Muuttujan muuttamisen ajan ja paikan jäljittäminen saattaa tällöin vaikeutua.
* Jos käyttäjä tekee muutoksen liukusäätimeen ja muuttaa sitten mieltään, liukusäädin on mahdollista palauttaa sen alkuperäiseen arvoon.  Mitään muutosta ei ole havaittavissa: sovellus näyttää samat ohjausobjektin arvot kuin aiemminkin.  Kokeiluista ja entä jos -testailuista ei ole seuraamuksia samalla tavalla kuin Excelissä.  

Yleisesti ottaen, jos voit saavuttaa tehosteen käyttämällä kaavaa, se kannattaa. Anna PowerApps-kaavan tehdä työ puolestasi.  

## <a name="know-when-to-use-variables"></a>Milloin muuttujia kannattaa käyttää

Muutetaan yksinkertainen lisäystoiminto siten, että se toimii kuin perinteinen laskin, joka näyttää juoksevan summan. Jos valitset **Lisää**-painikkeen, lisäät luvun juoksevaan summaan. Jos valitset **Tyhjennä**-painikkeen, palautat juoksevan summan nollaksi.

| Näytä | Kuvaus |
|----|----|
| <style> IMG {Enimmäisleveys: ei mitään} </style> ![tekstiviesti sovelluksen syötteen ohjausobjektia, selite ja kaksi painiketta](media/working-with-variables/button-changes-state-1.png) | Kun sovellus käynnistyy, Juokseva summa on 0.<br><br>Punaista edustaa käyttäjän allekirjoitus, johon käyttäjä kirjoittaa tekstisyötteen ruutua **77**. |
| ![Tekstisyötteen ohjausobjekti sisältää 77 ja Lisää-painiketta painetaan](media/working-with-variables/button-changes-state-2.png) | Käyttäjä valitsee **Lisää** painike. |
| ![Kokonaismäärä on 77 ja toinen 77 lisätään siihen](media/working-with-variables/button-changes-state-3.png) | 77 lisätään juoksevan summan.<br><br>Käyttäjä valitsee **Lisää** painike uudelleen. |
| ![Summa on 154, ennen kuin se on tyhjä.](media/working-with-variables/button-changes-state-4.png) | 77 lisätään uudelleen juoksevan summan, 154 tuloksena.<br><br>Käyttäjä valitsee **Tyhjennä** painike. |
| ![Summa on poistettu.](media/working-with-variables/button-changes-state-5.png) | Juokseva summa palautetaan 0. |

Laskurimme käyttää jotain, mikä puuttuu Excelistä: painiketta. Tässä sovelluksessa ei voi käyttää vain kaavoja juoksevan summan laskemiseen, koska sen arvo vaihtelee useiden käyttäjän valitsemien toimintojen mukaan. Juokseva summa on sen sijaan tallennettava ja päivitettävä manuaalisesti. Useimmat ohjelmointityökalut tallentavat nämä tiedot *muuttujaan*.

Joskus tarvitset muuttujan sovellukseen, jotta se toimisi haluamallasi tavalla.  Tehtävä ei ole helppo:

* Juokseva summa täytyy päivittää manuaalisesti. Automaattinen uudelleenlaskenta ei tee sitä puolestasi.
* Juoksevaa summaa ei enää voida laskea muiden ohjausobjektien arvojen perusteella. Tämä vaihtelee sen mukaan, miten monta kertaa käyttäjä valitsi **Lisää**-painikkeen ja mikä arvo tekstisyötteen ohjausobjektissa oli kullakin kerralla. Lisäsikö käyttäjä luvun 77 ja valitsi **Lisää** kahdesti, vai määrittikö hän luvut 24 ja 130 kullekin lisäykselle? Eroa ei ole, kun summa on saavuttanut luvun 154.
* Muutokset summaan voivat olla peräisin eri poluilta. Tässä esimerkissä sekä **Lisää**- että **Tyhjennä**-painikkeilla voidaan päivittää summa. Jos sovellus ei toimi odotetulla tavalla, kumpi painike aiheuttaa ongelman?

## <a name="use-a-global-variable"></a>Käyttää yleistä muuttujaa

Jotta voimme luoda laskimen, tarvitsemme muuttujan, joka sisältää juoksevan summan. PowerApps-muuttujat, joiden kanssa on helpointa toimia, ovat *yleisiä muuttujia*.  

Näin yleiset muuttujat toimivat:

* Yleisen muuttujan arvo asetetaan **[Set](functions/function-set.md)**-funktiolla.  **Set( MyVar, 1 )** asettaa yleisen muuttujan **MyVar** arvoon **1**.
* Yleistä muuttujaa käytetään viittaamalla nimeen, jota käytetään **Set**-funktion kanssa.  Tässä tapauksessa **MyVar** palauttaa arvon **1**.
* Yleiset muuttujat voivat sisältää mitä tahansa arvoja, mukaan lukien merkkijonoja, lukuja, tietueita ja [taulukkoja](working-with-tables.md).

Rakennetaan laskuri uudelleen käyttämällä yleistä muuttujaa:

1. Lisää tekstisyötteen ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **Määritä (RunningTotal, RunningTotal + TextInput1)**

    Pelkkä olemassaolo tämä kaava määrittää **RunningTotal** yleisen muuttujan, joka sisältää useita koska **+** operaattori. Voit viitata **RunningTotal** missä tahansa sovelluksessa. Aina, kun käyttäjä avaa sovelluksessa **RunningTotal** ensimmäinen arvo on *tyhjä*.

    Kun käyttäjä valitsee ensimmäisen kerran **Lisää** painike ja **[määrittää](functions/function-set.md)** suoritetaan, **RunningTotal** asetetaan arvo  **RunningTotal + TextInput1**.

    ![Lisää-painikkeen OnSelect-ominaisuuden asetus on joukko-funktio](media/working-with-variables/global-variable-1.png)

4. Jotta juokseva summa määritetään **nollaksi** aina, kun käyttäjä valitsee **Tyhjennä**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **Set( RunningTotal, 0 )**

    ![Tyhjennä-painike OnSelect-ominaisuus määritetään joukko-funktio](media/working-with-variables/global-variable-2.png)

5. Lisää **[Nimi](controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **RunningTotal**.

    Tämä kaava lasketaan automaattisesti uudelleen, ja se näyttää käyttäjälle **RunningTotal**-arvon sen muuttuessa sen mukaan, mitä painikkeita käyttäjä valitsee.

    ![Nimen teksti-ominaisuuden asetus on muuttujan nimi](media/working-with-variables/global-variable-3.png)

6. Esikatsele sovellusta, ja edellä kuvaamamme laskuri on valmis. Kirjoita numero tekstiruutuun ja paina **Lisää**-painiketta muutaman kerran. Kun olet valmis, palaa muokkausominaisuuteen Esc-näppäimellä.

    ![Tekstisyöte-ohjausobjekti sisältää arvon ja selite Juokseva summa](media/working-with-variables/global-variable-4.png)

7. Jos haluat nähdä yleisen muuttujan arvon, valitse **tiedoston** valikko ja valitse **muuttujien** vasemmanpuoleisesta ruudusta.

    ![Tiedosto-valikon muuttujat-asetus](media/working-with-variables/global-variable-file-1.png)

8. Jos haluat nähdä kaikki paikat, joissa muuttuja määritetään ja käytetään, valitse se.

    ![Luettelon sijainti, jossa muuttujaa käytetään](media/working-with-variables/global-variable-file-2.png)

## <a name="types-of-variables"></a>Muuttujien tyypit

Powerappsissa on kolme muuttujatyyppiä:

| Muuttujan tyyppi | Vaikutusalue | Kuvaus | Funktiot, jotka vahvistavat |
| --- | --- | --- | --- |
| Yleiset muuttujat |Sovellus |Helpoin käyttää. Sisältää esimerkiksi luvun, tekstimerkkijonon, totuusarvon, tietueen tai taulukon, johon voidaan viitata missä tahansa sovelluksen kohdassa. |[**Joukko**](functions/function-set.md) |
| Kontekstimuuttujat |Näyttö |Sopii hyvin arvojen välittämiseen näyttöön, kuten parametrit toimintosarjassa muissa kielissä. Voidaan viitata vain yhdestä näytöstä. |[**UpdateContext**](functions/function-updatecontext.md)<br>[**Navigate**](functions/function-navigate.md) |
| Kokoelmat |App |Sisältää taulukon, jota voi viitata missä tahansa sovelluksessa. Sallii taulukon sisällön muokkaamisen sen sijaan, että se määritettäisiin kokonaisena. Voidaan tallentaa paikalliseen laitteeseen myöhempää käyttöä varten. |[**Collect**](functions/function-clear-collect-clearcollect.md)<br>[**ClearCollect**](functions/function-clear-collect-clearcollect.md) |

## <a name="create-and-remove-variables"></a>Luo ja poista muuttujat

Kaikki muuttujat luodaan implisiittisesti, kun ne näkyvät **määrittää**, **UpdateContext**, **Navigate**, **kerätä**, tai  **ClearCollect** funktio. Muuttuja ja tyyppi ilmoittamaan sinulle on vain siihen näistä funktioista missä tahansa sovelluksessa. Mikään näistä funktioista luoda muuttujia. he vain täyttää muuttujien arvot. Älä koskaan kielessä muuttujia eksplisiittisesti sillä ehkä toista ohjelmointityökalua, ja kaikki kirjoittamalla on implisiittinen käyttöön.

Esimerkiksi voi olla Painikeohjausobjekti, jolla **OnSelect** kaava on yhtä suuri kuin **Set (X, 1)**. Tämä kaava määrittää **X** muuttujaksi, jonka tyyppi on numero. Voit käyttää **X** kaavoissa luku ja kyseisen muuttujan on *tyhjä* sen jälkeen, kun avaat sovelluksen, mutta ennen kuin valitset painikkeen. Kun valitset painikkeen, voit antaa **X** arvo **1**.

Jos olet lisännyt toinen painike ja määritä sen **OnSelect** ominaisuudeksi **Set (X, ”Hei”)**, ilmetä virhe, koska (merkkijono) ei vastaa tyyppi edellisten **määrittää**(luku). Muuttujan implisiittinen määritelmät on hyväksyttävä tyypin. Uudelleen, kaikki tämä tapahtui, koska olet mainitaan **X** kaavoissa ei, koska jokin kaavojen oli itse asiassa suoritetaan.

Poista muuttujan poistamalla kaikki **määrittää**, **UpdateContext**, **Navigate**, **kerätä**, tai **ClearCollect**  funktioita, jotka vahvistavat implisiittisesti muuttujan. Nämä funktiot ilman muuttujaa ei ole. Sinun on poistettava myös muuttujan viittauksia, koska ne aiheuttaa virheen.

## <a name="variable-lifetime-and-initial-value"></a>Muuttujan elinkaaren ja alkuarvo

Kaikki muuttujat säilytetään muistissa, kun sovellus suoritetaan. Kun sovellus sulkeutuu, muuttujien säilyttää arvot menetetään.

Voit tallentaa muuttujan sisällön tietolähteeseen käyttämällä **Patch** tai **kerätä** funktioita. Voit myös tallentaa arvoja kokoelmat laitteesta käyttämällä [ **SaveData** ](functions/function-savedata-loaddata.md) funktio.

Kun käyttäjä avaa sovelluksen, Kaikilla muuttujilla on alkuarvo, *tyhjä*.

## <a name="reading-variables"></a>Muuttujien lukeminen

Arvo luetaan sen muuttujan nimen avulla. Voit esimerkiksi määrittää muuttuja on tämä kaava:

`Set( Radius, 12 )`

Sitten voit käyttää **Radius** tahansa voit määrittää luvun, että se korvataan **12**:

`Pi() * Power( Radius, 2 )`

Jos annat kontekstimuuttujan on sama nimi kuin yleisen muuttujan tai kokoelmaan, kontekstimuuttujan etusijalla. Voit edelleen viitata yleisen muuttujan tai kokoelmassa käytettäessä [selvitysoperaattoria](functions/operators.md#disambiguation-operator) **@[Radius]**.

## <a name="use-a-context-variable"></a>Käytät kontekstimuuttujaa

Katsotaan seuraavaksi, miten laskin luodaan käyttäen kontekstimuuttujaa yleisen muuttujan sijasta.

Näin kontekstimuuttujat toimivat:

* Implisiittisesti muodostaa ja määrittää kontekstimuuttujan **[UpdateContext](functions/function-updatecontext.md)** tai **[Navigate](functions/function-navigate.md)** funktio. Kun sovellus käynnistyy, kaikki kontekstimuuttujat alkuarvo on *tyhjä*.
* Kontekstimuuttujat päivitetään tietueiden kanssa. Muissa ohjelmointityökaluissa voidaan yleisesti käyttää merkkiä ”=” vastaamaan varausta, kuten ”x = 1”. Kontekstimuuttujien, käytä **{x: 1}** sen sijaan. Kun käytät kontekstimuuttujaa, käytä suoraan ilman tietueen syntaksi sen nimeä.
* Voit myös määrittää kontekstimuuttujan käytettäessä **[Navigate](functions/function-navigate.md)** näyttö-toiminnon. Jos kuvittelet näytön olevan eräänlainen toimintosarja tai aliohjelma, tämä menetelmä muistuttaa parametrin välittämistä muissa ohjelmointityökaluissa.
* Paitsi **[Siirry](functions/function-navigate.md)**-funktio, kontekstimuuttujat on rajoitettu yhden näytön kontekstiin, jossa ne saavat nimensä. Niitä ei voi käyttää tai määrittää tämän kontekstin ulkopuolella.
* Kontekstimuuttujat voivat sisältää mitä tahansa arvoja, mukaan lukien merkkijonoja, lukuja, tietueita ja [taulukkoja](working-with-tables.md).

Rakennetaan laskuri uudelleen käyttämällä kontekstimuuttujaa:

1. Lisää tekstisyötteen ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **UpdateContext ({RunningTotal: RunningTotal + TextInput1})**

    Pelkkä olemassaolo tämä kaava määrittää **RunningTotal** kuin jokin kontekstimuuttuja, joka sisältää useita keskeytti **+** operaattori. Voit viitata **RunningTotal** missä tahansa tässä näytössä. Aina, kun käyttäjä avaa sovelluksessa **RunningTotal** ensimmäinen arvo on *tyhjä*.

    Kun käyttäjä valitsee ensimmäisen kerran **Lisää** painike ja **[UpdateContext](functions/function-updatecontext.md)** suoritetaan, **RunningTotal** asetetaan arvoksi **RunningTotal + TextInput1**.

    ![Lisää OnSelect-ominaisuudessa](media/working-with-variables/context-variable-1.png)

4. Jotta juokseva summa määritetään **nollaksi** aina, kun käyttäjä valitsee **Tyhjennä**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **UpdateContext ({RunningTotal: 0 } )**

    Uudelleen **[UpdateContext](functions/function-updatecontext.md)** käytetään kaavan **UpdateContext ({RunningTotal: 0 } )**.

    ![OnSelect-ominaisuudessa Tyhjennä-painike](media/working-with-variables/context-variable-2.png)

5. Lisää **[Nimi](controls/control-text-box.md)**-ohjausobjekti ja määritä sen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **RunningTotal**.

    Tämä kaava lasketaan automaattisesti uudelleen, ja se näyttää käyttäjälle **RunningTotal**-arvon sen muuttuessa sen mukaan, mitä painikkeita käyttäjä valitsee.

    ![Otsikon tekstin ominaisuutta](media/working-with-variables/context-variable-3.png)

6. Esikatsele sovellusta, ja edellä kuvaamamme laskuri on valmis. Kirjoita numero tekstiruutuun ja paina **Lisää**-painiketta muutaman kerran. Kun olet valmis, palaa muokkausominaisuuteen Esc-näppäimellä.

    ![Tekstisyöte-ohjausobjekti näyttää arvo ja selite näyttää juoksevan summan](media/working-with-variables/context-variable-4.png)

7. Voit määrittää kontekstimuuttujan arvon siirtyessäsi näyttöön. Tästä on hyötyä välitettäessä kontekstia tai parametreja näytöstä toiseen. Tätä tapaa osoittamaan Lisää näyttö, Lisää painike ja määritä sen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    **Navigate( Screen1, None, { RunningTotal: -1000 } )**

    ![Painikkeen OnSelect-ominaisuus](media/working-with-variables/context-variable-5.png)

    Pidä Alt-näppäintä samalla, kun valitset tämän painikkeen avulla sekä Näytä **Screen1** ja määrittää kontekstimuuttujan **RunningTotal** arvoksi – 1000.

    ![Screen1 on avattu](media/working-with-variables/context-variable-6.png)

8. Jos haluat nähdä kontekstimuuttujan arvon, valitse **tiedoston** valikko ja valitse sitten **muuttujien** vasemmanpuoleisesta ruudusta.

    ![Tiedosto-valikon muuttujat-vaihtoehto](media/working-with-variables/context-variable-file-1.png)

9. Näytetään, missä kontekstimuuttuja määritetään ja käytetään, valitse se.

    ![Luettelo, jossa muuttujan käytetään](media/working-with-variables/context-variable-file-2.png)

## <a name="use-a-collection"></a>Käytä kokoelma

Tutustutaan lopuksi laskimen lisäämiseen kokoelman avulla.  Koska kokoelma sisältää taulukon, jota on helppo muokata, teemme tästä laskimesta sellaisen, että se säilyttää ”paperinauhan” kustakin annetusta arvosta.

Näin kokoelmat toimivat:

* Luo ja määritä kokoelmia **[ClearCollect](functions/function-clear-collect-clearcollect.md)**-funktiolla.  Voit vaihtoehtoisesti käyttää **[Collect](functions/function-clear-collect-clearcollect.md)**-funktiota, mutta periaatteessa se edellyttää toista muuttujaa vanhan muuttujan korvaamisen sijasta.  
* Kokoelma on eräänlainen tietolähde ja näin ollen taulukko. Voit käyttää kokoelman yhtä arvoa **[First](functions/function-first-last.md)**-funktion avulla ja poimia yhden kentän tuloksena saatavasta tietueesta. Jos käytit yksittäistä arvoa **[ClearCollect](functions/function-clear-collect-clearcollect.md)**-funktion kanssa, tämä on **Arvo**-kenttä, kuten tässä esimerkissä:<br>
**First(** *VariableName* **).Value**

Luodaan seuraavaksi laskin uudelleen kokoelman avulla:

1. Lisää **[tekstisyötteen](controls/control-text-input.md)** ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)**-ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **Collect( PaperTape, TextInput1.Text )**

    Tämä kaava pelkkä olemassaolo määrittää **PaperTape** kuin kokoelma, jossa tekstimerkkijonoa yksisarakkeisen taulukon. Voit viitata **PaperTape** missä tahansa sovelluksessa. Aina, kun käyttäjä avaa sovelluksessa **PaperTape** on tyhjä taulukko.

    Kun tämä kaava suoritetaan, se lisää uuden arvon kokoelman loppuun. Koska lisäämme yksittäisen arvon, **kerätä** sijoittaa sen automaattisesti yhden sarakkeen taulukko, ja sarakkeen nimi on **arvo**, jota käytät myöhemmin.

    ![Lisää OnSelect-ominaisuudessa](media/working-with-variables/papertape-1.png)

4. Poista Paperinauha, kun käyttäjä valitsee **Tyhjennä** painikkeen, määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuuden arvoksi tämä kaava:

    **Clear( PaperTape )**

    ![OnSelect-ominaisuudessa Tyhjennä-painike](media/working-with-variables/papertape-2.png)

5. Näytä juokseva summa lisäämällä nimi, ja määritä sen **[Teksti](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **Sum( PaperTape, Value )**

    ![Otsikon tekstin ominaisuutta](media/working-with-variables/papertape-3.png)

6. Suorita laskin painamalla F5-näppäintä, mikä avaa esikatselun, lisää lukuja tekstisyötteen ohjausobjektiin ja valitse painikkeet.

    ![Tekstisyötteen ohjausobjekti näyttää arvon ja otsikko Näytä Juokseva summa](media/working-with-variables/papertape-run-1.png)

7. Palaa oletustyötilaan painamalla Esc-näppäintä.

8. Näytä paperinauha lisäämällä **Arvotaulukko**-ohjausobjekti ja määritä sen **[Kohteet](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **PaperTape**

    Valitse oikeanpuoleisessa ruudussa **arvo** sarake näyttää sen.

    ![Tietojen taulukon, joka näyttää arvoja lisätään kokoelmaan](media/working-with-variables/papertape-4.png)

9. Näytä kokoelman arvot valitsemalla **Tiedosto**-valikosta **Kokoelmat**.

    ![PaperTape kokoelman esikatselun](media/working-with-variables/papertape-file.png)

10. Tallentaa ja Nouda kokoelma lisäämällä kaksi muuta painikeohjausobjektia ja määrittämällä niiden **tekstin** ominaisuudet, jotta voit **lataaminen** ja **Tallenna**. Määritä **OnSelect** -ominaisuuden **lataaminen** painike Tämä kaava:

     **Clear( PaperTape ); LoadData( PaperTape, "StoredPaperTape", true )**

     Haluat tyhjentää kokoelman ensin, koska **LoadData** liittää tallennetut arvot kokoelman loppuun.

     ![Lataa-painikkeen OnSelect-ominaisuudessa](media/working-with-variables/papertape-5.png)

11. Määritä **OnSelect** -ominaisuuden **Tallenna** painike Tämä kaava:

     **SaveData( PaperTape, "StoredPaperTape" )**

     ![Ominaisuuden OnSelect * Tallenna-painiketta](media/working-with-variables/papertape-6.png)

12. Esikatsele uudelleen painamalla F5-näppäintä, kirjoita luvut tekstisyötteen ohjausobjektiin ja valitse painikkeet. Valitse **Tallenna**-painike. Sulje ja lataa sovellus uudelleen ja valitse **lataaminen** painike kokoelma uudelleen.

> [!NOTE]
> **SaveData** ja **LoadData** PowerApps Mobilessa, mutta ei PowerApps Studio tai web Playeristä PowerApps-funktiota.