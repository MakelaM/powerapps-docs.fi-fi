---
title: Ratkaisujen esittely | Microsoft Docs
description: Tutustu mallisovellusten luomiseen ratkaisuilla.
services: ''
suite: powerapps
documentationcenter: na
author: JimDaly
manager: faisalmo
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/19/2018
ms.author: jdaly
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: bcf89d9c52e1e277f65f7f02013885f30862aa56
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864975"
---
# <a name="introduction-to-solutions"></a>Ratkaisujen esittely

Mukauttajat ja kehittävät luovat, paketoivat ja ylläpitävät Common Data Service for Apps -palvelua laajentavia ohjelmistoyksiköitä *ratkaisuilla*. Esimerkiksi Dynamics 365 for Sales-, Dynamics 365 for Marketing- ja Dynamics 365 for Customer Service -sovellukset koostuvat ratkaisuista. Mukauttajat ja kehittäjät jakelevat ratkaisuja, jotta organisaatiot voivat asentaa ja poistaa ratkaisujen määrittämiä liiketoiminnallisia toimintoja Common Data Service for Apps -palvelun avulla.

Jokainen Common Data Service for Apps -palveluun tai aiemmin asennettuun ratkaisuun tekemäsi mukautus on osa ratkaisua. Kaikkia tekemiäsi muutoksia seurataan ja mitkä tahansa riippuvuudet voidaan laskea. Kun viet hallitun ratkaisun, se sisältää kaikki muutokset, jotka on otettu käyttöön tässä ratkaisussa. Ne sisältyvät tiedostoon, jonka voit sitten viedä toiseen Common Data Service for Apps -ympäristöön.

Jos aiot siirtää mukautuksia tai laajennuksia eri Common Data Service for Apps -ympäristöjen välillä tai jakaa ratkaisuja AppSourcen avulla, sinun täytyy ymmärtää, miten ratkaisut toimivat.

## <a name="managed-and-unmanaged-solutions"></a>Hallitut ja hallitsemattomat ratkaisut

Ratkaisut voidaan jakaa *hallittuihin* ja *hallitsemattomiin*.

**Hallittu** ratkaisu on valmis ratkaisu, joka on tarkoitettu jaeltavaksi ja asennettavaksi. 
- Et voi muokata hallitun ratkaisun komponentteja.
- Et voi viedä hallittua ratkaisua.
- Voit lisätä hallitun ratkaisun komponentteihin hallitsemattomia mukautuksia. Kun teet näin, luot riippuvuuden hallitsemattomien mukautusten ja hallitun ratkaisun välille. Kun riippuvuus on olemassa, hallitun ratkaisun asennusta ei voi poistaa, ennen kuin poistat riippuvuuden.
- Kun hallittu ratkaisu poistetaan (sen asennus poistetaan), myös kaikki siihen sisältyvät mukautukset ja laajennukset poistetaan.

  > [!IMPORTANT]
  > Kun poistat hallitun ratkaisun asennuksen, menetät seuraavat tiedot: menetät tiedot, jotka tallennetaan mukautettuihin entiteetteihin, jotka ovat osa hallittua ratkaisua, ja tiedot, jotka tallennetaan mukautettuihin määritteisiin, jotka ovat osa hallittua ratkaisua muissa entiteeteissä, jotka eivät ole osa hallittua ratkaisua.

**Hallitsematon** ratkaisu on ratkaisu, jonka kehitys on edelleen kesken tai jota ei ole tarkoitettu jaeltavaksi. 
- Kun ratkaisu on hallitsematon, voit lisätä siihen komponentteja ja poistaa siitä komponentteja. 
- Voit viedä hallitsemattoman ratkaisun, jos haluat siirtää hallitsemattomia mukautuksia ympäristöstä toiseen.
- Kun hallitsematon ratkaisu poistetaan, vain siihen sisältyvien mukautusten ratkaisusäilö poistetaan. Kaikki hallitsemattomat mukautukset pysyvät edelleen voimassa ja kuuluvat oletusratkaisuun. 
- Kun hallitsematon ratkaisu on valmis ja haluat aloittaa sen jakelun, voit viedä sen hallittuna ratkaisuna.

  > [!NOTE]
  > Et voi tuoda hallittua ratkaisua samaan ympäristöön, joka sisältää alkuperäisen hallitsemattoman ratkaisun. Jos haluat testata hallittua ratkaisua, tarvitset erillisen ympäristön, johon voit tuoda sen.

