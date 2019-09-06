---
title: Lomakkeiden suunnitteluohjelmassa käytettävissä olevat ominaisuudet| MicrosoftDocs
ms.custom: ''
ms.date: 02/19/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="properties-available-in-the-form-designer"></a>Lomakkeiden suunnitteluohjelmassa käytettävissä olevat ominaisuudet

Mallipohjaisen lomakkeiden suunnitteluohjelman oikeassa ruudussa on ominaisuusruutu, jossa voit tarkastella ja päivittää nopeasti esikatselu- tai siirtymisruudussa valitun elementin ominaisuuksia. 

> [!div class="mx-imgBorder"] 
> ![](media/form-designer-property-pane.png "Lomakkeiden suunnitteluohjelman ominaisuusruutu")

## <a name="form-properties"></a>Lomakkeen ominaisuudet


|Nimi  |Kuvaus  |
|---------|---------|
|**Otsikko**     | Kirjoita nimi, jolla on merkitystä käyttäjille. Käyttäjät näkevät tämän nimen lomaketta käytettäessä. Jos he käyttävät useita entiteettiin määritettyjä lomakkeita, lomakkeet erotetaan toisistaan tämän nimen avulla. <br /> Tämä ominaisuus on pakollinen.        |
|**Kuvaus**     |  Kirjoita kuvaus, joka selittää, miten tämä lomake eroaa muista päälomakkeista. Kuvaus näkyy vain ratkaisunhallinnassa entiteetin lomakeluettelossa.        |
|**Enimmäisleveys**     | Määritä enimmäisleveys (kuvapisteinä) rajoittamaan lomakkeen leveyttä. Oletusarvo on 1 900. <br /> Tämä ominaisuus on pakollinen.       |
|**Näytä kuva**      | Näytä entiteetin **Ensisijainen kuva**, jos se on määritetty. Tällä asetuksella voidaan näyttää tämän lomakkeen otsikon kuvakentässä. <br /> Katso Entiteetin asetusten ottaminen käyttöön tai poistaminen käytöstä, jos haluat lisätietoja entiteetin asetuksista.         |


## <a name="tab-properties"></a>Välilehden ominaisuudet

|aluekaavioita   |Nimi  |Kuvaus  |
|---------|---------|---------|
|**Näyttöasetukset**      | **Välilehden otsikko**      | Välilehden lokalisoitava otsikko, jonka käyttäjä näkee. <br /> Tämä ominaisuus on pakollinen.         |
| **Näyttöasetukset**      |  **Nimi**     |  Välilehden yksilöivä nimi, jolla siihen viitataan komentosarjoissa. Nimessä voi olla vain aakkosnumeerisia merkkejä ja alaviivoja. <br />Tämä ominaisuus on pakollinen.      |
| **Näyttöasetukset**      |  **Laajenna tämä välilehti oletusarvoisesti**      |  Välilehden tilaa voi vaihdella laajennetun tai tiivistetyn välillä lomakkeen komentosarjoilla. Käyttäjät voivat vaihtaa sitä myös otsikon valitsemalla. Valitse välilehden oletustila.       |
| **Näyttöasetukset**      | **Piilota välilehti**     | Kun valittu, välilehti piilotetaan oletusarvoisesti ja voidaan näyttää koodin avulla.       |
| **Näyttöasetukset**      | **Piilota puhelimessa**     |  Välilehdet voidaan piilottaa tämän lomakkeen puhelimen näyttöön tarkoitetussa tiivistetyssä versiossa.     |
| **Muotoilu**   | **Asettelu**     |  Välilehdissä voi olla enintään kolme saraketta. Näillä asetuksilla voit määrittää välilehtien lukumäärän ja niiden leveyden osuutena kokonaisleveydestä.      |

## <a name="section-properties"></a>Osan ominaisuudet


|aluekaavioita   |Nimi  |Kuvaus  |
|---------|---------|---------|
|**Näyttöasetukset**      | **Osan nimi**    | Osan lokalisoitava otsikko, jonka käyttäjä näkee. <br /> Tämä ominaisuus on pakollinen.      |
|**Näyttöasetukset**      | **Nimi**    | Osan yksilöivä nimi, jolla siihen viitataan komentosarjoissa. Nimessä voi olla vain aakkosnumeerisia merkkejä ja alaviivoja. <br /> Tämä ominaisuus on pakollinen.        |
|**Näyttöasetukset**      | **Piilota otsikko**   |  Kun valittu, osan otsikko on piilotettu.  |
|**Näyttöasetukset**      | **Lukitusosa**    | Lukitse tämä osa, jolloin sitä ei voi poistaa.      |
|**Näyttöasetukset**      | **Piilota osa**     | Kun valittu, osa piilotetaan oletusarvoisesti ja voidaan näyttää koodin avulla.      |
|**Näyttöasetukset**      | **Piilota puhelimessa**     |  Osat voidaan piilottaa tämän lomakkeen puhelimen näyttöön tarkoitetussa tiivistetyssä versiossa.     |
|**Muotoilu**     |  **Sarakkeet**    |  Voit määrittää osaan enintään neljä saraketta.      |

## <a name="field-properties"></a>Kentän ominaisuudet


|aluekaavioita  |Nimi  |Kuvaus  |
|---------|---------|---------|
|**Näyttöasetukset**     | **Kentän teksti**    | Otsikko vastaa oletusarvoisesti kentän nimeä. Voit ohittaa tämän lomakkeen nimen kirjoittamalla uuden otsikon tähän.       |
|**Näyttöasetukset**     |  **Kentän nimi**    | Kentän nimi. Se saadaan entiteetin kentän ominaisuuksista ja on vain luku -muotoinen.     |
|**Näyttöasetukset**     | **Piilota otsikko**     | Kun valittu, kentän otsikko on piilotettu.      |
|**Näyttöasetukset**     | **Vain luku -kenttä**    | Kun valittu, kentän arvoa ei voi muokata.      |
|**Näyttöasetukset**     |  **Lukituskenttä**   |  Lukitse tämä kenttä, jolloin sitä ei voi poistaa.     |
|**Näyttöasetukset**     |  **Piilota kenttä**     | Kun valittu, kenttä piilotetaan oletusarvoisesti ja voidaan näyttää koodin avulla.      |
|**Näyttöasetukset**     |  **Piilota puhelimessa**    | Kentät voidaan piilottaa tämän lomakkeen puhelimen näyttöön tarkoitetussa tiivistetyssä versiossa.         |
|**Näyttöasetukset**     | **Kentän leveys**      |  Kun kenttiä sisältävässä osassa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osassa on.       |


## <a name="see-also"></a>Katso myös
[Mallipohjaisen sovelluksen lomakkeen suunnitteluohjelman yleiskatsaus](form-designer-overview.md)  
[Lomakkeiden luominen tai muokkaaminen lomakkeiden suunnitteluohjelman avulla](create-and-edit-forms.md)  
[Lomakkeiden kenttien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-fields-on-form.md)  
[Lomakkeiden osien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-sections-on-form.md)  
[Lomakkeiden välilehtien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-tabs-on-form.md)  
[Ylätunnisteen ominaisuuksien määrittäminen lomakkeiden suunnitteluohjelmassa](form-designer-header-properties.md)  
[Lomakkeen suunnitteluohjelman puunäkymän käyttäminen](using-tree-view-on-form.md)  
[Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-field-portal.md)
