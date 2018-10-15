---
title: Virtuaalisten entiteettien luominen ja muokkaaminen Common Data Service for Appsilla| MicrosoftDocs
description: Opettele luomaan virtuaalisia entiteettejä
ms.custom: ''
ms.date: 06/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: 44834893-0bf6-4a64-8f06-7583fe08330d
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: 675c0ac5763698c82a7d13bfc75f8b7357d6cf0b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674872"
---
# <a name="create-and-edit-virtual-entities-that-contain-data-from-an-external-data-source"></a>Ulkoisesta tietolähteestä peräisin olevia tietoja sisältävien virtuaalisten entiteettien luominen ja muokkaaminen

Virtuaalinen entiteetti on Common Data Service for Appsissa oleva mukautettu entiteetti, joka sisältää tietoja ulkoisesta tietolähteestä. Virtuaaliset entiteetit näkyvät sovelluksessa käyttäjille tavallisina entiteettitietueina, mutta ne sisältävät ulkoisesta tietokannasta, kuten Microsoft Azuren SQL-tietokannasta, lähtöisin olevia tietoja. Virtuaalisiin entiteetteihin perustuvat tietueet ovat käytettävissä kaikissa asiakkaissa, mukaan lukien mukautetuissa asiakkaissa, jotka on kehitetty käyttämällä CDS for Apps -verkkopalveluita.  
  
Aiemmin erillisten tietolähteiden integroimiseksi piti luoda liitin tietojen siirtämiseksi tai kehittää mukautettu laajennus joko asiakas- tai palvelinpuolelle. Kuitenkin virtuaalisten entiteettien avulla voit yhdistää suoraan ulkoiseen tietolähteeseen suoritusaikana niin, että tietyt tiedot ulkoisesta tietolähteestä ovat käytettävissä ympäristössä ilman tarvetta tietojen replikoinnille.  

Virtuaaliset entiteetit koostuvat kolmesta pääosasta, jotka ovat *tietopalvelu*, *tietolähde*tietue ja *virtuaalinen entiteetti*. Tietopalvelu koostuu laajennuksista ja tietolähde-entiteetistä. Tietolähde on CDS for Appsissa oleva entiteettitietue, joka sisältää metatietoja, jotka edustavat yhteysparametrien rakennetta. Jokainen virtuaalinen entiteetti viittaa tietolähteeseen entiteetin määritelmässä.  
  
CDS for Apps sisältää OData-tietopalvelun, jonka avulla voit muodostaa yhteyden OData v4 -verkkopalveluun, joka käyttää ulkoisia tietoja. 
  
Vaihtoehtoisesti kehittäjät voivat luoda omia tietopalveluita. Tietopalvelut asennetaan ympäristöön ratkaisuna. Lisätietoja: [Kehitysdokumentaatio: Aloita virtuaalisten entiteettien käyttäminen](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)
  
 ![Virtuaalisen entiteetin kaavio](media/virtual-entity-diagram.png "Virtuaalisen entiteetin kaavio")  
  
<a name="benefits"></a> 
  
## <a name="virtual-entity-benefits"></a>Virtuaalisen entiteetin edut  
  
- Kehittäjät voit toteuttaa laajennuksia lukeakseen ulkoisia tietoja CDS for Apps -verkkopalveluita ja laajennuksen rekisteröintityökalua käyttämällä.  
- Järjestelmän mukauttajat käyttävät PowerApps-ratkaisunhallintaa tietolähdetietueen määrittämisessä ja virtuaalisten entiteettien luomisessa, joiden avulla voidaan käyttää ulkoisia tietoja ilman koodin kirjoittamista.  
- Virtuaalisen entiteetin luomia tietueita käsittelemällä käyttäjät voivat tarkastella kenttien, ruudukoiden ja hakutulosten tietoja ja noutaa XML-pohjaisia raportteja ja koontinäyttöjä.  
  
<a name="AddDataSource"></a> 
  
