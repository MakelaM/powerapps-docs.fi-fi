---
title: Kangassovelluksen näytön koon ja suunnan muuttaminen | Microsoft Docs
description: Vaiheittaiset ohjeet kangassovelluksen näytön koon ja suunnan muuttamiseen PowerAppsissa
author: evchaki
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/07/2018
ms.author: evchaki
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1d3bd48f658e31f795ca3489fa1973c48da94a22
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995618"
---
# <a name="change-screen-size-and-orientation-of-a-canvas-app-in-powerapps"></a>Kangassovelluksen näytön koon ja suunnan muuttaminen PowerAppsissa
Mukauta kangassovellusta muuttamalla sen näytön kokoa ja suuntaa.

## <a name="prerequisites"></a>Edellytykset

Luo sovellus tai avaa se muokkaamista varten ja valitse sitten **tiedosto-** valikosta **sovellus asetukset** .

## <a name="change-screen-size-and-orientation"></a>Muuta näytön kokoa ja suuntaa
1. Valitse **sovelluksen asetukset**-kohdassa **näytön koko + suunta**.

    ![Tämän vaihtoehdon avulla voit muuttaa sovelluksen näytön kokoa tai suuntaa](./media/set-aspect-ratio-portrait-landscape/size-orientation.png)

1. Valitse **suunta** -luettelosta **pysty** tai **Vaaka**.

1. (Vain Tablet-sovellukset) Tee **kuva suhde**-kohdassa jompikumpi seuraavista vaiheista:

    - Valitse suhde, joka vastaa tämän sovelluksen kohde laitetta.
    - Valitse **Mukautettu** , jos haluat määrittää oman koon, ja määritä sitten leveys välillä 50-3840 ja korkeus 50-2160.

    ![Tablet-sovelluksen kuvasuhteen muuttaminen](./media/set-aspect-ratio-portrait-landscape/aspect-tablet.png)
    
1. Määritä **Sovita**-kohdassa joko **käytössä** tai ei **käytössä**.

    Tämä asetus on oletus arvon mukaan käytössä, jotta sovelluksen näyttöjen koko voidaan sovittaa laitteen käytettävissä olevaan tilaan. Kun tämä asetus on käytössä, sovelluksen **Width** -ominaisuus vastaa sen **designwidth**-ominaisuutta ja sovelluksen **Korkeus** vastaa sen **designheight**-kohdetta.

    Jos poistat tämän asetuksen käytöstä, sovellus mukautuu sen laitteen kuva suhteeseen, jossa se on käynnissä, ja vie kaiken käytettävissä olevan tilan. Sovellus ei skaalaa, ja sen seura uksena näytöt voivat näyttää lisä tietoja.

    Kun tämä asetus on poistettu käytöstä, **Lukitse kuva suhde** poistetaan automaattisesti käytöstä ja poistetaan käytöstä. Lisäksi kaikkien näyttöjen **Width** -ominaisuudeksi on määritetty `Max(App.Width, App.DesignWidth)`, ja niiden **Korkeus** -ominaisuudeksi on määritetty `Max(App.Height, App.DesignHeight)`, jotta ne voivat seurata sen ikkunan mittoja, jossa sovellus on käynnissä. Tämän muutoksen avulla voit luoda sovelluksia, jotka vastaavat eri laitteisiin ja ikkunan ulottuvuuksiin. Lisätietoja: [Luo reagoiva ulkoasu](create-responsive-layout.md)

1. Valitse kohdassa **Lukitse kuvasuhde**joko **Käytössä** tai **Ei käytössä**.

    Jos tämä asetus on käytössä, sovellus säilyttää näytön suunnan ja kuva suhteen, jotka olet määrittänyt vaiheissa 2 ja 3, olipa laite mikä tahansa. Esimerkiksi verkko selaimessa toimiva Puhelin sovellus säilyttää puhelimen suhteen, jolloin kummassakin reunassa näkyy tumma palkki ikkunan täyttämisen sijaan.

    Jos tämä asetus on pois käytöstä, sovellus mukautuu sen laitteen kuva suhteeseen, jossa se on käynnissä (ja vääristää käyttö liittymää tarvittaessa).

1. Määritä kohdassa **Lukitse kuvasuhde** joko **Käytössä** tai **Ei käytössä**.

    Jos lukitset sovelluksen suunnan, sovellus säilyttää määrittämäsi suunnan. Jos sovellusta suoritetaan laitteessa, jossa näyttö on eri suunnassa, sovellus näyttää virheellisesti ja voi näyttää ei-toivottuja tuloksia. Jos poistat sovelluksen suunnan lukituksen, se mukautuu sen laitteen näytön suuntaan, jossa se on käynnissä.

    Voit myös muokata sovelluksen suuntaa ottamalla **käyttöön sovelluksen upottamisen käyttö kokemuksen** **lisä asetuksissa**. Tämä ominaisuus Tasaa sovelluksen, kun se on upotettu, ja muuttaa isännöinti alustan tausta värin valkoiseksi.

1. Tallenna muutoksesi valitsemalla **Käytä**.

## <a name="next-step"></a>Seuraava vaihe
Julkaise sovelluksesi uudelleen käyttäen uusia sovelluksia valitsemalla **Tiedosto**-valikossa kohta **Tallenna**.