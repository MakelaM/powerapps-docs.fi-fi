---
title: Luo pohjaan perustuvan sovelluksen riippuvaiset avattavasta | Microsoft Docs
description: Luo Powerappsissa avattavan luettelon, joka suodattaa toisen avattavan luettelon pohjaan perustuvassa sovelluksessa.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/04/2019
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: dc1b3b87e2c1fdcd4ab7eb6634db7f9e7c049ec2
ms.sourcegitcommit: f84095d964fe1fe5cc5290e5edbee284bd768e1e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/18/2019
ms.locfileid: "59042751"
---
# <a name="create-dependent-drop-down-lists-in-a-canvas-app"></a>Luo pohjaan perustuva sovellus riippuvaiset avattavia luetteloita

Kun luot riippuvaiset (tai CSS) avattavia luetteloita, käyttäjät valita vaihtoehto-luettelon toisen luettelon asetukset. Monet organisaatiot luoda riippuvaiset avulla käyttäjät voivat täyttää lomakkeita entistä tehokkaammin. Esimerkiksi käyttäjien valita maata tai aluetta, voit suodattaa kaupungit tai käyttäjien valita luokan näyttämään vain koodit luokan.

Paras käytäntö on luoda ”ylätasoksi” ja ”lapsi” arvojen tietolähteeseen (esimerkiksi maat tai alueet ja kaupungit) eli erillään tietolähde, joka käyttäjät päivittää sovelluksen avulla. Jos otat tämän lähestymistavan, voit käyttää samaa pää- ja tiedot useampi kuin yksi sovellus ja voit päivittää tiedot ilman uudelleenjulkaisemista sovellusta tai sovelluksia, jotka käyttävät niitä. Voit tehdä samat käyttämällä kokoelman tai staattisia tietoja, mutta se ei ole suositeltavaa yrityksen skenaarioita varten.

Tässä aiheessa skenaarion tallentaa työntekijät Lähetä ongelmat **tapaukset** luettelon lomakkeen kautta. Työntekijät määrittää ei vain säilön sijainnin ilmenivät mutta jotka myös osasto sisällä kyseiseen sijaintiin. Kaikki sijainnit on sama Osastot, joten **sijaintien** luettelon avulla voidaan varmistaa, että työntekijät ei voi määrittää sijaintiin, joka ei ole osaston osasto.

Tässä aiheessa käytetään tietolähteenä Microsoft SharePoint-luetteloihin, mutta kaikki taulukkomuotoisia tietolähteitä toimivat samalla tavalla.

## <a name="create-data-sources"></a>Luo tietolähteitä

A **sijaintien** luettelossa näytetään kussakin osastojen.

| Location | Department |
|----------------|------------------|
| Eganville      | Leipomoon           |
| Eganville      | Deli             |
| Eganville      | Tuottaa          |
| Renfrew        | Leipomoon           |
| Renfrew        | Deli             |
| Renfrew        | Tuottaa          |
| Renfrew        | Apteekin         |
| Renfrew        | Kukikas           |
| Pembroke       | Leipomoon           |
| Pembroke       | Deli             |
| Pembroke       | Tuottaa          |
| Pembroke       | Kukikas           |

**Tapaukset** luettelossa näytetään yhteystiedot ja kunkin tapauksen tietoja. Kuin päivämäärä-sarakkeen luominen **päivämäärä** saraketta, mutta luoda muita sarakkeita kuin **Yksi tekstirivi** määritystä ja vältä sarakkeita [delegointia](./delegation-overview.md) varoitukset Microsoft PowerApps.

| Etunimi | Sukunimi | Puhelinnumero     | Location | Department | Kuvaus       | Date      |
|------------|-----------|------------------|----------------|------------|-------------------------|-----------|
| Tonya       | Cortez   | (206) 555 - 1022 | Eganville      | Tuottaa    | Minulla oli ongelma...   | 2/12/2019 |
| Moses     | Laflamme     | (425) 555 - 1044 | Renfrew        | Kukikas     | Olen kohtasi ongelman... | 2/13/2019 |

Mukautettuja SharePoint-luetteloita sisältävät oletusarvoisesti **otsikko** sarake ei voi nimetä uudelleen tai poistaa, että niissä on tietoja, ennen kuin voit tallentaa kohde luettelosta. Voit määrittää sarakkeen, niin, että se ei tarvitse tiedot seuraavasti:

1. Oikeassa yläkulmassa oleva rataskuvake ja valitse sitten **Luetteloasetukset**.
1. Valitse **asetukset** sivulla **otsikko** luettelossa olevien sarakkeiden.
1. Valitse **edellyttävät, että sarake sisältää tietoa**, valitse **ei**.

