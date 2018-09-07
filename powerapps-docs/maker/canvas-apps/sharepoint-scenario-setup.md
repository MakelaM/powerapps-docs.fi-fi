---
title: Luo luetteloita SharePoint Onlinen integroimiseksi PowerAppsin, Microsoft Flow’n ja Power BI:n kanssa | Microsoft Docs
description: Tässä tehtävässä luomme SharePoint-luetteloita, jotka toimivat sovellusten, työnkulkujen, raporttien ja koontinäyttöjen tietolähteinä.
author: mgblythe
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 12/19/2017
ms.author: mblythe
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9e1694a3190740c788eb9cd53de1187ed32d0fbc
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833316"
---
# <a name="set-up-lists-for-sharepoint-online-integration-with-powerapps-microsoft-flow-and-power-bi"></a>Luo luetteloita SharePoint Onlinen integroimiseksi PowerAppsin, Microsoft Flow’n ja Power BI:n kanssa
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämisestä SharePoint Onlinen kanssa. Varmista, että luet [sarjan esittelyn](sharepoint-scenario-intro.md), jotta saat paremman käsityksen kokonaiskuvasta, sekä aiheeseen liittyvät ladattavat tiedostot.

SharePointissa on lukemattomia jakamisen ja yhteistyön ominaisuuksia, mutta keskitymme tässä artikkelissa yhteen skenaarion ominaisuuteen: [SharePoint-luettelot](https://support.office.com/article/Introduction-to-lists-0A1C3ACE-DEF0-44AF-B225-CFA8D92C52D7). Luettelo on yksinkertaisesti tietokokoelma, jonka voit jakaa ryhmäsi jäsenten ja muiden sivuston käyttäjien kanssa. Käymme läpi tässä skenaariossa käytettyjä luetteloita. Sitten voit luoda niitä omalla SharePoint Online -sivustollasi.

## <a name="step-1-understand-the-lists"></a>Vaihe 1: Luetteloiden ymmärtäminen
Ensimmäinen luettelo on **Projektipyynnöt**, jolla projektin pyytäjä lisää pyynnön. Sitten projektin hyväksyjä tarkastelee pyyntöä ja hyväksyy tai hylkää sen.

| **Luettelon sarake** | **Tietotyyppi** | **Muistiinpanot** |
| --- | --- | --- |
| Otsikko |Yksi tekstirivi |Oletussarake, jota käytetään projektin nimeä varten |
| Kuvaus |Yksi tekstirivi | |
| Projektin tyyppi |Yksi tekstirivi |Arvot: uusi laitteisto, päivitetty laitteisto, uusi ohjelmisto, päivitetty ohjelmisto |
| Pyynnön päivämäärä |Päivämäärä | |
| Pyytäjä |Yksi tekstirivi | |
| Arvioidut päivät |Lukumäärä |Mahdollistaa pyytäjän arvion vertailun projektipäällikön arvioon sekä toteutuneeseen lukumäärään |
| Hyväksytty |Yksi tekstirivi |Arvot: odottava, kyllä, ei |

> [!NOTE]
> Käytämme myös **Tunnus**-saraketta, jonka SharePoint muodostaa automaattisesti ja joka on oletusarvoisesti piilotettuna. Yksinkertaisuuden vuoksi käytämme tietojen perustyyppejä, mutta oikeassa sovelluksessa ne saattavat olla monimutkaisempia, kuten **Henkilö tai ryhmä** **Pyytäjä**-sarakkeessa. Lisätietoja PowerAppsin tukemista tietotyypeistä saat lukemalla [Microsoft PowerAppsin yhdistäminen SharePointiin](connections/connection-sharepoint-online.md#known-issues) -artikkelin.

Toinen luettelo on **Projektitiedot**, johon tallentuu kaikkien hyväksyttyjen projektien tiedot, kuten sille valittu projektipäällikkö.

| **Luettelon sarake** | **Tietotyyppi** | **Muistiinpanot** |
| --- | --- | --- |
| Otsikko |Yksi tekstirivi |Oletussarake, jota käytetään projektin nimeä varten |
| Pyynnön tunnus |Lukumäärä |Yhdistää **Projektipyyntö**-luettelon **Tunnus**-sarakkeen arvoon |
| Hyväksymispäivämäärä |Päivämäärä | |
| Tila |Yksi tekstirivi |Arvot: ei aloitettu, kesken, valmis |
| Projektin aloituspäivämäärä |Päivämäärä |Ajankohta, jolloin projektipäällikkö arvioi projektin alkavan |
| Projektin päättymispäivämäärä |Päivämäärä |Ajankohta, jolloin projektipäällikkö arvioi projektin päättyvän |
| Ennakoidut päivät |Lukumäärä |Työpäivät; yleensä lasketaan, mutta ei tässä skenaariossa |
| Toteutuneet päivät |Lukumäärä |Valmiiden projektien osalta |
| Valittu projektipäällikkö |Yksi tekstirivi |Projektipäällikkö |

## <a name="step-2-create-and-review-the-lists"></a>Vaihe 2: Luo luettelo ja tarkastele sitä
Voidaksesi jatkaa tätä skenaariota sinun on luotava kaksi SharePoint-luetteloa ja täytettävä ne esimerkkitiedoilla. Näytämme sinulle, miten tämä tehdään luomalla luettelo ja liittämällä siihen esimerkkitietoja. Varmista, että sinulla on [latauspaketin](https://aka.ms/o4ia0f) Excel-tiedostot.

> [!NOTE]
> Käytä tätä vaihetta varten Internet Explorer -selainta.

### <a name="create-the-lists"></a>Luetteloiden luominen

1. Napauta tai napsauta Internet Explorer -selaimen SharePoint-sivustolla **Uusi** ja sitten **Luettelo**.
   
    ![Uusien SharePoint-luetteloiden luominen](./media/sharepoint-scenario-setup/01-01-01-new-list.png)

2. Anna nimi ”Projektipyynnöt” ja napauta tai napsauta sitten **Luo**.
   
    ![Anna uudelle luettelolle nimi](./media/sharepoint-scenario-setup/01-01-02-create-list.png)
   
    **Projektipyynnöt**-luettelo luodaan oletusarvoisen **Otsikko**-kentän kanssa.
   
    ![Projektipyynnöt-luettelo](./media/sharepoint-scenario-setup/01-01-03-initial-list.png)

### <a name="add-columns-to-the-list"></a>Lisää luetteloon sarakkeita

1. Napsauta tai napauta ![Uusi kohde -kuvaketta](./media/sharepoint-scenario-setup/icon-new.png) ja sitten **Yksi tekstirivi**.
   
    ![Lisää yksi tekstirivi -kenttä](./media/sharepoint-scenario-setup/01-01-04-add-column.png)

2. Anna nimi ”Kuvaus” ja napauta tai napsauta sitten **Tallenna**.
   
3. Toista vaiheet **1** ja **2** muita luettelossa olevia sarakkeita varten:
   
   1. **Yksi tekstirivi** > ”Projektin tyyppi”
   2. **Päivämäärä** > ”Pyynnön päivämäärä”
   3. **Yksi tekstirivi** > ”Pyytäjä”
   4. **Lukumäärä** > ”Arvioidut päivät”
   5. **Yksi tekstirivi** > ”Hyväksytty”

### <a name="copy-data-into-the-list"></a>Tietojen kopioiminen luetteloon
1. Napauta tai napsauta **Pikamuokkaus**.
   
    ![Pikamuokkaus luetteloa varten](./media/sharepoint-scenario-setup/01-01-06-quick-edit.png)
2. Valitse ruudukon solut.
   
    ![Kaikki sarakkeet sisältävä luettelo](./media/sharepoint-scenario-setup/01-01-07-empty-grid.png)
3. Avaa project-requests.xlsx-työkirja ja valitse kaikki tiedot (ei otsikkoja).
   
    ![Projektipyyntöjen Excel-taulukko](./media/sharepoint-scenario-setup/01-01-08-excel-table.png)
4. Kopioi tiedot ja liitä ne ruudukkoon SharePointissa. Napauta tai napsauta sitten **Valmis**.
   
    ![Valmis tietoja sisältävä luettelo](./media/sharepoint-scenario-setup/01-01-09-full-grid.png)
5. Toista luettelon luomisvaiheet ja kopiointiprosessi Projektitiedot-luettelon osalta. Käytä project-details.xlsx-työkirjaa. Katso ohjeet sarakkeiden nimiä ja tietotyyppejä varten [Vaihe 1: Luetteloiden ymmärtäminen](#step-1-understand-the-lists) -osuuden Projektitiedot-taulukosta.

## <a name="step-3-update-connections-to-samples---optional"></a>Vaihe 3: Päivitä yhteydet esimerkkeihin (valinnainen)
Kuten tämän opetusohjelmasarjan johdannossa todettiin, olemme lisänneet kaksi esimerkkisovellusta ja raportin [latauspakettiin](https://aka.ms/o4ia0f). Voit suorittaa tämän skenaarion loppuun ilman näiden esimerkkien käyttöä, mutta jos haluat käyttää esimerkkejä, sinun on päivitettävä yhteydet SharePoint-luetteloihin. Kun päivität yhteydet, ne käyttävät *sinun* luetteloitasi tietolähteinä meidän lähteidemme sijaan.

### <a name="update-connections-for-the-sample-apps"></a>Päivitä esimerkkisovellusten yhteydet

1. Napauta tai napsauta [PowerApps Studion](https://create.powerapps.com/studio/) vasemmassa ruudussa **Avaa**. 

2. Napauta tai napsauta **Selaa** ja avaa sitten lataamasi **project-management-app.msapp**-tiedosto.

3. Napauta tai napsauta **Salli**, jotta PowerApps voi käyttää SharePointia.

4. Napauta tai napsauta **Näkymä**-välilehden nauhassa **Tietolähteet**.

    ![PowerAppsin tietolähteet](./media/sharepoint-scenario-setup/01-03-01-data-sources.png)
5. Napauta tai napsauta **Tiedot**-paneelin kolmea pistettä (**. . .**) **Projektitiedot**-kohdan vieressä ja napauta tai napsauta sitten **Poista**.
   
    ![Projektitietojen tietolähteen poistaminen](./media/sharepoint-scenario-setup/01-03-02-remove.png)
6. Napauta tai napsauta **Lisää tietolähde**.
   
    ![Tietolähteen lisääminen](./media/sharepoint-scenario-setup/01-03-03-add.png)

7. Esitämme kaksi tapaa, joilla voit luoda yhteyden luetteloon. Valitse sopiva tapa sen perusteella, onko PowerAppsin ja SharePointin välille jo luotu sinua varten yhteys: 

    * Jos näet, että SharePoint-yhteys on jo luotu, napauta tai napsauta kyseistä yhteyttä.

        ![Olemassa oleva yhteys](./media/sharepoint-scenario-setup/01-03-03aa-existing-connection.png)

    * Jos et näe SharePoint-yhteyttä, napauta tai napsauta **Uusi yhteys**.

        ![Uusi yhteys](./media/sharepoint-scenario-setup/01-03-03a-new-connection.png)

        Napauta tai napsauta sitten **SharePoint** ja napauta tai napsauta sitten **Luo**.
   
        ![SharePoint-yhteys](./media/sharepoint-scenario-setup/01-03-03b-sharepoint.png)

8. Anna sen SharePoint Online -sivuston URL-osoite, joka sisältää luomasi luettelot. Napauta tai napsauta sitten **Siirry**.
   
    ![SharePoint-URL-osoite](./media/sharepoint-scenario-setup/01-03-03c-sharepoint-url.png)
9. Valitse **Projektitiedot**-luettelo ja napauta tai napsauta sitten **Yhdistä**.
   
    ![Projektitiedot-luettelo](./media/sharepoint-scenario-setup/01-03-03d-project-details.png)
   
    **Tiedot**-paneelista näet luomasi yhteyden.
   
    ![Tietolähteet](./media/sharepoint-scenario-setup/01-03-03e-data-sources.png)

10. Napauta tai napsauta kolmea pistettä (**. . .**) **Projektitietojen** vieressä ja napauta tai napsauta sitten **Päivitä**.
    
    ![Projektitietojen tietolähteen päivittäminen](./media/sharepoint-scenario-setup/01-03-02-remove.png)

11. Napsauta ![Suorita sovellus -kuvaketta](./media/sharepoint-scenario-setup/icon-run-arrow.png) oikeassa yläkulmassa, jotta voit suorittaa sovelluksen ja varmistaa, että yhteydet toimivat asianmukaisesti.

12. Napauta tai napsauta **Tiedosto** ja tallenna sitten sovellus pilveen. 

12. Toista tämän osuuden vaiheet **project-requests-app.msapp**-sovelluksen osalta käyttämällä **Projektipyynnöt**-luetteloa.

### <a name="update-connections-for-the-sample-report"></a>Päivitä esimerkkiraportin yhteydet
1. Avaa Power BI -työpöydällä **project-analysis.pbix**.

2. Napauta tai napsauta **Koti**-välilehden nauhassa kohtaa **Muokkaa pyyntöjä** ja sitten **Tietolähteiden asetukset**.
   
    ![Pyyntöjen muokkaaminen](./media/sharepoint-scenario-setup/01-03-04-edit-queries.png)

3. Napauta tai napsauta **Muuta lähdettä**.
   
    ![Tietolähdeasetukset](./media/sharepoint-scenario-setup/01-03-05-settings.png)

4. Anna SharePoint Online -sivuston URL-osoite ja napsauta tai napauta sitten **OK** ja sen jälkeen **Sulje**.
   
    ![SharePoint-luetteloiden URL-osoite](./media/sharepoint-scenario-setup/01-03-06-list-url.png)

5. Power BI -työpöydällä näkyy nauhan alla palkki, joten voit toteuttaa muutokset ja tuoda tietoja uudesta lähteestä. Napauta tai napsauta **Ota muutokset käyttöön**.
   
    ![Ota kyselyn muutokset käyttöön](./media/sharepoint-scenario-setup/01-03-07-apply.png)

6. Kirjaudu Microsoft-tiliin (SharePoint Onlineen kirjautumiseen käyttämäsi tili) ja napauta tai napsauta sitten **Yhdistä**.
   
    ![Yhdistä SharePoint Onlineen](./media/sharepoint-scenario-setup/01-03-08-connect.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelmasarjan seuraava vaihe on [sovelluksen muodostaminen projektipyyntöjen käsittelyä varten](sharepoint-scenario-generate-app.md).

