---
title: Aloita kaavojen käyttäminen | Microsoft Docs
description: Kaavojen avulla voit mukauttaa sovellusta.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: e4c2f78fb00e726bd0b0bf3cde4fe4f42d40dddc
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="get-started-with-formulas"></a>Aloita kaavojen käyttäminen
Määritä sovellukseesi kaavoja, jotka eivät ainoastaan laske arvoja ja suorita muita tehtäviä (samalla tavoin kuin Excelissä), vaan myös vastaavat käyttäjän syötteeseen (kuten sovellus edellyttää).

* Excelissä voit luoda kaavoja, jotka esimerkiksi täyttävät soluja ja luovat taulukoita ja kaavioita.
* PowerAppsissa luot samankaltaisia kaavoja, kun määrität ohjausobjekteja solujen sijaan. Lisäksi voit luoda kaavoja, jotka koskevat erityisesti sovelluksia laskentataulukoiden sijaan.

Voit esimerkiksi luoda kaavan, joka määrittää, miten sovelluksesi reagoi, kun käyttäjät valitsevat painikkeen, säätävät liukusäädintä tai antavat muita syötteitä. Nämä kaavat saattavat tuoda näkyviin eri näytön, päivittää sovelluksen ulkopuolisen tietolähteen tai luoda taulukon, joka sisältää aiemmin luodun taulukon tietojen alijoukon.

Voit käyttää kaavoja moniin erilaisiin skenaarioihin. Voit esimerkiksi käyttää laitteen GPS:ää, kartan ohjausobjektia ja kaavaa, joka käyttää signaaleja **Location.Latitude** ja **Location.Longitude** nykyisen sijaintisi näyttämiseen. Kun siirryt, kartta seuraa sijaintiasi automaattisesti.

Tässä aiheessa annetaan vain yleiskatsaus kaavojen käsittelemiseen. Saat tarkempia tietoja ja täydellisen luettelon funktioista, operaattoreista ja muista rakenneosista siirtymällä kohtaan [kaavan viittaus](formula-reference.md).

## <a name="prerequisites"></a>Edellytykset

* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md) PowerAppsissa.

## <a name="show-a-simple-value"></a>Näytä yksinkertainen arvo
Excelissä voit syöttää tietoja, kuten luvun **42** tai lauseen **Hei maailma**, kirjoittamalla ne soluun. Tieto näkyy solussa aina täsmälleen samalla tavalla kuin kirjoitit sen. PowerAppsissa voit vastaavasti määrittää muuttumattoman tiedon määrittämällä selitteelle ominaisuuden **[Teksti](controls/properties-core.md)**, jolloin haluamaasi tarkkaa merkkijonoa ympäröivät lainausmerkit.

1. Valitse **Tiedosto**-valikosta (läheltä näytön vasenta reunaa) **Uusi**.
2. Valitse **Tyhjä sovellus** -ruudun **Luo sovellus** -kohdassa **puhelinasettelu**.
   
    Kaavarivi sijaitsee näytön yläreunassa.
   
    ![Kaavarivi](./media/working-with-formulas/formula-bar.png)
   
    Tällä rivillä on kaksi osaa:
   
   * *Ominaisuusluettelo*: jokaiseen ohjausobjektiin ja näyttöön liittyy [ominaisuusjoukko](reference-properties.md).  Valitse tietty ominaisuus tämän luettelon avulla.  
   * *Kaava*: tälle ominaisuudelle laskettava kaava, joka muodostuu [arvoista, operaattoreista ja funktioista](formula-reference.md).
     
     Kaavarivillä voit tarkastella ja muokata valitun ohjausobjektin ominaisuuksia tai näytön ominaisuuksia, jos ohjausobjektia ei ole valittu.  Voit nähdä valitun ohjausobjektin nimen **Sisältö**-välilehdessä:
     
     ![Sisältöpalkissa näkyy tällä hetkellä valittu ohjausobjekti](./media/working-with-formulas/content-tab-selection.png)
     
     Voit muuttaa valitun ohjausobjektin nimeä **Sisältö**-välilehdessä napsauttamalla nimeä.
