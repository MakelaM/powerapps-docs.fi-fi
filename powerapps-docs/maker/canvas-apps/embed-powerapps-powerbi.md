---
title: Uuden pohjaan perustuvan sovelluksen upottaminen Power BI -raporttiin | Microsoft Docs
description: Upota uusi pohjaan perustuva sovellus, joka käyttää samaa tietolähdettä ja voidaan suodattaa samalla tavalla kuin muut raporttikohteet
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/15/2018
ms.author: mblythe
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 046bd1c56a7c27068c4d52cbc0bd28b1bb800ede
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42853655"
---
# <a name="embed-a-new-canvas-app-in-a-power-bi-report"></a>Uuden pohjaan perustuvan sovelluksen upottaminen Power BI -raporttiin

Power BI:n avulla voit laajentaa sen ominaisuuksia lisäämällä *mukautettuja visualisointeja* raporttiin. Tässä opetusohjelmassa luomme PowerAppsin mukautetulla visualisoinnilla uuden pohjaan perustuvan sovelluksen, joka on upotettu malliraporttiin. Tämä sovellus on vuorovaikutuksessa kyseisen raportin muiden kohteiden kanssa.

Jos sinulla ei ole PowerApps-tilausta, [luo ilmainen tili](../signup-for-powerapps.md) ennen aloittamista.

Tässä opetusohjelmassa opit seuraavat asiat:
> [!div class="checklist"]
> * PowerAppsin mukautetun visualisoinnin tuominen Power BI- raporttiin
> * raportin tietoja käyttävän uuden sovelluksen luominen
> * sovelluksen tarkasteleminen raportissa.

## <a name="prerequisites"></a>Edellytykset

* [Google Chrome](https://www.google.com/chrome/browser/)- tai [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) -selain
* [Power BI -tilaus](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi), jossa on [mahdollisuusanalyysimalli](https://docs.microsoft.com/power-bi/sample-opportunity-analysis#get-the-content-pack-for-this-sample) asennettuna
* Käsitys siitä, miten [sovelluksia luodaan PowerAppsissa](data-platform-create-app-scratch.md) ja [Power BI -raportteja](https://docs.microsoft.com/power-bi/service-the-report-editor-take-a-tour) muokataan.

## <a name="import-the-powerapps-custom-visual"></a>PowerAppsin mukautetun visualisoinnin tuominen

Ensimmäinen vaihe on PowerAppsin mukautetun visualisoinnin tuominen, jotta voit käyttää sitä malliraportissa.

1. Napsauta tai napauta mahdollisuusanalyysimallin raportissa **Tulevia mahdollisuuksia** -välilehteä.

2. Napsauta tai napauta raportin yläreunassa **Muokkaa raporttia**.

3. Napsauta tai napauta **Visualisoinnit**-ruudussa kolmea pistettä (**...** ) > **Tuo Marketplacesta**. 

    ![Tuo Marketplacesta](media/embed-powerapps-powerbi/import-visual.png)

4. Etsi **Power BI -visualisoinnit** -näytöstä ”PowerApps” ja napsauta tai napauta sitten **Lisää**. Power BI lisää mukautetun visualisoinnin kuvakkeen **Visualisoinnit**-ruudun alaosaan.

    ![PowerAppsin visualisoinnin kuvake](media/embed-powerapps-powerbi/powerapps-icon.png)

5. Tallenna raportti.

## <a name="create-a-new-app"></a>Luo uusi sovellus
Nyt lisäämme mukautetun visualisoinnin raporttiin ja luomme uuden sovelluksen raportin tietojen perusteella. Kun luot sovelluksen, se käynnistää PowerApps Studion PowerAppsin ja Power BI:n välisellä reaaliaikaisella tietoyhteydellä.

1. Tee tilaa sovellukselle siirtämällä joitakin raporttiruutuja ja muuttamalla niiden kokoa.

    ![Siirrä raporttiruutuja ja muuta niiden kokoa](media/embed-powerapps-powerbi/move-resize.png)

2. Napsauta tai napauta PowerAppsin mukautetun visualisoinnin kuvaketta ja muuta sitten sen kokoa, niin että se mahtuu tekemääsi tilaan.

3. Valitse **Kentät**-ruudussa **Nimi**, **Tuotekoodi** ja **Myyntivaihe**. 

    ![Valitse kentät](media/embed-powerapps-powerbi/select-fields.png)

4. Valitse mukautetussa visualisoinnin ruudussa PowerApps-ympäristö, johon haluat luoda sovelluksen, ja napsauta tai napauta sitten **Luo uusi**.

    ![Luo uusi sovellus](media/embed-powerapps-powerbi/create-new-app.png)

    Näet PowerApps Studiossa luodun perussovelluksen sekä *valikoiman*, jossa näkyy jokin Power BI:ssä valitsemistasi kentistä.

5.  Muuta valikoiman kokoa siten, että se vie vain puolet näytöstä. 

6. Napsauta tai napauta vasemmassa ruudussa **Screen1** ja määritä sitten näytön **Täyttö**-ominaisuudeksi ”LightBlue” (jotta se erottuu paremmin raportissa).

    ![Sovellus ja valikoima, jonka kokoa on muutettu](media/embed-powerapps-powerbi/app-gallery.png)

6. Lisää valikoiman alle Otsikko-ohjausobjekti, jonka **Teksti**-ominaisuutena on `"Opportunity Count: " & CountRows(Gallery1.AllItems)`. Näet nyt tietojoukon mahdollisuuksien kokonaismäärän.

    ![Mahdollisuuksien lukumäärä](media/embed-powerapps-powerbi/opportunity-count.png)

7. Tallenna sovellus nimellä ”Mahdollisuudet”. 


## <a name="view-the-app-in-the-report"></a>Sovelluksen tarkasteleminen raportissa
Sovellus on nyt käytettävissä raportissa, ja se on vuorovaikutuksessa muiden visualisointien kanssa, koska se jakaa saman tietolähteen.

Valitse Power BI -raportin osittajassa **Jan**. Näin koko raportti suodatetaan, mukaan lukien sovelluksen tiedot.

![Suodatettu raportti](media/embed-powerapps-powerbi/filtered-report.png)

Huomaa, että mahdollisuuksien lukumäärä sovelluksessa vastaa raportin vasemmassa yläkulmassa olevaa lukua. Voit valita muita raportin kohteita; sovelluksen tiedot päivitetään.


## <a name="clean-up-resources"></a>Puhdista resurssit
Jos et enää halua käyttää mahdollisuusanalyysimallia, voit poistaa koontinäytön, raportin ja tietojoukon.


## <a name="next-steps"></a>Seuraavat vaiheet
Tässä opetusohjelmassa opit seuraavat asiat:
> [!div class="checklist"]
> * PowerAppsin mukautetun visualisoinnin tuominen Power BI- raporttiin
> * raportin tietoja käyttävän uuden sovelluksen luominen
> * Sovelluksen tarkasteleminen raportissa

Siirry seuraavaan artikkeliin oppimaan lisää
> [!div class="nextstepaction"]
> [PowerAppsin mukautettu visualisointi Power BI:lle](powerapps-custom-visual.md)

