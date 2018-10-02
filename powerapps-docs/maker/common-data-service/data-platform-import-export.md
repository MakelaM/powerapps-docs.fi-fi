---
title: Common Data Service sovelluksille -ratkaisun tietojen tuominen tai tietojen vieminen ratkaisuun
description: Common Data Service sovelluksille -ratkaisun Excel- tai CSV-tiedostojen tietojen joukkotuonti ja -vienti Hae tiedot Excelistä- ja Vie tiedot -toimintojen avulla
author: sabinn-msft
ms.service: powerapps
ms.topic: conceptual
ms.component: cds
ms.date: 05/14/2018
ms.author: sabinn
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-or-export-data-from-common-data-service-for-apps"></a>Common Data Service sovelluksille -ratkaisun tietojen tuominen tai tietojen vieminen ratkaisuun

Voit joukkotuoda ja -viedä tietoja Microsoft Excel- tai CSV-tiedostoista päivitetyn Common Data Service sovelluksille -ratkaisun ympäristöjen Hae tiedot Excel-tiedostosta- ja Vie tiedot -toimintojen avulla.

Tiedostoja voi tuoda entiteetteihin Excel- tai CSV-tiedostoista kahdella eri tavalla.

## <a name="option-1-import-by-creating-and-modifying-a-file-template"></a>Vaihtoehto 1: Tuo luomalla tiedostomalli ja muokkaamalla sitä

Jokaisella entiteetillä on pakollisia kenttiä, joiden on oltava syöttötiedostossa. On suositeltavaa luoda malli. Vie ensin entiteetin tiedot. Käytä samaa tiedostoa (joka on muokattu tietojesi avulla), kun tuot tiedot entiteettiin. Tämä malli säästää aikaa ja vaivaa. Kunkin entiteetin pakollisia kenttiä ei tarvitse ottaa huomioon.

1. Valmistele tiedostomalli.

    a. Vie entiteetin tiedot CVS-tiedostoon. Noudata **Tietojen vieminen CSV-tiedostoon** -kohdan ohjeita.  
    b. Määritä suunnitelma, jonka avulla varmistat tietojen yksilöllisyyden. Käytä joko **ensisijaisia** tai **vaihtoehtoisia avaimia**.  
    c. Seuraavassa osassa on ohjeita siitä, miten tietojen yksilöllisyys varmistetaan ennen tietojen tuontia entiteettiin. 

1. Muokkaa tiedostoa tietojen avulla.

    - Kopioi tiedot Excelistä tai CSV-tiedostosta juuri luotuun malliin.

1. Tuo tiedosto.  
    a. Laajenna [powerapps.com](https://web.powerapps.com/)-sivustossa **Tiedot**-osa. Valitse siirtymisruudun **Entiteetit**.  
    b. Valitse entiteetti, johon tiedot tuodaan.  
    c. Valitse yläreunan kolme pistettä tai valikko. Valitse **Hae tiedot**. Valitse **Hae tiedot Excelistä**.  

    > [!NOTE]
    > Voit tuoda tiedot useaan entiteettiin valitsemalla yläreunan valikossa **Hae tiedot**. Valitse **Hae tiedot Excelistä**. Tämän jälkeen voit valita useita entiteettejä ja valita sitten **Seuraava**-kohdan.

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki tietojen tuomisesta **Asiakas**-entiteettiin](./media/data-platform-import-export/import-data-to-account.png)

    d. Valitse **Tuo tiedot** -näytössä, tuodaanko tiedot Excelistä vai CSV-tiedostosta.  
    e. Valitse **Lataa**.  
    f. Valitse tiedosto. Lataa tiedosto seuraamalla kehotteita.  

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki tiedoston lataamisesta **Asiakas**-entiteettiin](./media/data-platform-import-export/upload-account.png)

    g. Kun tiedosto on ladattu ja **Yhdistämisen tila** on vihreä, valitse oikeassa yläkulmassa **Tuo**. Seuraavassa osassa on lisätietoja mahdollisten yhdistämismääritysvirheiden löytämisestä ja korjaamisesta.  

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki onnistuneesta **Yhdistämisen tila**- ja **Tuo**-painikkeesta](./media/data-platform-import-export/success-map-imp.png)

    h. Kun tuonti on valmis, näyttöön tulee lisäysten ja päivitysten kokonaismäärä.  

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki onnistuneesta tuonnista, joka näyttää lisäysten ja päivitysten määrän](./media/data-platform-import-export/success-imp-insert.png)

    > [!NOTE]
    > Käytä Upsert (Update or Insert, päivitys tai lisäys) -logiikkaa tietueen päivityksessä, jos se on jo olemassa, tai uuden tietueen lisäyksessä.

## <a name="option-2-import-by-bringing-your-own-source-file"></a>Vaihtoehto 2: Tuonti tuomalla oma lähdetiedosto

Jos olet kokenut käyttäjä ja tiedät Common Data Service sovelluksille -entiteettien annetun entiteetin pakolliset kentät, määritä oma Excel- tai CSV-lähdetiedosto. Noudata kohdan **Tiedoston tuominen** ohjeita.

## <a name="navigate-mapping-errors"></a>Yhdistämismääritysvirheisiin siirtyminen

Jos saat yhdistämismääritysvirheitä tiedoston lataamisen jälkeen, valitse **Yhdistämismäärityksen tila**. Noudata seuraavia ohjeita ja tarkista ja korjaa kentän yhdistämismääritysvirheet.

