---
title: Pohjaan perustuvien sovellusten tietolomakkeen asettelun ymmärtäminen | Microsoft Docs
description: Luo PowerAppsissa upeita lomakeasetteluja pohjaan perustuvissa sovelluksissa käyttämällä rivejä ja sarakkeita.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/17/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b6bff4d0f9586f94e4d0da133197fcb7f78c765d
ms.sourcegitcommit: 826bde1eab3dd32d7bf9fa3f43ea069694845597
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2019
ms.locfileid: "57800257"
---
# <a name="understand-data-form-layout-for-canvas-apps-in-powerapps"></a>Pohjaan perustuvien sovellusten tietolomakkeen asettelun ymmärtäminen PowerAppsissa

Voida luoda helposti näyttävän ja tehokkaan lomakkeen, kun luot pohjaan perustuvan sovelluksen PowerAppsissa. Harkitse esimerkiksi tätä peruslomaketta myyntitilausten tallennusta varten:

![Myyntitilausmalli](./media/working-with-form-layout/sales-order.png)

Tässä opetusohjelmassa käymme läpi vaiheet tämän lomakkeen luomiseen. Tarkastelemme myös joitakin edistyneempiä aiheita, kuten kenttien dynaamista koonmuutamista käytettävissä olevan tilan täyttämiseksi.

## <a name="before-you-start"></a>Ennen aloittamista

Jos olet uusi PowerApps-käyttäjä (tai olet luonut sovelluksia vain automaattisesti), kannattaa [luoda sovellus alusta](get-started-create-from-blank.md), ennen kuin ryhdyt toimimaan tämän ohjeaiheen mukaan. Luomalla sovelluksen alusta opit välttämättömiä käsitteitä, joita mainitaan tässä ohjeaiheessa, mutta ei selitetä, kuten tietolähteiden ja ohjausobjektien lisääminen.

Tämä ohjeaihe on kirjoitettu aivan kuin sinulla tietoja tietolähteen, jonka nimi on **myyntitilaus** , joka sisältää kenttien edellisessä kuvassa. Jos sinulla on Powerappsin palvelupaketin 2 käyttöoikeus tai [kokeiluversion käyttöoikeus](../signup-for-powerapps.md) järjestelmänvalvojaan tai järjestelmän mukauttajat oikeudet, voit [entiteetin](../common-data-service/data-platform-create-entity.md) luomiseen Common Data Service (CDS) for Appsissa ja lisää samanlaiset kentät. 

## <a name="add-a-gallery"></a>Lisää valikoima

1. Luo tablettisovellus alusta ja lisätä tietolähteen.

    Kaikki tässä aiheessa kuvatut asiat koskevat myös puhelinasetteluja, paitsi että puhelinsovelluksissa on usein vain yksi pystysuuntainen sarake.
    
2. Lisää vaakasuuntainen **Valikoima**-ohjausobjekti ja aseta sen **Kohteet**-ominaisuudeksi **Myyntitilaus**.
   
    (valinnainen) Jotta esimerkit vastaavat tätä opetusohjelmaa, muuta valikoiman **asettelua** siten, että se näyttää vain **otsikon ja alaotsikon**.
   
    ![Myyntitilausluettelo](./media/working-with-form-layout/gallery-layout.png)
3. Napsauta tai napauta valikoimassa **SO004**.
   
    ![Myyntitilausluettelo](./media/working-with-form-layout/sales-order-gallery-screen.png)
   
    Tämä tietue näkyy lomakkeessa, jonka luot tämän ohjeartikkelin myöhempien vaiheiden ohjeiden mukaan.

## <a name="add-a-title-bar"></a>Lisää otsikkorivi
1. Lisää tyhjä näyttö, johon lisäät lomakkeen.
   
    Tämän opetusohjelman ulkopuolella voit sijoittaa **Valikoima**- ja **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektit samaan näyttöön, mutta saat enemmän työskentelytilaa, jos sijoitat ne eri näyttöihin.
2. Lisää uuden näytön yläosaan **[Nimi](controls/control-text-box.md)**-ohjausobjekti ja määritä sen **Teksti**-ominaisuudeksi seuraava lauseke:
   <br>**"Sales Order " & Gallery1.Selected.SalesOrderId**
   
    Nimi näyttää valikoimasta valitsemasi tietueen myyntitilausnumeron.
