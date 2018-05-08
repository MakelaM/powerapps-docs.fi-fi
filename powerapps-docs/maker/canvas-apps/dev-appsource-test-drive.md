---
title: Anna asiakkaiden koekäyttää sovelluksiasi AppSourcessa | Microsoft Docs
description: Käytä AppSourcea sovellusten jakamiseen asiakkaille ja liidien luomiseksi yrityksellesi.
services: ''
suite: powerapps
documentationcenter: na
author: linhtranms
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 05/08/2017
ms.author: litran
ms.openlocfilehash: 5e2a14a2c453dc1aabe8657f7c0ae13c388abb4a
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="let-customers-test-drive-your-apps-on-appsource"></a>Anna asiakkaiden koekäyttää sovelluksiasi AppSourcessa
Oletko kiinnostunut sovellusten luomisesta PowerAppsissa? Onko sinulla sovellus, jonka haluat jakaa asiakkaille? Tuemme nyt PowerApps Test Drive -ratkaisuja osoitteessa [AppSource.com](https://appsource.microsoft.com) menetelmänä sovellusten ja työnkulkujen jakamiseksi asiakkaiden kanssa ja liidien luomiseksi yrityksellesi.

## <a name="what-is-a-test-drive-solution"></a>Mikä on Test Drive -ratkaisu?
Test Drive -ratkaisun avulla asiakkaasi voivat testata oikeaa sovellusta rekisteröitymättä PowerApps-palvelupakettia varten tai asentamatta sovelluksia. Asiakkaat vain kirjautuvat sisään osoitteessa AppSource.com käyttämällä Azure Active Directory (AAD) -tiliään ja suorittavat sovelluksen verkkoselaimessa. Ilman Test Drivea asiakkaat voivat vain lukea tietoja sovelluksestasi tai katsoa videon, jossa sitä kuvaillaan. Test Driven avulla asiakas saa paremman kuvan ratkaisustasi ja sovelluksesi toiminnallisuudesta. He pääsevät oikeasti käyttämään sovellusta. Asiakkaat eivät voi katsoa konepellin alle ja tarkastella sovelluksen rakennetta, joten immateriaalioikeutesi on suojattu. Keräämme ja jaamme liiditietoja käyttäjistä, jotka käyttävät Test Drive -sovellustasi, mikä auttaa kasvattamaan liiketoimintaasi.

Tässä on esimerkki [sovellussivusta](https://go.microsoft.com/fwlink/?linkid=848867) AppSource.comissa:

![Esimerkki-AppSource-sivu ](./media/dev-appsource-test-drive/sample-app-source-listing.png)

**Ilmainen kokeiluversio** -linkin valitseminen yllä olevalta sovellussivulta käynnistää siihen liittyvän PowerApps Test Drive -sovelluksen suoraan käyttäjän selaimessa:

![Esimerkki App Web Playeristä](./media/dev-appsource-test-drive/sample-app-web-player.png)

## <a name="how-do-i-build-a-test-drive-solution"></a>Kuinka rakennan Test Drive -ratkaisun?
Sovelluksen rakentaminen Test Drive -ratkaisua varten on kuin sovelluksen luominen yleensä PowerAppsissa, mutta sitä varten käytetään upotettuja tietoja ulkoisten tietolähteiden sijaan. Upotettujen tietojen käyttäminen pienentää estettä sovelluksen antamiseksi asiakkaasi käyttöön, jotta kynnys sovelluksen kokeiluun olisi mahdollisimman matala. Asiakkaille lopulta levitettävä täysi ratkaisu sisältää yleensä tietoyhteyksiä, mutta upotetut tiedot sopivat hyvin Test Drive -ratkaisua varten.

PowerApps tukee suoraan sovellusten rakentamista upotetuilla tiedoilla, joten tarvitset vain sovelluksen käyttämät esimerkkitiedot. Nämä tiedot tulee sisällyttää Excel-tiedostoon yhtenä tai useampana taulukkona. PowerAppsissa sitten noudetaan Excel-taulukkojen tiedot sovellukseen ja niitä käsitellään siinä ulkoisen tietolähteen sijasta. Alla kuvatussa kolmen vaiheen prosessissa näytetään, kuinka tiedot noudetaan ja kuinka niitä käytetään sovelluksessa.

### <a name="step-1-import-data-into-the-app"></a>Vaihe 1: Tietojen tuominen sovellukseen
Oletetaan, että sinulla on Excel-tiedosto, jossa on kaksi taulukkoa: **SiteInspector** ja **SitePhotos**.

![Tuotavat Excel-taulukot](./media/dev-appsource-test-drive/excel-file.png)

Tuo nämä taulukot PowerAppsiin valitsemalla **Lisää staattisia tietoja sovellukseesi**.

![Lisää staattisia tietoja sovellukseesi](./media/dev-appsource-test-drive/static-data.png)

Nyt taulukot ovat tietolähteinä sovelluksessasi.

![Excel-taulukot tuotuina tietolähteinä](./media/dev-appsource-test-drive/data-sources.png)

### <a name="step-2-handling-read-only-and-read-write-scenarios"></a>Vaihe 2: Vain luku- ja luku ja kirjoitus -skenaarioiden käsittely
Tuodut tiedot ovat *staattisia*, eli niitä voidaan vain lukea. Jos sovelluksesi on vain luku -sovellus (eli se vain näyttää tietoja käyttäjälle), viittaa taulukoihin suoraan sovelluksessa. Jos esimerkiksi haluat käyttää **SiteInspector**-taulukon **Title**-kenttää, käytä kaavassasi tekstiä **SiteInspector.Title**.

Jos sovelluksesi sallii myös kirjoittamisen, nouda tiedot ensin taulukoista *kokoelmaan*, joka on PowerAppsin taulukkomuotoinen tietorakenne. Voit sitten työskennellä kokoelman kanssa taulukon sijaan. Tietojen noutaminen **SiteInspector**- ja **SitePhotos**-taulukoista **SiteInspectorCollect**- ja **SitePhotosCollect**-kokoelmiin:

```
ClearCollect(SiteInspectorCollect,SiteInspector); ClearCollect(SitePhotosCollect,SitePhotos)
```

Kaava tyhjentää kummankin kokoelman ja kerää tiedot taulukoista asianmukaiseen kokoelmaan:

* Lataa tiedot kutsumalla tämä kaava jossain kohtaa sovelluksessasi.
* Tarkastele kaikkia sovelluksesi kokoelmia valikossa **Tiedosto** > **Kokoelmat**.
* Katso lisätietoja aiheesta [Luo ja päivitä kokoelma sovelluksessasi](../canvas-apps/create-update-collection.md).

Jos haluat käyttää **Title**-kenttää, käytä kaavassasi tekstiä **SiteInspectorCollect.Title**.

### <a name="step-3-add-update-and-delete-data-in-your-app"></a>Vaihe3: Tietojen lisääminen, päivitys ja poistaminen sovelluksessa
Olet nähnyt, kuinka tietoja voidaan lukea suoraan kokoelmasta; nyt näytämme kuinka voit lisätä, päivittää tai poistaa kokoelman tietoja:

**Lisää kokoelmaan rivi** käyttämällä kaavaa [Collect( DataSource, Kohde, ... )](../canvas-apps/functions/function-clear-collect-clearcollect.md):

```
Collect(SiteInspectorCollect,{ID:Value(Max(SiteInspectorCollect, ID)+1),
    Title:TitleText.Text,SubTitle:SubTitleText.Text,Description:DescriptionText.Text)
```

**Päivitä kokoelman rivi** käyttämällä kaavaa [UpdateIf( DataSource, Ehto1, Muutostietue1 [, Ehto2, Muutostietue2, ...] )](../canvas-apps/functions/function-update-updateif.md):

```
UpdateIf(SiteInspectorCollect,ID=record.ID,
    {Title:TitleEditText.Text,SubTitle:SubTitleEditText.Text,Description:DescriptionEditText.Text)
```

**Poista kokoelmasta rivi** käyttämällä kaavaa [RemoveIf( DataSource, Ehto [, ...] )](../canvas-apps/functions/function-remove-removeif.md):

```
RemoveIf(SiteInspectorCollect,ID=record.ID)
```

> [!NOTE]
> Tietoja säilytetään kokoelmissa vain, kun sovellusta suoritetaan. Muutokset poistetaan, kun sovellus suljetaan.

Yhteenvetona voit luoda sovelluksestasi version, joka käyttää upotettuja tietoja. Se simuloi tietolähteitä käyttävän sovelluksesi käyttökokemusta. Kun tiedot on upotettu, olet valmis julkaisemaan sovelluksen Test Drive -ratkaisuna AppSource.comissa.

## <a name="how-do-i-list-my-test-drive-solution-on-appsourcecom"></a>Kuinka julkaisen Test Drive -ratkaisun AppSource.comissa?
Nyt kun sovelluksesi on valmis, on aika julkaista se AppSource.comissa. Tämän prosessin aloittamiseksi ole hyvä ja täytä [sovelluslomake](https://powerapps.microsoft.com/partners/get-listed/) PowerApps.comissa.

Kun olet täyttänyt lomakkeen, saat sähköpostiviestin, jossa on ohjeet sovelluksen lähettämiseksi julkaisua varten AppSource.comissa. Koko prosessin alusta loppuun näyttävän perehdytysdokumentaation voi myös ladata [täältä](https://go.microsoft.com/fwlink/?linkid=851031).

