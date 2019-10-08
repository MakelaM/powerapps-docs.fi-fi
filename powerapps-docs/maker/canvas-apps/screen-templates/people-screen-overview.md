---
title: People-Screen-malli | Microsoft Docs
description: Tutustu siihen, miten Canvas-sovellusten People-Screen-malli toimii ja miten voit laajentaa näyttöä omiin käyttö tapauksiisi
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 12/30/2018
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: da7f7c037010df0da30e0363f988ac616f9fb6cc
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71995680"
ms.PowerAppsDecimalTransform: true
---
# <a name="overview-of-the-people-screen-template-for-canvas-apps"></a>Kangas sovellusten ihmisinäyttömallin yleiskatsaus

Lisää kangas sovelluksessa People-näyttö, jonka avulla käyttäjät voivat hakea henkilöitä organisaatioissaan. Käyttäjät voivat hakea, valita ja lisätä henkilöitä kokoelmaan. Voit muuttaa haku tulos valikoimassa näkyviä tieto tyyppejä, lähettää sähkö postia henkilöiden valintojen avulla ja tehdä muita mukautuksia.

Voit myös lisätä muita mallipohjaisia näyttöjä, jotka näyttävät eri tietoja Office 365: sta, kuten [sähkö postista](email-screen-overview.md), käyttäjän [kalenterista](calendar-screen-overview.md)ja käyttäjien [saatavuudesta](meeting-screen-overview.md) .

Tässä yleiskatsauksessa opit:
> [!div class="checklist"]
> * Oletus henkilöiden näytön käyttäminen.
> * Näytön muokkaaminen.
> * Ohjeet näytön integroimaan sovelluksiin.

Lisä tietoja tämän näytön oletus toiminnoista on kohdassa [People-Screen viittaus](people-screen-reference.md).

## <a name="prerequisite"></a>Edellytys

Perehtyneisyys näyttöjen ja muiden ohjaus objektien lisäämiseen ja määrittämiseen [, kun luot sovelluksen Powerappsissa](../data-platform-create-app-scratch.md).

## <a name="default-functionality"></a>Oletus toiminto

Henkilö näytön lisääminen mallista:

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) powerappsiin ja luo sitten sovellus tai Avaa olemassa oleva sovellus PowerApps Studio.

    Tässä ohje aiheessa näytetään Puhelin sovellus, mutta samat käsitteet koskevat myös Tablet-sovellusta.

1. Valitse valinta nauhan **Aloitus** -väli lehdeltä **Uusi näyttö** > **henkeä**.

    Oletus arvon mukaan näyttö näyttää seuraavanlaiselta:

    ![Alkuperäisten henkilöiden näytön tila](media/people-screen/people-screen-empty.png)

1. Jos haluat aloittaa käyttäjien etsimisen, valitse Tekstin syöttö ruutu ylhäällä ja ala kirjoittaa työtoverin nimeä. Haku tulokset näkyvät teksti syöte ruudun alla:

    ![henkilöiden näytön haku tila](media/people-screen/people-browse-gall-full.png)

1. Kun valitset henkilöitä haku tuloksista, ne lisätään **Mypeople** -kokoelmaan. Haku palkin syöte arvo nollataan, mikä paljastaa valitsemiesi henkilöiden kokoelman:

    ![henkilöiden näyttö kokoelman tulokset](media/people-screen/people-people-gall-full.png)

## <a name="modify-the-screen"></a>Muokkaa näyttöä

