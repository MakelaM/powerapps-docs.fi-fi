---
title: Sovelluksen luominen alusta alkaen | Microsoft Docs
description: Voit luoda sovelluksen alusta alkaen määrittämällä kaikki käyttöliittymän elementit ja toiminnot, joilla voit hallita liiketoiminnallesi tärkeitä tietoja.
services: ''
suite: powerapps
documentationcenter: na
author: AFTOwen
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/16/2016
ms.author: anneta
ms.openlocfilehash: efc965d607198ed6366f3390960ccdf44b2ea210
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
---
# <a name="create-an-app-from-scratch"></a>Sovelluksen luominen alusta alkaen
Luo oma sovelluksesi alusta alkaen käyttämällä erinäisiä tietolähteitä. Voit halutessasi lisätä uusia lähteitä myöhemmin. Voit määrittää jokaisen käyttöliittymäelementin ulkoasun ja toiminnan sekä optimoida tuloksen omia tavoitteitasi ja työnkulkuasi varten. Tämä menetelmä vie enemmän aikaa kuin [sovelluksen muodostaminen automaattisesti](get-started-create-from-data.md), mutta kokeneet käyttäjät voivat näin tehdä parhaiten tarpeitaan vastaavan sovelluksen.

Tässä opetusohjelmassa luodaan sovellus, joka sisältää kaksi näyttöä. Yhdellä näytöllä käyttäjät voivat selata tietuejoukkoa:

![Näyttö, jolla käyttäjä voi selata tietojoukkoa](./media/get-started-create-from-blank/first-screen-final.png)

Toisella näytöllä käyttäjät voivat luoda tietueen, päivittää tietueen yhtä tai useampaa kenttää tai poistaa koko tietueen:

![Näyttö, jolla käyttäjä voi lisätä tai päivittää tietoja](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="prerequisites"></a>Edellytykset
Voit käyttää omaa Excel-tiedostoasi ja katsoa opetusohjelmasta vain yleiset käsitteet. Excel-tiedoston tietojen täytyy kuitenkin olla taulukkomuodossa. Lisätietoja on artikkelissa [Excel-taulukon muotoileminen](how-to-excel-tips.md).

Noudata seuraavia ohjeita tarkasti luomalla ensin Excel-tiedosto, jossa on nämä mallitiedot.

1. Kopioi nämä tiedot ja liitä ne Excel-tiedostoon.

   | Aloituspäivä | Aloitusaika | Vapaaehtoinen 1 | Vapaaehtoinen 2 |
   | --- | --- | --- | --- |
   | Lauantai |Klo 10–12 |Vasquez |Kumashiro |
   | Lauantai |Klo 12–14 |Ice |Singhal |
   | Lauantai |Klo 14–16 |Myk |Mueller |
   | Sunnuntai |Klo 10–12 |Li |Adams |
   | Sunnuntai |Klo 10–12 |Singh |Morgan |
   | Sunnuntai |Klo 10–12 |Batye |Nguyen |

2. Muotoile tiedot taulukoksi nimeltä **Schedule**, jotta PowerApps voi jäsentää tiedot.

    Lisätietoja on artikkelissa [Excel-taulukon muotoileminen](how-to-excel-tips.md).

3. Tallenna tiedosto nimellä **eventsignup.xls** ja lataa se [pilvitallennustilille](connections/cloud-storage-blob-connections.md), kuten OneDriveen.

4. Jos olet uusi PowerApps-käyttäjä:

   * Lue, kuinka voit [lisätä ohjausobjektin ja asettaa sen ominaisuudet](add-configure-controls.md), jotka määrittelevät sen ulkoasun ja toiminnot.
   * Lue, kuinka [ruutu lisätään ja nimetään uudelleen](add-screen-context-variables.md).

## <a name="create-a-blank-app-and-connect-to-data"></a>Luo tyhjä sovellus ja muodosta yhteys tietoihin
1. Napsauta tai napauta PowerApps Studion **Tiedosto-valikon** (lähellä ruudun vasenta reunaa) kohtaa **Uusi**.

    ![Tiedosto-valikon Uusi-vaihtoehto](./media/get-started-create-from-blank/file-new.png)

2. Napsauta tai napauta **Tyhjä sovellus** -ruudulta kohtaa **Puhelinasettelu**.

    ![Asetus sovelluksen luomiseksi tiedoista](./media/get-started-create-from-blank/create-from-blank.png)

3. Pyydettäessä katso esittely, jossa selitetään PowerAppsin pääalueet (tai napsauta tai napauta **Ohita**).

    ![Pikaesittely](./media/get-started-create-from-blank/quick-tour.png)

    Voit aina katsella esittelyn myöhemmin napsauttamalla tai napauttamalla kysymysmerkkikuvaketta, joka on lähellä ruudun vasenta yläkulmaa ja sitten napsauttamalla tai napauttamalla **Katso esittely**.

4. Voit vaihtaa pikkukuvanäkymään napsauttamalla tai napauttamalla vasemman navigointipalkin oikeassa yläkulmassa olevaa kuvaketta.

    ![Näkymien vaihtaminen](./media/get-started-create-from-blank/toggle-view.png)

5. Napsauta tai napauta oikean ruudun kohtaa **Lisää tietolähde**.

    ![Lisää tietolähde](./media/get-started-create-from-blank/add-data-source.png)

6. Suorita jompikumpi seuraavista toimista:

   * Jos olet jo muodostanut yhteyden pilvitallennustiliisi, napsauta tai napauta sitä.
   * Jos et ole muodostanut yhteyttä pilvitallennustiliisi, napsauta tai napauta kohtaa **Lisää yhteys**, napsauta tai napauta tilisi tyyppiä, napsauta tai napauta **Yhdistä** ja syötä (kysyttäessä) tunnistetietosi.

7. Siirry kohdassa **Valitse Excel-tiedosto** tiedostoon **eventsignup.xlsx** ja napsauta tai napauta sitä.

    ![Käytettävän Excel-tiedoston määrittäminen](./media/get-started-create-from-blank/select-excel-file.png)

8. Valitse **Valitse taulukko** -kohdasta **Schedule**-valintaruutu ja sitten napsauta tai napauta **Yhdistä**.

    ![Käytettävän Excel-taulukon määrittäminen](./media/get-started-create-from-blank/select-table.png)

    Oikeanpuoleisen ruudun **Tietolähteet**-välilehdellä näytetään tietolähteet, jotka olet lisännyt sovellukseesi.

    ![Yhdistettyjen tietolähteiden näyttäminen](./media/get-started-create-from-blank/data-connect.png)

    Tämä opetusohjelma vaatii vain yhden tietolähteen, mutta voit lisätä muita tietolähteitä myöhemmin.

## <a name="show-the-data"></a>Näytä tiedot
1. Napsauta tai napauta **Aloitus**-välilehdeltä **Uusi näyttö** ja napsauta tai napauta **Luettelonäyttö**.

    ![Lisää asettelu ja siihen otsikko, aliotsikko ja runkoelementti](./media/get-started-create-from-blank/add-gallery.png)

    Kun näyttö lisätään, siinä on useita oletusohjausobjekteja, kuten hakukenttä ja **[Valikoima](controls/control-gallery.md)**-ohjausobjekti. Valikoima kattaa koko näytön hakukentän alapuolella.

2. Napsauta tai napauta mitä tahansa valikoiman kohtaa paitsi nuolta, esimerkiksi hakukentän alapuolista aluetta.

    ![Valitse valikoima](./media/get-started-create-from-blank/select-gallery.png)

3. Avaa oikeanpuoleisen ruudun **Asettelut**-luettelo ja napsauta tai napauta vaihtoehtoa, jossa on otsikko, aliotsikko ja runko.

    ![Valitse valikoima](./media/get-started-create-from-blank/select-layout.png)

4. Napsauta tai napauta ominaisuusluettelon kohtaa **[Items](controls/properties-core.md)**, kopioi tämä kaava ja liitä se kaavariville:

    **SortByColumns(Search(Schedule, TextSearchBox1.Text, "Vapaaehtoinen_x0020_1"), "Vapaaehtoinen_x0020_1", If(SortDescending1, SortOrder.Descending, SortOrder.Ascending))**

    Jos et ole varma ominaisuusluettelon sijainnista, katso [Lisää ja määritä ohjausobjekteja](add-configure-controls.md).

    > [!NOTE]
> PowerApps näyttää Excel- ja SharePoint-tietolähteiden sarakkeiden nimien välilyönnit muodossa **”\_x0020\_”**. Tässä esimerkissä sarake **”Vapaaehtoinen 1”** näkyy kaavassa muodossa **"Vapaaehtoinen_x0020_1"**.

    Tässä valikoimassa näytetään **Schedule**-taulukon tiedot.

    ![Valikoiman oletusarvoiset Schedule-tiedot](./media/get-started-create-from-blank/show-data-default.png)

    Hakukentällä voidaan suodattaa valikoimaa käyttäjän kirjoittaman tekstin mukaan. Jos käyttäjä kirjoittaa ainakin yhden kirjaimen hakukenttään, valikoimassa näytetään vain tietueet, joissa **Vapaaehtoinen 1** -kenttä sisältää käyttäjän antaman tekstin.

    Lajittelupainikkeella tietueet voidaan lajitella **Vapaaehtoinen 1** -sarakkeen tietojen mukaan. Jos käyttäjä napsauttaa tai napauttaa tätä painiketta, lajittelujärjestys vaihtuu nousevan ja laskevan välillä.

    Kaava sisältää funktiot **Sort**, **If**, **IsBlank**, **Filter** ja **Text**. Katso lisätietoja näistä ja muista funktioista kohdasta [Lisätietoja kaavasta](formula-reference.md)

5. Kirjoita hakukenttään **i** ja napsauta tai napauta lajittelupainiketta kerran (tai pariton määrä kertoja).

    Valikoima näyttää nämä tulokset.

    ![Lajittele ja suodata valikoimaa](./media/get-started-create-from-blank/sort-filter.png)

    Lisätietoja **[lajittelusta](functions/function-sort.md)**, **[suodatuksesta](functions/function-filter-lookup.md)** ja [muista funktioista](formula-reference.md)

6. Valitse ruudun yläosan **[Otsikko](controls/control-text-box.md)**-ohjausobjekti napsauttamalla tai napauttamalla sitä.

    ![Valitse otsikkorivi](./media/get-started-create-from-blank/select-title-bar.png)

7. Napsauta tai napauta ominaisuusluettelossa **[Text](controls/properties-core.md)**, kopioi tämä teksti ja liitä se kaavariville.<br>
   **"Näytä tietueet"**

    ![Muuta otsikkoriviä](./media/get-started-create-from-blank/change-title-bar.png)

## <a name="create-the-changescreen-and-its-banner"></a>Luo ChangeScreen ja sen palkki
1. Poista **Screen1** ja muuta kohteen **Screen2** nimeksi **ViewScreen**.

    ![Nimeä näyttö uudelleen](./media/get-started-create-from-blank/rename-screen.png)

2. Lisää näyttö ja anna sen nimeksi **ChangeScreen**.

    ![Lisää ja nimeä näyttö uudelleen](./media/get-started-create-from-blank/add-screen.png)

3. Napsauta tai napauta **Lisää**-välilehdeltä **Teksti** ja sitten napsauta tai napauta **[Otsikko](controls/control-text-box.md)**.

4. Määritä juuri lisäämäsi **Otsikko**-ohjausobjekti:

   * Määritä sen **Text**-ominaisuudeksi tämä kaava:
     <br>**"Muuta tietuetta"**

   * Määritä sen **Fill**-ominaisuudeksi tämä kaava:
     <br>**RGBA(62, 96, 170, 1)**.

   * Määritä sen **Color**-ominaisuudeksi tämä kaava:
     <br>**RGBA(255, 255, 255, 1)**

   * Määritä sen **Align**-ominaisuudeksi **Center**.
   * Määritä sen **X**-ominaisuudeksi **0**.

   * Määritä sen **Leveys**-ominaisuudeksi **640**.
     **Otsikko**-ohjausobjekti muuttuu tekemiesi muutosten mukaisesti.

     ![ChangeScreen palkin kanssa](./media/get-started-create-from-blank/change-screen-blank.png)

## <a name="add-and-configure-a-form"></a>Lisää ja määritä lomake
1. Napsauta tai napauta **Lisää**-välilehdeltä **Lomakkeet** ja napsauta tai napauta **Muokkaa**.

2. Siirrä lomaketta ja muuta sen kokoa niin, että se kattaa suurimman osan näytöstä.

    ![Lisää lomake](./media/get-started-create-from-blank/add-form.png)

    Lomakkeen nimi on oletusarvoisesti **Form1**, paitsi jos olet jo lisännyt ja poistanut lomakkeen. Tässä tapauksessa anna lomakkeelle nimi **Form1**.

3. Määritä **Form1**:n **[DataSource](controls/control-form-detail.md)**-ominaisuudeksi **Schedule**.

4. Määritä **Form1**:n **Item**-ominaisuudeksi tämä lauseke:
   <br>**BrowseGallery1.Selected**

5. Napsauta tai napauta oikeanpuoleisessa ruudussa olevia kenttien valintaruutuja niiden näyttämiseksi.

    ![Näytä kentät lomakkeessa](./media/get-started-create-from-blank/schedule-checkbox.png)

6. Napsauta tai napauta lomakkeen alaosasta **Lisää mukautettu kortti**.

    ![Lisää mukautettu kortti](./media/get-started-create-from-blank/add-custom-card.png)

7. Lisää uuteen korttiin **[Otsikko](controls/control-text-box.md)**-ohjausobjekti.

8. Määritä uuden ohjausobjektin **[AutoHeight](controls/control-text-box.md)**-ominaisuudeksi **tosi** ja määritä sen **[Text](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**Form1.Error**

    Otsikko näyttää lomakkeen virheet.

9. Napsauta tai napauta vasemman navigointipalkin **ChangeScreen**-pikkukuvaa, niin se valitaan.

10. Napsauta tai napauta **Lisää**-välilehdeltä **Kuvakkeet**, napsauta tai napauta vaihtoehtoa, jolla lisätään **Takaisin-nuoli** ja siirrä sitten nuoli näytön vasempaan alakulmaan.

11. Määritä nuolen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

     **ResetForm(Form1);Navigate(ViewScreen,ScreenTransition.None)**

      Kun käyttäjä napsauttaa tai napauttaa nuolta, **[Navigate](functions/function-navigate.md)**-funktio avaa **ViewScreen**-näytön.

12. Lisää lomakkeen alapuolelle **[Painike](controls/control-button.md)**-ohjausobjekti ja aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi **"Tallenna"**.

     ![Tallennuspainikkeen lisääminen](./media/get-started-create-from-blank/add-save-button.png)

13. Määritä painikkeen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **SubmitForm(Form1); If(Form1.ErrorKind = ErrorKind.None, Navigate(ViewScreen, ScreenTransition.None))**

    Kun käyttäjä napsauttaa tai napauttaa painiketta, **[SubmitForm](functions/function-form.md)**-funktio tallentaa muutokset tietolähteeseen ja **ViewScreen** näytetään uudelleen.

14. Lisää näytön alaosaan uusi painike, aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi **”Poista”** ja aseta sitten sen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **Remove(Schedule,BrowseGallery1.Selected);<br>If(IsEmpty(Errors(Schedule)),Navigate(ViewScreen,ScreenTransition.None))**

    Kun käyttäjä napsauttaa tai napauttaa tätä painiketta, **[Remove](functions/function-remove-removeif.md)**-funktio poistaa tietueen ja **ViewScreen** näytetään uudelleen.

15. Määritä **Poista**-painikkeen **[Visible](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
    <br>**Form1.Mode=FormMode.Edit**

    Tämä vaihe piilottaa **Poista**-painikkeen, kun käyttäjä on luomassa tietuetta.

    **ChangeScreen** vastaa tätä esimerkkiä:

    ![Lopullinen ChangeScreen](./media/get-started-create-from-blank/changescreen-final.png)

## <a name="set-navigation-from-viewscreen"></a>ViewScreenistä siirtymisen asettaminen
1. Napsauta tai napauta vasemman navigointipalkin **ViewScreen**-pikkukuvaa.

    ![Avaa ViewScreen](./media/get-started-create-from-blank/select-viewscreen.png)

2. Napsauta tai napauta valikoiman ensimmäisen tietueen **Seuraava-nuolta**.

    ![Seuraava-nuoli](./media/get-started-create-from-blank/next-arrow.png)

3. Määritä nuolen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **Navigate(ChangeScreen,ScreenTransition.None)**

4. Napsauta tai napauta oikean yläkulman plus-kuvaketta.

    ![Tietueen lisääminen](./media/get-started-create-from-blank/add-record.png)

5. Määritä valitun kuvakkeen **[OnSelect](controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **NewForm(Form1);Navigate(ChangeScreen,ScreenTransition.None)**`

     Kun käyttäjä napsauttaa tai napauttaa tätä kuvaketta, **ChangeScreen** näytetään kaikki kentät tyhjänä, jotta käyttäjä voi luoda tietueen helpommin.

## <a name="run-the-app"></a>Sovelluksen suorittaminen
Kun mukautat sovellusta, voit testata muutoksia suorittamalla sovelluksen Esikatselu-tilassa tämän osion vaiheiden mukaisesti.

1. Valitse vasemmasta navigointipalkista **ViewScreen** napsauttamalla tai napauttamalla ylintä pikkukuvaa.

    ![ViewScreenin valitseminen](./media/get-started-create-from-blank/select-viewscreen.png)

2. Avaa esikatselutila painamalla F5-näppäintä (tai napsauttamalla tai napauttamalla **Esikatselu**-kuvaketta oikean yläkulman läheltä).

    ![Esikatselutilan avaaminen](./media/get-started-create-from-blank/open-preview.png)

3. Napsauta tai napauta tietueen Seuraava-nuolta, niin tietueesta näytetään tietoja.

4. Muuta **ChangeScreen**-ruudulla yhden tai useamman kentän tietoja ja tallenna muutokset napsauttamalla tai napauttamalla **Tallenna** tai poista tietue napsauttamalla tai napauttamalla **Poista**.

5. Sulje esikatselutila painamalla ESC-näppäintä (tai napsauttamalla tai napauttamalla Sulje-kuvaketta otsikkorivin alapuolella).

    ![Esikatselutilan sulkeminen](./media/get-started-create-from-blank/close-preview.png)

## <a name="next-steps"></a>Seuraavat vaiheet
* Tallenna sovelluksesi pilveen painamalla Ctrl+S, jotta voit suorittaa sen muissa laitteissa.
* [Jaa sovellus](share-app.md) niin, että muut voivat suorittaa sen.
* Lisätietoa [valikoimista](add-gallery.md), [lomakkeista](add-form.md) ja [kaavoista](working-with-formulas.md).
