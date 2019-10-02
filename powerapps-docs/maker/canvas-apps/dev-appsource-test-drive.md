---
title: Anna asiakkaiden koekäyttää pohjaan perustuvia sovelluksiasi AppSourcessa | Microsoft Docs
description: Käytä AppSourcea pohjaan perustuvien sovellusten jakamiseen asiakkaille ja liidien luomiseen yrityksellesi.
author: tapanm-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 05/08/2017
ms.author: litran
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 1e9ac3428a9621da360fd1cc5f1c376d52352d1b
ms.sourcegitcommit: 60fd1792430b9f3da08ec161cb2277506d795e3a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/01/2019
ms.locfileid: "71705350"
---
# <a name="let-customers-test-drive-your-canvas-app-on-appsource"></a>Anna asiakkaiden koekäyttää pohjaan perustuvia sovelluksiasi AppSourcessa

Oletko kiinnostunut pohjaan perustuvien sovellusten luomisesta PowerAppsissa? Haluatko jakaa pohjaan perustuvan sovelluksen asiakkaillesi? [AppSource.com](https://appsource.microsoft.com) tukee nyt PowerApps Test Drive -ratkaisuja menetelmänä sovellusten jakamiseen asiakkaiden kanssa ja liidien luomiseen yrityksellesi.

## <a name="what-is-a-test-drive-solution"></a>Mikä on Test Drive -ratkaisu?

Test Drive -ratkaisun avulla asiakkaasi voivat testata oikeaa sovellusta rekisteröitymättä PowerApps-palvelupakettia varten tai asentamatta sovelluksia. Asiakkaat vain kirjautuvat sisään osoitteessa AppSource.com käyttämällä Azure Active Directory (AAD) -tiliään ja suorittavat sovelluksen verkkoselaimessa. Ilman Test Drivea asiakkaat voivat vain lukea tietoja sovelluksestasi tai katsoa videon, jossa sitä kuvaillaan. Test Driven avulla asiakas saa paremman kuvan ratkaisustasi ja sovelluksesi toiminnallisuudesta. He pääsevät oikeasti käyttämään sovellusta. Asiakkaat eivät voi katsoa konepellin alle ja tarkastella sovelluksen rakennetta, joten immateriaalioikeutesi on suojattu. Keräämme ja jaamme liiditietoja käyttäjistä, jotka käyttävät Test Drive -sovellustasi, mikä auttaa kasvattamaan liiketoimintaasi.

Tässä on esimerkki [sovellussivusta](https://go.microsoft.com/fwlink/?linkid=848867) AppSource.comissa:

![Esimerkki AppSource-sivusta ](./media/dev-appsource-test-drive/sample-app-source-listing.png)

**Ilmainen kokeiluversio** -linkin valitseminen yllä olevalta sovellussivulta käynnistää siihen liittyvän PowerApps Test Drive -sovelluksen suoraan käyttäjän selaimessa:

![Esimerkki App Web Playeristä](./media/dev-appsource-test-drive/sample-app-web-player.png)

## <a name="how-do-i-build-a-test-drive-solution"></a>Kuinka rakennan Test Drive -ratkaisun?
Sovelluksen rakentaminen Test Drive -ratkaisua varten on kuin sovelluksen luominen yleensä PowerAppsissa, mutta sitä varten käytetään upotettuja tietoja ulkoisten tietolähteiden sijaan. Upotettujen tietojen käyttäminen helpottaa sovelluksen antamista asiakkaasi käyttöön, jotta kynnys sovelluksen kokeiluun olisi mahdollisimman matala. Asiakkaille lopulta levitettävä täysi ratkaisu sisältää yleensä tietoyhteyksiä, mutta upotetut tiedot sopivat hyvin Test Drive -ratkaisuun.

PowerApps tukee suoraan sovellusten rakentamista upotettujen tietojen avulla, joten tarvitset vain sovelluksen käyttämät esimerkkitiedot. Nämä tiedot tulee sisällyttää Excel-tiedostoon yhtenä tai useampana taulukkona. PowerAppsissa noudetaan sitten Excel-taulukkojen tiedot sovellukseen ja niitä käsitellään sovelluksessa, ei ulkoisen yhteyden kautta. Alla kuvatussa kolmivaiheisessa prosessissa näytetään, kuinka tiedot noudetaan ja kuinka niitä käytetään sovelluksessa.

### <a name="step-1-import-data-into-the-app"></a>Vaihe 1: Tuo tietoja sovellukseen
Oletetaan, että sinulla on Excel-tiedosto, jossa on kaksi taulukkoa: **Siteinspector** ja **sitephotos**.

![Tuotavat Excel-taulukot](./media/dev-appsource-test-drive/excel-file.png)

Tuo nämä taulukot PowerAppsiin valitsemalla **Lisää staattisia tietoja sovellukseesi**.

![Lisää staattisia tietoja sovellukseesi](./media/dev-appsource-test-drive/static-data.png)

Nyt taulukot ovat tietolähteinä sovelluksessasi.

![Excel-taulukot tuotuina tietolähteinä](./media/dev-appsource-test-drive/data-sources.png)

### <a name="step-2-handling-read-only-and-read-write-scenarios"></a>Vaihe 2: Käsitellään vain luku-ja luku-ja kirjoitus-tilanteita
Tuodut tiedot ovat *staattisia*, eli niitä voidaan vain lukea. Jos sovelluksesi on vain luku -sovellus (eli se vain näyttää tietoja käyttäjälle), viittaa taulukoihin suoraan sovelluksessa. Jos esimerkiksi haluat käyttää **SiteInspector**-taulukon **Title**-kenttää, käytä kaavassasi tekstiä **SiteInspector.Title**.

Jos sovelluksesi sallii myös kirjoittamisen, nouda tiedot ensin taulukoista *kokoelmaan*, joka on PowerAppsin taulukkomuotoinen tietorakenne. Voit sitten työskennellä kokoelman kanssa taulukon sijaan. Tietojen noutaminen **SiteInspector**- ja **SitePhotos**-taulukoista **SiteInspectorCollect**- ja **SitePhotosCollect**-kokoelmiin:

```powerapps-dot
ClearCollect( SiteInspectorCollect, SiteInspector ); 
ClearCollect( SitePhotosCollect, SitePhotos )
```

Kaava tyhjentää molemmat kokoelmat ja kerää tiedot taulukoista asianmukaiseen kokoelmaan:

* Lataa tiedot kutsumalla tämä kaava jossain kohtaa sovelluksessasi.
* Tarkastele kaikkia sovelluksesi kokoelmia valikossa **Tiedosto** > **Kokoelmat**.
* Katso lisätietoja aiheesta [Luo ja päivitä kokoelma sovelluksessasi](../canvas-apps/create-update-collection.md).

Jos haluat käyttää **Title**-kenttää, käytä kaavassasi tekstiä **SiteInspectorCollect.Title**.

### <a name="step-3-add-update-and-delete-data-in-your-app"></a>Vaihe 3: Lisää, Päivitä ja poista tietoja sovelluksessasi
Olet nähnyt, kuinka tietoja voidaan lukea suoraan kokoelmasta. Nyt näytämme, kuinka voit lisätä, päivittää tai poistaa kokoelman tietoja:

**Lisää kokoelmaan rivi** käyttämällä kaavaa [Collect( DataSource, Item, ... )](../canvas-apps/functions/function-clear-collect-clearcollect.md):

```powerapps-dot
Collect( SiteInspectorCollect,
    {
        ID: Value( Max( SiteInspectorCollect, ID ) + 1 ),
        Title: TitleText.Text,
        SubTitle: SubTitleText.Text,
        Description: DescriptionText.Text
    }
)
```

**Päivitä kokoelman rivi** käyttämällä kaavaa [UpdateIf( DataSource, Condition1, ChangeRecord1 [, Condition2, ChangeRecord2, ...] )](../canvas-apps/functions/function-update-updateif.md):

```powerapps-dot
UpdateIf( SiteInspectorCollect,
    ID = record.ID,
    {
        Title: TitleEditText.Text,
        SubTitle: SubTitleEditText.Text,
        Description: DescriptionEditText.Text
    }
)
```

**Poista kokoelmasta rivi** käyttämällä kaavaa [RemoveIf( DataSource, Condition [, ...] )](../canvas-apps/functions/function-remove-removeif.md):

```powerapps-dot
RemoveIf( SiteInspectorCollect, ID = record.ID )
```

> [!NOTE]
> Tietoja säilytetään kokoelmissa vain, kun sovellusta suoritetaan. Muutokset poistetaan, kun sovellus suljetaan.

Yhteenvetona voit luoda sovelluksestasi version, joka käyttää upotettuja tietoja. Se simuloi tietolähteitä käyttävän sovelluksesi käyttökokemusta. Kun tiedot on upotettu, olet valmis julkaisemaan sovelluksen Test Drive -ratkaisuna AppSource.comissa.

## <a name="how-do-i-list-my-test-drive-solution-on-appsourcecom"></a>Kuinka julkaisen Test Drive -ratkaisun AppSource.comissa?
Kun sovelluksesi on nyt valmis, on aika julkaista se AppSource.comissa. Tämän prosessin aloittamiseksi täytä [sovelluslomake](https://powerapps.microsoft.com/partners/get-listed/) PowerApps.comissa.

Kun olet täyttänyt lomakkeen, saat sähköpostiviestin, jossa on ohjeet sovelluksen lähettämiseen AppSource.comissa julkaisemista varten. Koko prosessin alusta loppuun esittelevän perehdytysdokumentaation voi myös ladata [täältä](https://go.microsoft.com/fwlink/?linkid=851031).