1. Käytä oikealla **Näytä**-kohdan alla olevaa avattavaa valikkoa ja käsittele **yhdistämättömät kentät**, **kentät, joissa ei ole virheitä**, tai **pakolliset kentät**.

    > [!TIP]
    > Sen mukaan, onko kyseessä varoitus- vai virhesanoma, tarkista **yhdistämättömät kentät** tai **kentät, joissa ei ole virheitä**, **Kentän yhdistämismääritykset** -kohdan avattavan valikon avulla.

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki osittaisesta vastaavuudesta, joka johtuu kentän yhdistämismäärityksiä sisältävistä varoituksista](./media/data-platform-import-export/partial-match.png)

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki kentän yhdistämismääritysten ongelmiin siirtymisestä](./media/data-platform-import-export/navigate-mappings.png)

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki kentän yhdistämismäärityksiä sisältävien varoitusten tarkistamisesta ja korjaamisesta](./media/data-platform-import-export/inspect-warnings.png)

2. Kun kaikki virheet ja varoitukset on ratkaistu, valitse oikeassa yläkulmassa oleva **Tallenna muutokset**. Siirryt takaisin **Tuo tiedot** -näyttöön.
3. Kun **Yhdistämisen tila** -sarakkeessa on **Valmis** vihreällä, valitse oikeassa yläkulmassa oleva **Tuo**.
4. Kun näyttöön tulee **Tuonti onnistui** -sanoma, näet lisäysten ja päivitysten kokonaismäärät.

## <a name="ensure-uniqueness-when-you-import-data-into-an-entity-from-excel-or-csv"></a>Varmista yksilöllisyys, kun tuot tiedot entiteettiin Excelistä tai CSV-tiedostosta

Common Data Service sovelluksille -entiteetit käyttävät ensisijaista avainta Common Data Service -entiteettitaulukon tietueiden yksilöinnissä. Common Data Service -entiteetin ensisijainen avain on GUID-tunnus. Se muodostaa tietueen tunnistamisen oletusperustan. Tietotoiminnot, kuten tietojen tuominen Common Data Service -entiteetteihin, tuovat esille ensisijaiset oletusavaimet.

Esimerkki:  
**Asiakas**-entiteetin ensisijainen avain on **accountid**.

   > [!div class="mx-imgBorder"] 
   > ![**Asiakas**-entiteetin mallituontitiedosto, jossa ensisijainen avain on **accountid**](./media/data-platform-import-export/export-pk.png)

Joskus ensisijainen avain ei toimi, jos tietoja integroidaan ulkoisesta lähteestä. Käytä Common Data Service -sovellusta, kun haluat määrittää ensisijaisen avaimen sijaan tietueen yksilöivät vaihtoehtoiset avaimet.

Esimerkki:  
**Asiakas**-entiteetin vaihtoehtoiseksi avaimeksi voidaan määrittää **transactioncurrencyid** luonnollisen avaimeen perustuvan tunnistamisen avulla. Voit esimerkiksi käyttää **Yhdysvaltain dollaria** aiemmin näytetyn GUID-arvon **88c6c893-5b45-e811-a953-000d3a33bcb9** sijaan. Voit valita avaimiksi myös **rahayksikön tunnuksen** tai **valuutan nimen**.

   > [!div class="mx-imgBorder"] 
   > ![Esimerkki vaihtoehtoisen avaimen luomisesta **Valuutta**-entiteetille](./media/data-platform-import-export/create-ak.png)

   > [!div class="mx-imgBorder"] 
   > ![**Asiakas**-entiteetin mallituontitiedosto, jossa luonnollinen avain on **valuutan nimi**](./media/data-platform-import-export/export-nk.png)

Käyttäjät voivat yhä käyttää ensisijaisia avaimia tunnuksina vaihtoehtoisten avainten määrittämisen jälkeen. Edellisessä esimerkissä ensimmäinen tiedosto on yhä sallittu, jos GUID-tunnukset ovat sallittuja.

## <a name="export-data-to-csv"></a>Tietojen vieminen CSV-tiedostoon

Voit tehdä tietojen viennin kerran vakioentiteetistä tai mukautetusta entiteetistä. Ja voit viedä tietoja useista entiteeteistä kerralla. Jos viet tietoja useista entiteeteistä, jokainen entiteetti viedään sen omaan Microsoft CSV -tiedostoon.

1. Laajenna [powerapps.com](https://web.powerapps.com/)-sivustossa **Tiedot**-osa. Valitse siirtymisruudun **Entiteetit**.
1. Valitse entiteetti, josta haluat viedä tiedot.
1. Valitse yläreunan kolme pistettä tai valikko. Valitse **Vie**. Valitse **Tiedot**.

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki tietojen viemisestä **Asiakas**-entiteetistä](./media/data-platform-import-export/export-account.png)

    > [!NOTE]
    > Jos haluat viedä tietoja useista entiteeteistä, valitse yläreunan valikossa **Vie**. Valitse **Tiedot**. Voit valita useita entiteettejä.

1. Kun vienti on suoritettu, voit **ladata viedyt tiedot**. Tämä lataus sisältää linkin ladattavaan CSV-tiedostoon.

    > [!div class="mx-imgBorder"] 
    > ![Esimerkki viennistä, joka näyttää onnistuneen viennin ja linkin ladattavaan tiedostoon](./media/data-platform-import-export/export-success.png)

## <a name="unsupported-data-types"></a>Tietotyypit, joita ei tueta

Seuraavia tietotyyppejä ei tueta tällä hetkellä.

- Aikavyöhyke
- Monivalinta-asetusjoukko
- Kuva
