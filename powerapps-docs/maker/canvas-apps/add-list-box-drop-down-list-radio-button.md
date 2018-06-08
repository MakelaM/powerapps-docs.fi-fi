---
title: Lisää luetteloruutu, avattava luettelo ja valintanapit | Microsoft Docs
description: Luo tai määritä monivalintoja PowerAppsissa
documentationcenter: ''
author: lonu
manager: kfile
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/23/2016
ms.author: lonu
ms.openlocfilehash: 1fbaf4f9d740084a1ed0d630b94d1cd41713ba03
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825552"
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons"></a>Lisää luetteloruutu, avattava luettelo tai valintanapit
PowerApps sisältää moni- ja yksittäisvalintavaihtoehtoja, kuten luetteloruudun, avattavan luettelon ja valintanapit. Tässä aiheessa lisäämme nämä ohjausobjektit ja käytämme **Taulukko**-kaavaa luetteloiden rakentamiseen. Kun jokin luettelon kohde on valittuna, muut ohjausobjektit päivitetään.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="add-a-list-box"></a>Luetteloruudun lisääminen
1. Valitse **Lisää**-välilehdeltä **Ohjausobjektit** ja valitse sitten **Luetteloruutu**:  

    ![][2]  

2. Anna **Luetteloruutu**-ohjausobjektille nimi **MyListBox**:  

    ![][3]

3. Määritä sen **[Items](controls/properties-core.md)**-ominaisuudeksi seuraava lauseke:  
   ```["circle","triangle","rectangle"]```  <br/>

    Suunnittelutyökalusi näyttää jotakuinkin seuraavalta:

    ![][4]

4. Valitse **Lisää**-välilehdeltä **Kuvakkeet**, valitse ympyrä ja siirrä se **Luetteloruutu**-ohjausobjektin alle:

    ![][5]  

5. Lisää kolmio ja suorakulmio ja järjestele muodot riviksi **Luetteloruutu**-ohjausobjektin alle:

    ![][6]  

6. Määritä seuraavien muotojen **[Visible](controls/properties-core.md)**-ominaisuudeksi seuraavat funktiot:  

   | Muoto | Määritä Visible-funktioksi |
   | --- | --- |
   | circle |```If("circle" in MyListBox.SelectedItems.Value, true)``` |
   | triangle |```If("triangle" in MyListBox.SelectedItems.Value, true)``` |
   | rectangle |```If("rectangle" in MyListBox.SelectedItems.Value, true)``` |

7. Esikatsele luomustasi ![][1]. Valitse eri muodot **Luetteloruutu**-ohjausobjektissa. Vain valitsemasi muoto tai muodot näytetään. Palaa näyttöösi painamalla ESC-näppäintä tai valitsemalla **X**.

Näissä vaiheissa käytit lauseketta luettelon luomiseksi **Luetteloruutu**-ohjausobjektiin. **Luetteloruutu**-ohjausobjektissa tehdyn valinnan mukaan näytetään eri muotoja. Voit käyttää tätä muihinkin elementteihin liiketoiminnassa. Voit esimerkiksi käyttää **Luetteloruutu**-ohjausobjektia esimerkiksi tuotekuvien tai -kuvausten näyttämiseen.

## <a name="add-radio-buttons"></a>Valintanappien lisääminen
1. Valitse **Aloitus**-välilehdeltä **Uusi näyttö**.

2. Valitse **Lisää**-välilehdeltä **Ohjausobjektit** ja valitse sitten **Valintanappi**.

    ![][10]  

3. Anna **Valintanappi**-ohjausobjektille nimi **Choices** ja aseta sen **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:  
   ```["red","green","blue"]```  <br/>

    ![][12]  

    Tarvittaessa muuta ohjausobjektin kokoa, jotta näet kaikki vaihtoehdot.

4. Valitse **Lisää**-välilehdeltä **Kuvakkeet** ja valitse ympyrä.

5. Määritä ympyrän **[Fill](controls/properties-color-border.md)**-ominaisuudeksi seuraava funktio:  
   ```If(Choices.Selected.Value = "red", RGBA(192, 0, 0, 1), Choices.Selected.Value = "green", RGBA(0, 176, 80, 1), Choices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```  

    Tällä kaavalla ympyrä vaihtaa väriään valitun valintanapin mukaan.

6. Siirrä ympyrä **Valintanappi**-ohjausobjektin alle esimerkin mukaisesti:

    ![][14]  

7. Esikatsele luomustasi: ![][1]. Valitse eri valintanappi ympyrän värin muuttamiseksi. Palaa näyttöösi painamalla ESC-näppäintä tai valitsemalla **X**.

## <a name="add-a-drop-down-list"></a>Avattavan luettelon lisääminen
1. Lisää näyttö ja lisää sitten **Avattava luettelo** -ohjausobjekti.

    ![][15]  

2. Anna ohjausobjektille nimi **DDChoices** ja aseta sen **[Items](controls/properties-core.md)**-ominaisuudeksi tämä kaava:<br>
   **["red","green","blue"]**

3. Lisää ympyrä, siirrä se **Avattava luettelo** -ohjausobjektin alle ja aseta ympyrän **[Fill](controls/properties-color-border.md)**-ominaisuudeksi tämä kaava:  
   ```If(DDChoices.Selected.Value = "red", RGBA(192, 0, 0, 1), DDChoices.Selected.Value = "green", RGBA(0, 176, 80, 1), DDChoices.Selected.Value = "blue", RGBA(0, 32, 96, 1))```

4. Esikatsele luomustasi: ![][1]. Valitse eri vaihtoehtoja ympyrän värin muuttamiseksi.

[1]: ./media/add-list-box-drop-down-list-radio-button/preview.png
[2]: ./media/add-list-box-drop-down-list-radio-button/listbox.png
[3]: ./media/add-list-box-drop-down-list-radio-button/renamelistbox.png
[4]: ./media/add-list-box-drop-down-list-radio-button/itemslistbox.png
[5]: ./media/add-list-box-drop-down-list-radio-button/circle.png
[6]: ./media/add-list-box-drop-down-list-radio-button/allshapes.png
[10]: ./media/add-list-box-drop-down-list-radio-button/radiobutton.png
[12]: ./media/add-list-box-drop-down-list-radio-button/itemsradio.png
[14]: ./media/add-list-box-drop-down-list-radio-button/radiocircle.png
[15]: ./media/add-list-box-drop-down-list-radio-button/dropdown.png
