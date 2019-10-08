---
title: Riippuvien avattavien luetteloiden luominen kangas sovelluksessa | Microsoft Docs
description: Luo Powerappsissa avattava luettelo, joka suodattaa toisen avattavan luettelo ruudun kangas sovelluksessa.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/04/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 57abde44541a2a1e40e3a8ffc55a89e37a8c6478
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985762"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-dependent-drop-down-lists-in-a-canvas-app"></a>Riippuvien avattavien luetteloiden luominen kangas sovelluksessa

Kun luot riippuvaisten (tai limittäisten) avattavien luetteloiden, käyttäjät valitsevat vaihto ehdon luettelosta, jos haluat suodattaa toisen luettelon asetuksia. Monet organisaatiot luovat riippuvaisten luetteloiden avulla käyttäjiä täyttämään lomakkeita entistä tehokkaammin. Käyttäjät voivat esimerkiksi valita maan tai alueen kaupunki luettelon suodattamiseksi, tai käyttäjät voivat valita luokan näyttämään vain kyseisen luokan koodit.

Paras käytäntö on luoda tieto lähde "Parent"-ja "Child"-luetteloiden arvoille (esimerkiksi maat/alueet ja kaupungit), jotka ovat erillään tieto lähteestä, jonka käyttäjät päivittävät sovelluksen avulla. Jos otat tämän lähestymis tavan käyttöön, voit käyttää samoja pää-ja alitietoja useammassa kuin yhdessä sovelluksessa, ja voit päivittää nämä tiedot julkaisematta uudelleen sovellusta tai sovelluksia, jotka käyttävät niitä. Voit suorittaa saman tuloksen käyttämällä kokoelmaa tai staattisia tietoja, mutta sitä ei suositella yritys tilanteisiin.

Tämän ohje aiheen skenaariossa Tallenna työn tekijät lähettävät ongelmia **tapa** ukset-listaan lomakkeen kautta. Työn tekijät määrittävät sen säilön sijainnin, jossa tapaus sattui, mutta myös kyseisen sijainnin osaston. Kaikilla sijainneissa ei ole samoja osastoja, joten **sijaintien** luettelon avulla varmistetaan, että työn tekijät eivät voi määrittää osastoa sijainnille, jolla ei ole kyseistä osastoa.

Tässä ohje aiheessa käytetään Microsoft SharePoint-luetteloita tieto lähteinä, mutta kaikki taulukkomuotoiset tieto lähteet toimivat samalla tavalla.

## <a name="create-data-sources"></a>Luo tieto lähteitä

**Sijainnit** -luettelossa näkyvät kunkin sijainnin osastot.

| Location | Department |
|----------------|------------------|
| Eganville      | Leipomo           |
| Eganville      | Deli             |
| Eganville      | Tuottaa          |
| Renfrew        | Leipomo           |
| Renfrew        | Deli             |
| Renfrew        | Tuottaa          |
| Renfrew        | Apteekki         |
| Renfrew        | Kukanvalkoinen           |
| Pembroke       | Leipomo           |
| Pembroke       | Deli             |
| Pembroke       | Tuottaa          |
| Pembroke       | Kukanvalkoinen           |

Tapaus **luettelossa näkyvät kunkin tapa uksen** yhteys tiedot ja tiedot. Luo päivämäärä sarake **päivämäärä** sarakkeeksi, mutta luo Muut sarakkeet **yhdeksi teksti** sarakkeeksi, jotta voit yksinkertaistaa määritystä ja välttää [delegointi](./delegation-overview.md) varoituksia Microsoft PowerApps.

| Etunimi | Suku nimi | Puhelin numero     | Location | Department | Kuvaus       | Date      |
|------------|-----------|------------------|----------------|------------|-------------------------|-----------|
| Tonya       | Cortez   | (206) 555-1022 | Eganville      | Tuottaa    | Minulla oli ongelma...   | 2/12/2019 |
| Mooses     | Laflamme     | (425) 555-1044 | Renfrew        | Kukanvalkoinen     | Koin ongelman... | 2/13/2019 |

Oletus arvon mukaan mukautetut SharePoint-luettelot sisältävät **otsikko** sarakkeen, jota ei voi nimetä uudelleen tai poistaa, ja sen on sisällettävä tiedot, ennen kuin voit tallentaa kohteen luetteloon. Jos haluat määrittää sarakkeen niin, että se ei edellytä tietoja:

1. Valitse oikean yläkulman lähellä ratas kuvake ja valitse sitten **luettelosta asetukset**.
1. Valitse **Asetukset** -sivulla sarake luettelosta **otsikko** .
1. Valitse **edellytä, että tämä sarake sisältää tietoja**, valitse **ei**.

