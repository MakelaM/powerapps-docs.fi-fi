---
title: Alustan sovellusten PowerApps Component Framework | Microsoft Docs
description: Luo koodi komponentteja kangas sovelluksille
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 08/31/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d100dc3-bd82-4b45-964c-d90eaebc0735
ms.openlocfilehash: e1c6b4bad1280bdabf8c27e30396b368276ff10b
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72347218"
---
# <a name="powerapps-component-framework-for-canvas-apps"></a>PowerApps Component Framework for Canvas-sovellukset

> [!IMPORTANT]
> Ominaisuus on edelleen kokeellinen, ja se on oletus arvon mukaan poistettu käytöstä. Lisä tietoja on kohdassa [Experimental-ja Preview-ominaisuudet](../../maker/canvas-apps/working-with-experimental.md).

PowerApps Component Frameworkin avulla sovelluksen tekijät voivat luoda koodi komponentteja, joita voidaan käyttää sovelluksessa tai sovellusten välillä. Lisä tietoja: [Powerapps Component Framework-yleiskatsaus](overview.md) 

Tämän kokeellisen esikatselun avulla PowerApps Component Framework mahdollistaa sen, että sovelluksen tekijät voivat luoda koodi komponentteja, tehdä virheen korjauksen, tuoda ja lisätä niitä pohjaan sovelluksiin PowerApps CLI-työkaluilla. Vain määritettyjä ohjelmointi raja pintoja tuetaan tässä kokeiluluonteisessä esikatselussa. Suosittelemme, että tarkistat kunkin ohjelmointi raja pinnan ja selvität, tukeeko se pohjaan nähden sovelluksia. 

> [!WARNING]
> Koodi komponentit sisältävät koodia, jota Microsoft ei välttämättä pysty muodostamaan, ja se voi käyttää suojaus tunnuksia ja-tietoja. Kun lisäät koodi komponentteja sovellukseen, varmista, että koodi komponentti ratkaisut ovat perä isin luotettavasta lähteestä.

## <a name="prerequisites"></a>Edellytykset

Järjestelmänvalvojan oikeudet vaaditaan, jotta PowerApps-komponentti ominaisuus voidaan ottaa käyttöön ympäristössä.

> [!IMPORTANT]
> Oletusarvoisesti PowerApps Component Framework on otettu käyttöön mallipohjaisia sovelluksia varten.

## <a name="enable-powerapps-component-framework-feature"></a>Ota käyttöön PowerApps Component Framework-ominaisuus

Jos haluat lisätä koodi komponentteja sovellukseen, sinun on otettava PowerApps Component Framework-ominaisuus käyttöön kaikissa ympäristöissä, joissa haluat käyttää niitä. Jotta ympäristö voi käyttää koodi komponentteja sovellustesi sisällä:

