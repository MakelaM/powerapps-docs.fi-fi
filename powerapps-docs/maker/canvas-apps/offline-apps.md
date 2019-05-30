---
title: Kehitä offline-tilassa toimivia pohjaan perustuvia sovelluksia | Microsoft Docs
description: Kehitä offline-tilassa toimivia pohjaan perustuvia sovelluksia, jotta käyttäjät voivat työskennellä tehokkaasti myös ilman verkkoyhteyttä.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/31/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 8004a39e83ea3615ce8a77637a9f5c0271b67781
ms.sourcegitcommit: 157ab15738e2d0d1bf9097bbb7b9e3d9c29a4015
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/28/2019
ms.locfileid: "66265780"
---
# <a name="develop-offline-capable-canvas-apps"></a>Kehitä offline-tilassa toimivia pohjaan perustuvia sovelluksia

Mobiilikäyttäjät usein tarvitsevat ollakseen tuottavia jopa kun heillä on rajoitetusti tai niitä ei ole. Kun rakennat pohjaan perustuvan sovelluksen, voit tehdä seuraavia tehtäviä:

- Avaa PowerApps Mobilessa ja suorittaa sovelluksia offline-tilassa.
- Määrittää, onko sovellus offline-tilassa, verkossa tai käyttääkö se käytön mukaan laskutettavaa yhteyttä käyttämällä [Connection](../canvas-apps/functions/signals.md#connection)-signaaliobjektia.
- Käyttää [kokoelmia](../canvas-apps/create-update-collection.md) ja hyödyntää funktioita, kuten [LoadData ja SaveData](../canvas-apps/functions/function-savedata-loaddata.md), perustietojen tallennukseen offline-tilassa.

## <a name="limitations"></a>Rajoitukset

**LoadData** ja **SaveData** yhdistää lomake yksinkertainen mekanismia pieniä tietomääriä tallentaa paikalliseen laitteeseen. Näiden funktioiden avulla voit lisätä yksinkertainen offline-ominaisuuksista sovellukseesi.

Nämä funktiot rajoittavat käytettävissä oleva sovellus muistin määrä, koska ne toimivat muistissa-kokoelma. Käytettävissä olevaa muistia voi vaihdella laitteen, käyttöjärjestelmän, PowerApps Mobilessa käyttämän muistin ja näyttöjä ja ohjausobjekteja sovelluksen monimutkaisuudesta riippuen. Jos tallennat useita megatavua, kokeile sovellusta odotettua skenaarioita, jolloin oletat suoritettavaksi laitteissa. Sinun tulee yleisesti käytettävissä olevaa muistia 30 – 70 megatavua.

Funktiot myös ei automaattisesti ratkaisemaan yhdistämisen ristiriitoja, kun laite on online-tilassa. Mitä tietoja on tallennettu ja miten käsitellään yhteyden muodostamista uudelleen määritys on enintään valmistaja, kun kirjoitat lausekkeita.

Offline-ominaisuuksista päivitykset, palaa tässä ohjeaiheessa ja tilaa [PowerApps-blogin](https://powerapps.microsoft.com/blog/).

## <a name="overview"></a>Yleiskatsaus

Kun suunnittelet offline-tilanteita, ensin harkitse miten sovelluksesi käsittelevät tietoja. PowerApps-sovellusten käyttää tietoja pääasiassa kautta joukon [liittimet](../canvas-apps/connections-list.md) , käyttöympäristön, kuten SharePointin, Office 365 ja Common Data Service. Voit myös luoda mukautettuja liittimiä, jotka antavat sovelluksille mahdollisuuden käyttää mitä tahansa palvelua, joka tarjoaa RESTful-päätepisteen. Tämä voi olla WWW-ohjelmointirajapinta tai palvelu, kuten Azure Functions. Nämä liittimet toimivat Internetin kautta HTTPS-käytännöllä, minkä vuoksi käyttäjillä on oltava Internet-yhteys, jotta he voivat käyttää palvelun tarjoamia tietoja ja ominaisuuksia.

![PowerApps-sovellus liittimineen](./media/offline-apps/online-app.png)

### <a name="handling-offline-data"></a>Offline-tietojen käsitteleminen

Powerappsissa voit suodattaa, Hae, lajitella, koostaa ja käsitellä tietoja yhdenmukaisesti tietolähteestä riippumatta. Lähteet kokoelmista muistissa sovelluksen SharePoint-luetteloihin, SQL-tietokantoihin ja Common Data Service. Tämän yhdenmukaisuuden vuoksi sinun voit helposti kohdistaa sovelluksen käyttää eri tietolähteitä varten. Tärkeintä offline-tilanteita, voit käyttää paikallisten kokoelmien käyttämisen tietojen hallintaan lähes kokonaan ilman muutoksia sovelluksen logiikkaan. Itse asiassa paikalliset kokoelmat ovat ensisijainen mekanismi offline-tietojen käsittelyyn.

## <a name="build-an-offline-app"></a>Luo offline-sovellus

Tässä aiheessa kuvataan kohdistus pitää sovelluskehityksen offline-ominaisuuksia, yksinkertaisen Twitteriin liittyvän skenaarion. Luot sovelluksen, jonka avulla voit lukea Twitter-julkaisuja ja lähettää twiittejä ollessasi offline-tilassa. Kun sovellus siirtyy online-tilaan, sovellus julkaisee twiitit ja lataa paikalliset tiedot uudelleen.

Korkean tason, sovelluksen suorittaa seuraavia tehtäviä:

- Kun käyttäjä avaa sovelluksen:

  - Jos laite on online-tilaan, sovellus hakee tietoja Twitter-liittimen kautta ja täyttää kokoelma tietojen kanssa.
  - Jos laite on offline-tilassa, sovelluksen lataa tiedot paikallisen välimuistitiedosto käyttämällä [ **LoadData** ](../canvas-apps/functions/function-savedata-loaddata.md) funktio.
  - Käyttäjä voi lähettää twiittejä. Jos sovellus on online-tilassa, se julkaisee twiitit suoraan Twitteriin ja päivittää paikallisen välimuistin.

- Viiden minuutin välein, kun sovellus on online-tilassa:

  - Sovellus julkaisee kaikki twiitit paikallisessa välimuistissa.
  - Sovelluksen päivittää paikallisen välimuistin ja tallentaa sen avulla [ **SaveData** ](../canvas-apps/functions/function-savedata-loaddata.md) funktio.

### <a name="step-1-add-twitter-to-a-blank-phone-app"></a>Vaihe 1: Lisää Twitter tyhjä puhelinsovellus

1. Valitse PowerApps Studio **tiedoston** > **uusi**.
1. Valitse **Tyhjä sovellus** -ruudusta **Puhelinasettelu**.
1. Valitse **Näytä**-välilehdessä **Tietolähteet**.
1. Tässä **tietojen** ruudussa **Lisää tietolähde**.
1. Valitse **uusi yhteys** > **Twitter** > **luoda**.
1. Anna tunnistetietosi, Luo yhteys ja sulje sitten **tietojen** ruudussa.

### <a name="step-2-collect-existing-tweets"></a>Vaihe 2: Kerää aiemmin twiitit

1. - **Puu näkymän** ruudussa **sovelluksen**, ja aseta sen **OnStart** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( Connection.Connected,
        ClearCollect( LocalTweets, Twitter.SearchTweet( "PowerApps", {maxResults: 10} ) );
            Set( statusText, "Online data" ),
        LoadData( LocalTweets, "LocalTweets", true );
            Set( statusText, "Local data" )
    );
    SaveData( LocalTweets, "LocalTweets" );
    ```

    > [!div class="mx-imgBorder"]
    > ![Kaava twiittien](./media/offline-apps/load-tweets.png)

1. - **Puu näkymän** ruudussa-valikko **sovelluksen** objekti ja valitse sitten **suorittaa OnStart** suorittaa kyseisen kaavan.

    > [!div class="mx-imgBorder"]
    > ![Suorita kaava twiittien](./media/offline-apps/load-tweets-run.png)

    > [!NOTE]
    > **LoadData** ja **SaveData** Funktiot voi näyttää virheen PowerApps Studio koska selaimet eivät tue niitä. Kuitenkin ne suorittaa yleensä kun otat tämän sovelluksen laitteeseen.

Tämä kaava tarkistaa, onko laite online:

- Jos laite on online-tilassa, kaava Lataa enintään 10 twiittejä sisältävät hakusanan ”PowerApps” **LocalTweets** kokoelma.
- Jos laite on offline-tilassa, kaava Lataa paikalliseen välimuistiin tiedoston nimeltä ”LocalTweets”, jos se on käytettävissä.

### <a name="step-3-show-tweets-in-a-gallery"></a>Vaihe 3: Twiitit näyttäminen valikoimassa

1. Valitse **Lisää** -välilehden **valikoiman** > **tyhjä, joustava korkeus**.

1. Määritä **kohteet** -ominaisuuden [ **valikoiman** ](controls/control-gallery.md) ohjausobjektin `LocalTweets`.

1. Valikoiman mallipohja, Lisää kolme [ **nimen** ](controls/control-text-box.md) ohjausobjekteja ja määritä **teksti** ominaisuuden jokaisen selitteen jokin näistä arvoista:

    - `ThisItem.UserDetails.FullName & " (@" & ThisItem.UserDetails.UserName & ")"`
    - `Text(DateTimeValue(ThisItem.CreatedAtIso), DateTimeFormat.ShortDateTime)`
    - `ThisItem.TweetText`

1. Lihavoi tekstin viimeisen selitteen niin, että valikoiman muistuttaa tätä esimerkkiä.

    > [!div class="mx-imgBorder"]
    > ![Valikoima näyttää mallin twiitit](./media/offline-apps/tweet-gallery.png)

### <a name="step-4-show-connection-status"></a>Vaihe 4: Näytä yhteyden tila

1. Valitse valikoiman Lisää selite ja aseta sen **väri** ominaisuudeksi **Red**.

1. Määritä uusin nimen **tekstin** -ominaisuuden arvoksi tämä kaava:

    `If( Connection.Connected, "Connected", "Offline" )`

Tämä kaava määrittää, onko laite online-tilassa. Jos se on, selite näyttää **yhdistetty**; muussa tapauksessa se näyttää **Offline**.

### <a name="step-5-add-a-box-to-compose-tweets"></a>Vaihe 5: Lisää ruutu twiittien laatimista varten

1. Yhteyden tila-nimen alla Lisää [ **Tekstisyöte** ](controls/control-text-input.md) ohjausobjekti ja nimeä se uudelleen **NewTweetTextInput**.

1. Määritä tekstisyötteen ruutu **oletus** ominaisuudeksi `""`.

    > [!div class="mx-imgBorder"]
    > ![Valikoiman tila tiedot ja tekstisyötteen ruutu](./media/offline-apps/status-input.png)

### <a name="step-6-add-a-button-to-post-the-tweet"></a>Vaihe 6: Lisää painike, jolla twiitti

1. Lisää tekstisyötteen ruutua **painike** ohjausobjekti ja määritä sen **tekstin** ominaisuudeksi tämä arvo:

    `"Tweet"`

1. Määritä painikkeen **OnSelect** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( Connection.Connected,
        Twitter.Tweet( "", {tweetText: NewTweetTextInput.Text} ),
        Collect( LocalTweetsToPost, {tweetText: NewTweetTextInput.Text} );
            SaveData( LocalTweetsToPost, "LocalTweetsToPost" )
    );
    Reset( NewTweetTextInput );
    ```  

1. - **OnStart** -ominaisuuden **sovelluksen**, Lisää rivi kaavan lopussa:

    ```powerapps-dot
    If( Connection.Connected,
        ClearCollect( LocalTweets, Twitter.SearchTweet( "PowerApps", {maxResults: 100} ) );
            Set( statusText, "Online data" ),
        LoadData( LocalTweets, "LocalTweets", true );
            Set( statusText, "Local data" )
    );
    SaveData( LocalTweets, "LocalTweets" );
    LoadData( LocalTweetsToPost, "LocalTweetsToPost", true );  // added line
    ```

    > [!div class="mx-imgBorder"]
    > ![Suorita kaava twiittien uncommented viiva](./media/offline-apps/load-tweets-save.png)

Tämä kaava määrittää, onko laite online:

- Jos laite on online-tilassa, se julkaisee twiitin heti.
- Jos laite on offline-tilassa, se sieppaa twiitin **LocalTweetsToPost** kokoelmaan ja tallentaa sen laitteeseen.

Sitten kaava palauttaa tekstiruudun tekstin syötön.

### <a name="step-7-check-for-new-tweets"></a>Vaihe 7: Tarkista uusia twiittejä

1. Lisää painike oikealla puolella **ajastin** ohjausobjektin.

    > [!div class="mx-imgBorder"]
    > ![Lopullinen sovellukset](./media/offline-apps/final-app.png)

1. Määritä ajastimen **kesto** ominaisuudeksi **300000**.

1. Määritä ajastimen **AutoStart** ja **toista** ominaisuudet, jotta voit **true**.

1. Määritä ajastimen **OnTimerEnd** tämä kaava:

    ```powerapps-dot
    If( Connection.Connected,
        ForAll( LocalTweetsToPost, Twitter.Tweet( "", {tweetText: tweetText} ) );
        Clear( LocalTweetsToPost );
        ClearCollect( LocalTweets, Twitter.SearchTweet( "PowerApps", {maxResults: 10} ) );
        SaveData( LocalTweets, "LocalTweets" );
   )
    ```

Tämä kaava määrittää, onko laite online-tilassa. Jos näin on, sovellus twiittaa kaikki kohteet **LocalTweetsToPost** kokoelma ja tyhjentää kokoelman.

## <a name="test-the-app"></a>Sovelluksen testaus

1. Avaa sovellus mobiililaitteella, joka on yhdistetty Internetiin.

    Aiemmin twiittejä näkyvät valikoimassa ja tilana näkyy **yhdistetty**.

1. Katkaise Internet laitteen laitteen lentokonetilasta ottamisesta käyttöön ja poistamisesta wi-fi.

    Tilan selite näyttää, että sovellus on **Offline**.

1. Kun laite on offline-tilassa, kirjoita twiitti, joka sisältää **Powerappsin**, ja valitse sitten **Twiitin** painike.

    Twiitin tallennetaan paikallisesti **LocalTweetsToPost** kokoelma.

1. Muodostaa uudelleen yhteyden organisaatioosi Internet laitteen käytöstä laitteen lentokonetilasta ja otat käyttöön wi-fi.

    Viiden minuutin aikana sovellus julkaisee twiitin, joka näkyy valikoimassa.

Toivottavasti saat tästä artikkelista käsityksen, millaisia ominaisuuksia PowerAppsissa on offline-tilassa toimivien sovellusten laatimista varten. Kuten aina, anna palautetta Microsoftin [keskustelupalstalla](https://powerusers.microsoft.com/t5/PowerApps-Forum/bd-p/PowerAppsForum1) ja jaa offline-sovellusesimerkkejäsi [PowerAppsin yhteisöblogissa](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/bg-p/PowerAppsBlog).