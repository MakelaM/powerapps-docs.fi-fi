---
title: Mallipohjaisen sovelluksen lomakeominaisuudet PowerAppsissa | MicrosoftDocs
description: Tutustu päälomakeominaisuuksiin
Keywords: Main form properties; Dynamics 365
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 4ed30bb7-dca1-4de8-80f3-842152ea921a
ms.openlocfilehash: 4aec7fd8a117257d4f21ac2f692643785fd21791
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39677104"
---
# <a name="model-driven-app-form-properties"></a>Mallipohjaisen sovelluksen lomakeominaisuudet 

Voit käyttää **lomakeominaisuuksia** ratkaisunhallinnassa. Kun olet **Osat**-kohdassa, laajenna **Entiteetit**, laajenna haluamasi entiteetti ja valitse **Lomakkeet**. Avaa lomakeluettelosta lomake, jonka tyyppi on **Pää**. Valitse sitten **Aloitus**-välilehdeltä **Lomakeominaisuudet**.

![lomakeominaisuudet](media/form-properties.png)

Lomakeominaisuudet on lueteltu seuraavassa taulukossa:  
  
|Välilehti|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Tapahtumat**|**Lomakekirjastot**|Hallitse, mitkä JavaScript-verkkoresurssit ovat käytettävissä lomakkeessa ja missä järjestyksessä ne ladataan.|  
||**Tapahtumakäsittelijät**|Määritä, mitkä lomakekirjastojen JavaScript-funktiot suoritetaan lomaketapahtumille `OnLoad` ja `OnSave`, ja missä järjestyksessä ne suoritetaan.|  
|**Näyttö**|**Lomakkeen nimi**|Anna nimi, joka on käyttäjille merkityksellinen. Tämä nimi näytetään ihmisille, kun he käyttävät lomaketta. Jos he voivat käyttää useita lomakkeita, jotka on määritetty entiteetille, he käyttävät tätä nimeä lomakkeiden erotteluun.|  
||**Kuvaus**|Anna kuvaus, jossa kerrotaan, miten tämän lomake eroaa muista päälomakkeista. Tämä kuvaus näkyy vain entiteetin lomakeluettelossa ratkaisunhallinnassa.|  
||**Lomakeavustaja**|Valitse valintaruutu, jos haluat ottaa käyttöön lomakeavustajan tai näyttää lomakkeen laajennettuna oletusarvon mukaan.|
||**Sivulla siirtyminen**|Voit poistaa siirtymiskohteet näkyvistä.<br /><br /> Päivitettyjen entiteettien lomakkeissa tämä tarkoittaa, että näkyvän tietueen ensisijaista nimiarvoa ei näytetä siirtymispalkissa liittyviin näkymiin pääsemiseksi.<br /><br /> Klassisen esitystavan lomakkeissa ei näytetä siirtymisvalintoja, joilla voidaan valita liittyviä näkymiä.|  
||**Kuva**|Kun entiteetillä on kuvakenttä ja entiteettien **Ensisijainen kuva** -asetus on määritetty, tämä asetus ottaa käyttöön tämän kuvakentän lomakkeen otsikossa.<br /><br /> Katso lisätietoja entiteetin asetuksista kohdasta [Entiteetin asetuksien ottaminen käyttöön tai pois käytöstä](../common-data-service/edit-entities.md#enable-or-disable-entity-options).|  ||**Näyttö**|**Määritä enimmäisleveys (kuvapisteinä)** lomakkeen leveyden rajoittamiseksi. Oletusarvo on 1900.|  
||**Näyttö**|Kirjoita tähän lomakkeen leveyden enimmäisarvo kuvapisteinä.|
|**Parametrit**|**Parametrit**|Jokainen lomake voidaan avata koodilla URL-osoitteen kautta. URL-osoite voi sisältää myös tietoja, jotka voidaan välittää lomakkeeseen käyttämällä kyselymerkkijonoa, joka liitetään URL-osoitteeseen. Kyselymerkkijono voi näyttää esimerkiksi seuraavalta:<br />`?p_firstName=Jim&p_lastName=Daly`<br /><br /> Suojaussyistä lomakkeet eivät hyväksy mitään tuntemattomia kyselymerkkijonon parametreja. Käytä tätä parametriluetteloa määrittääksesi parametrit, jotka tämän lomakkeen tulee hyväksyä tukeakseen koodia, joka lähettää tiedot lomakkeisiin kyselymerkkijonon avulla.<br /><br /> Tietojen nimi ja tyyppi tarkistetaan eikä lomake avaudu, jos siihen toimitetaan virheellisiä kyselymerkkijonon parametreja.<br /><br />**Huomautus:** nimen alussa ei voi olla alaviiva (_) tai crm\_. Nimen alussa on oltava aakkosnumeerisia merkkejä ja niiden jälkeen alaviiva (\_). Esimerkiksi: parametri_1 tai 1_parametri. Nimi ei voi sisältää yhdysmerkkejä (-), kaksoispisteitä (:), puolipisteitä (;), pilkkuja (,) tai pisteitä (.). <br /><br />|  
|**Muut kuin tapahtumapohjaiset riippuvuudet**|**Riippuvaiset kentät**|Kullakin tapahtumakäsittelijällä on vastaava **Riippuvaiset kentät** -ominaisuus, jotta kaikki komentosarjan tarvitsemat kentät voidaan rekisteröidä. Riippuvaisia kenttiä ei voi poistaa.<br /><br /> Jotkin komentosarjat toimivat lomakkeessa, mutta niitä ei ole määritetty tapahtumakäsittelijässä. Komentopalkista aloitetuissa komentosarjoissa ei ole paikkaa riippuvaisten kenttien rekisteröintiä varten. Tämä lomakeominaisuus tarjoaa paikan näiden riippuvaisten kenttien rekisteröinnille.|  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja sen osien käyttäminen](use-main-form-and-components.md)