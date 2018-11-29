---
title: Julkisten näkymien tai järjestelmän mallipohjaisten sovellusten näkymien luominen tai muokkaaminen sovelluksen suunnitteluohjelmalla PowerAppsissa | MicrosoftDocs
description: Tietoja näkymien luomisesta tai muokkaamisesta sovelluksen suunnitteluohjelmalla
keywords: ''
ms.date: 05/24/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 666ab3f3-abda-468c-b248-3a0b410286b0
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 1
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-create-and-edit-public-or-system-model-driven-app-views-by-using-the-app-designer"></a>Opetusohjelma: Julkisten näkymien tai järjestelmän mallipohjaisten sovellusten näkymien luominen tai muokkaaminen sovelluksen suunnitteluohjelmalla

Tässä opetusohjelmassa suoritetaan useita tehtäviä, jotka ovat pakollisia näkymiä käsiteltäessä. Näitä ovat esimerkiksi julkisen näkymän luominen, olemassa olevan näkymän lisääminen sovellukseen ja näkymän sarakkeiden, suodattimien ja lajittelujärjestyksen muuttaminen.

Näkymät määrittävät PowerAppsissa, miten tietyn entiteetin tietueet näytetään. Näkymä määrittää
-  näytettävät sarakkeet (määritteet)
-  sarakkeiden leveyden
-  tietueiden oletusarvoisen lajittelun
-  suodattimet, joilla määritetään oletusarvoisesti luettelossa näkyvät tietueet.

Näkymät luokitellaan yleensä kolmeksi tyypiksi:
- **Henkilökohtaisen:** Yksittäiset käyttäjät voivat luoda henkilökohtaisia, omia tarpeitaan vastaavia näkymiä. Nämä näkymät ovat vain näkymän luoneen käyttäjän sekä henkilöiden, joiden kanssa hän jakaa näkymät, nähtävissä. 
- **Julkinen:** Sovelluksen tekijänä voit luoda ja muokata organisaation vaatimuksia vastaavia julkisia näkymiä. Nämä näkymät näkyvät näyttövalitsimessa, eikä niitä voi käyttää lomakkeen aliruudukoissa lomakkeessa eikä koontinäytön luettelona.
- **Järjestelmä:** Sovelluksen tekijänä voit myös muokata järjestelmänäkymät vastaamaan organisaation vaatimuksia. Ne ovat erikoisnäkymiä, joiden mukaan sovellus määräytyy: ne ovat olemassa järjestelmäentiteettejä varten tai ne luodaan automaattisesti, kun luot mukautettuja entiteettejä. Nämä näkymät ovat käyttöoikeuksien mukaan joidenkin tai kaikkien käyttäjien käytettävissä.

Lisätietoja: [Tietoja näkymistä](create-edit-views.md).

## <a name="create-a-public-view-in-powerapps"></a>Julkisen näkymän luominen PowerAppsissa
Sovelluksen tekijänä voit luoda tai muokata julkisia näkymiä PowerAppsin avulla.
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  


    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Näkymät**-välilehti. 

3. Valitse työkaluriviltä **Lisää näkymä**. 

4. Anna **Näkymän ominaisuudet** -valintaikkunaan nimi ja halutessasi kuvaus. Valitse sitten **OK**. 
    
