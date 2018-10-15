---
title: Tutustu kangassovellusten paikallisiin tietoyhdyskäytäviin | Microsoft Docs
description: Paikallisten tietoyhdyskäytävien viitetietoja, kuten asennus PowerAppsissa ja vianmääritys
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: ''
ms.date: 10/20/2017
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5dcc07f3ba9b9b4baca39cf2090a2c57cb7e67b7
ms.sourcegitcommit: 967812754d8e5b1ff72baa35ffbe548f3b9b0085
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726925"
---
# <a name="understand-on-premises-data-gateways-for-canvas-apps"></a>Tutustu kangassovellusten paikallisiin tietoyhdyskäytäviin
## <a name="installation-and-configuration"></a>Asennus ja määritys
**Edellytykset**

Vähintään:

* .NET 4.5 Framework
* Windows 7:n tai Windows Server 2008 R2:n (tai uudemman) 64-bittinen versio

Suositus:
* 8 ytimen suoritin
* 8 Gt muistia
* Windows 2012 R2:n (tai uudemman) 64-bittinen versio

Aiheeseen liittyviä tietoja:

* Et voi asentaa yhdyskäytävää toimialueen ohjauskoneeseen.
* Älä asenna yhdyskäytävää tietokoneeseen, kuten kannettavaan tietokoneeseen, joka voidaan kytkeä pois päältä tai asettaa lepotilaan tai jota ei ole yhdistetty Internetiin. Yhdyskäytävä ei toimi näissä olosuhteissa. Lisäksi yhdyskäytävän suorituskyky voi kärsiä langattomassa verkossa.

**Asenna yhdyskäytävä**

