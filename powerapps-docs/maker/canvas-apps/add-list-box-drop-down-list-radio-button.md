---
title: Lisää luetteloruutu, avattava luettelo tai valintanappeja pohjaan perustuvaan sovellukseen | Microsoft Docs
description: Luo tai määritä PowerAppsissa monivalintoja pohjaan perustuvassa sovelluksessa
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 10/24/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 211a5be4a97780a440bf151157576a5ab56933a5
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987509"
ms.PowerAppsDecimalTransform: true
---
# <a name="add-a-list-box-a-drop-down-list-or-radio-buttons-to-a-canvas-app"></a>Lisää luetteloruutu, avattava luettelo tai valintanappeja pohjaan perustuvaan sovellukseen

Näytä yksi tietosarake (esimerkiksi usean sarakkeen taulukosta) pohjaan perustuvassa sovelluksessa, jotta käyttäjät voivat valita luettelosta yhden tai useamman kohteen.

- Lisää luetteloruutu, jotta käyttäjät voivat valita useamman kuin yhden vaihtoehdon.
- Lisää vähemmän näyttötilaa vievä avattava luettelo.
- Lisää joukko valintanappeja halutun ulkoasun luomiseksi.

Tässä artikkelissa käsitellään erityisesti luetteloruutuja ja valintanappeja, mutta samat käytännöt koskevat myös avattavia luetteloita.

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="create-a-simple-list"></a>Yksinkertaisen luettelon luominen

1. Lisää **Luetteloruutu**-ohjausobjekti, anna sille nimeksi **MyListBox** ja aseta sen **Kohteet**-ominaisuudeksi tämä lauseke:

    ```["circle";"triangle";"rectangle"]```  <br/>

    Suunnittelutyökalusi näyttää jotakuinkin seuraavalta:

    ![][4]

4. Valitse **Lisää**-välilehdestä **Kuvakkeet**, valitse ympyrä ja siirrä se **MyListBox**-ohjausobjektin alle:

    ![][5]  

5. Lisää kolmio ja suorakulmio ja järjestele muodot riviksi **MyListBox**-ohjausobjektin alle:

    ![][6]  

6. Määritä seuraavien muotojen **[Visible](controls/properties-core.md)** -ominaisuudeksi seuraavat funktiot:  

   | Muoto | Määritä Visible-funktioksi |
   | --- | --- |
   | circle |```If("circle" in MyListBox.SelectedItems.Value; true)``` |
   | triangle |```If("triangle" in MyListBox.SelectedItems.Value; true)``` |
   | rectangle |```If("rectangle" in MyListBox.SelectedItems.Value; true)``` |

7. Pidä Alt-näppäintä painettuna ja valitse yksi tai useampia muotoja **MyListBox**-ohjausobjektista.

    Vain valitsemasi muoto tai muodot näytetään.

Näissä vaiheissa käytit lauseketta luettelon luomiseen. Voit käyttää tätä muihinkin elementteihin liiketoiminnassa. Voit käyttää **Avattava luettelo** -ohjausobjektia esimerkiksi tuotekuvien tai -kuvausten näyttämiseen.

## <a name="add-radio-buttons"></a>Valintanappien lisääminen
1. Valitse **Aloitus**-välilehdestä **Uusi näyttö** ja valitse sitten **Tyhjä**.

2. Valitse **Lisää**-välilehdeltä **Ohjausobjektit** ja valitse sitten **Valintanappi**.

    ![][10]  

3. Anna **Valintanappi**-ohjausobjektille nimi **Choices** ja aseta sen **[Items](controls/properties-core.md)** -ominaisuudeksi tämä kaava:  
   ```["red";"green";"blue"]```  <br/>

    ![][12]  

    Tarvittaessa muuta ohjausobjektin kokoa, jotta näet kaikki vaihtoehdot.

4. Valitse **Lisää**-välilehdeltä **Kuvakkeet** ja valitse ympyrä.

5. Määritä ympyrän **[Fill](controls/properties-color-border.md)** -ominaisuudeksi seuraava funktio:  
   ```If(Choices.Selected.Value = "red"; Red; Choices.Selected.Value = "green"; Green; Choices.Selected.Value = "blue"; Blue)```  

    Tällä kaavalla ympyrä vaihtaa väriään valitun valintanapin mukaan.

6. Siirrä ympyrä **Valintanappi**-ohjausobjektin alle esimerkin mukaisesti:

    ![][14]  

7. Pidä Alt-näppäintä painettuna ja valitse eri valintanappi ympyrän värin muuttamiseksi.

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