3. Lisää näyttöön **[Label](controls/control-text-box.md)**-ohjausobjekti.
   
    ![TextBox-ohjausobjekti lisätty](./media/working-with-formulas/add-a-label.png)
   
    Kun haluat lisätä selitteen, ominaisuusluettelo näyttää automaattisesti **[Teksti](controls/properties-core.md)**-ominaisuuden, joka määrää, mitä ohjausobjekti näyttää. Tämän ominaisuuden arvo on oletusarvoisesti **Teksti**.  
4. Määritä **[Teksti](controls/properties-core.md)**-ominaisuuden arvoksi **”Hei maailma”** kirjoittamalla tämä merkkijono kaavariville lainausmerkkeihin:
   
    ![Käytä selitettä ”Hei maailma”](./media/working-with-formulas/label-hello-world.png)
   
    Tämä selitteen uusi arvo päivittyy heti sitä kirjoitettaessa.  Näytössä saattaa näkyä keltaisia huutomerkkikuvakkeita kirjoitettaessa. Nämä kuvakkeet ovat merkkejä virheistä, mutta ne poistuvat, kun olet kirjoittanut kelvollisen arvon. Esimerkiksi merkkijono ilman lainausmerkkejä molemmissa päissä ei ole kelvollinen.
   
    Excelissä voit näyttää luvun, kuten **42**, kirjoittamalla sen soluun tai kirjoittamalla kaavan, jonka tuloksena on tämä luku, kuten **=SUM(30,12)**. PowerAppsissa saat aikaan saman vaikutuksen määrittämällä ohjausobjektille, kuten selitteelle, **42**:lle tai **Sum(30,12)**:lle ominaisuuden **Teksti**. Solu ja selite näyttävät aina tämän numeron riippumatta siitä, mikä laskentataulukossa tai sovelluksessa muuttuu.
   
    > [!NOTE]
