---
title: Mallipohjaisten sovellusten lokalisoitavan tekstin kääntäminen | MicrosoftDocs
description: 'Tietoja lokalisoitavan tekstin kääntämisestä niin, että se tukee useita kieliä'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="translate-localizable-text-for-model-driven-apps"></a>Mallipohjaisten sovellusten lokalisoitavan tekstin kääntäminen

Jos olet mukauttanut entiteetin tai kentän tekstiä, esimerkiksi kentän otsikkoa tai avattavan luettelon arvoja, voit antaa käyttäjille mahdollisuuden käyttää mukautettuja tekstejä heidän ensisijaisella kielellään ympäristön asennuskielen sijaan. 

Prosessi sisältää seuraavat vaiheet:
1. Muiden kielten ottaminen käyttöön ympäristössä
2. Lokalisoitavan tekstin vieminen
3. Lokalisoitavan tekstin kääntäminen
4. Lokalisoidun tekstin tuominen

## <a name="enable-other-languages-for-your-environment"></a>Muiden kielten ottaminen käyttöön ympäristössä

Jos et ole vielä ottanut kieliä käyttöön ympäristössä, voit ottaa ne käyttöön kohdan [Kielen käyttöönotto](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) vaiheiden avulla.

> [!IMPORTANT]
> Kunkin kielen käyttöönotto voi kestää useita minuutteja. Tänä aikana ympäristön muut käyttäjät eivät voi käyttää sovellusta. Ota kielet käyttöön silloin, kun siitä on vähiten haittaa muille käyttäjille.