3. (valinnainen) Muotoile nimi seuraavasti:
   
   1. Määritä sen **Tasaa**-ominaisuudeksi **Keskellä**.
   
   2. Määritä sen **Koko**-ominaisuudeksi **20**.
   
   3. Määritä sen **Täyttö**-ominaisuudeksi **Laivastonsininen**.
   
   4. Määritä sen **Väri**-ominaisuudeksi **Valkoinen**.
   
   5. Määritä sen **Leveys**-ominaisuudeksi **Parent.Width**.
   
   6. Määritä sen **X**- ja **Y**-ominaisuuksiksi **0**.
      
      ![Otsikkorivi](./media/working-with-form-layout/title-bar.png)

## <a name="add-a-form"></a>Lomakkeen lisääminen
1. Lisää **Muokkaa lomaketta** -ohjausobjekti, siirrä sitä ja muuta sen kokoa niin, että se täyttää näytön nimen alla.
   
    Yhdistä seuraavassa vaiheessa lomakkeen ohjausobjekti **Myyntitilaus**-tietolähteeseen oikeanpuoleisen ruudun, ei kaavarivin, avulla. Jos käytät kaavariviä, lomake ei oletusarvoisesti näytä kaikkia kenttiä. Voit aina näyttää kaikki haluamasi kentät valitsemalla yhden tai useita valintaruutuja oikeanpuoleisessa ruudussa.
2. Napsauta tai napauta oikeanpuoleisessa ruudussa olevaa alanuolta kohdan **Tietolähdettä ei ole valittu** vieressä, ja napsauta tai napauta **Myyntitilaus**.
   
    **Myyntitilaus**-tietolähteen oletusarvoinen kenttäjoukko näkyy yksinkertaisessa kolmen sarakkeen asettelussa. Monet ovat kuitenkin tyhjiä, ja niiden asettumiseen lopullisiin paikkoihinsa saattaa kulua muutama hetki.  
3. Määritä lomakkeen **Kohde**-ominaisuudeksi **Gallery1.Selected**.
   
    Lomake näyttää tietueen, jotka valitsit valikoimassa, mutta oletuskenttäjoukko ei ehkä vastaa suunnitelmaasi lopullisesta tuotteesta.
4. Piilota oikeanpuoleisessa ruudussa jokainen näistä kentistä tyhjentämällä valinta sen valintaruudusta:
   
   * **Myyntitilauksen tunnus**
   * **Tili**
   * **Myyjä**
   * **Tilin yhteyshenkilö**
5. Siirrä **Tilauksen tila** -kenttää vetämällä sitä vasemmalle ja pudottamalla sen **Asiakkaan ostotilauksen viite** -kentän toiselle puolelle.
   
    Näytön pitäisi näyttää samalta kuin tässä esimerkissä:
   
    ![Myyntitilaus kolmen sarakkeen perusasettelussa](./media/working-with-form-layout/sales-order-form-screen-3.png)

## <a name="select-a-data-card"></a>Tietokortin valitseminen
Jokaisella näytetyllä kentällä on vastaava tietokortti lomakkeessa. Tämä kortti koostuu ohjausobjektijoukosta kentän otsikolle, tekstiruudulle, tähdelle (joka tulee näkyviin, jos kenttä on pakollinen) ja vahvistuksen virhesanomalle.

Voit myös valita kortteja suoraan lomakkeessa. Kun kortti on valittuna, musta kuvateksti tulee näkyviin sen yläpuolelle.

![Tietokortin valinta](./media/working-with-form-layout/sales-order-data-card-selection.png)

> [!NOTE]
> Jos haluat poistaa kortin (ei pelkästään piilottaa sen), valitse se ja paina sitten Poista.

## <a name="arrange-cards-in-columns"></a>Järjestä kortit sarakkeisiin
Lomakkeissa tablettisovelluksissa on oletusarvoisesti kolme saraketta ja puhelinsovelluksissa yksi. Voit määrittää lomakkeen sarakkeiden lukumäärän lisäksi myös sen, pitääkö kaikkien korttien mahtua sarakkeen reunojen sisäpuolelle.

