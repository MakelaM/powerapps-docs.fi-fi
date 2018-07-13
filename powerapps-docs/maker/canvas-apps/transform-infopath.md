---
title: InfoPath-lomakkeiden muuntaminen PowerAppsiin | Microsoft Docs
description: Aloita InfoPath-lomakkeiden muuntaminen PowerAppsiin opettelemalla yleisimmät InfoPath-skenaariot ja miten niitä voi luoda PowerAppsissa.
author: richardriley99
manager: kvivek
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/05/2018
ms.author: rriley
ms.openlocfilehash: 74445d4a9398afe00407e7b1a1eae5b7d773dd22
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39020396"
---
# <a name="transform-your-infopath-forms-to-powerapps"></a>InfoPath-lomakkeiden muuntaminen PowerAppsiin

Rakennatko upeita InfoPath-luomuksia, jotka haluaisit tarjota vankemmassa ympäristössä?

## <a name="key-advantages-of-powerapps-over-infopath"></a>PowerAppsin tärkeimmät edut InfoPathiin verrattuna

Olet todennäköisesti muiden InfoPath-tehokäyttäjien tapaan hyödyntänyt ainutlaatuista osaamistasi jo jonkin aikaa. Ja tuloksena on ollut hienoja lomakkeita. Vaikka olet erittäin tyytyväinen tuottamiisi lomakkeisiin, tunnet hyvin niiden rajoitukset: &quot;klassinen&quot; tuntuma, mobiililaitteissa takkuileva käyttökokemus, epävarmuus käyttökelpoisuuden jatkumisesta ja laatikkoon jumiutuminen, kun yrität yhdistää muihin palveluihin ilman koodausta.

Microsoft PowerApps -tiimi kuuli nämä ja monen muun käyttäjä kohtaamat haasteet. Se paiski ankarasti töitä sen eteen, että saat paremman käyttökokemuksen PowerAppsissa. Tavoitteena on, että voit luoda sovelluksia liiketoimintaasi ja nykyistä teknologista osaamistasi hyödyntämällä. PowerAppsilla voit siten luoda ja ottaa käyttöön asianmukaisia liiketoimintaratkaisuja nopeasti ja koodia kirjoittamatta.

**PowerApps takaa tehokkaan tulevaisuuden**  
PowerApps on SaaS-pilvipalvelu, jossa voit nopeasti rakentaa erittäin toimivia sovelluksia ja ottaa ne vaivatta käyttöön verkossa, SharePointissa, Dynamics 365:ssä, Teamsissa, Power BI:ssä tai mobiililaitteessa. Ja koska sovellukset on helppo ottaa käyttöön (jakamalla julkaistun sovelluksen URL-osoite), ne on myös helppo päivittää.

**Omien sovellusten jakaminen**  
Oletko koskaan yrittänyt rakentaa sovellusta ja saada sen julkaistuksi Google Play- tai Apple Store -sovelluskaupassa? Se on monimutkaista. Haasteellisuus kasvaa, jos haluat ottaa käyttöön toisen sovelluksen tai päivittää nykyistä. Käyttäjien on käytävä läpi todella monia vaiheita. Mutta ei PowerAppsissa. Käyttäjät asentavat Microsoft PowerApps -sovelluksen omasta sovelluskaupastaan ja kirjautuvat sitten sisään Microsoft-tilin käyttäjätunnuksella ja salasanalla. Voilà, heidän käytössään ovat kaikki erittäin toimivat sovellukset, jotka olet heidän kanssaan jakanut. Jatkossa kaikki sovelluspäivitykset ja käyttäjille jakamasi uudet sovellukset näkyvät käyttäjien laitteissa. Mobiilisovelluksien tarjoaminen ilman laitehallintahässäkkää helpottaa sinun elämääsi ja yrityksesi toimintaa huomattavasti.

**Mobiililaitteista puheen ollen**  
PowerAppsin avulla voit hyödyntää käyttäjän mobiililaitteen tehon. Voit käyttää kiihdytystä, kameraa, kompassia, yhteystietoja ja sijaintisignaaleja suoraan sovelluksessa. Se tarjoaa todella paljon mahdollisuuksia tehokkaiden ja käytännöllisten sovellusten luomiseen. Lisäksi kosketustoiminto on PowerAppsissa tietenkin automaattisesti käytössä, joten sovelluksen luonti ei vaadi lisäkoodausta.

