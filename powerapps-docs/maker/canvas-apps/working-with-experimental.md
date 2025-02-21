---
redirect_url: working-with-experimental-preview
title: Ymmärrä esikatseluominaisuuksia ja kokeellisia ominaisuuksia | Microsoft Docs
description: Testaa ja aloita uusien ominaisuuksien käyttö.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 03/20/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b56fcf1b0ee14bf9a39b4c0ad54d4e707d635f37
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994756"
---
# <a name="understand-experimental-and-preview-features-in-powerapps"></a>Ymmärrä PowerAppsin esikatseluominaisuuksia ja kokeellisia ominaisuuksia

Jokainen julkaistu versio tuo mukanaan muutoksia ja lisäominaisuuksia, joiden ansiosta PowerApps sopii parhaiten tarpeisiisi. Viemme tuotetta eteenpäin.  

Yhteensopivuus aikaisempien versioiden kanssa on meille tärkeää. Minkä tahansa muutoksen tai parannuksen kanssa saattaa kuitenkin ilmetä tahattomia sivuvaikutuksia, joiden takia sovelluksesi ei ehkä toimi täsmälleen samalta tavalla kuin aikaisemmin.

Tasapainottaaksemme olemassa olevien sovellusten parannuksia esittelemme suuremmat ominaisuudet vaiheiden kautta. Tässä artikkelissa kuvataan kyseistä prosessia ja sitä, miten voit hallita altistustasi kehitteillä oleville ominaisuuksille.

## <a name="feature-roll-out-stages"></a>Ominaisuuden julkaisuvaiheet

Ominaisuudet kulkevat kolmen eri vaiheen läpi ennen kuin niistä tulee virallinen osa tuotetta:

1. **Kokeellinen**:  Tämä ominaisuus on keskeneräinen. Älä laske vielä sen varaan, siihen saattaa tulla merkittäviä muutoksia.
1. **Esikatselu**:  Tämä ominaisuus on melkein valmista, ja se on vakaa. Aloita olemassa olevien sovellusten siirto.
1. **Lähetetty**:  Tämä ominaisuus on tehty. Ominaisuus on käytössä kaikissa sovelluksissa, eikä sitä voida poistaa käytöstä.

Kussakin vaiheessa ominaisuutta käyttävien henkilöiden määrä nousee auttaen meitä vahvistamaan, että ominaisuus on tarpeellinen ja ettei sillä ole tahattomia sivuvaikutuksia.

**Palautteesi on tässä prosessissa tärkeää.**  Julkaise palautteesi [PowerApps-yhteisön keskustelupalstalla](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).

Kuinka kauan kukin julkaisuvaihe kestää? Tämä vaihtelee ominaisuuden mukaan. Tarkastelemme monia tekijöitä, kuten ominaisuutta käyttävien sovellusten määrää, ilmoitettujen ongelmien määrää ja miten kiireellisesti ominaisuutta tarvitaan. Ominaisuudet saattavat pysyä yhdessä vaiheessa viikoista kuukausiin.

Tämän taulukon avulla voit päättää, koska haluat liittyä mukaan: 

| Vaihe | Milloin sitä kuuluu käyttää? | Voiko sitä käyttää luotettavasti? | On se oletusarvoisesti käytössä uusissa sovelluksissa? | 
|----|----|----|-----|------|
| **Kokeellinen** | Jos olet aikainen käyttäjä, näet jotakin sinulle hyödyllistä ja haluat auttaa ominaisuuden testaamisessa. | Ei.  Kokeellisia ominaisuuksia voidaan muuttaa tai ne voivat kadota kokonaan milloin tahansa. | Ei. Sinun on annettava nimenomainen suostumus ominaisuudelle.  |  
| **Esikatselu** | Ominaisuus sisältyy automaattisesti uusiin sovelluksiin.  Aloita käyttöönotto ja testaus nykyisissä sovelluksissa, koska tämä ominaisuus otetaan lopulta käyttöön myös niissä. | Kyllä. Tästä ominaisuudesta on tulossa pysyvä osa tuotetta.  | Kyllä. Haluat ehkä poistaa sen käytöstä, jos kohtaat ongelmia.  Ilmoita ongelmista. Tämä on tärkein syy sille, miksi ominaisuus on esikatselussa. | 
| **Toimitettu** (ei näy enää **lisäasetuksissa**) | Kaikissa sovelluksissa on tämä ominaisuus. | Kyllä. | Kyllä.  Useimpia ei voi poistaa käytöstä.  |  