## <a name="solution-publishers"></a>Ratkaisujulkaisijat

Jokainen ratkaisu on yhdistetty ratkaisujulkaisijaan. Ratkaisujulkaisija antaa tiedot, joiden avulla voit ottaa yhteyttä siihen, sekä mukautuksen etuliitearvon. Oletusarvo on `new`.

Jos ratkaisun mihin tahansa osaan sisältyy mitä tahansa rakennemuutoksia, ratkaisujulkaisijan mukautusetuliite liitetään rakennekohteiden nimien eteen. Tämä arvo liitetään myös kaikkiin mukautettuihin toimintoihin. Tästä on hyötyä, koska tämän ansiosta tunnistat helposti, mikä ratkaisu lisäsi rakennekohteen tai mukautetun toiminnon. Ratkaisun kaikkien rakennekohteiden ja mukautettujen toimintojen ei tarvitse käyttää samaa mukautusetuliitettä, mutta suosittelemme tätä vahvasti.

> [!IMPORTANT]
> Ennen kuin aloitat ratkaisun luomisen, luo ratkaisujulkaisijan tietue ja luo uusi siihen yhdistetty ratkaisu. Varmista, että mukautusetuliite on arvo, joka soveltuu sinulle. 

Ratkaisujulkaisijan valinta on tärkeää, jos haluat julkaista päivityksiä jo jakelemiisi ratkaisuihin. Hallituissa ratkaisuissa voi ottaa käyttöön päivityksiä vain samalla julkaisijalla kuin alkuperäisessä hallitussa ratkaisussa. 