## <a name="add-a-data-source-to-use-for-virtual-entities"></a>Tietolähteen lisääminen käytettäväksi virtuaalisille entiteeteille 
 
 Kehittäjät luovat mukautetun laajennuksen, jota käytetään tietopalveluna virtuaaliselle entiteetille. Vaihtoehtoisesti voit käyttää annettua OData v4 -tietopalvelua. Lisätietoja: [OData v4 -tietopalvelun määrittäminen, vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Hallinta** > **Virtuaalisen entiteetin tietolähteet**.  
1. Valitse Toiminnot-työkaluriviltä **Uusi**.  
1. Valitse **Valitse tietopalvelu** -valintaikkunassa jokin seuraavista tietolähteistä ja valitse sitten **OK**.
 
    |Tietopalvelu|Kuvaus|
    |--|--|
    |*Mukautettu tietopalvelu*|Jos olet tuonut tietopalvelun laajennuksen, tietopalvelu näkyy tässä. Lisätietoja [Kehitysdokumentaatio: Aloita virtuaalisten entiteettien käyttäminen](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)|
    |**OData v4 -tietopalvelu**|CDS for Apps sisältää OData-tietopalvelun, jota voidaan käyttää OData v4 w-verkkopalveluiden kanssa. Lisätietoja [OData v4 -tietopalvelun määrittäminen, vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)|

  
### <a name="add-a-secured-field-to-a-data-source"></a>Suojatun kentän lisääminen tietolähteeseen

Voit luoda kenttiä tietolähteeseen samalla tavalla kuin muihinkin entiteetteihin. Jos tiedot ovat salattuja tai luottamuksellisia, ota käyttöön Tietolähteen salasana -määrite tietolähteen mukautetussa kentässä. Näin voit esimerkiksi suojata kentän, joka sisältää tietokannan yhteysmerkkijonon. 

> [!NOTE]
> Tietolähteen salasana -määrite on käytettävissä vain kentissä, jotka lisätään tietolähteen lomakkeeseen.

![Tietolähteen salasana -määrite](media/datasourcesecret.png)
  
<a name="createVirtualEntity"></a> 
  
## <a name="create-a-virtual-entity"></a>Virtuaalisen entiteetin luominen
  
Voit luoda virtuaalisen entiteetin samaan tapaan kuin muutkin CDS for Appsin entiteetit muutaman tässä kuvatun lisämääritteen lisäksi. Virtuaaliset entiteetit on luotava ratkaisunhallintaa käyttämällä.

> [!NOTE]
>  Vaikka voit luoda virtuaalisen entiteetin valitsemalla tietolähteeksi **Ei mitään**, virtuaalinen entiteetti edellyttää tietolähdettä, jotta se voi hankkia tietoja. Lisätietoja [Tietolähteen lisääminen käytettäväksi virtuaalisille entiteeteille](#AddDataSource)

### <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Luomasi virtuaalisen entiteetin nimeen sisältyy mukautusetuliite. Etuliite määräytyy käytössäsi olevan ratkaisun julkaisijan mukaan. Jos mukautusetuliitteellä on sinulle merkitystä, varmista, että käytät hallitsematonta ratkaisua, jossa mukautusetuliite on se, jota haluat käyttää kyseiselle virtuaaliselle entiteetille. Lisätietoja: [Ratkaisun julkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="create-a-virtual-entity"></a>Virtuaalisen entiteetin luominen
  
1. Luo uusi entiteetti ratkaisunhallinnassa. Voit tehdä sen valitsemalla vasemmassa siirtymisruudussa **Entiteetit** ja valitsemalla sitten **Uusi**.  
2. **Entiteetin määritelmä** -kohdan **Yleistä**-välilehdessä valitse **Virtuaalinen entiteetti** ja valitse sitten avattavassa **Tietolähde**-luettelossa haluamasi tietolähde.  
  
    ![Virtuaalisen entiteetin vaihtoehto entiteetin määritelmässä](media/virtual-entity-click-option.png)  
  
1. Täytä entiteetin määritelmässä seuraavat pakolliset kentät.
  
    |Kenttä|Kuvaus|
    |--|--|
    |**Ulkoinen nimi**|Anna ulkoisessa tietolähteessä olevan taulukon nimi, johon tämä entiteetti yhdistää.|
    |**Ulkoisen kokoelman nimi**|Anna ulkoisessa tietolähteessä olevan taulukon monikkomuotoinen nimi, johon tämä entiteetti yhdistää.|
      
    Tässä on esimerkki *Movie*-nimisestä virtuaalisesta entiteetistä, joka käyttää tiedostoja Azure Cosmos DB -tietopalvelun avulla.  
      
    ![Virtuaalisen entiteetin määritelmä, joka käyttää Azure Cosmos DB -tietopalveluja](media/virtual-entity-definition.PNG)  
      
    > [!IMPORTANT]
    > Useat vaihtoehdot, kuten käyttöoikeusryhmät, jonot ja pikaluonti, eivät ole käytettävissä virtuaalisten entiteettien kanssa. Lisätietoja [Huomioon otettavia seikkoja virtuaalisten entiteettien käyttämisessä](#considerations)  
      
    Täytä muut pakolliset ja valinnaiset ominaisuudet, kuten näyttö- ja monikkomuotoiset nimet, tarpeen mukaan. Katso lisätietoja näistä ominaisuuksista kohdasta [Entiteettien luominen ja muokkaaminen](create-edit-entities.md).  
  
1. Luo ja lisää yksi tai useampi kenttä virtuaaliselle entiteetille. Kentän vakio-ominaisuuksien lisäksi, joita mukautetun kentän luominen edellyttää, nämä valinnaiset ominaisuudet ovat käytettävissä jokaiselle mukautetulle kentälle, jonka luot virtuaaliselle entiteetille.

    |Kenttä|Kuvaus|
    |--|--|
    |**Ulkoinen nimi**|Tämä on yleensä yksilöivä nimi niiden tietojen tunnistamiselle, jotka haluat näyttää kentässä.|
    |**Ulkoisen tyypin nimi**|Jos luomasi kenttätyyppi on asetusjoukko: Tämä ominaisuus yhdistää arvojoukon ulkoiseen nimeen asetusjoukon ulkoisessa palvelussa.  Yleensä tämä voi olla valintalista tai merkkijonon arvoluokan nimi. Ulkoisen tyypin nimeä voidaan käyttää, kun täydellinen nimi vaaditaan.  Esimerkiksi *Tyyppinimi* OData-tiedoilla, joissa kyselyn parametrit edellyttävät täydellistä nimeä, kuten [*Tyyppinimi*].[*Arvo*].|
    |**Ulkoinen arvo**|Jos luomasi kenttätyyppi on asetusjoukko: Tämä ominaisuus yhdistää vastaavaan arvoon asetusjoukon ulkoisessa tietolähteessä.  Tämän arvon avulla määritetään, mikä asetusjoukko sovelluksessa näytetään.  |

    Viimeistele lisäominaisuudet tarpeen mukaan. Katso lisätietoja näistä ominaisuuksista kohdasta [Luo ja muokkaa kenttiä](create-edit-fields.md).  
  
1. Valitse **Tallenna ja sulje** **Kentän** ominaisuudet -sivulla.  
1. Valitse ratkaisunhallinnan työkalurivillä **Tallenna**.  
1. Valitse ratkaisunhallinnan työkalurivillä **Julkaise**.  
1. Sulje ratkaisunhallinta.  

<a name="considerations"></a>
   
## <a name="considerations-when-you-use-virtual-entities"></a>Huomioon otettavia seikkoja virtuaalisten entiteettien käyttämisessä  

Virtuaalisissa entiteeteissä on seuraavat rajoitukset.  
  
- Kaikki virtuaaliset entiteetit ovat vain luku -tilassa.  
- Olemassa olevia entiteettejä ei voi muuntaa virtuaalisiksi entiteeteiksi.  
- Oletusarvon mukaan virtuaaliset entiteetit sisältävät vain Nimi- ja Tunnus-kentän.  Muita järjestelmän hallitsemia kenttiä, kuten Tila tai Luotu/Muokattu, ei tueta.
- Virtuaaliset entiteetit eivät tue mukautettuja kenttiä, joissa on Valuutta-, Kuva- tai Asiakas-tietotyyppejä.
- Virtual entiteetit eivät tue seurantaa.  
- Virtuaalisten entiteettien kenttiä ei voi käyttää koonti- tai lasketuissa kentissä.
- Virtuaalinen entiteetti ei voi olla aktiviteettityyppinen entiteetti.  
- Monia ominaisuuksia, jotka vaikuttavat entiteetin taulukon riveihin, ei voi ottaa käyttöön virtuaalisten entiteettien kanssa.  Tällaisia ovat esimerkiksi jonot, tietämyksenhallinta, palvelutasosopimukset, kaksoiskappaleiden tunnistus, muutosten seuranta, mobile offline -ominaisuus, kentän suojaus, osuvuushaku, portaalit Dynamics 365 -verkkoportaaliratkaisuille ja N:N-suhteet virtuaalisten entiteettien välillä.  
- Virtuaaliset entiteetit ovat organisaation omistamia, ja ne eivät tue rivitason Commond Data Service for Appsin suojauskäsitteitä. Suosittelemme, että toteutat oman suojausmallin ulkoiselle tietolähteelle.  
- Suosittelemme, että otat kohteeksi yksittäisen tietolähteen, kun käytät virtuaalisia entiteettejä erikoishauissa. Esimerkiksi erikoishaun luomista, joka luo lopulta liitoksen Common Data Service for Appsin alkuperäisten tietojen ja virtuaalisen entiteetin ulkoisten tietojen välille, ei tueta.  
- Kentän metatieto-ominaisuudet, jotka vahvistetaan päivityksen yhteydessä, eivät koske virtuaalisia entiteettejä. Esimerkiksi Kokonaisluku-kenttä virtuaalisen entiteetin kentässä on saatettu määrittää niin, että sen pienin arvo on nolla. Kuitenkin koska arvo on peräisin ulkoisesta tietolähteestä, kysely palauttaa arvoja, jotka ovat pienempiä kuin nolla, kun ne noudetaan virtuaalisesta entiteetistä.  Vähimmäisarvo-ominaisuutta ei ilmaista kyselyssä.  Arvot täytyy silti suodattaa niin, että ne ovat suurempia kuin 0, jos haluat tuloksen olevan sellainen.
- Virtuaaliset entiteetit eivät tue muutosten seurantaa eikä niitä voi synkronoida CDS for Apps -ominaisuuden, kuten tietojen vientipalvelun, avulla.
  
### <a name="see-also"></a>Katso myös  

[OData v4 -tietopalvelun vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)</br> 
[Entiteettien luominen ja muokkaaminen](create-edit-entities.md)</br>
[Luo ja muokkaa kenttiä](create-edit-fields.md)
