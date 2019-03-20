---
title: Projektipyyntöjä käsittelevän kangassovelluksen laatiminen| Microsoft Docs
description: Tässä tehtävässä luomme tavallisen kolmen näytön kangassovelluksen suoraan SharePoint-luettelosta.
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/12/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c9c7e58c8127b1c2784e0b1d79e78a1cb9478054
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799314"
---
# <a name="generate-a-canvas-app-to-handle-project-requests"></a>Kangassovelluksen luominen projektipyyntöjen hallintaa varten
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa, joka käsittelee PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämistä SharePoint Onlinen kanssa. Lukemalla [sarjan esittelyn](sharepoint-scenario-intro.md) saat paremman käsityksen kokonaiskuvasta sekä aiheeseen liittyvät ladattavat tiedostot.

Nyt kun SharePoint-luettelot ovat paikallaan, voimme luoda ja mukauttaa ensimmäisen sovelluksemme. PowerApps on integroitu SharePointin kanssa, joten tavallisen *kolmen näytön sovelluksen* luominen suoraan luettelosta on helppoa. Tämän sovelluksen avulla voit tarkastella yhteenvetoa ja yksityiskohtaisia tietoja jokaisesta luettelon kohteesta, päivittää olemassa olevia luettelokohteita ja luoda uusia luettelokohteita. Jos luot sovelluksen suoraan luettelosta, sovellus näkyy kyseisen luettelon *näkymänä*. Voit suorittaa kyseisen sovelluksen selaimessa sekä matkapuhelimessa.

