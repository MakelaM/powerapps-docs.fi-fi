---
title: Help Desk -mallin asentaminen ja määrittäminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Tässä artikkelissa annetaan vaiheittaiset ohjeet PowerAppsin Help Desk -mallin asentamista ja määrittämistä varten pohjaan perustuvissa sovelluksissa.
author: caburk
manager: kvivek
ms.service: powerapps
ms.topic: sample
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/08/2018
ms.author: caburk
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3945bc2e164d9fa88ee122910d3e15371b9e239e
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42834620"
---
# <a name="install-and-configure-the-help-desk-sample-in-powerapps"></a>Asenna ja määritä Help Desk -malli PowerAppsissa

Tässä artikkelissa annetaan vaiheittaiset ohjeet PowerAppsin Help Desk -mallin asentamista ja määrittämistä varten pohjaan perustuvissa sovelluksissa.

Näiden vaiheiden arvioitu suoritusaika on **10–15 minuuttia**

> [!TIP]
> Jos haluat nähdä tämän prosessin esittelyn, katso tämä [video](https://youtu.be/z4cdtD6hB_4).

## <a name="overview-of-the-sample"></a>Mallin yleiskatsaus

Tukipalvelu tarjoaa käyttäjäystävällisen tavan muodostaa yhteys loppukäyttäjien ja tukiasiantuntijoiden välille. Löydä nopeasti vastauksia tärkeimpiin kysymyksiisi, seuraa avointen tukipyyntöjen edistymistä ja tarkista edellisten pyyntöjen tiedot. Tämä sovellus edellyttää jonkin verran määrittämistä, jotta saat siitä haluamasi kaltaisen.

![Help Desk PowerAppin aloitusnäyttö](./media/help-desk-install/Login-screen.png)

> [!TIP]
> Katso tästä [videosta](https://youtu.be/sl5fXwwnvzI), miten Help Desk PowerApp -mallia käytetään.

## <a name="prerequisites"></a>Edellytykset

- [Rekisteröidy](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerAppsiin.
- Kelvollinen SharePoint Online -käyttöoikeus ja luetteloiden luontioikeus tarvitaan.

## <a name="create-the-helpdesk-sharepoint-list"></a>Luo HelpDeskin SharePoint-luettelo

Tähän luetteloon tallennetaan tukipalvelun tukipyyntöjä.

1. Avaa selain ja siirry kohteeseen https://portal.office.com.
2. Kirjaudu sisään tilillä, jolla on oikeus luoda SharePoint-luetteloita.
3. Siirry sivustokokoelmaan, johon haluat sijoittaa tukipalvelun luettelon.
4. Napsauta **hammaspyöräkuvaketta** web-sivun yläosassa oikealla.
5. Napsauta kohtaa **Lisää sovellus**.
6. Syötä **Etsi sovellus** -tekstiruutuun **Mukautettu**.
7. Napsauta **hakukuvaketta**.
8. Napsauta **Custom List** -sovellusta.
9. Syötä **Nimi**-tekstiruutuun **HelpDesk**.

    > [!IMPORTANT]
    > Jos valitset luettelolle eri nimen, muista kirjoittaa se ylös, sillä sinun täytyy korvata se HelpDeskin tilalle kaikkialla, missä näet sen asennus- ja määritysprosessin aikana.

10. Valitse **Luo**.

### <a name="create-description-column"></a>Kuvaus-sarakkeen luominen

1. Valitse kolme pistettä HelpDesk-luettelon vieressä ja valitse **Asetukset**.
2. Napsauta **Luo sarake**.
3. Syötä **Sarakkeen nimi** -tekstikenttään**Kuvaus**.
4. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Useita tekstirivejä**.
5. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
6. Valitse **Määritä sallittavan tekstin tyyppi** -valintanappiluettelossa **Vain teksti**.
7. Valitse **OK**.

### <a name="create-category-column"></a>Luo Luokka-sarake

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään**Luokka**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
4. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstikenttään seuraavat arvot, kukin omalle rivilleen: 
    - Kannettavan tietokoneen tai PC-laitteen ongelma
    - Kannettavan tietokoneen tai PC-ohjelmiston ongelma
5. Valitse **Pakota yksilölliset arvot** -valintanappiluettelossa **Ei**.
6. Valitse **Vaihtoehtojen näyttömuoto** -valintanappiluettelossa **Avattava valikko**.
7. Syötä **Oletusarvo** -tekstiruutuun **Kannettavan tietokoneen tai PC-laitteen ongelma**.
8. Napsauta **OK**.

### <a name="create-percentcomplete-column"></a>ProsenttiaValmiina-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Anna **Sarakkeen nimi** -tekstiruutuun **ProsenttiaValmiina**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Numero (1, 10, 100)**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Ei**.
5. Valitse **OK**.

### <a name="create-priority-column"></a>Luo Prioriteetti-sarake

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään **Prioriteetti**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
4. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstikenttään seuraavat arvot, kukin omalle rivilleen: 
    - SUURI
    - NORMAALI
    - PIENI
5. Valitse **Pakota yksilölliset arvot** -valintanappiluettelossa **Ei**.
6. Valitse **Vaihtoehtojen näyttömuoto** -valintanappiluettelossa **Avattava valikko**.
7. Syötä **Oletusarvo** tekstiruutuun **PIENI**.
8. Valitse **OK**.

### <a name="create-taskstatus-column"></a>Luo Tehtävän tila -sarake

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään**Tehtävän tila**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
4. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstikenttään seuraavat arvot, kukin omalle rivilleen: 
    - EI ALOITETTU
    - KESKENERÄINEN
    - VALMIS
    - SIIRRETTY
    - ODOTTAA ASIAKASPALVELUA
5. Valitse **Pakota yksilölliset arvot** -valintanappiluettelossa **Ei**.
6. Valitse **Vaihtoehtojen näyttömuoto** -valintanappiluettelossa **Avattava valikko**.
7. Syötä **Oletusarvo** tekstiruutuun **EI ALOITETTU**.
8. Valitse **OK**.

### <a name="create-assignedto-column"></a>Luo Vastaava henkilö -sarake

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään**Vastaava henkilö**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Henkilö tai ryhmä**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Ei**.
5. Valitse **Salli useita valintoja** -valintanappiluettelossa **Ei**.
6. Valitse **OK**.

### <a name="edit-title-column"></a>Muokkaa ”Otsikko”-saraketta

1. Napsauta **Otsikko**-sarakkeen linkkiä.
2. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Ei**.
3. Valitse **OK**.

## <a name="download-the-help-desk-powerapp"></a>Lataa Help Desk PowerApp

1.  [Lataa](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/helpdesk/docs/HelpDesk(SP_List).zip) PowerApps-paketti ja tallenna se tietokoneeseesi.

## <a name="create-connections"></a>Yhteyksien luominen

1.  Siirry selaimella osoitteeseen [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2.  Kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
3.  Valitse vasemmasta valikosta **Tiedot** ja **Yhteydet**.
    
### <a name="create-office-365-outlook-connection"></a>Luo Office 365 Outlook -yhteys

1.  Napsauta **+ Uusi yhteys**.
2.  Syötä **Haku**-tekstikenttään **Office 365 Outlook**.
3.  Valitse luettelosta **Office 365 Outlook**.
4.  Napsauta **Luo**.
5.  Valitse ponnahdusikkunassa tili, jolla kirjauduit sisään.

### <a name="create-sharepoint-connection"></a>SharePoint-yhteyden luominen

1.  Napsauta **+ Uusi yhteys**.
2.  Syötä **Haku**-tekstikenttään **SharePoint**.
3.  Valitse luettelosta **SharePoint**.
4.  Napsauta **Luo**.
5.  Valitse ponnahdusikkunassa tili, jolla kirjauduit sisään.

### <a name="create-office-365-users-connection"></a>Office 365 Users -yhteyden luominen

1.  Napsauta kohtaa **+ Uusi yhteys**.
2.  Syötä **Haku**-tekstikenttään **office 365 users**.
3.  Valitse luettelosta **Office 365 Users**.
4.  Valitse **Luo**.
5.  Valitse ponnahdusikkunassa tili, jolla kirjauduit sisään.

## <a name="import-the-help-desk-powerapp"></a>Tuo Help Desk PowerApp

1. Siirry selaimella kohteeseen https://web.powerapps.com.
2. Kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
3. Valitse vasemmasta valikosta **Sovellukset**. 
4. Napsauta kohtaa **Tuo paketti (esikatselu)**.
    
   ![Tuo paketti -näyttö](./media/help-desk-install/import-package.png)

5. Napsauta **Lataa palvelimeen**-painiketta ja valitse PowerApp-paketti, jonka latasit edellisten vaiheiden aikana.
6. Määritä **App**- ja **Flow**-resurssityypeille **Tuonnin määritykset** -arvoksi **Luo uusina**.
7. Määritä **SharePoint**- ja **Outlook**-yhteyksille **Tuonnin määritykset** -arvoksi **Valitse tuonnin aikana**.
    
   ![Tuonnin asetukset -näyttö](./media/help-desk-install/import-settings.png)

8. Napsauta **SharePoint-yhteyden** **punaista kuvaketta**.
9. Napsauta yhteydet-luettelossa kohdetta, jossa on käyttäjänimesi.

   ![Tuonnin asetukset -näyttö](./media/help-desk-install/import-settings-sharepoint.png)

10. Napsauta **Tallenna**.
11. Napsauta **Office 365 Outlook -yhteyden** **punaista kuvaketta**.
12. Napsauta yhteydet-luettelossa kohdetta, jossa on käyttäjänimesi.

    ![Tuonnin asetukset -näyttö](./media/help-desk-install/import-settings-office365outlook.png)

13. Napsauta **Tallenna**.

    > [!TIP] 
    > Kun olet valmis, se näyttää tältä.

    ![Tuonnin asetukset -näyttö](./media/help-desk-install/import-settings-done.png)

14. Napsauta **Tuo** ja odota, kunnes prosessi on valmis.

    ![Tuonnin asetukset -näyttö](./media/help-desk-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-list"></a>Määritä PowerApp käyttämään SharePoint-luetteloa

1. Valitse seuraavissa vaiheissa **Avaa sovellus**.
2. Valitse **Salli** oikeutta pyydettäessä.

### <a name="delete-connections"></a>Yhteyksien poistaminen

1. Napsauta **Näkymä**.
2. Napsauta **Tietolähteet**.
3. Napsauta **Tiedot**-ruudussa **kolmea pistettä** **HelpDeskin** SharePoint-yhteyden vieressä.
4. Napsauta **Poista**.

### <a name="helpdesk-list"></a>HelpDesk-luettelo

1. Napsauta **Näkymä**.
2. Napsauta **Tietolähteet**.
3. Napsauta **Tiedot**-ruudussa **+ Lisää tietolähde**.
4. Valitse **SharePoint**.
5. Valitse **Luo**.
6. Valitse **Viimeisimmät sivustot** -luettelosta SharePoint-sivusto, jossa loit HelpDesk-luettelon.

    > [!TIP] 
    > Jos sivusto ei näy luettelossa, kirjoita SharePoint-sivuston URL-osoite tekstikenttään ja napsauta **Siirry**.

7. Syötä luettelon yläosassa olevaan **Haku**-tekstikenttään **HelpDesk**.
8. Valitse **HelpDesk**-luettelon vieressä oleva valintaruutu.
9. Napsauta **Yhdistä**.

### <a name="update-admin-list"></a>Päivitä järjestelmänvalvojien luettelo

1. Valitse **LoginScreen**.
2. Valitse **OnStart** avattavasta valikosta.
3. Laajenna kaavaikkuna ja Etsi **AdminList**-kokoelma.
4. Korvaa <strong>user@microsoft.com</strong> HelpDesk-järjestelmänvalvojillasi.

    ![Päivitä järjestelmänvalvojaluettelo](./media/help-desk-install/Change-admin.png)
    
   > [!TIP]
   > Jos sinulla on useampi kuin yksi järjestelmänvalvoja, käytä pilkkua järjestelmänvalvojien erottelemiseen.  Esimerkki: "admin1@microsoft.com","admin2@microsoft.com".
   > Jos haluat varmistaa, että AdminList-luettelon osoitteet vastaavat PowerAppsin vaatimaa muotoa, valitse Näytä > Muuttujat > Yleiset > Oma profiili ja katso, onko Sähköposti-sarakkeessa vaadittava sähköpostimuoto.

5. Napsauta **Tiedosto**.
6. Napsauta **Tallenna**.
7. Napsauta **Julkaise**.
8. Napsauta **Julkaise tämä versio**.

## <a name="modify-the-flow"></a>Työnkulun muokkaaminen

1.  Valitse vasemmasta valikosta **Työnkulut**.
2.  Jos sinua pyydetään kirjautumaan sisään, kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
3.  Valitse **Omat työnkulut** yläreunan valikosta.
4.  Napsauta **HelpDeskFlow**-työnkulun vieressä olevaa **kynäkuvaketta**. 
 
    ![Muokkaa työnkulun näyttöä](./media/help-desk-install/edit-flow.png)

5.  Laajenna **Hae kohteet** -toiminto. 
6.  Muuta **Sivuston osoite** ja **Luettelonimi** vastaamaan luomaasi HelpDesk SharePoint -luetteloa.
    
    ![Muokkaa työnkulun näyttöä](./media/help-desk-install/edit-flow-getitems.png)

    > [!TIP] 
    > Sinun ei tarvitse kirjoittaa manuaalisesti, voit valita sen avattavasta luettelosta.

7.  Laajenna **Vaihda**.
8.  Laajenna **EI ALOITETTU** -tapaus.
9.  Laajenna **Tapausta ei aloitettu** -toiminto.
10. Muuta **Vastaanottaja** siten, että se vastaa tukipalvelun järjestelmänvalvojan sähköpostiosoitetta.

    ![Muokkaa työnkulun näyttöä](./media/help-desk-install/edit-flow-condition-send-email.png) 

11. Napsauta **Päivitä työnkulku**.

## <a name="play-the-powerapp"></a>Toista PowerApp

1. Napsauta selaimessa kohtaa **Sovellukset**.
2. Napsauta **kolmea pistettä** HelpDesk PowerAppin vieressä.
3. Napsauta **Avaa**. 

> [!TIP]
> Katso tästä [videosta](https://youtu.be/sl5fXwwnvzI), miten Help Desk PowerApp -mallia käytetään.


## <a name="next-steps"></a>Seuraavat vaiheet
- [SharePoint-luettelolomakkeen mukauttaminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Ohjausobjektin lisääminen ja määrittäminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [SharePoint-luettelon tai -kirjaston käyttöoikeuksien muokkaaminen ja hallinta](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)
 
