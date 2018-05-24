---
title: Valikoiman mukauttamisen opetusohjelma | Microsoft Docs
description: Tässä opetusohjelmassa mukautamme PowerAppsissa luodun sovelluksen oletusselainnäyttöä sekä valikoimaa.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/11/2018
ms.author: anneta
ms.openlocfilehash: 30ec6be11b40e01dddfe09cf0ac8af0ed3a8a437
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="tutorial-customize-a-gallery-in-powerapps"></a>Opetusohjelma: Valikoiman mukauttaminen PowerAppsissa
Tässä opetusohjelmassa mukautamme PowerAppsissa luodun sovelluksen oletusselainnäyttöä sekä valikoimaa. Voit hallita tietoja oletussovelluksella mukauttamatta sitä, mutta se on paljon tehokkaampi ja helpompi käyttää, jos teet nämä muutokset:

> [!div class="checklist"]
> * Asettelun muuttaminen
> * Näyttöön tulevien tietojen muuttaminen
> * Sarakkeiden määrittäminen suodatusta ja lajittelua varten
> * Suodatuksen ja lajittelun testaaminen
> * Otsikon muuttaminen
> * Vierityspalkin näyttäminen

Tämä opetusohjelma alkaa [Common Data Service for Apps](../common-data-service/data-platform-intro.md)ista luodulla sovelluksella, mutta samat käsitteet koskevat sovelluksia, jotka on luotu SharePointista, Excelistä ja muista tietolähteistä. 

Jos sinulla ei ole PowerApps-käyttöoikeutta, voit [rekisteröityä ilmaiseksi](../signup-for-powerapps.md).

## <a name="prerequisites"></a>Edellytykset
Ennen kuin aloitat tämän opetusohjelman [luo sovellus](data-platform-create-app.md) Common Data Service for Appsista.

