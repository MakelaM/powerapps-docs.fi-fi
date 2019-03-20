---
title: InfoPath-lomakkeen muuntaminen pohjaan perustuvaan sovellukseen | Microsoft Docs
description: Aloita InfoPath-lomakkeen muuntaminen PowerAppsiin yleisiä skenaarioita koskevista tiedoista ja ohjeista, joiden avulla näitä luodaan pohjaan perustuvassa sovelluksessa.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/05/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 0ceffa705262e879ee09df2494f71f59bcc2d1b5
ms.sourcegitcommit: 4db9c763455d141a7e1dd569a50c86bd9e50ebf0
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 02/20/2019
ms.locfileid: "57802373"
---
# <a name="transform-your-infopath-form-to-powerapps"></a>InfoPath-lomakkeen muuntaminen PowerAppsiin

Rakennatko upeita InfoPath-luomuksia, jotka haluaisit tarjota vankemmassa ympäristössä?

## <a name="key-advantages-of-powerapps-over-infopath"></a>PowerAppsin tärkeimmät edut InfoPathiin verrattuna

Muiden InfoPath-tehokäyttäjien tapaan olet hyödyntänyt ainutlaatuista osaamistasi jo jonkin aikaa. Ja tuloksena on ollut hienoja lomakkeita. Vaikka olet erittäin tyytyväinen tuottamiisi lomakkeisiin, tunnet hyvin niiden rajoitukset: &quot;klassinen&quot; tuntuma, mobiililaitteissa takkuileva käyttökokemus, epävarmuus käyttökelpoisuuden jatkumisesta ja laatikkoon jumiutuminen, kun yrität yhdistää muihin palveluihin ilman koodausta.

PowerApps-tiimi on kuullut näistä ja monista muista haasteista. Tiimi pyrkii saamaan aikaan paremman käyttökokemuksen ja mahdollistamaan pohjaan perustuvien sovellusten luomisen jo olemassa olevien liiketoiminta- ja teknologiataitojen perusteella. PowerAppsia käyttämällä voit luoda ja ottaa käyttöön asianmukaisia liiketoimintaratkaisuja nopeasti ja koodia kirjoittamatta.

**PowerApps takaa tehokkaan tulevaisuuden**  
PowerApps on SaaS-pilvipalvelu, jossa voit nopeasti rakentaa tehokkaita sovelluksia ja ottaa ne vaivatta käyttöön verkossa, SharePointissa, Dynamics 365:ssä, Teamsissa, Power BI:ssä tai mobiililaitteessa. Koska sovellusten URL-osoitteen jakaminen tekee sovellusten käyttöönotosta helppoa, ne on myös helppo päivittää.

**Omien sovellusten jakaminen**  
Oletko koskaan yrittänyt luoda sovelluksen ja julkaista sen sitten iOS- tai Android-laitteille? Se on monimutkaista. Toisen sovelluksen käyttöönotto ja jo käytössä olevan sovelluksen päivittäminen vaatii käyttäjiltä paljon vaivaa. Ei PowerAppsissa. Käyttäjät vain asentavat PowerApps Mobilen laitteelleen ja kirjautuvat sisään. Siinä kaikki; käyttäjät voivat sen jälkeen käyttää tehokkaita sovelluksia, jotka olet jakanut heille. Jatkossa kaikki sovelluspäivitykset ja käyttäjille jakamasi uudet sovellukset näkyvät käyttäjien laitteilla. Mobiilisovelluksien tarjoaminen ilman laitehallintahässäkkää helpottaa sekä sinun elämääsi että yrityksesi toimintaa huomattavasti.

**Mobiililaitteista puheen ollen**  
PowerAppsin avulla voit hyödyntää käyttäjän mobiililaitteen tehon. Voit käyttää kiihdytystä, kameraa, kompassia, verkkoyhteyden tietoja ja sijaintisignaaleja suoraan sovelluksessa. Se tarjoaa todella paljon mahdollisuuksia tehokkaiden ja käytännöllisten sovellusten luomiseen. Lisäksi kosketustoiminto on PowerAppsissa automaattisesti käytössä, joten sovelluksen luonti ei vaadi lisäkoodausta.

