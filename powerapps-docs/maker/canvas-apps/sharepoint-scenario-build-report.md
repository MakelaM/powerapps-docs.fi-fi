---
title: Power BI -raportin luominen projektien analysointiin | Microsoft Docs
description: Tässä tehtävässä luomme Power BI -raportin, joka perustuu kahteen SharePoint-luetteloon.
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/10/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 7eb5e7385c57e0cabaab1c8457f17dc1feff96fb
ms.sourcegitcommit: c52c1869510a9a37d9f7b127e06f07583529588b
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/28/2019
ms.locfileid: "64671040"
ms.PowerAppsDecimalTransform: true
---
# <a name="create-a-power-bi-report-to-analyze-projects"></a>Power BI -raportin luominen projektien analysointiin
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa, joka käsittelee PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämistä SharePoint Onlinen kanssa. Varmista, että luet [sarjan esittelyn](sharepoint-scenario-intro.md), jotta saat paremman käsityksen kokonaiskuvasta. Lue myös aiheeseen liittyvät ladattavat tiedostot.

Tässä tehtävässä luomme Power BI -raportin, joka perustuu kahteen SharePoint-luetteloon. Tuomme luettelotiedot Power BI Desktopiin ja siistimme tietoja hieman. Sen jälkeen teemme perustason tietojen mallinnusta ja luomme joukon visualisointeja, jotka auttavat meitä tutustumaan tietoihin paremmin.

