---
title: Funktiot, signaalit ja luetteloinnit | Microsoft Docs
description: Viitetietoja funktioista, signaaleista ja luetteloinneista PowerAppsissa.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/05/2018
ms.author: gregli
ms.openlocfilehash: b131f9da9dbf0624185fc837c5582c9ef0477089
ms.sourcegitcommit: 6d9fe9967841e381b108a7fb53c9057e295336ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948592"
---
# <a name="formula-reference-for-powerapps"></a>Kaavaviittaus PowerAppsia varten
Kaavoissa yhdistetään useita elementtejä.  Alla on lueteltu:

* **Funktiot** käyttävät parametreja, suorittavat toiminnon ja palauttavat arvon. Esimerkiksi **Sqrt(25)** palauttaa arvon **5**. Funktiot on mallinnettu Microsoft Excelin funktioiden mukaan.  Joillakin funktioilla on sivuvaikutuksia, kuten **SubmitForm**eilla, jotka sopivat vain **Button.OnSelect**in kaltaiseen [toimintakaavaan](working-with-formulas-in-depth.md).
* **Signaalit** palauttavat tietoja ympäristöstä. Esimerkiksi **[Location](functions/signals.md)** palauttaa laitteen nykyiset GPS-koordinaatit. Signaalit eivät käytä parametreja, eikä niillä ole sivuvaikutuksia.
* **Luetteloinnit** palauttavat valmiiksi määritetyn vakioarvon. Esimerkiksi **[Color](functions/function-colors.md)** on luettelointi, jolla on ennalta määritetyt arvot **Color.Red**, **Color.Blue** ja niin edelleen.  Yleiset luetteloinnit ovat mukana tässä. Funktiokohtaiset luetteloinnit on kuvattu funktion yhteydessä.
* **Nimettyjen operaattorien**, kuten **[ThisItem](functions/operators.md#thisitem-operator)** ja **[Parent](functions/operators.md#parent-operator)**, avulla päästään käsiksi tietoihin säiliön sisältä.

Muita elementtejä ovat:

* [Kaikki operaattorit](functions/operators.md)
* [Ohjausobjektit ja niiden ominaisuudet](reference-properties.md)

## <a name="a"></a>A
**[Abs](functions/function-numericals.md)** – luvun itseisarvo.  

**[Acceleration](functions/signals.md)** – lukee laitteen kiihtyvyysanturia.

**[Acos](functions/function-trig.md)** – palauttaa luvun arkuskosinin radiaaneina.

**[Acot](functions/function-trig.md)** – palauttaa luvun arkuskotangentin radiaaneina.

**[AddColumns](functions/function-table-shaping.md)** – palauttaa taulukon, johon on lisätty [sarakkeita](working-with-tables.md#columns).

**[And](functions/function-logicals.md)** – totuusarvoehdon AND-operaattori.  Palauttaa arvon **tosi**, jos kaikkien argumenttien arvo on **tosi**.  Voit käyttää myös [**&&**-operaattoria](functions/operators.md).

**[App](functions/signals.md)** – palauttaa tietoja käynnissä olevasta sovelluksesta, kuten sen, mikä näyttö on näkyvissä.

**[Asin](functions/function-trig.md)** – palauttaa luvun arkussinin radiaaneina.

**[Atan](functions/function-trig.md)** – palauttaa luvun arkustangentin radiaaneina.

**[Atan2](functions/function-trig.md)** – palauttaa (*x*,*y*)-koordinaattiin perustuvan arkustangentin radiaaneina.

**[Average](functions/function-aggregates.md)** – laskee taulukon lausekkeen tai argumenttijoukon keskiarvon.

## <a name="b"></a>B
**[Back](functions/function-navigate.md)** – näyttää edellisen näytön.  

**[Blank](functions/function-isblank-isempty.md)** – palauttaa *tyhjän* arvon, jonka avulla voidaan lisätä NULL-arvo tietolähteeseen.

## <a name="c"></a>C
**[Calendar](functions/function-clock-calendar.md)** – hakee nykyistä aluetta koskevia tietoja kalenterista.

**[Char](functions/function-char.md)** – muuntaa merkkikoodin merkkijonoksi.

**[Choices](functions/function-choices.md)** – Palauttaa hakusarakkeen mahdollisten arvojen taulukon.

**[Clear](functions/function-clear-collect-clearcollect.md)** – poistaa kaikki tiedot [kokoelmasta](working-with-data-sources.md#collections).

**[ClearCollect](functions/function-clear-collect-clearcollect.md)** – poistaa kaikki tiedot kokoelmasta ja lisää sitten joukon [tietueita](working-with-tables.md#records).

**[Clock](functions/function-clock-calendar.md)** – noutaa nykyistä aluetta koskevat kellon tiedot.

**[Coalesce](functions/function-isblank-isempty.md)** – korvaa *tyhjät* arvot jättäen muut kuin *tyhjät* arvot muuttumattomiksi.

**[Collect](functions/function-clear-collect-clearcollect.md)** – luo kokoelman tai lisää tietoja tietolähteeseen.

**[Color](functions/function-colors.md)** – asettaa väriarvon sisältämän ominaisuuden.

**[ColorFade](functions/function-colors.md)** – häivyttää väriarvon.

**[ColorValue](functions/function-colors.md)** – kääntää CSS-värinimen tai heksadesimaalikoodin väriarvoksi.  

**[Compass](functions/signals.md)** – palauttaa kompassisuuntasi.

**[Concat](functions/function-concatenate.md)** – yhdistää merkkijonot tietolähteessä.  

**[Concatenate](functions/function-concatenate.md)** – yhdistää merkkijonot.

**[Concurrent](functions/function-concurrent.md)** – Arvioi useita kaavoja keskenään samanaikaisesti. 

**[Connection](functions/signals.md)** – palauttaa tietoja verkkoyhteydestäsi.

**[Count](functions/function-table-counts.md)** – laskee taulukon tietueet, jotka sisältävät lukuja.

**[Cos](functions/function-trig.md)** – palauttaa radiaaneina määritetyn kulman kosinin.

**[Cot](functions/function-trig.md)** – palauttaa radiaaneina määritetyn kulman kotangentin.

**[CountA](functions/function-table-counts.md)** – laskee taulukon tietueet, jotka eivät ole [tyhjiä](functions/function-isblank-isempty.md).

**[CountIf](functions/function-table-counts.md)** – laskee taulukon tietueet, jotka täyttävät ehdon.  

**[CountRows](functions/function-table-counts.md)** – laskee taulukon tietueet.   

## <a name="d"></a>D
**[DataSourceInfo](functions/function-datasourceinfo.md)** – antaa tietoja tietolähteestä.

**[Date](functions/function-date-time.md)** – palauttaa päivämäärän ja ajan arvon **vuoden**, **kuukauden** ja **päivän** arvojen perusteella.  

**[DateAdd](functions/function-dateadd-datediff.md)** – lisää päiviä, kuukausia, neljännesvuosia tai vuosia päivämäärä- ja aika-arvoon.

**[DateDiff](functions/function-dateadd-datediff.md)** – vähentää kaksi päivämääräarvoa ja näyttää tuloksen päivinä, kuukausina, vuosineljänneksinä tai vuosina.

**[DateTimeValue](functions/function-datevalue-timevalue.md)** – muuntaa päivämäärä- ja kellonaikamerkkijonon päivämäärä- ja aika-arvoksi.

**[DateValue](functions/function-datevalue-timevalue.md)** – muuntaa vain päivämäärän sisältävän merkkijonon päivämäärä- ja aika-arvoksi.

**[Day](functions/function-datetime-parts.md)** – hakee päivämäärä- ja aika-arvon päiväosan.  

**[Defaults](functions/function-defaults.md)** – palauttaa tietolähteelle oletusarvot.

**[Degrees](functions/function-trig.md)** – muuntaa radiaanit asteiksi.

**[Disable](functions/function-enable-disable.md)** – poistaa käytöstä signaalin, kuten GPS:n lukemisen **[Location](functions/signals.md)**.

**[Distinct](functions/function-distinct.md)** – tekee taulukon tietueista yhteenvedon ja poistaa kaksoiskappaleet.  

**[Download](functions/function-param.md)** – lataa tiedoston Internetistä paikalliseen laitteeseen.

**[DropColumns](functions/function-table-shaping.md)** – palauttaa taulukon, josta poistetaan vähintään yksi sarake.

## <a name="e"></a>E
**[EditForm](functions/function-form.md)** – nollaa lomakkeen ohjausobjektin kohteen muokkaamista varten.

**[Enable](functions/function-enable-disable.md)** – ottaa käyttöön signaalin, kuten GPS:n lukemisen **[Location](functions/signals.md)**.

**[EndsWith](functions/function-startswith.md)** – tarkistaa, päättyykö tekstimerkkijono toiseen merkkijonoon.

**[Errors](functions/function-errors.md)** – antaa tietolähteen edellisiin muutoksiin liittyvät virhetiedot.

**[EncodeUrl](functions/function-encode-decode.md)** – koodaa erikoismerkit käyttäen URL-koodausta.

**[Exit](functions/function-exit.md)** – sulkee käynnissä olevan sovelluksen.

**[Exp](functions/function-numericals.md)** – palauttaa *e*:n korotettuna potenssiin.

## <a name="f"></a>F
**[Filter](functions/function-filter-lookup.md)** – palauttaa suodatetun taulukon vähintään yhden ehdon perusteella.

**[Find](functions/function-find.md)** – tarkistaa, esiintyykö yksi merkkijono toisessa merkkijonossa, ja palauttaa sijainnin.

**[First](functions/function-first-last.md)** – palauttaa taulukon ensimmäisen tietueen.

**[FirstN](functions/function-first-last.md)** – palauttaa taulukon ensimmäisen tietuejoukon (N tietuetta).

**[ForAll](functions/function-forall.md)** – laskee arvot ja suorittaa toiminnot taulukon kaikille tietueille.

## <a name="g"></a>G
**[GroupBy](functions/function-groupby.md)** – palauttaa taulukon, jossa tietueet on ryhmitelty yhteen.

## <a name="h"></a>H
**[HashTags](functions/function-hashtags.md)** – poimii aihetunnisteet (#merkkijonot) merkkijonosta.

**[Hour](functions/function-datetime-parts.md)** – palauttaa tunnin osan päivämäärä- ja aika-arvosta.

## <a name="i"></a>I
**[If](functions/function-if.md)** – palauttaa yhden arvon, jos ehto on tosi, ja toisen arvon, jos ei ole. 

**[IfError](functions/function-iferror.md)**  – havaitsee virheitä ja tarjoaa vaihtoehtoisen arvon tai suorittaa toimen. 

**[IsBlank](functions/function-isblank-isempty.md)** – tarkistaa, onko arvo [tyhjä](functions/function-isblank-isempty.md).

**[IsEmpty](functions/function-isblank-isempty.md)** – tarkistaa, onko taulukko tyhjä.

**[IsMatch](functions/function-ismatch.md)** – tarkistaa merkkijonon kuviota vastaan.  Säännönmukaisia lausekkeita voidaan käyttää.

**[IsNumeric](functions/function-isnumeric.md)** – tarkistaa, onko arvo numeerinen.

**[IsToday](functions/function-now-today-istoday.md)** – tarkistaa, onko päivämäärä- ja aika-arvo jossain vaiheessa tämän päivän aikana.

## <a name="l"></a>L
**[Language](functions/function-language.md)** – palauttaa nykyisen käyttäjän kielitunnisteen.

**[Last](functions/function-first-last.md)** – palauttaa taulukon ensimmäisen tietueen.

**[LastN](functions/function-first-last.md)** – palauttaa taulukon viimeisen tietuejoukon (N tietuetta).

**[Launch](functions/function-param.md)** – avaa Internet-osoitteen tai sovelluksen.

**[Left](functions/function-left-mid-right.md)** – palauttaa merkkijonossa äärimmäisenä vasemmalla olevan osan.

**[Len](functions/function-len.md)** – palauttaa merkkijonon pituuden.

**[Ln](functions/function-numericals.md)** – palauttaa luonnollisen logaritmin.

**[LoadData](functions/function-savedata-loaddata.md)** – lataa kokoelman PowerAppsin yksityisestä tallennustilasta.

**[Location](functions/signals.md)** – palauttaa sijaintisi karttakoordinaatteina käyttämällä GPS-järjestelmää ja muita tietoja.

**[LookUp](functions/function-filter-lookup.md)** – etsii taulukosta yksittäisen tietueen yhden tai useamman ehdon perusteella.

**[Lower](functions/function-lower-upper-proper.md)** – muuntaa tekstimerkkijonon kirjaimet pieniksi kirjaimiksi.

## <a name="m"></a>M
**[Max](functions/function-aggregates.md)** – taulukon lausekkeen tai argumenttijoukon suurin arvo.

**[Mid](functions/function-left-mid-right.md)** – palauttaa merkkijonon keskiosan.

**[Min](functions/function-aggregates.md)** – taulukon lausekkeen tai argumenttijoukon pienin arvo.

**[Minute](functions/function-datetime-parts.md)** – noutaa päivämäärä- ja aika-arvon minuuttiosuuden.  

**[Mod](functions/function-mod.md)** – palauttaa jakojäännöksen, kun jaettava jaetaan jakajalla.

**[Month](functions/function-datetime-parts.md)** – noutaa päivämäärä- ja aika-arvon kuukausiosuuden.

## <a name="n"></a>N
**[Navigate](functions/function-navigate.md)** – vaihtaa näytettävän näytön.

**[NewForm](functions/function-form.md)** – nollaa lomakkeen ohjausobjektin kohteen luomista varten.

**[Not](functions/function-logicals.md)** – totuusarvoehdon NOT-operaattori.  Palauttaa arvon **tosi**, jos sen argumentti on **epätosi**, ja palauttaa arvon **epätosi**, jos sen argumentti on **tosi**.  Voit myös käyttää [**!**-operaattoria](functions/operators.md).

**[Ilmoita](functions/function-showerror.md)** – Näyttää ilmoitussanoman käyttäjälle.

**[Now](functions/function-now-today-istoday.md)** – Palauttaa nykyisen päivämäärä- ja aika-arvon.

## <a name="o"></a>O
**[Or](functions/function-logicals.md)** – totuusarvoehdon OR-operaattori.  Palauttaa arvon **tosi**, jos jonkin sen argumentin arvo on **tosi**.  Voit myös käyttää [**||**-operaattoria](functions/operators.md).

## <a name="p"></a>P
**[Param](functions/function-param.md)** – tarjoaa pääsyn sovellukseen välitettyihin parametreihin, kun käyttäjä on avannut sen.

**[Parent](functions/operators.md#parent-operator)** – tarjoaa pääsyn säilöohjausobjektin ominaisuuksiin.

**[Patch](functions/function-patch.md)** – muokkaa tietolähteessä olevaa tietuetta, luo tietueen tietolähteeseen tai yhdistää tietueet tietolähteen ulkopuolella.

**[Pi](functions/function-trig.md)** – palauttaa luvun &pi;.

**[PlainText](functions/function-encode-decode.md)** – poistaa HTML- ja XML-tunnisteet merkkijonosta.

**[Power](functions/function-numericals.md)** – palauttaa luvun korotettuna haluttuun potenssiin.  Voit myös käyttää [**^**-operaattoria](functions/operators.md).

**[Proper](functions/function-lower-upper-proper.md)** – muuntaa merkkijonon kunkin sanan ensimmäisen kirjaimen isoksi kirjaimeksi ja loput pieniksi kirjaimiksi.

## <a name="r"></a>R
**[Radians](functions/function-trig.md)** – muuntaa asteet radiaaneiksi.

**[Rand](functions/function-rand.md)** – palauttaa näennäissatunnaisluvun.

**[Refresh](functions/function-refresh.md)** – päivittää tietolähteen tietueita.

**[Remove](functions/function-remove-removeif.md)** – poistaa yhden tai useita määrättyjä tietueita tietolähteestä.

**[RemoveIf](functions/function-remove-removeif.md)** – poistaa tietueita ehdon perusteella tietolähteestä.

**[RenameColumns](functions/function-table-shaping.md)** – nimeää taulukon sarakkeet uudelleen.

**[Replace](functions/function-replace-substitute.md)** – korvaa osan merkkijonosta toisella merkkijonolla aloittaen merkkijonon asemasta.

**[Reset](functions/function-reset.md)** – nollaa syötön ohjausobjektin oletusarvoonsa hyläten kaikki käyttäjän tekemät muutokset.

**[ResetForm](functions/function-form.md)** – nollaa lomakkeen ohjausobjektin nykyisen kohteen muokkaamista varten.

**[Revert](functions/function-revert.md)** – lataa uudelleen ja poistaa virheet tietolähteen tietueista.

**[RGBA](functions/function-colors.md)** – palauttaa väriarvon punaisen, vihreän ja sinisen komponentin sekä alfa-komponentin joukon perusteella.

**[Right](functions/function-left-mid-right.md)** – palauttaa merkkijonossa äärimmäisenä oikealla olevan osan.

**[Round](functions/function-round.md)** – pyöristää lähimpään lukuun.

**[RoundDown](functions/function-round.md)** – pyöristää alaspäin edelliseen suurimpaan lukuun.

**[RoundUp](functions/function-round.md)** – pyöristää ylöspäin pienimpään seuraavaan numeroon.

## <a name="s"></a>S
**[SaveData](functions/function-savedata-loaddata.md)** – tallentaa kokoelman PowerAppsin yksityiseen tallennustilaan.

**[Search](functions/function-filter-lookup.md)** – etsii taulukosta tietueet, jotka sisältävät merkkijonon yhdessä niiden sarakkeista.  

**[Second](functions/function-datetime-parts.md)** – noutaa päivämäärä- ja aika-arvon sekuntiosuuden.

**[Select](functions/function-select.md)** – Simuloi valintatoiminnon käyttämistä ohjausobjektiin, aiheuttaen **OnSelect**-kaavan laskennan.

**[Set](functions/function-set.md)** – asettaa yleisen muuttujan arvon.

**[ShowColumns](functions/function-table-shaping.md)** – palauttaa taulukon, jossa on vain valitut sarakkeet.

**[Shuffle](functions/function-shuffle.md)** – järjestää taulukon tietueet uudelleen satunnaisesti.

**[Sin](functions/function-trig.md)** – palauttaa radiaaneina määritetyn kulman sinin.

**[Sort](functions/function-sort.md)** – palauttaa kaavan perusteella lajitellun taulukon.

**[SortByColumns](functions/function-sort.md)** – palauttaa yhden tai useamman sarakkeen perusteella lajitellun taulukon.

**[Split](functions/function-split.md)** – jakaa merkkijonon alimerkkijonojen taulukoksi.

**[Sqrt](functions/function-numericals.md)** – palauttaa luvun neliöjuuren.

**[StartsWith](functions/function-startswith.md)** – tarkistaa, alkaako tekstimerkkijono toisella tekstimerkkijonolla.

**[StdevP](functions/function-aggregates.md)** – palauttaa argumenttiensa keskihajonnan.  

**[Substitute](functions/function-replace-substitute.md)** – korvaa merkkijonon osan toisella merkkijonolla vertaamalla merkkijonoja.

**[SubmitForm](functions/function-form.md)** – tallentaa lomakkeen ohjausobjektin kohteen tietolähteeseen.

**[Sum](functions/function-aggregates.md)** – laskee taulukon lausekkeen tai argumenttijoukon summan.  

**[Switch](functions/function-if.md)** – vertaa arvojoukkoa ja arvioi sitten vastaavan kaavan.

## <a name="t"></a>T
**[Table](functions/function-table.md)** – luo väliaikaisen taulukon.  

**[Tan](functions/function-trig.md)** – palauttaa radiaaneina määritetyn kulman tangentin.

**[Text](functions/function-text.md)** – muotoilee luvun merkkijonoksi näyttämistä varten.

**[ThisItem](functions/operators.md#thisitem-operator)** – jos ollaan valikoimassa tai lomakkeessa, palauttaa nykyisen kohteen tiedot säilöstä.

**[Time](functions/function-date-time.md)** – palauttaa päivämäärä- ja aika-arvon perusteella **tunti**-, **minuutti**- ja **sekunti**arvot.  

**[TimeValue](functions/function-datevalue-timevalue.md)** – muuntaa vain ajan sisältävän merkkijonon päivämäärä- ja aika-arvoksi.

**[TimeZoneOffset](functions/function-dateadd-datediff.md)** – palauttaa eron UTC-ajan ja käyttäjän paikallisen ajan välillä minuutteina.

**[Today](functions/function-now-today-istoday.md)** – palauttaa nykyisen päivä- ja aika-arvon.

**[Trim](functions/function-trim.md)** – poistaa ylimääräiset välilyönnit tekstimerkkijonon päistä ja sisältä.

**[TrimEnds](functions/function-trim.md)** – poistaa ylimääräiset välilyönnit vain tekstimerkkijonon päistä.

## <a name="u"></a>U
**[Ungroup](functions/function-groupby.md)** – poistaa ryhmittelyn.

**[Update](functions/function-update-updateif.md)** – korvaa tietolähteen tietueen.

**[UpdateContext](functions/function-updatecontext.md)** – määrittää nykyisen näytön yhden tai useamman [kontekstimuuttujan](working-with-variables.md#create-a-context-variable) arvon.

**[UpdateIf](functions/function-update-updateif.md)** – muokkaa tietolähteen tietuejoukon ehdon perusteella.

**[Upper](functions/function-lower-upper-proper.md)** – muuntaa tekstimerkkijonon kirjaimet isoiksi kirjaimiksi.

**[User](functions/function-user.md)** – palauttaa tietoja nykyisestä käyttäjästä.

## <a name="v"></a>V
**[Validate](functions/function-validate.md)** – tarkistaa, onko yksittäisen sarakkeen tai täydellisen tietueen arvo kelvollinen tietolähteelle.

**[Value](functions/function-value.md)** – muuntaa merkkijonon luvuksi.

**[VarP](functions/function-aggregates.md)** – palauttaa argumenttien varianssin.  

**[ViewForm](functions/function-form.md)** – nollaa lomakkeen ohjausobjektin nykyisen kohteen muokkaamista varten.

## <a name="w"></a>W
**[Weekday](functions/function-datetime-parts.md)** – noutaa päivämäärä- ja aika-arvon viikonpäiväosan.

## <a name="y"></a>Y
**[Year](functions/function-datetime-parts.md)** – noutaa päivämäärä- ja aika-arvon vuosiosan.  