Lisätietoja: [Dynamics 365 Customer Engagementin kehittäjän opas: hallittujen ratkaisujen ylläpito > hallittujen ratkaisujen päivitysten luominen](/dynamics365/customer-engagement/developer/maintain-managed-solutions#create-managed-solution-updates)

## <a name="create-a-solution-publisher-and-solution"></a>Ratkaisujulkaisijan ja ratkaisun luominen 

Jos haluat luoda ratkaisujulkaisijan ja ratkaisun, siirry Dynamics 365:n mukautusalueelle.

[powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)

1. Valitse vasemman yläkulman *vohvelikuvake*.
2. Valitse pikaikkunassa **Kaikki sovellukset**.
3. Etsi kohta **Dynamics 365 – mukautettu sovellus**.
 Voit napsauttaa kolmen pisteen kohtaa (...) ja valita **Kiinnitä tämä sovellus**. Näin voit siirtyä sovellukseen helpommin myöhemmin.
4. Napsauta **Dynamics 365 – mukautettu sovellus** -sovellusta ja valitse.
5. Valitse **Asetukset** > **Mukautukset** > **Mukautukset**.

[home.dynamics.com](http://home.dynamics.com/)

1. Etsi **Dynamics 365 – mukautettu** -ruutu ja napsauta sitä.
2. Valitse **Asetukset** > **Mukautukset** > **Mukautukset**.

### <a name="create-a-solution-publisher"></a>Ratkaisujulkaisijan luominen

1. Valitse mukautusalueella **Julkaisijat**.
2. Valitse **Uusi**.
3. Anna julkaisijalomakkeessa **näyttönimi**. **Nimi**-arvo luodaan näyttönimen perusteella. Voit hyväksyä luodun arvon tai määrittää uuden.
4. Määritä **etuliitteen** kenttään mukautusetuliite, joka lisätään kaikkiin lisäämiisi mukautettuihin rakennekohteisiin, kun kehität ratkaisuasi. Oletusarvo on `new`. Valitse arvo, joka sopii organisaatiollesi ja jonka avulla ihmiset tunnistavat, mitkä heidän järjestelmiinsä asennetut komponentit ovat peräisin ratkaisustasi.
5. **Asetuksen arvon etuliite** luodaan valitsemasi mukautusetuliitteen perusteella. Tämä arvo liitetään kaikkiin asetusjoukon asetusten arvoihin, jotka lisäät ratkaisusi määritteisiin. Tämän arvon avulla tunnistat kaikki ratkaisuun lisäämäsi asetukset.
6. Lomakkeen **yhteystietojen** osioon voit lisätä yhteystiedot, jotka haluat tarjota ratkaisusi asentaville käyttäjille.
7. Kun olet valmis, napsauta **Tallenna ja sulje**.

### <a name="create-a-solution"></a>Ratkaisun luominen

1. Valitse mukautusalueella **Ratkaisut**.
2. Valitse **Uusi**.
3. Anna ratkaisulomakkeessa **näyttönimi**. **Nimi**-arvo luodaan näyttönimen perusteella. Voit hyväksyä luodun arvon tai määrittää uuden.
4. Etsi **Julkaisija**-kentässä julkaisija, jonka loit kohdassa [Ratkaisujulkaisijan luominen](#create-a-solution-publisher).
5. Valitse **Versio**-kentässä ratkaisullesi sopiva versionumero, esimerkiksi 1.0.0.0.
6. Kun olet valmis, napsauta **Tallenna**.

> [!IMPORTANT]
> Kun luot uuden ratkaisukomponentin, joka sisällytetään tähän ratkaisuun, käytä aina tätä ratkaisua tai toista ratkaisua, joka on yhdistetty samaan ratkaisujulkaisijaan.
> Ratkaisukomponentteja, jotka luodaan toiseen ratkaisujulkaisijaan yhdistetyssä ratkaisussa, voidaan lisätä tähän ratkaisuun, mutta niillä saattaa olla määritettynä erilaiset mukautuksen etuliitearvot.

## <a name="solution-layering"></a>Ratkaisujen kerrostaminen

On mahdollista asentaa kaksi hallittua ratkaisua, jotka ovat ristiriidassa keskenään. On myös mahdollista, että jotkin ympäristössä käyttöön otettavat mukautukset kumoavat hallitun ratkaisun. Miten tämä toimii?

Tämä toimii, koska Common Data Service for Apps arvioi hallitut ratkaisut niiden asennusjärjestyksessä ja koska kaikki mukautukset, jotka eivät kuulu hallittuun ratkaisuun, arvioidaan viimeisenä.

Seuraavasta kaaviosta näet, miten hallitut ratkaisut ja hallitsemattomat mukautukset ovat keskenään vuorovaikutuksessa ja määrittävät, mitä sovellukseen sisällytetään suoritettaessa.

![Ratkaisun kerrostamista kuvaava kaavio](media/solution-layering.png)

Tässä esimerkissä järjestelmäratkaisussa määritetty oletustoiminta kumotaan hallituilla ratkaisuilla tai sitä täydennetään niillä. Mitkä tahansa hallitsemattomat mukautukset voivat sitten kumota mukautuksia, jotka ovat silloin näkyvillä sovelluksessa, tai täydentää niitä.

Lisätietoja: [Dynamics 365 Customer Engagementin kehittäjän opas: ratkaisujen esittely > hallitsemattomat ja hallitut ratkaisut](/dynamics365/customer-engagement/developer/introduction-solutions#managed-and-unmanaged-solutions)

## <a name="managed-properties"></a>Hallitut ominaisuudet

Kun jakelet hallittua ratkaisua, kuka tahansa sen asentava voi sisällyttää siihen omia hallitsemattomia mukautuksiaan. Nämä hallitsemattomat mukautukset voidaan sitten lisätä ratkaisuun, jota joku muu jakelee ja joka perustuu sinun ratkaisuusi. Entä jos en halua, että ratkaisuani voidaan käyttää näin? Kun julkaiset hallitun ratkaisun, voit poistaa hallitun ratkaisusi komponenttien tiettyjä mukautuksia käytöstä hallituilla ominaisuuksilla.

Lisätietoja: [Dynamics 365 Customer Engagementin kehittäjän opas: hallittujen ominaisuuksien käyttäminen](/dynamics365/customer-engagement/developer/use-managed-properties)

## <a name="modular-solutions"></a>Modulaariset ratkaisut

Ratkaisujärjestelmän avulla voit luoda erillisiä komponenttijoukkoja, jotka tarjoavat tiettyjä toimintojoukkoja. Jokaisen hallitun ratkaisun voi asentaa ja sen asennuksen voi poistaa. Tällä tavoin asiakkaan käyttöönotto voidaan palauttaa alkuperäiseen tilaan. Jokainen luomasi hallittu ratkaisu suoritetaan järjestelmäratkaisun päällä. Voit käyttää myös tämän taustalla olevan ratkaisun toimintoja.

Voit myös luoda hallittuja ratkaisuja, jotka suoritetaan muiden ratkaisujen päällä. Näin voit luoda toimintojoukkoja, joita voidaan jakaa eri ratkaisujen kesken. Tällä tavalla voit luoda yhteisen moduulin ratkaisuksi useiden ratkaisujen tukemiseen sekä ylläpitää sitä. Tämän ansiosta asiakkaiden täytyy asentaa vain itselleen sopivat ratkaisut eikä sinun tarvitse sisällyttää samoja jaettuja toimintoja jokaiseen ratkaisuun. Jos sinun täytyy julkaista päivitys ratkaisulle, joka tukee useita ratkaisuja, sinun täytyy päivittää vain yhteinen moduuli.

Asiakkaat, järjestelmätoimittajat ja muut itsenäiset ohjelmistotoimittajat voivat sitten luoda omia ratkaisujaan ratkaisujesi päälle. Tällä tavoin he voivat luoda tarvitsemiaan mukautuksia.

Kun joukko liiketoiminnallisia toimintoja koostuu useista ratkaisuista, niitä kutsutaan paketeiksi. *Package Deployerilla* voit yhdistää useita ratkaisuja yhdeksi asennettavaksi yksiköksi.

## <a name="deploy-solution-packages"></a>Ratkaisupakettien käyttöönotto

*Package Deployerilla* voit luoda mukautetun asennustoiminnon paketille, joka voi sisältää 
- ratkaisutiedoston tai useita
- tietuetiedostoja tai vietyjä määritystietotiedostoja 
- mukautettua koodia, joka voidaan suorittaa ennen paketin käyttöönottoa, sen aikana tai sen jälkeen
- pakettikohtaista HTML-sisältöä, joka voidaan näyttää käyttöönottoprosessin aluksi ja lopuksi. Tämä voi olla kätevä tapa tarjota kuvaus paketilla käyttöönotettavista ratkaisuista ja tiedostoista.

Lisätietoja: [Dynamics 365 Customer Engagementin kehittäjän opas: pakettien luominen Dynamics 365 Package Deployerille](/dynamics365/customer-engagement/developer/create-packages-package-deployer).

## <a name="team-development-of-solutions"></a>Ratkaisujen tiimikehitys

Ratkaisutiedosto on yksittäinen binaaritiedosto, joka ei sovellu lähdekoodin hallintaan tai tiimikehitykseen. Ratkaisujen mukautettujen komponenttien työstäminen ei ole mahdollista useille kehittäjille.

*SolutionPackager*-työkalu ratkaisee lähdekoodin hallinnan ja tiimikehityksen ongelmat. Se tunnistaa pakatun ratkaisutiedoston yksittäiset komponentit ja purkaa ne yksittäisiksi tiedostoiksi. Työkalulla voidaan myös luoda ratkaisutiedosto uudelleen pakkaamalla aiemmin puretut tiedostot. Tämän ansiosta useat ihmiset voivat työstää itsenäisesti samaa ratkaisua ja purkaa muutoksensa yhteiseen sijaintiin. Koska ratkaisutiedoston jokainen komponentti on jaettu useaan tiedostoon, mukautuksia voidaan yhdistää siten, että aiempia muutoksia ei korvata. SolutionPackager-työkalua voidaan myös kutsua automaattisesta koontiversioprosessista. Näin voidaan luoda pakattu ratkaisutiedosto aiemmin puretuista komponenttitiedostoista ilman aktiivista Dynamics 365 -esiintymää.

Lisätietoja: [Dynamics 365 Customer Engagementin kehittäjän opas: työkalut tiimikehitykseen](/dynamics365/customer-engagement/developer/solution-tools-team-development)

### <a name="see-also"></a>Katso myös

[Common Data Service for Apps -palvelun kehittäjien yleiskatsaus](overview.md)
