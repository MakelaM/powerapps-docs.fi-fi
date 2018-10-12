---
title: Mallipohjaisten sovellusten lokalisoitavan tekstin kääntäminen | MicrosoftDocs
description: Ota selvää, miten voit käännättää lokalisoitavan tekstin useiden kielten tukemiseksi.
ms.custom: ''
ms.date: 06/03/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: 3d77d149-819b-45e6-8e70-1fbe54d5c153
caps.latest.revision: 19
ms.author: matp
manager: kvivek
ms.openlocfilehash: e2e305313f3b86be2ea410f6668676b56aa79d95
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674616"
---
# <a name="translate-localizable-text-for-model-driven-apps"></a>Mallipohjaisten sovellusten lokalisoitavan tekstin kääntäminen

Jos olet mukauttanut entiteettien tai kenttien tekstiä, kuten kenttien otsikoita tai avattavan valikon arvoja, voit tarjota nämä mukautetut tekstit sellaisten käyttäjien omilla kielillä, jotka eivät käytä ympäristösi peruskieliversiota. 

Prosessissa on seuraavat vaiheet:
1. Ota muita kieliä käyttöön ympäristössäsi
2. Vie lokalisoitava teksti
3. Käännätä lokalisoitava teksti
4. Tuo lokalisoitu teksti

## <a name="enable-other-languages-for-your-environment"></a>Ota muita kieliä käyttöön ympäristössäsi

Jos et ole vielä ottanut kieliä käyttöön ympäristössäsi, se tapahtuu ohjeaiheessa [Kielen ottaminen käyttöön](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) kuvatulla tavalla.

> [!IMPORTANT]
> Kunkin kielen käyttöönotossa voi kestää useita minuutteja. Tänä aikana ympäristön muut käyttäjät eivät ehkä voi käyttää sovellustasi. Kieliä tulisi ottaa käyttöön sellaisina aikoina, kun siitä on vähiten haittaa käyttäjille.

