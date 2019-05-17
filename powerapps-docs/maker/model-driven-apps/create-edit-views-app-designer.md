---
title: Julkisten näkymien tai järjestelmän mallipohjaisten sovellusten näkymien luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Tietoja näkymien luomisesta tai muokkaamisesta sovelluksen suunnitteluohjelmalla
keywords: ''
ms.date: 11/27/2018
ms.service: powerapps
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

# <a name="create-and-edit-public-or-system-model-driven-app-views"></a>Julkisten näkymien tai järjestelmän mallipohjaisten sovellusten näkymien luominen tai muokkaaminen

Tässä ohjeaiheessa suoritetaan useita tehtäviä, jotka ovat pakollisia näkymiä käsiteltäessä. Näitä ovat esimerkiksi julkisen näkymän luominen, olemassa olevan näkymän lisääminen sovellukseen ja näkymän sarakkeiden, suodattimien ja lajittelujärjestyksen muuttaminen.

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

4. Anna **Luo näkymä** -valintaikkunaan nimi ja halutessasi kuvaus. Valitse sitten **Luo**. 
    
5. Valitse näkymän suunnitteluohjelmassa pluspainike ja lisää näkymässä näytettävät lisäsarakkeet. Lisätietoja: [Sarakkeen lisääminen sovellusten suunnitteluohjelman näkymään](#add-a-column-to-your-view-in-app-designer) 

   ![Sarakkeen lisääminen](../common-data-service/media/add-column-to-view.png)

6. Näkymän suunnitteluohjelmassa voit suorittaa seuraavat tehtävät: 
   - Jos haluat muuttaa sarakkeen suodatusta, valitse suodatettavan sarakkeen otsikko ja valitse sitten avattavasta luettelosta **Suodatusperuste**.
   - Jos haluat muuttaa sarakkeen lajittelua, valitse suodatettavan sarakkeen otsikko ja valitse sitten **Lajittele A–Ö** tai **Lajittele Ö–A**.
   - Määritä sarakkeen leveys valitsemalla sarake ja vetämällä se haluttuun kohtaan.
   - Muuta sarakkeiden järjestystä vetämällä sarake paikkaan, johon haluat siirtää sen. 

    > [!NOTE]
    > Voit myös muuttaa sarakejärjestystä napsauttamalla sarakkeen otsikkoa ja valitsemalla **Siirrä oikealle** tai **Siirrä vasemmalle**.

10. Valitse **Julkaise**, jos haluat tallentaa näkymän niin, että se on organisaation muiden käyttäjien käytettävissä. 
   

## <a name="work-with-views-in-app-designer"></a>Sovellusten suunnitteluohjelman näkymien käsitteleminen
Seuraavissa osissa kerrotaan, miten näkymiä luodaan ja muokataan sovellusten suunnitteluohjelmassa.

### <a name="open-and-add-a-view-in-the-app-designer"></a>Näkymän avaaminen ja lisääminen sovellusten suunnitteluohjelmassa

Seuraavissa ohjeissa selitetään, miten näkymä avataan ja lisätään sovellusten suunnitteluohjelmassa.
1. Valitse PowerAppsin vasemmanpuoleisessa siirtymisruudussa **Sovellukset**. Valitse haluamasi sovelluksen vieressä oleva **...**-kohta ja valitse sitten **Muokkaa**. 

2. Valitse sovellusten suunnitteluohjelman **Entiteettinäkymä**-osassa **Näkymät**.

    Tässä esimerkissä **Asiakas**-entiteetissä on valittu **Näkymät**.

    ![Sovellusten suunnitteluohjelmanäkymä](media/ViewAppDesigner_AccountAppDesignerView.png "Asiakas-entiteetin sovellusten suunnitteluohjelmanäkymä")

3. Voit lisätä näkymän valitsemalla sen käyttämällä näkymätyyppejä, kuten julkinen, erikoishaku, liitetty ja valinta. Näkymä lisätään automaattisesti **Näkymät**-luetteloon.

    > [!NOTE]
    > Näkymät näkyvät valitun entiteetin perusteella. Jos valitsit esimerkiksi **Asiakas**, Asiakas-entiteettiin liittyvät näkymät näytetään.

Lisätietoja sovellusten suunnitteluohjelmasta: [Mukautettujen liiketoimintasovellusten suunnittelu sovellusten suunnitteluohjelmalla](design-custom-business-apps-using-app-designer.md)


### <a name="add-a-column-to-your-view-in-app-designer"></a>Sarakkeen lisääminen näkymään sovellusten suunnitteluohjelmassa
Näkymät näyttävät rivejä ja sarakkeita sisältävän taulukon tietueet. Kukin rivi on tietue, ja tietueesta näytettävät kentät määräytyvät näkymään lisättyjen sarakkeiden perusteella.

1. Valitse sovellusten suunnitteluohjelmassa haluamasi entiteettinäkymä ja valitse sitten näkymän oikeanpuoleisessa ruudussa Muokkaa (kynäpainike).  
2. Valitse **Osat**-välilehdessä joko **Ensisijainen entiteetti**- tai **Liittyvä entiteetti** -kohdassa **Sarakkeen määritteet**.

    ![Sarakkeen lisääminen](media/ViewAppDesigner_AddColumn.png "Sarakkeen lisääminen näkymään") 

3. Valitse luettelossa määrite ja vedä se tämän sarakkeen otsikkoon. Voit lisätä määritteen myös kaksoisnapsauttamalla sitä.
4. Toista vaihe 3, kunnes olet lisännyt kaikki näytettävät määritteet näkymään.

Kun lisäät määritteitä, voit vetää ne mihin tahansa aiemmin luotuun sarakeotsikkoon. Voit siirtää sarakkeita myös sen jälkeen, kun olet lisännyt ne näkymään.


### <a name="define-filter-criteria-in-app-designer"></a>Suodatusehtojen määrittäminen sovellusten suunnitteluohjelmassa
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

#### <a name="group-multiple-filters-in-app-designer"></a>Useiden suodattimien ryhmitteleminen sovellusten suunnitteluohjelmassa
Voit lisätä näkymään useita suodattimia näkymään, jos haluat käyttää suodatusperusteena useita kenttiä. 

1. Valitse ryhmiteltävät suodattimet.
    ![Ryhmän suodatuksen määrittäminen](media/ViewAppDesigner_GroupFilter.png "Ryhmän suodatuksen määrittäminen")
2. Ryhmitä suodattimet valitsemalla Ryhmittele JA tai Ryhmittele TAI.
    ![Ryhmäsuodattimen valinta](media/ViewAppDesigner_GroupFilterSelection.png "Valitse ryhmä suodatin") Kun valitset **Ryhmittele JA**, vain kumpaakin ehtoa vastaavat tietuet näkyvät näkymässä. Kun valitset **Ryhmittele TAI**, jotakin suodatusehtoa vastaavat tietueet näytetään. Jos haluat esimerkiksi näyttää vain tietueet, joiden prioriteetti on suuri tai normaali ja tila aktiivinen, valitse **Ryhmittele JA**.

Voit poistaa ryhmän suodattimen valitsemalla ensin ryhmän ja siten **Pura ryhmittely**. 

### <a name="set-primary-and-secondary-sort-order-for-columns-in-app-designer"></a>Sarakkeiden ensisijaisen ja toissijaisen lajittelujärjestyksen määrittäminen sovellusten suunnitteluohjelmassa
Kun näkymä avataan, näkymän tietueet lajitellaan näkymän luonnin yhteydessä luodun järjestyksen mukaan.   Tietueet lajitellaan oletusarvoisesti näkymän ensimmäisen sarakkeen mukaan, jos mitään lajittelujärjestystä ei ole valittu. Voit valita lajittelun yhden sarakkeen mukaan. Voit valita lajitteluperusteeksi myös kaksi saraketta, joista toinen on ensisijainen ja toissijainen. Kun näkymä avataan, tietueet lajitellaan ensimmäiseksi ensisijaisena lajittelujärjestyksenä käytettävän sarakkeen mukaan ja sitten sen sarakkeen mukaan, jota käytetään toissijaisena lajittelujärjestyksenä. 

> [!NOTE]
> Voit määrittää ensi- ja toissijaisen lajittelujärjestyksen vain niille sarakkeen määritteille, jotka lisäsit ensisijaisesta entiteetistä.

1. Valitse lajitteluun käytettävä sarake.
2. Valitse ensin alanuoli ja sitten **Ensisijainen lajittelu** tai **Toissijainen lajittelu**.
 
    ![Tietueen lajittelu](media/ViewAppDesigner_SortRecords.png "Tietueiden lajittelu ensi- ja toissijaisen lajittelujärjestyksen perusteella") 

Jos poistat ensisijaiseksi lajittelujärjestykseksi valitun sarakkeen, toissijaiseksi lajittelujärjestykseksi valitusta sarakkeesta tulee ensisijainen lajitteluperuste.

### <a name="define-a-web-resource-in-app-designer"></a>WWW-resurssin määrittäminen sovellusten suunnitteluohjelmassa
Määritä näkymässä sarakkeeseen liitettävän komentosarjatyypin verkkoresurssi. Nämä komentosarjat auttavat näyttämään sarakkeiden kuvakkeet.

1. Valitse sarake, johon verkkoresurssi lisätään.
2. Valitse **Ominaisuudet**-välilehdessä **Lisäasetukset**.
3. Valitse avattavasta **Verkkoresurssi**-luettelosta käytettävä verkkoresurssi.
4. Kirjoita toiminnon nimi **Toiminnon nimi** -ruutuun.

### <a name="edit-a-public-or-system-view-in-app-designer"></a>Julkisen näkymän tai järjestelmänäkymän muokkaaminen sovellusten suunnitteluohjelmassa
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
