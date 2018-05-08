---
title: Kognitiivisten palvelujen käyttö PowerAppsissa | Microsoft Docs
description: Luo perussovellus, joka analysoi tekstiä käyttämällä Microsoftin kognitiivisten palvelujen tekstianalysoinnin ohjelmointirajapintaa (API).
services: ''
suite: powerapps
documentationcenter: na
author: mgblythe
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/08/2017
ms.author: mblythe
ms.openlocfilehash: 2e82feb9df4121b24ffd1f5cad7669c6aa58c8e8
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="use-cognitive-services-in-powerapps"></a>Kognitiivisten palvelujen käyttö PowerAppsissa
Tässä artikkelissa kerrotaan, miten luodaan perussovellus, joka analysoi tekstiä käyttämällä [Microsoftin kognitiivisten palvelujen tekstianalysoinnin ohjelmointirajapintaa (API)](https://docs.microsoft.com/azure/cognitive-services/text-analytics/overview). Näytämme, miten voit määrittää tekstianalysoinnin ohjelmointirajapinnan ja yhdistää sen käyttämällä [tekstianalysointiyhteyttä](https://docs.microsoft.com/connectors/cognitiveservicestextanalytics/). Sen jälkeen näytämme, miten voit luoda sovelluksen, joka kutsuu API:a.

> [!NOTE]
> Jos PowerApps-sovellusten kehittäminen on sinulle uutta, suosittelemme lukemaan kohdan [Sovelluksen luominen alusta alkaen](get-started-create-from-blank.md) ennen kuin perehdyt tähän artikkeliin.

## <a name="introduction-to-microsoft-cognitive-services"></a>Microsoftin kognitiiviset palvelut
Microsoftin kognitiiviset palvelut ovat joukko API-liittymiä, SDK:ita ja palveluja, joiden avulla voit tehdä sovelluksestasi älykkäämmän, kiinnostavamman ja helpommin löydettävän. Näiden palvelujen avulla voit helposti lisätä sovelluksiisi älykkäitä ominaisuuksia – kuten tunnetilojen ja videokuvan tunnistuksen, kasvojen ja puheen tunnistuksen, tietokonenäön sekä puheen ja kielen ymmärtämisen.

Tässä artikkelissa keskitytään kielen ymmärtämiseen tekstianalyysin ohjelmointirajapinnan (Text Analytics API) avulla. Tämän API:n avulla voit tunnistaa asenteen, tärkeimmät lauseet, aiheet ja tekstin kielen. Aloitamme API:n kokeiluversiolla ja kirjaudumme sen jälkeen esikatseluversion käyttäjäksi.

### <a name="try-out-the-text-analytics-api"></a>Kokeile tekstianalyysin API:a
API:sta on kokeiluversio verkossa – näet, miten se toimii, ja tutustut JSON:iin, jonka palvelu palauttaa.

1. Siirry [tekstianalyysin API](https://azure.microsoft.com/services/cognitive-services/text-analytics/) -sivulle.

2. Valitse **Tutustu käytännössä** -osio ja käytä esimerkkitekstiä tai kirjoita oma. Napsauta tai napauta **Analysoi**. 
   
    ![Tekstianalyysin API:n kokeiluversio](./media/cognitive-services-api/text-analytics-demo.png)

3. Sivun **Analysoitu teksti** -välilehdellä näytetään muotoillut tulokset, ja JSON-vastaus näkyy **JSON**-välilehdellä. [JSON](http://json.org/) on tapa esittää tietoja – tässä tapauksessa tekstianalyysin API:n palauttamat tiedot.

## <a name="sign-up-for-the-text-analytics-api"></a>Kirjaudu tekstianalyysin API:n käyttäjäksi
API on saatavana maksuttomana esikatselutoimintona, ja se on liitetty Azure-tilaukseen. Voit hallita API:a Azure-portaalissa.

1. Jos sinulla ei vielä ole Azure-tiliä, [rekisteröidy ja tee maksuton tilaus](https://azure.microsoft.com/free/).

2. Kirjaudu Azure-tilillesi.

3. Siirry Azure-portaalissa kohtaan [Luo kognitiivisia palveluja](https://go.microsoft.com/fwlink/?LinkId=761108).

4. Syötä tekstianalyysin API:n tiedot seuraavassa kuvassa olevan mallin mukaan. Valitse hinnoittelutasoksi **F0** (maksuton).
   
    ![Luo tekstianalyysin API](./media/cognitive-services-api/azure-create.png)

5. Napsauta tai napauta vasemmassa alakulmassa **Luo**.

6. Napsauta tai napauta **koontinäytössä** API:a, jonka loit äsken.
   
    ![Azuren koontinäyttö](./media/cognitive-services-api/azure-dashboard.png)

7. Napsauta tai napauta **näppäimiä**.
   
    ![Azure-valikko](./media/cognitive-services-api/azure-menu-keys.png)

8. Kopioi jokin näytön oikeassa reunassa olevista näppäimistä. Käytät tätä avainta myöhemmin, kun luot yhteyden API-liittymään.
   
    ![API-avaimet](./media/cognitive-services-api/azure-keys.png)

## <a name="build-the-app"></a>Sovelluksen rakentaminen
Kun tekstianalysoinnin API on valmis ja toimii, voit luoda siihen yhteyden PowerAppsista ja rakentaa sovelluksen, joka kutsuu API:a. Tämä on yksittäinen näyttösovellus, joka tarjoaa samantapaiset toiminnot kuin tekstianalysoinnin API-sivulla oleva kokeiluversio. Aloitetaan sovelluksesi luominen.

### <a name="create-the-app-and-add-a-connection"></a>Luo sovellus ja lisää yhteys
Ensin sinun täytyy luoda tyhjä puhelinsovellus ja lisätä yhteys **tekstianalyysiyhteyden** avulla. Jos tarvitset lisätietoja näistä tehtävistä, katso kohdat [Sovelluksen luominen alusta alkaen](get-started-create-from-blank.md) ja [Yhteyksien hallinta PowerAppsissa](add-manage-connections.md).

1. Siirry osoitteeseen [web.powerapps.com](https://web.powerapps.com), valitse **Aloita tyhjästä** > ![Sovelluksen puhelinkuvake](./media/cognitive-services-api/icon-phone-app.png) (puhelin) > **Tee tämä sovellus**.

    ![Aloita tyhjästä](./media/cognitive-services-api/start-from-blank.png)

2. Valitse PowerApps Studion keskimmäisestä ruudusta **Yhdistä tietoihin**.

3. Napsauta tai napauta **Tiedot**-paneelin kohtaa **Uusi yhteys** > **Tekstianalyysi**.

4. Kopioi avain kohtaan **Tiliavain** ja napsauta tai napauta **Luo**.
   
    ![Tekstianalyysiliitin](./media/cognitive-services-api/create-connection-ta.png)

### <a name="add-controls-to-the-app"></a>Ohjausobjektien lisääminen sovellukseen
Seuraavaksi lisäät sovellukseen ohjausobjektit. Itse yleensä lisään ohjausobjekteihin kaavoja samalla kun kehitän sovellusta, mutta tässä tapauksessa keskitymme ensin ohjausobjekteihin ja lisäämme muutaman kaavan seuraavassa osiossa. Sovellus ja kaikki sen ohjausobjektit näkyvät seuraavassa kuvassa.

![Valmis sovellus](./media/cognitive-services-api/finished-app-no-data.png)

Luo tämä näyttö noudattamalla seuraavia ohjeita. Jos ohjausobjektin nimi on määritetty, kyseistä nimeä käytetään seuraavan osion kaavassa.

1. Napsauta tai napauta **Aloitus**-välilehdellä ensin **Uusi näyttö** ja sen jälkeen **Vieritettävä näyttö**. 

2. Valitse **Näyttö2** ja sen jälkeen **[Otsikko]**, ja muuta otsikon arvoksi **Tekstianalyysi**.

3. Lisää esittelytekstiä varten **Otsikko**-ohjausobjektin teksti.

4. Lisää **Tekstisyöte**-ohjausobjekti, jotta voit kirjoittaa analysoitavaksi tarkoitettua tekstiä. Anna ohjausobjektin nimeksi **tiTextToAnalyze**. Sovelluksen pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![Sovellus ja sen otsikko, alaotsikko ja tekstisyöte](./media/cognitive-services-api/partial-app-step1.png)

5. Lisää kolme **Valintaruutu**-ohjausobjektia, jotta voit valita, mitkä API-toiminnot suoritetaan. Anna ohjausobjektien nimiksi **chkLanguage**, **chkPhrases** ja **chkSentiment**.

6. Lisää painike, jolla voit kutsua API:n, kun olet valinnut suoritettavat toiminnot. Sovelluksen pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![Sovellus ja sen valintaruudut ja painike](./media/cognitive-services-api/partial-app-step2.png)

7. Lisää kolme **Otsikko**-ohjausobjektia. Kahdessa ensimmäisessä on kielten ja asenteen API-kutsujen vastaukset; kolmannessa on näytön alareunassa olevan valikoiman esittely.

8. Lisää **Tyhjä pystysuuntainen valikoima** -ohjausobjekti ja lisää valikoimaan **Otsikko**-ohjausobjekti. Valikoimassa on API-kutsusta saadut avainlauseet. Sovelluksen pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![Sovellus ja sen selitteet ja valikoima](./media/cognitive-services-api/partial-app-step3.png)

9. Valitse vasemmasta ruudusta **Näyttö1** > kolme pistettä (**...** ) > **Poista** (et tarvitse tätä näyttöä sovelluksessa).

Pidämme tämän sovelluksen yksinkertaisen ja keskitymme tekstianalyysin API:n kutsumiseen. Voisit kuitenkin lisätä sovellukseen muita ominaisuuksia, kuten logiikan, jolla näytetään ja piilotetaan ohjausobjekteja valittujen valintaruutujen mukaan, vianhallinnan tilanteessa, jossa käyttäjä ei valitse mitään vaihtoehtoa, jne.

### <a name="add-logic-to-make-the-right-api-calls"></a>Lisää logiikka, jolla tehdään oikeat API-kutsut
Nyt sinulla on hieno sovellus, jolla ei vielä ole mitään käyttöä. Korjataan tämä tilanne hetken päästä. Ennen kuin perehdymme yksityiskohtiin, on syytä ymmärtää malli, jonka mukaan sovellus toimii:

1. Sovellus tekee API-kutsut valittuna olevien valintaruutujen perusteella. Kun napsautat tai napautat **Analysoi teksti**, sovellus tekee 1, 2 tai 3 API-kutsua.

2. Sovellus tallentaa API:n palauttamat tiedot kolmeen eri [kokoelmaan](working-with-variables.md#create-a-collection): **languageCollect**, **sentimentCollect** ja **phrasesCollect**.

3. Näiden kolmen kokoelman sisällön perusteella sovellus päivittää valikoimaan kahden selitteen **Teksti**-ominaisuuden sekä **Kohteet**-ominaisuuden.

Pidä tämä mielessäsi, kun lisäät painikkeen **OnSelect** (Valittaessa) -ominaisuuden. Kohta alkaa tapahtua.

```
If(chkLanguage.Value=true,

        ClearCollect(languageCollect, TextAnalytics.DetectLanguage({numberOfLanguagesToDetect:1, text:tiTextToAnalyze.Text}).detectedLanguages.name)

);

If(chkPhrases.Value=true,

        ClearCollect(phrasesCollect, TextAnalytics.KeyPhrases({language:"en", text:tiTextToAnalyze.Text}).keyPhrases)

);

If(chkSentiment.Value=true,

        ClearCollect(sentimentCollect, TextAnalytics.DetectSentiment({language:"en", text:tiTextToAnalyze.Text}).score)

)
```

API-kutsun tekeminen muodostuu useasta osasta, jotka selitetään tässä:

* **If**-lausekkeet ovat yksinkertaisia – ne ovat ehtoja, jotka tarkoittavat, että "jos tietty valintaruutu on valittuna, tee kyseiselle ominaisuudelle API-kutsu".

* Määritä kullekin kutsulle parametrit:

  * Jokaisen kolmen kutsun syötetekstiksi määritetään **tiTextToAnalyze.Text**.

  * Kielen tunnistamiseen tarkoitettuun **DetectLanguage()**-asetukseen valittavien kielten määrä (**numberOfLanguagesToDetect**) on kovakoodattu arvoon 1, mutta voit ohittaa tämän parametrin käyttämällä sovelluksessa jotain logiikkaa.

  * Avainlauseiden **KeyPhrases()**-ominaisuuden ja asennetunnisteen **DetectSentiment()**-ominaisuuden **kielten enimmäismääräksi** on kovakoodattu ”fi”, mutta voit ohittaa tämän parametrin käyttämällä sovelluksessa jotain logiikkaa. Voit esimerkiksi tunnistaa kielen ensin **DetectLanguage()**-ominaisuuden avulla ja määrittää tämän parametrin sen mukaan, mitä edellä mainittu parametri palauttaa.

* Lisää kunkin kutsun tulokset asianmukaiseen kokoelmaan:

    * Lisää **languageCollect**-kokoelmaan tekstistä tunnistetun kielen **nimi**.

    * Lisää **phrasesCollect**-kokoelmaan **avainlauseet**, jotka tunnistettiin tekstistä.

    * Lisää **sentimentCollect**-kokoelmaan tekstin sisältämän asenteen **pistemäärä**, joka on 0–1 siten, että 1  on yhtä kuin 100 % positiivinen.

### <a name="display-the-results-of-the-api-calls"></a>API-kutsujen tulosten näyttäminen
Kun haluat nähdä API-kutsujen tulokset, katso asianmukainen kokoelma kustakin ohjausobjektista:

1. Määritä kielen selitteen **Text**-ominaisuudeksi: `"The language detected is " & First(languageCollect).name`.
   
    **First()**-funktio palauttaa ensimmäisen (ja tässä tapauksessa ainoan) tietueen **languageCollect**-kokoelmaan, ja sovellus näyttää kyseiseen tietueeseen liittyvän **nimen** (ainut kenttä).

2. Määritä asenne-selitteen **Text**-ominaisuudeksi: `"The sentiment score is " & Round(First(sentimentCollect.Value).Value, 3)\*100 & "% positive."`.
   
    Myös tämä kaava käyttää **First()**-funktiota, hakee **arvon** (0-1) ensimmäisestä ja ainoasta tietueesta ja muodostaa sen perusteella prosenttimäärän.

3. Määritä avainlauseiden valikoiman **Items**-ominaisuudeksi: `phrasesCollect`.
   
    Nyt käsittelet valikoimaa, joten et tarvitse **First()**-funktiota erottamaan yksittäistä arvoa. Viittaat kokoelmaan, ja valikoima näyttää avainlauseet luettelona.

## <a name="run-the-app"></a>Sovelluksen suorittaminen

Nyt kun sovellus on valmis, suorita se ja katso, miten se toimii: napsauta tai napauta oikeassa yläkulmassa olevaa Suorita-painiketta ![Sovelluksen suorittaminen](./media/cognitive-services-api/icon-run-app.png). Seuraavassa kuvassa kaikki kolme asetusta ovat valittuna ja teksti on sama kuin tekstianalyysin API-sivulla oleva oletusteksti.

![Valmis sovellus ja sen tiedot](./media/cognitive-services-api/finished-app.png)

Jos vertaat tämän sovelluksen lopputulosta artikkelin alussa esiteltyyn tekstianalyysin API -sivuun, näet, että niissä on samat tulokset.

Toivottavasti tiedät nyt hieman enemmän tekstianalyysin API:sta ja sinusta on ollut mielenkiintoista nähdä, kuinka se yhdistetään sovellukseen. Kerro meille, jos toivot meidän kertovan tarkemmin joistain muista kognitiivisista palveluista (tai mistä tahansa palveluista). Kuten aina, voit lisätä kommentteihin palautetta tai kysymyksiä.

