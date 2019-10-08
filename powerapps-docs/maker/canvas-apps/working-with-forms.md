---
title: Pohjaan perustuvan sovelluksen lomakkeiden ymmärtäminen | Microsoft Docs
description: Lisää PowerAppsissa lomake pohjaan perustuvaan sovellukseen, jotta voit kerätä ja näyttää tietoa tietolähteestä.
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/27/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 401d32f3d3cacee4b9b1a23a5fceb7d159623086
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994918"
ms.PowerAppsDecimalTransform: true
---
# <a name="understand-canvas-app-forms-in-microsoft-powerapps"></a>Pohjaan perustuvan sovelluksen lomakkeiden ymmärtäminen Microsoft PowerAppsissa

Lisää pohjaan perustuvaan sovellukseen kolmentyyppisiä ohjausobjekteja, jotta käyttäjä voi selata tietueita, näyttää kyseisen tietueen tietoja ja luoda tietueen ja muokata sitä:

| Toiminta | Ohjausobjekti | Kuvaus |
| --- | --- | --- |
| **Selaa tietueita** |**[Valikoima](controls/control-gallery.md)** -ohjausobjekti |Suodata, lajittele, hae ja selaa tietueita tietolähteessä ja valitse haluttu tietue. Näytä vain muutama kenttä kustakin tietueesta, jotta näet useita tietueita kerralla pienessäkin näytössä. |
| **Tietueen tietojen näyttäminen** |**[Näytä lomake](controls/control-form-detail.md)** -ohjausobjekti |Näytä yhden tietueen useita kenttiä tai kaikki kentät. |
| **Tietueen luominen tai muokkaaminen** |**[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti |Päivitä yksittäisen tietueen yhtä tai useampaa kenttää (tai luo tietue alkaen oletusarvoista) ja tallenna nämä muutokset takaisin pohjana olevaan tietolähteeseen. |

Sijoita kukin ohjausobjekti erilliseen näyttöön, jotta ne on helpompi erottaa:

![Selaa, tarkastele ja muokkaa tietueita kolmessa näytössä](./media/working-with-forms/three-screens.png)

Kuten tässä ohjeaiheessa kuvataan, nämä ohjausobjektit voi yhdistää kaavojen kanssa yleisen käyttökokemuksen luomiseksi.

## <a name="prerequisites"></a>Edellytykset

* [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.
* Lue, miten [ohjausobjekti määritetään](add-configure-controls.md) PowerAppsissa.

## <a name="explore-a-generated-app"></a>Tutki luotua sovellusta
PowerApps voi luoda automaattisesti sovelluksen, joka perustuu määrittämääsi tietolähteeseen. Jokainen sovellus sisältää kolme näyttöä ja ohjausobjektit, jotka on kuvattu edellä, ja kaavoja, jotka yhdistävät ne. Suorita nämä valmiit sovellukset sellaisenaan, mukauta niitä omia tavoitteitasi varten tai tutki, miten ne toimivat, jotta opit hyödyllisiä käsitteitä, jotka koskevat omia sovelluksiasi. Seuraavissa kohdissa tarkastelemme näyttöjä, ohjausobjekteja ja kaavoja, jotka ohjaavat luotua sovellusta.  

### <a name="browse-screen"></a>Selaa-näyttö
![Selaa-näytön ohjausobjektit](./media/working-with-forms/afd-browse-screen-basic.png)

Tämä näyttö sisältää seuraavat keskeiset kaavat:

| Ohjausobjekti | Tuettu toiminta | Kaava |
| --- | --- | --- |
| **BrowseGallery1** |Näytä **Assets**-tietolähteen tietueet. |Valikoiman **[Kohteet](controls/properties-core.md)** -ominaisuuden asetuksena on kaava, joka perustuu **Assets**-tietolähteeseen. |
| **ImageNewItem1** |Näytä **Muokkaa ja Luo** -näyttö, jossa kunkin kentän arvona on oletusarvo, jotta käyttäjä voi helposti luoda tietueen. |Kuvan **[OnSelect](controls/properties-core.md)** -ominaisuudeksi on asetettu tämä kaava:<br> **NewForm( EditForm1 );;<br>Navigate( EditScreen1; None )** |
| **NextArrow1** (valikoimassa) |Näytä **Tiedot**-näyttö, jossa voit tarkastella tällä hetkellä valitun tietueen useita tai kaikkia kenttiä. |Nuolen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi on asetettu tämä kaava:<br>**Navigate( DetailScreen1; None )** |

Tämän näytön ensisijainen ohjausobjekti **BrowseGallery1** kattaa suurimman osan näytön alueesta. Käyttäjä voi selata valikoimaa, etsiä haluamansa tietueen ja näyttää tai päivittää lisää kenttiä.

Aseta **[Kohteet](controls/properties-core.md)** -ominaisuus ja näytä sen tietolähteen tietueita. Voit esimerkiksi määrittää ominaisuudeksi **Assets** ja näyttää tietueita tämännimisestä tietolähteestä.

> [!NOTE]
> Luodussa sovelluksessa **[Kohteet](controls/properties-core.md)** on määritetty huomattavasti monimutkaisemmaksi kaavaksi oletusarvoisesti, jotta käyttäjä voi lajitella ja etsiä tietueita. Opit rakentamaan kyseisen kaavan jäljempänä tässä ohjeaiheessa. Yksinkertaisempi versio riittää toistaiseksi.

Sen sijaan, että käyttäjä etsii tietueen, jota voi tarkastella tai muokata, hän voi luoda tietueen valitsemalla valikoiman yläpuolelta +-merkin. Luo tämä tehoste lisäämällä **[Kuva](controls/control-image.md)** -ohjausobjekti, jossa näkyy +-merkki, ja määrittämällä sen **[OnSelect](controls/properties-core.md)** -ominaisuuden arvoksi tämä kaava:
<br>**NewForm( EditForm1 );; Navigate( EditScreen1; None )**

Tämä kaava avaa **Muokkaa ja Luo** -näytön, jossa on **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti nimeltä **EditForm1**. Kaava vaihtaa myös kyseisen lomakkeen **Uusi**-tilaan, jossa lomake näyttää oletusarvot tietolähteestä, jotta käyttäjä voi helposti luoda tietueen alusta.

Voit tutkia **BrowseGallery1**:ssä näkyvää ohjausobjektia valitsemalla ohjausobjektin valikoiman ensimmäisestä osiosta, joka toimii mallina muille osioille. Valitse esimerkiksi keskimmäinen **[Nimi](controls/control-text-box.md)** -ohjausobjekti vasemmassa reunassa:

![Selaa-näytön ohjausobjektit](./media/working-with-forms/afd-browse-gallery-controls.png)

Tässä esimerkissä ohjausobjektin **[Teksti](controls/properties-core.md)** -ominaisuutena on **ThisItem.AssignedTo**, joka on kenttä **Assets**-tietolähteessä. Valikoiman kolmen muun **[Nimi](controls/control-text-box.md)** -ohjausobjektin **[Teksti](controls/properties-core.md)** -ominaisuudeksi määritetään samankaltaiset kaavat, ja kukin ohjausobjekti näyttää eri kentän tietolähteessä.  

Valitse **[Muoto](controls/control-shapes-icons.md)** -ohjausobjekti (nuoli) ja varmista, että sen **[OnSelect](controls/properties-core.md)** -ominaisuuden arvona on tämä kaava:
<br>**Navigate( DetailScreen1; None )**

Jos käyttäjä löytää tietueen **BrowseGallery1**:ssä, hän voi valita tietueen nuolen ja näyttää lisätietoja siitä **DetailScreen1**-kohdassa. Valitsemalla nuolen käyttäjä muuttaa **BrowseGallery1**:n **Valittu**-ominaisuuden arvon. Tässä sovelluksessa kyseinen ominaisuus määrittää, mikä tietue näkyy **DetailScreen1**-kohdassa sekä, jos käyttäjä päättää päivittää tietuetta, **Muokkaa ja Luo** -näytössä.

### <a name="detail-screen"></a>Lisätiedot-näyttö
![Lisätiedot-näytön ohjausobjektit](./media/working-with-forms/afd-detail-screen-basic.png)

Tämä näyttö sisältää seuraavat keskeiset kaavat:

| Ohjausobjekti | Tuettu toiminta | Kaava |
| --- | --- | --- |
| **DetailForm1** |Näyttää tietueen **Assets**-tietolähteessä |Määritä **[DataSource](controls/control-form-detail.md)** -ominaisuuden arvoksi **Assets**. |
| **DetailForm1** |Määrittää, mikä tietue näytetään. Luodussa sovelluksessa näkyy tietue, jonka käyttäjä valitsi valikoimassa. |Määritä tämän ohjausobjektin **[Kohde](controls/control-form-detail.md)** -ominaisuudeksi tämä arvo:<br>**BrowseGallery1.Selected** |
| **[Kortti](controls/control-card.md)** -ohjausobjektit |Näyttää **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjektissa yhden kentän tietueessa. |Määritä **[DataField](controls/control-card.md)** -ominaisuuden arvoksi kentän nimi lainausmerkeissä (esimerkiksi **"Nimi"** ). |
| **ImageBackArrow1** |Kun käyttäjä valitsee tämän ohjausobjektin, **BrowseScreen1** avautuu. |Määritä **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>**Back()** |
| **ImageDelete1** |Kun käyttäjä valitsee tämän ohjausobjektin, tietue poistetaan. |Määritä **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>**Remove( Assets; BrowseGallery1.Selected )** |
| **ImageEdit1** |Kun käyttäjä valitsee tämän ohjausobjektin, **Muokkaa ja Luo** -näyttö avautuu nykyiseen tietueeseen. |Määritä **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>**Navigate( EditScreen1; None )** |

Näytön yläreunassa on **DetailForm1**-kohdan ulkopuolella kolme kuvaa, jotka toimivat painikkeina halliten sovelluksen kolmea näyttöä.

**DetailForm1** hallitsee tätä näyttöä ja näyttää tietueen, jonka käyttäjä valitsi valikoimassa (koska lomakkeen **[Kohde](controls/control-form-detail.md)** -ominaisuuden arvona on **BrowseGallery1.Selected**). Lomakkeen **[DataSource](controls/control-form-detail.md)** -ominaisuus tarjoaa myös metatietoja tietolähteestä, kuten käyttäjäystävällisen näyttönimen kullekin kentälle.

**DetailForm1** sisältää useita **[Kortti](controls/control-card.md)** -ohjausobjekteja. Voit valita joko itse **[Kortti](controls/control-card.md)** -ohjausobjektin tai sen sisältämän ohjausobjektin ja nähdä lisätietoja.

![Lisätiedot-kortti ja kortin ohjausobjektit valittuna muokkaustilassa](./media/working-with-forms/afd-detail-card-controls.png)

**[Kortti](controls/control-card.md)** -ohjausobjektin **[DataField](controls/control-card.md)** -ominaisuus määrittää, mitä kenttiä kortti näyttää. Tässä tapauksessa ominaisuuden arvona on **AssetID**. Kortti sisältää **[Nimi](controls/control-text-box.md)** -ohjausobjektin, jonka **[Teksti](controls/properties-core.md)** -ominaisuutena on **Parent.Default**. Tämä ohjausobjekti näyttää kortin **oletus**arvon, joka on määritetty **[DataField](controls/control-card.md)** -ominaisuuden kautta.

Luodussa sovelluksessa **[Kortti](controls/control-card.md)** -ohjausobjektit on oletusarvoisesti lukittu. Kun kortti on lukittu, et voi muokata joitakin ominaisuuksia, kuten **[DataField](controls/control-card.md)** , eikä kaavarivi ole näiden ominaisuuksien osalta käytettävissä. Tämä rajoitus auttaa varmistamaan, että mukautukset eivät riko luodun sovelluksen perustoimintoja. Voit kuitenkin muuttaa joitakin kortin ominaisuuksia ja sen ohjausobjekteja oikeanpuoleisessa ruudussa:

![Lisätiedot-näyttö ja Asetukset-ruutu avattuna](./media/working-with-forms/detail-screen-new.png)

Oikeanpuoleisessa ruudussa voit valita näytettävät kentät ja millaisessa ohjausobjektissa kukin kenttä näytetään.

### <a name="editcreate-screen"></a>Muokkaus-/luontinäyttö
![Muokkausnäytön ohjausobjektit](./media/working-with-forms/afd-edit-screen-basic.png)

Tämä näyttö sisältää seuraavat keskeiset kaavat:

| Ohjausobjekti | Tuettu toiminta | Kaava |
| --- | --- | --- |
| **EditForm1** |Näyttää tietueen **Assets**-tietolähteessä. |Määritä **[DataSource](controls/control-form-detail.md)** -ominaisuuden arvoksi **Assets**. |
| **EditForm1** |Määrittää, mikä tietue näytetään. Luodussa sovelluksessa näkyy tietue, jonka käyttäjä valitsi **BrowseScreen1**:ssä. |Määritä **[Kohde](controls/control-form-detail.md)** -ominaisuudeksi tämä arvo:<br>**BrowseGallery1.Selected** |
| **[Kortti](controls/control-card.md)** -ohjausobjektit |**[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti sisältää ohjausobjekteja, jotta käyttäjä voi muokata yhtä tai useampaa tietueen kenttää. |Määritä **[DataField](controls/control-card.md)** -ominaisuuden arvoksi kentän nimi lainausmerkeissä (esimerkiksi **"Nimi"** ). |
| **ImageCancel1** |Kun käyttäjä valitsee tämän ohjausobjektin, meneillään olevat muutokset hylätään, ja **Tiedot**-näyttö avautuu. |Määritä **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>**ResetForm( EditForm1 );; Back()** |
| **ImageAccept1** |Kun käyttäjä valitsee tämän ohjausobjektin, muutokset lähetetään tietolähteeseen. |Määritä **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>**SubmitForm( EditForm1 )** |
| **EditForm1** |Jos muutokset hyväksytään, edellinen näyttö avautuu. |Määritä **[OnSuccess](controls/control-form-detail.md)** -ominaisuudeksi tämä kaava:<br>**Back()** |
| **EditForm1** |Jos muutoksia ei hyväksytä, nykyinen näyttö pysyy avoinna, jotta käyttäjä voi korjata mahdolliset ongelmat, ja yrittää lähettää uudelleen. |Jätä **[OnFailure](controls/control-form-detail.md)** -ominaisuus tyhjäksi. |
| **LblFormError1** |Jos muutoksia ei hyväksytä, näyttää virhesanoman. |Aseta **[Teksti](controls/properties-core.md)** -ominaisuudeksi tämä arvo:<br>**EditForm1.Error** |

Kuten **Tiedot**-näytössä, lomakkeen ohjausobjekti nimeltä **EditForm1** hallitsee **Muokkaa ja Luo** -näyttöä. Lisäksi **EditForm1**:n **[Kohde](controls/control-form-detail.md)** -ominaisuutena on **BrowseGallery1.Selected**, jolloin lomake näyttää tietueen, jonka käyttäjä valitsi **BrowseScreen1**:ssä. Vaikka **Tiedot**-näytössä näytetään kentät vain luku -muodossa, käyttäjä voi päivittää yhden tai useamman kentän arvon kohdan **EditForm1** ohjausobjekteilla. Se myös käyttää **[DataSource](controls/control-form-detail.md)** -ominaisuutta tämän tietolähteen metatietojen, kuten kunkin kentän käyttäjäystävällisen näyttönimen sekä muutosten tallennussijainnin, hankkimiseen.

Jos käyttäjä peruuttaa päivityksen valitsemalla X-kuvakkeen, **[ResetForm](functions/function-form.md)** -funktio hylkää kaikki tallentamattomat muutokset ja **[Back](functions/function-navigate.md)** -funktio avaa **Tiedot**-näytön. Sekä **Tiedot**- että **Muokkaa ja luo** -näytöt näyttävät saman tietueen, kunnes käyttäjä valitsee jonkin muun **BrowseScreen1**:ssä. Kyseisen tietueen kentät säilyttävät arvot, jotka viimeksi tallennettiin, mutta ei mitään käyttäjän tekemiä ja hylkäämiä muutoksia.

Jos käyttäjä muuttaa lomakkeen yhden tai useamman arvon ja valitsee sitten valintamerkki-kuvakkeen, **[SubmitForm](functions/function-form.md)** -funktio lähettää käyttäjän tekemät muutokset tietolähteeseen.

* Jos muutokset tallennetaan, lomakkeen **[OnSuccess](controls/control-form-detail.md)** -kaava suoritetaan, ja **Back()** -funktio avaa Tiedot-näytön, jossa näkyy päivitetty tietue.
* Jos muutosten tallentaminen ei onnistu, lomakkeen **[OnFailure](controls/control-form-detail.md)** -kaava suoritetaan, mutta se ei muuta mitään, koska se on *tyhjä*. **Muokkaa ja luo** -näyttö pysyy avoimena, jotta käyttäjä voi joko peruuttaa muutokset tai korjata virheen. **LblFormError1** näyttää käyttäjäystävällisen virheviestin, johon lomakkeen **Virhe**-ominaisuus määritetään.

Kuten **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjekti, **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti sisältää **[Kortti](controls/control-card.md)** -ohjausobjekteja, jotka sisältävät muita ohjausobjekteja, jotka näyttävät eri kenttiä tietueessa:

![Muokkaa-kortti ja kortin ohjausobjektit valittuna muokkaustilassa](./media/working-with-forms/afd-edit-card-controls.png)

Edellisessä kuvassa valittu kortti näyttää **AssetID**-kentän ja sisältää **[Tekstisyöte](controls/control-text-input.md)** -ohjausobjektin, jotta käyttäjä voi muokata kentän arvoa. (Tiedot-näytössä näkyy sen sijaan sama kenttä **[Nimi](controls/control-text-box.md)** -ohjausobjektissa, joka on vain luku -tilassa.) **[Tekstisyöte](controls/control-text-input.md)** -ohjausobjektilla on **[Oletus](controls/properties-core.md)** -ominaisuus, jonka arvo on **Parent.Default**. Jos käyttäjä loi tietuetta sen muokkaamisen sijaan, tässä ohjausobjektissa näkyisi alkuarvo, jonka käyttäjä voi muuttaa uudelle tietueelle.

Oikeanpuoleisessa ruudussa voit näyttää tai piilottaa kunkin kortin, järjestää ne uudelleen tai määrittää ne näyttämään kenttiä erityyppisissä ohjausobjekteissa.

![Muokkaa-näyttö ja Asetukset-ruutu avattuna](./media/working-with-forms/edit-screen.png)

## <a name="build-an-app-from-scratch"></a>Luo sovellus alusta alkaen
Tutustumalla tapaan, jolla PowerApps luo sovelluksen, voit itse luoda sovelluksen, joka käyttää samoja rakenneosia ja kaavoja, joita käsittelimme aiemmin tässä ohjeaiheessa.

## <a name="identify-test-data"></a>Tunnista testitiedot
Saat parhaan edun tästä ohjeaiheesta aloittamalla tietolähteellä, jolla voit tehdä kokeiluja. Sen täytyy sisältää testitiedot, joita voit huoletta lukea ja päivittää.

> [!NOTE]
> Jos käytät SharePoint-luetteloa tai Excel-taulukkoa, joka sisältää sarakkeiden nimiä ja välilyöntejä tietolähteenä, PowerApps korvaa välilyönnit merkinnällä **”\_x0020\_”** . Esimerkiksi **"Sarakkeen Nimi"** SharePointissa tai Excelissä näkyy muodossa **"Sarakkeen_x0020_Nimi"** PowerAppsissa, kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.

Jotta voit tarkalleen noudattaa tämän ohjeaiheen loppuosaa, luo SharePoint-luettelo nimeltä ”Ice Cream”, joka sisältää nämä tiedot:

![Ice cream -SharePoint-luettelo](./media/working-with-forms/sharepointlist-icecream.png)

* Luo puhelinsovellus alusta ja [yhdistä se tietolähteeseen](add-data-connection.md).
  
    > [!NOTE]
  > Tablettisovellukset ovat hyvin samankaltaisia, mutta haluat ehkä erilaisen [näyttöasettelun](#screen-design), jotta voit käyttää hyväksesi ylimääräisen näyttötilan.
  
    Ohjeaiheen loppuosan esimerkit perustuvat tietolähteeseen nimeltä **Ice Cream**.

## <a name="browse-records"></a>Selaa tietueita
Hanki tietoyksikkö nopeasti tietueesta etsimällä se valikoimasta Selaa-näytössä.

1. Lisää **pystysuuntainen** valikoima ja muuta asetteluksi vain **Otsikko**.
   
    ![Valikoima yhdistettynä Ice Cream -tietolähteeseen](./media/working-with-forms/new-gallery.png)
2. Määritä valikoiman **[Kohteet](controls/properties-core.md)** -ominaisuudeksi **Ice Cream**.
3. Määritä valikoiman ensimmäisen nimen **[Teksti](controls/properties-core.md)** -ominaisuudeksi **ThisItem.Title**, jos siinä on jokin muu arvo.
   
    Nimi näyttää nyt arvon kunkin tietueen **Otsikko**-kentässä.
   
    ![Valikoima yhdistettynä Ice Cream -tietolähteeseen](./media/working-with-forms/new-gallery-2.png)
4. Muuta valikoiman kokoa, jotta se täyttää näytön, ja määritä sen **[TemplateSize](controls/control-gallery.md)** -ominaisuudeksi **60**.
   
    Näyttö muistuttaa tätä esimerkkiä, jossa näkyvät kaikki tietolähteen tietueet:
   
    ![Valikoima yhdistettynä Ice Cream -tietolähteeseen](./media/working-with-forms/new-gallery-icecream.png)

## <a name="view-details"></a>Näytä tiedot
Jos valikoimassa ei näy haluamiasi tietoja, avaa Tiedot-näyttö valitsemalla tietueen nuoli. Näytön **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjektissa näkyy enemmän kenttiä ja mahdollisesti kaikki kentät valitsemallesi tietueelle.

**[Näytä lomake](controls/control-form-detail.md)** -ohjausobjekti näyttää tietueen kahden ominaisuuden avulla:

* **[DataSource](controls/control-form-detail.md)** -ominaisuus.  Sen tietolähteen nimi, joka sisältää tietueen. Tämä ominaisuus täyttää oikeanpuoleisen paneelin kentät ja määrittää kunkin kentän näyttönimen ja tietotyypin (merkkijono, luku, päivämäärä jne.).  
* **[Kohde](controls/control-form-detail.md)** -ominaisuus.  Näytettävä tietue.  Tämä ominaisuus yhdistetään usein  **[valikoiman](controls/control-gallery.md)** **Valittu**-ominaisuuteen, jotta käyttäjä voi valita tietueen **[valikoimasta](controls/control-gallery.md)** ja porautua tietueeseen.

Kun **[DataSource](controls/control-form-detail.md)** -ominaisuus määritetään, voit lisätä ja poistaa kenttiä oikeanpuoleisen ruudun kautta ja muuttaa tapaa, jolla ne näytetään.

Tässä näytössä käyttäjät eivät voi tarkoituksella tai vahingossa muuttaa tietueen mitä tahansa arvoja. **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjekti on vain luku -ohjausobjekti, joten se ei muokkaa tietuetta.

**[Näytä lomake](controls/control-form-detail.md)** -ohjausobjektin lisääminen:

1. Lisää näyttö ja lisää siihen sitten **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjekti
2. Määritä lomakkeen ohjausobjektin **[DataSource](controls/control-form-detail.md)** -ominaisuudeksi **Ice Cream**.

Oikeanpuoleisessa ruudussa voit valita näytössä näytettävät kentät ja kussakin kentässä näytettävän korttityypin. Kun teet muutoksia oikeanpuoleisessa ruudussa, kunkin **[Kortti](controls/control-card.md)** -ohjausobjektin **[DataField](controls/control-card.md)** -ominaisuus määritetään kenttään, jota käyttäjä käyttää. Näytön pitäisi näyttää samalta kuin tässä esimerkissä:

![Näytetty lomake Ice Cream -tietolähteelle](./media/working-with-forms/ice-cream-new.png)

Lopuksi joudumme yhdistämään **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjektin **[valikoimaan](controls/control-gallery.md)** , jotta voimme tarkastella tietyn tietueen tietoja.  Heti, kun olemme määrittäneet **[Kohde](controls/control-form-detail.md)** -ominaisuuden, valikoiman ensimmäinen tietue näkyy lomakkeessamme.

* Määritä **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjektin **[Kohde](controls/control-form-detail.md)** -ominaisuudeksi **Gallery1.Selected**.
   
    Valitun kohteen tiedot näkyvät lomakkeessa.
   
    ![Ice Cream -tietolähteen näytetty lomake yhdistettynä valikoiman ohjausobjektiin](./media/working-with-forms/view-form-select-coconut.png)

Hienoa!  Tutustumme nyt siirtymiseen: tapaan, jolla käyttäjä avaa Tiedot-näytön Valikoima-näytöstä ja Valikoima-näytön Tiedot-näytöstä.

* Lisää **[Painike](controls/control-button.md)** -ohjausobjekti näyttöön, määritä sen **[Teksti](controls/properties-core.md)** -ominaisuus näyttämään **[Takaisin](functions/function-navigate.md)** ja määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi **Back()** .
   
    Tämä kaava palauttaa käyttäjän takaisin valikoimaan, kun hän lopettaa tietojen tarkastelemisen.

    ![Ice Cream -tietolähteen näytetty lomake ja Takaisin-painike](./media/working-with-forms/viewform-icecream-back.png)

Palataan seuraavaksi **[Valikoima](controls/control-gallery.md)** -ohjausobjektiin ja lisätään joitakin siirtymisosia Tiedot-näyttöön.

1. Siirry ensimmäiseen näyttöön, joka isännöi **[Valikoima](controls/control-gallery.md)** -ohjausobjektia, ja valitse valikoiman ensimmäisen kohteen nuoli.

2. Määritä muodon **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:
   <br>**Navigate( Screen2; None )**
   
    ![Ice Cream -tietolähteen näytetty lomake ja Takaisin-painike](./media/working-with-forms/gallery-icecream-nav-new.png)

3. Paina F5-näppäintä ja näytä sitten kohteen tiedot valitsemalla nuolen valikoimassa.

4. Palaa tuotevalikoimaan valitsemalla **[Takaisin](functions/function-navigate.md)** ja paina sitten Esc-näppäintä.

## <a name="editing-details"></a>Tietojen muokkaaminen
Viimeinen keskeinen tehtävämme on tietueen sisällön muuttaminen. Käyttäjät tekevät tämän **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektissa.

**[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti näyttää tietueen ja muokkaa sitä kahden ominaisuuden avulla:

* **[DataSource](controls/control-form-detail.md)** -ominaisuus.  Tietueen sisältävän tietolähteen nimi.  Kuten **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjekti, tämä ominaisuus täyttää oikeanpuoleisen paneelin kentät ja määrittää kunkin kentän näyttönimen ja tietotyypin (merkkijono, luku, päivämäärä jne.). Tämä ominaisuus määrittää myös, onko kunkin kentän arvo kelvollinen ennen sen lähettämistä pohjana olevaan tietolähteeseen.
* **[Kohde](controls/control-form-detail.md)** -ominaisuus.  Muokattava tietue, joka yhdistetään usein **[Valikoima](controls/control-gallery.md)** -ohjausobjektin **Valittu**-ominaisuuteen. Tällä tavalla voit valita tietueen **[Valikoima](controls/control-gallery.md)** -ohjausobjektissa, näyttää sen Tiedot-näytössä ja muokata sitä **Muokkaa ja luo** -näytössä.

Lisää **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti:

1. Lisää näyttö ja **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjekti. Aseta sitten lomakkeen **[DataSource](controls/control-form-detail.md)** -ominaisuuden arvoksi **'Ice Cream'** .
2. Määritä **[Kohde](controls/control-form-detail.md)** -ominaisuudeksi **Gallery1.Selected**.

Voit nyt valita näytössä näytettävät kentät. Voit myös valita korttityypin, joka näytetään kullekin kentälle. Kun teet muutoksia oikeanpuoleisessa ruudussa, kunkin **[Kortti](controls/control-card.md)** -ohjausobjektin **[DataField](controls/control-card.md)** -ominaisuus määritetään kenttään, jota käyttäjä käyttää.  Näytön pitäisi näyttää samalta kuin tässä esimerkissä:

![Näytetty lomake Ice Cream -tietolähteelle](./media/working-with-forms/icecream-edit.png)

Nämä kaksi ominaisuutta ovat samat kuin **[Näytä lomake](controls/control-form-detail.md)** -ohjausobjektin ominaisuudet.  Ja pelkästään näiden avulla voimme näyttää tietueen tiedot.  

**[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektissa on lisäksi **[SubmitForm](functions/function-form.md)** -funktio, joka kirjoittaa muutokset takaisin tietolähteeseen. Sitä käytetään painikkeen tai kuvan ohjausobjektilla tallentamaan käyttäjän muutokset.

* Lisää **[Painike](controls/control-button.md)** -ohjausobjekti, määritä sen **[Teksti](controls/properties-core.md)** -ominaisuus näyttämään **Tallenna** ja määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>
  **SubmitForm( Form1 )**

![Muokattu lomake Ice Cream -tietolähteelle](./media/working-with-forms/edit-icecream-save.png)

Lisää siirtyminen tähän näyttöön ja tästä näytössä näin:

1. Lisää toinen **[Painike](controls/control-button.md)** -ohjausobjekti, määritä sen **[Teksti](controls/properties-core.md)** -ominaisuus näyttämään **Peruuta** ja määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava: <br>**ResetForm( Form1 );; Back()**
   
    Tämä kaava hylkää kaikki tallentamattomat muokkaukset ja avaa edellisen näytön.
   
    ![Näytetty lomake Ice Cream -tietolähteelle](./media/working-with-forms/edit-icecream-cancel.png)
2. Määritä lomakkeen **[OnSuccess](controls/control-form-detail.md)** -ominaisuudeksi **Back()** .
   
    Kun päivitykset on tallennettu, edellinen näyttö (tässä tapauksessa Tiedot-näyttö) avautuu automaattisesti.
   
    ![Muokattu lomake ja lisätty OnSuccess-sääntö](./media/working-with-forms/edit-icecream-onsuccess.png)
3. Lisää **Näyttö**-ohjausobjekti, lisää painike, määritä sen **[Teksti](controls/properties-core.md)** -ominaisuus näyttämään **Muokkaa** ja määritä sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br> **Navigate( Screen3; None )**
   
    ![Näytetty lomake ja lisätty muokkauspainike](./media/working-with-forms/viewform-icecream-edit.png)

Olet laatinut perussovelluksen, jossa on kolme näyttöä tietojen tarkasteluun ja syöttämiseen.  Voit kokeilla sitä näyttämällä valikoimanäytön ja painamalla sitten F5-näppäintä (tai valitse eteenpäin osoittavan nuolen Esikatselu-painike näytön vasemman yläkulman lähellä). Vaaleanpunainen piste ilmaisee kohdan, jossa käyttäjä napsauttaa tai napauttaa näyttöä kussakin vaiheessa.

![Kokeile ice cream -sovellusta](./media/working-with-forms/try-icecream.png)

## <a name="create-a-record"></a>Tietueen luominen
Käyttäjä käyttää samaa **muokattua** lomaketta sekä päivittäessään että luodessaan tietueita. Kun käyttäjä haluaa luoda tietueen, **[NewForm](functions/function-form.md)** -funktio vaihtaa lomakkeen **Uusi**-tilaan.

Kun lomake on **Uusi**-tilassa, kunkin kentän arvoksi määritetään tietolähteen oletusarvot. Tietue, joka annetaan lomakkeen **[Kohde](controls/control-form-detail.md)** -ominaisuudelle, ohitetaan.  

Kun käyttäjä on valmis tallentamaan uuden tietueen, **[SubmitForm](functions/function-form.md)** suoritetaan. Kun lomakkeen lähettäminen on onnistunut, lomake siirtyy takaisin **EditMode**-tilaan.  

Ensimmäisessä näytössä lisätään **Uusi**-painike:

1. Valikoiman näytössä lisätään **[Painike](controls/control-button.md)** -ohjausobjekti.
2. Aseta painikkeen **[Teksti](controls/properties-core.md)** -ominaisuudeksi **Uusi** ja sen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>
   **NewForm( Form1 );; Navigate( Screen3; None )**
   
    Tämä kaava vaihtaa **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektin **Screen3**:ssa **Uusi**-tilaan ja avaa kyseisen näytön, jotta käyttäjä voi täyttää sen tietoja.

![Näytetty lomake ja lisätty muokkauspainike](./media/working-with-forms/gallery-icecream-new.png)

Kun Muokkaa ja luo -näyttö avautuu, lomake on tyhjä ja valmis sitä varten, että käyttäjä voi lisätä kohteen siihen. Kun käyttäjä valitsee **Tallenna**-painikkeen, **[SubmitForm](functions/function-form.md)** -funktio varmistaa, että tietue luodaan sen päivittämisen sijaan. Jos käyttäjä valitsee **Peruuta**-painikkeen, **[ResetForm](functions/function-form.md)** -funktio vaihtaa lomakkeen takaisin **Muokkaa**-tilaan ja **[Takaisin](functions/function-navigate.md)** -funktio avaa näytön valikoimassa selaamista varten.

## <a name="delete-a-record"></a>Tietueen poistaminen
1. Lisää **Näyttö**-näytössä painike ja määritä sen **[Teksti](controls/properties-core.md)** -ominaisuus näyttämään **Poista**.
2. Määritä painikkeen **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:
   <br>**Remove( 'Ice Cream'; Gallery1.Selected );; Back()**
   
    ![Näytetty lomake ja lisätty muokkauspainike](./media/working-with-forms/viewform-icecream-remove.png)

## <a name="handling-errors"></a>Virheiden käsittely
Tässä sovelluksessa ilmenee virhe, kun kentän arvo ei ole kelvollinen, pakollinen kenttä on tyhjä, verkkoyhteys katkeaa tai joitain muita ongelmia ilmenee.  

Jos **[SubmitForm](functions/function-form.md)** epäonnistuu jostakin syystä, **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektin **Virhe**-ominaisuus sisältää virhesanoman, joka näytetään käyttäjälle. Näiden tietojen avulla käyttäjän pitäisi pystyä korjaamaan ongelma ja lähettämään muutos uudelleen, tai hän voi peruuttaa päivityksen.

1. Lisää Muokkaa ja luo -näytössä **[Nimi](controls/control-text-box.md)** -ohjausobjekti ja siirrä se suoraan **Tallenna**-painikkeen alapuolelle. Virhe on helppo nähdä, kun käyttäjä valitsee tämän ohjausobjektin tallentaessaan muutoksia.

2. Määritä **[Nimi](controls/control-text-box.md)** -ohjausobjektin **[Teksti](controls/properties-core.md)** -ominaisuus näyttämään **Form1.Error**.

    ![Näytetty lomake ja lisätty muokkauspainike](./media/working-with-forms/edit-icecream-error.png)

Sovelluksessa, jonka PowerApps luo tiedoista, tämän ohjausobjektin **[AutoHeight](controls/control-text-box.md)** -ominaisuuden arvo on *true*, jotta tilaa ei käytetä, jos virheitä ei ilmene. **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektin **[Korkeus](controls/properties-size-location.md)** - ja **[Y](controls/properties-size-location.md)** -ominaisuuksia myös mukautetaan dynaamisesti, jotta tämä ohjausobjekti otetaan huomioon virheen tapahtuessa. Saat lisätietoja luomalla sovelluksen aiemmin luoduista tiedoista ja tarkastelemalla näitä ominaisuuksia. Virheiden tekstiruutu -ohjausobjekti on hyvin lyhyt, kun virheitä ei ole sattunut. Joudut ehkä avaamaan **Lisäasetukset**-näkymän (käytettävissä **Näkymä**-välilehdessä), jotta voit valita tämän ohjausobjektin.

![Sovellus tiedoista -muokkauslomake ja virhetekstin ohjausobjekti valittuna](./media/working-with-forms/edit-assets-error1.png)

![Sovellus tiedoista -muokkauslomake ja lomakkeen ohjausobjekti valittuna](./media/working-with-forms/edit-assets-error2.png)

## <a name="refresh-data"></a>Päivitä tiedot
Tietolähde päivitetään aina, kun käyttäjä avaa sovelluksen, mutta tietueet voidaan halutessa päivittää valikoimassa sulkematta sovellusta. Lisää **Päivitä**-painike, jotta käyttäjä voi valita sen ja manuaalisesti päivittää tiedot:

1. Lisää näyttöön, jossa on **[Valikoima](controls/control-gallery.md)** -ohjausobjekti, **[Painike](controls/control-button.md)** -ohjausobjekti. Määritä sen **[Teksti](controls/properties-core.md)** -ominaisuus näyttämään **Päivitä**.

2. Määritä tämän ohjausobjektin **[OnSelect](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br> **Refresh( 'Ice Cream' )**

    ![Päivitä tietolähde](./media/working-with-forms/browse-icecream-refresh.png)

## <a name="search-and-sort-the-gallery"></a>Valikoiman haku ja lajittelu
Sovelluksessa, jonka PowerApps loi tiedoista, on Selaa-näytön yläosassa kaksi ohjausobjektia, joista emme ole vielä puhuneet. Näiden ohjausobjektien avulla käyttäjä voi hakea yhtä tai useampaa tietuetta ja lajitella luetteloa nousevaan tai laskevaan järjestykseen.

![Lajittelun ja haun ohjausobjektit Selaa-näytössä](./media/working-with-forms/afd-browse-search-sort.png)

Kun käyttäjä valitsee lajittelupainikkeen, valikoiman lajittelujärjestys muuttuu käänteiseksi. Luomme tämän toiminnan *kontekstimuuttujalla*, joka seuraa suuntaa, johon valikoima on lajiteltu. Kun käyttäjä valitsee painikkeen, muuttuja päivitetään ja suunta muuttuu. Lajittelu-painikkeen **[onselect](controls/properties-core.md)** -ominaisuudeksi on määritetty tämä kaava: **UpdateContext ({SortDescending1:! SortDescending1})**

**[UpdateContext](functions/function-updatecontext.md)** -toiminto luo **SortDescending1**-kontekstimuuttujan, jos sitä ei vielä ole olemassa. Funktio lukee muuttujan arvon ja määrittää sen loogiseen vastakkaiseen arvoon **!** -operaattorilla. Jos arvo on *true*, siitä tulee *false*. Jos arvo on *false*, siitä tulee *true*.

**[Valikoima](controls/control-gallery.md)** -ohjausobjektin **[Kohteet](controls/properties-core.md)** -ominaisuuden kaava käyttää tätä kontekstimuuttujaa yhdessä tekstin kanssa **TextSearchBox1**-ohjausobjektissa:

```powerapps-comma
Sort( 
    If( IsBlank(TextSearchBox1.Text);
        Assets;
        Filter( Assets; TextSearchBox1.Text in Text(ApproverEmail) ) 
    );
    ApproverEmail;
    If(SortDescending1; Descending; Ascending) 
)
```

Katsotaan tätä tarkemmin:

* Ulkopuolella on **[Sort](functions/function-sort.md)** -funktio, joka ottaa kolme argumenttia: taulukon, kenttä, jonka avulla lajitellaan, ja suunnan, jonka mukaan lajitellaan.  
  
  * Lajittelusuunta haetaan kontekstimuuttujasta, joka vaihtuu, kun käyttäjä valitsee **ImageSortUpDown1**-ohjausobjektin. *true*/*false*-arvo muunnetaan vakioille **Laskeva** ja **Nouseva**.
  * Lajiteltava kenttä on kiinteä **ApproverEmail**. Jos muutat kenttiä, jotka näkyvät valikoimassa, joudut myös muuttamaan tätä argumenttia.
* Sisällä on **[Filter](functions/function-filter-lookup.md)** -funktio, joka ottaa taulukon argumenttina ja lausekkeen kunkin tietueen arvioimista varten.
  
  * Taulukko on raaka **Assets**-tietolähde, joka on lähtökohta ennen suodattamista tai lajittelemista.
  * Lauseke etsii merkkijonon esiintymää kohteen **TextSearchBox1** sisältä **ApproverEmail**-kentässä.  Jos taas muutat kenttiä, jotka näkyvät valikoimassa, joudut myös päivittämään tämän argumentin.
  * Jos **TextSearchBox1** on tyhjä, käyttäjä haluaa näyttää kaikki tietueet, ja **[Filter](functions/function-filter-lookup.md)** -funktio ohitetaan.

Tämä on kuitenkin vain yksi esimerkki; voit luoda oman kaavan **[Kohteet](controls/properties-core.md)** -ominaisuudelle sovelluksesi tarpeiden mukaan lisäämällä **[Filter](functions/function-filter-lookup.md)** -,  **[Sort](functions/function-sort.md)** - ja muut funktiot ja operaattorit mukaan.    

## <a name="screen-design"></a>Näytön rakenne
Tähän mennessä emme ole käsitelleet muita tapoha, joilla ohjausobjekteja voidaan jakaa eri näytöissä. Tämä johtuu siitä, että vaihtoehtoja on useita ja paras valinta vaihtelee sovelluksen tarpeiden mukaan.

Koska tila puhelimen näytöissä on niin rajoitettu, haluat todennäköisesti selata, näyttää ja muokata/luoda eri näytöissä. Tässä ohjeaiheessa **[Navigate](functions/function-navigate.md)** - ja **[Back](functions/function-navigate.md)** -funktiot avaavat kukin näytön.  

Tabletissa voit selata, näyttää ja muokata/luoda kahdessa tai jopa yhdessä näytössä. Jälkimmäisessä tapauksessa **[Navigate](functions/function-navigate.md)** - tai **[Back](functions/function-navigate.md)** -funktiota ei tarvittaisi.

Jos käyttäjä työskentelee samassa näytössä, varmista, että hän ei voi muuttaa valintaa **[valikoimassa](controls/control-gallery.md)** ja mahdollisesti menettää tehtyjä muokkauksia **[Muokkaa lomaketta](controls/control-form-detail.md)** -ohjausobjektissa.  Jotta käyttäjä ei voi valita eri tietuetta, kun toiseen tietueeseen tehtyjä muutoksia ei ole vielä tallennettu, määritä valikoiman **[Ei käytössä](controls/properties-core.md)** -ominaisuudeksi tämä kaava:<br>
**EditForm.Unsaved**

