---
title: Tietueen näyttäminen, muokkaaminen tai lisääminen kangas sovelluksessa | Microsoft Docs
description: Käytä pohjaan perustuvan sovelluksen lomaketta tietueen näyttämiseen, muokkaamiseen tai lisäämiseen tietolähteesi taulukosta.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/06/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ed7493dcc9c2ef5f0b84052a11dbadb0947af38e
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994118"
---
# <a name="show-edit-or-add-a-record-in-a-canvas-app"></a>Tietueen näyttäminen, muokkaaminen tai lisääminen kangas sovelluksessa

Lisää ja Määritä Näytä lomake-ohjaus objekti kangas **[sovelluksessa näyttämään tietueen](controls/control-form-detail.md)** kaikki kentät. Voit myös lisätä ja määrittää **[Muokkaa](controls/control-form-detail.md)** lomaketta-ohjaus objektin, jos haluat muokata mitä tahansa tietueen kenttää, lisätä tietueen ja tallentaa muutokset takaisin tieto lähteeseen.

## <a name="prerequisites"></a>Edellytykset

- Lue, miten [voit lisätä ja määrittää ohjausobjektin](add-configure-controls.md) PowerAppsissa.
- Lataa [tämä Excel-tiedosto](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), joka sisältää tämän opetusohjelman näytetiedot.
- Lataa Excel-tiedosto [pilvitallennuspalveluun](connections/cloud-storage-blob-connections.md), kuten OneDrive for Business -palveluun.
- Luo tai avaa sovellus puhelimille, [Lisää yhteyden](add-data-connection.md) Excel-tiedoston **Flouringin arviot** -taulukkoon.

    Voit lisätä lomakkeen Tablet-sovellukseen, mutta se ei vastaa tätä aihetta, koska lomakkeessa on oletus arvon mukaan kolme saraketta.

- Jos avaat olemassa olevan sovelluksen, [Lisää siihen näyttö](add-screen-context-variables.md) .

## <a name="add-a-form-and-show-data"></a>Lomakkeen lisääminen ja tietojen näyttäminen
1. Lisää tyhjässä näytössä **[avattava luettelo](controls/control-drop-down.md)** -ohjaus objekti ja nimeä se **chooseproduct**.

    > [!NOTE]
   > Jos et ole varma, kuinka ohjausobjekteja lisätään, nimetään uudelleen tai kuinka niille määritetään ominaisuus, katso [Ohjausobjektien lisääminen ja määrittäminen](add-configure-controls.md).

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdeltä **kohteet** `FlooringEstimates` ja **arvoksi** `Name`.

    ![Lomakkeen Items-ominaisuuden asetukset](./media/add-form/items-property.png)

    Luettelossa näytetään tietolähteeltä saadut lattiatuotteiden nimet.

1. Lisää **Muokkaa** lomaketta-ohjaus objekti, siirrä se kohtaan **chooseproduct**ja muuta lomakkeen kokoa niin, että se kattaa suurimman näytön.

    ![Lomakkeen lisääminen](./media/add-form/add-a-form.png)

    > [!NOTE]
   > Tässä ohje aiheessa kuvataan **Muokkaa** lomaketta-ohjaus objektia, mutta vastaavat periaatteet koskevat **Näytä** lomake-ohjaus objektia.

1. Valitse lomakkeen **[DataSource](controls/control-form-detail.md)** -ominaisuudeksi **Floaltingestilages** ja sen **[Item](controls/control-form-detail.md)** -ominaisuudeksi seuraava kaava:

    `First(Filter(FlooringEstimates, Name=ChooseProduct.Selected.Value))`

   Tällä kaavalla määritetään, että lomakkeen määritysten suorittamisen jälkeen siinä näkyvät tietueet, jotka käyttäjä valitsee kohdassa **ChooseProduct**.

1. Valitse oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdestä **Muokkaa kenttiä**.

    ![Muokkaa kenttiä](./media/add-form/edit-fields.png)

1. Valitse **Kentät**-ruudussa **Lisää kenttä**, valitse kunkin kentän valintaruutu ja valitse sitten **Lisää**.

    ![Lisää kenttiä](./media/add-form/add-fields.png)

1. Valitse **Lisää kenttä**-kohdan vierestä kolme pistettä (...), valitse **Kutista kaikki**ja vedä sitten **nimi** luettelon kärkeen.

    ![Siirrä kenttä](./media/add-form/move-field.png)

    **Muokkaa** lomaketta-ohjaus objekti vastaa muutoksesi.

    ![Näytä lomake](./media/add-form/show-form1.png)

## <a name="set-the-card-type-for-a-field"></a>Kortin tyypin asettaminen kentälle
1. Laajenna **kentät** -ruudussa **hinta** -kenttä valitsemalla sen alanuoli.

1. Avaa **ohjaus objekti tyyppi** -luettelosta ja valitse sitten **Muokkaa liuku säädintä**.

    ![Muokkaa liuku säädintä](./media/add-form/edit-slider.png)

    -Lomakkeen **hinta** -kentässä näytetään **liuku** säädin **teksti syöte** -ohjaus objektin sijaan.

1. valinnainen Noudata samaa prosessia, jos haluat muuttaa **Yleiskatsaus** -kentän ohjaus objektin **muokattavaksi moniriviseksi teksti-** ohjaus objektin.

## <a name="edit-form-only-save-changes"></a>(Vain Muokkaa lomaketta) Muutosten tallentaminen

1. Nimeä lomakkeen **muokkain-lomake**uudelleen.

1. Lisää **[painike](controls/control-button.md)** ohjausobjekti ja määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi seuraava kaava:

   `SubmitForm(EditForm)`

1. Avaa esikatselu painamalla F5, muuta tuotteen nimeä ja valitse sitten luomasi painike.

    **[Submitform](functions/function-form.md)** -toiminto tallentaa tekemäsi muutokset tieto lähteeseen.

1. valinnainen Sulje esikatselu painamalla ESC-näppäintä (tai valitsemalla sulkemis kuvake oikeassa yläkulmassa).

## <a name="next-steps"></a>Seuraavat vaiheet
Lisätietoa [lomakkeiden](working-with-forms.md) ja [kaavojen](working-with-formulas.md) kanssa työskentelystä.
