---
title: Luo sovellus ja hallitse projekteja | Microsoft Docs
description: Tässä tehtävässä rakennamme sovelluksen alusta alkaen. Tämä sovellus sallii käyttäjän määrittää esimiehen projekteihin ja päivittää projektin tietoja.
documentationcenter: na
author: mgblythe
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 06/12/2017
ms.author: mblythe
ms.openlocfilehash: fca166ef388921e08bf71149a8b1274a31a7dc52
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "32330625"
---
# <a name="create-an-app-to-manage-projects"></a>Luo sovellus ja hallitse projekteja
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämisestä SharePoint Onlinen kanssa. Varmista, että luet [sarjan esittelyn](sharepoint-scenario-intro.md), jotta saat paremman käsityksen kokonaiskuvasta. Lue myös aiheeseen liittyvät ladattavat tiedostot.

Tässä tehtävässä rakennamme sovelluksen alusta alkaen. Tämä sovellus sallii käyttäjän määrittää esimiehen projekteihin ja päivittää projektin tietoja. Näkyviin tulee joitakin samoja ohjausobjekteja ja kaavoja, joita näimme ensimmäisessä sovelluksessa, mutta tällä kertaa rakennamme enemmän sovellusta itse. Prosessi on monimutkaisempi, mutta opit lisää, joten uskomme, että tämä kannattaa.