> [!TIP]
> Tämän skenaarion [latauspaketti](https://aka.ms/o4ia0f) sisältää viimeistellyn version raportista project-analysis.pbix.

## <a name="quick-review-of-power-bi-desktop"></a>Lyhyt katsaus Power BI Desktopiin
Ennen kuin aloitamme raportin luomisen, esittelemme hiukan Power BI Desktopia. Kyseessä on tehokas työkalu, jossa on paljon ominaisuuksia. Tämän vuoksi keskitymme tarkastelemaan alueita, joita käytät tässä tehtävässä. On kolme pääasiallista työaluetta tai *näkymät* Power BI Desktop: **Raportin** näkymässä **tietojen** -näkymässä ja **suhteita** näkymä. Power BI Desktop sisältää myös **Kyselyeditorin**, joka avautuu erilliseen ikkunaan.

Seuraavassa näytössä näkyy Power BI Desktop vasemmalle kolme näkymäkuvaketta: **Raportin**, **tietojen**, ja **suhteita**, ylhäältä alas. Vasemmalla oleva keltainen palkki osoittaa nykyisen näkymän: tässä tapauksessa näytettävänä on **Raportti**-näkymä. Vaihda näkymää valitsemalla jokin kolmesta kuvakkeesta.

![Power BI Desktopin näkymät](./media/sharepoint-scenario-build-report/05-00-00-tabs.png)

**Raportti**-näkymässä on viisi pääaluetta:

1. Valintanauha, joka sisältää raportteihin ja visualisointeihin liittyviä yleisiä tehtäviä.
2. **Raportti**-näkymä eli pohja, jossa visualisointeja luodaan ja järjestellään
3. Alareunassa oleva **Sivu**-välilehtien alue, josta voit valita tai lisätä uuden raporttisivun.
4. **Visualisoinnit**-ruutu, jossa voit muuttaa visualisointeja, mukauttaa värejä tai akseleita, lisätä suodattimia, vetää kenttiä ja paljon muuta.
5. **Kentät**-ruutu, jossa kyselyn elementtejä ja suodattimia voi vetää **Raportti**-näkymään tai **Visualisoinnit**-ruudun **Suodattimet**-alueelle.

![Power BI Desktopin välilehdet, näkymät ja ruudut](./media/sharepoint-scenario-build-report/05-00-01-report.png)

**Tiedot**-näkymässä on kolme pääaluetta:

1. Valintanauha, josta alla olevassa kuvassa on valittuna **Mallinnus**-välilehti. Tällä välilehdellä luodaan laskettuja taulukoita ja sarakkeita ja tehdään muita muutoksia tietomalliin.
2. Keskimmäinen ruutu, jossa näytetään valitun taulukon tiedot.
3. **Kentät**-ruutu, jossa voit määrittää, miten kentät näytetään raporteissa.

![Power BI Desktopin tietonäkymä](./media/sharepoint-scenario-build-report/05-00-02-data.png)

Emme käytä tässä tehtävässä **Suhteet**-näkymää, mutta voit tutustua siihen myöhemmin, kun olemme tuoneet luettelotiedot Power BI Desktopiin.

**Kyselyeditorissa** voit laatia kyselyjä, muuntaa tietoja ja ladata sitten tarkennetun tietomallin Power BI Desktopiin. **Kyselyeditorissa** on neljä pääaluetta:

1. Valintanauha, jossa on useita vaihtoehtoja tuotujen tietojen muovaamiseen ja muuntamiseen.
2. Vasen ruutu, jossa on luettelo kyselyistä ja josta ne valitaan tarkasteltaviksi tai muovattaviksi.
3. Keskimmäinen ruutu, jossa valitun kyselyn tiedot näytetään ja muokataan.
4. **Kyselyasetukset**-ikkuna, jossa on luettelo kyselyn ominaisuuksista ja tietomuunnosvaiheista, jotka on otettu käyttöön.

![Power BI Desktopin kyselyeditori](./media/sharepoint-scenario-build-report/05-00-03-query.png)

## <a name="step-1-get-data-into-power-bi-desktop"></a>Vaihe 1: Saat tietoja Power BI Desktop
Tässä vaiheessa yhdistämme ensin kaksi luetteloa. Sitten siistimme tiedot poistamalla sarakkeita, joita emme tarvitse tietoanalyysiin. Muutamme myös joidenkin jäljelle jäävien sarakkeiden tietotyyppejä, jotta laskutoimitukset toimivat oikein. Lisätietoja tietojen noutamisesta ja siistimisestä Power BI Desktopissa saat ohjatun oppimisen kurssin osasta [Tietojen noutaminen](https://powerbi.microsoft.com/guided-learning/powerbi-learning-1-1-overview-of-power-bi-desktop).

### <a name="connect-to-sharepoint-lists"></a>Yhdistäminen SharePoint-luetteloihin
1. Napsauta tai napauta Power BI Desktopin **Aloitus**-välilehdellä **Nouda tiedot** ja sitten **Lisää…**
   
    ![Nouda tiedot](./media/sharepoint-scenario-build-report/05-01-01-get-data.png)
2. Napsauta tai napauta **Nouda tiedot** -valintaikkunassa **SharePoint Online -luettelo** ja sitten **Muodosta yhteys**.
   
    ![Yhdistäminen SharePoint-luetteloon](./media/sharepoint-scenario-build-report/05-01-02-sharepoint-list.png)
3. Anna SharePoint-sivustosi URL-osoite ja napsauta tai napauta **OK**.
   
    ![SharePoint-luettelon URL-osoite](./media/sharepoint-scenario-build-report/05-01-03-sharepoint-url.png)
4. Jos näyttöön tulee seuraava valintaikkuna, varmista, että olet kirjautunut sisään oikeilla tunnistetiedoilla, ja napsauta tai napauta **Yhdistä**.
   
    ![SharePoint-luettelon tunnistetiedot](./media/sharepoint-scenario-build-report/05-01-04-credentials.png)
5. Valitse **Projektin tiedot** ja **Projektipyynnöt** ja napsauta tai napauta sitten **Muokkaa**.
   
    ![Sharepoint-luetteloiden valitseminen](./media/sharepoint-scenario-build-report/05-01-05-list-navigator.png)
   
    Luettelot näytetään nyt taulukkoina kyselyeditorissa.
   
    ![Taulukot kyselyeditorissa](./media/sharepoint-scenario-build-report/05-01-06-query-editor.png)

### <a name="remove-unnecessary-columns-from-the-tables"></a>Tarpeettomien sarakkeiden poistaminen taulukoista
1. Napsauta tai napauta vasemmassa siirtymisruudussa **Projektin tiedot**.
2. Valitse keskimmäisessä ruudussa sarake **FileSystemObjectType** ja napsauta tai napauta **Poista sarakkeet**.
   
    ![Poista sarakkeet](./media/sharepoint-scenario-build-report/05-01-07-remove-column.png)
3. Poista jälkeen kaksi saraketta **tunnus** sarakkeen: **ServerRedirectedEmbedURL** ja **ContentTypeId**. 
   > [!TIP]
   > Valitse molemmat sarakkeet käyttämällä vaihtonäppäintä ja napsauta tai napauta sitten **Poista sarakkeet**.
4. Poista kaikki sarakkeen **PMAssigned** oikealla puolella olevat sarakkeet (yhteensä 22 saraketta). Taulukon pitäisi vastata seuraavaa kuvaa:
   
    ![Project Details -taulukko kyselyeditorissa](./media/sharepoint-scenario-build-report/05-01-08-table-details.png)
5. Toista sama prosessi uudelleen, tällä kertaa kohteelle **Projektipyynnöt**: poista **FileSystemObjectType**, **ServerRedirectedEmbedURL**,  **ContentTypeId** ja kaikki **Hyväksytty**-sarakkeen oikealla puolella olevat sarakkeet (yhteensä 22 saraketta). Taulukon pitäisi vastata seuraavaa kuvaa:
   
    ![ Projektipyynnöt-taulukko kyselyeditorissa](./media/sharepoint-scenario-build-report/05-01-09-table-requests.png)

### <a name="change-the-data-type-on-project-details-columns"></a>Tietotyypin muuttaminen Projektin tiedot -sarakkeissa
1. Valitse **ProjectedDays** sarake, napsauta tai napauta **tietotyyppi: Mikä tahansa**, sitten **kokonaisluku**.
   
    ![Tietotyypin muuttaminen kokonaisluvuksi](./media/sharepoint-scenario-build-report/05-01-10-datatype-number.png)
2. Toista edellinen vaihe **ActualDays**-sarakkeelle.
3. Valitse **ApprovedDate** sarake, napsauta tai napauta **tietotyyppi: Mikä tahansa**, sitten **päivämäärä**.
   
    ![ Tietotyypin muuttaminen päivämääräksi](./media/sharepoint-scenario-build-report/05-01-11-datatype-date.png)

4. Toista edellinen vaihe **ProjectedStartDate**- ja **ProjectedEndDate**-sarakkeille.

### <a name="change-the-data-type-on-project-requests-columns"></a>Tietotyypin muuttaminen Projektipyynnöt-sarakkeissa

1. Valitse **arvioidut päivät** sarake, napsauta tai napauta **tietotyyppi: Mikä tahansa**, sitten **kokonaisluku**.

2. Valitse **pyynnön päivämäärä** sarake, napsauta tai napauta **tietotyyppi: Mikä tahansa**, sitten **päivämäärä**.

### <a name="apply-and-save-changes"></a>Ota muutokset käyttöön ja tallenna

1. Sulje kyselyeditori ja palaa Power BI Desktop -pääikkunaan valitsemalla **Aloitus**-välilehdestä **Sulje ja ota käyttöön**.
   
    ![Sulje ja ota muutokset käyttöön](./media/sharepoint-scenario-build-report/05-01-12-close-apply.png)

2. Napsauta tai napauta **Tiedosto** ja sitten **Tallenna** ja tallenna nimellä project-analysis.pbix.

## <a name="step-2-improve-the-data-model"></a>Vaihe 2: Tietomallin parantaminen
SharePoint-luetteloiden tiedot on nyt noudettu Power BI Desktopiin, ja voimme siirtyä tietojen mallinnukseen. Tietojen mallinnus voi olla aikaa vievä prosessi, mutta näytämme lyhyesti muutamia kiinnostavia keinoja, joiden avulla saat luettelotiedoista enemmän irti Power BI Desktopissa:

* Muuta tapaa, jolla kaksi taulukkoa liittyy toisiinsa
* Lisää päivämäärätaulukko, jotta voimme tehdä viikonpäiviin perustuvia laskutoimituksia
* Laske projektin välitavoitteiden väliset aikavälit lisäämällä laskettuja sarakkeita
* Lisää mittayksiköitä projektin arvioitujen päivien ja toteutuneiden päivien varianssin laskemiseen

Kun nämä vaiheet on suoritettu, voimme luoda visualisointeja, jotka hyödyntävät malliin tehtyjä parannuksia. Lisätietoja tiedon mallintamisesta ja siistimisestä Power BI Desktopissa saat ohjatun oppimisen kurssin osasta [Mallintaminen](https://powerbi.microsoft.com/guided-learning/powerbi-learning-2-1-intro-modeling-data).

### <a name="change-table-relationships"></a>Taulukon suhteiden muuttaminen
Kun Power BI Desktop toi luettelot, se loi niiden välille suhteen molempien taulukoiden **Id**-sarakkeiden perusteella. Suhteen pitäisi olla **Projektipyynnöt**-taulukon **Id**-sarakkeen ja **Projektin tiedot** -taulukon **RequestId**-sarakkeen välillä. Korjataan ongelma:

1. Napsauta tai napauta **Tietonäkymä**-kuvaketta.
   
    ![Tietonäkymä](./media/sharepoint-scenario-build-report/05-02-01-data-view.png)

2. Napsauta tai napauta **Mallinnus**-välilehdeltä **Suhteiden hallinta**. Pysymme tässä **Tiedot**-näkymän välilehdessä kaikkien tiedon mallinnukseen liittyvien vaiheiden ajan.
   
    ![Suhteiden hallinta](./media/sharepoint-scenario-build-report/05-02-02-manage-relationships.png)

3. Varmista, että olemassa oleva suhde on valittuna, napsauta tai napauta **Poista** ja vahvista valitsemalla uudelleen **Poista**.
   
    ![Poista suhde](./media/sharepoint-scenario-build-report/05-02-03-delete-relationship.png)

4. Luo erilainen suhde valitsemalla **Uusi**.

5. **Luo suhde** -valintaikkunassa:
   
   1. Valitse ensimmäisessä taulukossa **Project Requests** ja **Id**-sarake.
   
   2. Valitse toisessa taulukossa **Project Details** ja **RequestId**-sarake.
   
   3. Näytön pitäisi nyt näyttää samalta kuin seuraavassa kuvassa. Kun olet valmis, napsauta tai napauta **OK** ja sitten **Sulje**.
      
       ![Luo suhde](./media/sharepoint-scenario-build-report/05-02-04-create-relationship.png)

### <a name="add-a-date-table-to-make-date-based-calculations-easier"></a>Päivämäärätaulukon lisääminen helpottamaan päivämäärään perustuvia laskutoimituksia
1. Napsauta tai napauta **Uusi taulukko**.
   
    ![Uusi taulukko](./media/sharepoint-scenario-build-report/05-02-05-modeling-table.png)
2. Kirjoita kaavariville seuraava kaava: **Dates = CALENDARAUTO()**.
   
    ![Kaavarivi Dates = CALENDARAUTO()](./media/sharepoint-scenario-build-report/05-02-06-formula-bar.png)
   
    Kaava luo taulukon nimeltä **Dates**, jossa on yksi sarake. Taulukko kattaa kaikki toisen taulukon päivämäärät, ja se päivittyy automaattisesti, jos muita päivämääriä lisätään (eli jos tiedot päivitetään).
   
    Tämä kaava ja muut tässä osassa olevat kaavat käyttävät DAX-kieltä (Data Analysis Expressions, tietojen analysoinnin lausekkeet), joka on Power BI:ssä ja muissa tekniikoissa käytetty kaavakieli. Lisätietoja on kohdassa [DAX-kielen perusteet Power BI Desktopissa](https://docs.microsoft.com/power-bi/desktop-quickstart-learn-dax-basics).
3. Luo **Dates**-taulukko painamalla Enter.
   
    ![Dates-taulukko](./media/sharepoint-scenario-build-report/05-02-07-date-table.png)

### <a name="add-a-calculated-column-to-the-dates-table"></a>Lasketun sarakkeen lisääminen Dates-taulukkoon
1. Napsauta tai napauta päivämäärätaulukossa **Uusi sarake**.
   
    ![Uusi sarake](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Kirjoita kaavariville seuraava kaava: **IsWeekDay = SWITCH(WEEKDAY(Dates[Date]); 1;0;7;0;1)**.
   
    Tämä kaava määrittää, onko **Päivämäärä**-sarakkeessa oleva päivä arkipäivä. Jos päivämäärä on arkipäivä, **IsWeekDay**-sarake saa arvon 1; muussa tapauksessa se saa arvon 0.
3. Lisää **IsWeekDay**-sarake **Dates**-taulukkoon painamalla Enter.
   
    ![Lisää IsWeekDay-sarake](./media/sharepoint-scenario-build-report/05-02-08-column-isweekday.png)

### <a name="add-a-calculated-column-to-the-project-details-table"></a>Lasketun sarakkeen lisääminen Project Details -taulukkoon
1. Napsauta tai napauta oikeassa ruudussa **Projektin tiedot** -taulukkoa ja sitten **Uusi sarake**.
   
    ![Uusi sarake](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Kirjoita kaavariville seuraava kaava:
   
    ```dax
    ApprovedStartDiff = CALCULATE(SUM(Dates[IsWeekday]),
       DATESBETWEEN(Dates[Date],
          'Project Details'[ApprovedDate],
          'Project Details'[ProjectedStartDate]
      )
    )
    ```
   
    Tämä kaava laskee projektin hyväksymispäivän ja sen arvioidun aloituspäivän erotuksen päivinä. Koska kaava käyttää **Dates**-taulukon **IsWeekDay**-saraketta, se laskee vain arkipäivät.
3. Paina Enter ja lisää **ApprovedStartDiff**-sarake **Projektin tiedot** -taulukkoon.
   
    ![Lisää ApprovedStartDiff-sarake](./media/sharepoint-scenario-build-report/05-02-09-column-approvedstartdiff.png)

### <a name="add-a-calculated-column-to-the-project-requests-table"></a>Lasketun taulukon lisääminen Projektipyynnöt-taulukkoon
1. Napsauta tai napauta oikeassa ruudussa **Projektipyynnöt**-taulukkoa ja sitten **Uusi sarake**.
   
    ![Uusi sarake](./media/sharepoint-scenario-build-report/05-02-00-modeling-column.png)
2. Kirjoita kaavariville seuraava kaava:
   
    ```dax
    RequestDateAge = CALCULATE(SUM(Dates[IsWeekday]),
       DATESBETWEEN(Dates[Date],
          'Project Requests'[RequestDate],
          NOW()
       )
    )
    ```
   
    Tämä kaava laskee projektin pyytämispäivämäärän ja tämän päivän päivämäärän (NOW()) välisen erotuksen. Kuten aiemmin mainittiin, kaava laskee vain arkipäivät. Tätä saraketta käytetään, kun etsitään projektia, joka on odottanut pisimpään.
3. Lisää **RequestDateAge**-sarake **Projektipyynnöt**-taulukkoon painamalla Enter.
   
    ![Lisää RequestDateAge-sarake](./media/sharepoint-scenario-build-report/05-02-10-column-requestdateage.png)

### <a name="add-a-measure-to-the-project-details-table"></a>Lisää mittayksikkö Projektin tiedot -taulukkoon
1. Napsauta tai napauta oikeassa ruudussa **Project Details** -taulukkoa ja sitten **Uusi mittari**.
   
    ![Uusi mittayksikkö](./media/sharepoint-scenario-build-report/05-02-00-modeling-measure.png)
2. Kirjoita kaavariville seuraava kaava:
   
    ```dax
    VarProjectedActual = DIVIDE(
        SUM('Project Details'[ActualDays]) - SUM('Project Details'[ProjectedDays]),
        SUM('Project Details'[ProjectedDays])
    )
    ```
   
    Tämä kaava laskee projektin toteutuneiden ja arvioitujen päivien välisen varianssin. Lisäämme tämän mittarina emmekä laskettuna sarakkeena, joten se palauttaa oikeat tulokset riippumatta siitä, miten tiedot on suodatettu tai koostettu raporttiin.
3. Lisää **VarProjectedActual**-mittari **Project Details** -taulukkoon painamalla Enter.
   
    ![Lisää VarProjectedActual-mittari](./media/sharepoint-scenario-build-report/05-02-11-measure-varprojectedactual.png)

### <a name="add-a-measure-to-the-project-requests-table"></a>Mittayksikön lisääminen Projektipyynnöt-taulukkoon
1. Napsauta tai napauta oikeassa ruudussa **Project Requests** -taulukkoa ja sitten **Uusi mittari**.
   
    ![Uusi mittayksikkö](./media/sharepoint-scenario-build-report/05-02-00-modeling-measure.png)
2. Kirjoita kaavariville seuraava kaava:
   
    ```dax
    MaxDaysPending = MAXX(
        FILTER('Project Requests', 'Project Requests'[Approved]="Pending"),
        'Project Requests'[RequestDateAge]
    )
    ```
   
    Tämä kaava etsii aiemmin määritetyn lasketun sarakkeen perusteella projektin, joka on odottanut pisimpään.
3. Lisää **MaxDaysPending**-mittayksikkö **Projektipyynnöt**-taulukkoon painamalla Enter.
   
    ![Lisää MaxDaysPending-mittayksikkö](./media/sharepoint-scenario-build-report/05-02-12-measure-maxdayspending.png)

## <a name="step-3-create-report-visualizations"></a>Vaihe 3: Raportin visualisointien luominen
Nyt olemme vaiheessa, joka monelle tulee mieleen tietojen analysoinnista: visualisointien luomisessa. Visualisointi auttaa löytämään tiedoista toistuvia kuvioita. Tässä vaiheessa luomme neljä visualisointia:

* pylväskaavion, joka näyttää projektin arvioidut päivät ja toteutuneet päivät
* pylväskaavion, joka näyttää jokaisen projektin varianssin
* kortin, joka näyttää, mikä projekti on odottanut pisimpään
* taulukon, joka näyttää projektin hyväksynnän ja arvioidun aloituspäivän välisen ajan.

Kun olemme luoneet raportin visualisoinnit Power BI Desktopissa, julkaisemme tiedot ja raportit Power BI -palveluun, jotta voimme luoda ja jakaa koontinäyttöjä. Lisätietoja raporttien luomisesta Power BI Desktopissa saat ohjatun oppimisen kurssin osasta [Visualisoinnit](https://powerbi.microsoft.com/guided-learning/powerbi-learning-3-1-intro-visualizations).

### <a name="create-a-bar-chart-to-show-projected-versus-actual"></a>Luo pylväskaavio, joka näyttää arvioidun verrattuna toteutuneeseen
1. Napsauta tai napauta **Raportti**-näkymän kuvaketta. Pysymme tässä näkymässä loppuajan, jonka vietämme Power BI Desktopissa.
   
    ![Raporttinäkymä](./media/sharepoint-scenario-build-report/05-03-01-report-view.png)
2. Valitse oikealta **Visualisoinnit**-ruutu ja napsauta tai napauta **Klusteroitu pylväskaavio**.
   
    ![Visualisoinnit – klusteroitu pylväskaavio](./media/sharepoint-scenario-build-report/05-03-00-visuals-column.png)
3. Vedä **PMAssigned** ja **Title** **Kentät**-ruudun kohdasta **Projektin tiedot** **Visualisoinnit**-ruudun kohtaan **Akseli**.
   
    ![Akseli Visualisoinnit-ruudussa](./media/sharepoint-scenario-build-report/05-03-00-axis.png)
4. Vedä **ActualDays** ja **ProjectedDays** **Kentät**-ruudun kohdasta **Projektin tiedot** **Visualisoinnit**-ruudun kohtaan **Arvo**.
   
    ![Arvo Visualisoinnit-ruudussa](./media/sharepoint-scenario-build-report/05-03-03-value-projected.png)
5. Visualisoinnin pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![ProjectedDays ja ActualDays sarakkeen PMAssigned mukaan](./media/sharepoint-scenario-build-report/05-03-04-chart-projected.png)
6. Vedä **Status** **Kentät**-ruudun kohdasta **Project Details** **Visualisoinnit**-ruudun **Suodattimet**-alueelle ja valitse sitten **Valmis**-valintaruutu.
   
   ![Suodata Status-sarakkeen perusteella](./media/sharepoint-scenario-build-report/05-03-05-filters-projected.png)
   
   Kaavio suodatetaan näyttämään vain valmiit projektit, koska vertailemme arvioituja päiviä toteutuneisiin päiviin.
7. Voit siirtyä projektipäälliköiden ja projektien hierarkiassa ylös- ja alaspäin napsauttamalla kaavion vasemmassa yläkulmassa olevia nuolia. Seuraavassa kuvassa näet, miltä projekteihin porautuminen näyttää.
   
   ![Poraudu pylväskaavioon](./media/sharepoint-scenario-build-report/05-03-06-chart-projected-drill.png)

### <a name="create-a-bar-chart-to-show-variance-from-projected"></a>Luo pylväskaavio, joka näyttää varianssin arvioidusta
1. Napsauta tai napauta pohjaa juuri luomasi visualisoinnin ulkopuolelta.
2. Valitse oikealta **Visualisoinnit**-ruutu ja napsauta tai napauta **Klusteroitu pylväskaavio**.
   
    ![Visualisoinnit – klusteroitu pylväskaavio](./media/sharepoint-scenario-build-report/05-03-00-visuals-column.png)
3. Vedä **PMAssigned** ja **Title** **Kentät**-ruudun kohdasta **Projektin tiedot** **Visualisoinnit**-ruudun kohtaan **Akseli**.
   
    ![Akseli Visualisoinnit-ruudussa](./media/sharepoint-scenario-build-report/05-03-00-axis.png)
4. Vedä **VarProjectedActual** **Kentät**-ruudun kohdasta **Projektin tiedot** **Visualisoinnit**-ruudun kohtaan **Arvo**.
   
    ![Arvo Visualisoinnit-ruudussa](./media/sharepoint-scenario-build-report/05-03-07a-value-variance.png)
5. Vedä **Status** **Kentät**-ruudun kohdasta **Project Details** **Visualisoinnit**-ruudun **Suodattimet**-alueelle ja valitse sitten **Valmis**-valintaruutu.
   
    ![Suodata Status-sarakkeen perusteella](./media/sharepoint-scenario-build-report/05-03-07b-filters-variance.png)
   
    Visualisoinnin pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![VarProjectedActual sarakkeen PMAssigned mukaan](./media/sharepoint-scenario-build-report/05-03-08-chart-variance.png)
   
    Kaaviosta näkyy selvästi, kuinka paljon enemmän vaihtelua Irvin Sayersin suorittamissa projekteissa on verrattuna Joni Shermanin projekteihin. Näet projektikohtaisen vaihtelun porautumalla syvemmälle. Näet myös, oliko arvioituja päiviä enemmän vai vähemmän kuin toteutuneita päiviä.
   
    ![VarProjectedActual sarakkeen Title mukaan](./media/sharepoint-scenario-build-report/05-03-09-chart-variance-drill.png)
6. Siirrä luotuja visualisointeja ja muuta niiden kokoa, jotta ne sopivat rinnakkain, ennen kuin luomme lisää visualisointeja.
   
    ![Sovita kaaviot rinnakkain](./media/sharepoint-scenario-build-report/05-03-10-two-charts.png)

### <a name="create-a-card-that-shows-the-longest-pending-project"></a>Luo kortti, joka näyttää pisimpään odottaneen projektin
1. Napsauta tai napauta pohjaa juuri luomasi visualisoinnin ulkopuolelta.
2. Valitse oikealta **Visualisoinnit**-ruutu ja napsauta tai napauta **Kortti**.
   
    ![Visualisoinnit – kortti](./media/sharepoint-scenario-build-report/05-03-11-visuals-card.png)
3. Vedä **MaxDaysPending** **Kentät**-ruudun kohdasta **Projektipyynnöt** **Visualisoinnit**-ruudun kohtaan **Kentät**.
   
    ![Kentät Visualisoinnit-ruudussa](./media/sharepoint-scenario-build-report/05-03-12-value-max.png)
4. Napsauta tai napauta **Muotoile** (maalitela), ja määritä sitten **Reuna**-kohdan tilaksi **Käytössä**.
   
    ![Muotoilusivellin – Reuna](./media/sharepoint-scenario-build-report/05-03-13a-format.png)
5. Määritä **Otsikko**-kohdan tilaksi **Käytössä** ja lisää sitten otsikko ”Päivien enimmäismäärä hyväksynnän odottamiselle”.
   
    ![Lisää otsikko](./media/sharepoint-scenario-build-report/05-03-13b-title.png)
   
    Visualisoinnin pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![ Päivien enimmäismäärä hyväksynnän odottamiselle](./media/sharepoint-scenario-build-report/05-03-14-chart-max.png)
   
    Kun raportti on julkaistu, käytämme tätä ruutua laukaisemaan hälytyksen, jos odottavan projektin enimmäisarvo saavuttaa tietyn raja-arvon.

### <a name="create-a-table-that-shows-the-time-between-project-approval-and-projected-start-date"></a>Luo taulukko, joka näyttää projektin hyväksynnän ja arvioidun aloituspäivän välisen ajan
1. Napsauta tai napauta pohjaa juuri luomasi visualisoinnin ulkopuolelta.
2. Valitse oikealta **Visualisoinnit**-ruutu ja napsauta tai napauta **Taulukko**.
   
    ![Visualisoinnit – taulukko](./media/sharepoint-scenario-build-report/05-03-15-visuals-table.png)
3. Vedä**PMAssigned**, **Title** ja **ApprovedStartDiff** **Kentät**-ruudun kohdasta **Projektin tiedot** **Visualisoinnit**-ruudun kohtaan **Arvot**.
   
    ![Arvot visualisointiruudussa](./media/sharepoint-scenario-build-report/05-03-16-value-diff.png)
4. Vedä **ProjectedStartDate** **Kentät**-ruudun kohdasta **Projektin tiedot** **Visualisoinnit**-ruudun **Suodattimet**-alueelle, ja valitse sitten kaikki päivämäärät paitsi **(Tyhjä)**.
   
    ![Suodata ProjectedStartDate-sarakkeen perusteella](./media/sharepoint-scenario-build-report/05-03-17-filters-diff.png)
5. Muuta taulukon sarakkeiden kokoa siten, että näet kaikki tiedot, ja lajittele laskevasti **ApprovedStartDiff**-sarakkeen mukaan. Visualisoinnin pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![Taulukko, jossa on ApprovedStartDiff-arvot](./media/sharepoint-scenario-build-report/05-03-18-chart-diff.png)
6. Napsauta tai napauta **Arvot**-alueen kohdan **ApprovedStartDiff** alanuolta ja valitse sitten **Keskiarvo**. Nyt voimme nähdä projektin hyväksynnän ja arvioidun aloituspäivämäärän välisen ajan keskiarvon.
   
    ![Laske keskiarvo](./media/sharepoint-scenario-build-report/05-03-20a-average-menu.png)
7. Napsauta tai napauta kohdan **ApprovedStartDiff** alanuolta uudelleen, napsauta tai napauta **Ehdollinen muotoilu** ja valitse sitten **Taustaväriasteikot**.
   
   ![Ehdollinen muotoilu](./media/sharepoint-scenario-build-report/05-03-20b-conditional-menu.png)
8. Aseta värit **pienimmälle** ja **suurimmalle** kentälle alla näkyvällä tavalla ja napsauta tai napauta sitten **OK**.
   
   ![Ehdollisen muotoilun asetukset](./media/sharepoint-scenario-build-report/05-03-21-conditional-dialog.png)
   
   Visualisoinnin pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
   ![Valmis ehdollinen muotoilu](./media/sharepoint-scenario-build-report/05-03-22-chart-diff-completed.png)
   
   Kuten näet, Irvin Sayersin projekteilla on tapana alkaa paljon myöhemmin hyväksynnän jälkeen. Määritetyn päällikön lisäksi myös moni muu tekijä voi vaikuttaa asiaan, mutta tätä kannattaa tutkia.

Olemme saapuneet raporttiosion loppuun. Sinulla pitäisi nyt olla valmis raportti, joka perustuu SharePointista tuotuihin tietoihin, jotka on siistitty ja mallinnettu Power BI Desktopissa. Jos kaikki sujui suunnitelmien mukaan, raportin pitäisi näyttää samalta kuin seuraavassa kuvassa.

![Valmis raportti](./media/sharepoint-scenario-build-report/05-03-23-report-completed.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelmasarjan seuraava vaihe on [Power BI -projektiraportin julkaiseminen ja koontinäytön luominen](sharepoint-scenario-publish-report.md).

