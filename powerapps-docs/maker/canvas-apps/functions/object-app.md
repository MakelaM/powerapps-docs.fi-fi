---
title: Sovelluksen objektin | Microsoft Docs
description: Viitetiedot, mukaan lukien syntaksi ja esimerkkejä powerappsin App-objekti
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/29/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 232accd1050fb84816e86ea95069b8c8778f6586
ms.sourcegitcommit: 562c7ed5fbb116be1cbb0f45e3f6e75e3e4cf011
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/31/2019
ms.locfileid: "66451606"
---
# <a name="app-object-in-powerapps"></a>Sovelluksen objektin powerappsissa

Tietoja käynnissä sovelluksen ja hallita sovelluksen toiminnan.

## <a name="description"></a>Kuvaus

Ohjausobjekti, kuten **sovelluksen** objekti sisältää ominaisuuksia, joka määrittää, mikä näyttö näytetään ja, jotka kehottavat käyttäjää korjaamaan sen tallentamaan muutokset, jotta ne eivät ole menettää. Jokaisella on **sovelluksen** objekti.

Voit kirjoittaa kaavoja joitakin ominaisuuksia **sovelluksen** objekti. Yläosassa **puu näkymän** ruudussa **sovelluksen** objekti sinuna haluat muiden ohjausobjekti tai näyttö. Tarkastele ja Muokkaa yksi objektin ominaisuuksia valitsemalla sen vasemmalla puolella kaavarivin avattavasta-luettelosta.

> [!div class="mx-imgBorder"]
> ![Puunäkymässä App-objekti](media/object-app/appobject.png)

## <a name="activescreen-property"></a>ActiveScreen ominaisuus

**ActiveScreen** ominaisuus tunnistaa näyttö, joka näyttää.

Tämä ominaisuus palauttaa näytön ohjausobjektin, jota voit käyttää viittaamaan näytön ominaisuuksiin tai vertaamaan toiseen näyttöön määrittääksesi, mikä näyttö näytetään. Voit myös käyttää lauseke **App.ActiveScreen.Name** noutaa näyttö, joka näyttää nimi.

Käytä **[takaisin](function-navigate.md)** tai **[Navigate](function-navigate.md)** funktiota muuttaaksesi näyttö, joka näyttää.

## <a name="onstart-property"></a>OnStart-ominaisuus

**OnStart** ominaisuus suoritetaan, kun käyttäjä käynnistää sovelluksen. Sovellusten tekijöille usein tämän ominaisuuden avulla voit suorittaa seuraavia tehtäviä:

- Hae ja tietoja välimuistiin kokoelmiin käyttämällä **[kerätä](function-clear-collect-clearcollect.md)** funktio.
- Yleiset muuttujat määrittää käyttämällä **[määrittää](function-set.md)** funktio.
- Siirry ensimmäisen näytön käyttämällä **[Navigate](function-navigate.md)** funktio.

Kaava lasketaan, ennen kuin ensimmäinen näyttö näytetään. Yhtään näyttöä ei ladattu, joten et voi määrittää kontekstimuuttujan kanssa **[UpdateContext](function-updatecontext.md)** funktio. Voit kuitenkin välittää kontekstimuuttujia kanssa **Navigate** funktio.

Sen jälkeen, kun muutat **OnStart** ominaisuutta, testata sitä hiiri **sovelluksen** objektin **puu näkymän** ruutu valitsemalla kolme pistettä (...), joka näkyy ja valitsemalla sitten **Suorittaa OnStart**. Toisin kuin kun sovellusta ladataan ensimmäistä kertaa olemassa oleviin kokoelmiin ja muuttujat jo määritetään. Aloita tyhjä kokoelmia, käytä **[ClearCollect](function-clear-collect-clearcollect.md)** funktion sijaan **kerätä** funktio.

> [!div class="mx-imgBorder"]
> ![Suorita OnStart App-kohteen pikavalikko](media/object-app/appobject-runonstart.png)

## <a name="confirmexit-properties"></a>ConfirmExit ominaisuudet

Kukaan haluaa menettää tallentamattomat muutokset. Käytä **ConfirmExit** ja **ConfirmExitMessage** voit varoittaa käyttäjää ennen kuin käyttäjä sulkee sovelluksen ominaisuudet.

> [!NOTE]
> **ConfirmExit** ei toimi sovelluksia, jotka on upotettu, esimerkiksi Power BI- ja SharePoint.

