---
title: Mallipohjaisen sovelluksen näkymän luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Lisätietoja näkymän luomisesta tai muokkaamisesta
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="understand-model-driven-app-views"></a>Tietoja mallipohjaisen sovelluksen näkymistä

<a name="BKMK_CreatingAndEditingViews"></a>   

Voit määrittää PowerApps-sovelluksissa näkymien avulla, miten tietyn entiteetin tietueluettelo näytetään sovelluksessa. Näkymä määrittää:

- Näytössä näkyvät sarakkeet
- Miten leveitä sarakkeiden pitäisi olla
- Kuinka tietueiden luettelo lajitellaan oletusarvoisesti
- Mitä oletussuodattimia olisi sovellettava rajoittamaan, mitkä tietueet näkyvät luettelossa

Avattavan luettelon näkymät esitetään usein niin, että ihmisillä on erilaisia näkymiä tietueen tiedoille.

Tietueet, jotka ovat näkyvissä yksittäisissä näkymissä, näkyvät luettelossa, jota kutsutaan joskus ruudukoksi, joka tarjoaa usein vaihtoehtoja, jotta ihmiset voivat muuttaa oletuslajittelua, sarakkeiden leveyttä ja suodattimia, joiden avulla on helpompi tarkastella tietoja, jotka ovat heille tärkeitä. Näkymät määrittävät sovelluksessa käytettävien kaavioiden tietojen lähteen.  
  
## <a name="types-of-views"></a>Näkymien tyypit  
  
Näkymätyyppejä on kolme: *henkilökohtainen*, *järjestelmä* ja *julkinen*.

Tässä ohjeaiheessa on tietoja siitä, miten järjestelmänvalvojat ja järjestelmän mukauttajat käsittelevät järjestelmää ja julkisia näkymiä. 
  
### <a name="personal-views"></a>henkilökohtaiset näkymät  
  
 Sinulla ja jollakulla muulla, jolla on vähintään Käyttäjä-tason käyttöoikeus toimiin Saved View -tietueessa, on mahdollisuus myös luoda omia näkymiä. Järjestelmänvalvojana voit muokata jokaista käyttöoikeusroolia määrittääksesi syvyyden, jolla ihmiset voivat luoda, lukea, kirjoittaa, poistaa, delegoida tai jakaa henkilökohtaisia näkymiä.

Henkilökohtaiset näkymät ovat yksilöiden omaisuutta, ja heidän oletus käyttäjä-tason käyttöoikeutensa takia ne näkyvät vain kyseiselle henkilölle tai jollekulle muulle, jonka kanssa he haluavat jakaa oman näkymänsä. Voit luoda henkilökohtaisia näkymiä tallentamalla kyselyn, joka määritetään erikoishaun avulla tai käyttämällä Tallenna suodattimet -toimintoa Uusina katsauksina ja Tallenna suodattimet nykyiseen näkymään -vaihtoehtoja näkymäluettelossa. Näitä näkymiä sisällytetään yleensä järjestelmän luetteloiden lopuksi tai julkisiin näkymiin, jotka ovat käytettävissä sovelluksessa. Vaikka voit luoda uuden oman näkymän järjestelmän tai julkisen näkymän perusteella, et voi luoda järjestelmää tai julkista näkymää henkilökohtaisen näkymän perusteella.
  
### <a name="system-views"></a>Järjestelmänäkymät
Järjestelmänvalvojana tai järjestelmän mukauttajana voit muokata järjestelmänäkymiä. Järjestelmänäkymät ovat erityisiä näkymiä, joiden mukaan sovellus määräytyy ja jotka ovat olemassa järjestelmäentiteettejä varten tai luodaan automaattisesti, kun luot mukautettuja entiteettejä. Näillä näkymillä on erityisiä tarkoituksia ja joitakin lisäominaisuuksia. 


|Järjestelmänäkymät  |Kuvaus  |
|---------|---------|
|Pikahaku     | Oletusnäkymä, kun hakuja tehdään käyttäen pikahakua. Tämä näkymä myös määrittää haettavat kentät, haun ominaisuuksia käytettäessä Pikahaku- ja Haku -näkymiä.        |
|Erikoishaku     |  Oletusnäkymän avulla näytetään hakutulokset käytettäessä Erikoishaku-toimintoa. Tämä näkymä määrittää myös oletusarvoiset sarakkeet, kun mukautettuja uusia julkisia näkymiä tai omien näkymiä luodaan määrittämättä käytettyä näkymää oletusarvoksi.       |
|Liitetty     |  Oletusnäkymä, jossa näkyvät tietueeseen liittyvät entiteetit.       |
|Valinta     | Näkymä, jonka näet, kun valitset tietueen määrittääksesi hakukentän.        |

Nämä näkymät eivät näy näyttövalitsimessa eikä niitä voi käyttää aliluetteloissa lomakkeessa tai koontinäytön luettelossa. Et voi poistaa kokonaan tai poistaa käytöstä näitä näkymiä. Lisätietoja: [Näkymien poistaminen](remove-views.md).