Tämän muutoksen jälkeen voit ohittaa **otsikko** sarakkeen, tai voit [poistaa sen](https://support.office.com/article/edit-a-list-column-in-sharepoint-online-77130c2e-76d1-4f80-af8b-4c6f47b264b8) oletusnäkymän, jos vähintään yksi sarake.

## <a name="open-the-form"></a>Avaa lomake

1. Avaa **tapaukset** luettelo ja valitse sitten **Powerappsin** > **lomakkeiden**.

    > [!div class="mx-imgBorder"]
    > ![Avaa tapaukset-luettelo ja valitse sitten PowerApps > lomakkeiden mukauttaminen. ](./media/dependent-drop-down-lists/open-form.png "Avaa tapaukset-luettelo ja valitse sitten PowerApps > lomakkeiden mukauttaminen.")

    Oletuslomakkeen PowerApps Studio avautuu selaimen välilehti.

1. (valinnainen) - **Kentät** ruudussa hiirtä **otsikko** kentän, valitse kolme pistettä (...), joka näkyy ja valitse sitten **poistaa**.

    Jos olet suljettu **kentät** ruudussa voit avata sen uudelleen valitsemalla **SharePointForm1** vasemmassa siirtymispalkissa ja valitsemalla sitten **Muokkaa kenttiä** , **Ominaisuudet** välilehti oikeanpuoleisessa ruudussa.

1. (valinnainen) Toista edellinen vaihe voit poistaa **liitteet** kenttä muodossa.

    Lomake tulee näkyviin vain kentät, jotka olet lisännyt.

    > [!div class="mx-imgBorder"]
    > ![Lomakkeen otsikko ja liitteitä kentät ilman](./media/dependent-drop-down-lists/default-form.png)

## <a name="replace-the-controls"></a>Korvaa ohjausobjektit

1. - **Kentät** ruudussa Valitse nuoli kohdan **sijainti**.

    Jos olet suljettu **kentät** ruudussa voit avata sen uudelleen valitsemalla **SharePointForm1** vasemmassa siirtymispalkissa ja valitsemalla sitten **Muokkaa kenttiä** , **Ominaisuudet** välilehti oikeanpuoleisessa ruudussa.

1. Avaa **ohjausobjekti tyyppi** luettelo ja valitse sitten **sallita arvot**.

    > [!div class="mx-imgBorder"]
    > ![Sallitut arvot](./media/dependent-drop-down-lists/change-control.png)

    Syötteen mekanismi muuttuu **avattava** ohjausobjektin.

1. Toista nämä vaiheet **osasto** kortti.

## <a name="add-the-locations-list"></a>Sijaintien luettelon lisääminen

1. Valitse **Näytä** > **tietolähteet** > **tietolähde**.

1. Valitse tai luo SharePoint-yhteyden ja määritä sitten sivuston, joka sisältää **sijaintien** luettelo.

1. Valitse luettelon valintaruutu ja valitse sitten **Yhdistä**.

    > [!div class="mx-imgBorder"]
    > ![Tietoruutu](./media/dependent-drop-down-lists/select-list.png)

    Yhteydet näkyy luettelo **tapaukset** luettelon, joka perustuu lomakkeen, ja **sijaintien** luettelo, joka tunnistaa sijainnit ja osastojen muodossa.

    > [!div class="mx-imgBorder"]
    > ![SharePoint-tietolähteet](./media/dependent-drop-down-lists/data-sources.png)

## <a name="unlock-the-cards"></a>Lukituksen kortit

1. Valitse **sijainti** , kortti **lisäasetukset** välilehti oikeanpuoleisessa ruudussa ja valitse sitten **lukituksen, voit muuttaa ominaisuuksia**.

1. Toista edellinen vaihe **osasto** kortti.

## <a name="rename-the-controls"></a>Nimeä ohjausobjektit uudelleen

Jos nimeät ohjausobjektit, voi määrittää entistä helpommin ja esimerkit on helpompi seurata. Löytää muita parhaita käytäntöjä, tarkista [koodaamisen standardeja ja ohjeet tekninen raportti](https://aka.ms/powerappscanvasguidelines).

1. - **Sijainti** , kortti **avattava** ohjausobjektin.

1. Oikeanpuoleisen ruudun yläosassa nimeä kirjoittamalla tai liittämällä valitun ohjausobjektin **ddLocation**.

    > [!div class="mx-imgBorder"]
    > ![Ohjausobjektin nimeäminen uudelleen](./media/dependent-drop-down-lists/rename-control.png)

1. Toista edellisen kaksi vaiheet **osasto** kortin nimetä uudelleen **avattava** ohjausobjektin **ddDepartment**.

## <a name="configure-the-locations"></a>Määritä sijainnit

1. Määritä **kohteet** ominaisuuden **ddlocation** tämä kaava:

    `Distinct(Locations, Location)`

1. (valinnainen) Kun pidät alhaalla Alt-näppäintä, Avaa **ddLocation**, ja varmista, että luettelossa on kolme sijainteja.

## <a name="configure-the-departments"></a>Määritä yksiköiden

1. Valitse **ddDepartment**, ja sitten, **ominaisuudet** välilehti oikeanpuoleisessa ruudussa Valitse **on riippuvainen.**

1. Kohdassa **ohjausobjektin Parent**, varmista, että **ddLocation** näkyy ylempi luettelo ja **tuloksen** on alempi luettelo.

    > [!NOTE]
    > Jos et halua vastaamaan merkkijonon, mutta todellinen tunnus rivin tiedot, valitse **tunnus** sijaan **tuloksen**.

1. Valitse **Matching kentän**, valitse **sijaintien** Valitse ylempi luettelo **sijainti** alempi luettelo ja valitse sitten **Käytä**.

    > [!div class="mx-imgBorder"]
    > ![Linkki on riippuvainen](./media/dependent-drop-down-lists/depends-on.png)

    **Kohteet** ominaisuuden **ddDepartment** on asetettu tämä kaava:

    `Filter(Locations, Location = ddLocation.Selected.Result)`

    Tämä kaava suodattaa kohteet **ddDepartment** perusteella käyttäjä valitsee- **ddLocation**. Kokoonpanossa varmistaa, että osastojen ”lapsi”-luettelo päivittyy ”ylätasoksi” sen sijainnin tiedot kuin **sijaintien** luettelo SharePointissa määrittää.

1. Käyttöön **ominaisuudet** välilehti oikeanpuoleisessa ruudussa, Avaa luettelo kohdan **arvo**, ja valitse sitten **osasto**.

    Tässä vaiheessa määrittää näytettävän tekstin asetukset **osasto** sarakkeen **sijaintien** luettelo SharePointissa.

    > [!div class="mx-imgBorder"]
    > ![Osasto arvo](./media/dependent-drop-down-lists/dept-value.png)

## <a name="test-the-form"></a>Testaa lomake

Kun pidät Alt-näppäintä, Avaa luettelo sijainneista, valitse jokin, Avaa osastojen luettelo ja valitse sitten yksi.

Luettelot sijaintien ja osastojen kuvastaa tiedot **sijaintien** luettelo SharePointissa.

> [!div class="mx-imgBorder"]
> ![Avaa luettelo sijainneista, Muuta valinta Renfrew Pembroke ja avaa sitten osastojen luettelo](./media/dependent-drop-down-lists/dropdowns.gif)

## <a name="save-and-open-the-form-optional"></a>Tallenna ja Avaa lomake (valinnainen)

1. Avaa **tiedoston** valikko ja valitse sitten **Tallenna** > **Julkaise SharePointiin** > **Julkaise SharePointiin**.

1. Valitse vasemmassa yläkulmassa, paluunuoli ja valitse sitten **Takaisin SharePointiin**.

1. Avaa mukautettu lomakkeesi valitsemalla komentopalkissa **Uusi**.

## <a name="faq"></a>USEIN KYSYTYT KYSYMYKSET

**En näe mitään tietoja: lähteet ovat kaikki tyhjiä tai on virheellisiä tietoja.**
Vahvista onko näytät oikeaan kenttään ohjausobjektin jommankumman seuraavista tavoista:

- Valitse avattavasta luettelosta ja valitse sitten **arvo** ominaisuus **ominaisuudet** välilehti oikeanpuoleisessa ruudussa.

    > [!div class="mx-imgBorder"]
    > ![Muuta avattava luettelo](./media/dependent-drop-down-lists/drop-down-display-field.png)

- Valitse yhdistelmäruudun ja varmista, että ensisijainen teksti on kenttä, jonka haluat näyttää.

    > [!div class="mx-imgBorder"]
    > ![Muuta yhdistelmäruudun](./media/dependent-drop-down-lists/combo-box-display-field.png)

**Omat alikohde avattavasta luettelosta sisältää päällekkäisyyksiä.**
Tämä ongelma on todennäköisesti vuoksi käyttämällä **LookUp** sarakkeen SharePointissa tai **vaihtoehtoja** -funktio powerappsissa. Voit poistaa kohteen rivitys **Distinct** funktio palauttaa oikein tietojen ympärille. Lisätietoja: [DISTINCT-funktio](functions/function-distinct.md).

## <a name="known-limitations"></a>Tunnetut rajoitukset

Tämä määritys on käytettävissä **avattava** ohjausobjekteja, sekä **yhdistelmäruudun** ja **luetteloruutu** ohjausobjekteja, jotka sallivat kerrallaan yhden valinnan. Et voi käyttää **riippuu-** määritys jonkin näiden ohjausobjektien, jos ne Salli useita valintoja. Tämä lähestymistapa ei ole suositeltavaa käsitteleminen asetusjoukkoja tässä Common Data Service.

**Riippuu-** määritys ei tue staattisia tietoja tai kokoelmia. Määrittämään näiden tietolähteiden riippuvaiset avattavia luetteloita Muokkaa lauseketta suoraan kaavarivillä. Lisäksi PowerApps ei tue kaksi valinta-kenttiä SharePointissa ilman mitään vastaavaa taulukon ja ei voi määrittää **Matching kentän** sisällä tämän Käyttöliittymän.