> [!NOTE]
> Tällä hetkellä nämä ominaisuudet voi viitata vain ensimmäisessä näytössä ohjausobjekteja, jos **Delayed lataaminen** esiversio-ominaisuus on käytössä (se on oletusarvoisesti uusia sovelluksia). Jos viittaukset tehdään, PowerApps Studio ei Näytä virhe, mutta tuloksena julkaistun sovelluksen ei avaa PowerApps Mobilessa tai selaimessa. Pyrimme aktiivisesti poistamaan tämän rajoituksen. Sillä välin, voit poistaa käytöstä **Delayed lataaminen** - **tiedoston** > **sovellusasetukset** > **lisäasetukset**(kohdassa **esiversio-ominaisuudet**).

### <a name="confirmexit"></a>ConfirmExit

**ConfirmExit** on totuusarvo, joka, kun *true*, näyttöön tulee valintaikkuna, vahvistus, ennen kuin sovellus on suljettu. Oletusarvon mukaan tämä ominaisuus on *false*, ja ei-valintaikkuna.

Tämän ominaisuuden avulla voit näyttää vahvistusvalintaikkuna, jos käyttäjä on tehnyt muutoksia, mutta ei tallennettu. Käytetään kaavaa, joka voit tarkistaa muuttujia ja ohjausobjektien ominaisuudet (esimerkiksi **Unsaved** -ominaisuuden [ **muokkauslomake** ](../controls/control-form-detail.md) ohjausobjektin).

Vahvistus-valintaikkuna tulee näkyviin missä tahansa tilanteessa, jossa tiedot voidaan menettää, kuten näissä esimerkeissä:

- Käynnissä [ **poistu** ](function-exit.md) funktio.
- Jos sovellus on käynnissä selaimessa:
  - Sulkemisen selaimen tai selaimen välilehteä, jossa sovellus on käynnissä.
  - Selaimen Edellinen-painikkeen valitseminen
- Jos sovellus on käynnissä PowerApps Mobilen (iOS- tai Android):
  - Käynnissä [ **Käynnistä** ](function-param.md) funktio.<br>**Käynnistä** funktio ei käynnistin valintaikkunassa selaimessa, koska toinen välilehti avautuu siten, että tiedot eivät ole menetetty.
  - Vaihda eri sovelluksen PowerApps Mobilessa kosketusnäyttöä.
  - Valitsemalla Takaisin-painike Android-laitteessa.

Kaikilla laitteilla ja versioista Powerappsin saattavat vaihdella vahvistusvalintaikkunassa tarkka ulkoasun.

Vahvistusvalintaikkunassa näy PowerApps Studio.

### <a name="confirmexitmessage"></a>ConfirmExitMessage

Vahvistusvalintaikkunassa näytetään oletuksena yleinen viesti, kuten **”saattaa tallentamattomia muutoksia”.** käyttäjän kielellä.

Käytä **ConfirmExitMessage** antamaan Mukautettu viesti tässä vahvistusikkunassa. Jos tämä ominaisuus on *tyhjä*, oletusarvo on käytössä. Mukautettuja viestejä katkaistaan kuin on tarpeen vahvistusvalintaikkunassa mahtumaan, joten viestin joitakin riveille enintään.

Selaimessa vahvistusvalintaikkunassa saattaa näkyä yleinen viesti selaimesta.

### <a name="example"></a>Esimerkki

1. Luo sovellus, joka sisältää kaksi lomake-ohjausobjektit **AccountForm** ja **ContactForm**.

1. Määritä **sovelluksen** objektin **ConfirmExit** ominaisuudeksi seuraava lauseke:

    ```powerapps-dot
    AccountForm.Unsaved Or ContactForm.Unsaved
    ```

    Tämä valintaikkuna tulee näyttöön, jos käyttäjä muuttaa kummassa tiedot ja yrittää sitten sulkea sovelluksen muutokset tallentamatta.

    > [!div class="mx-imgBorder"]
    > ![Yleinen vahvistusvalintaikkuna](media/object-app/confirm-native.png)

1. Määritä **sovelluksen** objektin **ConfirmExitMessage** -ominaisuuden arvoksi tämä kaava:

    ```powerapps-dot
    If( AccountsForm.Unsaved,
        "Accounts form has unsaved changes.",
        "Contacts form has unsaved changes."
    )
    ```

    Tämä valintaikkuna tulee näyttöön, jos käyttäjä muuttaa lomakkeen tilin tietoja ja yrittää sitten sulkea sovelluksen muutokset tallentamatta.

    > [!div class="mx-imgBorder"]
    > ![Lomakkeeseen liittyvät vahvistusvalintaikkuna](media/object-app/confirm-native-custom.png)