1. Kirjaudu sisään [PowerAppsiin](https://powerapps.microsoft.com/en-us/).

2. Valitse **Asetukset** -kuvake ja valitse sitten **hallinta keskus**.
    
    ![Asetukset ja hallinta keskuksen](media/select-admin-center-from-settings.png "Asetukset ja hallinta keskus") 

3. Valitse ympäristö, jossa haluat ottaa tämän ominaisuuden käyttöön, valitse kolme pistettä ( **..** .) ja valitse sitten **Asetukset**.

4. Valitse **tuotteet** -väli lehdeltä **Ominaisuudet**.

   ![Ota powerapps Component Framework]käyttöön ota(media/enable-pcf-feature.png "powerapps Component Framework käyttöön")

5. Valitse käytettävissä olevien ominaisuuksien luettelo-kohdassa Siirry **Powerapps Component Framework for Canvas-sovelluksiin** **-asetukseksi** .

6. Avaa nyt sovellus, johon haluat lisätä koodi komponentin, ja siirry kohtaan **tiedosto**  > **sovellus asetukset** ja valitse **lisä asetukset**.

   ![Ota powerapps Component Frameworkin komponentit](media/enable-components-for-pcf.png "käyttöön, jotta powerapps Component Framework-komponentit otetaan") käyttöön
   
7. Ota **komponentit** käyttöön- **asetukseksi käytössä** **kokeellinen ominaisuus** -osiossa.

## <a name="implementing-code-components"></a>Koodi komponenttien toteuttaminen

Kun olet ottanut PowerApps Component Framework-ominaisuuden käyttöön ympäristössäsi, voit aloittaa koodi komponenttien logiikan käyttöönoton. [Toteuta esimerkki komponentti](implementing-controls-using-typescript.md) -aihe esittelee vaiheittaisen prosessin, jolla luodaan mukautetun logiikan ja luettelo tiedoston toteuttamiseen liittyviä koodi komponentteja, suoritetaan virheen korjaus prosessi, luodaan ratkaisun zip-tiedosto ja tuodaan ratkaisua common Tieto palvelu.

> [!NOTE]
> Koodi komponentit ovat samat sekä mallipohjaisissa sovelluksissa että pohjaan perustuvissa sovelluksissa (kokeellinen esikatselu). Ainoa ero on koodi komponenttien lisääminen. 

## <a name="add-components-to-a-canvas-app"></a>Komponenttien lisääminen kangas sovellukseen

> [!NOTE]
> Jos haluat lisätä koodi komponentteja kenttään tai entiteettiin mallipohjaisia sovelluksia varten, tutustu Ohje artikkeliin [koodi komponenttien lisääminen mallipohjaisia sovelluksiin](add-custom-controls-to-a-field-or-entity.md)

Koodi komponenttien lisääminen kangas sovellukseen:

1. Siirry PowerApps Studio.
2. Luo uusi kangas sovellus tai muokkaa aiemmin luotua sovellusta, johon haluat lisätä koodi komponentin.

   > [!IMPORTANT]
   > Varmista, että ratkaisun zip-tiedosto on jo [tuotu](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/import-update-export-solutions) Common Data Service, ennen kuin jatkat seuraavaan vaiheeseen.

3. Siirry kohtaan **lisää**  > **komponentit**  > **Import Component**. 
 
    ![Lisää komponentteja](media/insert-components-import.png "Lisää osia")

4. Valitse **koodi (kokeellinen)** -väli lehti, lisää komponentti luettelosta ja valitse sitten **tuo**. Tämä lisää malli osan **komponentit** -valikkoon.

    ![Import Sample Component](media/import-component-add-sample-component.png "Import-malli komponentti")

5. Siirry **komponentteihin** ja valitse komponentti, jotta voit lisätä sen sovellukseen.

   ![Lisää malli komponentti](media/add-sample-component-from-list.png "Lisää malli-osa")

## <a name="delete-a-code-component"></a>Poista koodi komponentti 

Jos haluat poistaa koodi osan kangas sovelluksesta, valitse poistettava koodi komponentti ja valitse sitten valikosta **Poista** -painike. Kun koodi komponentti poistetaan sovelluksesta, kaikki koodi komponentti elementit poistetaan sovelluksesta ja sovellus paketista. 

## <a name="update-existing-code-components"></a>Päivitä aiemmin luodut koodi komponentit

Kun päivität koodi komponentteja, Määritä *versio* -määrite luettelo tiedostossa, jotta viimeisimmät muutokset näkyvät suoritus palvelussa. Kun päivität olemassa olevia koodi komponentteja kangas sovelluksissa, sinun ei tarvitse päivittää *versio* -määritettä. Kangas sovellukset valitsevat uusimman koodi komponentin ja näyttävät sen suorituksen aikana. Kangas sovelluksissa voi olla vain yksittäinen versio samasta komponentista.

> [!NOTE]
> Aiemmin luodut koodi komponentit päivitetään vain, kun sovellus suljetaan tai avataan uudelleen PowerApps Studio. Kun avaat sovelluksen uudelleen, se pyytää sinua päivittämään koodi komponentit. Vain koodi komponenttien poistaminen tai koodi osan lisääminen takaisin sovellukseen ei päivitä komponentteja.

## <a name="see-also"></a>Katso myös

[PowerApps Component Frameworkin yleiskatsaus](overview.md)<br/>
[Toteuta esimerkki komponentti](implementing-controls-using-typescript.md)

