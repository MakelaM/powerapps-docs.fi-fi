---
title: Vieritysnäytön lisääminen | Microsoft Docs
description: Luo näyttö, jota käyttäjät voivat vierittää näyttääkseen enemmän sisältötyyppejä kuin mitä näytölle kerralla mahtuu.
documentationcenter: na
author: lonu
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 10/25/2016
ms.author: lonu
ms.openlocfilehash: fd7b418de7a78220dfc1019c923749fb8e6ddf5c
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "31825322"
---
# <a name="add-a-scrolling-screen-in-powerapps"></a>Vieritysnäytön lisääminen PowerAppsissa
Luo näyttö, jossa käyttäjät voivat näyttää eri kohteita vierittämällä sitä. Voit esimerkiksi luoda sovelluksen, joka näyttää tiedot sekä pylväskaaviossa että viivakaaviossa. Lisäämällä vieritysnäytön voit lisätä useita ohjausobjekteja, jotka käyttäjä voi näyttää vierittämällä ruutua.

Kun lisäät osaan useita ohjausobjekteja, ohjausobjektit säilyttävät suhteellisen sijaintinsa kyseisessä osassa riippumatta siitä, onko kyseessä puhelinsovellus vai tablettisovellus. Huomaa, että näytön koko ja suunta saattavat määrittää osien asettelun.  

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="create-a-scrolling-screen"></a>Vieritysnäytön luominen
1. Napsauta tai napauta **Aloitus**-välilehdestä **Uusi näyttö**:
   
    ![Asetus, jolla sovellukseen lisätään näyttö][1]
2. Valitse **Aloitus**-välilehti, napsauta tai napauta **Asettelut** ja valitse sitten loputtoman vierityspohjan lisäysvaihtoehto:  
   
    ![Asetus, jolla sovellukseen lisätään loputon vierityspohja][2]
   
    Pohja lisätään:  
   
    ![Oletusnäkymä näytöstä, joka sisältää loputtoman vierityspohjan][3]

## <a name="add-elements"></a>Elementtien lisääminen
Seuraavaksi pohjaan lisätään ohjausobjekteja, jotta nähdään, miten vieritettävä näyttö toimii.

1. Napsauta tai napauta lisäämässäsi pohjassa kohtaa **Lisää kohde Lisää-välilehdestä**.
   
    ![][4]
2. Napsauta tai napauta **Lisää**-välilehdessä **Kaaviot** ja sitten **Pylväskaavio**.
   
    ![Asetus, jolla pylväskaavio lisätään][5]
   
    Näytön ensimmäiseen korttiin tulee näkyviin pylväskaavio:  
   
    ![Oletuspylväskaavio][7]
3. Napsauta tai napauta **Lisää**-välilehdestä **Teksti** ja napsauta tai napauta sitten **Kynän syöte**:  
   
    ![Asetus, jolla kynäohjausobjekti lisätään][8]
4. Siirrä kynäohjausobjekti kaavion alapuolelle ja muuta sen kokoa siten, että se peittää kortin alaosan:  
   
    ![Kynäohjausobjektin siirtäminen ja koon muuttaminen][9]

## <a name="add-a-section"></a>Osan lisääminen
Seuraavaksi lisäämme toisen kortin, jossa on toinen ohjausobjekti.

1. Napsauta tai napauta näytön alaosasta **Lisää osa**:  
   
    ![Asetus, jolla osa lisätään][10]
   
    Näyttöön lisätään uusi kortti:  
   
    ![Uusi kortti oletusosan alapuolella][11]
2. Pidä kortti edelleen valittuna, siirry **Lisää**-välilehteen, napsauta tai napauta **Kaaviot** ja napsauta tai napauta **Viivakaavio**.
   
    Uusi kaavio on liian suuri näytettäväksi näytössä muiden ohjausobjektien kanssa:  
   
    ![Viivakaavio lisättynä uuden kortin alapuolelle][12]
3. Avaa esikatselutila painamalla F5-näppäintä (tai napsauttamalla tai napauttamalla toistokuvaketta oikean yläkulman läheltä).
   
    ![Esikatselutilan avaaminen](./media/add-scrolling-screen/open-preview.png)
4. Näytä uusi viivakaavio vierittämällä alas.  
   
    ![Esikatselu, jossa näytetään uusi viivakaavio][13]

[1]: ./media/add-scrolling-screen/add-screen.png
[2]: ./media/add-scrolling-screen/add-canvas.png
[3]: ./media/add-scrolling-screen/default-canvas.png
[4]: ./media/add-scrolling-screen/insert-visual.png
[5]: ./media/add-scrolling-screen/add-chart.png
[7]: ./media/add-scrolling-screen/default-chart.png
[8]: ./media/add-scrolling-screen/add-pen.png
[9]: ./media/add-scrolling-screen/move-resize-pen.png
[10]: ./media/add-scrolling-screen/add-section.png
[11]: ./media/add-scrolling-screen/new-card.png
[12]: ./media/add-scrolling-screen/add-line-chart.png
[13]: ./media/add-scrolling-screen/line-chart-preview.png