> [!TIP]
> Tämän skenaarion [latauspaketti](https://aka.ms/o4ia0f) sisältää viimeistellyn version tästä sovelluksesta: project-details-app.msapp.

## <a name="quick-review-of-powerapps-studio"></a>Lyhyt PowerApps Studio -katsaus
PowerApps Studiossa on kolme ruutua ja valintanauha, joiden avulla sovellusten luominen on samankaltaista kuin diapinon tekeminen PowerPointissa:

1. Vasen siirtymispalkki, jossa näkyy sovelluksen kaikkien näyttöjen ja ohjausobjektien hierarkkinen näkymä, sekä näyttöjen pikkukuvat
2. Keskimmäinen ruutu, joka sisältää sovelluksen näytön, jossa työskennellään
3. Oikea ruutu, jossa määritetään asetuksia, kuten asettelu ja tietolähteet
4. Avattava Ominaisuus-luettelo, jossa valitaan ominaisuudet, joihin kaavat vaikuttavat
5. Kaavarivi, johon lisätään kaavoja (kuten Excelissä), jotka vaikuttavat sovelluksen toimintaan
6. Valintanauha, jossa lisätään ohjausobjekteja ja mukautetaan suunnitteluelementtejä

![PowerApps Studio](./media/sharepoint-scenario-build-app/04-00-00-powerapps-studio.png)

## <a name="step-1-create-screens"></a>Vaihe 1: Luo näytöt
Aloitetaan sitten sovelluksen rakentaminen.

### <a name="create-and-save-the-app"></a>Luo ja tallenna sovellus
1. Napsauta tai napauta PowerApps Studiossa **Uusi** ja napsauta tai napauta kohdassa **Tyhjä sovellus** **Puhelinasettelu**.
   
    ![Tyhjä sovellus, puhelinasettelu](./media/sharepoint-scenario-build-app/04-01-01-blank-phone-app.png)
2. Napsauta tai napauta **Tiedosto**. **Sovellusasetukset**-välilehti avautuu. Kirjoita nimi ”Projektinhallinnan sovellus”.
   
    ![Sovelluksen nimi](./media/sharepoint-scenario-build-app/04-01-02-app-name.png)
3. Napsauta tai napauta **Tallenna nimellä**, varmista, että sovellus tallennetaan pilvipalveluun, ja napsauta sitten oikeassa alakulmassa **Tallenna**.
   
    ![Tallenna pilveen](./media/sharepoint-scenario-build-app/04-01-03-save-to-cloud.png)

4. Napsauta tai napauta ![Takaisin sovellukseen -kuvake](./media/sharepoint-scenario-build-app/icon-back-to-app.png) siirtyäksesi takaisin sovellukseen.

### <a name="add-four-screens-to-the-app"></a>Lisää neljä näyttöä sovellukseen
Tässä vaiheessa luomme neljä tyhjää näyttöä sovellukselle. Käytämme erilaisia näytön asetteluja näytön tarkoituksen mukaan. Lisäämme elementtejä näihin näyttöihin myöhemmissä vaiheissa.

| **Näyttö** | **Tarkoitus** |
| --- | --- |
| **SelectTask** |Avausnäyttö; siirry muihin näyttöihin |
| **AssignManager** |Määritä esimies hyväksyttyyn projektiin |
| **ViewProjects** |Näytä luettelo projekteista sekä yhteenvetotietoja |
| **UpdateDetails** |Näytä ja päivitä projektin tiedot |

1. Napsauta tai napauta **Aloitus**-välilehdessä ensin **NewScreen** ja sen jälkeen **Vieritettävissä oleva näyttö**.
   
    ![Vieritettävissä oleva näyttö](./media/sharepoint-scenario-build-app/04-01-03a-scrollable-screen.png)
2. Anna näytölle uusi nimi **SelectTask**.
   
    ![Nimeä näyttö uudelleen](./media/sharepoint-scenario-build-app/04-01-04-rename-screen.png)
3. Luo ja nimeä muita näyttöjä uudelleen:
   
   1. Napsauta tai napauta **NewScreen** ja sen jälkeen **Vieritettävissä oleva näyttö**. Anna näytölle uusi nimi **AssignManager**.
   2. Napsauta tai napauta **NewScreen** ja sen jälkeen **Luettelonäyttö**. Anna näytölle uusi nimi **ViewProjects**.
   3. Napsauta tai napauta **NewScreen** ja sen jälkeen **Lomakenäyttö**. Anna näytölle uusi nimi **UpdateDetails**.
4. Valitse **Screen1**:n vieressä kolme pistettä (**...** ) ja napsauta tai napauta **Poista**.
   
    ![Näytön poistaminen](./media/sharepoint-scenario-build-app/04-01-04a-delete-screen.png)

Sovelluksen pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.

![Kaikki sovelluksen näytöt](./media/sharepoint-scenario-build-app/04-01-05-all-screens.png)

## <a name="step-2-connect-to-a-sharepoint-list"></a>Vaihe 2: Yhdistä SharePoint-luetteloon
Tässä vaiheessa yhdistämme **tuotetietojen** SharePoint-luetteloon. Käytämme vain yhtä luetteloa tässä sovelluksessa, mutta voit helposti yhdistää molempiin, jos haluat laajentaa sovellusta.

1. Napsauta tai napauta vasemmassa siirtymispalkissa kohtaa **SelectTask**.
2. Napsauta tai napauta oikean ruudun kohtaa **Lisää tietolähde**.
   
    ![Yhdistä tietoihin](./media/sharepoint-scenario-build-app/04-02-01-connect.png)
3. Napsauta tai napauta **Uusi yhteys**.
   
    ![Uusi yhteys](./media/sharepoint-scenario-build-app/04-02-02-new-connection.png)
4. Napsauta tai napauta **SharePoint**.
   
    ![SharePoint-yhteys](./media/sharepoint-scenario-build-app/04-02-03-sharepoint-connection.png)
5. Valitse **Yhdistä suoraan (pilvipalvelut)** ja napsauta tai napauta **Luo**.
   
    ![Yhdistä suoraan (pilvipalvelut)](./media/sharepoint-scenario-build-app/04-02-03a-sharepoint-cloud.png)
6. Kirjoita SharePointin URL-osoite ja napsauta tai napauta **Siirry**.
   
    ![SharePointin URL-osoite yhteyden muodostamista varten](./media/sharepoint-scenario-build-app/04-02-04-sharepoint-url.png)
7. Valitse **Projektitiedot**-luettelo ja napauta tai napsauta sitten **Yhdistä**.
   
    ![Valitse Projektitiedot-luettelo](./media/sharepoint-scenario-build-app/04-02-05-sharepoint-lists.png)
   
    **Tietolähteet**-välilehti oikeanpuoleisessa ruudussa näyttää nyt luomasi yhteyden.
   
    ![Tietolähteet-välilehti](./media/sharepoint-scenario-build-app/04-02-06-data-sources.png)

## <a name="step-3-build-the-selecttask-screen"></a>Vaihe 3: Rakenna SelectTask-näyttö
Tässä vaiheessa kerromme tavan, jolla voit siirtyä sovelluksen muihin näyttöihin, työskennellessäsi joidenkin PowerAppsin tarjoamien ohjausobjektien, kaavojen ja muotoiluasetusten kanssa.

### <a name="update-the-title-and-insert-introductory-text"></a>Päivitä otsikko ja lisää esittelyteksti
1. Napsauta tai napauta vasemmassa siirtymispalkissa **SelectTask**-näyttöä.
2. Valitse keskimmäisessä ruudussa oletusarvo **[Otsikko]** ja päivitä sitten kaavarivillä **Teksti**-ominaisuuden arvoksi ”Contoso Project Management”.
   
    ![Teksti-ominaisuus kaavarivillä](./media/sharepoint-scenario-build-app/04-03-02-text-property.png)
3. Valitse **Lisää**-välilehti, napsauta tai napauta **Nimi** ja vedä sitten otsikko alas yläpalkin alapuolelle.
   
    ![Lisää nimi](./media/sharepoint-scenario-build-app/04-03-03-text-default.png)
4. Määritä seuraavat nimen ominaisuudet kaavarivillä:
   
   * **Väri**-ominaisuus = **DarkGray**

   * **Koko**-ominaisuus = **18**

   * **Teksti**-ominaisuus = ”**Napsauta tai napauta tehtävää ja jatka...”**
     
     ![Päivitä nimiteksti](./media/sharepoint-scenario-build-app/04-03-04-text-updated.png)

### <a name="add-two-navigation-buttons"></a>Lisää kaksi siirtymispainiketta
1. Napsauta tai napauta **Lisää**-välilehdessä **Painike** ja vedä sitten painike nimen alapuolelle.
   
    ![Lisää painike](./media/sharepoint-scenario-build-app/04-03-05-button-default.png)
2. Määritä seuraavat painikkeen ominaisuudet kaavarivillä:
   
   * **OnSelect**-ominaisuus = **Navigate(AssignManager, Fade)**. Kun suoritat sovelluksen ja napsautat tätä painiketta, siirryt sovelluksen seuraavaan näyttöön himmennettyjen siirtymien kautta.

   * **Teksti**-ominaisuus = **"Assign Manager"**

3. Muuta painikkeen kokoa tekstille sopivaksi.
   
    ![Päivitä-painikkeen teksti](./media/sharepoint-scenario-build-app/04-03-06-button-updated.png)
4. Lisää toinen painike, jossa on seuraavat ominaisuudet:
   
   * **OnSelect**-ominaisuus = **Navigate(ViewProjects, Fade)**.

   * **Teksti**-ominaisuus = **"Update Details"**
     
     ![Päivitä-painikkeen teksti](./media/sharepoint-scenario-build-app/04-03-08-buttons-final.png)
     
     > [!NOTE]
> Painikkeessa on nimi **Päivitä tiedot**, mutta siirrymme ensin **ViewProjects**-näyttöön valitsemaan päivitettävän projektin.

### <a name="run-the-app"></a>Sovelluksen suorittaminen
Sovelluksella ei voi vielä tehdä paljoakaan, mutta voit suorittaa sen halutessasi:

1. Napsauta tai napauta **SelectTask**-näyttöä (sovellus käynnistyy valitusta näytöstä esikatselutilassa PowerApps Studiossa).

2. Napsauta tai napauta ![Suorita sovellus -kuvaketta](./media/sharepoint-scenario-build-app/icon-run-arrow.png) oikeassa yläkulmassa suorittaaksesi sovelluksen.

3. Napsauta tai napauta jotakin painiketta, jotta voit siirtyä toiseen näyttöön.

4. Napsauta tai napauta ![Sulje sovelluksen esikatselu -kuvake](./media/sharepoint-scenario-build-app/icon-close-preview.png) oikeassa yläkulmassa sulkeaksesi sovelluksen.

## <a name="step-4-build-the-assignmanager-screen"></a>Vaihe 4: Rakenna AssignManager-näyttö
Tässä vaiheessa käytämme valikoimaa näyttämään kaikki projektit, jotka on hyväksytty, mutta joilla ei vielä ole esimiestä. Lisäämme muita ohjausobjekteja, jotta voit määrittää esimiehen.

> [!NOTE]
>  Luomme sovellukseen myöhemmin sivun, jossa voit muokata projektin kaikkia kenttiä (mukaan lukien esimiehen kenttää), mutta mielestämme olisi siistiä rakentaa myös tällainen näyttö.

1. Tallenna tähän mennessä tekemäsi muutokset.

2. Napsauta tai napauta vasemmassa siirtymispalkissa **AssignManager**-näyttöä.

### <a name="update-the-title-and-insert-introductory-text"></a>Päivitä otsikko ja lisää esittelyteksti

1. Muuta kohdan **[Otsikko]** arvoksi **Assign Manager**.

2. Lisää nimi käyttäen seuraavia ominaisuuksia:
   
   * **Väri**-ominaisuus = **DarkGray**

   * **Koko**-ominaisuus = **18**

   * **Teksti**-ominaisuus = "**Select a project, then assign a manager"**
     
     ![Määritä esimies -asettelu](./media/sharepoint-scenario-build-app/04-04-01-layout.png)

### <a name="add-a-back-arrow-to-return-to-the-selecttask-screen"></a>Lisää takaisin-nuoli, jolla palataan SelectTask-näyttöön

1. Napsauta tai napauta näytön yläreunassa olevaa sinistä palkkia.

2. Napsauta tai napauta **Lisää**-välilehdestä **Kuvakkeet** ja napsauta tai napauta sitten **Vasen**.
   
    ![Lisää vasen nuoli](./media/sharepoint-scenario-build-app/04-04-02-icon-left.png)

3. Siirrä nuoli sinisen palkin vasemmalle puolelle ja määritä seuraavat ominaisuudet:
   
   * **Väri**-ominaisuus = **White**

   * **Korkeus**-ominaisuus = **40**

   * **OnSelect**-ominaisuus = **Navigate(SelectTask, Fade)**

   * **Leveys**-ominaisuus = **40**
     
     ![Lisää takaisin-painike](./media/sharepoint-scenario-build-app/04-04-03-left-arrow.png)

### <a name="add-and-modify-a-gallery"></a>Lisää valikoima ja muokkaa sitä

1. Napsauta tai napauta **Lisää**-välilehdessä **Valikoima** ja sitten **Pysty**.
   
    ![Lisää pystysuuntainen valikoima](./media/sharepoint-scenario-build-app/04-04-04-gallery.png)

2. Valitse oikeanpuoleisessa ruudussa **Asettelu**-valikosta **Otsikko, alaotsikko ja leipäteksti**. 
   
    ![Muuta valikoiman asettelua](./media/sharepoint-scenario-build-app/04-04-04a-gallery-layout.png)
   
    Valikoimassa on nyt oikea asettelu, mutta siinä on yhä oletusarvoinen esimerkkiteksti. Korjataan se seuraavaksi.
   
    ![Valikoima, jossa on oletusteksti](./media/sharepoint-scenario-build-app/04-04-05-gallery-default.png)

3. Määritä seuraavat valikoiman ominaisuudet:
   
   * **BorderThickness**-ominaisuus = **1**

   * **BorderStyle**-ominaisuus = **Dotted**

   * **Kohteet**-ominaisuus = **Filter('Project Details', PMAssigned="Unassigned")**. Vain projektit, joille ei ole määritetty esimiestä, sisältyvät valikoimaan.
     
     ![Valikoima, jossa on tekstiä luettelosta](./media/sharepoint-scenario-build-app/04-04-06-gallery-updated.png)

4. Päivitä kentät oikeassa ruudussa vastaamaan seuraavaa luetteloa:
   
   * **ApprovedDate**

   * **Tila**

   * **Otsikko**
     
     ![Valikoimakentät](./media/sharepoint-scenario-build-app/04-04-07-gallery-fields.png)

5. Muuta soveltuvin osin valikoiman nimien kokoa ja poista nuoli ensimmäisestä valikoimakohteesta (emme joudu siirtymään pois tästä valikoimasta).
   
    ![Poista nuoli -kuvake](./media/sharepoint-scenario-build-app/04-04-07a-remove-arrow.png)
   
    Näytön pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![Muotoiltu valikoima](./media/sharepoint-scenario-build-app/04-04-07b-gallery-size-text.png)

### <a name="change-the-color-of-an-item-if-its-selected"></a>Muuta kohteen väriä, jos se on valittuna

1. Valitse valikoima ja määritä sitten **TemplateFill**-ominaisuuden arvoksi **If (ThisItem.IsSelected=true, Orange, White)**.

2. Valitse kohde valikoimassa. Näytön pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
   
    ![Valikoima, jossa on valittu kohde](./media/sharepoint-scenario-build-app/04-04-08-gallery-selected.png)

### <a name="add-a-label-text-input-and-ok-button-to-submit-manager-assignments"></a>Lisää nimi, tekstisyöte ja OK-painike, joilla lähetetään esimiestehtäviä

1. Napsauta tai napauta jotakin työstetyn valikoiman ulkopuolista kohtaa.

2. Napsauta tai napauta **Lisää**-välilehdessä **Nimi**. Vedä nimi vasemmalle valikoiman alle. Määritä seuraavat nimen ominaisuudet:
   
   * **Koko**-ominaisuus = **20**

   * **Teksti**-ominaisuus = **"Manager:"**
   
   ![Lisää esimies -otsikko](./media/sharepoint-scenario-build-app/04-04-09-controls-text.png)

3. Napsauta tai napauta **Lisää**-välilehdestä **Teksti** ja sitten **Tekstisyöte**. Vedä tekstisyöte keskelle, valikoiman alapuolelle. Määritä seuraavat avattavan luettelon ominaisuudet:
   
   * **Oletus**-ominaisuus = **""**

   * **Korkeus**-ominaisuus = **60**

   * **Koko**-ominaisuus = **20**

   * **Leveys**-ominaisuus = **250**
   
   ![Lisää tekstisyöte](./media/sharepoint-scenario-build-app/04-04-10-controls-text-box.png)

4. Napsauta tai napauta **Lisää**-välilehdessä **Painike**. Vedä painike oikealle valikoiman alle. Määritä seuraavat painikkeen ominaisuudet:
   
   * **Korkeus**-ominaisuus = **60**

   * **OnSelect**-ominaisuus = **Patch('Project Details', LookUp('Project Details', ID = Gallery1.Selected.ID), {PMAssigned: TextInput1.Text})**. Katso lisätietoja kohdasta [Kaavoja pintaa syvemmältä](#formula-deep-dive).

   * Tämä kaava päivittää **Projektitiedot**-luettelon asettaen arvon PMAssigned-kentälle.

   * **Koko**-ominaisuus = **20**

   * **Teksti**-ominaisuus = **"OK"**

   * **Leveys**-ominaisuus = **80**
   
   ![Lisää OK-painike](./media/sharepoint-scenario-build-app/04-04-11-controls-button.png)

Valmiin näytön pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.

![Valmis Määritä esimies -näyttö](./media/sharepoint-scenario-build-app/04-04-12-complete.png)

## <a name="step-5-build-the-viewprojects-screen"></a>Vaihe 5: Rakenna ViewProjects-näyttö
Tässä vaiheessa muutamme valikoiman ominaisuuksia **ViewProjects**-näytössä. Tämä valikoima näyttää kohteita **Projektitiedot**-luettelosta. Valitsemme kohteen tässä näytössä ja muokkaamme sitten tietoja **UpdateDetails**-näytössä.

1. Napsauta tai napauta vasemmassa siirtymispalkissa **ViewProjects**-näyttöä.

2. Muuta kohdan **[Otsikko]** arvoksi **”Näytä projektit”**.

3. Napsauta tai napauta vasemmassa siirtymispalkissa **ViewProjects**-näytön kohtaa **BrowserGallery1**.

4. Valitse oikeanpuoleisessa ruudussa **Asettelu**-valikosta **Otsikko, alaotsikko ja leipäteksti**. 
   
    ![Muuta valikoiman asettelua](./media/sharepoint-scenario-build-app/04-04-04a-gallery-layout.png)
   
    Valikoimassa on nyt oikea asettelu ja oletusarvoinen esimerkkiteksti.
   
    ![Valikoima, jossa on oletusteksti](./media/sharepoint-scenario-build-app/04-04-04b-gallery-default.png)

5. Valitse päivityspainikkeen ![Päivitä-kuvake](./media/sharepoint-scenario-build-app/icon-refresh.png) ja määritä sen **OnSelect**-ominaisuuden arvoksi **Refresh('Project Details')**.

6. Valitse uuden kohteen painike ![Lisää uusi kuvake](./media/sharepoint-scenario-build-app/icon-add-item.png) ja määritä sen **OnSelect**-ominaisuuden arvoksi **NewForm(EditForm1); Navigate(UpdateDetails, ScreenTransition.None)**.

### <a name="add-a-back-arrow-to-return-to-the-selecttask-screen"></a>Lisää takaisin-nuoli, jolla palataan SelectTask-näyttöön

1. Napsauta tai napauta vasemmassa siirtymispalkissa **AssignManager**-näyttöä.

2. Valitse lisätty takaisin-nuoli ja kopioi se.

3. Liitä nuoli **ViewProjects**-näyttöön ja sijoita se päivityspainikkeen vasemmalle puolelle. 
   
    ![Takaisin-painike](./media/sharepoint-scenario-build-app/04-05-04-left-arrow-v.png)
   
    Kaikki ominaisuudet tulevat sen mukana, mukaan lukien **OnSelect**-ominaisuuden **Navigate(SelectTask, Fade)**.

### <a name="change-the-data-source-for-the-browsegallery1-gallery"></a>BrowseGallery1-valikoiman tietolähteen muuttaminen

1. Valitse **BrowseGallery1**-valikoima ja määritä valikoiman **Kohteet**-ominaisuudeksi **SortByColumns(Filter('Project Details', StartsWith(Title, TextSearchBox1.Text)), "Title", If(SortDescending1, Descending, Ascending))**.
   
    Tämä asetus määrittää valikoiman tietolähteen **Projektitiedot**-luetteloon ja käyttää hakemiseen ja lajitteluun **Otsikko**-kenttää.

2. Valitse ![Tiedot-nuolikuvake](./media/sharepoint-scenario-build-app/icon-details-arrow.png) ensimmäisessä valikoiman kohteessa ja määritä **OnSelect**-ominaisuuden arvoksi **Navigate(UpdateDetails, None)**.
   
    ![ Näytä projektien valikoima – ensimmäinen kohde valittuna](./media/sharepoint-scenario-build-app/04-05-05b-gallery-arrow-v.png)

3. Päivitä kentät oikeassa ruudussa vastaamaan seuraavaa luetteloa:
   
   * **Tila**

   * **PMAssigned**

   * **Otsikko**
     
     ![Valikoimakentät](./media/sharepoint-scenario-build-app/04-05-06-gallery-fields.png)
     
     Valmiin näytön pitäisi nyt näyttää samalta kuin seuraavassa kuvassa.
     
     ![Näytä valmis projektinäyttö](./media/sharepoint-scenario-build-app/04-05-07-viewprojects-final.png)

## <a name="step-6-build-the-updatedetails-screen"></a>Vaihe 6: Rakenna UpdateDetails-näyttö
Tässä vaiheessa yhdistämme muokkauslomakkeen **UpdateDetails**-näytössä tietolähteeseen ja teemme joitakin ominaisuus- ja kenttämuutoksia. Tässä näytössä muokkaamme tietoja projektille, jonka valitsit **Näytä projektit** -näytössä.

1. Napsauta tai napauta vasemmassa siirtymispalkissa **UpdateDetails**-näyttöä.

2. Muuta **[Otsikko]**-arvoksi **”Päivitä tiedot”**.

3. Napsauta tai napauta vasemmassa siirtymispalkissa **UpdateDetails**-näytön alla olevaa kohtaa **EditForm1**.

4. Määritä lomakkeelle seuraavat ominaisuudet:
   
   * **DataSource**-ominaisuus = **'Project Details'**

   * **Kohde**-ominaisuus = **BrowseGallery1.Selected**

5. Kun lomake on edelleen valittuna, napsauta tai napauta oikeanpuoleisessa ruudussa olevaa seuraavien kenttien valintaruutua esitetyssä järjestyksessä:
   
   * **Otsikko**

   * **PMAssigned**

   * **Tila**

   * **ProjectedStartDate**

   * **ProjectedEndDate**

   * **ProjectedDays**

   * **ActualDays**
     
     ![Muokkaa lomakkeen kenttiä](./media/sharepoint-scenario-build-app/04-06-03-edit-fields.png)
6. Valitse Peruuta-painikkeen ![Peruuta kuvake](./media/sharepoint-scenario-build-app/icon-cancel.png) ja määritä sen **OnSelect** -ominaisuuden arvoksi **ResetForm(EditForm1); Back()**.

7. Valitse tallennuspainikkeen ![Valintamerkin tallennus -kuvake](./media/sharepoint-scenario-build-app/icon-check-mark.png) ja tarkista **OnSelect**-kaava **SubmitForm(EditForm1)**. Koska käytämme lomakkeen muokkausohjausobjektia, voimme käyttää **Submit()**:ia **Patch()**:n sijaan, kuten teimme aiemmin.

Valmiin näytön pitäisi nyt näyttää samanlaiselta kuin seuraavassa kuvassa (jos kentät ovat tyhjiä, varmista, että valitset kohteen **Näytä projektit** -näytössä).

![Päivitä tiedot -näyttö on valmis](./media/sharepoint-scenario-build-app/04-06-06-edit-final.png)

## <a name="step-7-run-the-app"></a>Vaihe 7: Sovelluksen suorittaminen
Nyt kun sovellus on valmis, suorita se, niin näet, miten se toimii. Lisäämme linkin sovellukseen SharePoint-sivustoon. Pystyt suorittamaan sovelluksen selaimessa, mutta joudut ehkä jakamaan sovelluksen, jotta muut käyttäjät voivat käyttää sitä. Lisätietoja on kohdassa [Jaa omat sovellukset](https://powerapps.microsoft.com/guided-learning/learning-manage-share-apps).

### <a name="add-a-link-to-the-app"></a>Linkin lisääminen sovellukseen
1. Napsauta tai napauta Office 365 -sovelluksen käynnistysohjelmassa **PowerApps**.
   
    ![PowerApps Office 365:n käynnistysohjelmassa](./media/sharepoint-scenario-build-app/04-07-02a-waffle.png)

2. Napsauta tai napauta PowerAppsissa **Projektinhallinta-sovelluksen** kolmea pistettä (**...** ) ja sitten **Avaa**.
   
    ![Valitse projektinhallintasovellus](./media/sharepoint-scenario-build-app/04-07-02b-select-app.png)

3. Kopioi sovelluksen osoite (URL) selaimeen.
   
    ![Sovelluksen URL-osoitteen kopioiminen](./media/sharepoint-scenario-build-app/04-07-02ba-copy-url.png)

4. Napsauta tai napauta SharePointissa **MUOKKAA LINKKEJÄ**.
   
    ![Muokkaa SharePoint-sivuston linkkejä](./media/sharepoint-scenario-build-app/04-07-02c-edit-links.png)

5. Napsauta tai napauta kohtaa **(+)-linkki**.
   
    ![Sovelluksen linkin lisääminen SharePoint-sivustoon](./media/sharepoint-scenario-build-app/04-07-02d-add-link.png)

6. Kirjoita ”Projektinhallintasovellus” ja liitä osoitteeseen sovellukselle.
   
    ![Linkin ominaisuuksien muokkaaminen](./media/sharepoint-scenario-build-app/04-07-02e-link-dialog.png)

7. Napsauta tai napauta **OK** ja sen jälkeen **Tallenna**.
   
    ![Tallenna linkin muutokset](./media/sharepoint-scenario-build-app/04-07-02f-save.png)

### <a name="assign-a-manager-to-a-project"></a>Määritä esimies projektiin
Nyt kun olemme lisänneet sovelluksen SharePoint-sivustoon, omaksumme projektin hyväksyjän roolin: etsimme projekteja, joille ei ole määritetty esimiestä, ja määritämme esimiehen yhdelle näistä projekteista. Omaksumme sitten projektipäällikön roolin ja lisäämme joitakin tietoja projektista, joka on määritetty meille.

1. Katsotaan ensin **Projektitiedot**-luetteloa SharePointissa. Kahdella projektilla on arvo **Määrittämätön** sarakkeessa **PMAssigned**. Näemme ne sovelluksessa.
   
    ![Määrittämättömät projektit SharePoint-luettelossa](./media/sharepoint-scenario-build-app/04-07-01-unassigned.png)

2. Napsauta tai napauta linkkiä, jonka loit sovellukselle.

3. Napsauta tai napauta ensimmäisessä näytössä **Määritä esimies**.
   
    ![Sovelluksen esittelynäyttö](./media/sharepoint-scenario-build-app/04-07-03-intro-screen.png)

4. **Määritä esimies** -näytössä näet kaksi määrittämätöntä projektia luettelossa. Valitse **Uusi BI-ohjelmisto** -projekti.
   
    ![Valikoima, jossa on valittu kohde](./media/sharepoint-scenario-build-app/04-07-04-selected.png)

5. Kirjoita **Esimies**-tekstisyötteeseen ”Joni Sherman” ja valitse **OK**.
   
    Luetteloon tehdään muutos, ja valikoima päivittyy, joten vain jäljellä olevat määrittämättömät projektit ovat näkyvissä.
   
    ![Esimiehen määrittäminen projektille](./media/sharepoint-scenario-build-app/04-07-05-updated.png)

6. Siirry takaisin SharePoint-luetteloon ja päivitä sivu. Näet, että projektimerkintään on nyt päivitetty projektipäällikön nimi.
   
    ![Projektipäällikkö määritettynä SharePoint-luettelossa](./media/sharepoint-scenario-build-app/04-07-07-assigned.png)

### <a name="update-details-for-the-project"></a>Päivitä projektin tiedot

1. Napsauta tai napauta ![takaisin-kuvaketta](./media/sharepoint-scenario-build-app/icon-back.png) siirtyäksesi takaisin ensimmäiseen näyttöön ja napsauta tai napauta sitten **Päivitä tiedot**.
   
   ![Sovelluksen esittelynäyttö](./media/sharepoint-scenario-build-app/04-07-08-intro-screen.png)

2. Kirjoita **Näytä projektit** -näytössä hakuruutuun ”Uusi”.
   
   ![Hae sovellusvalikoimassa](./media/sharepoint-scenario-build-app/04-07-09-search-new.png)

3. Valitse ![Tiedot-nuolikuvake](./media/sharepoint-scenario-build-app/icon-details-arrow.png) kohteelle **Uusi BI-ohjelmisto**.
   
   ![Valikoiman kohde valittuna](./media/sharepoint-scenario-build-app/04-07-10-select-project.png)

4. Määritä seuraavat arvot **Päivitä tiedot** -näytössä:
   
   * **Projektin aloituspäivämäärä** -kenttä = ”3/6/2017”

   * **Projektin lopetuspäivämäärä** -kenttä = ”3/24/2017”

   * **Ennakoidut päivät** -kenttä = ”15”
   
   ![Päivitä kohteen tiedot](./media/sharepoint-scenario-build-app/04-07-11-update.png)

5. Napsauta tai napauta ![valintamerkki-kuvaketta](./media/sharepoint-scenario-build-app/icon-check-mark.png) ottaaksesi muutoksen käyttöön SharePoint-luettelossa.

6. Sulje sovellus ja siirry takaisin luetteloon. Näet, että projektimerkintään on nyt päivitetty päivämäärä- ja päivämuutokset.
   
    ![Päivitetty SharePoint-luettelo](./media/sharepoint-scenario-build-app/04-07-11-updated-list.png)

## <a name="formula-deep-dive"></a>Kaavoja pintaa syvemmältä
Tämä on toinen valinnainen osa, jossa käsitellään PowerApps-kaavoja. Ensimmäisessä tutustuimme yhteen kaavoista, joita PowerApps luo selausvalikoimalle kolmen näytön sovelluksessa. Tässä syventävässä ohjeessa tarkastelemme kaavaa, jota käytämme toisen sovelluksen **AssignManager**-näytössä. Tässä on kaava:

**Patch ( 'Project Details', LookUp ( 'Project Details', ID = Gallery1.Selected.ID ), {PMAssigned: TextInput1.Text} )**

Mitä tämä kaava tekee? Kun valitset kohteen valikoimassa ja napsautat **OK**-painiketta, kaava päivittää **Projektitiedot**-luettelon asettaen **PMAssigned**-sarakkeen arvoon, jonka määritit tekstisyötteessä. Kaavassa käytetään funktioita sen tehtävien suorittamiseen:

* [**Patch**-funktio](functions/function-patch.md) muokkaa yhtä tai useampaa tietolähteen tietuetta.

* [**LookUp**-funktio](functions/function-filter-lookup.md) etsii taulukosta ensimmäisen tietueen, joka täyttää kaavan.

Kun yhdistelet funktioita kaavaan, tapahtuu seuraavaa:

1. Kun napsautat **OK**-painiketta, **Patch**-funktiota kutsutaan päivittämään **Projektitiedot**-luettelo.

2. **Patch**-funktiossa **LookUp**-funktio tunnistaa, mikä **Projektitiedot**-luettelon rivi päivitetään. Se tekee tämän vertaamalla valitun valikoiman kohteen tunnusta luettelon tunnukseen. Esimerkiksi tunnus 12 tarkoittaa, että **Uusi BI-ohjelmisto** -merkintää täytyy päivittää.

3. Nyt kun **Patch**-funktiolla on oikea tunnus, se päivittää **PMAssigned**-kentän arvoon kohdassa **TextInput1.Text**.

## <a name="next-steps"></a>Seuraavat vaiheet
Seuraava vaihe tässä opetusohjelmasarjassa on [luoda Power BI -raportti projektin analysoimista varten](sharepoint-scenario-build-report.md).