Esikatselun lopulla, saatamme ottaa toiminnon käyttöön kaikissa sovelluksissa kerralla ja tämä merkitään **lopulliseksi vahvistukseksi**.  Tämä antaa useimmille käyttäjille viimeisen mahdollisuuden kokeilla ominaisuutta samalla, kun se voidaan vielä poistaa käytöstä. Reaaliaikainen palaute on tänä aikana ratkaisevaa, koska seuraavassa vaiheessa ominaisuus on täysin toimitettu, eikä sitä voida poistaa käytöstä.

Lopullisen siirtymisen yhteydessä voimme poistaa **esiversio-valitsimen**sovelluksissa, joissa toiminto on jo käytössä, ja kääntää toiminnon pysyvästi pysyvästi. Tämä muutos koskee useimpia sovelluksia, koska ominaisuus on ollut Oletus arvon mukaan käytössä ennen tätä pistettä. Sovelluksille, joissa ominaisuus on poistettu käytöstä, esikatselu-valitsin on edelleen käytettävissäsi, kun otat sen käyttöön, testaat ominaisuutta ja poistat käytöstä samassa PowerApps Studio istunnossa. Jos kuitenkin tallennat sovelluksen, kun valitsin on käytössä, se ei ole käytettävissä, kun sovellus ladataan uudelleen, joten et voi poistaa toimintoa käytöstä uudelleen. Tässä vaiheessa voit [palauttaa sovelluksen aiempaan versioon](restore-an-app.md) , jolloin sovellus palautetaan tilaan, jossa se oli, ennen kuin ominaisuus otettiin käyttöön.

## <a name="documentation"></a>Asia kirjat

Mistä voit löytää tietoja näistä ominaisuuksista?  Pidämme esikatselussa olevia ominaisuuksia valmiina, ja voit lukea niistä lisätietoja samalla tavalla kuin tuotteen muista ominaisuuksista: 
- [PowerApps-dokumentaatio](https://docs.microsoft.com/powerapps/maker/canvas-apps/getting-started). Listaamme uuden ominaisuuden perusteet: edut, käytön aloittaminen ja viitetiedot.
- [PowerApps-yhteisön keskustelupalsta](https://powerusers.microsoft.com/t5/PowerApps-Community/ct-p/PowerApps1).  Muut tutkivat uutta ominaisuutta samaan aikaan kanssasi. Lue heidän kokemuksiaan ja jaa omasi.
- [PowerApps-blogi](https://powerapps.microsoft.com/blog/).  Blogikirjoituksen mukana on usein uusi ominaisuus.

Kokeelliset ominaisuudet ovat erilaisia.  Ne ovat vielä työn alla, emmekä pidä niitä valmiina sovelluksina. Lyhyt kuvaus **sovellusasetukset** -ruudussa (alla) voi olla niitä koskeva ainoa tieto. Kokeellisia ominaisuuksia ei normaalista näy dokumentaatiossa. Yhteisön keskustelupalsta on todennäköisesti paras tietolähteesi.  Joissakin tapauksissa varhainen blogikirjoitus kuvailee toimintoa.  Jos et löydä riittävästi tietoja, kysy keskustelupalstoilta tai odota kunnes ominaisuus on siirretty esikatselu-vaiheeseen.

## <a name="controlling-which-features-are-enabled"></a>Ominaisuuksien käyttöönoton hallinta

Kokeelliset ja esikatseluominaisuudet on lueteltu sovelluksen **lisäasetuksissa**.  Valitse sovelluksen **Tiedosto**-valikosta **Sovellusasetukset** ja valitse sitten **Lisäasetukset**. Vieritä alaspäin **Esikatseluominaisuudet** ja **Kokeelliset ominaisuudet** -kohtaan:

![](media/working-with-experimental/advanced-settings.png)

Kullakin ominaisuudella on käytössä/pois käytöstä -valitsin.  **Pois käytöstä** tarkoittaa, että ominaisuus on poistettu käytöstä.  Kaikkien kytkimet ovat lähtökohtaisesti pois päältä, ja tämä on turvallisin tapa suorittaa sovellus.

Joissakin tapauksissa saatat joutua sulkemaa ja avaamaan sovelluksen uudelleen, kun muutat asetusta.  Ominaisuuden kuvauksesta tulisi käydä ilmi, milloin tämä täytyy suorittaa.

**Lisäasetukset**-paneelin yläreunassa näkyvät asetukset täysin toimitetuille ominaisuuksille, jotka eivät ole esikatselmuksellisia tai kokeellisia ja joihin voit luottaa täysin. 

Nämä asetukset ovat ominaisia kullekin ominaisuudelle, joten käytössä/pois käytöstä -valitsimen asennon muuttaminen vaikuttaa vain avoinna olevaan sovellukseen. Jos luot sovelluksen, nämä valitsimet palaavat kyseisen sovelluksen oletusarvoihin.