5. Valitse näkymän suunnitteluohjelmassa **Lisää sarakkeet** ja lisää näkymässä näytettävät lisäsarakkeet. Lisätietoja: [Sarakkeen lisääminen näkymään](#add-a-column-to-your-view)
6. Valitse **Muokkaa suodatusehtoja** ja muuta suodatusta seuraavalla tavalla: 
    -  Voit ottaa käyttöön suodatusehdot ja tarkentaa näkymässä näytettäviä tietoja. Lisätietoja: [Suodatinehtojen määrittäminen](#define-filter-criteria). 
    - Tarkenna näkymässä näkyviä tietoja ryhmittelemällä suodattimia **JA**- tai **TAI**-vaihtoehdoilla. Lisätietoja: [Useiden suodattimien ryhmitteleminen](#group-multiple-filters)
7. Valitse **Määritä lajittelu**, kun haluat muuttaa tietojen järjestystä määrittämällä sarakkeiden ensi- ja toissijaisen lajittelujärjestyksen. Lisätietoja: [Sarakkeiden ensi- ja toissijaisen lajittelujärjestyksen määrittäminen](#set-primary-and-secondary-sort-order-for-columns)
8. (Valinnainen) Sarakkeen leveyden määrittäminen: 
  
    a. Valitse sarake. **Ominaisuudet**-välilehti avautuu.
    
    b. Määritä haluamasi sarakkeen leveys **Valitse leveys** -asetuksella.
    
    > [!NOTE]
    > Sarakkeen leveyden arvo voi olla 25–300 pikseliä.
9. (Valinnainen) Muuta sarakkeiden järjestystä vetämällä sarake paikkaan, johon haluat siirtää sen. 

    Visuaalinen ilmaisin tulee näkyviin, kun pidät saraketta paikassa, johon haluat siirtää sen.

    ![Sarakkeiden järjestäminen uudelleen](media/ViewAppDesigner_ReorderColumn.png "Näkymän sarakkeiden järjestäminen uudelleen")

    > [!NOTE]
    > Voit muuttaa sarakkeiden järjestystä myös pikanäppäimillä. Leikkaa sarake Ctrl + X -näppäinyhdistelmällä, valitse sarake ja liitä se Ctrl + V -näppäinyhdistelmällä. Sarake siirretään valitun sarakkeen oikealle puolelle.
10. (Valinnainen) Liitä sarakkeeseen kuvake tai tiedosto erottamaan se muista sarakkeista suorituksen aikana. Lisätietoja: [WWW-resurssin määrittäminen](#define-a-web-resource)
11. **Tallenna ja sulje** näkymä. 
12. Valitse **Julkaise**, jos haluat, että näkymä on organisaation muiden käyttäjien käytettävissä. 
   

## <a name="open-and-add-a-view-in-the-app-designer"></a>Näkymän avaaminen ja lisääminen sovellusten suunnitteluohjelmassa

Seuraavissa ohjeissa selitetään, miten näkymä avataan ja lisätään sovellusten suunnitteluohjelmassa.
1. Valitse ratkaisunhallinnassa **Sovellukset** ja valitse sitten muokattava sovellus avattavaksi sovelluksen suunnitteluohjelmassa. 

2. Valitse **Entiteettinäkymä**-osassa **Näkymät**.

    Tässä esimerkissä **Asiakas**-entiteetissä on valittu **Näkymät**.

    ![Sovellusten suunnitteluohjelmanäkymä](media/ViewAppDesigner_AccountAppDesignerView.png "Asiakas-entiteetin sovellusten suunnitteluohjelmanäkymä")

3. Voit lisätä näkymän valitsemalla sen käyttämällä näkymätyyppejä, kuten julkinen, erikoishaku, liitetty ja valinta. Näkymä lisätään automaattisesti **Näkymät**-luetteloon.

    > [!NOTE]
    > Näkymät näkyvät valitun entiteetin perusteella. Jos valitsit esimerkiksi **Asiakas**, Asiakas-entiteettiin liittyvät näkymät näytetään.

Lisätietoja sovellusten suunnitteluohjelmasta: [Mukautettujen liiketoimintasovellusten suunnittelu sovellusten suunnitteluohjelmalla](design-custom-business-apps-using-app-designer.md)


## <a name="add-a-column-to-your-view"></a>Sarakkeen lisääminen näkymään
Näkymät näyttävät rivejä ja sarakkeita sisältävän taulukon tietueet. Kukin rivi on tietue, ja tietueesta näytettävät kentät määräytyvät näkymään lisättyjen sarakkeiden perusteella.

1. Valitse sovelluksen suunnitteluohjelmassa **Osat**-välilehdessä joko **Ensisijainen entiteetti**- tai **Liittyvä entiteetti** -kohdassa **Sarakkeen määritteet**.

    ![Sarakkeen lisääminen](media/ViewAppDesigner_AddColumn.png "Sarakkeen lisääminen näkymään") 

2. Valitse luettelossa määrite ja vedä se tämän sarakkeen otsikkoon. Voit lisätä määritteen myös kaksoisnapsauttamalla sitä.
3. Toista vaihe 2, kunnes olet lisännyt kaikki näytettävät määritteet näkymään.

Kun lisäät määritteitä, voit vetää ne mihin tahansa aiemmin luotuun sarakeotsikkoon. Voit siirtää sarakkeita myös sen jälkeen, kun olet lisännyt ne näkymään.


## <a name="define-filter-criteria"></a>Suodatusehtojen määrittäminen
Voit määrittää suodatinehdot niin, että vain tietueiden alijoukko näkyy näkymässä. Kun käyttäjä avaa näkymän, vain määritettyjä tietue-ehtoja vastaavat tietueet näkyvät. Voit valita suodatettavaksi sekä ensisijaisten ja liittyvien entiteettien kenttiä.
1. Laajenna sovelluksen suunnitteluohjelman **Suodatusehdot**-osa.
   
    ![Suodatusehtojen määrittäminen](media/ViewAppDesigner_FilterCriteria.png "Suodatusehtojen määrittäminen") 

2. Valitse **Lisää suodatin**.
3. Valitse määrite ensimmäisen sarakkeen avattavasta luettelosta. 
4. Valitse operaattori toisen sarakkeen avattavasta luettelosta.

    ![Suodatusehtojen operaattorin määrittäminen](media/ViewAppDesigner_FilterCriteriaOption.png "Suodatusehtojen operaattorin määrittäminen")

5. Anna suodatettava arvo kolmannessa sarakkeessa.

Voit suodattaa tietoja ensisijaisen entiteetin lisäksi myös liittyvien entiteettien määritteitä. 

1. Valitse **Osat**-välilehden **Liittyvä entiteetti** -kohdassa **Sarakkeen määritteet** -luettelo. Valitse sitten ylimmässä kentässä **Valitse entiteetti** -alanuoli ja valitse entiteetti sen jälkeen.

    Erillinen osa lisätään nyt.

2. Toista edellisen ohjeen vaiheet 2–5.

Lisätietoja: [Suhteiden luominen ja niiden muokkaaminen entiteettien välillä](../common-data-service/create-edit-entity-relationships.md)

## <a name="group-multiple-filters"></a>Useiden suodattimien ryhmittely
Voit lisätä näkymään useita suodattimia näkymään, jos haluat käyttää suodatusperusteena useita kenttiä. 

1. Valitse ryhmiteltävät suodattimet.
    ![Ryhmän suodatuksen määrittäminen](media/ViewAppDesigner_GroupFilter.png "Ryhmän suodatuksen määrittäminen")
2. Ryhmitä suodattimet valitsemalla Ryhmittele JA tai Ryhmittele TAI.
    ![Ryhmäsuodattimen valinta](media/ViewAppDesigner_GroupFilterSelection.png "Valitse ryhmä suodatin") Kun valitset **Ryhmittele JA**, vain kumpaakin ehtoa vastaavat tietuet näkyvät näkymässä. Kun valitset **Ryhmittele TAI**, jotakin suodatusehtoa vastaavat tietueet näytetään. Jos haluat esimerkiksi näyttää vain tietueet, joiden prioriteetti on suuri tai normaali ja tila aktiivinen, valitse **Ryhmittele JA**.

Voit poistaa ryhmän suodattimen valitsemalla ensin ryhmän ja siten **Pura ryhmittely**. 

## <a name="set-primary-and-secondary-sort-order-for-columns"></a>Sarakkeiden ensi- ja toissijaisen lajittelujärjestyksen määrittäminen
Kun näkymä avataan, näkymän tietueet lajitellaan näkymän luonnin yhteydessä luodun järjestyksen mukaan.   Tietueet lajitellaan oletusarvoisesti näkymän ensimmäisen sarakkeen mukaan, jos mitään lajittelujärjestystä ei ole valittu. Voit valita lajittelun yhden sarakkeen mukaan. Voit valita lajitteluperusteeksi myös kaksi saraketta, joista toinen on ensisijainen ja toissijainen. Kun näkymä avataan, tietueet lajitellaan ensimmäiseksi ensisijaisena lajittelujärjestyksenä käytettävän sarakkeen mukaan ja sitten sen sarakkeen mukaan, jota käytetään toissijaisena lajittelujärjestyksenä. 

> [!NOTE]
> Voit määrittää ensi- ja toissijaisen lajittelujärjestyksen vain niille sarakkeen määritteille, jotka lisäsit ensisijaisesta entiteetistä.

1. Valitse lajitteluun käytettävä sarake.
2. Valitse ensin alanuoli ja sitten **Ensisijainen lajittelu** tai **Toissijainen lajittelu**.
 
    ![Tietueen lajittelu](media/ViewAppDesigner_SortRecords.png "Tietueiden lajittelu ensi- ja toissijaisen lajittelujärjestyksen perusteella") 

Jos poistat ensisijaiseksi lajittelujärjestykseksi valitun sarakkeen, toissijaiseksi lajittelujärjestykseksi valitusta sarakkeesta tulee ensisijainen lajitteluperuste.

## <a name="define-a-web-resource"></a>Verkkoresurssin määrittäminen
Määritä näkymässä sarakkeeseen liitettävän komentosarjatyypin verkkoresurssi. Nämä komentosarjat auttavat näyttämään sarakkeiden kuvakkeet.

1. Valitse sarake, johon verkkoresurssi lisätään.
2. Valitse **Ominaisuudet**-välilehdessä **Lisäasetukset**.
3. Valitse avattavasta **Verkkoresurssi**-luettelosta käytettävä verkkoresurssi.
4. Kirjoita toiminnon nimi **Toiminnon nimi** -ruutuun.

## <a name="edit-a-public-or-system-view"></a>Julkisen näkymän tai järjestelmänäkymän muokkaaminen
Voit muuttaa tapaa, jolla julkinen näkymä tai järjestelmänäkymä näytetään, lisäämällä, määrittämällä tai poistamalla sarakkeita.
1. Valitse entiteetin **Näkymät**-luettelossa **Näytä viittausluettelo** -alanuoli ![Avattava luettelo](media/DownArrow.png "Avattava luettelo -nuoli").
    ![Näkymän muokkaaminen](media/ViewAppDesigner_EditView.png "Julkisen näkymän tai järjestelmänäkymän muokkaaminen")
2. Valitse muokattavan näkymän vieressä **Avaa näkymän suunnitteluohjelma** ![Avaa näkymän suunnitteluohjelma](media/dynamics365-open-designer.png "Avaa näkymän suunnitteluohjelma"). 

    Näkymä avautuu näkymän suunnitteluohjelmassa. 

Julkista näkymää tai järjestelmänäkymää muutokset on tallennettava ja julkaistava, ennen kuin ne näkyvät sovelluksessa.


## <a name="community-tools"></a>Yhteisön työvälineet
**Näkymän asettelun replikoija** ja **Näkymän suunnitteluohjelma** ovat XrmToolbox-yhteisön Dynamics 365 Customer Engagement -sovellukselle kehittämät työkalut.

Lisätietoja: [Sovelluskehittäjän työkalut](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools).

> [!NOTE]
> Nämä työkalut tarjoaa XrmToolBox ja Microsoft ei tue niitä. Jos sinulla on kysymyksiä työkalusta, ota yhteyttä julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com/). 

### <a name="next-steps"></a>Seuraavat vaiheet
[1:N (yksi moneen)- tai N:1 (monta yhteen) -suhteen luominen](../common-data-service/create-edit-1n-relationships.md)
