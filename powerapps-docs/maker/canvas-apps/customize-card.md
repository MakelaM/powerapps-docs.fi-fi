---
title: Kortin mukauttaminen kangas sovelluksessa | Microsoft Docs
description: Kortissa näkyvän tietojen tai muokkaus lomakkeen oletus ohjaus objektin muuttaminen kangas sovelluksessa
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5bcf1515f72bdce0872f91c64b5ac4fe5028ee2c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71985910"
---
# <a name="customize-a-card-in-a-canvas-app"></a>Kortin mukauttaminen kangas sovelluksessa

Voit suorittaa kortille perustason mukautuksia (poistamatta kortin lukitusta) esimerkiksi vaihtamalla sen ohjausobjektia. Edistyneitä mukautuksia varten kortin lukitus täytyy poistaa. Näihin kuuluu esimerkiksi sellaisen ohjausobjektin lisääminen, joka ei ole oletuksena käytettävissä kyseiselle kortille.

Katso yleiskatsaus aiheesta [Tutustu tietokortteihin](working-with-cards.md).

## <a name="prerequisites"></a>Edellytykset

- Lue, kuinka [voit lisätä ja määrittää ohjausobjekteja](add-configure-controls.md).
- Voit tutustua tähän aiheeseen vain yleisiin käsitteisiin tai voit seurata sitä vaiheittain, jos suoritat ensin näiden aiheiden toimet:

    1. [Sovelluksen luominen](data-platform-create-app.md).
    1. [Valikoiman mukauttaminen](customize-layout-sharepoint.md).
    1. [Lomakkeiden mukauttaminen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Lukitun kortin mukauttaminen

Tässä toimenpiteessä korvaat **[teksti syöte-](controls/control-text-input.md)** ohjaus objektin, jonka **[Slider] (Controls/Control-Slider. MD-** ohjaus objekti ei poista kortin lukitusta.

1. Valitse luomasi ja mukauttamasi sovelluksen vasemmasta siirtymis palkista **EditForm1** ja valitse sitten **Muokkaa kenttiä** oikeanpuoleisen ruudun **Ominaisuudet** -väli lehdeltä.

1. Valitse kenttä luettelosta **työn tekijöiden määrän**alaspäin osoittava nuoli ja avaa sitten luettelo **ohjaus objektin tyyppi**-kohdassa.

    > [!div class="mx-imgBorder"]
    > ![Avattavasta numero kortin asetusten luettelo @ no__t-1

1. Valitse **Muokkaa liuku säädintä**.

    Näyttö päivittyy muutoksen mukaisesti.

    > [!div class="mx-imgBorder"]
    > ![editform1 ja liuku säätimen-ohjaus objekti @ no__t-1

## <a name="unlock-and-customize-a-card"></a>Kortin lukituksen poistaminen ja mukauttaminen

Tässä toimenpiteessä poistat kortin lukituksen ja päivität juuri lisäämäsi **liuku säädin** -ohjaus objektin **Max** -ominaisuuden.

1. Valitse **EditForm1**-kohdassa **liuku säädin** **työn tekijöiden määrän** kortissa.

    > [!div class="mx-imgBorder"]
    > ![Valitse liuku säädin @ no__t-1

1. Avaa kortin lukitus valitsemalla oikeanpuoleisen ruudun **lisä asetukset** -väli lehdestä lukko kuvake.

    > [!div class="mx-imgBorder"]
    > ![Poista kortin lukitus @ no__t-1

1. Säädä **liuku säädin** -ohjaus objektin **Max** -ominaisuudeksi 10 000.

    > [!div class="mx-imgBorder"]
    > ![Max-ominaisuus lisä asetukset-väli lehdessä @ no__t-1

    **Liuku säädin** -ohjaus objektissa näytetään tarkempi arvo.

    > [!div class="mx-imgBorder"]
    > ![Slider-alue: 0-10000 @ no__t-0

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun ymmärrät sovelluksen luomisen sekä valikoiman, lomakkeen ja kortin mukauttamisen, voit [luoda oman sovelluksen alusta alkaen](data-platform-create-app-scratch.md).