Tässä kuvassa lomakkeen sarakkeiden lukumäärä muutettiin kolmesta neljään ja **Kohdista sarakkeisiin** -valintaruutu valittiin. Lomakkeen kortit järjestettiin automaattisesti uuteen asetteluun sopivaksi.

![Myyntitilaus neljän sarakkeen perusasettelussa](./media/working-with-form-layout/sales-order-form-screen-4.png)

## <a name="resize-cards-across-multiple-columns"></a>Muuta korttien kokoa usean sarakkeen alueelta
Sen mukaan, mitä tietoja kussakin kortissa on, haluat ehkä joidenkin korttien sopivan yhteen sarakkeeseen ja toisten korttien ulottuvan usean sarakkeen yli. Jos kortti sisältää enemmän tietoja kuin haluat näyttää yhdessä sarakkeessa, voit leventää korttia valitsemalla sen ja vetämällä sitä sen valintakehyksen oikean tai vasemman reunan kahvasta. Kun vedät kahvaa, kortti ”kohdistetaan” sarakkeen rajoihin.

Voit tehdä mallistasi joustavamman säilyttäen rakenteen suurentamalla sarakkeiden lukumäärän 12:een. Tällä muutoksella voit helposti määrittää kunkin kortin koon joko esimerkiksi koko lomakkeen, puolikkaan lomakkeen, 1/3-lomakkeen, 1/4-lomakkeen tai 1/6-lomakkeen kokoiseksi. Tutustutaan tähän käytännössä.

1. Määritä oikeanpuoleisessa ruudussa lomakkeen sarakkeiden määräksi **12**.
   
    ![Määritä sarakkeiden lukumäärä](./media/working-with-form-layout/12-columns.png)
   
    Lomake ei muutu näkyvästi, mutta käytössäsi on enemmän kohdistuskohtia, kun vedät oikean- tai vasemmanpuoleista kahvaa.
2. Suurenna **Tilauspäivä**-kortin leveyttä vetämällä oikeanpuoleista kahvaa yhden kohdistuskohdan verran oikealle.
   
    Kortti kattaa neljä lomakkeen 12 sarakkeesta (tai kolmasosan lomakkeesta) kolmen sarakkeen (tai neljäsosalomakkeesta) sijasta. Aina, kun levennät korttia yhden kohdistuskohdan verran, kortti laajenee 1/12-lomakkeen verran.
   
    ![Muuta kortin kokoa vetämällä ja pudottamalla](./media/working-with-form-layout/card-resize-1.png)
3. Toista edelliset vaiheet **Tilauksen tila**- ja **Asiakkaan ostotilauksen viite** -korttien osalta.
   
    ![Kolme korttia ensimmäisellä rivillä](./media/working-with-form-layout/card-resize-2.png)

4. Muuta **Nimi**- ja **Kuvaus**-korttien kokoa siten, että ne vievät kuusi lomakkeen saraketta (tai puolet lomakkeesta).

5. Laajenna toimitusosoitteen kaksi riviä kattamaan koko lomake:

Valmis! Olemme luoneet lomakkeet, jossa on rivejä, joilla on eri määrä sarakkeita:

![Myyntitilaus 12 sarakkeen asettelussa ja muutettu koko](./media/working-with-form-layout/card-resize-done.png)

## <a name="manipulate-controls-in-a-card"></a>Käsittele kortin ohjausobjekteja
Toimitusosoite sisältää useita tietoja, jotka haluamme ryhmitellä visuaalisesti yhteen käyttäjälle. Kukin kenttä säilyy omassa tietokortissaan, mutta voimme käsitellä kortin ohjausobjekteja, jotta ne sopivat paremmin yhteen.

1. Valitse **Jakeluosoitteen ensimmäinen rivi** -kortti, valitse nimi kortissa ja poista tekstin kolme ensimmäistä sanaa.
   
    ![Myyntitilauksen jakeluosoitteen ensimmäisen riviotsikon nimeäminen uudelleen](./media/working-with-form-layout/delivery-address-rename.png)
2. Valitse **Jakeluosoitteen toinen rivi** -kortti, valitse nimi kortissa ja poista kaikki sen teksti.
   
    Koko nimi-ohjausobjektin poistaminen saattaa tuntua houkuttelevalta, ja monissa tapauksissa se toimiikin. Mutta kaavat saattavat olla riippuvaisia tämän ohjausobjektin olemassaolosta. Turvallisempi tapa on poistaa teksti tai määrittää ohjausobjektin **Näkyvissä**-ominaisuuden arvoksi **false**.
   
    ![Myyntitilauksen jakeluosoitteen toisen rivin otsikon nimeäminen uudelleen](./media/working-with-form-layout/delivery-address-rename-2.png)
