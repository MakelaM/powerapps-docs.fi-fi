---
title: Mallipohjaisen sovelluksen näkymän luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Lue, miten voit luoda näkymän tai muokata näkymää
ms.custom: ''
ms.date: 06/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: bd1d393d-16ea-40ac-8136-26643c37dd2a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
ms.openlocfilehash: 215f927b68decac864a2f1b667f64a7649827682
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678560"
---
# <a name="understand-model-driven-app-views"></a>Tutustu mallipohjaisen sovelluksen näkymiin

<a name="BKMK_CreatingAndEditingViews"></a>   

Voit määrittää PowerApps-sovelluksissa näkymien avulla, miten tietyn entiteetin tietueluettelo näytetään sovelluksessa. Näkymä määrittää:

- Näytettävät sarakkeet
- Kuinka leveitä sarakkeiden kuuluu olla
- Miten tietueluettelo lajitellaan oletusarvoisesti
- Mitä oletussuodattimia olisi sovellettava rajoittamaan, mitkä tietueet näkyvät luettelossa

Sovelluksessa näytetään usein avattava luettelo näkymistä, jotta käyttäjillä olisi käytettävissä erilaisia näkymiä entiteettitietojen tarkastelemiseen.

Yksittäisissä näkymissä näkyvät tietueet näytetään luettelossa, jota kutsutaan joskus myös ruudukoksi. Käyttäjät voivat usein muuttaa ruudukon oletusasetuksia, kuten siinä käytettävää lajittelua, sarakkeiden leveyttä ja suodattimia, jotta he löytäisivät heille olennaisimmat tiedot helpommin. Näkymät määrittävät myös sovelluksessa käytettävien kaavioiden tietolähteen.  
  
## <a name="types-of-views"></a>Näkymätyypit  
  
Näkymätyyppejä on kolme: *henkilökohtainen*, *järjestelmä* ja *julkinen*.

Tässä ohjeaiheessa on tietoja siitä, miten järjestelmänvalvojat ja järjestelmämukauttajat käsittelevät järjestelmä- ja julkisia näkymiä. 
  
### <a name="personal-views"></a>Henkilökohtaiset näkymät  
  
 Sinulla ja kellä tahansa muulla, jolla on vähintään Käyttäjä-tason käyttöoikeus Tallennettu näkymä -entiteetin toimintoihin, on mahdollisuus myös luoda omia näkymiä. Järjestelmänvalvojana voit muokata jokaisen toiminnon käyttöoikeustasoa käyttöoikeusroolissa määrittääksesi syvyyden, jolla ihmiset voivat luoda, lukea, kirjoittaa, poistaa, määrittää tai jakaa henkilökohtaisia näkymiä.

Henkilökohtaiset näkymät ovat yksilöiden omaisuutta, ja koska heillä on oletusarvoinen Käyttäjä-tason käyttöoikeus, nämä näkymät näkyvät vain kyseiselle henkilölle sekä kaikille muille, joiden kanssa henkilö on halunnut jakaa omat näkymänsä. Voit luoda omia näkymiä tallentamalla kyselyn, joka määritetään erikoishaun avulla tai käyttämällä Tallenna suodattimet uusina näkyminä ja Tallenna suodattimet nykyiseen näkymään -asetuksia näkymäluettelossa. Näitä näkymiä sisällytetään yleensä sovelluksessa käytettävissä olevien järjestelmänäkymä- tai julkisten näkymien luetteloiden loppuun. Voit luoda uuden henkilökohtaisen näkymän, joka perustuu järjestelmä- tai julkisen näkymään, mutta et voi luoda järjestelmä- tai julkista näkymää, joka perustuu henkilökohtaiseen näkymään.
  
### <a name="system-views"></a>Järjestelmänäkymät
Järjestelmänvalvojat ja järjestelmämukauttajat voivat muokata järjestelmänäkymiä. Järjestelmänäkymät ovat erityisiä näkymiä, joista sovellus on riippuvainen ja jotka ovat olemassa järjestelmäentiteettejä varten tai luodaan automaattisesti, kun luot mukautettuja entiteettejä. Nämä näkymät ovat suunniteltu erityisiä tarkoituksia varten ja sisältävät joitain lisätoimintoja. 


|Järjestelmänäkymät  |Kuvaus  |
|---------|---------|
|Pikahaku     | Oletusnäkymä, kun haku suoritetaan pikahaun avulla. Tämä näkymä määrittää myös haettavat kentät, kun käytät pikahaku- ja valintanäkymän hakuominaisuuksia.        |
|Erikoishaku     |  Oletusnäkymä, jossa hakutulokset näytetään, kun käytät erikoishakua. Tämä näkymä määrittää myös oletusarvoiset sarakkeet, kun luot uuden, mukautetun julkisen tai henkilökohtaisen näkymän ilman mallinäkymää.       |
|Liittyvä     |  Oletusnäkymä, joka luettelee tietueeseen liittyvät entiteetit.       |
|Haku     | Näkymä, joka näytetään valitessa hakukenttään määritettävää tietuetta.        |