Järjestelmänäkymät ovat organisaation omistamia siten, että kaikki näkevät ne. Esimerkiksi kaikilla on organisaatiotason oikeus lukea Näytä (tyyppikoodin) -entiteetin tietueet. Näitä näkymiä on liitetty tiettyihin entiteetteihin, ja ne näkyvät ratkaisunhallinnassa. Näitä näkymiä voi sisällyttää ratkaisuihin, koska ne liittyvät entiteettiin.

### <a name="public-views"></a>Julkiset näkymät

Julkiset näkymät ovat yleiskäyttöisiä näkymiä, joita voit mukauttaa niin kuin tuntuu sopivalta. Nämä näkymät näkyvät näyttövalitsimessa eikä niitä voi käyttää aliluetteloissa lomakkeessa tai koontinäytön luettelossa. Osa julkisista näkymistä on olemassa oletusarvoisesti järjestelmäentiteeteille ja mille tahansa mukautetulle entiteetille. Esimerkiksi kun luot uuden mukautetun kohteen, siinä on seuraava yhdistelmä julkisille ja järjestelmänäkymille.


|Nimi  |Tyyppi  |
|---------|---------|
|Aktiivinen *entiteetin monikkonimi*     |  Julkinen       |
|Passiivinen *entiteetin monikkonimi*    |  Julkinen       |
|Pikahaun aktiivinen *entiteetin monikkonimi*     | Pikahaku        |
|*entiteetin nimen* erikoishaun näkymä     | Erikoishaku        |
|*entiteetin nimen* liitetty näkymä     |  Liitetty       |
|*entiteetin nimen* valintanäkymä     | Valinta        |

Voit luoda mukautettuja julkisia näkymiä. Voit poistaa minkä tahansa mukautetun julkisen näkymän, jonka olet luonut hallitsemattomassa ratkaisussa. Et voi poistaa minkä tahansa järjestelmän määrittämiä julkisia näkymiä. Mukautetuilla julkisilla näkymillä, jotka on lisätty tuomalla hallittu ratkaisu, voi olla hallittujen ominaisuuksien joukko, jotka estävät niiden poistamisen, lukuun ottamatta hallitun ratkaisun asennuksen poistamista.

## <a name="places-where-you-can-access-the-view-editor-to-create-or-edit-views"></a>Sijainteja, joissa voit käyttää näkymäeditoria ja luoda tai muokata näkymiä

- PowerApps-sivusto: Voit käyttää näkymän suunnitteluohjelmaa kohdassa **Mallipohjainen**-alue > **Tiedot** > **Entiteetit** > **Näkymä**-välilehti. Avaa olemassa oleva näkymä tai luo uusi näkymä. Lisätietoja: [Näkymän luominen tai muokkaaminen](create-and-edit-views.md)
- Sovellusten suunnitteluohjelma: Jos käytät sovellusta, kannattaa käyttää sovellusten suunnitteluohjelmaa. Sen avulla voi luoda näkymiä yksinkertaisessa ja intuitiivisessa käyttöliittymässä, jossa on vedä ja pudota -toimintoja. Lisätietoja: [Opetusohjelma: Julkisten näkymien tai järjestelmän näkymien luominen tai muokkaaminen sovelluksen suunnitteluohjelmalla](create-edit-views-app-designer.md)
- Ratkaisunhallinta: Jos olet jo kokenut Dynamics 365:n käyttäjä, voit käyttää ratkaisunhallintaa. Lisätietoja: [Sovelluksen luonnin ja mukautuksen alueiden lisäasetuksiin siirtyminen](advanced-navigation.md#solution-explorer)
 
## <a name="customize-views"></a>Näkymien mukauttaminen

Järjestelmän mukauttajana voit mukauttaa näkymät ohjausobjektien kautta tekemällä ruudukoista (luettelon) muokattavia ja yhteensopivia Unified Interfacen kanssa. Seuraavia ohjausobjekteja käytetään:

- Muokattava ruudukko: Mahdollistaa muokattavien ruudukoiden avulla käyttävien voivan muokata rivejä monella tavoin suoraan ruudukoissa ja aliruudukoissa riippumatta siitä, käyttävätkö he verkkosovellusta, tablettia vai puhelinta. Lisätietoja: [Ruudukoiden muuttaminen muokattaviksi muokattavan ruudukon mukautetun ohjausobjektin avulla](make-grids-lists-editable-custom-control.md)
- Vain luettava ruudukko: Lisäksi uusi Sales-sovellus käyttää responsiivisia verkkosuunnitteluperiaatteita voidakseen antaa optimaalisen katselu- ja vuorovaikutuskokemuksen näytön koosta tai suunnasta riippumatta esim. mobiililaitteilla ja tableteilla responsiivisia suunnitteluperiaatteita noudattaen. Lisätietoja: [Unified Interface -sovellusten ominaisuuksien määrittäminen](specify-properties-for-unified-interface-apps.md)

## <a name="next-steps"></a>Seuraavat vaiheet

[Näkymien luominen tai muokkaaminen](create-and-edit-views.md)
