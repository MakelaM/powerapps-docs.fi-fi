---
title: Sovellus objekti | Microsoft Docs
description: Powerappsin sovellus objektin viite tiedot, mukaan lukien syntaksi ja esimerkit
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 05/29/2019
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b0ab20ce5e0700337bb059644c458a2665d20f1e
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71983564"
---
# <a name="app-object-in-powerapps"></a>Sovellus objekti Powerappsissa

Antaa tietoja käynnissä olevasta sovelluksesta ja valvoo sovelluksen toimintaa.

## <a name="description"></a>Kuvaus

Ohjaus objektin tavoin **sovellus** objekti tarjoaa ominaisuuksia, jotka määrittävät, mitä näyttöä näytetään, ja kehottaa käyttäjää tallentamaan muutokset niin, että ne eivät häviä. Jokaisella sovelluksella on **sovellus** objekti.

Voit kirjoittaa kaavoja joihinkin **sovellus** objektin ominaisuuksiin. Valitse **puunäkymä** ruudun yläosasta **sovellus** objekti samalla tavalla kuin mitä tahansa muuta ohjaus objektia tai näyttöä. Tarkastele ja Muokkaa jotakin objektin ominaisuutta valitsemalla se kaava rivin vasemmalla puolella olevasta avattavasta valikosta.

