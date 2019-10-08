---
title: Muuttujien ymmärtäminen pohjaan perustuvissa sovelluksissa | Microsoft Docs
description: Viitetietoja työskentelyyn tilan, kontekstimuuttujien ja kokoelmien parissa pohjaan perustuvissa sovelluksissa
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 02/28/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 036de37aa2593254d6ae665f8546fe4038dd922d
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994841"
ms.PowerAppsDecimalTransform: true
---
# <a name="understand-canvas-app-variables-in-powerapps"></a>Pohjaan perustuvan sovelluksen muuttujien ymmärtäminen PowerAppsissa

Jos olet käyttänyt toista ohjelmointi työkalua, kuten Visual Basic tai JavaScriptiä, saatat pyytää seuraavaa: **Missä muuttujat ovat?** PowerApps on hieman erilainen ja edellyttää erilaista käyttötapaa. Sen sijaan, että haluat saada muuttujan, kun rakennat kangas sovellusta, kysy itseltäsi seuraavaa: **Mitä Excelissä pitäisi tehdä?**

Muissa työkaluissa olet ehkä eksplisiittisesti suorittanut laskutoimituksen ja tallentanut tuloksen muuttujaan. PowerApps ja Excel laskevat kuitenkin kaavat automaattisesti uudelleen syötetietojen muuttuessa, joten muuttujia ei yleensä tarvitse luoda ja päivittää. Noudattamalla tätä lähestymistapaa aina kun mahdollista, voit helpommin luoda, ymmärtää ja ylläpitää sovelluksia.

Joudut joissakin tapauksissa käyttämään muuttujia PowerAppsissa, joka laajentaa Excelin mallia lisäämällä [toimintakaavioita](working-with-formulas-in-depth.md). Nämä kaavat suoritetaan esimerkiksi silloin, kun käyttäjä valitsee painikkeen. Toimintakaaviossa kannattaa usein määrittää muuttuja, jota käytetään muissa kaavoissa.

Yleensä kannattaa välttää muuttujien käyttämistä. Toisinaan kuitenkin vain muuttuja pystyy mahdollistamaan halutun ominaisuuden. Muuttujat luodaan implisiittisesti, ja ne kirjoitetaan, kun ne näkyvät funktioissa, jotka asettavat arvot. 

## <a name="translate-excel-into-powerapps"></a>Excel vs. PowerApps

### <a name="excel"></a>Excel

Muistellaan, miten Excel toimii. Solu voi sisältää arvon, kuten luvun tai merkkijonon, tai kaavan, joka perustuu muiden solujen arvoihin. Sen jälkeen, kun käyttäjä on lisännyt eri arvon soluun, Excel laskee automaattisesti uudestaan kaavat, jotka ovat riippuvaisia uudesta arvosta. Tätä varten ei tarvitse tehdä mitään ohjelmointia.

Seuraavassa esimerkissä solu **a3** on määritetty kaavalla **a1 + a2**. Jos **a1** -tai **a2** -muutos muuttuu, **a3** -muutos lasketaan automaattisesti uudelleen muutoksen mukaan. Tämä toiminta ei edellytä koodausta kaavan ulkopuolella.

![Animaatio kahden luvun summan uudelleenlaskemista varten Excelissä](media/working-with-variables/excel-recalc.gif)

Excelissä ei ole muuttujia. Kaavan sisältävän solun arvo muuttuu siihen syötettyjen tietojen mukaan, mutta kaavan tulosta ei voi muistaa eikä tallentaa soluun tai minnekään muualle. Jos muutat solun arvoa, koko laskentataulukko saattaa muuttua, jolloin aiemmin lasketut arvot menetetään. Excel-käyttäjä voi kopioida ja liittää soluja, mutta tämä on käyttäjän manuaalisessa hallinnassa, eikä sitä ole mahdollista tehdä kaavoilla.

### <a name="powerapps"></a>PowerApps

Sovellukset, jotka luot PowerAppsissa, toimivat hyvin samalla tavalla kuin Excel. Sen sijaan, että päivität solut, voit lisätä ohjausobjekteja mihin tahansa näytön kohtaan ja nimetä ne kaavoissa käyttämistä varten.

