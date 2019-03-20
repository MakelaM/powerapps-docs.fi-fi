---
title: Suhteen luominen SharePoint-luettelojen välille hakukentän avulla pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Suhteen luominen PowerAppsissa SharePoint-luettelojen välille käyttämällä hakukenttää pohjaan perustuvassa sovelluksessa.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/20/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 32a7c0a6848ee5b9521de65b9af0f28d85939f57
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799728"
---
# <a name="how-to-link-sharepoint-lists-using-a-lookup-field-in-powerapps"></a>SharePoint-luettelojen linkittäminen käyttämällä hakukenttiä PowerAppsissa

Tässä opetusohjelmassa näytetään, miten voit yhdistää kaksi SharePoint-luetteloa hakukentän avulla pohjaan perustuvassa sovelluksessa.

## <a name="overview"></a>Yleiskatsaus

SharePoint sisältää kahdentyyppisiä hakukenttiä:

* **Haku**: linkittää toiseen luetteloon – esimerkiksi *Tilaukset*-luettelolla voi olla hakukenttä, joka linkittää *Asiakas*-luettelon asiakkaisiin;
* **Valinta**: kentän napsauttaminen tai napauttaminen näyttää pienen valikon valittavista kohteista.

Tässä opetusohjelmassa luodaan sovellus, joka käyttää tällaisia hakukenttiä.

### <a name="why-use-a-lookup-field"></a>Perusteet hakukentän käyttämiselle

Yrityksen tiedot ovat suuria ja monimutkaisia. Yhden SharePoint-luettelon tiedot liittyvät usein toiseen luetteloon. Hakukentät ovat ensisijainen tapa yhdistää tällainen yritystieto.

Sinulla voi olla esimerkiksi **Tilaukset**-luettelo, jossa on **Asiakkaat**-luetteloon linkittävä hakukenttä, jotta näet tilauksen tehneen asiakkaan. **Tilaukset**-luettelon hakukenttä antaa sinun hakea myös muita tietoja **Asiakkaat**-luettelosta. Voit käyttää hakukenttää myös **Tilaukset**-luettelon yhdistämiseksi **Tuote**-luetteloon ja tuoda tietoja, joita tarvitset tilatusta tuotteesta, kuten tuotteen kuvat, määritykset, valmistajan tiedot ja niin edelleen.

### <a name="what-are-choice-fields-used-for"></a>Mihin Valinta-kenttiä käytetään?
**Valinta**-kenttiä käytetään erittäin lyhyissä luetteloissa. Erillisen luettelon luomisen sijaan sisällytät luettelon arvot pieneen valikkoon, joka tulee näkyviin, kun napsautat tai napautat **Valinta**-kenttää ja valitset jonkin arvoista.

Esimerkkejä tiedoista ovat asiakkaan tilakoodi, tuotteen saatavuus ja tilakoodit – käytännössä siis mikä tahansa suhteellisen lyhyt kiinteä luettelo. Näistä tiedoista voidaan itse asiassa luoda erillisiä luetteloita ja käyttää **Haku**-kenttää niiden linkittämiseen. On kuitenkin yleensä helpompaa ja nopeampaa toteuttaa ne **Valinta**-kenttinä.

## <a name="create-the-lists-in-sharepoint"></a>Luettelojen luominen SharePointissa
Tässä opetusohjelmassa linkität yhteen kaksi muokattua SharePoint-luetteloa, **Assets** ja **RepairShop**. **Assets**-luetteloa käytetään laitteiston seuraamiseen tiimin sisällä. Koska laitteita rikkoutuu ajoittain, käytämme **RepairShop**-luetteloa paikallisten korjaamojen löytämiseen.

### <a name="the-lookup-fields-used-in-this-example"></a>Tässä esimerkissä käytetyt hakukentät
**RepairShop**-luettelo käyttää *ContactEmail*-kenttää myymälän tunnistamiseen. Tämä luettelo on määritetty ensin, jotta jokaisella **Assets**-luettelon rivillä on paikka, johon viitata.

**Assets**-luettelo sisältää kaksi kenttää:

* toinen on **Haku**-tyyppinen kenttä *RepairShop*, joka käyttää sähköpostiosoitteita **RepairShop**-luettelon merkintöihin viittaamiseen, ja
* toinen on **Valinta**-tyyppinen kenttä *AssetType*, jossa luetellaan laitteistotyypit, joihin tämä resurssi voi kuulua.

Määrität todennäköisesti lisää kenttiä seurattavasta tiedosta riippuen.

### <a name="define-the-repairshop-list-and-add-data"></a>Määritä RepairShop-luettelo ja lisää tiedot
Tämä tehdään ensin, jotta **RepairShop**-merkinnät ovat valittavissasi *Assets.RepairShop*-hakukentässä, kun lisäät tietoja **Assets**-luetteloon.

1. Luo uusi **RepairShop**-luettelo SharePoint-sivustollasi.

    ![](./media/sharepoint-lookup-fields/new-list.png)

