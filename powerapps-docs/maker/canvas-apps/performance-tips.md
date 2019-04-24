---
title: Kangassovellusten suorituskyvyn optimointi | Microsoft Docs
description: Noudattamalla tämän aiheen parhaita käytäntöjä voit tehostaa PowerAppsissa luomiesi kangassovellusten suorituskykyä.
author: yingchin
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 08/31/2018
ms.author: yingchin
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 6406afad9079895a0da38c7f1f6e3961f2e37fa1
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61536364"
---
# <a name="optimize-canvas-app-performance-in-powerapps"></a>Kangassovellusten suorituskyvyn optimointi PowerAppsissa
Microsoft tekee kaikkensa parantaakseen kaikkien PowerApps-ympäristössä toimivien sovellusten suorituskykyä. Tämän aiheen parhaiden käytäntöjen avulla voit myös tehostaa luomiesi sovellusten suorituskykyä.

Kun käyttäjä avaa sovelluksen, sovellus käy seuraavat suoritusvaiheet läpi, ennen kuin se avaa käyttöliittymän: 
1. **Käyttäjän todentaminen** - Jos käyttäjä ei ole avannut sovellusta aiemmin, sovellus kehottaa käyttäjää kirjautumaan sisään tunnistetiedoillaan sovelluksen tarvitsemia yhteyksiä varten. Jos sama käyttäjä avaa sovelluksen uudelleen, hän saattaa joutua kirjautumaan sisään uudelleen organisaation suojauskäytäntöjen mukaisesti. 
2. **Metatietojen hakeminen** - Noutaa metatiedot, kuten sovelluksen PowerApps-ympäristön version ja lähteet, josta sen on haettava tietoja. 
3. **Sovelluksen alustaminen** - Suorittaa kaikki **OnStart**-ominaisuudessa määritetyt tehtävät. 
4. **Näyttöjen hahmontaminen** - Hahmontaa ensimmäisen ohjausobjekteja sisältävän näytön, jonka sovellus on täyttänyt tiedoilla. Jos käyttäjä avaa muita näyttöjä, sovellus hahmontaa ne käyttämällä samaa menetelmää.  

## <a name="limit-data-connections"></a>Rajoita tietoyhteyksiä 
**Älä yhdistä yli 30 tietolähteeseen samassa sovelluksessa**. Sovellus pyytää uusia käyttäjiä kirjautumaan sisään jokaiseen liittimeen, joten jokainen ylimääräinen liitin kasvattaa sovelluksen käynnistysaikaa. Kun sovellusta suoritetaan, jokainen liitin käyttää suoritinresursseja, muistia ja verkon kaistanleveyttä, kun sovellus pyytää tietoja kyseisestä tietolähteestä. 

