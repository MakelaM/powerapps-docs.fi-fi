---
title: Pohjaan perustuvan sovelluksen kortin mukauttaminen | Microsoft Docs
description: Muuta oletuksena näytettävää ohjausobjektia tiedot-kortin tai Muokkaa lomaketta pohjaan perustuvassa sovelluksessa
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 03/18/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ddc1c677ed95caf10d8cd6e0e7e12e6aaf88a0f5
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61559799"
---
# <a name="customize-a-card-in-a-canvas-app"></a>Pohjaan perustuvan sovelluksen kortin mukauttaminen

Voit suorittaa kortille perustason mukautuksia (poistamatta kortin lukitusta) esimerkiksi vaihtamalla sen ohjausobjektia. Edistyneitä mukautuksia varten kortin lukitus täytyy poistaa. Näihin kuuluu esimerkiksi sellaisen ohjausobjektin lisääminen, joka ei ole oletuksena käytettävissä kyseiselle kortille.

Katso yleiskatsaus aiheesta [Tutustu tietokortteihin](working-with-cards.md).

## <a name="prerequisites"></a>Edellytykset

- Lue, kuinka [voit lisätä ja määrittää ohjausobjekteja](add-configure-controls.md).
- Voit tarkastella tämän aiheen yleisiä käsitteitä tai vaihtoehtoisesti seurata vaihe vaiheelta toimit näiden aiheiden vaiheet toimintosarjoja:

    1. [Sovelluksen luominen](data-platform-create-app.md).
    1. [Valikoiman mukauttaminen](customize-layout-sharepoint.md).
    1. [Lomakkeiden mukauttaminen](customize-forms-sharepoint.md).

## <a name="customize-a-locked-card"></a>Lukitun kortin mukauttaminen

Tässä toimenpiteessä korvaat **[tekstisyötteen](controls/control-text-input.md)** ohjausobjektin **[liukusäätimen] (ohjausobjekteja/ohjausobjektin-slider.md** ohjausobjektilla poistamatta kortin.

1. Valitse luomasi ja mukauttamasi sovellus **EditForm1** vasemmassa siirtymisruudussa ja valitse sitten **Muokkaa kenttiä** , **ominaisuudet** välilehti oikeanpuoleisessa ruudussa.

1. Valitse kentät-luettelosta alanuolta **työntekijöiden määrä**, ja Avaa luettelo kohdassa **ohjausobjekti tyyppi**.

    > [!div class="mx-imgBorder"]
    > ![Avattavasta luettelosta, jolla asetukset](./media/customize-card/card-selector.png)

1. Valitse **Muokkaa liukusäädintä**.

    Näyttö päivittyy muutoksen mukaisesti.

    > [!div class="mx-imgBorder"]
    > ![EditForm1 liukusäätimellä](./media/customize-card/add-slider.png)

## <a name="unlock-and-customize-a-card"></a>Kortin lukituksen poistaminen ja mukauttaminen

Tässä toimenpiteessä poistetaan kortin lukitus ja päivittää **Max** -ominaisuuden **liukusäätimen** juuri lisäämäsi ohjausobjektin.

1. - **EditForm1**, valitse **liukusäätimen** ohjausobjektia **työntekijöiden määrä** kortti.

    > [!div class="mx-imgBorder"]
    > ![Valitse liukusäädin](./media/customize-card/select-slider.png)

1. Valitse **lisäasetukset** välilehti oikeanpuoleisessa ruudussa Valitse Avaa kortin lukitus lukkokuvaketta.

    > [!div class="mx-imgBorder"]
    > ![Kortin lukituksen avaaminen](./media/customize-card/lock-icon.png)

1. Määritä **Max** -ominaisuuden **liukusäätimen** ohjausobjektin 10 000.

    > [!div class="mx-imgBorder"]
    > ![Suurin-ominaisuus Lisäasetukset-välilehdessä](./media/customize-card/max-property.png)

    **Liukusäätimen** ohjausobjekti näyttää tarkemman arvon.

    > [!div class="mx-imgBorder"]
    > ![Liukusäätimen alue: 0-10,000](./media/customize-card/final-slider.png)

## <a name="next-steps"></a>Seuraavat vaiheet

Nyt kun ymmärrät sovelluksen luomisen sekä valikoiman, lomakkeen ja kortin mukauttamisen, voit [luoda oman sovelluksen alusta alkaen](data-platform-create-app-scratch.md).