## <a name="open-the-generated-app"></a>Avaa luotu sovellus
1. Kirjaudu [PowerAppsiin](https://web.powerapps.com) ja napsauta tai napauta sitten vasemman reunan lähellä olevaa kohtaa **Sovellukset**.

    ![PowerAppsin aloitussivu](./media/customize-layout-sharepoint/sign-in.png)

1. Etsi luomasi sovellus ja napsauta tai napauta sen kolmen pisteen kuvaketta (**...** ) oikean reunan lähellä.

    ![Sovellusluettelo](./media/customize-layout-sharepoint/open-for-edit.png)

1. Napsauta tai napauta näyttöön tulevasta valikosta sovelluksen muokkausvalintaa. 

## <a name="customize-the-gallery"></a>Mukauta valikoimaa
1. Napsauta tai napauta selausnäytössä mitä tahansa kohdetta paitsi tililuettelon ensimmäistä kohdetta.

    Tässä vaiheessa valitaan **Valikoima**-ohjausobjekti, joka näyttää tilien luettelon.

    ![Valittu valikoima](./media/customize-layout-sharepoint/select-gallery.png)

1. Napsauta tai napauta oikeanpuoleisessa ruudussa **Tilit** **Tiedot**-otsikon oikealla puolella.

    ![Avaa Tiedot-ruutu](./media/customize-layout-sharepoint/open-data-pane.png)

1. Avaa **Asettelu**-kohdan alla oleva valintaluettelo napsauttamalla tai napauttamalla alanuolta **Tiedot** -ruudussa.

    ![Näytä asetteluasetukset](./media/customize-layout-sharepoint/show-layouts.png)

1. Napsauta tai napauta valintaluettelossa vaihtoehtoa, jossa näkyy vain otsikko.

    ![Valitse vain otsikko -asettelu](./media/customize-layout-sharepoint/choose-layout.png)

1. Avaa valintaluettelo otsikolle napsauttamalla tai napauttamalla alanuolta **Tiedot**-ruudussa.

    ![Valitse vain otsikko -asettelu](./media/customize-layout-sharepoint/show-title-options.png)

1. Näytä **Valikoima**-ohjausobjektin tiedot napsauttamalla tai napauttamalla **Nimi**.

    ![Lopullinen valikoima](./media/customize-layout-sharepoint/final-gallery.png)


## <a name="set-the-sort-and-search-columns"></a>Määritä lajittelu- ja hakusarakkeet
1. Valitse **Valikoima**-ohjausobjekti edellisen osan ohjeiden mukaan.

    ![Valitse valikoima](./media/customize-layout-sharepoint/select-gallery-title.png)

2. Varmista vasemman yläkulman alueelta, että ominaisuusluettelo näyttää **Kohteet**.

    ![Kohteiden ominaisuus](./media/customize-layout-sharepoint/items-property.png)

    Tämä ominaisuuden arvo näkyy kaavarivillä ja määrittää valikoiman tietolähteen lisäksi myös suodatus- ja lajittelusarakkeet.

1. Korvaa kaavarivillä molemmat **emailaddress1**-esiintymät **nimellä**. Säilytä jokaista esiintymää ympäröivät lainausmerkit.

    Kaavan pitäisi näyttää tällaiselta:

    ![Kohteet-ominaisuuden kaava](./media/customize-layout-sharepoint/items-value.png)

    Ensimmäinen **nimen** esiintymä määrittää, että käyttäjä voi suodattaa luettelon näyttämään vain ne tietueet, joiden tilin nimi sisältää tekstin, jonka käyttäjä kirjoitti hakupalkkiin. Toinen **nimen** esiintymä määrittää, että käyttäjä voi lajitella luettelon aakkosjärjestyksessä tilin nimen mukaan. Lisätietoja näistä ja muista funktioista on artikkelissa [Lisätietoja kaavasta](formula-reference.md).

## <a name="test-sorting-and-searching"></a>Testaa lajittelu ja haku
1. Avaa esikatselutila painamalla F5-näppäintä (tai napsauttamalla tai napauttamalla toistokuvaketta oikean yläkulman läheltä).

    ![Esikatselutilan avaaminen](./media/customize-layout-sharepoint/open-preview.png)

1. Napsauta tai napauta selausnäytön oikean yläkulman lähettyviltä lajittelukuvaketta kerran tai useita kertoja. Näin aakkosjärjestys muuttuu nousevan ja laskevan välillä.

    ![Testaa lajittelukuvake](./media/customize-layout-sharepoint/sort-button.png)

1. Kirjoita hakuruutuun **k**. Näin näytetään vain ne tilit, joiden nimessä on kirjoittamasi kirjain.

    ![Testaa hakupalkki](./media/customize-layout-sharepoint/test-filter.png)

1. Poista kaikki teksti hakupalkista ja sulje sitten esikatselutila painamalla Esc-näppäintä (tai napsauttamalla tai napauttamalla sulkukuvaketta PowerAppsin otsikkorivin *alapuolella*).

## <a name="change-the-title-of-the-screen"></a>Muuta otsikkoa näytössä
1. Valitse otsikko näytössä napsauttamalla tai napauttamalla sitä.

    ![Valitse näytön otsikko](./media/customize-layout-sharepoint/select-title.png)

1. Varmista, että ominaisuusluettelossa näkyy **Teksti** ja kirjoita kaavariville sitten **Selaa** käyttäen lainausmerkkejä.

    ![Päivitä näytön otsikko](./media/customize-layout-sharepoint/change-screen-title.png)

    Näyttö päivittyy muutoksen mukaisesti.

    ![Uusi näyttöotsikko](./media/customize-layout-sharepoint/new-screen-title.png)

## <a name="show-a-scroll-bar"></a>Näytä vierityspalkki
Jos käyttäjillä ei mahdollisesti ole kosketusnäyttöä tai hiiren kiekkopainiketta, määritä **Valikoima**-ohjausobjekti näyttämään vierityspalkki, kun käyttäjä siirtää kohdistimen sen päälle. Näin käyttäjät voivat tuoda näkyviin kaikki tilit, vaikka näyttö ei pystyisi näyttämään niitä kaikkia kerralla.

1. Valitse **Valikoima**-ohjausobjekti ensimmäisen toimenpiteen ohjeiden mukaan.

    ![Valitse valikoima](./media/customize-layout-sharepoint/select-gallery-sorted.png)

1. Napsauta tai napauta **Valikoima**-välilehdessä **Näytä vierityspalkki** ja vahvista, että kyseisen ominaisuuden arvoksi on muuttunut **true**. 

    ![Näytä vierityspalkki](./media/customize-layout-sharepoint/show-scrollbar.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tässä opetusohjelmassa mukautimme **Valikoima**-ohjausobjektia ja luodun sovelluksen oletusselausnäytön otsikkoa. Voit myös mukauttaa oletusnäyttöjä tietojen näyttämistä ja tilien luomista tai päivittämistä varten. Nämä näytöt sisältävät **Näytetty lomake** -ohjausobjektin ja **Mukautettu lomake** -ohjausobjektin, ja voit muuttaa (esimerkiksi) niiden näyttämiä tietotyyppejä ja näiden järjestystä.

> [!div class="nextstepaction"]
> [Lomakkeiden mukauttaminen](customize-forms-sharepoint.md)