Voit nopeasti mitata sovelluksesi suorituskykyä ottamalla käyttöön kehittäjätyökalut [Microsoft Edgessä](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) tai [Google Chromessa](https://developers.google.com/web/tools/chrome-devtools/network-performance/) sovelluksen suorittamisen aikana. Sovelluksesi on todennäköisesti kestää kauemmin kuin 15 sekuntia palauttamana tietoja, jos se pyytää tietoja usein yli 30 tietolähteisiin, kuten Common Data Service-, Azure SQL-, SharePoint- ja Excel onedrivessa.  

## <a name="limit-the-number-of-controls"></a>Rajoita ohjausobjektien määrää 
**Älä lisää yli 500 ohjausobjektia samaan sovellukseen**. PowerApps luo HTML DOMin kunkin ohjausobjektin hahmontamista varten. Mitä enemmän ohjausobjekteja lisäät, sitä enemmän muodostamisaikaa PowerApps tarvitsee. 

Voit joissakin tapauksissa saavuttaa saman lopputuloksen ja nopeuttaa sovelluksen käynnistymisaikaa, kun käytät valikoimaa yksittäisten ohjausobjektien sijaan. Lisäksi voit vähentää samassa näytössä käytettävien ohjausobjektityyppien määrää. Jotkin ohjausobjektit (kuten esimerkiksi PDF-katseluohjelma, tietotaulukko ja yhdistelmäruutu) vaativat suuria suorituskomentosarjoja, jolloin niiden hahmontamiseen kuluu enemmän aikaa. 

## <a name="optimize-the-onstart-function"></a>Optimoi OnStart-funktio
[**ClearCollect**](functions/function-clear-collect-clearcollect.md)-funktion avulla voit tallentaa tietoja välimuistiin paikallisesti, jos ne eivät muutu käyttäjäistunnon aikana. Voit myös käyttää [**Concurrent**](functions/function-concurrent.md)-funktiota tietolähteiden lataamiseen samanaikaisesti.

Kuten [tässä aiheessa](functions/function-concurrent.md) esitellään, **Concurrent**-funktion avulla voit puolittaa ajan, jonka sovellus käyttää tietojen lataamiseen.

Ilman **Concurrent**-funktiota, tämä kaava joutuu lataamaan nämä neljä taulukkoa aina yksi kerrallaan:

    ClearCollect( Product, '[SalesLT].[Product]' );
    ClearCollect( Customer, '[SalesLT].[Customer]' );
    ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' );
    ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' )

Voit varmistaa tämän toiminnan selaimesi kehittäjätyökalujen avulla:

![Sarjoitettu ClearCollect](./media/performance-tips/perfconcurrent1.png)
    
Voit sisällyttää saman kaavan **Concurrent**-funktioon vähentääksesi toiminnon vaatiman kokonaisajan:

    Concurrent( 
        ClearCollect( Product, '[SalesLT].[Product]' ),
        ClearCollect( Customer, '[SalesLT].[Customer]' ),
        ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' ),
        ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' ))
        
Tämän muutoksen jälkeen sovellus noutaa taulukot rinnakkain: 

![Rinnakkaisen ClearCollect](./media/performance-tips/perfconcurrent2.png)  

## <a name="cache-lookup-data"></a>Välimuistin hakutiedot
Käytä **Joukko**-funktiota tallentaaksesi hakutaulukkotietoja välimuistiin paikallisesti, jolloin et joudu toistuvasti noutamaan tietoja lähteestä. Tämä menetelmä auttaa optimoimaan suorituskykyä, jos tiedot eivät oletettavasti tule muuttumaan istunnon aikana. Kuten tässä esimerkissä näytetään, tiedot noudetaan lähteestä kerran, jonka jälkeen niihin viitataan paikallisesti siihen asti, kunnes käyttäjä sulkee sovelluksen. 

    Set(CustomerOrder, Lookup(Order, id = “123-45-6789”));
    Set(CustomerName, CustomerOrder.Name);
    Set(CustomerAddress, CustomerOrder.Address);
    Set(CustomerEmail, CustomerOrder.Email);
    Set(CustomerPhone, CustomerOrder.Phone);

Yhteystiedot, oletusarvot ja käyttäjätiedot eivät muutu usein. Siksi voit yleisesti ottaen käyttää tätä menetelmää myös **Defaults**- ja **Käyttäjä**-funktioiden kanssa. 

## <a name="avoid-controls-dependency-between-screens"></a>Vältä näyttöjen välistä ohjausobjektiriippuvuutta
Jos ohjausobjektin arvo riippuu eri näytössä olevan ohjausobjektin arvosta, hallinnoi tätä tietoa muuttujan, kokoelman tai tietolähdeviittauksen avulla.

## <a name="use-global-variables"></a>Käytä yleisiä muuttujia
Jotta voit välittää sovelluksen tilan näytöstä toiseen, luo tai muokkaa yleistä muuttuja-arvoa [**Joukko**](functions/function-set.md)-funktion avulla **Navigate**- ja **UpdateContext)**-funktioiden sijaan.

## <a name="use-delegation"></a>Käytä delegointia
Mikäli mahdollista, käytä funktioita, jotka delegoivat tietojen käsittelyä tietolähteeseen sen sijaan, että ne noutaisivat tietoja paikallisen laitteen käsiteltäväksi. Jos sovelluksen on käsiteltävä tietoja paikallisesti, toiminto vaatii paljon enemmän käsittelytehoa, muistia ja verkon kaistanleveyttä, erityisesti jos tietojoukko on suuri.

Kuten [tämä luettelo](delegation-list.md) osoittaa, eri tietolähteet tukevat eri toimintojen delegointia:

![Käytä delegointia](./media/performance-tips/perfdelegation1.png)

Esimerkiksi SharePoint-luettelot tukevat [**Suodatin**](functions/function-filter-lookup.md)-funktion delegointia mutta eivät [**Hae**](functions/function-filter-lookup.md)-funktion. Tämä tarkoittaa siis sitä, että sinun kannattaa käyttää **Suodatin**-funktiota **Haku**-funktion sijaan, jos haluat löytää kohteita valikoimasta, jonka SharePoint-luettelo sisältää yli 500 kohdetta. Lisätietoja löytyy kohdasta [Suurien SharePoint-luetteloiden käyttäminen PowerAppsissa](https://powerapps.microsoft.com/blog/powerapps-now-supports-working-with-more-than-256-items-in-sharepoint-lists/) (blogikirjoitus). 

## <a name="use-delayed-load"></a>Käytä viivästettyä kuormitusta
Ota käyttöön [kokeellinen ominaisuus](working-with-experimental.md) viivästetty kuormitus, jos sovelluksesi sisältää yli 10 näyttöä, ei yhtään sääntöä ja useita ohjausobjekteja, jotka löytyvät usealta näytöltä ja jotka on sidottu suoraan tietolähteeseen. Jos luot tämän tyyppisen sovelluksen ja et ota tätä ominaisuutta käyttöön, sovelluksen suorituskyky saattaa kärsiä, sillä jokaisen näytön ohjausobjekti on tuotava jokaiseen näyttöön silloinkin, kun ne eivät ole avoinna. Lisäksi kaikki sovelluksen näytöt on päivitettävä aina, kun tietolähde muuttuu esimerkiksi silloin, kun käyttäjä lisää tietueen.

## <a name="working-with-large-data-sets"></a>Suurten tietojoukkojen käsitteleminen
Käyttämällä delegoitavia tietolähteitä ja kaavoja voit varmistaa sovelluksesi toiminnan ja sen, että käyttäjäsi pääsevät aina käsiksi tarvitsemiinsa tietoihin. Samalla myös vältät 2 000 tietojen rivirajoituksen kyselyille, joita ei voi delegoida. Tietuesarakkeet, joita käyttäjät voivat käyttää tietojen hakemiseen, suodattamiseen tai lajitteluun, nämä sarakkeiden indeksit ovat suunniteltu [SQL Serverille](https://docs.microsoft.com/sql/relational-databases/sql-server-index-design-guide?view=sql-server-2017) ja [SharePointille](https://support.office.com/article/Add-an-index-to-a-SharePoint-column-f3f00554-b7dc-44d1-a2ed-d477eac463b0), kuten näissä dokumenteissa kuvataan.  

## <a name="republish-apps-regularly"></a>Julkaise sovelluksesi uudelleen säännöllisesti
[Julkaise sovelluksesi uudelleen](https://powerapps.microsoft.com/blog/republish-your-apps-to-get-performance-improvements-and-additional-features/) (blogikirjoitus) saadaksesi suorituskyvyn parannuksia ja muita ominaisuuksia PowerApps-ympäristöstä.

## <a name="avoid-repeating-the-same-formula-in-multiple-places"></a>Toistaa saman kaavan useita paikoissa
Jos useita ominaisuudet (etenkin, jos se on monimutkainen) samaa kaavaa, harkitse määritetty kerran ja viittaavat kaikki lisäehdot ensimmäisen ominaisuus tulos. Esimerkiksi ei määritetty **DisplayMode** saman monimutkaisia kaavan ohjausobjekteja A, B, C, D ja E-ominaisuuden. Määritä sen sijaan A: n **DisplayMode** ominaisuus monimutkaisia kaava B **DisplayMode** A: n tuloksen ominaisuudeksi **DisplayMode** -ominaisuuden, ja niin edelleen C D ja E.

## <a name="enable-delayoutput-on-all-text-input-controls"></a>DelayOutput käyttöön kaikki teksti syöteohjausobjektit
Jos sinulla on useita kaavat tai sääntöjä, jotka viittaavat arvo **Tekstisyöte** ohjausobjekti, Määritä **DelayedOutput** TRUE tämän ohjausobjektin ominaisuuden. **Tekstin** päivitetään vasta, kun näppäilyt annettu nopeasti peräkkäin on lopettanut tämän ohjausobjektin ominaisuuden. Kaavoja tai sääntöjä ei suoriteta niin monta kertaa ja parantaa sovelluksen suorituskykyä.

## <a name="avoid-using-formupdates-in-rules-and-formulas"></a>Vältä Form.Updates säännöt ja kaavat
Jos viittaat käyttäjän syötteen arvon sääntö tai kaavan avulla **Form.Updates** muuttujan, se laskee kaikki lomakkeen tiedot kortteja funktion ja luo tietueen aina, kun. Jos haluat tehdä sovelluksen tehokkaampia, viitata suoraan kortin tai ohjausobjektin arvo arvo.

## <a name="next-steps"></a>Seuraavat vaiheet
Tarkista [koodausstandardeja](https://aka.ms/powerappscanvasguidelines) maksimoida sovellusta ja pitämällä sovellukset ylläpitämistä.