2. Lisää *ContactEmail*-kenttä, jonka tyyppi on **Yksi tekstirivi**.

    ![](./media/sharepoint-lookup-fields/add-email-field.png)

3. Lisää muut tarvitsemasi kentät.

4. Napsauta tai napauta **+ Uusi** ja syötä esimerkkitiedot luetteloon. Täytä vähintään kolme riviä eri *ContactEmail*-arvoilla. Kun resurssi on korjattava, valitset jonkin näistä.

    ![](./media/sharepoint-lookup-fields/add-repair-shops.png)

### <a name="define-the-assets-list"></a>Määritä Assets-luettelo
1. Luo uusi **Assets**-luettelo SharePoint-sivustollasi.

2. Napsauta tai napauta plus-merkkiä ja valitse **Lisää**.

    ![](./media/sharepoint-lookup-fields/choose-more-type.png)

3. Lisää **Valinta**-tyyppinen *AssetType*-kenttä ja täytä **Type each choice on a separate line** -tekstiruutuun arvot, jotka haluat näyttää valintavalikossa. Napsauta tai napauta **OK**.

    ![](./media/sharepoint-lookup-fields/define-choice-column.png)

4. Aloita toisen kentän lisääminen kuten vaiheessa 2: napsauta tai napauta plus-merkkiä ja valitse **Lisää**.

5. Lisää **Haku**-tyyppinen *RepairShop*-kenttä, valitse **Get information from** -tekstiruudusta **RepairShop** ja valitse **In this column** -tekstiruudusta *ContactEmail*. Napsauta tai napauta **OK**.

    ![](./media/sharepoint-lookup-fields/setup-lookup-column.png)

6. Lisää muut haluamasi kentät.

## <a name="create-an-app-from-the-assets-list"></a>Sovelluksen luominen Assets-luettelosta
Tämän sovelluksen avulla voit lisätä tietoja **Assets**-luetteloon.

1. [Kirjaudu sisään PowerApps Studioon](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc). Jos olet uusi PowerApps-käyttäjä, [rekisteröidy ilmaiseksi](https://powerapps.microsoft.com) organisaatiosähköpostiosoitteesi avulla.

2. Napsauta tai napauta **Tiedosto**-valikossa (vasemmassa laidassa) **Uusi** ja napsauta tai napauta **SharePoint**.

    ![](./media/sharepoint-lookup-fields/create-app.png)

1. Valitse SharePoint-sivustosi **Viimeisimmät sivustot** -luettelosta tai kirjoittamalla sivustosi URL-osoite suoraan tekstikenttään. Napsauta tai napauta **Siirry**.

    ![](./media/sharepoint-lookup-fields/choose-sharepoint-site.png)

1. Valitse SharePoint-sivustosi pääluettelo, tässä esimerkissä **Assets**. Napsauta tai napauta **Yhdistä**-painiketta oikeassa alakulmassa.

    ![](./media/sharepoint-lookup-fields/choose-main-list.png)


## <a name="add-data-to-the-assets-list"></a>Tietojen lisääminen Assets-luetteloon
Nyt voit suorittaa sovelluksen ja katsoa, miltä hakukenttien tietojen näyttökenttä näyttää.

1. Paina F5 tai valitse Esikatsele ( ![](./media/sharepoint-lookup-fields/preview.png) ).

2. Lisää merkintä napsauttamalla tai napauttamalla symbolia **+** oikeassa yläkulmassa.

3. Kirjoita resurssille **Otsikko**.

4. Napsauta tai napauta avattavaa **AssetType**-valikkonuolta. Näet arvot, jotka syötit luodessasi tämän kentän. Valitse jokin merkinnöistä.

    ![](./media/sharepoint-lookup-fields/fill-asset-type-3.png)

5. Napsauta tai napauta avattavaa **RepairShop**-valikkonuolta. Valitse jokin merkinnöistä.

    ![](./media/sharepoint-lookup-fields/fill-repair-shop-3.png)

6. Tallenna uusi merkintä napsauttamalla tai napauttamalla valintamerkkiä oikeassa yläkulmassa.

7. (valinnainen) Toista tämä menettely ja lisää luetteloon niin monta kohdetta kuin haluat.

8. Palaa oletustyötilaan painamalla Esc-näppäintä.

## <a name="for-more-information"></a>Lisätietoja
* [Esittelyssä haun tuki ja uusi esimerkkisovellus](https://powerapps.microsoft.com/blog/support-for-lookups/)
* [Suorituskyky-, Päivitä-painike, ForAll sekä useiden kenttien haut](https://powerapps.microsoft.com/blog/performance-refresh-forall-multiple-field-lookups-531/)
* [Sovelluksen luominen käyttämällä Common Data Service -tietokantaa](data-platform-create-app.md)
* [Sovelluksen luominen alusta alkaen Common Data Service -tietokannan avulla](data-platform-create-app-scratch.md)