3. Siirrä samassa kortissa muokkausruutu nimen päälle pienentämään tilaa ensimmäisen ja toisen osoiterivin välissä.
   
    Kortin korkeus pienenee, kun sen sisältö vie vähemmän tilaa.
   
    ![Myyntitilauksen jakeluosoitteen toisen rivin nimen nimeäminen uudelleen](./media/working-with-form-layout/delivery-address-move-input.png)

Tarkastellaan seuraavaksi osoitteen kolmatta riviä. Samoin kuin juuri teimme, lyhennämme näiden korttien kunkin nimen tekstiä ja järjestämme muokkausruudun kunkin nimen oikealle puolelle. Seuraavassa ovat **Osavaltio**-kortin vaiheet:

| Vaihe | Kuvaus | Tulos |
| --- | --- | --- |
| 1 |Valitse **Osavaltio**-kortti niin, että kahvat tulevat näkyviin sen ympärille. |![Valitse kortti](./media/working-with-form-layout/state-morph-2.png) |
| 2 |Valitse kortin nimi niin, että kahvat tulevat näkyviin sen ympärille. |![Valitse ohjausobjekti kortissa](./media/working-with-form-layout/state-morph-3.png) |
| 3 |Aseta kohdistin tekstin oikealle puolelle ja poista sitten tarpeeton osa. |![Muuta tekstiä kortin ohjausobjektissa](./media/working-with-form-layout/state-morph-3b.png) |
| 4 |Muuta reunojen kahvojen avulla nimi-ohjausobjektia niin, että se sopii uuden tekstin kokoon. |![Muuta ohjausobjektin kokoa kortissa](./media/working-with-form-layout/state-morph-4b.png) |
| 5 |Valitse tekstisyötteen ohjausobjekti tässä kortissa. |![Valitse jokin toinen ohjausobjekti kortissa](./media/working-with-form-layout/state-morph-6.png) |
| 6 |Muuta tekstinsyötteen ohjausobjektin kokoa haluamaasi kokoon reunojen kahvojen avulla. |![Muuta ohjausobjektin kokoa kortissa](./media/working-with-form-layout/state-morph-6b.png) |
| 7 |Vedä tekstisyötteen ruutua ylöspäin ja nimi-ohjausobjektin oikealle puolelle ja pudota sitten tekstisyötteen ruutu. |![Siirrä ohjausobjektia kortissa](./media/working-with-form-layout/state-morph-7b.png) |
| Muutokset **Osavaltio**-korttiin on nyt tehty. |![Muutokset korttiin on tehty](./media/working-with-form-layout/state-morph-8.png) | |

Valmiin kolmannen osoiterivin tulos:

![Myyntitilauksen jakeluosoite ja tiiviimpi kolmas rivi](./media/working-with-form-layout/delivery-address-resize-city-1.png)

Huomaa, että monien korttien ominaisuudet ovat alussa dynaamisia kaavoja. Esimerkiksi tekstisyötteen ohjausobjektilla, jonka kokoa muutimme ja jota siirsimme edellä, oli **Leveys**-ominaisuus sen ylätason leveyden perusteella. Kun siirrät ohjausobjektia tai muutat sen kokoa, nämä dynaamisen kaavat korvataan staattisilla arvoilla. Jos haluat, voit palauttaa dynaamiset kaavat kaavarivin avulla.

## <a name="turning-off-snap-to-columns"></a>Sarakkeisiin kohdistamisen poistaminen käytöstä
Joskus saatat kaivata tarkempaa hallintaa kuin 12 vakiosaraketta voi tarjota. Näissä tapauksissa voit poistaa käytöstä **Kohdista sarakkeisiin** -valinnan ja sijoittaa kortit manuaalisesti. Lomake kohdistetaan yhä 12 sarakkeeseen, mutta voit myös asettaa kortin ja muuttaa sen kokoa manuaalisesti pitämällä Alt-näppäintä painettuna.

