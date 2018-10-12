---
title: Kirjautuminen sisään ensimmäistä kertaa | Microsoft Docs
description: Uusi koti kaikille sovellusten tekijöille.
author: AFTOwen
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 08/06/2018
ms.author: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3ecf468f8c1b15d20b144aa127fe31c13dba484e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42849745"
---
# <a name="sign-in-to-powerapps-for-the-first-time"></a>Kirjautuminen sisään PowerAppsiin ensimmäistä kertaa

Kun kirjaudut sisään [PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), sivusto tarjoaa monenlaisia vaihtoehtoja omien sovellusten luomiseen, itsesi tai muiden luomien sovellusten avaamiseen ja erilaisten tehtävien suorittamiseen. Tehtävät voivat olla hyvin yksinkertaisia, kuten oikeuksia antavien käyttöoikeuksien tunnistaminen, mutta voit suorittaa myös kehittyneempiä toimintoja, kuten luoda mukautettuja yhteyksiä tiettyihin tietolähteisiin.

Vaihtoehdot jakautuvat kolmelle yleiselle alueelle:

- sivun yläosan otsikko

    ![Otsikko](media/intro-maker-portal/header.png)

- sivun vasemman laidan siirtymispalkki

    ![Siirtymispalkki](media/intro-maker-portal/nav-bar.png)

- sivun keskiosan suuret kuvakkeet

    ![Aloitussivun keskialue](media/intro-maker-portal/center-area.png)

Aloita varmistamalla, että aloitussivu on määritetty oikealle ympäristölle.

## <a name="choose-an-environment"></a>Ympäristön valitseminen

Kun luot sovelluksen, työnkulun, tietoyhteyden tai entiteetin Common Data Service for Appsissa, suurin osa PowerAppsissa tehtävistä toimista rajoittuu tiettyyn ympäristöön. Ympäristöt luovat rajoja erityyppisille töille. Esimerkiksi organisaatiolla voi olla erilliset ympäristöt eri osastoille. Monet organisaatiot käyttävät ympäristöjä vielä kehitteillä olevien sovellusten erottamiseen jo laajaan käyttöön valmiista sovelluksista. Sinulla voi olla käyttöoikeus useisiin ympäristöihin tai esimerkiksi vain yhteen. Voit luoda omia ympäristöjäsi, jos sinulla on siihen asianmukaiset oikeudet.

Otsikon oikealla puolella oleva ympäristövalitsin näyttää nykyisen ympäristön.

![Ympäristövalitsin](media/intro-maker-portal/environment-switcher.png)

Jos luot sovelluksen tietyssä ympäristöstä, et voi nähdä sitä toisesta ympäristöstä käsin. Lisäksi henkilöt, jotka haluavat suorittaa sovelluksesi, tarvitsevat käyttöoikeuden ympäristöön, jossa sen loit.

> [!IMPORTANT]
> Varmista, että olet oikeassa ympäristössä, *ennen* kuin luot sovelluksen, työnkulun tai vastaavan osan. Osia ei voi helposti siirtää yhdestä ympäristöstä toiseen.

Lisätietoja on kohdassa [Ympäristöjen yleiskatsaus](../../administrator/environments-overview.md).

## <a name="choose-an-app-type"></a>Sovelluksen tyypin valitseminen

PowerAppsissa voit luoda ja suorittaa seuraavantyyppisiä sovelluksia:

- **Pohjaan perustuvat sovellukset** tukevat mukautetun käyttöliittymän suunnittelua ja yhteyden muodostamista useissa lähteissä oleviin tietoihin.
- **Mallipohjaisissa sovelluksissa** on vakiokäyttöliittymä ja ne muodostavat yhteyden vain Common Data Service (CDS) for Appsissa oleviin tietoihin. Niissä voit kuitenkin helpommin luoda muita elementtejä, kuten näkymiä, koontinäyttöjä ja erityyppisiä liiketoimintalogiikkoja.

Oletusarvoisesti **aloitussivulla** näytetään pohjaan perustuvien sovellusten luomisen ja suorittamiseen tarvittavat valinnat. Jos haluat nähdä sen sijaan mallipohjaisten sovellusten valinnat, valitse ympäristö, jossa on CDS for Apps -tietokanta. Avaa sitten vasemman alakulman valikko.

![Pohjaan perustuvien ja mallipohjaisten sovellusten välillä vaihtaminen](media/intro-maker-portal/mode-switcher.png)

## <a name="play-or-edit-an-app"></a>Sovelluksen toistaminen tai muokkaaminen

Jos olet jo luonut sovelluksen (tai sen on luonut joku muu ja jakanut sinulle), voit toistaa tai muokata sitä **Sovellukset**-sivulla.

