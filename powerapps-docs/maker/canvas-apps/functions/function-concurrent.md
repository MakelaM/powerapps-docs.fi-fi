---
title: Concurrent-funktio | Microsoft Docs
description: PowerAppsin Concurrent-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/26/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ce8128f3a5eddf3a67fe2082844bf996c25adc05
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61551381"
ms.PowerAppsDecimalTransform: true
---
# <a name="concurrent-function-in-powerapps"></a>PowerAppsin Concurrent-funktio
Arvioi useita kaavoja keskenään samanaikaisesti.

## <a name="description"></a>Kuvaus
**Concurrent**-funktio arvioi useita kaavoja samaan aikaan. Yleensä kaavat lasketaan ketjuttamalla niitä yhdessä [ **;** ](operators.md) operaattoria, joka laskee kaikki peräkkäisessä järjestyksessä järjestyksessä. Kun sovellus suorittaa toimintoja samanaikaisesti, käyttäjät saavat tuloksen tavallista nopeammin.

Paranna sovelluksesi suorituskykyä, kun se lataa tietoja, käyttämällä sovelluksen [**OnStart**](../controls/control-screen.md)-ominaisuuden **Concurrent**-funktiota. Kun tietokutsut eivät ala ennen edellisten kutsujen valmistumista, sovelluksen on odotettava kaikkien pyyntöaikojen summaa. Jos tietokutsut alkavat samanaikaisesti, sovelluksen on odotettava vain pisimmän pyyntöajan verran. Selaimet parantavat usein suorituskykyä suorittamalla tietotoimintoja samanaikaisesti.

Ei voida ennustaa, missä järjestyksessä kaavojen arviointi **Concurrent**-funktiossa alkaa ja päättyy. **Concurrent**-funktion kaavoissa ei tulisi olla riippuvuuksia muihin kaavoihin samassa **Concurrent**-funktiossa, ja PowerApps tuo näyttöön virhesanoman, jos riippuvuuksia on. Funktion sisältä voi turvallisesti käyttää riippuvuuksia **Concurrent**-funktion ulkopuolisiin kaavoihin, koska ne päättyvät ennen **Concurrent**-funktion käynnistymistä. Kaavat jälkeen **samanaikaisten** funktio voi olla riippuvuudet turvallisesti kaavoja: kaikki suoritetaan loppuun ennen **samanaikaisten** funktio on valmis ja siirtyy seuraava kaava ketjun (Jos voit Käytä **;** operaattorin). Varo hienovaraisia järjestysriippuvuuksia, jos kutsut funktioita tai palvelumenetelmiä, joilla on sivuvaikutuksia.

Voit ketjun kaavat yhdessä **;** operaattorin argumentti sisällä **samanaikaisten**. Esimerkiksi funktio **Concurrent( Set( a; 1 );; Set( b; a+1 ); Set( x; 2 );; Set( y; x+2 ) )** arvioi kaavan **Set( a; 1 );; Set( b; a+1 )** samanaikaisesti kaavan **Set( x; 2 );; Set( y; x+2 )** kanssa. Tässä tapauksessa kaavojen sisäisiä riippuvuuksia voidaan käyttää: **a** määritetään ennen **b**:tä ja **x** määritetään ennen **y**:tä.

Sen mukaan, missä laitteessa tai selaimessa sovellus on käynnissä, vain kourallinen kaavoja saatetaan arvioida samanaikaisesti. **Concurrent** käyttää käytettävissä olevia ominaisuuksia, eikä sen suoritus pääty, ennen kuin kaikki kaavat on arvioitu.

Jos otat **kaavatason virheiden hallinnan** käyttöön (lisäasetuksissa), ensimmäinen argumentista löytyvä virhe palautetaan **Concurrent**-funktiosta; muutoin palautetaan *tyhjä*. Jos kaikki kaavat ovat oikein, palautetaan arvo *tosi*. Jos yksi kaava epäonnistuu, kyseisen kaavan loppuosa pysäytetään, mutta muiden kaavojen arviointi jatkuu.