Tässä esimerkissä neljä osaa, jotka muodostavat osoitteen kolmannen rivin, ovat kaikki täsmälleen yhtä leveitä. Tämä ei välttämättä kuitenkaan ole paras asettelu, sillä kaupunkien nimet ovat pitempiä kuin osavaltioiden lyhenteet, ja maiden/alueiden tekstisyötteen ruutu on lyhyt sen nimen pituuden vuoksi.

Voit optimoida tämän tilan poistamalla **Kohdista sarakkeisiin** -valinnan käytöstä oikeanpuoleisessa ruudussa ja pitämällä sitten Alt-näppäintä painettuna, kun muutat näiden korttien kokoa ja sijoitat niitä. Aina, kun pidät Alt-näppäintä painettuna, kaikissa ohjausobjekteissa näkyy musta teksti. Tämä on tarkoituksellista, sillä se näyttää ohjausobjektien nimet.

![Sijoittelu ja koon muutos Alt-näppäin painettuina](./media/working-with-form-layout/delivery-address-alt-resize.png)

Huolellisen sijoittamisen jälkeen saadaan sopiva koko kullekin kentälle ja tasainen vaakasuuntainen välistys kenttien välillä:

![Myyntitilauksen toimitusosoitteen kolmas rivi tarkalleen sijoitettuna](./media/working-with-form-layout/delivery-address-resize-city-2.png)

Mitä voimme siis päätellä **Kohdista sarakkeisiin** -valinnan käytöstä verrattuna sen poistamiseen käytöstä?

| Toiminta | Kohdista sarakkeisiin käytössä | Kohdista sarakkeisiin pois käytöstä |
| --- | --- | --- |
| Kohdista ja muuta kokoa |Valittujen sarakkeiden määrä:<br>1, 2, 3, 4, 6 tai 12 |12 saraketta |
| Kohdistaminen ja koon muuttaminen voidaan ohittaa |Ei |Kyllä, Alt-näppäimellä |
| Kortit asetellaan automaattisesti rivien väliin (lisätietoja jäljempänä) |Kyllä |Ei |

## <a name="set-width-and-height"></a>Määritä leveys ja korkeus
Kuten kaikkialla PowerAppsissa, lomakkeen asettelua säätelevät kortin ohjausobjektien ominaisuudet. Kuten jo kerroimme, voit muuttaa näiden ominaisuuksien arvoja vetämällä ohjausobjekteja eri paikkoihin tai muuttamalla ohjausobjektien kokoa vetämällä kahvoista. Huomaat kuitenkin tilanteita, joissa haluat ymmärtää ja käsitellä näitä ominaisuuksia tarkemmin, erityisesti silloin, kun teet lomakkeista dynaamisia kaavojen avulla.

### <a name="basic-layout-x-y-and-width"></a>Perusasettelu: X, Y ja leveys
Ominaisuudet **X** ja **Y** määräävät korttien sijainnin. Kun käytämme ohjausobjekteja tyhjällä pohjalla, nämä ominaisuudet tarjoavat absoluuttisen sijainnin. Lomakkeessa näillä ominaisuuksilla on eri merkitys:

* **X**: Tilauksen rivin.
* **Y**: Rivin numero.

Kuten mallipohjan ohjausobjektit, **Leveys**-ominaisuus määrittää kortin vähimmäisleveyden (lisätietoja vähimmäissuhteesta hieman myöhemmin).

Tutustutaan korttien ominaisuuksiin **X**, **Y** ja **Leveys** lomakkeessa:

![Myyntitilauksen lomakkeen X- ja Y-koordinaatit](./media/working-with-form-layout/sales-order-xy.png)

### <a name="overflowing-rows"></a>Ylivuoto riveillä
Mitä tapahtuu, jos kortit rivillä ovat liian leveitä kyseiselle riville? Yleensä tästä ei tarvitse huolehtia. **Kohdista sarakkeisiin** -valinnalla nämä ominaisuudet säädetään automaattisesti niin, että kaikki mahtuvat siististi riveille.

Mutta jos **Kohdista sarakkeisiin** tai kaavapohjainen **Leveys** on poistettu käytöstä yhdessä tai useammassa kortissa, rivit saattavat ylitäyttyä. Tässä tapauksessa kortit rivitetään automaattisesti niin, että käytännössä luodaan toinen rivi. Muutetaan esimerkkinä **Asiakkaan ostotilauksen viite** -kortin **Leveys**-ominaisuus manuaalisesti (ensimmäinen rivi, kolmas kohde) arvoon **500**:

