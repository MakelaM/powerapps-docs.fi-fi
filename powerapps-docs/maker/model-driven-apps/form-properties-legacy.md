---
title: Mallipohjaisen sovelluksen lomakkeen ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeiden ominaisuuksista
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="model-driven-app-form-properties"></a>Mallipohjaisen sovelluksen lomakkeen ominaisuudet 

Voit käyttää **lomakkeen ominaisuuksia** ratkaisunhallinnassa. Laajenna ensin **Osat**-kohdassa **Entiteetit**, sitten haluamasi entiteetti ja napsauta **Lomakkeet**. Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**. Valitse sitten **Koti**-välilehdessä **Lomakkeen ominaisuudet**.

![form-properties](media/form-properties.png)

Taulukossa on esitetty lomakeominaisuudet:  
  
|Sarkain|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Tapahtumat**|**Lomakekirjastot**|Hallitse lomakkeessa käytettävissä olevia JavaScript-WWW-resursseja ja niiden latausjärjestystä.|  
||**Tapahtumakäsittelijät**|Määritä, mitkä lomakekirjaston JavaScript-toiminnot suoritetaan `OnLoad`- ja `OnSave`-lomaketapahtumissa ja missä järjestyksessä ne suoritetaan.|  
|**Näyttö**|**Lomakkeen nimi**|Kirjoita nimi, jolla on merkitystä käyttäjille. Käyttäjät näkevät tämän nimen lomaketta käytettäessä. Jos he käyttävät useita entiteettiin määritettyjä lomakkeita, lomakkeet erotetaan toisistaan tämän nimen avulla.|  
||**Kuvaus**|Kirjoita kuvaus, joka selittää, miten tämä lomake eroaa muista päälomakkeista. Kuvaus näkyy vain ratkaisunhallinnassa entiteetin lomakeluettelossa.|  
||**Lomakeavustaja**|Valitse valintaruutu, jos haluat ottaa lomakeavustajan käyttöön tai tarkastella lomaketta oletusarvoisesti laajennettuna.|
||**Sivussa siirtyminen**|Voit halutessasi olla näyttämättä siirtymiskohteita.<br /><br /> Päivitettyjen entiteettien lomakkeissa tämä tarkoittaa sitä, että näytettävän tietueen arvon ensisijainen nimi ei näy siirtymispalkissa, joten sen avulla ei voi siirtyä liittyviin näkymiin.<br /><br /> Perinteistä esitystä käyttävissä lomakkeissa lomakkeen vasemmalla puolella olevat siirtymisasetukset, joilla voi valita liittyvät näkymät, eivät näy.|  
||**Kuva**|Kun entiteetissä on kuvakenttä ja entiteetin **Ensisijainen kuva** -asetus on valittu, asetus mahdollistaa kuvakentän näyttämisen lomakkeen ylätunnisteessa.<br /><br /> Katso [Entiteetin asetusten ottaminen käyttöön tai poistaminen käytöstä](../common-data-service/edit-entities.md#enable-or-disable-entity-options), jos haluat lisätietoja entiteetin asetuksista.|  ||**Näytä**|**Määritä enimmäisleveys (kuvapisteinä)** rajoittaa lomakkeen leveyttä. Oletusarvo on 1 900.|  
||**Näytä**|Anna tässä lomakkeen suurin leveys kuvapisteinä.|
|**Parametrit**|**Parametrit**|Kukin lomake voidaan avata koodilla (URL-osoitteella). URL-osoite voi sisältää myös tietoja, jotka voidaan välittää lomakkeeseen käyttämällä URL-osoitteeseen liitettyä kyselymerkkijonoa. Kyselymerkkijono voi olla esimerkiksi tällainen:<br />`?p_firstName=Jim&p_lastName=Daly`<br /><br /> Tietoturvasyistä lomakkeet eivät hyväksy tuntemattomia kyselymerkkijonoparametreja. Tällä parametriluettelolla voit määrittää parametrit, jotka lomake hyväksyy tukemaan koodia, jolla tiedot välitetään lomakkeisiin kyselymerkkijonolla.<br /><br /> Tietojen nimi ja tyyppi tarkistetaan eikä lomake avaudu, jos siihen välitetään virheellisiä kyselymerkkijonon parametreja.<br /><br />**Huomautus:** Nimi ei voi alkaa alaviivalla (_) tai merkkijonolla crm\_. Nimen alussa on oltava aakkosnumeerisia merkkejä ja alaviiva (\_). Esimerkiksi: parametri_1 tai 1_parametri. Nimessä ei voi olla yhdysmerkkejä (-), kaksoispistettä (:), puolipistettä (;), pilkkuja (,) tai pisteitä (.). <br /><br />|  
|**Muut kuin tapahtumariippuvuudet**|**Alisteiset kentät**|Kaikissa tapahtumakäsittelijöissä on samankaltainen **Alisteiset kentät** -ominaisuus, jotta kaikki komentosarjan tarvitsemat kentät voidaan rekisteröidä. Alisteisia kenttiä ei voi poistaa kuka tahansa.<br /><br /> Jotkin komentosarjat toimivat lomakkeessa, mutta niitä ei ole määritetty tapahtumakäsittelijässä. Komentopalkista käynnistetyillä komentosarjoilla ei ole paikkaa, johon alisteiset kentät voidaan rekisteröidä. Tämä lomakkeen ominaisuus mahdollistaa kyseisten komentosarjojen alisteisten kenttien rekisteröinnin.|  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)
