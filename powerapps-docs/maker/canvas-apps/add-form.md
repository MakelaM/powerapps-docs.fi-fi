---
title: Näytä, Muokkaa tai pohjaan perustuva sovellus tietueen lisääminen | Microsoft Docs
description: Käytä pohjaan perustuvan sovelluksen lomaketta tietueen näyttämiseen, muokkaamiseen tai lisäämiseen tietolähteesi taulukosta.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/06/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e94aa48ed3fba1b4591e196e3b81d3fb0f76666f
ms.sourcegitcommit: 4ed29d83e90a2ecbb2f5e9ec5578e47a293a55ab
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "63321438"
ms.PowerAppsDecimalTransform: true
---
# <a name="show-edit-or-add-a-record-in-a-canvas-app"></a>Näytä, Muokkaa tai pohjaan perustuva sovellus tietueen lisääminen

Pohjaan perustuvassa sovelluksessa, Lisää ja määritä **[näytön](controls/control-form-detail.md)** lomake-ohjausobjekti tietueen kaikkien kenttien näyttämiseksi voit myös lisätä ja määrittää **[Muokkaa](controls/control-form-detail.md)** lomakkeen ohjausobjektin muokata mitä tahansa tietueen kenttää, lisätä tietueen ja tallentaa muutokset takaisin tietolähteeseen.

## <a name="prerequisites"></a>Edellytykset

- Lue, miten [voit lisätä ja määrittää ohjausobjektin](add-configure-controls.md) PowerAppsissa.
- Lataa [tämä Excel-tiedosto](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), joka sisältää tämän opetusohjelman näytetiedot.
- Lataa Excel-tiedosto [pilvitallennuspalveluun](connections/cloud-storage-blob-connections.md), kuten OneDrive for Business -palveluun.
- Luo tai avaa sovellus puhelinsovellus [Lisää yhteys](add-data-connection.md) - **FlooringEstimates** taulukko Excel-tiedoston.

    Voit lisätä lomakkeen tablettisovellus, mutta se ei vastaa tässä ohjeaiheessa, koska lomake on kolme saraketta oletuksena.

- Jos avaat olemassa olevan sovelluksen [Lisää näyttö](add-screen-context-variables.md) siihen.

## <a name="add-a-form-and-show-data"></a>Lomakkeen lisääminen ja tietojen näyttäminen
1. Lisää tyhjä näyttö **[avattava](controls/control-drop-down.md)** ohjausobjekti ja anna sille **ChooseProduct**.

    > [!NOTE]
   > Jos et ole varma, kuinka ohjausobjekteja lisätään, nimetään uudelleen tai kuinka niille määritetään ominaisuus, katso [Ohjausobjektien lisääminen ja määrittäminen](add-configure-controls.md).

1. Käyttöön **ominaisuudet** välilehti oikeanpuoleisessa ruudussa määrittää **kohteet** - `FlooringEstimates` ja **arvo** - `Name`.

    ![Lomakkeen Items-ominaisuuden asettaminen](./media/add-form/items-property.png)

    Luettelossa näytetään tietolähteeltä saadut lattiatuotteiden nimet.

1. Lisää **Muokkaa** lomake-ohjausobjekti, siirrä se kohdan **ChooseProduct**, ja muuta kokoa niin, se kattaa suurimman osan näytöstä.

    ![Lomakkeen lisääminen](./media/add-form/add-a-form.png)

    > [!NOTE]
   > Tässä aiheessa kuvataan **Muokkaa** lomake-ohjausobjekti, mutta samankaltaisia periaatteet pätevät **Näytä** lomake-ohjausobjekti.

1. Määritä lomakkeen **[DataSource](controls/control-form-detail.md)** ominaisuudeksi **FlooringEstimates** ja sen **[kohteen](controls/control-form-detail.md)** -ominaisuuden arvoksi Tämä kaava:

    `First(Filter(FlooringEstimates; Name=ChooseProduct.Selected.Value))`

   Tällä kaavalla määritetään, että lomakkeen määritysten suorittamisen jälkeen siinä näkyvät tietueet, jotka käyttäjä valitsee kohdassa **ChooseProduct**.

1. Valitse **ominaisuudet** välilehti oikeanpuoleisessa ruudussa Valitse **Muokkaa kenttiä**.

    ![Muokkaa kenttiä](./media/add-form/edit-fields.png)

1. Valitse **Kentät**-ruudussa **Lisää kenttä**, valitse kunkin kentän valintaruutu ja valitse sitten **Lisää**.

    ![Lisää kenttiä](./media/add-form/add-fields.png)

1. Valitse kolme pistettä (...) kohdan **Lisää kenttä**, valitse **Kutista kaikki**, ja vedä sitten **nimi** luettelon ylimmäksi.

    ![Siirrä kenttä](./media/add-form/move-field.png)

    **Muokkaa** lomake-ohjausobjekti päivittyy muutoksen mukaisesti.

    ![Näytä lomake](./media/add-form/show-form1.png)

## <a name="set-the-card-type-for-a-field"></a>Kortin tyypin asettaminen kentälle
1. - **Kentät** ruudusta, laajenna **hinta** kentän valitsemalla sen alanuolta.

1. Avaa **ohjausobjekti tyyppi** luettelo ja valitse sitten **Muokkaa liukusäädintä**.

    ![Muokkaa liukusäädintä](./media/add-form/edit-slider.png)

    Lomakkeen **hinta** kenttä näkyy **liukusäätimen** ohjausobjektin sijaan **Tekstisyöte** ohjausobjektin.

1. (valinnainen) Voit muuttaa ohjausobjektin saman prosessia **yleiskatsaus** kenttä **Muokkaa monirivistä tekstiä** ohjausobjektin.

## <a name="edit-form-only-save-changes"></a>(Vain Muokkaa lomaketta) Muutosten tallentaminen

1. Anna lomakkeelle **EditForm**.

1. Lisää **[painike](controls/control-button.md)** ohjausobjekti ja määritä sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:

   `SubmitForm(EditForm)`

1. Avaa esikatselu painamalla F5-näppäintä muuttaa tuotteen nimen ja valitse sitten painike, jonka loit.

    **[SubmitForm](functions/function-form.md)** funktio tallentaa muutokset tietolähteeseen.

1. (valinnainen) Sulje esikatselutila painamalla ESC-näppäintä (tai valitsemalla sulkemiskuvake oikeassa yläkulmassa).

## <a name="next-steps"></a>Seuraavat vaiheet
Lisätietoa [lomakkeiden](working-with-forms.md) ja [kaavojen](working-with-formulas.md) kanssa työskentelystä.