> [!TIP]
> Kun otat kieliä käyttöön, ota ylös jokaiselle kielelle käytetyt LCID-arvot. Tämä arvo merkitsee kieltä lokalisoitavan tekstin viedyissä tiedoissa. Kielikoodit ovat neli- tai viisinumeroisia aluekohtaisten asetusten tunnuksia. Kelvolliset aluetunnukset löydät ohjeaiheesta [Aluekohtaisten asetusten tunnusten (LCID) kaavio](http://go.microsoft.com/fwlink/?LinkId=122128).

## <a name="export-the-localizable-text"></a>Vie lokalisoitava teksti

Vietävän lokalisoitavan tekstin alueen muodostaa hallitsematon ratkaisu, joka sisältää lokalisoitavan tekstin. Tämän voi tehdä vain Ratkaisunhallinnassa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Avaa lokalisoitavan tekstin sisältävä hallitsematon ratkaisu valikkoriviltä valitsemalla **Käännökset** > **Vie käännökset**. 

![Vie käännökset](media/export-localizable-text.png)

Näet seuraavan ilmoituksen:
> Mukautettujen otsikoiden vieminen käännettäväksi voi kestää useita minuutteja. Älä napsauta vientilinkkiä uudelleen, ennen kuin ensimmäinen vientitoiminto on päättynyt. Haluatko varmasti suorittaa viennin nyt? 

Valitse **OK**, jos haluat jatkaa.

Kun vienti on valmis, löydät Ladatut tiedostot -kansiostasi tiedoston, joka on muotoa `CrmTranslations_{0}_{1}.zip`. Nimessä `{0}` on ratkaisun yksilöivä nimi ja `{1}` ratkaisun versionumero.

## <a name="get-the-localizable-text-translated"></a>Käännätä lokalisoitava teksti

Voit lähettää tämän tiedoston kääntäjälle, käännöstoimistolle tai lokalisointiyritykselle.

Jos pystyt kääntämään tekstin itse tai haluat vain tarkastella sen muotoa, voit purkaa viemäsi tiedoston. Se sisältää kaksi XML-tiedostoa. 
 - `[Content_Types].xml`
 - `CrmTranslations.xml`

CrmTranslations.xml-tiedoston voi avata Microsoft Office Excelissä.

> [!TIP]
> Jos et normaalisti avaa XML-tiedostoja Excelissä, avaa ensin Excel ja avaa sitten tiedosto liittämällä polku purettuun CrmTranslations.xml-tiedostoon.

> [!IMPORTANT]
> Älä muuta tiedostomuotoa. Jos tallennat tiedoston toisessa muodossa, sitä ei voi tuoda takaisin.

Kun tiedosto on avoinna Excelissä, tutustu **Lokalisoidut otsikot** -välilehteen.

![Lokalisointia varten viety teksti](media/localized-labels-tab-exported-languages.png)

Mukautettuja entiteettien tai kenttien lokalisoitavia tekstejä edustavat tyhjät solut. Lisää lokalisoidun arvot näille kohteille.

> [!NOTE]
> Jos olet muuttanut jonkin vakioentiteetin tai entiteettikentän näyttönimeä tai kuvausta, lokalisoidut merkkijonot ovat edelleen alkuperäisten arvojen käännöksiä. Ne tulisi lokalisoida vastaamaan uusia arvoja.

**Näyttömerkkijonot**-välilehti sisältää tekstin, joka näytetään muille käyttöliittymän elementeille, kuten valintanauhan komennoille, virhesanomille ja lomakkeen otsikoille.

### <a name="updating-localizable-text-in-the-base-language"></a>Peruskielen lokalisoitavan tekstin päivittäminen

Jos muutat sellaisen vakioentiteetin tai entiteettikentän näyttönimeä, joka sisältyy erikoisviestiin, voit käyttää mukauttamaasi nimeä päivittämällä **Näyttömerkkijonot**-välilehden tiedot.

> [!TIP]
> Järjestelmän entiteettiviestien muokkaamista varten näytetty käyttöliittymä sisältää lukuisia viittauksia entiteettinimiin, mutta se ei sisällä niitä kaikkia. Käyttämällä tätä tekniikkaa saatat löytää niitä enemmän. Lisätietoja: [Järjestelmän entiteettiviestien muokkaaminen](../common-data-service/edit-system-entity-messages.md)

Jos esimerkiksi muutat Account-entiteetin näyttönimeksi *Company*, hae **Näyttömerkkijonot**-välilehden peruskielisarakkeesta osumat `account`, `accounts`, `Account` ja `Accounts`. Muuta ne samassa järjestyksessä arvoiksi `company`, `companies`, `Company` ja `Companies`.

> [!IMPORTANT]
> Älä tee tätä yleisellä Etsi ja korvaa -toiminnolla. Varmista, että vastaava teksti todella viittaa muuttamiisi nimiin.


## <a name="import-the-localized-text"></a>Tuo lokalisoitu teksti
Tekstin tuominen edellyttää tiedostojen pakkaamista ja tuomista järjestelmään.

### <a name="compress-the-files"></a>Pakkaa tiedostot

Kun muutokset on tehty tiedoston `CrmTranslations.xml`, se on pakattava zip-muotoon yhdessä tiedoston `[Content_Types].xml` kanssa. Valitse *molemmat tiedostot* ja avaa sitten pikavalikko hiiren kakkospainikkeella. Valitse pikavalikosta **Lähetä kohteeseen** > **Pakattu kansio (zip-tiedosto)**.

### <a name="import-the-files"></a>Tuo tiedostot

Valitse **Käännökset** > **Tuo käännökset** saman hallitsemattoman ratkaisun valikosta, josta veit käännökset. 

![Tuo käännökset](media/import-translations.png)

Valitse tiedosto, joka sisältää pakatun käännetyn tekstin, ja valitse **Tuo**.

![Tuo valittu tiedosto](media/import-translated-text-dialog.png)

Kun käännetty teksti on tuotu, julkaise kaikki mukautukset, niin näet sovellukseen tai sovelluksiin tehdyt muutokset.

## <a name="community-tools"></a>Yhteisötyökalut

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) on XrmToolBox-yhteisön kehittämä työkalu. Easy Translatorilla voit viedä ja tuoda käännöksiä yhdessä kontekstitiedon kanssa. 

> [!NOTE]
> Microsoft ei tue yhteisön kehittämiä työkaluja.
> Jos sinulla on kysyttävää työkalusta, ota yhteyttä sen julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com).


## <a name="next-steps"></a>Seuraavat vaiheet
[Organisaation alue- ja kieliasetukset](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)<br />
[Järjestelmän entiteettiviestien muokkaaminen](../common-data-service/edit-system-entity-messages.md)

