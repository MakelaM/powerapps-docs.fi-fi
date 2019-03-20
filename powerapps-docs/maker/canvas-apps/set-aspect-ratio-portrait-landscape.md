---
title: Kangassovelluksen näytön koon ja suunnan muuttaminen | Microsoft Docs
description: Vaiheittaiset ohjeet kangassovelluksen näytön koon ja suunnan muuttamiseen PowerAppsissa
author: evchaki
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/07/2018
ms.author: evchaki
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c4d9f648a4519ef30887d8d0739d7dc3d940555b
ms.sourcegitcommit: 0dbbf53aea319e53edadc1d3a9efa5728856ebd8
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/19/2019
ms.locfileid: "58172675"
---
# <a name="change-screen-size-and-orientation-of-a-canvas-app-in-powerapps"></a>Kangassovelluksen näytön koon ja suunnan muuttaminen PowerAppsissa
Mukauta kangassovellusta muuttamalla sen näytön kokoa ja suuntaa.

## <a name="prerequisites"></a>Edellytykset

Luo sovellus tai avaa sovellus muokkaamista varten ja valitse sitten **sovellusasetukset** - **tiedoston** valikosta.

## <a name="change-screen-size-and-orientation"></a>Muuta näytön kokoa ja suuntaa
1. Valitse **sovellusasetukset**, valitse **näytön koko + suunta**.

    ![Tämän vaihtoehdon avulla voit muuttaa sovelluksen näytön kokoa tai suuntaa](./media/set-aspect-ratio-portrait-landscape/size-orientation.png)

1. Tässä **suunta** luettelosta **pysty** tai **vaaka**.

1. (Vain tablettisovellukset) Valitse **kuvasuhde**, suorita jompikumpi seuraavista vaiheista:

    - Valitse suhde, joka vastaa tämän sovelluksen kohdelaitetta.
    - Valitse **mukautettu** määrittää oman koon ja määritä leveydeksi 50 3840 ja korkeus 50 2160 välillä.

    ![Tablet-sovelluksen kuvasuhteen muuttaminen](./media/set-aspect-ratio-portrait-landscape/aspect-tablet.png)
    
1. Valitse **Sovita**, joko **-** tai **käytöstä**.

    Tämä asetus on oletusarvoisesti niin, että sovelluksen näytöt kokoa sopimaan laitteen tilaa. Kun tämä asetus on käytössä, sovelluksen **leveys** ominaisuuden vastaavuudet sen **DesignWidth**, ja sovelluksen **korkeus** vastaa sen **DesignHeight**.

    Jos poistat tämän asetuksen käytöstä, sovellus säätää kuvasuhteen sen laitteen, johon se on käynnissä ja käyttää kaikki käytettävissä olevan tilan. Sovellus ei Skaalaa ja siksi näyttöjä näyttää enemmän tietoja.

    Kun tämä asetus on poistettu käytöstä, **lukitse kuvasuhde** on automaattisesti poistettu käytöstä ja poistettu käytöstä. Lisäksi **leveys** kaikki näytöt asetuksena on `Max(App.Width, App.DesignWidth)`, ja niiden **korkeus** asetuksena on `Max(App.Height, App.DesignHeight)` niin, että he seurata dimensiot-ikkunan, jossa sovellus on käynnissä. Muutos voit luoda sovelluksia, jotka vastaavat eri laitteille ja ikkunan dimensioita. Lisätietoja: [Luo reagoiva asettelu](create-responsive-layout.md)

1. Valitse kohdassa **Lukitse kuvasuhde**joko **Käytössä** tai **Ei käytössä**.

    Jos tämä asetus on käytössä, sovellus säilyttää näytön suunnan ja kuvasuhdetta, jonka määritit vaiheet 2 ja 3, olipa laite. Esimerkiksi puhelinsovellus, jossa on käytössä selaimella säilyttää puhelimelle, näytetään Tumma palkin kummallakin puolella täyttämisen ikkunan sijaan suhde.

    Jos tämä asetus on poistettu käytöstä, sovellus säätää kuvasuhteen sen laitteen, johon se on käynnissä (ja vääristää Käyttöliittymän tarvittaessa).

1. Määritä kohdassa **Lukitse kuvasuhde** joko **Käytössä** tai **Ei käytössä**.

    Jos lukitset sovelluksen suunnan, sovellus säilyttää määrittämäsi suunnan määrität. Jos sovellus suoritetaan laitteessa, jonka näyttö on eri asennossa, sovellus näkyy väärin ja voi olla Vääränlainen. Jos vapautat sovelluksen suunnan, se säätää näytön suunnan laitteen, jossa se toimii.

    Voit muokata sovelluksen suunnan ottamalla **Ota käyttöön sovelluksen upottamisen käyttäjäkokemus** - **lisäasetukset**. Tämä ominaisuus vasemmassa Tasaa sovelluksen, kun se on upotettu ja muuttaa isännöinnin pohjan taustavärin valkoiseksi.

1. Tallenna muutoksesi valitsemalla **Käytä**.

## <a name="next-step"></a>Seuraava vaihe
Julkaise sovelluksesi uudelleen käyttäen uusia sovelluksia valitsemalla **Tiedosto**-valikossa kohta **Tallenna**.