> [!TIP]
> Kun otat käyttöön kieliä, ota huomioon kunkin kielen käytössä olevat LCID-arvot. Arvo näyttää lokalisoitavan tekstin vietyjen tietojen kielen. Kielikoodit ovat neli- tai viisinumeroisia aluekohtaisten asetusten tunnuksia. Kelvolliset aluekohtaisten asetusten tunnusten arvot löytyvät [Locale ID (LCID) -kaaviosta)](http://go.microsoft.com/fwlink/?LinkId=122128).

## <a name="export-the-localizable-text"></a>Lokalisoitavan tekstin vieminen

Vietävän lokalisoitavan tekstin vaikutusalue on hallitsematon ratkaisu, joka sisältää lokalisoitavan tekstin. Tämä voidaan tehdä vain ratkaisunhallinnan avulla

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Avaa hallitsematon ratkaisu, joka sisältää lokalisoitavan tekstin. Valitse valikkorivillä **Käännökset** > **Vie käännökset**. 

![Käännösten vieminen](media/export-localizable-text.png)

Näkyviin tulee seuraavat tiedot sisältävä ilmoitus:
> Käännöksen mukautettujen otsikoiden vieminen voi kestää useita minuutteja. Valitse vientilinkki uudelleen vasta sitten, kun ensimmäinen vienti on valmis. Haluatko varmasti suorittaa viennin nyt? 

Valitse **OK**, jos haluat jatkaa.

Kun vienti on tehty, latauskansiossa on tiedosto, jonka nimi on `CrmTranslations_{0}_{1}.zip` tai vastaava. `{0}` on ratkaisun yksilöllinen nimi ja `{1}` ratkaisun version numero.

## <a name="get-the-localizable-text-translated"></a>Lokalisoitavan tekstin kääntäminen

Voit lähettää tämän tiedoston kääntäjälle, käännöstoimistoon tai lokalisointiyritykseen.

Jos osaat kääntää teksti tai jos haluat vain nähdä muodon, voit purkaa viedyn zip-tiedoston. Se sisältää kaksi XML-tiedostoa. 
 - `[Content_Types].xml`
 - `CrmTranslations.xml`

Voit avata CrmTranslations.xml-tiedoston Microsoft Office Excelissä.

> [!TIP]
> Jos et yleensä avaa XML-tiedostoja Excelissä, voi olla helpoin avata Excel ja avata tiedosto liittämällä puretun CrmTranslations.xml-tiedoston polku.

> [!IMPORTANT]
> Varmista, että tiedostomuotoa ei muuteta. Jos tallennat tiedoston jossakin toisessa muodossa, et voi tuoda sitä takaisin.

Kun tarkastelet tietoja Excelissä, valitse **Lokalisoidut otsikot** -välilehti.

![Lokalisointia varten viety teksti](media/localized-labels-tab-exported-languages.png)

Kaikissa mukautetuissa entiteeteissä ja kentissä on tyhjiä soluja lokalisoitavaa tekstiä varten. Lisää näihin kohteisiin lokalisoidut arvot.

> [!NOTE]
> Jos olet muuttanut vakioentiteetin tai entiteettikentän näyttönimeä tai kuvausta, lokalisoidut merkkijonot vastaavat yhä alkuperäisen arvon käännöksiä. Nämä tulee lokalisoida uutta arvoa vastaaviksi.

**Näyttömerkkijonot**-välilehti sisältää tekstin, joka näytetään muissa käyttöliittymäelementeissä, kuten valintanauhan komennoissa, virhesanomissa ja lomakkeen otsikoissa.

### <a name="updating-localizable-text-in-the-base-language"></a>Lokalisoitavan tekstin päivittäminen asennuskielellä

Jos muutat minkä tahansa erityissanoman osana olevan vakioentiteetin tai entiteettikentän näyttönimeä, voit päivittää **Näyttömerkkijonot**-välilehden tiedot käyttämään mukautettua nimeä.

> [!TIP]
> Vaikka järjestelmäentiteettisanomien muokkauksessa käytettävä käyttöliittymä sisältää useita viittauksia entiteettien nimiin, se ei sisällä niitä kaikkia. Tämän tekniikan avulla voit löytää niitä lisää. Lisätietoja: [Järjestelmän entiteettisanomien muokkaaminen](../common-data-service/edit-system-entity-messages.md)

Jos esimerkiksi muutat Asiakas-entiteetin näyttönimeksi *Yritys*, voit hakea **Näyttömerkkijonot**-kohdan asennuskielen sarakkeesta seuraavia vastaavuuksia: `account`, `accounts`, `Account` ja `Accounts`. Tämän jälkeen voit korvata vastaavat soveltuvat kohdat seuraavista: `company`, `companies`, `Company` ja `Companies`.

> [!IMPORTANT]
> Älä tee tiedostossa yleistä etsi ja korvaa -toimintoa. Varmista, että vastaavat teksti todella viittaa muutettuihin nimiin.


## <a name="import-the-localized-text"></a>Lokalisoidun tekstin tuominen
Tekstin tuominen vaatii tiedostojen pakkaamisen ja niiden tuomisen järjestelmään.

### <a name="compress-the-files"></a>Tiedostojen pakkaaminen

Kun `CrmTranslations.xml`-tiedostoon on tehty muutokset, se on pakattava yhdessä `[Content_Types].xml`-tiedoston kanssa zip-muotoon. Valitse *molemmat tiedostot* ja valitse sitten hiiren oikeanpuoleinen painike. Näyttöön avautuu pikavalikko. Valitse pikavalikosta **Lähetä kohteeseen** > **Pakattu kansio (zip-tiedosto)**.

### <a name="import-the-files"></a>Tiedostojen tuominen

Siirry samaan hallitsemattomaan ratkaisuun, josta veit käännökset, ja valitse pikavalikossa **Käännökset** > **Tuo käännökset**. 

![Käännösten tuominen](media/import-translations.png)

Valitse pakatun käännetyn tekstin sisältävä tiedosto ja valitse sitten **Tuo**.

![Valitun tiedoston tuominen](media/import-translated-text-dialog.png)

Kun käännetty teksti on tuotu, voit julkaista kaikki mukautukset ja tarkistaa sovelluksiin tehdyt muutokset.

## <a name="community-tools"></a>Yhteisön työvälineet

[Easy Translator](https://www.xrmtoolbox.com/plugins/MsCrmTools.Translator/) on työkalu, jonka on kehittänyt XrmToolbox-yhteisö. Easy Translatorin avulla voit viedä ja tuoda käännökset järjestelmään tilannekohtaiset tietojen kanssa 

> [!NOTE]
> Microsoft ei tue yhteisön työkaluja.
> Jos sinulla on kysymyksiä työkalusta, ota yhteyttä julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com).


## <a name="next-steps"></a>Seuraavat vaiheet
[Organisaation alue- ja kieliasetukset](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages)<br />
[Järjestelmäentiteetin sanomien muokkaaminen](../common-data-service/edit-system-entity-messages.md)