Voit käyttää **Concurrent**-funktiota vain [toimintakaavoissa](../working-with-formulas-in-depth.md).

## <a name="syntax"></a>Syntaksi
**Concurrent**( *Formula1*; *Formula2* [; ...] )

* *Formula(s)* – Pakollinen. Samanaikaisesti arvioitavat kaavat. Vähintään kaksi kaavaa on annettava.

## <a name="examples"></a>Esimerkkejä

#### <a name="loading-data-faster"></a>Tietojen lataamisen nopeuttaminen

1. Luo sovellus ja lisää neljä tietolähteitä Common Data Service, SQL Server-tai SharePoint. 

    Tässä esimerkissä käytetään neljää taulukkoa [SQL Azuren Adventure Works -mallitietokannasta](https://docs.microsoft.com/azure/sql-database/sql-database-get-started-portal). Kun olet luonut tietokannan, yhdistä se PowerAppsista käyttämällä täydellistä palvelimen nimeä (esimerkiksi srvname.database.windows.net):

    ![Yhteyden muodostaminen Azuren Adventure Works -tietokantaan](media/function-concurrent/connect-database.png)

2. Lisää **[Painike](../controls/control-button.md)**-ohjausobjekti ja määritä sen **OnSelect**-ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    ClearCollect( Product; '[SalesLT].[Product]' );;
    ClearCollect( Customer; '[SalesLT].[Customer]' );;
    ClearCollect( SalesOrderDetail; '[SalesLT].[SalesOrderDetail]' );; 
    ClearCollect( SalesOrderHeader; '[SalesLT].[SalesOrderHeader]' )
    ```

3. Ota [Microsoft Edge](https://docs.microsoft.com/microsoft-edge/devtools-guide/network)- tai [Google Chrome](https://developers.google.com/web/tools/chrome-devtools/network-performance/) -selaimessa kehitystyökalut käyttöön, jotta voit tarkkailla verkkoliikennettä sovelluksen ollessa käynnissä.

1. (valinnainen) Ota verkon rajoittaminen käyttöön tämän vertailun vaikutuksen liioittelemista varten.

4. Pidät Alt-näppäintä painettuna, valitse painike ja seuraa sitten verkkoliikennettä.

    Työkalut näyttävät neljä sarjana suoritettavaa pyyntöä, kuten tässä esimerkissä.  Todelliset ajat on poistettu, sillä ne vaihtelevat suuresti.  Kaaviosta nähdään, että jokainen kutsu käynnistyy, kun edellinen on päättynyt:

    ![Koko aikavälin kattava aikakaavio neljästä verkkopyynnöstä, joista jokainen käynnistyy edellisen päätyttyä](media/function-concurrent/chained-network.png)

5. Tallenna, sulje ja avaa sovellus uudelleen.

    PowerApps tallentaa tietoja välimuistiin, joten painikkeen valitseminen uudelleen ei välttämättä aiheuta neljää uutta pyyntöä. Aina, kun haluat testata suorituskykyä, sulje ja avaa sovellus uudelleen. Jos olet ottanut verkon rajoituksen käyttöön, voit halutessasi poistaa sen käytöstä, kunnes olet valmis toiseen testiin.

1. Lisää toinen **[Painike](../controls/control-button.md)**-ohjausobjekti ja määritä sen **OnSelect**-ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    Concurrent( 
        ClearCollect( Product; '[SalesLT].[Product]' ); 
        ClearCollect( Customer; '[SalesLT].[Customer]' );
        ClearCollect( SalesOrderDetail; '[SalesLT].[SalesOrderDetail]' );
        ClearCollect( SalesOrderHeader; '[SalesLT].[SalesOrderHeader]' )
    )
    ```

    Huomaa, että lisäsit samat **ClearCollect**-kutsut ensimmäiseen painikkeeseen, mutta ne on tässä vaiheessa rivitetty ja erotettu pilkulla **Concurrent**-funktiossa.

2. Tyhjennä verkonvalvonta selaimessa.

1. Jos käytit aiemmin verkon rajoittamista, ota se uudelleen käyttöön.

3. Pidät Alt-näppäintä pohjassa, valitse toinen painike ja seuraa sitten verkkoliikennettä.

    Työkalut näyttävät neljä samanaikaisesti suoritettavaa pyyntöä, kuten tässä esimerkissä.  Tässäkin todelliset ajat on poistettu, koska ne vaihtelevat suuresti.  Kaaviosta nähdään, että kaikki kutsut käynnistyvät samanaikaisesti, eivätkä odota edellisen päättymistä:

    ![Noin puolet koko aikavälistä kattava aikakaavio neljästä verkkopyynnöstä, jotka kaikki käynnistyvät yhdessä](media/function-concurrent/concurrent-network.png)

    Nämä kaaviot perustuvat samaan asteikkoon. Käyttämällä **Concurrent**-funktiota olet puolittanut näiden operaatioiden loppuun suorittamiseen kuluvan kokonaisajan. 

5. Tallenna, sulje ja avaa sovellus uudelleen.

#### <a name="race-condition"></a>Kilpailutilanne

1. Lisää sovellukseesi yhteys [Microsoft Translator](../connections/connection-microsoft-translator.md) -palveluun.

2. Lisää [ **Tekstisyöte**](../controls/control-text-input.md)-ohjausobjekti ja nimeä se nimellä **TextInput1**, jos sillä on eri nimi.

3. Lisää **Painike**-ohjausobjekti ja määritä sen **OnSelect**-ominaisuudeksi seuraava kaava:

    ```powerapps-comma
    Set( StartTime; Value( Now() ) );;
    Concurrent(
        Set( FRTrans; MicrosoftTranslator.Translate( TextInput1.Text; "fr" ) );; 
            Set( FRTransTime; Value( Now() ) );
        Set( DETrans; MicrosoftTranslator.Translate( TextInput1.Text; "de" ) );; 
            Set( DETransTime; Value( Now() ) )
    );;
    Collect( Results;
        { 
            Input: TextInput1.Text;
            French: FRTrans; FrenchTime: FRTransTime - StartTime; 
            German: DETrans; GermanTime: DETransTime - StartTime; 
            FrenchFaster: FRTransTime < DETransTime
        }
    )
    ```

4. Lisää [**Arvotaulukko**](../controls/control-data-table.md)-ohjausobjekti ja aseta sen **Items**-ominaisuudeksi **Tulokset**.

1. Käyttöön **ominaisuudet** välilehti oikeanpuoleisessa ruudussa Valitse **Muokkaa kenttiä** avaamiseen **kentät** ruudussa.

1. Valitse kenttäluettelossa kaikkien niiden kenttien valintaruutu, joiden haluat näkyvän arvotaulukossa.

1. (valinnainen) Vedä **Syöte**-kenttä luettelon alkuun ja vedä **FrenchFaster**-kenttä luettelon loppuun.

    ![Tuloskokoelman kenttäluettelo](media/function-concurrent/field-list.png) 

6. Valitse **Tekstisyöte**-ohjausobjekti ja kirjoita tai liitä käännettävä lause.

7. Pidä Alt-näppäintä painettuna ja täytä taulukko valitsemalla painike useita kertoja.

    Ajat näkyvät millisekunteina.
  
    ![Arvotaulukon näyttö, joka sisältää tulokset merkkijonon ”Hello World” kääntämisestä ranskaksi ja saksaksi. Joskus kääntäminen ranskaksi on nopeampaa kuin saksaksi ja joskus päinvastoin.](media/function-concurrent/race-condition.png) 

    Joissakin tapauksissa ranskankielinen käännös saadaan nopeammin kuin saksankielinen ja päinvastoin. Molemmat käynnistyvät samaan aikaan, mutta toinen palaa ennen toista monista eri syistä, kuten verkkoviiveen ja palvelinpuolen käsittelyn takia.

    [Kilpailutilanne](https://en.wikipedia.org/wiki/Race_condition) ilmenee, jos sovelluksella on riippuvuus ensin päättyvään käännökseen. PowerApps kuitenkin merkitsee useimmat havaitsemansa ajoitusriippuvuudet.
