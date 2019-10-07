---
title: Kangassovellusten suorituskyvyn optimointi | Microsoft Docs
description: Noudattamalla tämän aiheen parhaita käytäntöjä voit tehostaa PowerAppsissa luomiesi kangassovellusten suorituskykyä.
author: yingchin
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/17/2019
ms.author: yingchin
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9943678815b53df048ad197e3cdcbd56f4070fa3
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995790"
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

Voit nopeasti mitata sovelluksesi suorituskykyä ottamalla käyttöön kehittäjätyökalut [Microsoft Edgessä](https://docs.microsoft.com/microsoft-edge/devtools-guide/network) tai [Google Chromessa](https://developers.google.com/web/tools/chrome-devtools/network-performance/) sovelluksen suorittamisen aikana. Sovelluksesi vie todennäköisemmin yli 15 sekuntia aikaa tietojen palauttamiseen, jos se pyytää usein tietoja yli 30 tieto lähteestä, kuten Common Data Service, Azure SQL:stä, SharePointista ja Excelistä OneDrivessa.  

## <a name="limit-the-number-of-controls"></a>Rajoita ohjausobjektien määrää 
**Älä lisää yli 500 ohjausobjektia samaan sovellukseen**. PowerApps luo HTML DOMin kunkin ohjausobjektin hahmontamista varten. Mitä enemmän ohjausobjekteja lisäät, sitä enemmän muodostamisaikaa PowerApps tarvitsee. 

Voit joissakin tapauksissa saavuttaa saman lopputuloksen ja nopeuttaa sovelluksen käynnistymisaikaa, kun käytät valikoimaa yksittäisten ohjausobjektien sijaan. Lisäksi voit vähentää samassa näytössä käytettävien ohjausobjektityyppien määrää. Jotkin ohjausobjektit (kuten esimerkiksi PDF-katseluohjelma, tietotaulukko ja yhdistelmäruutu) vaativat suuria suorituskomentosarjoja, jolloin niiden hahmontamiseen kuluu enemmän aikaa. 

## <a name="optimize-the-onstart-function"></a>Optimoi OnStart-funktio
[**ClearCollect**](functions/function-clear-collect-clearcollect.md)-funktion avulla voit tallentaa tietoja välimuistiin paikallisesti, jos ne eivät muutu käyttäjäistunnon aikana. Voit myös käyttää [**Concurrent**](functions/function-concurrent.md)-funktiota tietolähteiden lataamiseen samanaikaisesti.

Kuten [tässä aiheessa](functions/function-concurrent.md) esitellään, **Concurrent**-funktion avulla voit puolittaa ajan, jonka sovellus käyttää tietojen lataamiseen.

Ilman **Concurrent**-funktiota, tämä kaava joutuu lataamaan nämä neljä taulukkoa aina yksi kerrallaan:

```
ClearCollect( Product, '[SalesLT].[Product]' );
ClearCollect( Customer, '[SalesLT].[Customer]' );
ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' );
ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' )
```

Voit varmistaa tämän toiminnan selaimesi kehittäjätyökalujen avulla:

![Sarjoitettu ClearCollect](./media/performance-tips/perfconcurrent1.png)
    
Voit sisällyttää saman kaavan **Concurrent**-funktioon vähentääksesi toiminnon vaatiman kokonaisajan:

```
Concurrent( 
    ClearCollect( Product, '[SalesLT].[Product]' ),
    ClearCollect( Customer, '[SalesLT].[Customer]' ),
    ClearCollect( SalesOrderDetail, '[SalesLT].[SalesOrderDetail]' ),
    ClearCollect( SalesOrderHeader, '[SalesLT].[SalesOrderHeader]' ))
```

Tämän muutoksen jälkeen sovellus noutaa taulukot rinnakkain: 

![Rinnakkainen ClearCollect](./media/performance-tips/perfconcurrent2.png)  

## <a name="cache-lookup-data"></a>Välimuistin hakutiedot
Käytä **Joukko**-funktiota tallentaaksesi hakutaulukkotietoja välimuistiin paikallisesti, jolloin et joudu toistuvasti noutamaan tietoja lähteestä. Tämä menetelmä auttaa optimoimaan suorituskykyä, jos tiedot eivät oletettavasti tule muuttumaan istunnon aikana. Kuten tässä esimerkissä näytetään, tiedot noudetaan lähteestä kerran, jonka jälkeen niihin viitataan paikallisesti siihen asti, kunnes käyttäjä sulkee sovelluksen. 

```
Set(CustomerOrder, Lookup(Order, id = “123-45-6789”));
Set(CustomerName, CustomerOrder.Name);
Set(CustomerAddress, CustomerOrder.Address);
Set(CustomerEmail, CustomerOrder.Email);
Set(CustomerPhone, CustomerOrder.Phone);
```

Yhteystiedot, oletusarvot ja käyttäjätiedot eivät muutu usein. Siksi voit yleisesti ottaen käyttää tätä menetelmää myös **Defaults**- ja **Käyttäjä**-funktioiden kanssa. 

## <a name="avoid-controls-dependency-between-screens"></a>Vältä näyttöjen välistä ohjausobjektiriippuvuutta
Jos haluat parantaa suoritus tehoa, sovelluksen näytöt ladataan muistiin vain, kun niitä tarvitaan. Tämä optimointi voi vaikeutua, jos esimerkiksi näyttö 1 on ladattu ja jokin sen kaavoista käyttää ohjaus objektin ominaisuutta näytöstä 2. Nyt näyttö 2 on ladattava riippuvuuden täyttämiseksi, ennen kuin näyttö 1 voidaan näyttää. Imagine Screen 2: lla on riippuvuussuhde näytössä 3, jossa on toinen riippuvuus näytöstä 4 ja niin edelleen. Tämä riippuvuusketju voi aiheuttaa useiden näyttöjen lataamisen.

Tästä syystä Vältä kaavojen riippuvuuksia näyttöjen välillä. Joissakin tapa uksissa voit käyttää yleistä muuttujaa tai kokoelmaa tietojen jakamiseen näyttöjen välillä.

On olemassa poikkeus. Edellisessä esimerkissä voidaan kuvitella, että näyttö 1 voidaan näyttää vain siirtymällä näytöstä 2. Sitten näyttö 2 olisi jo ladattu muistiin, kun näyttö 1 ladattiin. Lisä työtä ei tarvita näytön 2 riippuvuuden täyttämiseksi, joten suoritus kyky ei ole vaikutusta.

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

## <a name="avoid-repeating-the-same-formula-in-multiple-places"></a>Vältä saman kaavan toistamista useissa paikoissa
Jos useita ominaisuuksia suoritetaan samalla kaavalla (etenkin jos se on monimutkainen), harkitse sen asettamista kerran ja viittaa sitten ensimmäisen ominaisuuden tulos teen myöhempiin ominaisuuksiin. Älä esimerkiksi määrittää ohjaus objektien A, B, C, D ja E **DisplayMode** -ominaisuudeksi samaa monimutkaista kaavaa. Sen sijaan, Set A **DisplayMode** -ominaisuudeksi Complex Formula, Set B: n **DisplayMode** -ominaisuudeksi n **DisplayMode** -ominaisuuden tulos ja niin edelleen C, D ja E.

## <a name="enable-delayoutput-on-all-text-input-controls"></a>Ota DelayOutput käyttöön kaikissa teksti syöte ohjaus objekteissa
Jos sinulla on useita kaavoja tai sääntöjä, jotka viittaavat **teksti syöte** -ohjaus objektin arvoon, voit määrittää kyseisen ohjaus objektin **Delayedoutput** -ominaisuudeksi True. Ohjaus objektin **Text** -ominaisuus päivitetään vain, kun pikanäppäimen painallukset on lopetettu. Kaavoja tai sääntöjä ei suoriteta niin monta kertaa, ja sovelluksen suoritus kyky paranee.

## <a name="avoid-using-formupdates-in-rules-and-formulas"></a>Vältä lomakkeen käyttämistä. päivitykset sään töihin ja kaavoihin
Jos viittaat käyttäjän syöte arvoon säännössä tai kaavassa **lomakkeen avulla. päivittää** muuttujan, se iteroi kaikki lomakkeen tieto kortit ja luo tietueen joka kerta. Jos haluat tehostaa sovelluksesi käyttöä, viittaa arvoon suoraan tieto kortista tai ohjaus objektin arvosta.

## <a name="next-steps"></a>Seuraavat vaiheet
Lue [koodaus standardit](https://aka.ms/powerappscanvasguidelines) , joiden avulla voit maksimoida sovelluksen suoritus tehon ja pitää sovelluksia helpommin ylläpidetä.