> [!TIP]
> Tämän skenaarion [latauspaketti](https://aka.ms/o4ia0f) sisältää viimeistellyn version tästä sovelluksesta: project-requests-app.msapp.

## <a name="step-1-generate-an-app-from-a-sharepoint-list"></a>Vaihe 1: Sovelluksen luominen SharePoint-luettelosta

1. Napsauta tai napauta luomassasi **Projektipyynnöt**-luettelossa kohtaa **PowerApps** ja sen jälkeen **Luo sovellus**.
   
    ![Luo sovellus](./media/sharepoint-scenario-generate-app/02-01-01-create-app.png)

2. Anna sovellukselle nimi, kuten ”Projektipyyntösovellus”, ja napsauta tai napauta sitten kohtaa **Luo**. Kun sovellus on valmis, se avautuu PowerApps Studiossa.
   
    ![Määritä sovelluksen nimi](./media/sharepoint-scenario-generate-app/02-01-02-create-app-name.png)

## <a name="step-2-review-the-app-in-powerapps-studio"></a>Vaihe 2: Tarkista sovellus PowerApps Studio

1. PowerApps Studiossa näkyy vasemmassa siirtymispalkissa oletusarvoisesti hierarkkinen näkymä sovelluksen näytöistä ja ohjausobjekteista.
   
    ![PowerApps Studio ja hierarkkinen näkymä](./media/sharepoint-scenario-generate-app/02-02-01-studio-screens-hierarchy.png)

2. Vaihda näkymää napsauttamalla tai napauttamalla pikkukuvan kuvaketta.
   
    ![PowerApps Studion näkymän valitsin](./media/sharepoint-scenario-generate-app/02-02-02-studio-view-selector.png)

3. Napsauta tai napauta kutakin näyttöä sen tarkastelemiseksi keskimmäisessä ruudussa. Näyttöjä on kolme:
   
    (a). **Selaa**-näyttö, jossa selaat, lajittelet ja suodatat luettelosta haettuja tietoja.
    
    (b). **Tiedot**-näyttö, jossa voit tarkastella kohteita tarkemmin.
    
    (c). **Muokkaa/luo**-näyttö, jossa muokataan olemassa olevaa kohdetta tai luodaan uusi.
      
      ![PowerApps Studio, jossa näkyy pikkukuvanäkymä](./media/sharepoint-scenario-generate-app/02-02-03-studio-screens-thumbnails.png)

## <a name="step-3-customize-the-apps-browse-screen"></a>Vaihe 3: Sovelluksen Selaa-näytön mukauttaminen

1. Napsauta tai napauta selaa-näyttöä.
   
    Tällä näytöllä on *asettelu*, joka sisältää *valikoiman* luetteloiden kohteiden näyttämiseen sekä muita *ohjausobjekteja*, kuten hakupalkin ja lajittelupainikkeen.

2. Valitse **BrowseGallery1**-valikoima napsauttamalla tai napauttamalla mitä tahansa tietuetta ensimmäistä lukuun ottamatta.
   
    ![Selaa valikoimaa](./media/sharepoint-scenario-generate-app/02-03-01-browse-gallery.png)

3. Napsauta tai napauta oikeanpuoleisessa ruudussa, kohdassa **ominaisuudet** sijaitsevaa kohtaa **projektipyynnöt**. 

4. Päivitä kentät vastaamaan seuraavaa luetteloa:
   
   * **Pyynnön päivämäärä**

   * **Pyytäjä**

   * **Otsikko**

     ![Valikoimakentät](./media/sharepoint-scenario-generate-app/02-03-02-gallery-fields.png)

5. Valitse **Items**-ominaisuus **BrowseGallery1**:n ollessa edelleen valittuina.
   
    ![Items-ominaisuus](./media/sharepoint-scenario-generate-app/02-03-03-items.png)

6. Muuta kaava muotoon **SortByColumns(Filter('Projektipyynnöt', StartsWith(Otsikko, TextSearchBox1.Text)), "Otsikko", If(SortDescending1, Descending, Ascending))**.
   
    ![Kaavarivi](./media/sharepoint-scenario-generate-app/02-03-04-formula.png)
   
    Näin voit lajitella ja hakea **Otsikko**-kentästä PowerAppsin valitseman oletuksen sijasta. Katso lisätietoja kohdasta [Kaavoja pintaa syvemmältä](#formula-deep-dive).

6. Napsauta tai napauta kohtaa **Tiedosto** ja sen jälkeen **Tallenna**. Palaa sovellukseen napsauttamalla tai napauttamalla ![Takaisin sovellukseen -kuvaketta](./media/sharepoint-scenario-generate-app/icon-back-to-app.png).

## <a name="step-4-review-the-apps-details-screen-and-edit-screen"></a>Vaihe 4: Tarkista sovelluksen tiedot-näyttö ja Muokkaa-näyttö
1. Napsauta tai napauta tiedot-näyttöä.
   
    Tässä näytössä on erilainen asettelu, joka sisältää kohteen *Näytä lomake* valikoimasta valitun kohteen tietojen näyttämiseen. Sillä on ohjausobjekteja kohteiden muokkaamista ja poistamista varten ja takaisin selailunäyttöön siirtymistä varten.
   
    ![Yksityiskohtien näyttölomake](./media/sharepoint-scenario-generate-app/02-04-01-details.png)

4. Napsauta tai napauta muokkausnäyttöä.
   
    Tämä näyttö sisältää *muokkauslomakkeen* valitun kohteen muokkaamista tai uuden luomista varten (jos tulit tänne suoraan selaa-näytöstä). Sillä on ohjausobjektit muutosten tallentamista tai hylkäämistä varten.

    ![Muokkaa lomaketta](./media/sharepoint-scenario-generate-app/02-04-03-edit.png)

## <a name="step-5-run-the-app-from-the-list"></a>Vaihe 5: Suorita sovellus luettelosta

1. Napsauta tai napauta **Projektipyynnöt**-luettelossa kohtaa **Kaikki kohteet** ja sen jälkeen kohtaa **Projektipyyntöjen sovellus**.
   
    ![Tarkastele projektipyyntösovellusta](./media/sharepoint-scenario-generate-app/02-05-01-view-app.png)
2. Napsauta kohtaa **Avaa**, joka avaa sovelluksen selaimen uudessa välilehdessä.
   
    ![Avaa projektipyyntösovellus](./media/sharepoint-scenario-generate-app/02-05-02-open-app.png)

3. Napsauta tai napauta sovelluksessa ![siirry tietoihin -kuvaketta](./media/sharepoint-scenario-generate-app/icon-details-arrow.png) valikoiman selauksen ensimmäistä kohdetta varten.
   
    ![Ensimmäinen valikoiman kohde](./media/sharepoint-scenario-generate-app/02-05-04-first-item.png)

4. Napsauta tai napauta ![muokkauksen kynäkuvaketta](./media/sharepoint-scenario-generate-app/icon-pencil.png) kohteen muokkaamiseksi.

5. Päivitä **Kuvaus**-kenttä. Muuta viimeinen sana ”ryhmä” sanaksi ”tiimi” ja napsauta tai napauta sitten ![valintamerkkikuvaketta](./media/sharepoint-scenario-generate-app/icon-check-mark.png)
   
   ![Päivitä Kuvaus-kenttä](./media/sharepoint-scenario-generate-app/02-05-07-edit.png)

6. Sulje selaimen välilehti.

7. Siirry takaisin **Projektipyynnöt**-luetteloon, napsauta tai napauta **Projektipyyntösovellusta** ja sen jälkeen kohtaa **Kaikki kohteet**.
   
   ![Näytä kaikki kohteet](./media/sharepoint-scenario-generate-app/02-05-08-view-all.png)
8. Tarkista sovelluksesta tekemäsi muutos.
   
    ![Vahvista muutoksesi](./media/sharepoint-scenario-generate-app/02-05-09-verify-edit.png)

Tämä on melko yksinkertainen sovellus, ja teimme siihen vain muutaman perusmukautuksen, mutta kuten näet, mielenkiintoisten toimintojen luominen nopeasti on mahdollista. Siirrymme seuraavaan tehtävään, mutta tarkastele vielä halutessasi sovellusta tarkemmin ja katso, miten ohjausobjektit ja kaavat toimivat yhdessä ja ohjaavat sovelluksen toimintaa.

## <a name="formula-deep-dive"></a>Kaavoja pintaa syvemmältä
Tämä osa on valinnainen, mutta se auttaa ymmärtämään kaavojen toimintaa paremmin. Tämän tehtävän vaiheessa 3 muokkasimme **BrowseGallery1**:n **Items**-ominaisuuden kaavaa. Tarkemmin sanottuna muutimme lajittelua ja hakua käyttämään **Otsikko**-kenttää PowerAppsin valitseman kentän sijaan. Tässä on muokattu kaava:

**SortByColumns ( Filter ( 'Project Requests', StartsWith ( Otsikko, TextSearchBox1.Text ) ), "Otsikko", If ( SortDescending1, Descending, Ascending ) )**

Mutta mitä tämä kaava tekee? Se määrittää tietolähteen, joka näkyy valikoimassa, suodattaa tiedot minkä tahansa hakukenttään kirjoitetun tiedon perusteella ja lajittelee tuloksen sovelluksen lajittele-painikkeen perusteella. Kaavassa käytetään *funktioita* sen tehtävien suorittamiseen. Funktiot käyttävät parametreja (eli syötteitä), suorittavat toiminnon (kuten suodattamisen) ja palauttavat arvon (eli tuloksen):

* [**SortByColumns**-funktio ](functions/function-sort.md) lajittelee taulukon yhden tai useamman sarakkeen perusteella.
* [**Filter**-funktio](functions/function-filter-lookup.md) löytää taulukosta tietueet, jotka vastaavat määrittämääsi kaavaa.
* [**StartsWith**-funktio ](functions/function-startswith.md) testaa, alkaako tekstimerkkijonoksi toisella.
* [**If**-funktio](functions/function-if.md) palauttaa yhden arvon, jos ehto on tosi, ja palauttaa toisen arvon, jos sama ehto on epätosi.

Kun yhdistelet funktioita kaavaan, tapahtuu seuraavaa:

1. Jos kirjoitat hakuruutuun tekstiä, **StartsWith**-funktio vertaa kyseistä tekstiä jokaisen merkkijonon alkuun luettelon **Otsikko**-sarakkeessa.
   
    **StartsWith ( Otsikko, TextSearchBox1.Text )**
   
    Esimerkiksi, jos kirjoitat hakuruutuun ”de”, näet neljä tulosta, mukaan lukien kohteet, jotka alkavat ”Desktop” ja ”Device”. Et näe kaikkia ”Mobile devices” -kohteita, koska ne eivät *ala merkkijonolla* ”de”.

2. **Filter**-funktio *palauttaa* rivit **projektipyynnöt**-taulukosta. Jos hakukentässä ei ole verrattavaa tekstiä, **Filter** palauttaa kaikki rivit.
   
    **Filter ( 'Projektipyynnöt', StartsWith ( Otsikko, TextSearchBox1.Text )**

3. **If**-funktio katsoo, onko muuttujalle **SortDescending1** määritetty arvo tosi vai epätosi (sovelluksessa lajittele-painike määrittää tämän). Funktio palauttaa sen jälkeen arvon **Descending** (laskeva) tai **Ascending** (nouseva).
   
    **If ( SortDescending1, Descending, Ascending )**

4. Nyt **SortByColumns**-funktio voi lajitella valikoiman. Tässä tapauksessa se lajittelee **Otsikko**-kentän perusteella, mutta tämä voi olla eri kenttä kuin se, mitä haet.

Jos luit tänne asti, toivomme, että sait paremman käsityksen siitä, miten tämä kaava toimii ja miten voit yhdistää funktioita ja muita elementtejä, jotta sovellukset toimivat tarvitsemallasi tavalla. Lisätietoja on artikkelissa [Viitetietoja PowerAppsin kaavoista](formula-reference.md).

## <a name="next-steps"></a>Seuraavat vaiheet
Seuraava vaihe on tämän opetusohjelmasarjan [Luo työnkulku projektin työnkulkujen hallitsemista varten](sharepoint-scenario-approval-flow.md).