> [!div class="mx-imgBorder"]
> ![Sovellus-objekti puunäkymän ruudussa @ no__t-1

## <a name="activescreen-property"></a>ActiveScreen-ominaisuus

**Activescreen** -ominaisuus määrittää näkyvissä olevan näytön.

Tämä ominaisuus palauttaa näyttö objektin, jonka avulla voit viitata näytön ominaisuuksiin tai verrata toiseen näyttöön määrittääksesi, mitä näyttöä näytetään. Voit myös hakea näytettävän näytön nimen käyttämällä lauseketta **app.ActiveScreen.name** .

Voit muuttaa **[näytellä näyttöä Back](function-navigate.md)** -tai **[Navigate](function-navigate.md)** -funktiolla.

## <a name="onstart-property"></a>OnStart-ominaisuus

**ONSTART** -ominaisuus suoritetaan, kun käyttäjä käynnistää sovelluksen. Sovellusten tekijät käyttävät tätä ominaisuutta usein näiden tehtävien suorittamiseen:

- Nouda ja Tallenna tiedot kokoelmiin **[Collect](function-clear-collect-clearcollect.md)** -funktiolla.
- Määritä yleiset muuttujat käyttämällä **[joukkoa](function-set.md)** -funktiolla.
- Siirry ensimmäiseen näyttöön **[Navigoi](function-navigate.md)** -funktiolla.

Tämä kaava arvioidaan, ennen kuin ensimmäinen näyttö tulee näkyviin. Mitään näyttöä ei ole ladattu, joten et voi valita Context-muuttujia, joilla on **[updatecontext](function-updatecontext.md)** -funktiolla. Voit kuitenkin välittää Context-muuttujia **Navigoi** -funktiolla.

Kun olet muuttanut **ONSTART** -ominaisuutta, testaa sitä viemällä hiiren osoitin **sovellus** -objektin päälle **puunäkymä** -ruudussa, valitse kolme pistettä (...), joka tulee näkyviin, ja valitsemalla sitten **Suorita ONSTART**. Toisin kuin silloin, kun sovellus ladataan ensimmäistä kertaa, olemassa olevat kokoelmat ja muuttujat on jo määritetty. Jos haluat aloittaa tyhjillä kokoelmilla, käytä **[Clearcollect](function-clear-collect-clearcollect.md)** -funktiota **Collect** -funktiolla.

> [!div class="mx-imgBorder"]
> ![Sovelluskohteen pikavalikko kohteelle Run OnStart @ no__t-1

## <a name="confirmexit-properties"></a>Conconmexit-ominaisuudet

Kukaan ei halua menettää tallentamattomia muutoksia. Varoita käyttäjää, ennen kuin hän sulkee sovelluksesi, käyttämällä **Conconmexit** -ja **Consmexitmessage** -ominaisuuksia.

> [!NOTE]
> **Conconmexit** ei toimi sovelluksissa, jotka on upotettu esimerkiksi Power BI ja SharePointiin.

> [!NOTE]
> Tällä hetkellä nämä ominaisuudet voivat viitata ohjaus objekteihin vain ensimmäisessä näytössä, jos **viivästetty kuormituksen** esikatselu on käytössä (se on oletuksena uusille sovelluksille). Jos viitta uksia tehdään, PowerApps Studio ei Näytä virhettä, mutta tuloksena saatu julkaistu sovellus ei avaudu PowerApps Mobilessa tai selaimessa. Pyrimme aktiivisesti poistamaan tämän rajoituksen. Tällä välin voit poistaa **viivästyneen kuormituksen** käytöstä **tiedosto** > -**sovelluksen asetuksissa** > **lisä asetukset** (kohdassa **esikatselutoiminnot**).

### <a name="confirmexit"></a>Conconmexit

**Confirmexit** on Boolean-ominaisuus, joka, kun se on *tosi*, avaa vahvistus valinta ikkunan, ennen kuin sovellus suljetaan. Oletus arvon mukaan tämä ominaisuus on *Epätosi*, eikä valinta ikkunaa tule näkyviin.

Tämän ominaisuuden avulla voit näyttää vahvistus valinta ikkunan, jos käyttäjä on tehnyt muutoksia, mutta ei tallentanut niitä. Käytä kaavaa, joka voi tarkistaa muuttujia ja ohjaus objektin ominaisuuksia (esimerkiksi [**Muokkaa lomaketta**](../controls/control-form-detail.md) -ohjaus objektin **tallentamaton** ominaisuus).

Vahvistus valinta ikkuna tulee näkyviin missä tahansa tilanteessa, jossa tietoja voidaan menettää, kuten Näissä esimerkeissä:

- Suoritetaan [**Lopetus**](function-exit.md) -funktiolla.
- Jos sovellusta suoritetaan selaimessa:
  - Suljetaan selain tai selain väli lehti, jossa sovellus on käynnissä.
  - Selaimen Edellinen-painikkeen valitseminen.
- Jos sovellusta suoritetaan PowerApps Mobilessa (iOS tai Android):
  - [**Käynnistetään Käynnistys**](function-param.md) -funktiolla.<br>**Launch** -funktiolla ei laukaista valinta ikkunaa selaimessa, koska toinen väli lehti avautuu niin, että tietoja ei häviä.
  - Pyyhkäisemällä voit vaihtaa eri sovellukseen PowerApps Mobilessa.
  - Valitsemalla Android-laitteen takaisin-painikkeen.

Vahvistus valinta ikkunan tarkka ulkoasu voi vaihdella eri laitteissa ja Powerappsin versioissa.

Vahvistus valinta ikkuna ei näy PowerApps Studio.

### <a name="confirmexitmessage"></a>Conconmexitmessage

Oletus arvon mukaan vahvistus-valinta ikkunassa näytetään yleinen sanoma, kuten **"sinulla voi olla tallentamattomia muutoksia".** käyttäjän kielellä.

Anna **confirmexitmessage** -kohteen avulla mukautettu sanoma vahvistus valinta ikkunassa. Jos tämä ominaisuus on *tyhjä*, käytetään oletus arvoa. Mukautetut sanomat katkaistaan tarvittaessa, jotta ne mahtuisivat vahvistus valinta ikkunaan, joten pidä viesti vain muutaman rivin päässä.

Selaimessa vahvistus valinta ikkuna saattaa näkyä selaimessa yleisellä viestillä.

### <a name="example"></a>Esimerkki

1. Luo sovellus, joka sisältää kaksi lomakkeen ohjaus objektia, **accountaform** ja **contaceform**.

1. Valitse **sovellus** objektin **Conformexit** -ominaisuudeksi tämä lauseke:

    ```powerapps-dot
    AccountForm.Unsaved Or ContactForm.Unsaved
    ```

    Tämä valinta ikkuna tulee näkyviin, jos käyttäjä vaihtaa tietoja jommassakummassa muodossa ja yrittää sitten sulkea sovelluksen tallentamatta muutoksia.

    > [!div class="mx-imgBorder"]
    > ![Yleinen vahvistus-valinta ikkuna @ no__t-1

1. Valitse **sovellus** objektin **Constmexitmessage** -ominaisuudeksi Tämä kaava:

    ```powerapps-dot
    If( AccountsForm.Unsaved,
        "Accounts form has unsaved changes.",
        "Contacts form has unsaved changes."
    )
    ```

    Tämä valinta ikkuna tulee näkyviin, jos käyttäjä muuttaa tili lomakkeessa olevia tietoja ja yrittää sulkea sovelluksen tallentamatta muutoksia.

    > [!div class="mx-imgBorder"]
    > ![Lomakekohtainen vahvistus-valinta ikkuna @ no__t-1