Voit esimerkiksi replikoida sovelluksen Excel-toiminnot **[lisäämällä nimi-ohjaus objektin nimeltä](controls/control-text-box.md)** **Label1**ja kaksi **[teksti syöte](controls/control-text-input.md)** ohjaus objektia nimeltä **TextInput1** ja **TextInput2**. Jos asetat **[teksti](controls/properties-core.md)** -ominaisuudeksi **Label1** - **TextInput1 + TextInput2**, se näyttää aina niiden lukujen summan, jotka ovat **TextInput1** ja **TextInput2** automaattisesti.

![Kahden luvun summan laskeminen Powerappsissa](media/working-with-variables/recalc1.png)

Huomaa, että **Label1** -ohjaus objekti on valittuna ja näyttää sen **[teksti](controls/properties-core.md)** kaavan näytön yläreunan kaava rivillä. Tässä on kaava **TextInput1 + TextInput2**. Tämä kaava luo riippuvuussuhteen näiden ohjausobjektien välille, samalla tavalla kuin riippuvuuksia luodaan Excel-työkirjan solujen välille.  Muutetaan **TextInput1**-arvoa:

![Animaatio, joka laskee kahden luvun summan Powerappsissa](media/working-with-variables/recalc2.gif)

Kaava kohteelle **Label1** on laskettu automaattisesti uudelleen, jolloin uusi arvo näytetään.

PowerAppsissa voidaan käyttää kaavoja määrittämään ohjausobjektin ensisijaisen arvon lisäksi myös ominaisuuksia, kuten muotoilun. Seuraavassa esimerkissä kaava nimen **[Väri](controls/properties-color-border.md)** -ominaisuudelle näyttää negatiiviset arvot automaattisesti punaisella. **[If](functions/function-if.md)** -funktio näyttää hyvin tutulta Excelistä:

`If( Value(Label1.Text) < 0; Red; Black )`

![Ehdollisen muotoilun Animaatio](media/working-with-variables/recalc-color.gif)

Voit käyttää kaavoja moniin erilaisiin skenaarioihin:

* Käyttämällä laitteen GPS:ää kartan ohjausobjekti voi näyttää nykyisen sijaintisi kaavalla, joka käyttää signaaleja **Location.Latitude** ja **Location.Longitude**.  Kun siirryt, kartta seuraa sijaintiasi automaattisesti.
* Muut käyttäjät voivat päivittää [tietolähteitä](working-with-data-sources.md).  Muut ryhmän jäsenet voivat esimerkiksi päivittää SharePoint-luettelon kohteita.  Kun päivität tietolähteen, riippuvat kaavat lasketaan automaattisesti uudelleen vastaamaan päivitettyjä tietoja. Jos viemme tätä esimerkkiä eteenpäin, haluat ehkä määrittää valikoiman **[Kohteet](controls/properties-core.md)** -ominaisuuden kaavaksi **Filter( SharePointList )** , joka näyttää automaattisesti vastikään suodatettujen [tietueiden](working-with-tables.md#records) sarjan.

### <a name="benefits"></a>Edut

Sovellusten tekemisellä kaavojen avulla on monia etuja:

* Jos tunnet Excelin, tunnet PowerAppsin. Malli ja kaavan kieli ovat samat.
* Jos olet käyttänyt muita ohjelmointityökaluja, mieti, kuinka paljon koodia vaadittaisiin näiden esimerkkien suorittamiseen.  Visual Basicissa joutuisit kirjoittamaan tapahtumakäsittelijän muutostapahtumalle jokaiselle tekstinsyötteen ohjausobjektille.  Koodi, joka suorittaa jokaisen laskutoimituksen, on ylimääräinen ja saattaa joutua epätahtiin, tai joutuisit kirjoittamaan yleisen aliohjelman.  PowerAppsissa sait kaiken tehtyä yksittäisellä yhden rivin kaavalla.
* Jos haluat ymmärtää, mistä **Label1**teksti on perä isin, tiedät tarkalleen, mistä näyttää: **[teksti](controls/properties-core.md)** -ominaisuuden kaava.  Tämän ohjausobjektin tekstiin ei voi vaikuttaa millään muulla tavalla.  Perinteisessä ohjelmointityökalussa kaikki tapahtumakäsittelijät tai aliohjelmat voivat muuttaa nimen arvoa ohjelman missä tahansa kohdassa.  Muuttujan muuttamisen ajan ja paikan jäljittäminen saattaa tällöin vaikeutua.
* Jos käyttäjä tekee muutoksen liukusäätimeen ja muuttaa sitten mieltään, liukusäädin on mahdollista palauttaa sen alkuperäiseen arvoon.  Mitään muutosta ei ole havaittavissa: sovellus näyttää samat ohjausobjektin arvot kuin aiemminkin.  Kokeiluista ja entä jos -testailuista ei ole seuraamuksia samalla tavalla kuin Excelissä.  

Yleisesti ottaen, jos voit saavuttaa tehosteen käyttämällä kaavaa, se kannattaa. Anna PowerApps-kaavan tehdä työ puolestasi.  

## <a name="know-when-to-use-variables"></a>Milloin muuttujia kannattaa käyttää

Muutetaan yksinkertainen lisäystoiminto siten, että se toimii kuin perinteinen laskin, joka näyttää juoksevan summan. Jos valitset **Lisää**-painikkeen, lisäät luvun juoksevaan summaan. Jos valitset **Tyhjennä**-painikkeen, palautat juoksevan summan nollaksi.

| Näyttö | Kuvaus |
|----|----|
| <style>IMG {Max-width: none}</style> ![app, jossa on teksti syöte-ohjaus objekti, otsikko ja kaksi painiketta @ no__t-2 | Kun sovellus käynnistyy, juokseva summa on 0.<br><br>Punainen piste edustaa käyttäjän sormea teksti syöte ruudussa, jossa käyttäjä kirjoittaa **77**. |
| ![Teksti syöte-ohjaus objekti sisältää 77, ja Lisää-painiketta painetaan](media/working-with-variables/button-changes-state-2.png) | Käyttäjä valitsee **Lisää** -painikkeen. |
| ![Kokonaismäärä on 77, ja siihen lisätään toinen 77](media/working-with-variables/button-changes-state-3.png) | 77 lisätään juoksevaan summaan.<br><br>Käyttäjä valitsee **Lisää** -painikkeen uudelleen. |
| ![Kokonaismäärä on 154, ennen kuin se tyhjennetään.](media/working-with-variables/button-changes-state-4.png) | 77 lisätään juoksevaan summaan, jolloin tuloksena on 154.<br><br>Käyttäjä valitsee **Tyhjennä** -painikkeen. |
| ![Summa tyhjennetään.](media/working-with-variables/button-changes-state-5.png) | Juokseva summa palautetaan arvoksi 0. |

Laskurimme käyttää jotain, mikä puuttuu Excelistä: painiketta. Tässä sovelluksessa ei voi käyttää vain kaavoja juoksevan summan laskemiseen, koska sen arvo vaihtelee useiden käyttäjän valitsemien toimintojen mukaan. Juokseva summa on sen sijaan tallennettava ja päivitettävä manuaalisesti. Useimmat ohjelmointityökalut tallentavat nämä tiedot *muuttujaan*.

Joskus tarvitset muuttujan sovellukseen, jotta se toimisi haluamallasi tavalla.  Tehtävä ei ole helppo:

* Juokseva summa täytyy päivittää manuaalisesti. Automaattinen uudelleenlaskenta ei tee sitä puolestasi.
* Juoksevaa summaa ei enää voida laskea muiden ohjausobjektien arvojen perusteella. Tämä vaihtelee sen mukaan, miten monta kertaa käyttäjä valitsi **Lisää**-painikkeen ja mikä arvo tekstisyötteen ohjausobjektissa oli kullakin kerralla. Lisäsikö käyttäjä luvun 77 ja valitsi **Lisää** kahdesti, vai määrittikö hän luvut 24 ja 130 kullekin lisäykselle? Eroa ei ole, kun summa on saavuttanut luvun 154.
* Muutokset summaan voivat olla peräisin eri poluilta. Tässä esimerkissä sekä **Lisää**- että **Tyhjennä**-painikkeilla voidaan päivittää summa. Jos sovellus ei toimi odotetulla tavalla, kumpi painike aiheuttaa ongelman?

## <a name="use-a-global-variable"></a>Käytä yleistä muuttujaa

Jotta voimme luoda laskimen, tarvitsemme muuttujan, joka sisältää juoksevan summan. PowerApps-muuttujat, joiden kanssa on helpointa toimia, ovat *yleisiä muuttujia*.  

Näin yleiset muuttujat toimivat:

* Yleisen muuttujan arvo asetetaan **[Set](functions/function-set.md)** -funktiolla.  **Set( MyVar; 1 )** asettaa yleisen muuttujan **MyVar** arvoon **1**.
* Yleistä muuttujaa käytetään viittaamalla nimeen, jota käytetään **Set**-funktion kanssa.  Tässä tapauksessa **MyVar** palauttaa arvon **1**.
* Yleiset muuttujat voivat sisältää mitä tahansa arvoja, mukaan lukien merkkijonoja, lukuja, tietueita ja [taulukkoja](working-with-tables.md).

Rakennetaan laskuri uudelleen käyttämällä yleistä muuttujaa:

1. Lisää tekstisyötteen ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)** -ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    **Asetus (RunningTotal, RunningTotal + TextInput1)**

    Tämän kaavan pelkkä olemassaolo muodostaa **Runningtotal** -kohteen maailmanlaajuisena muuttujana, jolla on numero **+-** operaattorin vuoksi. Voit viitata **Runningtotal** -kohteeseen missä tahansa sovelluksessa. Kun käyttäjä avaa tämän sovelluksen, **Runningtotal** -kohteella on alku arvo, joka on *tyhjä*.

    Kun käyttäjä valitsee ensimmäisen kerran **Lisää** -painikkeen ja **[määrittää](functions/function-set.md)** suoritukset, **runningtotal** -arvoksi määritetään arvo **runningtotal + TextInput1**.

    ![Add-painikkeen OnSelect-ominaisuudeksi on määritetty Määritä Function](media/working-with-variables/global-variable-1.png)

4. Jotta juokseva summa määritetään **nollaksi** aina, kun käyttäjä valitsee **Tyhjennä**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    **Set( RunningTotal; 0 )**

    ![Clear-painikkeen OnSelect-ominaisuudeksi on määritetty Määritä Function](media/working-with-variables/global-variable-2.png)

5. Lisää **[Nimi](controls/control-text-box.md)** -ohjausobjekti ja määritä sen **[Teksti](controls/properties-core.md)** -ominaisuudeksi **RunningTotal**.

    Tämä kaava lasketaan automaattisesti uudelleen, ja se näyttää käyttäjälle **RunningTotal**-arvon sen muuttuessa sen mukaan, mitä painikkeita käyttäjä valitsee.

    ![Otsikon Text-ominaisuudeksi on määritetty muuttujan nimi](media/working-with-variables/global-variable-3.png)

6. Esikatsele sovellusta, ja edellä kuvaamamme laskuri on valmis. Kirjoita numero tekstiruutuun ja paina **Lisää**-painiketta muutaman kerran. Kun olet valmis, palaa muokkausominaisuuteen Esc-näppäimellä.

    ![Teksti syöte-ohjaus objekti sisältää arvon, ja selite sisältää juoksevan summan](media/working-with-variables/global-variable-4.png)

7. Jos haluat näyttää yleisen muuttujan arvon, valitse **tiedosto-** valikko ja valitse **muuttujat** vasemmanpuoleisesta ruudusta.

    ![Tiedosto-valikon muuttujat-vaihto ehto](media/working-with-variables/global-variable-file-1.png)

8. Jos haluat näyttää kaikki paikat, joissa muuttuja on määritetty ja käytetty, valitse se.

    ![Sen sijainnin luettelo, jossa muuttujaa käytetään](media/working-with-variables/global-variable-file-2.png)

## <a name="types-of-variables"></a>Muuttujien tyypit

Powerappsissa on kolmenlaisia muuttujia:

| Muuttujan tyyppi | Vaikutusalue | Kuvaus | Funktiot, jotka luovat |
| --- | --- | --- | --- |
| Yleiset muuttujat |Sovellus |Helpoin käyttää. Sisältää esimerkiksi luvun, tekstimerkkijonon, totuusarvon, tietueen tai taulukon, johon voidaan viitata missä tahansa sovelluksen kohdassa. |[**Joukko**](functions/function-set.md) |
| Kontekstimuuttujat |Näyttö |Sopii hyvin arvojen välittämiseen näyttöön, kuten parametrit toimintosarjassa muissa kielissä. Voidaan viitata vain yhdestä näytöstä. |[**UpdateContext**](functions/function-updatecontext.md)<br>[**Navigate**](functions/function-navigate.md) |
| Kokoelmat |App |Sisältää taulukon, johon voidaan viitata mistä tahansa sovelluksessa. Sallii taulukon sisällön muokkaamisen sen sijaan, että se määritettäisiin kokonaisena. Voidaan tallentaa paikalliseen laitteeseen myöhempää käyttöä varten. |[**Collect**](functions/function-clear-collect-clearcollect.md)<br>[**ClearCollect**](functions/function-clear-collect-clearcollect.md) |

## <a name="create-and-remove-variables"></a>Luo ja poista muuttujia

Kaikki muuttujat luodaan implisiittisesti, kun ne näkyvät **joukko**-, **updatecontext**-, **Navigoi**-, **Collect**-tai **clearcollect** -funktiolla. Jos haluat määrittää muuttujan ja sen tyypin, sinun on sisällytettävä se mihin tahansa näistä funktioista missä tahansa sovelluksessa. Mikään näistä funktioista ei luo muuttujia; ne vain täyttävät muuttujat arvoilla. Et koskaan Määrittele muuttujia eksplisiittisesti samalla tavalla kuin muissa ohjelmointi työkaluissa, ja kaikki kirjoittaminen on implisiittistä käytöstä.

Sinulla voi olla esimerkiksi painike-ohjaus objekti, jolla on **onselect** -kaava, joka on yhtä suuri kuin **asetus (X, 1)** . Tämä kaava muodostaa **X** -muuttujan, jonka tyyppi on luku. Voit käyttää **X:ää** kaavoissa lukuna, ja kyseisen muuttujan arvo on *tyhjä* sen jälkeen, kun avaat sovelluksen, mutta ennen kuin valitset painikkeen. Kun valitset-painikkeen, annat **X:lle** arvon **1**.

Jos lisäsit toisen painikkeen ja määrität sen **onselect** -ominaisuudeksi **Set (X, "Hello")** , tapahtuu virhe, koska tyyppi (teksti merkki jono) ei vastaa edellisen **joukon** tyyppiä (luku). Kaikkien muuttujien implisiittisten määritysten on sovittava tyypistä. Kaikki tämä tapahtui, koska mainitsitte **x:n** kaavoissa, ei siksi, että mikään näistä kaavoista olisi todellisuudessa suoritettu.

Voit poistaa muuttujan poistamalla kaikki **joukko**-, **updatecontext**-, **Navigoi**-, **Collect**-ja **clearcollect** -Funktiot, jotka implisiittisesti luovat muuttujan. Ilman näitä funktioita muuttujaa ei ole. Sinun on poistettava myös kaikki viitta ukset muuttujaan, koska ne aiheuttavat virheen.

## <a name="variable-lifetime-and-initial-value"></a>Muuttujan käyttöikä ja alku arvo

Kaikki muuttujat säilytetään muistissa, kun sovellusta suoritetaan. Kun sovellus on sulkeutunut, arvot, joita muuttujat ovat hävinneet, katoavat.

Voit tallentaa muuttujan sisällön tieto lähteeseen käyttämällä **patch** -tai **Collect** -funktioita. Voit myös tallentaa arvoja kokoelmiin paikallisessa laitteessa käyttämällä [**SaveData**](functions/function-savedata-loaddata.md) -toimintoa.

Kun käyttäjä avaa sovelluksen, kaikkien muuttujien alku arvo on *tyhjä*.

## <a name="reading-variables"></a>Luetaan muuttujia

Muuttujan nimeä käytetään sen arvon lukemiseen. Voit esimerkiksi määrittää muuttujan, jolla on tämä kaava:

`Set( Radius; 12 )`

Sen jälkeen voit käyttää **RADIUS** -toimintoa missä tahansa, jolloin voit käyttää lukua, ja sen tilalle tulee **12**:

`Pi() * Power( Radius; 2 )`

Jos annat kontekstin muuttujalle saman nimen kuin yleinen muuttuja tai kokoelma, Context-muuttuja on etusijalla. Voit kuitenkin edelleen viitata yleiseen muuttujaan tai kokoelmaan, jos käytät Saksan- [operaattoria](functions/operators.md#disambiguation-operator) **@ [RADIUS]** .

## <a name="use-a-context-variable"></a>Käytä kontekstin muuttujaa

Katsotaan seuraavaksi, miten laskin luodaan käyttäen kontekstimuuttujaa yleisen muuttujan sijasta.

Näin kontekstimuuttujat toimivat:

* Voit implisiittisesti luoda ja määrittää kontekstin muuttujia käyttämällä **[updatecontext](functions/function-updatecontext.md)** -tai **[Navigate](functions/function-navigate.md)** -funktioita. Kun sovellus käynnistyy, kaikkien kontekstin muuttujien alku arvo on *tyhjä*.
* Päivität tietueita sisältäviä Context-muuttujia. Muissa ohjelmointityökaluissa voidaan yleisesti käyttää merkkiä ”=” vastaamaan varausta, kuten ”x = 1”. Käytä Context-muuttujia **{x: 1}** sen sijaan. Kun käytät Context-muuttujaa, käytä sen nimeä suoraan ilman tietueen syntaksia.
* Voit myös määrittää Context-muuttujan, kun käytät **[Navigoi](functions/function-navigate.md)** -toimintoa näytön näyttämiseen. Jos uskot, että näyttö on eräänlainen toiminto sarja tai alirutiini, tämä lähestymis tapa muistuttaa parametria, joka kulkee muissa ohjelmointi työkaluissa.
* Paitsi **[Siirry](functions/function-navigate.md)** -funktio, kontekstimuuttujat on rajoitettu yhden näytön kontekstiin, jossa ne saavat nimensä. Niitä ei voi käyttää tai määrittää tämän kontekstin ulkopuolella.
* Kontekstimuuttujat voivat sisältää mitä tahansa arvoja, mukaan lukien merkkijonoja, lukuja, tietueita ja [taulukkoja](working-with-tables.md).

Rakennetaan laskuri uudelleen käyttämällä kontekstimuuttujaa:

1. Lisää tekstisyötteen ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)** -ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    **UpdateContext ({RunningTotal: RunningTotal + TextInput1})**

    Tämän kaavan pelkkä olemassaolo muodostaa **Runningtotal** -kohteen kontekstin muuttujaksi, joka sisältää luvun **+-** operaattorin vuoksi. Voit viitata **Runningtotal** -kohteeseen missä tahansa tässä näytössä. Kun käyttäjä avaa tämän sovelluksen, **Runningtotal** -kohteella on alku arvo, joka on *tyhjä*.

    Kun käyttäjä valitsee ensimmäisen kerran **Lisää** -painikkeen ja **[updatecontext](functions/function-updatecontext.md)** -ajojen, **runningtotal** -arvoksi määritetään arvo **runningtotal + TextInput1**.

    ![Lisää-painikkeen OnSelect-ominaisuus](media/working-with-variables/context-variable-1.png)

4. Jotta juokseva summa määritetään **nollaksi** aina, kun käyttäjä valitsee **Tyhjennä**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    **UpdateContext ({RunningTotal: 0})**

    **[Updatecontext](functions/function-updatecontext.md)** -kohteen kanssa käytetään uudelleen kaavaa **updatecontext ({RunningTotal: 0})** .

    ![Clear-painikkeen OnSelect-ominaisuus](media/working-with-variables/context-variable-2.png)

5. Lisää **[Nimi](controls/control-text-box.md)** -ohjausobjekti ja määritä sen **[Teksti](controls/properties-core.md)** -ominaisuudeksi **RunningTotal**.

    Tämä kaava lasketaan automaattisesti uudelleen, ja se näyttää käyttäjälle **RunningTotal**-arvon sen muuttuessa sen mukaan, mitä painikkeita käyttäjä valitsee.

    ![Otsikon teksti-ominaisuus](media/working-with-variables/context-variable-3.png)

6. Esikatsele sovellusta, ja edellä kuvaamamme laskuri on valmis. Kirjoita numero tekstiruutuun ja paina **Lisää**-painiketta muutaman kerran. Kun olet valmis, palaa muokkausominaisuuteen Esc-näppäimellä.

    ![Teksti syöte-ohjaus objekti esittää arvon, ja otsikossa näytetään juokseva summa](media/working-with-variables/context-variable-4.png)

7. Voit määrittää kontekstimuuttujan arvon siirtyessäsi näyttöön. Tästä on hyötyä välitettäessä kontekstia tai parametreja näytöstä toiseen. Jos haluat näyttää tämän tekniikan, lisää näyttö, Lisää painike ja määritä sen **onselect** -ominaisuudeksi Tämä kaava:

    **Navigate( Screen1; None; { RunningTotal: -1000 } )**

    ![Painikkeen OnSelect-ominaisuus](media/working-with-variables/context-variable-5.png)

    Pidä Alt-näppäintä painettuna samalla, kun valitset tämän painikkeen sekä Näytä **Screen1** -että Aseta Context muuttuja **runningtotal** -arvoksi-1000.

    ![Screen1 on avoinna](media/working-with-variables/context-variable-6.png)

8. Jos haluat näyttää Context-muuttujan arvon, valitse **tiedosto-** valikko ja valitse sitten **muuttujat** vasemmanpuoleisesta ruudusta.

    ![Tiedosto-valikon muuttujat-vaihto ehto](media/working-with-variables/context-variable-file-1.png)

9. Jos haluat nähdä, missä kontekstin muuttuja on määritetty ja käytetty, valitse se.

    ![Luettelo, jossa muuttujaa käytetään](media/working-with-variables/context-variable-file-2.png)

## <a name="use-a-collection"></a>Käytä kokoelmaa

Tutustutaan lopuksi laskimen lisäämiseen kokoelman avulla.  Koska kokoelma sisältää taulukon, jota on helppo muokata, teemme tästä laskimesta sellaisen, että se säilyttää ”paperinauhan” kustakin annetusta arvosta.

Näin kokoelmat toimivat:

* Luo ja määritä kokoelmia **[ClearCollect](functions/function-clear-collect-clearcollect.md)** -funktiolla.  Voit vaihtoehtoisesti käyttää **[Collect](functions/function-clear-collect-clearcollect.md)** -funktiota, mutta periaatteessa se edellyttää toista muuttujaa vanhan muuttujan korvaamisen sijasta.  
* Kokoelma on eräänlainen tietolähde ja näin ollen taulukko. Voit käyttää kokoelman yhtä arvoa **[First](functions/function-first-last.md)** -funktion avulla ja poimia yhden kentän tuloksena saatavasta tietueesta. Jos käytit yksittäistä arvoa **[ClearCollect](functions/function-clear-collect-clearcollect.md)** -funktion kanssa, tämä on **Arvo**-kenttä, kuten tässä esimerkissä:<br>
**First(** *VariableName* **).Value**

Luodaan seuraavaksi laskin uudelleen kokoelman avulla:

1. Lisää **[tekstisyötteen](controls/control-text-input.md)** ohjausobjekti nimeltä **TextInput1** ja kaksi painiketta nimeltä **Button1** ja **Button2**.

2. Määritä **Button1**-painikkeen **[Teksti](controls/properties-core.md)** -ominaisuudeksi **Lisää** ja **Button2**-painikkeen **Teksti**-ominaisuudeksi **Tyhjennä**.

3. Jotta juokseva summa päivittyy aina, kun käyttäjä valitsee **Lisää**-painikkeen, määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    **Collect( PaperTape; TextInput1.Text )**

    Pelkkä tämän kaavan olemassaolo muodostaa **Papertape** -kokoelman, joka sisältää yksisarakkeisen teksti merkki jono taulukon. Voit viitata **Papertape** -kohteeseen missä tahansa tässä sovelluksessa. Kun käyttäjä avaa tämän sovelluksen, **Papertape** on tyhjä taulukko.

    Kun tämä kaava suoritetaan, se lisää uuden arvon kokoelman loppuun. Koska lisäämme yhden arvon, **keräys** sijoittaa sen automaattisesti yksisarakkeisen taulukon kohdalle ja sarakkeen nimi on **arvo**, jota käytät myöhemmin.

    ![Lisää-painikkeen OnSelect-ominaisuus](media/working-with-variables/papertape-1.png)

4. Jos haluat tyhjentää paperi nauhan, kun käyttäjä valitsee **Tyhjennä** -painikkeen, määritä sen **[onselect](controls/properties-core.md)** -ominaisuudeksi Tämä kaava:

    **Clear( PaperTape )**

    ![Clear-painikkeen OnSelect-ominaisuus](media/working-with-variables/papertape-2.png)

5. Näytä juokseva summa lisäämällä nimi, ja määritä sen **[Teksti](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    **Sum( PaperTape; Value )**

    ![Selitteen teksti-ominaisuus](media/working-with-variables/papertape-3.png)

6. Suorita laskin painamalla F5-näppäintä, mikä avaa esikatselun, lisää lukuja tekstisyötteen ohjausobjektiin ja valitse painikkeet.

    ![Teksti syöte-ohjaus objekti näyttää arvon, ja nimi näyttää juoksevan summan](media/working-with-variables/papertape-run-1.png)

7. Palaa oletustyötilaan painamalla Esc-näppäintä.

8. Näytä paperinauha lisäämällä **Arvotaulukko**-ohjausobjekti ja määritä sen **[Kohteet](controls/properties-core.md)** -ominaisuudeksi tämä kaava:

    **PaperTape**

    Valitse oikeanpuoleisessa ruudussa näytettävä **arvo** -sarake.

    ![Tieto taulukko, joka sisältää kokoelmaan lisätyt arvot](media/working-with-variables/papertape-4.png)

9. Näytä kokoelman arvot valitsemalla **Tiedosto**-valikosta **Kokoelmat**.

    ![PaperTape-kokoelman esikatselu](media/working-with-variables/papertape-file.png)

10. Tallenna ja nouda kokoelmasi lisäämällä kaksi muuta painike-ohjaus objektia ja määrittämällä niiden **teksti** ominaisuudet **lataamaan** ja **tallentamaan**. Määritä **Lataa** -painikkeen **onselect** -ominaisuudeksi Tämä kaava:

     **Clear( PaperTape );; LoadData( PaperTape; "StoredPaperTape"; true )**

     Sinun on tyhjennettävä kokoelma ensin, koska **Loaddata** liittää tallennetut arvot kokoelman loppuun.

     ![Lataus painikkeen OnSelect-ominaisuus](media/working-with-variables/papertape-5.png)

11. Määritä **Tallenna** -painikkeen **onselect** -ominaisuudeksi Tämä kaava:

     **SaveData( PaperTape; "StoredPaperTape" )**

     ![Tallenna-painikkeen OnSelect *-ominaisuus](media/working-with-variables/papertape-6.png)

12. Esikatsele uudelleen painamalla F5-näppäintä, kirjoita luvut tekstisyötteen ohjausobjektiin ja valitse painikkeet. Valitse **Tallenna**-painike. Sulje sovellus ja lataa se uudelleen ja lataa kokoelmasi uudelleen valitsemalla **Lataa** -painike.

> [!NOTE]
> **SaveData** -ja **loaddata** -Funktiot powerapps Mobilessa, mutta ei PowerApps Studio tai powerappsin verkko soittimessa.