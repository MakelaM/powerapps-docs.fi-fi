---
title: Vieritysnäytön lisääminen pohjaan perustuvaan sovellukseen | Microsoft Docs
description: Luo PowerAppsissa näyttö, jota käyttäjät voivat vierittää näyttääkseen enemmän sisältötyyppejä kuin mitä näytölle kerralla mahtuu pohjaan perustuvassa sovelluksessa.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/25/2016
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7094c42c8b070095d08d33a276785cce36933407
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61553041"
---
# <a name="add-a-scrolling-screen-to-a-canvas-app-in-powerapps"></a>Vieritysnäytön lisääminen pohjaan perustuvaan sovellukseen PowerAppsissa

Luo pohjaan perustuvassa sovelluksessa näyttö, jossa käyttäjät voivat näyttää eri kohteita vierittämällä sitä. Voit esimerkiksi luoda puhelinsovelluksen, joka näyttää tietoja useissa kaavioissa, jotka käyttäjät saavat näkyviin vierittämällä.

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
