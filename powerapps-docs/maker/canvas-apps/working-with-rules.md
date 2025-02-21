---
title: Säännön laatiminen | Microsoft Docs
description: Vaiheittaiset ohjeet sovelluksen logiikan kehittämiseen sääntöjä luomalla
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 11/10/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 52a28f73a0a9dae0e410714102f1bc78fe706fab
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994735"
---
# <a name="create-a-rule-in-powerapps"></a>Säännön luominen PowerAppsissa
Voit luoda sääntöjä, joilla voit muokata sovellusta automaattisesti määrittämiesi ehtojen perusteella. Luo esimerkiksi sellainen sääntö, jolla luettelokohteet näytetään punaisella, keltaisella tai vihreällä niiden tilan perusteella tai jolla hyväksyntäpainike näytetään vain tietyille käyttäjille (esimerkiksi esimiehille).

Voit lisätä sääntöjä useisiin erilaisiin ohjausobjekteihin. Tässä ohjeaiheessa lisäämme säännön, joka muuttaa **Nimi**-ohjausobjektin tekstin väriä, jos **Liukusäädin**-ohjausobjektin arvo on suurempi kuin 70.

## <a name="add-a-rule"></a>Säännön lisääminen
1. Valitse ohjausobjekti (tai lisää ohjausobjekti ja jätä se valituksi).

    [Lisää nimi ja liukusäädin](add-configure-controls.md), määritä nimen **teksti**-ominaisuuden arvoksi **Slider1.Value** ja valitse sitten liukusäädin tätä ohjeaihetta varten.

1. Napsauta tai napauta oikeanpuoleisessa paneelissa **Säännöt** ja napsauta tai napauta sitten **Uusi sääntö**.

    ![Uuden säännön luominen](./media/working-with-rules/new-rule.png)

    Jos valitset ohjausobjektin, jolle on jo määritetty yksi tai useampi sääntö, voit muokata mitä tahansa niistä napsauttamalla tai napauttamalla sitä.  

## <a name="add-a-condition"></a>Ehdon lisääminen
Ehto on lauseke, joka antaa tulokseksi tosi tai epätosi, kuten onko arvo suurempi kuin 70. Voit kirjoittaa lausekkeen perustuen malliin tai täysin alusta, ja voit mukauttaa lauseketta käyttöliittymän (Intellisense) ohjeiden perusteella.

1. Napsauta tai napauta **Lisää ehto** ja valitse sitten malli tai **Mukautettu ehto**.

    Napsauta tai napauta **Suurempi kuin** tätä ohjeaihetta varten.

    ![Lisää ehto](./media/working-with-rules/rule-conditions.png)

1. Päivitä lauseke määrittämään, milloin sääntöä sovelletaan.

    Muuta tässä ohjeaiheessa nolla 70:ksi, mistä saadaan tämä lauseke:  <br>**Slider1.Value > 70**

## <a name="add-an-action"></a>Lisää toiminto
Toiminnot määrittävät, mitä tapahtuu, kun sääntöä sovelletaan. PowerApps voi luoda toimintoja automaattisesti ohjausobjekteihin tekemiesi muutosten perusteella.

1. Napsauta tai napauta **Määritä toiminnot**.

    ![Määritä toiminnot](./media/working-with-rules/rule-define-actions.png)

1. Napsauta tai napauta vahvistusvalintaikkunassa **Selvä!** , niin PowerApps sieppaa seuraavan muutoksen tai muutokset yhdeksi tai useaksi toiminnoksi.

1. Määritä vähintään yksi ohjausobjekti vastaamaan odotuksia, kun ehto on tosi.

    Vaihda otsikon väriä tätä ohjeaihetta varten.

    ![Sieppaa ominaisuudet](./media/working-with-rules/rule-capture-properties.png)

1. (valinnainen) Tarkista tekemäsi muutokset napsauttamalla tai napauttamalla **Näytä toiminnot**.

    ![Tarkista toiminnot](./media/working-with-rules/rule-review-actions.png)

1. Kun olet lisännyt haluamasi toiminnot, napsauta tai napauta **Valmis**.

1. Tarkista säännön ehto ja toiminnot.

    ![Tarkista sääntö](./media/working-with-rules/rule-review.png)

## <a name="rename-the-rule"></a>Nimeä sääntö uudelleen

1. Pidä hiiren osoitinta kohdan **Rule1** päällä ja napsauta tai napauta Muokkaa-painiketta.

    ![Pidä hiiren osoitinta säännön nimen päällä](./media/working-with-rules/hover-over-rules_name.png)

1. Anna säännölle uusi nimi.

    ![Nimeä sääntö uudelleen](./media/working-with-rules/rename-rule.png)

1. Sulje editori napsauttamalla tai napauttamalla **Valmis**.

## <a name="test-the-rule"></a>Testaa sääntö
1. Esikatsele sovellusta painamalla F5 (tai napsauttamalla oikean yläkulman alueella olevaa toistopainiketta).

    ![Avaa esikatselu](./media/working-with-rules/open-preview.png)

1. Tee määrittämästäsi ehdosta tosi ja vahvista sitten, että toiminnot toimivat haluamallasi tavalla.

    Aseta tässä ohjeaiheessa liukusäätimen arvoksi suurempi kuin 70 ja vahvista, että otsikkotekstin väri muuttuu.

## <a name="see-all-rules"></a>Katso kaikki säännöt
**Säännöt**-välilehdellä näkyvät oletusarvoisesti vain valitun ohjausobjektin säännöt ja kaikki aliohjausobjektit, joita käytetään säännön ehdossa tai toiminnossa. Jos haluat näyttää kaikki sovelluksen säännöt, poista valinta **Näytä vain tämän ohjausobjektin säännöt**-valintaruudusta.

![Poista suodatin](./media/working-with-rules/rules-filter.png)

## <a name="known-limitations"></a>Tunnetut rajoitukset
Tätä kirjoitettaessa:

* Et voi määrittää **ThisItem**-ominaisuutta lomakkeessa tai valikoimassa osana ehtoa.