Tämän muutoksen jälkeen voit ohittaa **otsikko** -sarakkeen, tai voit [poistaa sen](https://support.office.com/article/edit-a-list-column-in-sharepoint-online-77130c2e-76d1-4f80-af8b-4c6f47b264b8) oletus näkymästä, jos vähintään yksi muu sarake tulee näkyviin.

## <a name="open-the-form"></a>Avaa lomake

1. Avaa **tapa** ukset-lista ja valitse sitten **powerapps** > **Mukauta lomakkeita**.

    > [!div class="mx-imgBorder"]
    > ![Avaa tapa ukset-lista ja valitse sitten PowerApps > Mukauta lomakkeita.](./media/dependent-drop-down-lists/open-form.png "Avaa tapa ukset-lista ja valitse sitten PowerApps > Mukauta lomakkeita.")

    Selain väli lehti avautuu, ja oletus lomake on PowerApps Studio.

1. valinnainen Vie hiiren osoitin **kentät** -ruudun **otsikko** -kentän päälle, valitse esiin tulevassa kolme pistettä (...) ja valitse sitten **Poista**.

    Jos olet sulkenut **kentät** -ruudun, voit avata sen uudelleen valitsemalla vasemmassa siirtymis palkissa **SharePointForm1** ja valitsemalla sitten oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdestä **Muokkaa kenttiä** .

1. valinnainen Poista **Liitteet** -kenttä lomakkeesta toistamalla edellinen vaihe.

    Näkyviin tulee lomake, joka sisältää vain lisäämäsi kentät.

    > [!div class="mx-imgBorder"]
    > ![Form ilman title-ja Attachments-kenttiä @ no__t-1

## <a name="replace-the-controls"></a>Korvaa ohjaus objekti

1. Valitse **kentät** -ruudussa **Sijainti**-kohdan vieressä oleva nuoli.

    Jos olet sulkenut **kentät** -ruudun, voit avata sen uudelleen valitsemalla vasemmassa siirtymis palkissa **SharePointForm1** ja valitsemalla sitten oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdestä **Muokkaa kenttiä** .

1. Avaa **ohjaus objekti tyyppi** -luettelosta ja valitse sitten **Sallitut arvot**.

    > [!div class="mx-imgBorder"]
    > ![Sallitut arvot @ no__t-1

    Syöttö mekanismi muuttuu **avattavasta** ohjaus objektille.

1. Toista nämä vaiheet **osasto** kortille.

## <a name="add-the-locations-list"></a>Lisää sijainnit-luettelon

1. Valitse **näytä** > **tieto lähteet** > **Lisää tieto lähde**.

1. Valitse tai luo SharePoint-liittymä ja määritä sitten toimi paikka, joka sisältää **sijainnit** -luettelon.

1. Valitse kyseisen luettelo ruudun valinta ruutu ja valitse sitten **Yhdistä**.

    > [!div class="mx-imgBorder"]
    > ![Tietoruutu @ no__t-1

    Yhteyksien luettelossa näytetään **tapa** ukset-luettelo, johon lomake perustuu, ja **sijainnit** -luettelo, joka tunnistaa lomakkeen sijainnit ja osastot.

    > [!div class="mx-imgBorder"]
    > ![Sharepointin tieto lähteet @ no__t-1

## <a name="unlock-the-cards"></a>Poista korttien lukitus

1. Valitse **Sijainti** kortti, valitse **lisä asetukset** -väli lehti oikeanpuoleisessa ruudussa ja **Muuta ominaisuuksia valitsemalla Avaa**.

1. Toista edellinen vaihe **osaston** kortille.

## <a name="rename-the-controls"></a>Ohjaus objektien nimeäminen uudelleen

Jos nimeät ohjaus objektin uudelleen, voit tunnistaa ne helpommin, ja esimerkkejä on helpompi seurata. Jos haluat löytää muita parhaita käytäntöjä, tarkista [koodaus standardit ja ohjeistojen tekninen raportti](https://aka.ms/powerappscanvasguidelines).

1. Valitse **Sijainti** kortissa **avattava** luettelo-ohjaus objekti.

1. Nimeä valittu ohjaus objekti uudelleen oikean ruudun yläosassa kirjoittamalla tai liittämällä **Ddlocation**.

    > [!div class="mx-imgBorder"]
    > ![Ohjaus objektin uudelleennimeäminen @ no__t-1

1. Toista kaksi edellistä vaihetta **osaston** kortissa ja nimeä **avattava** luettelo-ohjaus objekti uudelleen **ddendepartment**-arvoksi.

## <a name="configure-the-locations"></a>Määritä sijainnit

1. Valitse **ddadencation** - **kohteen Items** -ominaisuudeksi Tämä kaava:

    `Distinct(Locations; Location)`

1. valinnainen Pidä Alt-näppäintä painettuna ja avaa **Ddacation**ja vahvista, että luettelossa näkyvät kolme sijaintia.

## <a name="configure-the-departments"></a>Määritä osastot

1. Valitse **Dddepartment**ja valitse sitten oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdestä **depends on.**

1. Varmista **pääohjaus objektin**alla, että **ddlocation** näkyy ylemmässä luettelossa ja **tulos** näkyy alemmassa luettelossa.

    > [!NOTE]
    > Jos et halua täsmäyttää merkki jonoa, mutta tieto rivin todellisesta TUNNUKSESTA, valitse **tunnus** **tuloksen**sijaan.

1. Valitse **vastaava kenttä**-kohdassa **sijainnit** Yläluettelosta, valitse **Sijainti** alemmassa listassa ja valitse sitten **Käytä**.

    > [!div class="mx-imgBorder"]
    > ![Riippuu linkistä @ no__t-1

    **Dddepartment** - **kohteen Items** -ominaisuudeksi määritetään Tämä kaava:

    `Filter(Locations; Location = ddLocation.Selected.Result)`

    Tämä kaava suodattaa **Ddendepartment** -kohteiden kohteet sen perusteella, mitä käyttäjä valitsee **Ddindlocation**-kohteessa. Tällaisella kokoonpanolla varmistetaan, että osastojen "alatason" luettelo kuvastaa sen "Parent"-sijainnin tietoja, kuten SharePointin **sijainnit** -luettelo määrittää.

1. Avaa oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdeltä **arvo**-kohdan vieressä oleva luettelo ja valitse sitten **osasto**.

    Tämä vaihe määrittää näyttö tekstin asetukset SharePointin **sijainnit** -luettelon **osasto** -sarakkeesta.

    > [!div class="mx-imgBorder"]
    > ![Osaston arvo @ no__t-1

## <a name="test-the-form"></a>Testaa lomaketta

Kun pidät Alt-näppäintä painettuna, avaa sijainti luettelo, valitse yksi, avaa osastojen luettelo ja valitse sitten yksi.

Sijaintien ja osastojen luettelot vastaavat SharePointin **sijainnit** -luettelon tietoja.

> [!div class="mx-imgBorder"]
> ![Avaa sijaintien luettelo, muuta valintaa Renfrew-kohteesta Pembroke-kohteeksi ja avaa sitten osastojen luettelo @ no__t-1

## <a name="save-and-open-the-form-optional"></a>Tallenna ja avaa lomake (valinnainen)

1. Avaa **tiedosto** -valikko ja valitse sitten **Tallenna** > **Julkaise SharePointiin** > **Julkaise SharePointiin**.

1. Valitse vasemmassa yläkulmassa, paluunuoli ja valitse sitten **Takaisin SharePointiin**.

1. Avaa mukautettu lomakkeesi valitsemalla komentopalkissa **Uusi**.

## <a name="faq"></a>UKK

**En näe mitään tietoja: lähteet ovat tyhjiä tai niissä on vääriä tietoja.**
Varmista, että näytät oikean kentän ohjaus objektille jommallakummalla seuraavista tavoista:

- Valitse avattava luettelo ja valitse sitten **arvo** -ominaisuus oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdestä.

    > [!div class="mx-imgBorder"]
    > ![Avattavasta vaihto-valikosta @ no__t-1

- Valitse yhdistelmä ruutu ja varmista, että ensisijainen teksti on kenttä, jonka haluat näyttää.

    > [!div class="mx-imgBorder"]
    > ![Vaihda yhdistelmä ruutua @ no__t-1

**Avattava lapseni-luettelo sisältää kohteiden kaksoiskappaleita.**
Tämä oire aiheutuu todennäköisesti **haku** sarakkeen käyttämisestä SharePointissa tai Powerappsin **Choices** -funktiolla. Jos haluat poistaa päällekkäisyyden, kääri **erillinen** -funktiolla oikein palauttavien tietojen ympärille. Lisätietoja: [DISTINCT-funktiolla](functions/function-distinct.md).

## <a name="known-limitations"></a>Tunnetut rajoitukset

Tämä määritys on käytettävissä **avattavissa** ohjaus objekteissa sekä **yhdistelmä ruutu** -ja **luettelo ruutu** -ohjaus objekteissa, jotka sallivat yhden valinnan kerrallaan. Et voi käyttää **depends-** määritystä mihinkään näistä ohjaus objekteista, jos ne sallivat useita valintoja. Tätä lähestymis tapaa ei suositella käytettäessä asetus joukkoja Common Data Service.

**Depends on** Configuration ei tue staattisia tietoja tai kokoelmia. Jos haluat määrittää riippuvuussuhteessa olevia avattavia luetteloita näiden lähteiden avulla, Muokkaa lauseketta suoraan kaava rivillä. Lisäksi PowerApps ei tue kahden vaihtoehto kentän käyttämistä SharePointissa ilman vastaavaa tieto taulukkoa, etkä voi määrittää **vastaavaa kenttää** tässä käyttö liittymässä.