**Karkaa laatikosta**  
InfoPathin avulla käsittelet tavallisesti tietoja, jotka ovat peräisin yhdestä lähteestä. Asiat kuitenkin mutkistuivat, jos haluat päivittää toisesta lähteestä (esimerkiksi toisen sivustokokoelman SharePoint-luettelosta) tai yhdistää ulkoisiin palveluihin. Taustakoodin tapaiset käsitteet voivat aiheuttaa harmaita hiuksia. PowerApps on suunniteltu niin, että voit työstää useita tietolähteitä ja palveluyhteyksiä yhdessä sovelluksessa. Sen [yli 200 liitintä](connections-list.md#all-standard-connectors) tukevat paikallisten ja pilvitietojen yhdistelemistä. Tämä koskee mm. Microsoft Office 365:sta ja Azure-palveluista, kuten Microsoft Flow ja Dynamics 365, peräisin olevia tietoja. Voit myös muodostaa yhteyden useisiin kolmansien osapuolten palveluihin, kuten Dropbox, Google, Salesforce, Slack ja moniin muihin suosittuihin palveluihin.

Nyt voit luoda käyttäjien tarpeisiin venyviä ratkaisuja, jotka eivät rajoitu vain alkuperäiseen tiedonlähteeseen.

## <a name="powerapps-and-sharepoint-even-better-together"></a>PowerApps ja SharePoint – yhdessä vielä parempia

Erinomaisen PowerApps-työkalun avulla parannat SharePoint-käyttökokemusta kahdella tapaa. Voit joko mukauttaa lomakkeet SharePoint-luetteloa varten tai luoda erillisen sovelluksen SharePoint-tietojen käsittelyyn.

**SharePoint-lomakkeen mukauttamisesta** on hyötyä, jos haluat mukauttaa sitä, miten käyttäjät voivat lisätä, tarkastella tai muokata kohteita luettelossa, joita he käyttävät töissään päivittäin. **Mukauta lomakkeet** -kohdan napsauttaminen luo yhden näytön &quot;lomakesovelluksen&quot;, joka vaihtaa tiloja (uusi/muokkaa/näytä) kontekstista riippuen. SharePoint hallitsee näitä sovelluksia. Niiden oikeudet ovat samat kuin muokkauksen ja tarkastelun luettelo-oikeudet.

Jos **luot PowerApps-alustan sovelluksen SharePointista**, sovellus toimii itsenäisesti mobiililaitteessa. Voit myös upottaa sovelluksen SharePoint-sivuun. Tämän napsauttaminen luo kolmeruutuisen sovelluksen (selausluettelo, tietojen näyttäminen ja kohteen luominen/päivittäminen). Näiden sovellusten käyttöoikeus- ja jakomalli ei ole SharePointiin sidottu, vaan sitä voi hallita PowerAppsista.

Nyt kun ymmärrät näiden kahden vaihtoehdon erot, seuraava osio antaa yleiskuvan niiden käytöstä.

## <a name="sharepoint-forms"></a>SharePoint-lomakkeet

PowerApps- ja SharePoint-tiimi ovat luoneet yhteistyönä uuden mukautustavan, jota voit käyttää SharePointissa. Muiden InfoPath-kehittäjien tavoin opettelit InfoPathin luultavasti SharePointin käyttöä varten. SharePoint on kätevä, mutta sen oletuslomakkeet ovat hieman hidasliikkeisiä eikä mukautuksia ja liiketoimintalogiikkaa voi tehdä ilman InfoPathia. Niin asiat tehtiin ennen vanhaan.

PowerAppsilla voit nyt mukauttaa luettelolomakkeet natiivitoimintoina. Niin tehdessäsi valjastat kaiken PowerAppsin voiman. Seuraavassa näyttökuvassa on esimerkki PowerApps-lomakkeesta, johon on upotettu Power BI -raportti. Koko ratkaisu luotiin alle 15 minuutissa.

![SharePoint-integrointi](./media/transform-infopath/sharepoint-integration.png)

Toinen tärkeä PowerApps-ominaisuus on se, miten samasta lomakkeesta voi helposti yhdistää toiseen SharePoint-sivustokokoelmaan tai eri ympäristöön. Haluatko esimerkiksi luoda lomakkeen, joka näyttää ja päivittää samanaikaisesti sekä SharePoint Onlinen että paikallisen SharePoint-ympäristön tietoja? Ei huolta. Jos asennat [paikallisen tietoyhdyskäytävän](gateway-management.md), voit jo muutaman minuutin kuluttua yhdistää PowerAppsin, Power BI:n, Microsoft Flow’n ja Azure Logic Appsin paikallisiin tietoihisi. Palomuurin sääntöihin ei tarvitse tehdä muutoksia. Voit ottaa askeleen pidemmälle yhdistämällä sovelluksen Microsoft Flow’hun.

## <a name="a-standalone-sharepoint-app"></a>Erillinen SharePoint-sovellus

Käytä tätä tekniikkaa, jos haluat pelkän luettelolomakekokemuksen päivittämisen sijaan luoda SharePoint-tietoihin pohjautuvan kokonaisen, erillisen sovelluksen. Tämä on myös paras tapa päästä alkuun PowerApps-alustan opettelussa ja montaa tiedonlähdettä käyttävien sovellusten luomisessa.

Aloita seuraavasti:

1. Avaa SharePoint-luettelo, josta haluat luoda sovelluksen.
1. Valitse valikkoriviltä **PowerApps** ja valitse sitten **Luo sovellus**.
1. Anna sovellukselle nimi ja valitse sitten **Luo**.

PowerApps luo sovelluksen, jota voit itse mukauttaa.

Käytä ensimmäisessä sovelluksessa yksinkertaista mukautettua luetteloa, jossa on vain muutama erityyppinen kenttä. Näin rakennat vahvan pohjan, eikä uuden asian opettelu tunnu ylivoimaisen vaikealta. Ei huolta – pääset pian ammattilaisen tasolle ja voit alkaa luoda monimutkaisia sovelluksia. Jos tarvitset lisäapua ensimmäisen sovelluksen luomiseen, tutustu näihin [ohjeisiin](app-from-sharepoint.md#generate-an-app-from-within-sharepoint-online) tai katso tämä yhteisön [video](https://youtu.be/BnYe_7fpZRM). Seuraavat esimerkit esittelevät, miten yleisimmät InfoPath-tehtävät tehdään PowerAppsissa. Ne kaikki perustuvat yksinkertaiseen SharePoint-luettelosovellukseen.

## <a name="how-do-you-do-that-with-powerapps"></a>Sama PowerAppsissa

Nyt ymmärrät peruskäsitteet, ja voimme sukeltaa syvemmälle. Olet luonut ensimmäisen sovelluksesi. Tässä osiossa neuvotaan, miten sovellat joitain yleisiä InfoPath-käsitteitä PowerAppsissa.

**Kentän piilottaminen, näyttäminen tai lukitseminen arvon perusteella**  
Onnistuneet lomakkeet toteuttavat usein vahvaa liiketoimintalogiikkaa esimerkiksi muuttamalla kentän tilaa arvon tai toiminnon mukaan. PowerAppsissa voit määrittää ohjausobjektin **DisplayMode**-ominaisuudeksi **Muokkaa** tai **Näytä**. Tila ilmaisee, voiko käyttäjä muuttaa kenttää. Voit myös käyttää yksinkertaista, ehdollista **If**-kaavaa. Valitse ensin kortti, jota haluat muokata, ja valitse sitten lukkokuvake. Tämä vaihe avaa kortin niin, että voit muuttaa arvoa.

![Tietokorttien piilottaminen, näyttäminen ja lukitseminen](./media/transform-infopath/hide-show-lock.png)

Siirry oikeanpuoleisessa ruudussa **DefaultMode**-ominaisuuteen niin, että voit muokata sitä.

![If else -lauseilmaisut](./media/transform-infopath/if-else-statement.png)

Käytä tässä esimerkissä **If**-kaavaa:

```If(ThisItem.Color = "Blue", DisplayMode.View, DisplayMode.Edit)```

Tämä kaava ilmoittaa, että jos nykyinen kohteen **väri**-kenttä on **Sininen**, **Eläin**-kenttä on vain luku -tilassa. Muussa tapauksessa kenttää voi muokata.

Jos haluat piilottaa sen sijaan, että se muunnetaan vain luku -tilaan, lisää samanlainen funktio **DisplayMode**-kohdan yllä olevaan **Näkyvissä**-ominaisuuteen.

Voit myös kokeilla esimerkiksi sitä, että hyväksymispainike näytetään vain jos käyttäjän sähköpostiosoite vastaa hyväksyjän sähköpostiosoitetta. (Vihje: Käytä **User(). Lähetä** pääset käsiksi nykyisen käyttäjän sähköpostiosoitteeseen.) Voit tallentaa hyväksyjän sähköpostiosoitteen **YourDataCard**-kohtaan ja asettaa painikkeen **Näkyvissä**-ominaisuuden arvoksi seuraavan kaavan:

```If( YourDataCard.Text = User().Email, true, false )```

**Ehdollinen muotoilu**  
Samaan tapaan kuin edellisessä kentän piilottavassa esimerkissä voit antaa käyttäjille visuaalista palautetta. Ehkä haluat korostaa tekstin punaisella, jos annettu arvo ei ole hyväksytyllä alueella, tai ehkä haluat muuttaa latauspainikkeiden tekstin ja värin, kun tiedosto on ladattu. Voit tehdä molemmat käyttämällä **If**-funktiota esim. **Väri**- tai **Näkyvissä**-ominaisuuksissa.

Voit esimerkiksi käyttää **If**-funktiota yhdessä [IsMatch](functions/function-ismatch.md)-funktion kanssa, kun haluat vaihtaa sähköpostiosoitekentän tekstin värin punaiseksi, jos käyttäjä ei kirjoittanut syöteruutuun kelvollisen muotoista sähköpostiosoitetta. Voit tehdä tämän asettamalla **TextInput1**-kohdan (johon käyttäjä kirjoittaa sähköpostiosoitteen) **Väri**-arvoksi seuraavan kaavan:

```If( IsMatch(TextInput1.Text, Email), Black, Red )```

**IsMatch** tukee lukuisia erilaisia esimääritettyjä kuvioita, kuten Email, mutta voit luoda myös oman kuvion. Lisätietoja ehdollisesta muotoilusta on tässä [yhteisön videossa](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Conditional-Formatting-and-Popups/m-p/84962).

**Roolipohjaisen suojauksen käyttöönotto**  
Ensimmäiseksi kannattaa harkita [DataSourceInfo](functions/function-datasourceinfo.md)-funktiota. Tietolähteestä saatavat tiedot vaihtelevat, mutta usein voit tarkistaa tällä kaavalla, onko käyttäjällä tietojen muokkausoikeutta (korvaa *YourDataSource* oman tietolähteesi nimellä):

```DataSourceInfo( YourDataSource, DataSourceInfo.EditPermission )```

Tällä funktiolla lomake tai painike näytetään vain, jos käyttäjällä on muokkausoikeus. [DataSourceInfo](functions/function-datasourceinfo.md)-funktion ohjeissa on täydellinen luettelo tiedoista, joita siinä voi kysellä.

Jos haluat käyttää ActiveDirectory-ryhmiä sovelluksen painikkeiden tai lomakkeiden käytön hallintaan, sinun on perehdyttävä asiaan syvemmin. Hyödynnä PowerAppsin joustavuutta ja luo oma liittimesi Microsoft Graph -ohjelmointirajapinnan avulla. Jos se kuulostaa vaikealta, katso vaiheittaiset ohjeet tästä [blogikirjoituksesta](https://powerapps.microsoft.com/blog/implementing-role-based-permission/).

**Sähköpostiviestin lähettäminen sovelluksesta**  
Voit lähettää sähköpostiviestin PowerAppsista monella tavalla. Helpointa on käyttää Office 365 Outlook -liitintä. Tämän liittimen avulla voit lähettää sovelluksesta viestin omana itsenäsi. Voit lisäksi vastaanottaa sähköpostiviestejä ja muita sähköpostisi kanssa vuorovaikutuksessa olevia tehtäviä. Lue sähköpostin lähettämisen [ohjeet](connections/connection-office365-outlook.md) tai katso tämä yhteisön [video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Send-an-email-from-PowerApps/m-p/74349).

Voit lähettää monimutkaisemman viestin (esimerkiksi osana SharePointin hyväksynnän työnkulkua) käyttämällä Microsoft Flow’ta ja yhdistämällä sovelluksen luomaasi työnkulkuun. Kun yhdistät sovelluksen Microsoft Flow’hun, valjastat käyttöösi työnkulkuohjelman täydet hevosvoimat. Microsoft Flow on PowerAppsin tavoin erittäin hyvin yhteydessä ulkoisiin tietoihin ja palveluihin. Lisätietoja Microsoft PowerAppsin ja Microsoft Flow’n yhdistämisestä on näissä [ohjeissa](using-logic-flows.md).

Jos et vieläkään ole löytänyt sopivaa sähköpostivaihtoehtoa, voit hyödyntää PowerApps-liittimiä palveluille Benchmark Email, Gmail, MailChimp, Outlook.com, SendGrid tai SMTP. Yhdistettävyys kuuluu PowerAppsin parhaisiin puoliin.

**Työnkulut**  
Yrityssovelluksista ja liiketoimintalogiikasta puhuttaessa tulee aina jossain vaiheessa esiin työnkulkuohjelma. Hyvä uutinen on se, että PowerApps-tiimi ei yrittänyt keksiä pyörää uudelleen ja luoda uutta työnkulkuohjelmaa. Sen sijaan he antoivat käyttöösi tehokkaan Microsoft Flow -palveluun yhdistävän liittimen. Nyt voit automatisoida prosesseja ja tehtäviä yli [200 erilaisella palvelulla](https://flow.microsoft.com/connectors/) tämän helppokäyttöisen työnkulkupalvelun kautta. Lisätietoja Microsoft PowerAppsin ja Microsoft Flow’n yhdistämisestä on näissä [ohjeissa](using-logic-flows.md).

**Muuttujat PowerAppsissa**  
Muuttujien ajatellaan yleensä kuuluvan ratkaisujen luomiseen. PowerApps tarjoaa useita muuttujatyyppiä, mutta käyttää niitä vain silloin, kun se on tarpeen. Ajattele, että tiedon noutamisen, muuttujaan tallentamisen ja siihen muuttujaan viittaamisen sijaan voisit vain viitata suoraan tietoon. Ymmärrät mallin paremmin, jos vertaat sitä Exceliin. Excelissä summa ei ole muuttuja, vaan muiden kenttien summa. Joten jos haluat käyttää sen arvoa muualla laskentataulukossa, määrität solun, jossa summa laskettiin. [Ohjeissa](working-with-variables.md) on selitetty tämä kaikki erinomaisella tavalla. Pidä mieli avoinna uusille ajatustavoille.

Jos silti tarvitset muuttujaa (tällaisia tilanteita riittää), nämä ohjeet auttavat ymmärtämään erilaisia vaihtoehtoja. Muista, että PowerAppsissa muuttujia ei tarvitse määrittää. Muuttuja on helppo luoda käyttämällä funktiota nimen ja tallennettavan arvon määrittämiseen. Voit tarkastella luomiasi muuttujia valitsemalla **Muuttujat** **Näkymä**-välilehdeltä. Muuttujat säilytetään muistissa ja niiden arvot häviävät, kun suljet sovelluksen. Voit luoda seuraavantyyppisiä muuttujia:

- Yleiset muuttujat ovat tutuimpia. Voit määrittää yleisen muuttujan arvon [Set](functions/function-set.md)-funktiolla ja valitsemalla koko sovelluksen sen käyttöalueeksi:

    ```Set( YourVariable, YourValue )```

    Tämän jälkeen voit viitata *OmaMuuttuja*-muuttujaan sen nimellä kaikkialla sovelluksessasi.

- Kontekstimuuttujat näkyvät vain sillä ruudulla, jolla ne on määritetty. Kun poistut ruudusta, ne nollautuvat. Niillä tallennetaan usein edelliseltä sivulta siirrettyjä tietoja tai seurataan, onko lomake lähetetty. Voit määrittää kontekstimuuttujan [UpdateContext](functions/function-updatecontext.md)-funktiolla, kuten seuraavassa esimerkissä:

    ```UpdateContext( { Submitted: "true" } )```

    Tässä esimerkissä muuttujan arvoksi, jonka nimi on **Lähetetty**, annetaan **tosi**. Voit esimerkiksi liittää tämän kaavan lähetyspainikkeen **OnSelect**-ominaisuuteen, jolloin voit varmistaa tietojen lähetyksen ja muuttaa kaikki kentät vain luku -kentiksi.

- Kokoelmiin tallennetaan tietotaulukoita, joita voi päivittää yksittäin. Käytä [Kerää](functions/function-clear-collect-clearcollect.md)-toimintoa luodaksesi ostoskorin, jossa käyttäjä merkitsee lähetettäviä SharePoint-kohteita. Katso yhteisön [video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Learn-about-PowerApps-Collections/m-p/89180), joka näyttää konseptin käytännön toteutuksen.

**Avattavat johdannaisvalikot**  
Avattavat johdannaisvalikot ovat erittäin hyödyllisiä, koska voit esimerkiksi suodattaa avattavan valikon vaihtoehdot edellisessä avattavassa valikossa valitun arvon perusteella. PowerAppsissa ne luodaan usein määrittämällä sovellukselle kaksi tietolähdettä. Ensimmäisessä tietolähteessä ovat parhaillaan tarkasteltavat ja päivitettävät tiedot ja toisessa säilytetään arvoja, joilla haluttu johdannaistoiminto luodaan. Tässä kuviossa näytetään esimerkki toisesta tietolähteestä ja sen vaihtoehdoista.

![Avattavat johdannaisvalikot](./media/transform-infopath/cascading-dropdowns.png)

Tässä esimerkissä voit lisätä avattavan valikon, jonka nimi on **ddSelectType** ja määrittää sen **Kohteet**-ominaisuudeksi seuraavan arvon:

```Distinct( Impacts, Title )```

Avattava valikko näyttää vain Kustannukset-, Ohjelman vaikutus- ja Ajoitus-vaihtoehdot. Sen jälkeen voit lisätä toisen avattavan valikon ja määrittää sen **Kohteet**-ominaisuudeksi seuraavan kaavan:

```Filter( Impacts, ddSelectType.Selected.Value in SCategory )```

Tuloksena on avattavia johdannaisvalikkoja. Lisätietoja, tutustu PowerApps-tiimin julkaisussa [SharePoint: Avattavat Johdannaisvalikot in 4 Easy Steps!](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/SharePoint-Cascading-Dropdowns-in-4-Easy-Steps/ba-p/16248) ja tässä [yhteisön videossa](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Cascading-Dropdown/m-p/92813). Äläkä huoli, voit tehdä sen aivan yhtä helposti ilman SharePointia.

**Älä luo yhtä jättisovellusta**  
PowerAppsin avulla voit kutsua sovelluksia toisista sovelluksista. Voit siis luoda ryhmän sovelluksia, jotka kutsuvat toisiaan ja jopa siirtävät tietoa toisilleen. Kehittäminen on siten helpompaa ja voit jättää valtavat, juuri ja juuri koossa pysyvät InfoPath-lomakkeet taaksesi.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun olet omaksunut PowerAppsin ja edellä kerrotut tiedot, olet valmis valloittamaan maailman sovellus kerrallaan. Alla on käteviä linkkejä, kuten PowerAppsin yhteisösivuston linkki, jotka auttavat sinua jatkossa. Osallistu yhteisön keskustellun ja kasvata osaamistasi paljon nopeammin kuin yksin puurtamalla.

[**Kaavahakemisto**](formula-reference.md) – Oletusfunktioiden selaaminen on erinomainen tapa hankkia lisäinspiraatiota.

[**PowerAppsin yhteisö**](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) – Tutustu esimerkkeihin, keskustele muiden kanssa, kysy kysymyksiä ja vastaa muiden kysymyksiin. Auta PowerAppsin yhteisöä kasvamaan.