- Voit etsiä pohjaan perustuvan sovelluksen käyttämällä suodatusehtoja, kuten äskettäin avatut sovellukset.

    ![Luettelo pohjaan perustuvista sovelluksista](media/intro-maker-portal/org-apps.png)

    Voit myös etsiä sovellusta kirjoittamalla yhden tai useamman merkin hakukenttään oikean yläkulman lähellä. Kun löydät haluamasi sovelluksen, ellipsikuvaketta napsauttamalla näet vaihtoehdot sovelluksen toistamiseen tai muokkaamiseen.

    ![Ellipsivalikko](media/intro-maker-portal/ellipsis-menu.png)

- Et voi suodattaa mallipohjaisten sovellusten luetteloa, mutta voit myös etsiä sovellusta kirjoittamalla yhden tai useamman merkin hakukenttään oikean yläkulman lähellä. Kun löydät haluamasi sovelluksen, ellipsikuvaketta napsauttamalla näet vaihtoehdot sovelluksen toistamiseen tai muokkaamiseen.

    ![Mallipohjaisten sovellusten luettelo ja avoin ellipsivalikko](media/intro-maker-portal/model-driven-list.png)

## <a name="create-an-app"></a>Sovelluksen luominen

**Aloitussivulla** voit luoda sovelluksia useilla eri tavoilla:

- [luo pohjaan perustuva sovellus automaattisesti tietojoukosta](data-platform-create-app.md)
- [mukauta pohjaan perustuvan sovelluksen valmiiksi luotua mallia](open-and-run-a-sample-app.md)
- [luo pohjaan perustuva sovellus tyhjästä näytöstä lähtien](data-platform-create-app-scratch.md)
- [luo oma mallipohjainen sovellus](../model-driven-apps/overview-model-driven-samples.md)
- [mukauta mallipohjaisen sovelluksen valmiiksi luotua mallia.](../model-driven-apps/build-first-model-driven-app.md)

## <a name="learn-more"></a>Lue lisätietoja

Saat lisätietoja joko pohjaan perustuvista tai mallipohjaisista sovelluksista kahdella tavalla:

- Valitse vasemmassa siirtymispalkissa **Lisätietoja**.
- Valitse otsikon kysymysmerkkikuvake.

    ![Mallipohjaisten sovellusten luettelo ja avoin ellipsivalikko](media/intro-maker-portal/help-icon.png)

Molemmilla tavoilla näet linkkejä tähän dokumentaatioon, PowerApps-yhteisöön (jossa voit jakaa tietoja muiden organisaatioiden käyttäjien kanssa) ja PowerApps-blogiin (jossa ilmoitetaan uusimmista ominaisuuksista).

## <a name="other-common-tasks"></a>Muita yleisiä tehtäviä

Otsikon ja vasemman siirtymispalkin vaihtoehdoilla voit tehdä paljon muutakin kuin luoda ja avata sovelluksia.

### <a name="from-the-header"></a>Otsikon kautta

- Valitsemalla alanuolen voit ladata mobiili- ja muita asiakasohjelmia, joissa voit suorittaa sovelluksia.

    Lisätietoja on ohjeaiheessa [Etsi ja suorita sovelluksia](../../user/index.md).

- Valitsemalla rataskuvakkeen voit esimerkiksi muodostaa yhteyden tietolähteisiin, tarkastella PowerApps-käyttöoikeuksia ja avata sivun, jolla voit suorittaa hallintatehtäviä.

    Lisätietoja saat näistä ohjeaiheista:

  - [Pohjaan perustuvien sovellusten liittimien yleiskatsaus](connections-list.md)
  - [Pohjaan perustuvien sovellusten mukautettujen liittimien luominen ja sertifiointi](register-custom-api.md)
  - [Paikallisen tietoyhdyskäytävän hallitseminen](gateway-management.md)
  - [PowerAppsin hallitseminen](../../administrator/index.md)
  - [Käyttöoikeuksien yleiskatsaus](../../administrator/pricing-billing-skus.md)
  - [Yleiskatsaus mallipohjaisen sovelluksen luomiseen](../model-driven-apps/model-driven-app-overview.md)

### <a name="from-the-left-navigation-bar"></a>Vasemman siirtymispalkin kautta

Laajentaa sovellustesi toimintoja suorittamalla seuraavia tehtäviä:

- Hallitse entiteettejä, asetusjoukkoja ja tietojen integrointia [Common Data Service for Appsissa](../common-data-service/data-platform-intro.md).
- Määritä liiketoimintalogiikka [Microsoft Flow’ssa](https://docs.microsoft.com/flow/getting-started).
- Kehitä, paketoi ja ylläpidä [ratkaisuja](../../developer/common-data-service/introduction-solutions.md).