![Manuaalinen kortin koon muutos ja juoksutus uudelle riville](./media/working-with-form-layout/manual-size-500.png)

Ylimmän rivin kolme korttia eivät enää mahdu vaakasuunnassa, ja toinen rivi on luotu ylivuodon rivittämiseksi. Kaikkien korttien **Y**-koordinaatti on yhä sama 0, ja **Nimi**- ja **Kuvaus**-korttien **Y** on edelleen 1. Kortteja, joissa on eri **Y**-arvot, ei yhdistetä riveittäin.

Voit käyttää tätä toimintoa täysin dynaamisen asettelun luomiseen. Siinä kortit sijoitetaan Z-järjestyksen perusteella niin, että ne täyttävät tilaa niin paljon kuin mahdollista ennen seuraavalle riville siirtymistä. Tämä saadaan aikaan, kun kaikille korteille annetaan sama **Y**-arvo ja **X**-arvoa käytetään korttien järjestykseen.

### <a name="filling-spaces-widthfit"></a>Välien täyttäminen: WidthFit
Viimeisen esimerkin ylivuoto loi tilaa **Tilauksen tila** -kortin jälkeen, joka oli toinen kortti ensimmäisellä rivillä. Voisimme manuaalisesti säätää kahden muun kortin **Leveys**-ominaisuutta tilan täyttämiseksi, mutta se olisi vaivalloista.

Vaihtoehtona käytämme **WidthFit**-ominaisuutta. Jos tämä ominaisuus on **true** yhdelle tai useammalle rivin kortille, jäljellä oleva tila rivillä jaetaan tasaisesti niiden välillä. Tästä syystä mainitsimme aiemmin, että kortin **Leveys**-ominaisuus on *vähimmäisarvo*, ja mitä todellisuudessa näemme, voi olla leveämpi. Tämä ominaisuus ei koskaan aiheuta kortin pienenemistä, vain suurenemista.

Jos määritämme **WidthFit**-ominaisuudeksi **true** **Tilauksen tila** -kortissa, se täyttää käytettävissä olevan tilan ensimmäisen kortin pysyessä muuttumattomana:

![WidthFit-arvo true toisessa kortissa](./media/working-with-form-layout/manual-widthfit-1.png)

Jos myös määritämme **WidthFit**-ominaisuudeksi **true** **Tilauspäivä**-kortissa, molemmat kortit jakavat tasaisesti käytettävissä olevan tilan:

![WidthFit-arvo true ensimmäisessä ja toisessa kortissa](./media/working-with-form-layout/manual-widthfit-2.png)

Huomaa, että näiden korttien kahvat ottavat huomioon **WidthFit**-ominaisuuden tarjoaman ylimääräisen leveyden, ei **Leveys**-ominaisuuden tarjoamaa vähimmäisleveyttä. **Leveys**-ominaisuuden käsittely voi olla sekavaa **WidthFit**-ominaisuuden ollessa käytössä. Voit halutessasi poistaa sen käytöstä, tehdä muutoksia **Leveys**-ominaisuuteen ja ottaa sen sitten takaisin käyttöön.

Milloin **WidthFit**-ominaisuudesta voi olla hyötyä? Jos sinulla on kenttä, jota käytetään vain tietyissä tilanteissa, voit määrittää sen **Näkyvissä**-ominaisuudeksi **false**, jolloin mut rivin kortit täyttävät automaattisesti tilan sen ympärillä. Haluat ehkä käyttää kaavaa, joka näyttää kentän vain, kun toisella kentällä on tietty arvo.

Tässä kohdassa määritämme **Tilauksen tila** -kentän **Näkyvissä**-ominaisuudeksi staattisen **false**:

![WidthFit-arvo true ensimmäisessä kortissa ja tila näkymätön](./media/working-with-form-layout/manual-widthfit-3.png)

Nyt kun toinen kortti on käytännössä poistettu, kolmas kortti voi nyt palata samalle riville kuin ensimmäinen kortti. Ensimmäisen kortin **WidthFit**-asetus on yhä **true**, joten vain se suurenee ja täyttää käytettävissä olevan tilan.

