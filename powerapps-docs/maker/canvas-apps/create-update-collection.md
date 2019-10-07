---
title: Kokoelman luominen ja päivittäminen kangas sovelluksessa | Microsoft Docs
description: Luo kokoelma pohjaan perustuvassa sovelluksessa, lisää kohteita kokoelmaan ja poista niistä yksi tai kaikki kohteet
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 01/28/2019
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 375c4f19ed7715eed662c8456c539d5590c9f1ec
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71993197"
---
# <a name="create-and-update-a-collection-in-a-canvas-app"></a>Luo ja Päivitä kokoelma pohjaan sovelluksena

Kokoelman avulla voit tallentaa tietoja, joita käyttäjät voivat hallita sovelluksessasi. Kokoelma on ryhmä kohteita, jotka ovat samankaltaisia, kuten tuote luettelon tuotteet. Lisä tietoja erityyppisten muuttujien, kuten kokoelmien, tyypeistä: [Tutustu pohjaan ja sovellukseen](working-with-variables.md).

## <a name="prerequisites"></a>Edellytykset

- [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
- Luo sovellus tai avaa olemassa oleva sovellus PowerAppsissa.
- Lue, miten [ohjausobjekti määritetään](add-configure-controls.md) PowerAppsissa.

## <a name="create-a-multicolumn-collection"></a>Monisarakkeisen kokoelman luominen

1. Lisää PowerApps Studio **teksti syöte** -ohjaus objekti.

    ![Lisää teksti syöte-ohjaus objekti](./media/create-update-collection/add-textbox.png)

1. Nimeä ohjaus objekti uudelleen valitsemalla vasemmassa siirtymis ruudussa sen kolme pistettä, valitsemalla **Nimeä uudelleen**ja kirjoittamalla sitten **ProductName**.

    ![Ohjaus objektin nimeäminen uudelleen](./media/create-update-collection/rename-textbox.png)

1. Lisää **avattava luettelo** -ohjaus objekti.

    ![Lisää avattava luettelo](./media/create-update-collection/add-dropdown.png)

1. Nimeä **avattava** luettelo-ohjaus objektin **värit**uudelleen ja varmista, että **Items** -ominaisuus on valittuna ominaisuus-kohdassa.

    ![Kohteiden ominaisuus](./media/create-update-collection/items-property.png)

1. Korvaa kaava rivillä **Dropdownsample** tällä lausekkeella:

    `["Red","Green","Blue"]`

1. Lisää **painike** -ohjaus objekti, määritä sen **Text** -ominaisuudeksi **"Add"** ja määritä sen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    Collect(
        ProductList,
        {
            Product: ProductName.Text,
            Color: Colors.Selected.Value
        }
    )
    ```

1. Paina F5- **näppäintä, kirjoita**tekstiä tuote nimi-kohtaan, valitse **väri**-vaihto ehto ja valitse sitten **Lisää**.

    ![Sovelluksen esikatselu](./media/create-update-collection/preview-add.png)

1. Toista edellinen vaihe vähintään kaksi kertaa ja paina sitten ESC-näppäintä.

1. Näytä luomasi kokoelma valitsemalla **tiedosto-** valikosta **kokoelmat** .

    ![Näytä kokoelma](./media/create-update-collection/show-collection.png)

## <a name="show-a-collection"></a>Näytä kokoelma

1. Lisää pystysuuntainen **valikoima** -ohjaus objekti.

    ![Lisää pystysuuntainen valikoima](./media/create-update-collection/add-gallery.png)

1. Valitse valikoiman **Items** -ominaisuudeksi **productList**.

1. Valitse **tiedot** -ruudussa alaotsikko-kentän arvoksi **väri**ja valitse otsikko-kentäksi **tuote**.

    ![Valitse valikoiman kohteet-ominaisuus ja muuta siinä olevia kenttiä](./media/create-update-collection/configure-gallery.png)

1. Sulje **tiedot** -ruutu, valitse valikoima ja määritä sitten **ulkoasu** -kentän arvoksi **otsikko ja alaotsikko**.

    ![Valitse valikoiman kohteet-ominaisuus ja muuta siinä olevia kenttiä](./media/create-update-collection/change-layout.png)

    Näyttösi muistuttaa tätä esimerkkiä:

    ![Ensimmäisen näytön esimerkki](./media/create-update-collection/screen-example1.png)

## <a name="remove-one-or-all-items"></a>Poista yksi tai kaikki kohteet

1. Valitse valikoima malli napsauttamalla tai napauttamalla valikoiman alaosan lähellä ja napsauttamalla tai napauttamalla kynä kuvaketta vasemmassa yläkulmassa.

    ![Valitse valikoima malli](./media/create-update-collection/select-template.png)

1. Lisää **roska kori** -kuvake valikoima malliin.

    ![Lisää roska kori-kuvake](./media/create-update-collection/trash-icon.png)

1. Määritä kuvakkeen **onselect** -ominaisuudeksi Tämä kaava:

    `Remove(ProductList, ThisItem)`

1. Lisää valikoima-ruutuun painike, määritä sen **Text** -ominaisuudeksi **"Clear"** ja määritä sen **onselect** -ominaisuudeksi Tämä kaava:

    `Clear(ProductList)`

1. Pidä Alt-näppäintä painettuna ja Poista kohde kokoelmasta valitsemalla kohteen **roska kori** kuvake tai Poista kaikki kohteet kokoelmasta valitsemalla **Tyhjennä** -painike.

## <a name="put-a-sharepoint-list-into-a-collection"></a>SharePoint-luettelon asettaminen kokoelmaan

1. [Yhdistä SharePoint-luetteloon](connections/connection-sharepoint-online.md#create-a-connection).

1. Lisää painike ja määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä funktio. Korvaa *ListName* SharePoint-luettelon nimellä:<br>

    `Collect(MySPCollection, ListName)`

    Tämä funktio luo kokoelman, jonka nimi on **MySPCollection** ja joka sisältää samat tiedot kuin SharePoint-luettelokin.

1. Pidä Alt-näppäintä painettuna ja valitse painike.

1. valinnainen Jos haluat esikatsella luomaasi kokoelmaa, valitse **tiedosto-** valikosta **kokoelmat** .

Saat lisä tietoja siitä, miten voit näyttää tietoja SharePoint-luettelosta (kuten päivä määristä, valinnoista ja henkilöistä) valikoimassa: [Näytä valikoiman luetteloiden sarakkeet](connections/connection-sharepoint-online.md#show-list-columns-in-a-gallery). Tietoja siitä, miten tiedot näytetään lomakkeessa (avattavien luetteloiden, päivämäärä valitsimien ja henkilöiden poimintaan): [Muokkaa lomaketta ja Näytä lomake-ohjaus objektia](controls/control-form-detail.md).

## <a name="next-steps"></a>Seuraavat vaiheet

- Tarkasta **Collect** -funktiolla [viittaus-aihe](functions/function-clear-collect-clearcollect.md) .
- Lue, miten voit muotoilla kokoelman tietoja käyttämällä [Addcolumns-, DropColumns-, RenameColumns-ja ShowColumns](functions/function-table-shaping.md) -funktioita.