1. [Lataa asennusohjelma](http://go.microsoft.com/fwlink/?LinkID=820931) ja suorita se.

    ![Suorita asennusohjelma](./media/gateway-reference/run-installer.png)

2. Napsauta tai napauta ohjatun asennustoiminnon ensimmäisessä näytössä **Seuraava** hyväksyäksesi muistutuksen yhdyskäytävän asentamisesta kannettavaan tietokoneeseen.

    ![Muistutus-näyttö](./media/gateway-reference/laptop-reminder.png)

3. Määritä sijainti, johon haluat asentaa yhdyskäytävän, valitse valintaruutu käyttöehtojen ja tietosuojalausekkeen hyväksymiseksi ja napsauta tai napauta **Asenna**.

4. Jatka napsauttamalla tai napauttamalla **Käyttäjätilien valvonta** -valintaikkunoissa **Kyllä**.

5. Napsauta tai napauta ohjatun toiminnon seuraavassa näytössä **Kirjaudu sisään** ja anna sitten samat tunnistetiedot, joita käytät kirjautuessasi sisään PowerAppsiin.

    ![Kirjaudu sisään](./media/gateway-reference/sign-in.png)

6. Napsauta tai napauta valintaa uuden yhdyskäytävän luomiseksi, olemassa olevan yhdyskäytävän siirtämiseksi, palauttamiseksi tai ottamiseksi haltuun, ja napsauta tai napauta **Seuraava**.

    ![Valitse uusi tai olemassa oleva](./media/gateway-reference/new-existing.png)

   * Voit määrittää yhdyskäytävän kirjoittamalla sille **nimen** ja **palautusavaimen** sekä napsauttamalla tai napauttamalla **Määritä** ja **Sulje**.

       ![Määritä uusi yhdyskäytävä](./media/gateway-reference/configure-new.png)

       Määritä palautusavain, joka sisältää vähintään kahdeksan merkkiä, ja säilytä sitä turvallisessa paikassa. Tarvitset tätä avainta, jos haluat siirtää, palauttaa tai ottaa haltuun sen yhdyskäytävän.

   * Siirrä, palauta tai ota haltuun olemassa oleva yhdyskäytävä antamalla yhdyskäytävän nimi ja palautusavain, napsauttamalla tai napauttamalla **Määritä** ja noudattamalla lisäkehotteita.

       ![Palauta olemassa oleva yhdyskäytävä](./media/gateway-reference/recover-existing.png)

**Käynnistä yhdyskäytävä uudelleen**

Yhdyskäytävä toimii Windows-palveluna, joten voit käynnistää ja pysäyttää sen useilla tavoilla. Voit esimerkiksi avata komentokehotteen laajennetuin oikeuksin koneella, jolla yhdyskäytävä on toiminnassa, ja suorittaa sitten toisen näistä komennoista:

* Pysäytä palvelu suorittamalla tämä komento:<br>
  **net stop PBIEgwService**

* Käynnistä palvelu suorittamalla tämä komento:<br>
  **net start PBIEgwService**

**Määritä palomuuri tai välityspalvelin**

Saat lisätietoja välityspalvelimen tietojen lisäämisestä yhdyskäytävään kohdasta [Välityspalvelimen asetusten määrittäminen](https://docs.microsoft.com/power-bi/service-gateway-proxy).

Voit tarkistaa, estääkö palomuuri tai välityspalvelin yhteyksiä, suorittamalla seuraavan komennon PowerShell-kehotteesta. Tämä komento testaa yhdistettävyyden Azuren palveluväylään. Komento testaa vain verkon yhdistettävyyttä, eikä sillä ole mitään tekemistä pilvipalvelinpalvelun tai yhdyskäytävän kanssa. Se auttaa määrittämään, voiko koneesi muodostaa Internet-yhteyden.

**Test-NetConnection -ComputerName watchdog.servicebus.windows.net -Port 9350**

Tulosten tulisi näyttää tätä esimerkkiä vastaavilta. Jos **TcpTestSucceeded** ei ole **tosi**, palomuuri voi estää käytön.

    ComputerName           : watchdog.servicebus.windows.net
    RemoteAddress          : 70.37.104.240
    RemotePort             : 5672
    InterfaceAlias         : vEthernet (Broadcom NetXtreme Gigabit Ethernet - Virtual Switch)
    SourceAddress          : 10.120.60.105
    PingSucceeded          : False
    PingReplyDetails (RTT) : 0 ms
    TcpTestSucceeded       : True

Jos haluat olla perusteellinen, korvaa **ComputerName**- ja **Port**-arvot jäljempänä tässä aiheessa kohdassa **Porttien määritys** annetuilla arvoilla.

Palomuuri voi estää myös yhteydet, jotka Azuren palveluväylä muodostaa Azuren palvelinkeskuksiin. Lisää tässä tapauksessa alueesi kyseisten palvelinkeskusten IP-osoitteet sallittujen luetteloon (poista esto). Näet luettelon Azuren IP-osoitteista [täältä](https://www.microsoft.com/download/details.aspx?id=41653).

**Porttien määritys**

Yhdyskäytävä luo lähtevän yhteyden Azuren palveluväylään. Se viestii lähtevien porttien kautta: TCP 443 (oletusarvoinen), 5671, 5672, 9350–9354. Yhdyskäytävä ei vaadi saapuvia portteja.

Lue lisätietoja [yhdistelmäratkaisuista](https://azure.microsoft.com/documentation/articles/service-bus-fundamentals-hybrid-solutions/).

On suositeltavaa, että lisäät tietoalueesi IP-osoitteet sallittujen luetteloon palomuurin asetuksissa. Voit ladata viikoittain päivitettävän [Microsoft Azuren palvelinkeskusten IP-osoiteluettelon](https://www.microsoft.com/download/details.aspx?id=41653).

> [!NOTE]
> Osoitteet on lueteltu Azuren palvelinkeskusten IP-osoiteluettelossa [CIDR-merkintätapaa](http://whatismyipaddress.com/cidr) käyttäen. Esimerkiksi 10.0.0.0/24 ei tarkoita 10.0.0.0–10.0.0.24.

Tässä on luettelo yhdyskäytävän käyttämistä täysin valtuutetuista toimialuenimistä.

| Toimialuenimet | Lähtevien pyyntöjen portit | Kuvaus |
| --- | --- | --- |
| *.analysis.windows.net |443 |HTTPS |
| *.login.windows.net |443 |HTTPS |
| *.servicebus.windows.net |5671–5672 |Advanced Message Queuing Protocol (AMQP) |
| *.servicebus.windows.net |443, 9350–9354 |Kuuntelutoiminnot Azuren palveluväylässä käyttäen TCP-protokollaa (edellyttää 443:n käyttöoikeuksien hallinnan tunnusta hankintaa varten) |
| *.frontend.clouddatahub.net |443 |HTTPS |
| *.core.windows.net |443 |HTTPS |
| login.microsoftonline.com |443 |HTTPS |
| *.msftncsi.com |443 |Käytetään Internet-yhteyden testaamiseen, jos Power BI -palvelu ei saa yhteyttä yhdyskäytävään. |

**Kirjautumistili**

Käyttäjät kirjautuvat sisään työpaikan tai oppilaitoksen tilillä. Tämä on organisaatiotilisi. Jos rekisteröidyit Office 365 -tarjoukseen etkä antanut varsinaista työpaikan sähköpostiasi, se voi näyttää tältä: nancy@contoso.onmicrosoft.com. Pilvipalvelun sisällä oleva tilisi on tallennettu vuokraajaan Azure Active Directoryssa (AAD). Useimmissa tapauksissa AAD-tilisi UPN vastaa sähköpostiosoitetta.

**Windows-palvelutili**

Paikallinen tietoyhdyskäytävä on määritetty käyttämään *NT SERVICE\PBIEgwService* -palvelua Windows-palvelun sisäänkirjautumisen tunnistetiedoille. Sillä on oletusarvoisesti sisäänkirjautumisoikeus palveluna. Tämä on sen koneen kontekstissa, jolle asennat yhdyskäytävän.

Tätä tiliä ei käytetä yhdistämiseen paikallisiin tietolähteisiin tai työpaikan tai oppilaitoksen tiliin, jolla kirjaudut sisään pilvipalveluihin.

Jos kohtaat todentamisen vuoksi ongelmia välityspalvelimen kanssa, sinun kannattaa vaihtaa Windows-palvelutili toimialuekäyttäjäksi tai hallituksi palvelutiliksi kohdan [Välityspalvelimen määritys](https://docs.microsoft.com/power-bi/service-gateway-proxy#changing-the-gateway-service-account-to-a-domain-user) mukaan.

## <a name="tenant-level-administration"></a>Vuokraajatason hallinta 

Tällä hetkellä ei ole yhtä paikkaa, jossa vuokraajan järjestelmänvalvojat voivat hallita kaikkia yhdyskäytäviä, joita muut käyttäjät ovat asentaneet ja määrittäneet.  Jos olet vuokraajan järjestelmänvalvoja, sinun kannattaa pyytää organisaatiosi käyttäjiä lisäämään sinut järjestelmänvalvojaksi jokaiseen asentamaansa yhdyskäytävään. Näin voit hallita kaikkia organisaatiosi yhdyskäytäviä Yhdyskäytäväasetukset-sivulla tai [PowerShell-komennoilla](https://docs.microsoft.com/power-bi/service-gateway-high-availability-clusters#powershell-support-for-gateway-clusters).

## <a name="frequently-asked-questions"></a>Usein kysytyt kysymykset
#### <a name="general"></a>Yleistä
**Kysymys:** Mitä tietolähteitä yhdyskäytävä tukee?  
**Vastaus:** Tätä kirjoitettaessa:

* SQL Server
* SharePoint
* Oracle
* Informix
* Filesystem
* DB2

**Kysymys:** Tarvitsenko yhdyskäytävän pilvipalvelussa, kuten SQL Azuressa, oleviin tietolähteisiin?  
**Vastaus:** Et. Yhdyskäytävä muodostaa yhteyden vain paikallisiin tietolähteisiin.

**Kysymys:** Mikä on varsinaisen Windows-palvelun nimi?  
**Vastaus:** Palvelut-kohdassa yhdyskäytävän nimi on **Power BI Enterprise Gateway Service**.

**Kysymys:** Saapuuko pilvipalvelusta yhteyksiä yhdyskäytävään?  
**Vastaus:** Ei. Yhdyskäytävä käyttää lähteviä yhteyksiä Azuren palveluväylään.

**Kysymys:** Entä jos estän lähtevät yhteydet? Mitä minun tulee avata?  
**Vastaus:** Katso yllä oleva luettelo yhdyskäytävän käyttämistä porteista ja isännistä.

**Vastaus:** Onko yhdyskäytävä asennettava samalle koneelle kuin tietolähde?  
**Vastaus:** Ei. Yhdyskäytävä yhdistää tietolähteeseen käyttämällä annettuja yhteystietoja. Yhdyskäytävä on tässä mielessä eräänlainen asiakassovellus. Sen on vain pystyttävä muodostamaan yhteys annettuun palvelimen nimeen.

**Kysymys:** Mikä on viive suoritettaessa kyselyjä yhdyskäytävästä tietolähteeseen? Mikä on paras arkkitehtuuri?  
**Vastaus:** Vähennä verkon viivettä asentamalla yhdyskäytävä mahdollisimman lähelle tietolähdettä. Jos voit asentaa yhdyskäytävän varsinaiseen tietolähteeseen, viive minimoituu. Muista myös palvelinkeskukset. Jos palvelusi käyttää esimerkiksi West US -palvelinkeskusta ja sinulla on SQL Server isännöitynä Azure VM:ssä, haluat että Azure VM on myös West US:ssä. Tämä minimoi viiveen ja auttaa välttämään lähtevän liikenteen maksut Azure VM:ssä.

**Kysymys:** Onko verkon kaistanleveydelle vaatimuksia?  
**Vastaus:** On suositeltavaa, että verkkoyhteyden siirtomäärä on hyvä. Jokainen ympäristö on erilainen, ja lähetettävien tietojen määrä vaikuttaa tuloksiin. ExpressRouten käyttäminen voi auttaa varmistamaan siirtomäärätason paikallisten palvelinkeskusten ja Azuren palvelinkeskusten välillä.

Voit käyttää kolmannen osapuolen työkalua, [Azure Speed Test -sovellusta](http://azurespeedtest.azurewebsites.net/), siirtomäärän mittaamiseen.

**Kysymys:** Voiko yhdyskäytävän Windows-palvelu toimia Azure Active Directory -tilin kanssa?  
**Vastaus:** Ei. Windows-palvelulla on oltava kelvollinen Windows-tili. Oletusarvoisesti se toimii Service SID:llä, *NT SERVICE\PBIEgwService*.

**Kysymys:** Miten tulokset lähetetään takaisin pilvipalveluun?  
**Vastaus:** Tämä tehdään Azuren palveluväylän kautta. Saat lisätietoja [Miten se toimii](gateway-reference.md#how-the-gateway-works) -kohdasta.

**Kysymys:** Mihin tunnistetietoni tallennetaan?  
**Vastaus:** Tietolähteelle antamasi tunnistetiedot tallennetaan salattuina yhdyskäytävän pilvipalveluun. Tunnistetietojen salaus puretaan paikallisessa yhdyskäytävässä.

**Kysymys:** Voinko sijoittaa yhdyskäytävän edustaverkkoon (toiselta nimeltään DMZ tai suojattu aliverkko)?  
**Vastaus:** Yhdyskäytävä vaatii liitettävyyden tietolähteeseen. Jos tietolähde ei ole edustaverkossasi, yhdyskäytävä ei välttämättä voi muodostaa yhteyttä siihen. Esimerkiksi tietokone, joka käyttää SQL Serveriä, ei välttämättä ole edustaverkossasi, etkä voi yhdistää tähän tietokoneeseen edustaverkosta. Jos olet sijoittanut yhdyskäytävän edustaverkkoon, yhdyskäytävä ei voi tavoittaa SQL Serveriä käyttävää tietokonetta.

#### <a name="high-availabilitydisaster-recovery"></a>Korkea käytettävyys / järjestelmäpalautus
**Kysymys:** Onko suunnitteilla korkean käytettävyyden skenaarioiden ottamista käyttöön yhdyskäytävän kanssa?  
**Vastaus:** Voit ottaa korkean käytettävyyden käyttöön yhdistämällä vähintään 2 yhdyskäytävää saman klusteriin.  Korkean käytettävyyden yhdyskäytäväklusterit edellyttävät, että tietoyhdyskäytävään on asennettu marraskuun 2017 päivitys tai uudempi.  Lisätietoja saat [ilmoitukseen liittyvästä blogikirjoituksesta](https://powerapps.microsoft.com/en-us/blog/gateway-high-availability-for-powerapps-and-flow).

**Kysymys:** Mitä vaihtoehtoja järjestelmäpalautukseen on saatavilla?  
**Vastaus:** Voit käyttää palautusavainta yhdyskäytävän palauttamiseen tai siirtämiseen. Määritä palautusavain, kun asennat yhdyskäytävän.

**Kysymys:** Mitä etua palautusavaimesta on?  
**Vastaus:** Se tarjoaa tavan siirtää tai palauttaa yhdyskäytävän asetukset vakavan häiriön jälkeen.

#### <a name="troubleshooting"></a>Vianmääritys
**Kysymys:** Missä yhdyskäytävän lokit ovat?  
**Vastaus:** Katso [Työkalut](gateway-reference.md#tools) jäljempänä tässä aiheessa.

**Kysymys:** Miten näen, mitkä kyselyt lähetetään paikalliseen tietolähteeseen?  
**Vastaus:** Voit ottaa käyttöön kyselyjen seurannan, joka kattaa lähetettävät kyselyt. Muista vaihtaa oletusarvo takaisin, kun olet suorittanut vianmäärityksen. Jos kyselyjen seuranta jätetään käyttöön, lokit muuttuvat suuremmiksi.

Voit myös tutustua työkaluihin, jotka tietolähteesi sisältää kyselyjen seuraamista varten. Voit käyttää esimerkiksi Extended Events- tai SQL Profiler for SQL Server- ja Analysis Services -työkaluja.

## <a name="how-the-gateway-works"></a>Yhdyskäytävän toiminta
![Miten se toimii](./media/gateway-reference/gateway-arch.png)

Kun käyttäjä on vuorovaikutuksessa elementin kanssa, joka on yhdistetty paikalliseen tietolähteeseen:  

1. Pilvipalvelu luo kyselyn ja salatut tunnistetiedot tietolähteelle ja lähettää kyselyn yhdyskäytävän jonoon odottamaan käsittelyä.

2. Yhdyskäytävän pilvipalvelu analysoi kyselyn ja siirtää pyynnön [Azuren palveluväylään](https://azure.microsoft.com/documentation/services/service-bus/).

3. Paikallinen tietoyhdyskäytävä kyselee Azuren palveluväylästä odottavia pyyntöjä.

4. Yhdyskäytävä hakee kyselyn, purkaa tunnistetietojen salauksen ja yhdistää kyseisten tunnistetietojen tietolähteisiin.

5. Yhdyskäytävä lähettää kyselyn tietolähteeseen suorittamista varten.

6. Tulokset lähetetään tietolähteestä takaisin yhdyskäytävään ja sen jälkeen pilvipalveluun. Tämän jälkeen palvelu käyttää tuloksia.

## <a name="troubleshooting"></a>Vianmääritys
#### <a name="update-to-the-latest-version"></a>Päivitä uusimpaan versioon
Ongelmia voi esiintyä paljon, jos yhdyskäytävän versio on vanhentunut.  Hyvä yleinen käytäntö on varmistaa, että käytät aina uusinta versiota.  Jos et ole päivittänyt yhdyskäytävää ainakaan kuukauteen, sinun kannattaa harkita yhdyskäytävän uusimman version asentamista ja kokeilla ongelman toistamista.

#### <a name="error-failed-to-add-user-to-group---2147463168---pbiegwservice---performance-log-users---"></a>Virhe: Käyttäjän lisääminen ryhmään epäonnistui.  (-2147463168   PBIEgwService   Performance Log Users   )
Voit saada tämän virheviestin, jos yrität asentaa yhdyskäytävää toimialueen ohjauskoneeseen, mitä ei tueta. Sinun on otettava yhdyskäytävä käyttöön koneella, joka ei ole toimialueen ohjauskone.

## <a name="tools"></a>Työkalut
#### <a name="collecting-logs-from-the-gateway-configurator"></a>Lokien kerääminen yhdyskäytävän määritystoiminnosta
Voit kerätä useita lokeja yhdyskäytävästä. Aloita aina lokeista!

**Asennusohjelman lokit**

%localappdata%\Temp\On-premises_data_gateway_*.log

**Määrityksen lokit**

%localappdata%\Microsoft\on-premises data gateway\GatewayConfigurator*.log

**Yritysyhdyskäytävän palvelulokit**

C:\Users\PBIEgwService\AppData\Local\Microsoft\on-premises data gateway\Gateway*.log

**Tapahtumalokit**

**Paikallisen tietoyhdyskäytäväpalvelun** tapahtumalokit on esitetty kohdassa **Sovellukset ja palvelulokit**.

![Tapahtumalokit](./media/gateway-reference/event-logs.png)

#### <a name="fiddler-trace"></a>Fiddler-jäljitys
[Fiddler](http://www.telerik.com/fiddler) on Telerikin ilmainen työkalu, joka valvoo HTTP-liikennettä.  Voit tarkastella Power BI -palvelun tiedonsiirtoa asiakaskoneelta. Tämä saattaa näyttää virheitä ja muita olennaisia tietoja.