> PowerAppsissa ei aseteta kaavan eteen yhtäläisyysmerkkiä tai plus-merkkiä, kuten Excelissä. Kaavarivi käsittelee kaikkea siihen kirjoitettua oletusarvoisesti kaavana. Kaavaa ei myöskään ympäröidä lainausmerkeillä (”) kuten aikaisemmin määrittäessäsi merkkijonoa.
5. Korvaa selitteen **[Teksti](controls/properties-core.md)**-ominaisuuden sisältö **”Hei maailma”** kirjoittamalla sen tilalle **Sum(1,2,3)**.
   
    ![Osittaisen funktion Sum(1,2,3 kirjoittaminen ilman oikeaa suljetta tuo esiin virheitä](./media/working-with-formulas/label-sum-partial.png)
   
    Kun kirjoitat, kaavarivi auttaa näyttämällä kyseisen funktion kuvauksen ja odotetut argumentit.  Samoin kuin jälkimmäisen lainausmerkin osalta kirjoittaessasi tekstiä **”Hei maailma”**, näytössä näkyy keltaisia huutomerkkejä virheen merkkinä, kunnes kirjoitat tämän kaavan loppusulkeen:
   
    ![Täydellisen kaavan Sum(1,2,3) käyttäminen](./media/working-with-formulas/label-sum.png)

## <a name="change-a-value-based-on-input"></a>Muuta arvoa syötteen perusteella
Excelissä voit kirjoittaa soluun **=SUM(a1:a2)**, jolloin tuloksena näkyy summa solujen A1 ja A2 arvoista. Jos jompikumpi tai molemmat näistä arvoista muuttuu, kaavan sisältävä solu näyttää automaattisesti päivitetyn tuloksen.

![Kuva kahden luvun yhteenlaskun laskemisesta uudelleen Excelissä](./media/working-with-formulas/excel-recalc.png)

PowerAppsissa voit saavuttaa samanlaisen tuloksen lisäämällä ohjausobjekteja ja määrittämällä niiden ominaisuudet. Tässä esimerkissä näytetään edellisen toimintosarjan selite ja kaksi **[Teksti](controls/control-text-input.md)**-syötteen ohjausobjektia, joiden nimet ovat **TextInput1** ja **TextInput2**.

![Kuva kahden luvun yhteenlaskun laskemisesta uudelleen PowerAppsissa](./media/working-with-formulas/recalc1.png)

Riippumatta siitä, mitä numeroita kirjoitat tekstin syötön ohjausobjekteihin, selite näyttää aina näiden lukujen summan, koska sen **[Teksti](controls/properties-core.md)**-ominaisuuden arvoksi on asetettu tämä kaava:
<br>**TextInput1 + TextInput2**

![Kuva kahden luvun yhteenlaskun laskemisesta uudelleen PowerAppsissa](./media/working-with-formulas/recalc2.png)

Excelissä voit käyttää ehdollista muotoilua näyttämään esimerkiksi negatiiviset arvot punaisella. PowerAppsissa käytetään kaavaa, joka sisältää **[Jos](functions/function-if.md)**-funktion, joka toimii vastaavalla tavalla kuin Excelissä.

1. Määritä selitteen **[Väri](controls/properties-color-border.md)**-ominaisuudeksi seuraava kaava:<br>**If( Value(TekstiRuutu1.Text) < 0, Red, Black )**
   
    > [!NOTE]
> Määritä kaavassa ohjausobjektin ominaisuus syöttämällä ohjausobjektin nimi niin, että sen perässä on piste, jota seuraa ominaisuuden nimi. Määritä esimerkiksi **TextBox1**:n **[Teksti](controls/properties-core.md)**-ominaisuus kirjoittamalla **TextBox1.Text**.
   
    ![Kuva siitä, miten PowerAppsin uudelleenlaskenta muuttaa selitteen väriä sen arvon perusteella](./media/working-with-formulas/recalc-color1.png)
2. Määritä muuttujille **TextInput1** ja **TextInput2** kaksi lukua, joiden yhteenlaskettu summa on negatiivinen.
   
    ![Kuva siitä, miten PowerAppsin uudelleenlaskenta muuttaa selitteen väriä sen arvon perusteella](./media/working-with-formulas/recalc-color2.png)
   
    Selitteen arvo näkyy punaisena.

## <a name="change-a-color-based-on-user-input"></a>Värin muuttaminen käyttäjän syötteen perusteella
Voit määrittää sovelluksesi kaavojen avulla siten, että käyttäjät voivat muuttaa sovelluksesi ulkoasua tai toimintaa. Voit esimerkiksi luoda suodattimen näyttämään vain tiedot, jotka sisältävät käyttäjän määrittämän tekstimerkkijonon, tai voit antaa käyttäjien lajitella tiedot tietojoukon tietyn sarakkeen perusteella. Tässä toimintosarjassa annat käyttäjien muuttaa näytön väriä säätämällä yhtä tai useampaa liukusäädintä.

1. Poista ohjausobjektit edellisistä toimintosarjoista tai luo tyhjä sovellus samalla tavalla kuin aiemmin ja lisää siihen kolme liukusäädin-ohjausobjektia:
   
    ![Liukusäädin-ohjausobjektin lisääminen](./media/working-with-formulas/insert-slider.png)
2. Järjestä liukusäätimet niin, että ne eivät ole päällekkäin, lisää kolme selitettä ja määritä ne näyttämään **punainen**, **vihreä** ja **sininen**:
   
    ![Järjestä liukusäätimet ja lisää selitteet jokaiselle värikomponentille](./media/working-with-formulas/three-sliders.png)
3. Määritä jokaisen liukusäätimen **Max**-ominaisuudeksi 255, joka vastaa **[RGBA](functions/function-colors.md)**-funktion kunkin värikomponentin enimmäisarvoa.
   
    Voit määrittää **Max**-ominaisuuden valitsemalla sen **Sisältö**-välilehdessä tai ominaisuusluettelossa:
   
    ![Muuta jokaisen liukusäätimen enimmäisarvoa](./media/working-with-formulas/three-sliders-max.png)
4. Valitse näyttö napsauttamalla ohjausobjektin ulkopuolella olevaa kohtaa ja määritä sitten näytön **[Täyttö](controls/properties-color-border.md)**-ominaisuuden arvoksi tämä kaava:<br>**RGBA( Slider1.Value, Slider2.Value, Slider3.Value, 1 )**
   
    Kuten yllä kuvailtiin, voit muokata ohjausobjektin ominaisuuksia käyttämällä **.** -operaattoria.  **Slider1.Value** viittaa liukusäätimen **[Arvo](controls/properties-core.md)**-ominaisuuteen, joka vastaa sitä kohtaa, johon käyttäjä on asettanut liukusäätimen **Min**- ja **Max**-arvojen välillä. Kun kirjoitat tätä kaavaa, jokainen siihen sisältyvä ohjausobjekti värikoodataan näytön ja kaavarivin välillä:
   
    ![Muuta kaavaa näytön taustan täyttöväriä varten. Ei vielä valmis](./media/working-with-formulas/three-sliders-partial-rgba.png)
   
    Kun kirjoitat oikean sulkeen, näytön tausta muuttuu tummanharmaaksi, mikä vastaa kunkin liukusäätimen oletusarvoa, joka on **50**. Sillä hetkellä, kun lopetat kaavan kirjoittamisen, se lasketaan ja sitä käytetään taustan täyttövärin arvona. Voit olla vuorovaikutuksessa sovelluksesi kanssa oletustyötilassa eikä sinun tarvitse avata esikatselua:
   
    ![Muuta jokaisen liukusäätimen enimmäisarvoa](./media/working-with-formulas/three-sliders-complete-rgba.png)
5. Säädä liukusäätimiä ja katso, miten muutoksesi vaikuttavat taustaväriin.
   
    Kun kunkin liukusäätimen asento muuttuu, **[RGBA](functions/function-colors.md)**-funktion sisältävä kaava lasketaan uudelleen, mikä muuttaa heti näytön ulkonäköä.
   
    ![Muuta kaavaa näytön taustan täyttöväriä varten. Nyt valmis](./media/working-with-formulas/three-sliders-example-colors.png)

## <a name="manage-app-behavior"></a>Hallitse sovelluksen toimintaa
Voit käyttää kaavoja laskutoimitusten suorittamisen ja ulkoasun muuttamisen lisäksi myös toimenpiteiden suorittamiseen. Voit esimerkiksi määrittää painikkeen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi kaavan, joka sisältää **[Siirry](functions/function-navigate.md)**-funktion. Kun käyttäjä valitsee tämän painikkeen, näkyviin tulee näyttö, jonka olet määrittänyt kaavassa.

Voit käyttää joitakin funktioita, kuten **[Siirry](functions/function-navigate.md)** ja **[Kerää](functions/function-clear-collect-clearcollect.md)** vain toimintakaavoissa.  Kaavan viittaus antaa ilmoituksen, jos voit käyttää funktiota vain tässä yhteydessä.  

Voit suorittaa useamman kuin yhden toiminnan toimintakaavassa, jos erotat funktiot toisistaan puolipisteellä (;). Haluat ehkä päivittää kontekstimuuttujan, työntää tietoja tietolähteeseen ja lopuksi siirtyä toiseen näyttöön.

## <a name="view-a-list-of-properties-by-category"></a>Näytä ominaisuuksien luettelo luokittain
Ominaisuudet-luettelossa ominaisuudet näkyvät aakkosjärjestyksessä, mutta voit myös tarkastella kaikkia ohjausobjektin ominaisuuksia luokittain järjestettynä, jos valitset **Lisäasetukset**-vaihtoehdon **Näkymä**-välilehdessä:

![Näytä lisätiedot](./media/working-with-formulas/advanced-open.png)

Voit muokata kaavoja suoraan tässä näkymässä.  Ruudun yläreunassa sijaitsevan ohjausobjektin valitsimen avulla voit etsiä nopeasti ohjausobjektin, jota haluat käyttää.  Ominaisuushaun avulla voit lisäksi selvittää nopeasti tämän ohjausobjektin ominaisuuden.

Aluksi tässä näkymässä näkyvät tärkeimmät ominaisuudet.  Tuo näkyviin kaikki ominaisuudet napsauttamalla alanuolta ruudun alareunassa.  Jokaisella ohjausobjektilla on pitkä luettelo ominaisuuksista, jotka ohjaavat kaikkia ohjausobjektin toimintaan ja ulkoasuun liittyviä seikkoja. Voit selata luetteloa tai hakea ominaisuutta kirjoittamalla ruudun yläreunassa olevaan kenttään.

## <a name="formula-syntax"></a>Kaavan syntaksi
Kun kirjoitat kaavan kaavarivillä, eri syntaksielementit näkyvät erivärisinä, mikä parantaa luettavuutta ja auttaa ymmärtämään pitkiä kaavoja. Tässä on luettelo värikoodeista PowerAppsissa.

![syntaksikorostus](./media/working-with-formulas/syntax-highlighting.png)

