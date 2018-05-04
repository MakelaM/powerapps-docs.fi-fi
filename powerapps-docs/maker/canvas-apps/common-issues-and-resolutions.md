---
title: 'Yleisiä ongelmia ja ratkaisuja: PowerApps | Microsoft Docs'
description: Lue PowerAppsiin liittyvistä ongelmista ja ratkaisuista
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/12/2018
ms.author: sharik
ms.openlocfilehash: 369bbc445d54152f5b6319922d79a58c9b79121c
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="common-issues-and-resolutions-for-powerapps"></a>Yleisiä ongelmia ja ratkaisuja: PowerApps
## <a name="recently-addedchanged"></a>Äskettäin tehty lisäys/muutos
1. **Mukautetun kuvan käyttäminen sovelluksen kuvakkeena**

    PowerApps Studio for Windowsin versiossa 3.18043 mukautettuja kuvia ei voi käyttää sovellusten kuvakkeina. Voit kiertää tämän ongelman käyttämällä [PowerApps Studion verkkoversiota](https://web.powerapps.com) mukautetun kuvan lataamiseen. Voit vaihtoehtoisesti käyttää jotain Windowsin PowerApps Studioon sisältyvää kuvaketta ja mukauttaa sen taustaväriä.

1. **Näyttöjen kopioiminen ja liittäminen sovellusten välillä**

    Näyttöjen kopioimista ja liittämistä sovellusten välillä ei tällä hetkellä tueta. Voit kiertää ongelman, lisäämällä kohdesovellukseen uuden näytön, kopioimalla sitten ohjausobjektit lähdesovelluksen näytöstä ja liittämällä ne sitten kohdesovelluksen näyttöön.

1. **SharePoint-lomakkeiden asettelun muuttaminen**

    Kun SharePoint-lomakkeen asetuksia muokataan ja lomakkeen asettelu halutaan vaihtaa (oletusmuotoisesta) pystysuorasta vaakasuoraan, näyttöön voi joissakin kieliversioissa ilmaantua useita virhesymboleja (keltaisia kolmioita ohjausobjektien kohdalla). Voit korjata nämä virheet ja säilyttää vaaka-asettelun napsauttamalla **Kumoa**.

1. **Sovellus ei toimi**

    Jos luomasi sovellus lakkaa toimimasta ilman varoitusta, se voi johtua siitä, että sovellusta ei ole päivitetty tai julkaistu uudelleen kuuteen kuukauteen. Voit ratkaista ongelman päivittämällä sovelluksen tai julkaisemalla sen uudelleen, jolloin se synkronoituu uusimman PowerApps-version kanssa. Varmista sen jälkeen, että sovellus päivitetään tai julkaistaan uudelleen aina kuuden kuukauden sisällä.

1. **Tietotaulukko-ohjausobjekti**

    Jos kopioimassasi ja liittämässäsi **Tietotaulukko**-ohjausobjektissa olevan **Kohteet**-ominaisuuden kaava sisältää **Suodatin**-funktion, uuden **Tietotaulukko**-ohjausobjektin **Kohteet**-ominaisuuden kaava päättyy kenttänimiin, joiden loppupäätteenä on **_1**. Tämän tyyppinen kenttänimi ei ole kelvollinen, ja sen vuoksi tietotaulukkoon ei tule tietoja. Voit kiertää tämän ongelman varmistamalla ennen ohjausobjektin kopioimista, että **Filter**-funktio ei viittaa mihinkään tietolähteen kenttään, jolla on sama nimi kuin jollakin **Tietotaulukko**-ohjausobjektin sarakkeella. Jos niillä on sama nimi, nimeä **Tietotaulukko**-ohjausobjektin sarake uudelleen. Vaihtoehtoisesti voit poistaa viallisista kenttänimistä **_1**-loppupäätteen niin, että ne ovat yhteensopivia entiteetissä olevien nimien kanssa.

1. **Kamera-ohjausobjektit Windowsin PowerApps Studiossa**

    Windowsin PowerApps Studio saattaa kaatua, jos lisäät kamera- ohjausobjektin tai avaat sovelluksen, joka käyttää kamera-ohjausobjektia. Voit välttää tämän ongelman käyttämällä verkkokäyttöön tarkoitettua [PowerApps Studio ](create-app-browser.md)-versiota lisätessäsi tai käyttäessäsi kamera-ohjausobjektia.

2. **2.0.700 Android-laitteissa**

    Jos asennat Android-laitteeseen julkaisun 2.0.700, mutta sovellukset eivät aukea (tai jokin sovellus lakkaa toimimasta), poista PowerAppsin asennus, käynnistä laite uudelleen ja asenna PowerApps uudelleen.

3. **Valikoima on tyhjä, kun sovellus avataan**

    Jos luot sovelluksen automaattisesti tietojen pohjalta, tallennat sovelluksen ja avaat se uudelleen, selausvalikoimassa ei välttämättä näy heti mitään tietoja. Voit ratkaista ongelman kirjoittamalla hakukenttään vähintään yhden merkin ja sen jälkeen poistamalla kirjoittamasi tekstin. Tämän jälkeen valikoima näyttää odotetut tiedot.

4. **PowerAppsin päivittäminen Windows 8.1:ssa** 

    Jos asennat PowerAppsin tietokoneeseen, jossa on Windows 8 tai Windows 8.1, pidä Windows-kauppa auki ja aktiivisena, tarkista päivitykset Asetukset-oikopolun avulla ja asenna ne.

5. **Mukautetut yhdistämistoiminnot ja Common Data Service**

   Jos PowerApps-sovelluksen luomiseen on käytetty koontiversiota 2.0.540 tai aiempaa ja se käyttää Common Data Service -tietokantaa, ja vähintään yksi mukautettu yhdistämistoiminto on eri ympäristössä, ota tämä yhdistämistoiminto käyttöön samassa ympäristössä kuin tietokanta ja päivitä sovellus käyttämään uutta yhdistämistoimintoa. Muussa tapauksessa näyttöön tulee valintaikkuna, joka ilmoittaa, että API:a ei löytynyt. Lisätietoja on [ympäristöjen yleiskuvauksessa](../../administrator/environments-overview.md).

6. **Sovelluksen suorittaminen Windows 8.1:ssä** 

    Jos asennat [tämän päivityksen Windows 8.1:een](https://technet.microsoft.com/library/security/ms16-118), et voi suorittaa PowerApps Studiossa avaamiasi sovelluksia tässä käyttöjärjestelmässä. Voit kuitenkin edelleen suorittaa sovelluksia, jotka avaat [powerapps.com](https://web.powerapps.com)-sivulla tai käyttämällä PowerAppsin mobiiliversiota.

7. **Välilyönneillä varustetut sarakenimet**

    Jos käytät SharePoint-luetteloa tai Excel-taulukkoa, jonka sarakenimessä on välilyönti, PowerApps korvaa sen arvolla **”\_x0020\_”**. Esimerkiksi **"Sarakkeen Nimi"** SharePointissa tai Excelissä näkyy muodossa **"Sarakkeen_x0020_Nimi"** PowerAppsissa, kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.

## <a name="older"></a>Vanhempi
1. **Työnkulun muuttaminen jaetussa sovelluksessa**

    Jos lisäät sovellukseen työnkulun, jaat sen, ja sen jälkeen lisäät siihen palvelun tai muutat työnkulussa olevan yhteyden, sinun on poistettava työnkulku jaetusta sovelluksesta, lisättävä työnkulku uudelleen ja jaettava sovellus uudelleen. Muussa tapauksessa käyttäjät, jotka käynnistävät työnkulun, saavat todennusvirheen.

2. **Lokalisoidun version käyttäminen**.

    Jos käytössäsi on Windows 8.1 -julkaisu 2.0.531, et voi kirjoittaa **Tekstinsyöttö**-ohjausobjektiin, jos laitteen kieliasetukset vaativat IME-ikkunaa.

3. **Kamera-ohjausobjekti Windows-puhelimessa**

    Kamera-ohjausobjektin sisältävä sovellus saattaa kaatua, jos se avataan Windows-puhelimessa, jonka koontiversio on 10.0.10586.107. Voit välttää tämän ongelman päivittämällä uusimpaan koontiversioon (esimerkiksi suorittamalla [ päivityksen tukisovelluksen](https://www.microsoft.com/store/p/upgrade-advisor/9nblggh0f5g4)).

4. **Sovelluksen avaaminen mallipohjasta**.

    Jos käytössäsi on julkaisu 2.0.500 tai vanhempi, näyttöön tulee virhesanoma, kun yrität luoda sovelluksen mallipohjasta. Toiminnon käyttäminen vaatii päivittämistä uudempaan versioon.

    Jos käytössäsi on julkaisu 2.0.510 tai uudempi, näyttöön voi tulla varoitus, kun yrität luoda sovelluksen mallipohjasta. Voit kuitenkin sulkea viestin ja luoda sovelluksen.

5. **Viivakoodin skannaaminen**

    **Viivakoodi**-ohjausobjektin käyttöä ja koskevia ohjeita ja parhaita käytäntöjä koskevia tietoja on kohdassa [Viivakoodin skannaaminen](scan-barcode.md).

6. **Sovellusten luominen ja muokkaaminen selaimessa**

    Voit käyttää verkkopohjaisessa PowerAppsissa monia samoja ominaisuuksia kuin Windowsin PowerApps Studiossa, mutta et kaikkia. Lisätietoja on kohdassa [Sovelluksen luominen selaimessa](create-app-browser.md).

7. **Entiteetissä olevan otsikkokentän muuttaminen**

    Jos muutat otsikkokenttää entiteetissä, johon muut entiteetit viittaavat yhden tai useamman haun välityksellä, muutoksen tallentamisyritys saa aikaan virheilmoituksen. Voit kiertää ongelman poistamalla kaikki kyseiseen entiteettiin kohdistuvat haut, muuttamalla otsikkoa ja luomalla haut sen jälkeen uudestaan. Lisätietoja hakutoiminnoista on kohdassa [Entiteettien välisen suhteen luominen](../common-data-service/data-platform-entity-lookup.md).

8. **Sovellukset, jotka luovat yhteyden paikalliseen SharePointiin**

    Jos jaat sovelluksen, joka on riippuvainen yhteyksistä, joita ei jaeta automaattisesti (esimerkiksi paikallisesta SharePoint-sivustosta), verkkoselaimessa näkyy tyhjä valintaikkuna (ilman tekstiä), kun käyttäjä avaa sovelluksen selaimessa ja napsauttaa tai napauttaa kohtaa **Kirjaudu sisään**. Sulje valintaikkuna napsauttamalla tai napauttamalla oikeassa yläkulmassa olevaa Sulje (X) -kuvaketta. Valintaikkuna ei tule näkyviin, jos avaat sovelluksen PowerApps Studiossa tai PowerAppsin mobiiliversiossa. Lisätietoja jaetuista yhteyksistä on kohdassa [Sovelluksen resurssien jakaminen](share-app-resources.md).

9. **Kun PowerApps luo sovelluksen tietojen pohjalta, lajitteluun ja etsimiseen käytettävää kenttää ei määritetä automaattisesti**.

   Jos haluat määrittää tämän kentän, muokkaa **[Kohteet](controls/properties-core.md)**-kaavaa. Katso suodatusta ja lajittelua koskevat ohjeet kohdasta [Valikoiman lisääminen](add-gallery.md).

10. **Tietojen pohjalta luoduissa sovelluksissa voidaan käyttää vain tietolähteen 500:aa ensimmäistä tietuetta**.

     Yleisesti ottaen PowerApps toimii minkä tahansa kokoisen tietolähteen kanssa, koska se delegoi toiminnot tietolähteelle. Jos toimintoa ei voi delegoida, PowerApps antaa laatimisen aikana varoituksen ja toimii vain 500:n ensimmäisen tietolähteen tietueen kohdalla.  Lisätietoja delegoinnista on kohdassa [Filter-funktio](functions/function-filter-lookup.md).

11. **Excel-tietojen täytyy olla taulukkomuodossa**.

     Kohdassa [Pilvitallennusyhteydet](connections/cloud-storage-blob-connections.md#known-limitations) on tietoa rajoituksista, jotka koskevat Excelin käyttöä tietolähteenä.

12. **Mukautettuja SharePoint-luetteloita tuetaan, mutta ei kirjastoja, tietyntyyppisiä luettelosarakkeita tai sarakkeita, jotka tukevat useita arvoja tai valintoja**.

     Lisätietoja on kohdassa [SharePoint Online](connections/connection-sharepoint-online.md#known-issues).

13. **Yhteismuokkaamista ei tueta. Yksi tekijä kerrallaan, ole hyvä**.

     Jos useampi kuin yksi henkilö muokkaa samaa sovellusta samaan aikaan, sovellus voi vioittua tai yhden käyttäjän tekemät muutokset voivat korvata toisen tekemät muutokset. Sulje sovellus, ennen kuin joku toinen muokkaa sitä.

14. **Saattaa joskus kestää hetken, ennen kuin äskettäin jaettua sovellusta voi käyttää**.

     Joissakin tapauksissa äskettäin jaettu sovellus ei ole heti käytettävissä. Odota hetki, niin se tulee saataville.

15. **Et voi muuttaa tietoja [Lomake-ohjausobjektissa](controls/control-form-detail.md)käyttämällä mukautettua korttia**.

     Varaston mukautetusta kortista puuttuu **[Päivitys](controls/control-card.md)**-ominaisuus, joka vaaditaan muutosten takaisinkirjoittamiseen. Voit kiertää ongelman seuraavasti:

    * Valitse lomake-ohjausobjekti ja lisää kortti käyttämällä oikeanpuoleista ruutua sen kentän perusteella, jonka haluat kortin näyttävän.  
    * Avaa kortin lukitus. Katso ohjeet kohdasta [Tietokorttien esittely](working-with-cards.md#unlock-a-card).
    * Poista tai järjestele kortissa olevia ohjausobjekteja mielesi mukaan, samalla tavoin kuin teet mukautetulle kortille.

16. **Jos sovelluksen käyttöympäristö on Android 5.0, WebView-versioita v48 tai v49 käyttävä Nexus 6 voi kaatua**.

     Käyttäjä voi korjata tämän ongelman päivittämällä aiempaan WebView-versioon (3 x) tai Android 6.0:aan.

17. **Kamera saattaa olla tilapäisesti poissa käytöstä, jos muisti ei riitä**.

     Jos mobiililaitteessa on liian vähän muistia, kamera poistuu tilapäisesti käytöstä, jotta laite ei kaatuisi.

18. **Office 365:n videoliitäntää ei tueta**.

19. **Kortin valikoima on syrjäytetty**.

     Nykyisiä sovelluksia, jotka käyttävät tätä ominaisuutta, suoritetaan edelleen toistaiseksi, mutta korttivalikoimaa ei voi lisätä. Korvaa korttivalikoimat uusilla **[Muokkauslomake](controls/control-form-detail.md)**- ja **[Näyttölomake](controls/control-form-detail.md)** -ohjausobjekteilla.