Näitä näkymiä ei näytetä näkymävalitsimessa ja et voi käyttää niitä lomakkeen aliluetteloissa tai koontinäytön luettelona. Et voi poistaa näitä näkymiä tai poistaa niitä käytöstä. Lisätietoja: [Näkymien poistaminen](remove-views.md)

Järjestelmänäkymät ovat organisaation omistamia, jotta ne näkyisivät kaikille. Esimerkiksi jokaisella käyttäjällä on organisaatiotason käyttöoikeus Näkymä (SavedQuery) -entiteetin tietueiden lukemiseen. Nämä näkymät liittyvät tiettyihin entiteetteihin ja näkyvät ratkaisunhallinnassa. Voit sisällyttää näitä näkymiä ratkaisuihin, koska ne liittyvät entiteettiin.

### <a name="public-views"></a>Julkiset näkymät

Julkiset näkymät ovat yleiskäyttöisiä näkymiä, joita voit mukauttaa omien tarpeidesi mukaan. Nämä näkymät ovat käytettävissä näkymävalitsimessa ja voit käyttää niitä lomakkeen aliruudukoissa tai koontinäytön luettelona. Jotkin julkiset näkymät ovat oletusarvoisesti olemassa järjestelmäentiteettejä ja kaikkia mukautettuja entiteettejä varten. Esimerkiksi kun luot uuden mukautetun entiteetin, se tulee sisältämään seuraavan julkisten ja järjestelmänäkymien yhdistelmän.


|Nimi  |Tyyppi  |
|---------|---------|
|Aktiivinen *entiteetin monikkomuotoinen nimi*     |  Julkinen       |
|Passiivinen *entiteetin monikkomuotoinen nimi*    |  Julkinen       |
|Pikahaku, aktiiviset *entiteetin monikkomuotoinen nimi*     | Pikahaku        |
|*entiteetin nimi* Erikoishakunäkymä     | Erikoishaku        |
|*entiteetin nimi* Liittyvä-näkymä     |  Liittyvä       |
|*entiteetin nimi* Valintanäkymä     | Haku        |

Voit luoda mukautettuja julkisia näkymiä. Voit poistaa minkä tahansa mukautetun julkisen näkymän, jonka olet luonut hallitsemattomassa ratkaisussa. Et voi poistaa järjestelmän määrittämiä julkisia näkymiä. Mukautetut julkiset näkymät, jotka on lisätty tuomalla hallittu ratkaisu, saattavat sisältää hallittuja ominaisuuksia, jotka voivat estää niiden poistamisen, ellei hallittua ratkaisua poisteta.

## <a name="places-where-you-can-access-the-view-editor-to-create-or-edit-views"></a>Paikat, joissa voit käyttää näkymäeditoria näkymien luomiseen tai muokkaamiseen

- PowerApps-sivusto: Näkymän suunnitteluohjelma löytyy kohdasta **Mallipohjainen** alue > **Tieto** > **kohteet** > **-näkymä** -välilehti. Avaa aiemmin luotu näkymä tai luo uusi. Lisätietoja: [Näkymän luominen tai muokkaaminen](create-and-edit-views.md)
- Sovelluksen suunnittelutoiminto: Jos työskentelet sovelluksen sisällä, voit myös käyttää sovelluksen suunnittelutoimintoa, jossa voit luoda näkymiä yksinkertaisen ja intuitiivisen käyttöliittymän vedä ja pudota -toimintojen avulla. Lisätietoja: [Opetusohjelma: Luo ja muokkaa julkisia tai järjestelmänäkymiä sovelluksen suunnittelutoiminnon avulla](create-edit-views-app-designer.md)
- Ratkaisunhallinta: Jos olet jo kokeneempi Dynamics 365 -käyttäjä, haluat ehkä käyttää ratkaisunhallintaa. Lisätietoja: [Kehittyneiden sovellusten luomiseen ja mukauttamiseen tarkoitettuihin alueisiin siirtyminen](advanced-navigation.md#solution-explorer)
 
## <a name="customize-views"></a>Näkymien mukauttaminen

Järjestelmämukauttajat voivat mukauttaa ohjausobjektien kautta näkyviä näkymiä tekemällä ruudukoista (luetteloista) muokattavia ja yhteensopivia Unified Interfacea varten. Seuraavat ohjausobjektit ovat käytössä:

- Muokattava ruudukko: Käyttäjät voivat tehdä monipuolisia muokkauksia suoraan ruudukoissa ja aliruudukoissa verkkosovelluksen, tabletin tai puhelimen kautta. Lisätietoja: [Ruudukoiden muokattavaksi muuttaminen mukautetun Muokattava ruudukko -ohjausobjektin avulla](make-grids-lists-editable-custom-control.md)
- Vain luku -ruudukko: Hyödyntää reagoivan suunnittelun periaatteiden tarjotakseen käyttäjille parhaan mahdollisen tarkastelu- ja vuorovaikutuskokemuksen kaiken kokoisilla laitteilla. Lisätietoja: [Unified Interface -sovellusten ominaisuuksien määrittäminen](specify-properties-for-unified-interface-apps.md)

## <a name="next-steps"></a>Seuraavat vaiheet

[Luo tai muokkaa näkymiä](create-and-edit-views.md)