**Karkaa laatikosta**  
InfoPathissa työstettiin yleensä yhden tietolähteen tietoja. Jos kuitenkin halusit tehdä päivityksiä jossain muualla (esimerkiksi toisen sivustokokoelman SharePoint-luettelossa) tai yhdistää ulkoisiin palveluihin, asiat mutkistuivat ja erillisen koodin kaltaiset konseptit alkoivat valvottaa öisin. Ei PowerAppsissa. Se on suunniteltu niin, että voit työstää useita tietolähteitä ja palveluyhteyksiä yhdessä sovelluksessa. Tällä hetkellä käytössä on [yli 150 liitintä](https://docs.microsoft.com/powerapps/connections-list#all-connectors), joiden avulla voi yhdistää paikallisia ja pilvitietoja, Microsoft Office 365:n ja Azuren palveluja (esim. Flow ja Dynamics 365) ja monia ulkopuolisten palveluntarjoajien palveluja, kuten Dropbox, Google, Salesforce ja Slack. Nyt voit luoda käyttäjien tarpeisiin venyviä ratkaisuja, jotka eivät rajoitu vain alkuperäiseen tiedonlähteeseen.

## <a name="powerapps-and-sharepoint-even-better-together"></a>PowerApps ja SharePoint – yhdessä vielä parempia

Erinomaisen PowerApps-työkalun avulla parannat SharePoint-käyttökokemusta kahdella tapaa. Voit joko mukauttaa lomakkeet SharePoint-luetteloa varten tai luoda erillisen sovelluksen SharePoint-tietojen käsittelyyn.

**SharePoint-lomakkeen mukautus** on kätevää, jos käyttäjät käyttävät luetteloa päivittäisessä työssään, mutta haluat myös mukauttaa, miten käyttäjät lisäävät, tarkastelevat ja muokkaavat SharePoint-luettelon kohteita. **Mukauta lomakkeet** -kohdan napsauttaminen luo yhden näytön &quot;lomakesovelluksen&quot;, joka vaihtaa tiloja (uusi/muokkaa/näytä) kontekstista riippuen. SharePoint hallitsee näitä sovelluksia. Niiden oikeudet ovat samat kuin muokkauksen ja tarkastelun luettelo-oikeudet.

Jos **luot PowerApps-alustan sovelluksen SharePointista**, sovellus toimii itsenäisesti mobiililaitteessa. Se voidaan myös upottaa SharePoint-sivuun. Tämän napsauttaminen luo kolmenäyttöisen sovelluksen (luettelonäkymä, uusi lomake / muokkaa lomaketta ja näytä lomake).  Näiden sovellusten käyttöoikeus- ja jakomalli ei ole SharePointiin sidottu, vaan sitä voi hallita PowerAppsista.

Nyt kun ymmärrät näiden kahden vaihtoehdon erot, seuraava osio antaa yleiskuvan niiden käytöstä.

## <a name="sharepoint-forms"></a>SharePoint-lomakkeet

PowerApps- ja SharePoint-tiimi ovat luoneet yhteistyönä uuden mukautustavan, jota voit käyttää SharePointissa.  Muiden InfoPath-kehittäjien tavoin opettelit InfoPathin luultavasti SharePointin käyttöä varten. Vaikka SharePoint on kätevä, sen oletuslomakkeet ovat hieman hidasliikkeisiä ja mukautuksia ja liiketoimintalogiikkaa ei voi tehdä ilman InfoPathia. Niin asiat tehtiin ennen vanhaan.

PowerAppsilla voit nyt mukauttaa luettelolomakkeet natiivitoimintoina. Niin tehdessäsi valjastat kaiken PowerAppsin voiman. Seuraavassa näyttökuvassa on esimerkki PowerApps-lomakkeesta, johon on upotettu Power BI -raportti.  Koko ratkaisu luotiin alle 15 minuutissa.

![SharePoint-integrointi](./media/transform-infopath/sharepoint-integration.png)

Toinen tärkeä PowerApps-ominaisuus on se, miten samasta lomakkeesta voi helposti yhdistää toiseen SharePoint-sivustokokoelmaan tai eri ympäristöön. Haluatko esimerkiksi luoda lomakkeen, joka näyttää ja päivittää samanaikaisesti sekä SharePoint Onlinen että paikallisen SharePoint-ympäristön tietoja? Ei huolta. Asenna [paikallinen tietoyhdyskäytävä](https://docs.microsoft.com/powerapps/gateway-management), niin voit jo muutaman minuutin kuluttua yhdistää PowerAppsin, Power BI:n, Microsoft Flow’n ja Azure Logic Appsin paikallisiin tietoihisi. Ei vaadi palomuurisääntöjen muuttamista. Voit lisätä toimintoja entisestään yhdistämällä tämän sovelluksen Microsoft Flow’hun.

## <a name="a-standalone-sharepoint-app"></a>Erillinen SharePoint-sovellus

Käytä tätä tekniikkaa, jos haluat pelkän luettelolomakekokemuksen päivittämisen sijaan luoda SharePoint-tietoihin pohjautuvan kokonaisen, erillisen sovelluksen. Tämä on myös paras tapa päästä alkuun PowerApps-alustan opettelussa ja montaa tiedonlähdettä käyttävien sovellusten luomisessa.

Aloita siirtymällä SharePoint-luetteloon, jota haluat käyttää. Noudata sitten seuraavia ohjeita:

1. Valitse valikkoriviltä PowerApps.
2. Valitse Luo sovellus.
3. Anna nimi.
4. Valitse Luo.

PowerApps luo oletussovelluksen, jota voit mukauttaa.

Aloita yksinkertaisesti. Käytä ensimmäisessä sovelluksessa yksinkertaista mukautettua luetteloa, jossa on vain muutama erityyppinen kenttä. Näin rakennat vahvan pohjan, eikä uuden asian opettelu tunnu ylivoimaisen vaikealta. Ei huolta – pääset pian ammattilaisen tasolle ja voit alkaa luoda monimutkaisia sovelluksia.  Jos tarvitset lisäapua ensimmäisen sovelluksen luomiseen, tutustu näihin [ohjeisiin](https://docs.microsoft.com/powerapps/generate-app-from-sharepoint-list-interface) tai katso tämä yhteisön [video](https://youtu.be/BnYe_7fpZRM). Seuraavat esimerkit esittelevät, miten yleisimmät InfoPath-tehtävät tehdään PowerAppsissa. Ne kaikki perustuvat yksinkertaiseen SharePoint-luettelosovellukseen.

# <a name="how-do-you-do-that-with-powerapps"></a>Sama PowerAppsissa

Nyt ymmärrät peruskäsitteet, ja voimme sukeltaa syvemmälle. Olet luonut ensimmäisen sovelluksesi ja seuraava osio neuvoo, miten sovellat joitain yleisiä InfoPath-käsitteitä PowerAppsissa.

**Kentän piilottaminen, näyttäminen tai lukitseminen arvon perusteella**  
Onnistuneen lomakkeen luomiseen tarvitaan yleensä vahvaa liiketoimintalogiikkaa ja sen toteuttamiskykyä. Yksi tapa on muuttaa kentän tilaa arvon tai toiminnon perusteella. PowerAppsissa voit valita ohjausobjektin ja määrittää sen DisplayMode-ominaisuudeksi Muokkaa tai Näytä. Tila ilmaisee, voiko käyttäjä muuttaa kenttää. Toinen tapa on käyttää yksinkertaista, ehdollista If-kaavaa. Valitse ensin muokattava selite ja avaa kortti napsauttamalla lukkokuvaketta, jotta voit muuttaa sen arvoa.

![Tietokorttien piilottaminen, näyttäminen ja lukitseminen](./media/transform-infopath/hide-show-lock.png)

Vieritä kortin oikeassa reunassa kortin loppuun ja muokkaa DefaultMode-ominaisuutta.

![If else -lauseilmaisut](./media/transform-infopath/if-else-statement.png)

Käytä tässä esimerkissä If-lausetta. If(ThisItem.Color = &quot;Blue&quot;, DisplayMode.View, DisplayMode.Edit) Tämä lause ilmaisee, että jos nykyisten kohteiden värikenttä on sininen, eläinkenttää voi vain tarkastella. Jos se ei ole sininen, kenttää voi muokata.

Jos et halua näyttää korttia ollenkaan, voit lisätä samantapaisen funktion DisplayMode-ominaisuuden yläpuolella olevaan Visible-kenttään.

Tässä tapauksessa voisi myös piilottaa hyväksymispainikkeen, joka näkyy vain, jos käyttäjän sähköpostiosoite on sama kuin hyväksyjän sähköpostiosoite. Vihje: Kaavalla User().Email pääset käsiksi nykyisen käyttäjän sähköpostiosoitteeseen. Joten voit määrittää painikkeen Visible-arvoksi kaavan If(YourDataCard.Text = User().Email, true, false). Siinä DataCard on kortti, jossa hyväksyjän sähköpostiosoitetta säilytetään.

**Ehdollinen muotoilu**  
Samaan tapaan kuin edellisessä kentän piilottavassa esimerkissä voit antaa käyttäjille visuaalista palautetta. Ehkä haluat korostaa tekstin punaisella, jos annettu arvo ei ole hyväksytyllä alueella, tai ehkä haluat muuttaa latauspainikkeiden tekstin ja värin poistopainikkeeksi, kun tiedosto on ladattu. Kaikki nämä toiminnot voi suorittaa funktioilla (esim. ehdollinen If) värin ja näkyvyyden tapaisissa ominaisuuskentissä.

Voit esimerkiksi käyttää If-funktiota yhdessä [IsMatch](https://docs.microsoft.com/powerapps/functions/function-ismatch)-funktion kanssa, kun haluat vaihtaa sähköpostiosoitekentän tekstin värin punaiseksi, jos käyttäjä ei kirjoittanut syöteruutuun kelvollisen muotoista sähköpostiosoitetta. Toteuta se määrittämällä TextInput1:n väriarvoksi If(IsMatch(TextInput1.Text, Email), Black, Red). TextInput1 on tässä tapauksessa kenttä, johon käyttäjä kirjoittaa sähköpostiosoitteen. IsMatch tukee lukuisia erilaisia esimääritettyjä kuvioita, kuten Email, mutta mahdollistaa myös oman kuvion luomisen. Lisätietoja ehdollisesta muotoilusta on tässä [yhteisön videossa](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Conditional-Formatting-and-Popups/m-p/84962).

**Roolipohjaisen suojauksen käyttöönotto**  
Ensimmäiseksi kannattaa harkita [DataSourceInfo](https://docs.microsoft.com/powerapps/functions/function-datasourceinfo)-funktiota. Tietolähteestä saatavat tiedot riippuvat tietolähteestä, mutta usein voit tarkistaa kaavalla DataSourceInfo(YourDataSource, DataSourceInfo.EditPermission), onko käyttäjällä tietojen muokkausoikeutta. Korvaa YourDataSource tietolähteen nimellä. Tällä funktiolla näytät lomakkeen tai painikkeen vain, jos käyttäjällä on muokkausoikeus. DataSourceInfo-funktion ohjeissa on täydellinen luettelo tiedoista, joita siinä voi kysellä.

Jos haluat käyttää Active Directory -ryhmiä sovelluksen painikkeiden tai lomakkeiden käytön hallintaan, sinun on perehdyttävä asiaan syvemmin. Teet sen hyödyntämällä PowerAppsin joustavuutta ja luomalla oman liittimen Microsoft Graph -ohjelmointirajapinnan avulla. Tämä saattaa kuulostaa hyvin vaikealta, mutta saatavilla on vaiheittaiset [ohjeet](https://powerapps.microsoft.com/blog/implementing-role-based-permission/).

**Sähköpostiviestin lähettäminen sovelluksesta**  
PowerAppsista voi lähettää sähköpostiviestin monella tapaa. Helpointa on käyttää Office 365 Outlook -liitintä. Tämän liittimen avulla voit lähettää sovelluksesta sähköpostiviestin omana itsenäsi. Voit lisäksi vastaanottaa sähköpostiviestejä ja muita sähköpostisi kanssa vuorovaikutuksessa olevia tehtäviä. Lue sähköpostin lähettämisen [ohjeet](https://docs.microsoft.com/powerapps/connections/connection-office365-outlook) tai katso tämä yhteisön [video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Send-an-email-from-PowerApps/m-p/74349).

Jos haluat lähettää monimutkaisemman sähköpostiviestin, esimerkiksi luomalla SharePointin hyväksymistyönkulun hyväksymisketjun, kannattaa luoda Microsoft Flow -työnkulku ja yhdistää sovellus siihen. Kun yhdistät sovelluksen Microsoft Flow’hun, valjastat käyttöösi työnkulkuohjelman täydet hevosvoimat. Microsoft Flow on PowerAppsin tavoin erittäin hyvin yhteydessä ulkoisiin tietoihin ja palveluihin. Lisätietoja Microsoft PowerAppsin ja Microsoft Flow’n yhdistämisestä on näissä [ohjeissa](https://docs.microsoft.com/powerapps/using-logic-flows).

Jos et vieläkään ole löytänyt sopivaa sähköpostivaihtoehtoa, voit hyödyntää PowerApps-liittimiä palveluille Benchmark Email, Gmail, MailChimp, Outlook.com, SendGrid tai SMTP. Yhdistettävyyshän kuuluu PowerAppsin parhaisiin puoliin.

**Työnkulut**  
Yrityssovelluksista ja liiketoimintalogiikasta puhuttaessa tulee aina jossain vaiheessa esiin työnkulkuohjelma. Hyvä uutinen on se, että PowerApps-tiimi ei yrittänyt keksiä pyörää uudelleen ja luoda uutta työnkulkuohjelmaa. Sen sijaan he antoivat käyttöösi tehokkaan Microsoft Flow -palveluun yhdistävän liittimen. Nyt voit automatisoida prosesseja ja tehtäviä yli [200 erilaisella palvelulla](https://flow.microsoft.com/connectors/) tämän helppokäyttöisen työnkulkupalvelun kautta. Lisätietoja Microsoft PowerAppsin ja Microsoft Flow’n yhdistämisestä on näissä [ohjeissa](https://docs.microsoft.com/powerapps/using-logic-flows).

**Muuttujat PowerAppsissa**  
Muuttujien ajatellaan yleensä kuuluvan ratkaisujen luomiseen. Vaikka PowerApps tarjoaa kolmentyyppisiä muuttujia, niitä kannattaa käyttää vain pakkotilanteissa. Ajattele, että tiedon noutamisen, muuttujaan tallentamisen ja siihen muuttujaan viittaamisen sijaan voisit vain viitata suoraan tietoon. Asia on helpoin selittää Excelillä. Excelin summa ei ole muuttuja, vaan muiden kenttien summa. Joten jos haluat käyttää sen arvoa muualla laskentataulukossa, anna kenttä, jossa summa laskettiin. [Ohjeissa](https://docs.microsoft.com/powerapps/working-with-variables) on selitetty tämä kaikki erinomaisella tavalla. Pidä mieli avoinna uusille ajatustavoille.

Jos silti tarvitset muuttujia (tällaisia tilanteita riittää), nämä ohjeet auttavat ymmärtämään erilaisia vaihtoehtoja. Muista, että PowerAppsissa muuttujia ei tarvitse määrittää. Muuttuja on helppo luoda määrittämällä nimi ja tallennettavan arvo jollain funktiolla. Jos haluat tarkastella luomiasi muuttujia, napsauta valikkorivillä Näytä ja valitse sitten Muuttujat. Muuttujat säilytetään muistissa ja niiden arvot häviävät, kun suljet sovelluksen. Muuttujia on kolmentyyppisiä:

- Yleiset muuttujat ovat tutuimpia. Voit määrittää muuttujan arvon [Set](https://docs.microsoft.com/powerapps/functions/function-set)-funktiolla, minkä jälkeen se on käytettävissä koko sovelluksessa. Tässä käytämme esimerkkitapausta Set(OmaMuuttuja, OmaArvo). Tämän jälkeen voit viitata OmaMuuttuja-muuttujaan sen nimellä kaikkialla sovelluksessasi.
- Kontekstimuuttujat näkyvät ruudulla vain, jos ne on määritetty. Kun poistut näytöstä, ne nollautuvat. Niillä tallennetaan usein edelliseltä sivulta siirrettyjä tietoja tai seurataan, onko lomake esimerkiksi lähetetty. [UpdatedContext](https://docs.microsoft.com/powerapps/functions/function-updatecontext)-funktion yleinen käyttötapa UpdateContext( { Lähetetty: "true" } ) määrittää Lähetetty-muuttujan arvoksi true. Voit esimerkiksi liittää sen osaksi sivun lähetyspainiketta, jolloin voit varmistaa tietojen lähetyksen ja muuttaa kaikki kentät vain luku -kentiksi. Huomaa: Käytät merkkiä ":". Kokoelmiin tallennetaan tietotaulukoita, joita voi päivittää yksittäin. Tutustu ensimmäiseksi [Collect](https://docs.microsoft.com/powerapps/functions/function-clear-collect-clearcollect)-funktioon. Voit esimerkiksi luoda sillä ostoskorin, jossa käyttäjä merkitsee lähetettäviä SharePoint-kohteita. Katso yhteisön [video](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/Learn-about-PowerApps-Collections/m-p/89180), joka näyttää konseptin käytännön toteutuksen.

**Avattavat johdannaisvalikot**  
Avattavat johdannaisvalikot ovat erittäin hyödyllisiä. Niiden avulla voit suodattaa avattavassa valikossa näytettävät tiedot edellisessä avattavassa valikossa valitun arvon mukaan. PowerAppsissa ne luodaan usein määrittämällä sovellukselle kaksi tietolähdettä. Ensimmäisessä tietolähteessä ovat parhaillaan käsiteltävät ja päivitettävät tiedot ja toisessa säilytetään arvoja, joilla haluttu johdannaistoiminto luodaan. Alla on esimerkki toisesta tietolähteestä ja sen vaihtoehdoista.

![Avattavat johdannaisvalikot](./media/transform-infopath/cascading-dropdowns.png)

Nyt loisit ensimmäisen avattavan valikon ohjausobjektin ja käyttäisit sen Items-ominaisuudessa kaavaa Distinct(Impacts, Title). Sillä määrität, että avattavassa valikossa näkyvät vain vaihtoehdot Hinta, Ohjelman vaikutus ja Aikataulu. Sen jälkeen lisäisit toisen avattavan valikon ja määrittäisit sen Items-ominaisuudeksi kaavan Filter(Impacts,ddSelectType.Selected.Value in SCategory), jossa ddSelectType on ensimmäisen avattavan valikkoruudun nimi. Tuloksena on avattavia johdannaisvalikkoja. Lisätietoja on PowerApps-tiimin julkaisussa [SharePoint: Cascading Dropdowns in 4 Easy Steps!](https://powerusers.microsoft.com/t5/PowerApps-Community-Blog/SharePoint-Cascading-Dropdowns-in-4-Easy-Steps/ba-p/16248) (SharePoint: Avattavat johdannaisvalikot neljällä helpolla vaiheella!) ja tässä [yhteisön videossa](https://powerusers.microsoft.com/t5/Video-Webinar-Gallery/PowerApps-Cascading-Dropdown/m-p/92813). Äläkä huoli, voit tehdä sen aivan yhtä helposti ilman SharePointia.

**Älä luo yhtä jättisovellusta**  
PowerApps voi kutsua sovelluksia toisista sovelluksista. Joten luo ryhmä sovelluksia, jotka kutsuvat toisiaan ja jopa siirtävät tietoa toisilleen. Kehittäminen on siten helpompaa ja voit jättää valtavat, juuri ja juuri koossa pysyvät InfoPath-lomakkeet taaksesi.

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun olet omaksunut kaikki edellä mainitut tiedot, olet valmis valloittamaan maailman yksi PowerApps-sovellus kerrallaan. Alla on joitain käteviä linkkejä, jotka voivat auttaa matkan varrella. Yksi niistä on PowerAppsin yhteisösivuston linkki. Osallistu yhteisön keskustellun ja kasvata osaamistasi paljon nopeammin kuin yksin puurtamalla.

[**Kaavahakemisto**](https://docs.microsoft.com/en-us/powerapps/formula-reference) – Oletusfunktioiden selaaminen on erinomainen tapa hankkia lisäinspiraatiota.

[**PowerAppsin yhteisö**](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1) – Tutustu esimerkkeihin, keskustele muiden kanssa, kysy kysymyksiä ja vastaa muiden kysymyksiin. Auta PowerAppsin yhteisöä kasvamaan.