Koska **Tilauksen tila** on näkymätön, et pysty valitsemaan sitä helposti mallipohjalta. Voit kuitenkin valita minkä tahansa ohjausobjektin, näkyvän tai ei, ohjausobjektien hierarkkisessa luettelossa näytön vasemmassa reunassa.

### <a name="height"></a>Korkeus
**Korkeus**-ominaisuus hallitsee jokaisen kortin korkeutta. Korteissa on **WidthFit**-ominaisuutta vastaava ominaisuus **korkeudelle**, ja se on aina **true**. Kuvittele, että **HeightFit**-ominaisuus on olemassa, mutta älä etsi sitä tuotteesta, koska tämä ominaisuus ei ole vielä näkyvissä.

Et voi poistaa käytöstä tätä toimintoa, ja näin ollen korttien korkeuden muuttaminen voi olla haastavaa. Kaikki rivin kortit näyttävät samankorkuisilta kuin korkein kortti. Saatat nähdä seuraavanlaisen rivin:

![WidthFit-arvo true ensimmäisessä kortissa ja tila näkymätön](./media/working-with-form-layout/height-3.png)

Mikä kortti tekee rivistä korkean? Edellisessä kuvassa **Kokonaissumma**-kortti on valittuna ja näyttää korkealta, mutta sen **Korkeus**-ominaisuus on **80** (sama kuin ensimmäisen rivin korkeus). Jotta voit pienentää rivin korkeutta, sinun on pienennettävä rivin korkeimman kortin **korkeutta**, etkä pysty tunnistamaan korkeinta korttia tarkistamatta kunkin kortin **Korkeus**-ominaisuutta.

### <a name="autoheight"></a>AutoHeight
Kortti voi myös olla suurempi kuin oletat, jos se sisältää ohjausobjektin, jonka **AutoHeight**-ominaisuus on **true**. Useat kortit esimerkiksi sisältävät nimen, joka näyttää virhesanoman, jos kentän arvo aiheuttaa vahvistusongelman.

Ilman näytettävää tekstiä (virhettä) nimi pienenee nollakorkeuteen. Jos et tietäisi, et arvaisi sen olevan siinä, ja näin sen kuuluukin olla:

![Kortit, jotka sisältävät ohjausobjekteja ja joiden AutoHeight-arvo on true, eivät näytä korkeutta](./media/working-with-form-layout/autoheight-0.png)

Näytön vasemmassa reunassa oleva ohjausobjektien luettelo näyttää **ErrorMessage1**:n, joka on nimi-ohjausobjekti. Kun päivität sovelluksen, voit valita tämän ohjausobjektin. Se lisää korkeutta ja näyttää kahvat, joilla voit sijoittaa ohjausobjektin ja muuttaa sen kokoa. ”A” sinisessä ruudussa tarkoittaa, että ohjausobjektin **AutoHeight**-asetus on **true**:

![Laatimisen aikana AutoHeight-ohjausobjektit näyttivät jonkin verran korkeutta, mikä helpottaa vetämistä ja pudottamista](./media/working-with-form-layout/autoheight-1.png)

Tämän ohjausobjektin **Teksti**-ominaisuuden arvo on **Parent.Error**. Sitä käytetään dynaamisten virhetietojen hankkimiseen vahvistussääntöjen perusteella. Asetetaan staattisesti tämän ohjausobjektin **Teksti**-ominaisuus esimerkkitarkoituksessa. Tämä kasvattaa sen korkeutta (ja laajennettuna kortin korkeutta), jotta se mukautuu tekstin pituuteen:

![Virhesanoma, jonka myötä ohjausobjekti ja kortti kasvavat automaattisesti](./media/working-with-form-layout/autoheight-2.png)

Tehdään virhesanomasta hieman pitempi, niin ohjausobjekti ja kortti kasvavat taas sopivasti. Huomaa, että rivin korkeus suurenee kaikkialta säilyttäen pystytasauksen korttien välillä:

![Pidemmällä virhesanomalla ohjausobjekti ja kortti kasvavat vielä enemmän. Huomaa myös, että saman rivin kaikki kortit kasvavat yhdessä.](./media/working-with-form-layout/autoheight-3.png)