Voit muokata tämän näytön oletus toimintoja [näyttämällä eri tietoja henkilöille](people-screen-overview.md#show-different-data-for-people).

Jos haluat muokata näyttöä edelleen, käytä ohje aiheessa [People-Screen viittaus-viittausta](./people-screen-reference.md) .

### <a name="show-different-data-for-people"></a>Näytä eri tiedot henkilöille

Tämä näyttö käyttää [Office365Users. SearchUser](https://docs.microsoft.com/connectors/office365users/#searchuser) -toimintoa etsimään käyttäjiä organisaatiollesi. Se tarjoaa lisä kenttiä kullekin tapahtumalle sen jälkeen, mitä **Userbrowsegallery** -ohjaus objektissa näkyy. Kenttien lisääminen tai muuttaminen valikoimassa on yksinkertainen prosessi:

1. Valitse **Userbrowsegallery**-kohteessa muokattava selite (tai lisää se ja pidä se valittuna).

1. Kun sen **teksti** -ominaisuus on valittuna, korvaa sisältö kaava rivillä `ThisItem.`

    IntelliSense esittää luettelon kentistä, joita voit valita.

1. Valitse haluamasi kenttä.

    **Text** -ominaisuuden tulee päivittää `ThisItem.{FieldSelection}`.

## <a name="integrate-the-screen-into-an-app"></a>Näytön integroiminen sovellukseen

People-näyttö on tehokas nippu ohjaus objektien omaa oikeutta, mutta se toimii yleensä parhaiten osana suurempaa, monipuolisempaa sovellusta. Voit integroida tämän näytön suurempaan sovellukseen useilla eri tavoilla, esimerkiksi [käyttämällä väli muistissa olevaa henkilöiden luetteloasi](people-screen-overview.md#use-your-cached-list-of-people).

### <a name="use-your-cached-list-of-people"></a>Käytä väli muistissa olevaa henkilö luetteloasi

People-näyttö tallentaa henkilö valinnat **Mypeople** -kokoelmaan. Jos liiketoiminta skenaario edellyttää henkilö hakua, sinun on tiedettävä, miten tätä kokoelmaa käytetään. Täällä käydään läpi, miten voit yhdistää tämän näytön kehittymätön Sähkö posti-näyttöön ja lähettää sähkö posti viestejä käyttäjille **Mypeople** -kokoelmassa. Saat myös tietoa siitä, miten [sähkö postin näyttö](./email-screen-overview.md) toimii.

1. Lisää Office 365 Outlook-tieto lähde sovellukseesi valitsemalla **näkymä** -väli lehti, valitsemalla **tieto lähteet** > **Lisää tieto lähde**ja etsimällä Office 365 Outlook Connector. Saatat joutua valitsemaan **uuden yhteyden** löytääksesi sen.
1. Kun olet lisännyt People-näytön, Lisää uusi tyhjä näyttö. Lisää kyseisessä näytössä takaisin-nuoli kuvake, kaksi teksti syöte ruutua ja lähetä-kuvake.
1. Nimeä näyttö uudelleen nimellä **emaliscreen**, Back-Arrow-kuvake **backicon**-, yksi teksti-syöte-ruutuun **Subjectline**-kohteelle, toinen **Messageleipä-kohteelle**ja lähetä-kuvake **sendicon**-kohteelle.
1. Määritä **Backicon** **onselect** -ominaisuudeksi `Back()`.
1. Määritä **Sendicon** -kohteen **onselect** -ominaisuudeksi Tämä kaava:

    ```powerapps-comma
    Office365.SendEmail( 
        Concat( MyPeople; UserPrincipalName & ";" ); 
        SubjectLine.Text; 
        MessageBody.Text 
    )
    ```
    
    Tässä käytät Outlook Connectoria Sähkö posti viestin lähettämiseen. Ohitat sen `Concat(MyPeople; UserPrincipalName & ";")` vastaanottajien luettelona. Tämä kaava yhdistää kaikki **Mypeople** -kokoelman Sähkö posti osoitteet yhdeksi merkki jonoksi ja erottaa ne toisistaan puoli pisteillä. Tämä ei eroa siitä, että kirjoitat merkki jonon puoli pisteillä eroteltuina suosikki Sähkö posti ohjelmasi "to"-riville.
    * Olet välittämällä `SubjectLine.Text` viestin kohteena ja `MessageBody.Text` viestin leipä tekstinä.
1. Lisää **Sähkö posti** -kuvake People-näytön oikeassa yläkulmassa.
   Vaihda kuvakkeen väriksi mitä tahansa.
1. Määritä **Sendicon** -ominaisuuden **onselect** -ominaisuudeksi `Navigate( EmailScreen; None )`.

    Sinulla on nyt kahden näytön sovellus, jossa voit valita käyttäjiä, säveltää Sähkö posti viestin ja lähettää sen. Voit kokeilla sitä vapaasti, mutta ole varovainen, koska sovellus lähettää sähkö posti viestejä kaikille, jotka lisäät **Mypeople** -kokoelmaan.

## <a name="next-steps"></a>Seuraavat vaiheet

* [Näytä tämän näytön viite asiakirjat](./people-screen-reference.md).
* [Lue lisä tietoja Office 365 Outlook Connectorista](../connections/connection-office365-outlook.md).
* [Lue lisä tietoja Office 365-käyttäjien liittimestä](../connections/connection-office365-users.md).
