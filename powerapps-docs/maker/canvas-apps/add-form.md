---
title: Tietueen näyttäminen, muokkaaminen tai lisääminen taulukosta | Microsoft Docs
description: Käytä lomaketta tietueen näyttämiseen, muokkaamiseen tai lisäämiseen tietolähteesi taulukosta.
author: karthik-1
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/06/2017
ms.author: sharik
ms.openlocfilehash: b98c5d165ba6de983a874f0a34fb92c5db8a69cd
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39018947"
---
# <a name="show-edit-or-add-a-record-from-a-table-in-powerapps"></a>Tietueen näyttäminen, muokkaaminen tai lisääminen taulukosta PowerAppsissa
Lisää ja määritä **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjekti tietueen kaikkien kenttien näyttämiseksi. Voit muokata mitä tahansa tietueen kenttää (tai lisätä tietueen) ja tallentaa muutokset takaisin tietolähteeseen lisäämällä ja määrittämällä ensin **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektin.

## <a name="prerequisites"></a>Edellytykset

* Lue, miten [voit lisätä ja määrittää ohjausobjektin](add-configure-controls.md) PowerAppsissa.
* Lataa [tämä Excel-tiedosto](https://az787822.vo.msecnd.net/documentation/get-started-from-data/FlooringEstimates.xlsx), joka sisältää tämän opetusohjelman näytetiedot.
* Lataa Excel-tiedosto [pilvitallennuspalveluun](connections/cloud-storage-blob-connections.md), kuten OneDrive for Business -palveluun.
* Lisää uuteen tai olemassa olevaan sovellukseen [yhteys](add-data-connection.md) Excel-tiedoston **FlooringEstimates**-taulukkoon.
* Jos käytät olemassa olevaa sovellusta, [lisää siihen näyttö](add-screen-context-variables.md).

## <a name="add-a-form-and-show-data"></a>Lomakkeen lisääminen ja tietojen näyttäminen
1. Lisää **[Avattava luettelo](controls/control-drop-down.md)** -ohjausobjekti, anna sille nimeksi **ChooseProduct** ja aseta sen **[Items](controls/properties-core.md)**-ominaisuudeksi seuraava arvo:

    **FlooringEstimates.Name**

    > [!NOTE]
   > Jos et ole varma, kuinka ohjausobjekteja lisätään, nimetään uudelleen tai kuinka niille määritetään ominaisuus, katso [Ohjausobjektien lisääminen ja määrittäminen](add-configure-controls.md).

    Luettelossa näytetään tietolähteeltä saadut lattiatuotteiden nimet.

2. Lisää **Muokkaa lomaketta** -ohjausobjekti, siirrä se kohdan **ChooseProduct** alle ja muuta sen kokoa niin, että se kattaa suurimman osan näytöstä.

    ![Lomakkeen lisääminen](./media/add-form/add-a-form.png)

    > [!NOTE]
   > Tässä aiheessa kuvaillaan **Muokkaa lomaketta** -ohjausobjektia, mutta samanlaiset periaatteet pätevät myös **Näytä lomake** -ohjausobjektiin.

3. Aseta lomakkeen **[DataSource](controls/control-form-detail.md)**-ominaisuudeksi **FlooringEstimates** ja **[Item](controls/control-form-detail.md)**-ominaisuudeksi tämä kaava:

   **First(Filter(FlooringEstimates, Name=ChooseProduct.Selected.Value))**

   Tällä kaavalla määritetään, että lomakkeen määritysten suorittamisen jälkeen siinä näkyvät tietueet, jotka käyttäjä valitsee kohdassa **ChooseProduct**.

4. Napsauta tai napauta **Tiedot**-ruudulta kenttien valintaruutuja niiden näyttämiseksi.

    > [!NOTE]
   > Jos **Tiedot**-ruutu on suljettuna, avaa se valitsemalla lomake vasemmanpuoleisesta ruudusta ja napsauttamalla tai napauttamalla sitten oikeanpuoleisesta ruudusta **Tiedot**.

    ![Kenttien näyttäminen lomakkeessa](./media/add-form/checkbox.png)

5. Vedä **Tiedot**-ruudussa **Nimi**-tieto luettelon ylimmäksi.

    ![Kortin siirtäminen](./media/add-form/drag-field.png)

    **Muokkaa lomaketta** -ohjausobjekti päivittyy muutoksen mukaisesti.

    ![Nimi ylimpänä](./media/add-form/move-card-form.png)

## <a name="set-the-card-type-for-a-field"></a>Kortin tyypin asettaminen kentälle
1. Kun lomake on valittuna, napsauta tai napauta **Tiedot**-ruudussa **Price**-kohdan kortin valitsinta.

    ![Kortin valitsimen valinta](./media/add-form/price-card2.png)

2. Vieritä näkymää alemmaksi ja napsauta tai napauta sitten **Näytä teksti** -vaihtoehtoa, niin käyttöön otetaan vain luku -tila.

    ![Näytä teksti](./media/add-form/view-text.png)

    Lomake päivittyy muutoksen mukaisesti.

    ![Vain luku -numero](./media/add-form/read-only.png)  

## <a name="edit-form-only-save-changes"></a>(Vain Muokkaa lomaketta) Muutosten tallentaminen
1. Valitse lomake vasemmanpuoleisesta ruudusta ja napsauta tai napauta sitten kolmea pistettä (...).

   ![Lomakkeen valinta](./media/add-form/select-form.png)

2. Napsauta tai napauta **Nimeä uudelleen** ja anna lomakkeelle nimi **EditForm**.

3. Lisää **[Painike](controls/control-button.md)**-ohjausobjekti ja aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi **Tallenna**.

    ![Tallennuspainikkeen lisääminen](./media/add-form/save-button.png)  

4. Määritä **Tallenna**-painikkeen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi seuraava kaava:

   **SubmitForm(EditForm)**

5. Avaa esikatselutila valitsemalla oikean yläkulman alueella oleva toistopainike (tai painamalla F5-näppäintä).

    ![Esikatselutilan avaaminen](./media/add-form/open-preview.png)

6. Muuta jonkin tuotteen nimeä ja napsauta tai napauta sitten luomaasi **Tallenna**-painiketta.

    **[SubmitForm](functions/function-form.md)**-funktio tallentaa muutoksesi lomakkeelle määritettyyn tietolähteeseen.

7. (Valinnainen) Sulje esikatselutila valitsemalla sulkemiskuvake (tai painamalla ESC-näppäintä).

    ![Esikatselutilan sulkeminen](./media/add-form/close-preview.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Lisätietoa [lomakkeiden](working-with-forms.md) ja [kaavojen](working-with-formulas.md) kanssa työskentelystä.
