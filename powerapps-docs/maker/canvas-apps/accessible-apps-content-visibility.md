---
title: Näytä tai piilota sisältöä pohjaan perustuvat sovellukset käyttöä helpottavien toimintojen kanssa | Microsoft Docs
description: Näytä sisältö tarjoaminen käyttäjille tai vain – Näytönlukuohjelman käyttäjille vain pohjaan perustuvat sovellukset-tekniikoita
author: tahoon-ms
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.date: 10/22/2018
ms.author: tahoon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c680767bc6a56f0596eba03dd555c1c9a0205346
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61550084"
---
# <a name="show-or-hide-content-from-assistive-technologies-for-canvas-apps"></a>Näytä tai piilota sisältöä pohjaan perustuvat sovellukset käyttöä helpottavien toimintojen kanssa

Useimmissa tapauksissa kaikki käyttäjät pitäisi käyttää kaikkea sisältöä, mutta joskus haluat ehkä Näytä sisältöä tarjoaminen käyttäjille tai vain Näytönlukuohjelman käyttäjille. Esimerkiksi haluat ehkä vain Näytönlukuohjelman käyttäjät voivat käyttää kuvauksia kaavion trendit, jotka näkyvät tarjoaminen käyttäjille. Haluat ehkä myös Piilota käyttäjien Näytönlukuohjelman kuvake, jos viereinen nimen kuvaa sitä. Kuvaketta toisen kuvaus on tarpeetonta.

## <a name="hide-content-from-all-users"></a>Piilota sisältö kaikilta käyttäjiltä

* Määritä **[näkyvissä](controls/properties-core.md)** , false.

## <a name="hide-content-from-sighted-users-and-show-it-to-screen-reader-users"></a>Piilota tarjoaminen käyttäjiltä sisältö ja Näytä se näytön Näytönlukuohjelman käyttäjät

Millä tahansa seuraavilla tavoilla:

* Määritä **[koon](controls/properties-text.md)** 0.
* Määritä **[leveys](controls/properties-size-location.md)** ja **[korkeus](controls/properties-size-location.md)** 1.
* Määritä  **[X](controls/properties-size-location.md)** ,  **[Y](controls/properties-size-location.md)** , tai ominaisuuksia siten, että ohjausobjekti on näytön ulkopuolelta.
* Määritä **[väri](controls/properties-color-border.md)** ja liittyvät ominaisuudet läpinäkyvä.
* Suorakulmion sijainti **[muodon](controls/control-shapes-icons.md)** yllä sisältöä ja määritä **[Täytä](controls/properties-color-border.md)** saman taustaväriksi näytön taustavärin.

> [!NOTE]
> Käyttäjät voivat kuitenkin käyttää näppäimistöllä käyttämään vuorovaikutteisen komponentin, kuten  **[painike](controls/control-button.md)** , vaikka se käyttämällä tekniikoita luettelon. Määritä **[TabIndex](controls/properties-accessibility.md)** 1, jos haluat estää käyttäjiä käyttämästä ohjausobjekti painamalla SARKAINTA.

## <a name="hide-content-from-screen-reader-users-and-show-it-to-sighted-users"></a>Piilota – Näytönlukuohjelman käyttäjät sisältöä ja Näytä se tarjoaminen käyttäjille

* -  **[Kuvan](controls/control-image.md)** ,  **[kuvake](controls/control-shapes-icons.md)** , ja **[muodon](controls/control-shapes-icons.md)** ohjausobjekteja, Määritä **[AccessibleLabel](controls/properties-accessibility.md)** tyhjä merkkijono ””.

## <a name="next-steps"></a>Seuraavat vaiheet

Lue lisätietoja [helppokäyttöominaisuudet](controls/properties-accessibility.md) ohjausobjektien pohjaan perustuvat sovellukset.
