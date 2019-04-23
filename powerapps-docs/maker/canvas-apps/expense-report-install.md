---
title: Kuluraportti-mallin asentaminen ja määrittäminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Tässä artikkelissa annetaan vaiheittaiset ohjeet PowerAppsin Kuluraportti-mallin asentamista ja määrittämistä varten pohjaan perustuvissa sovelluksissa.
author: mr-dang-msft
manager: kvivek
ms.service: powerapps
ms.topic: sample
ms.custom: canvas
ms.reviewer: anneta
ms.date: 04/08/2018
ms.author: brdang
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 4640c1f3fcab1382ec70573cea2ac259cf8b2a30
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61560958"
---
# <a name="install-and-configure-the-expense-report-sample-for-canvas-apps-in-powerapps"></a>Kuluraportti-mallin asentaminen ja määrittäminen pohjaan perustuvassa sovelluksessa PowerAppsissa

Tässä artikkelissa annetaan vaiheittaiset ohjeet Kuluraportti-mallin asentamista ja määrittämistä varten. Voit myös esikatsella mallisovellusta [täältä](https://aka.ms/previewmyexpenses).

Vaiheiden arvioitu kesto: **10‒15 minuuttia**

> [!TIP]
> Katso [tästä videosta](https://youtu.be/kJXZPILfbwU) esittely siitä, miten voit käyttää kuluraporttimallisovellusta. 

Seuraa kuluraportteja niiden lähettämisestä hyväksymiseen. Kirjaa nimikkeitä yksittäisiksi kulukertymiksi ja lähetä ne hyväksyntään, kun ne ovat valmiita. Tämä sovellus edellyttää jonkin verran määrittämistä, jotta saat siitä haluamasi kaltaisen.

![Kuluraportti-PowerAppsin näytön avaaminen](./media/expense-report-install/expense-report-powerapp.png)

> [!TIP]
> Katso [tästä](https://youtu.be/h6E9cdrOvMU) videosta, miten kuluraporttimallia käytetään.

## <a name="prerequisites"></a>Edellytykset

- [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin.

## <a name="create-the-expenses-list"></a>Kulut-luettelon luominen

Tähän luetteloon tallennetaan kuluraportit.

1. Avaa verkkoselain ja siirry kohteeseen https://admin.microsoft.com.
2. Kirjaudu sisään tilillä, jolla on oikeus luoda luetteloita.
3. Siirry sivustokokoelmaan, johon haluat sijoittaa kululuettelon.
4. Napsauta hammaspyöräkuvaketta verkkosivun yläosassa oikealla.
5. Napsauta kohtaa **Lisää sovellus**.
6. Syötä **Etsi sovellus** -tekstiruutuun **Mukautettu**.
7. Napsauta **hakukuvaketta**.
8. Napsauta **Custom List** -sovellusta.
9. Syötä **Nimi**-tekstiruutuun **Kulut**.

    > [!IMPORTANT]
    > Jos valitset luettelolle eri nimen, muista kirjoittaa se ylös, sillä sinun täytyy korvata se Kulut-kohdan tilalle kaikkialla, missä näet sen asennus- ja määritysprosessin aikana.

10. Napsauta **Luo**.

### <a name="create-cost-center-column"></a>Kustannuskeskus-sarakkeen luominen

1. Napsauta **Kulut**-luetteloa.
2. Napsauta hammaspyöräkuvaketta verkkosivun yläosassa oikealla.
3. Napsauta **Luetteloasetukset**.
4. Napsauta **Luo sarake**.
5. Syötä **Sarakkeen nimi** -tekstikenttään**Kustannuskeskus**.
6. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
7. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstiruutuun seuraavat arvot, kukin omalle rivilleen: 
    - Microsoft
    - Contoso
8. Syötä **Oletusarvo**-tekstiruutuun **Microsoft**.
9. Napsauta **OK**.

### <a name="create-comments-column"></a>Kommentit-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstiruutuun **Kommentit**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Useita tekstirivejä**.
4. Napsauta **OK**.

### <a name="create-status-column"></a>Tila-sarakkeen luominen

1. Napsauta **Kulut**-luetteloa.
2. Napsauta **hammaspyöräkuvaketta** verkkosivun yläosassa oikealla.
3. Napsauta **Luetteloasetukset**.
4. Napsauta **Luo sarake**.
5. Syötä **Sarakkeen nimi** -tekstikenttään **Tila**.
6. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
7. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstiruutuun seuraavat arvot, kukin omalle rivilleen: 
    - Avaa
    - Odottaa
    - Hyväksytty
8. Syötä **Oletusarvo**-tekstiruutuun **Avaa**.
9. Napsauta **OK**.

### <a name="create-approvername-column"></a>ApproverName-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstiruutuun **ApproverName**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Henkilö tai ryhmä**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-datesubmitted-column"></a>DateSubmitted-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstiruutuun **DateSubmitted**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Päivämäärä ja aika**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-startdate-column"></a>StartDate-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstiruutuun **StartDate**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Päivämäärä ja aika**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-enddate-column"></a>EndDate-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstiruutuun **EndDate**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Päivämäärä ja aika**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

## <a name="create-the-lineitems-list"></a>LineItems-luettelon luominen

Tähän luetteloon tallennetaan kuhunkin kuluraporttiin liittyvät rivikohteet.

1. Siirry samaan sivustokokoelmaan, johon loit kululuettelon.
2. Napsauta hammaspyöräkuvaketta verkkosivun yläosassa oikealla.
3. Napsauta kohtaa **Lisää sovellus**.
4. Syötä **Etsi sovellus** -tekstiruutuun **Mukautettu**.
5. Napsauta **hakukuvaketta**.
6. Napsauta **Custom List** -sovellusta.
7. Syötä **Nimi**-tekstiruutuun **LineItems**.

    > [!IMPORTANT] 
    > Jos valitset luettelolle eri nimen, muista kirjoittaa se ylös, sillä sinun täytyy korvata se LineItems-kohdan tilalle kaikkialla, missä näet sen asennus- ja määritysprosessin aikana.

8. Napsauta **Luo**.
 
### <a name="create-category-column"></a>Luokka-sarakkeen luominen

1. Napsauta **LineItems**-luetteloa.
2. Napsauta hammaspyöräkuvaketta verkkosivun yläosassa oikealla.
3. Napsauta **Luetteloasetukset**.
4. Napsauta **Luo sarake**.
5. Syötä **Sarakkeen nimi** -tekstikenttään**Luokka**.
6. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
7. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstikenttään seuraavat arvot, kukin omalle rivilleen: 
    - Ruoka ja juoma
    - Kuljetus
    - Yrityksen tarpeet
8. Syötä **Oletusarvo**-tekstiruutuun **Ruoka ja juoma**.
9. Napsauta **OK**.

### <a name="create-cost-column"></a>Kustannus-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään**Kustannus**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Numero (1, 10, 100)**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-date-column"></a>Päivämäärä-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään**Päivämäärä**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Päivämäärä ja aika**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-description-column"></a>Kuvaus-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään**Kuvaus**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Useita tekstirivejä**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Valitse **Määritä sallittavan tekstin tyyppi** -valintanappiluettelossa **Vain teksti**.
6. Napsauta **OK**.

### <a name="create-reportid-column"></a>ReportID-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään **ReportID**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Haku (tämän sivuston tiedoista)**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Valitse avattavasta **Hanki tietoja kohteesta** -luettelosta luomasi **Kulu**-luettelo.
6. Valitse avattavasta **Tässä sarakkeessa** -luettelosta **Tunnus**.
7. Napsauta **OK**.

### <a name="edit-title-column"></a>Otsikko-sarakkeen muokkaaminen

1. Napsauta **Otsikko**-sarakkeen linkkiä.
2. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Ei**.
3. Napsauta **OK**.

## <a name="download-the-expense-report-app"></a>Kuluraporttisovelluksen lataaminen

1. Siirry selaimella seuraavaan linkkiin:

    [http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip).

2. Lataa Kuluraportti-PowerApps-mallipaketti ja tallenna se laitteeseesi.

## <a name="create-connections"></a>Yhteyksien luominen

1.  Siirry selaimella osoitteeseen [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2.  Kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
3.  Valitse vasemmasta valikosta **Yhteydet**.

### <a name="create-an-approvals-connection"></a>Hyväksynnät-yhteyden luominen

1.  Napsauta **+ Uusi yhteys**.
2.  Syötä **Haku**-tekstikenttään **Hyväksynnät**.
3.  Valitse luettelossa **Hyväksynnät**.
4.  Napsauta **Luo**.
    
### <a name="create-an-office-365-outlook-connection"></a>Office 365 Outlook -yhteyden luominen

1.  Napsauta **+ Uusi yhteys**.
2.  Syötä **Haku**-tekstikenttään **Office 365 Outlook**.
3.  Valitse luettelosta **Office 365 Outlook**.
4.  Napsauta **Luo**.
5.  Valitse ponnahdusikkunassa tili, jolla kirjauduit sisään.

### <a name="create-a-sharepoint-connection"></a>SharePoint-yhteyden luominen

1.  Napsauta **+ Uusi yhteys**.
2.  Syötä **Haku**-tekstikenttään **SharePoint**.
3.  Valitse luettelosta **SharePoint**.
4.  Napsauta **Luo**.
5.  Valitse ponnahdusikkunassa tili, jolla kirjauduit sisään.

## <a name="import-the-app"></a>Sovelluksen tuominen

1. Siirry selaimella osoitteeseen https://web.powerapps.com.
1. Kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
1. Valitse vasemmassa siirtymispalkissa **Sovellukset**, ja valitse sitten **Tuo paketti (esikatselu)**.

    ![Tuo paketti -näyttö](./media/expense-report-install/import-package.png)

1. Valitse **Lataa**, ja valitse sitten paketti, jonka latasit aiemmin.
1. Määritä **App**- ja **Flow**-resurssityypeille **Tuonnin määritykset** -arvoksi **Luo uusina**.
1. Määritä **SharePoint**- ja **Outlook**-yhteyksille **Tuonnin määritykset** -arvoksi **Valitse tuonnin aikana**.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings.png)

1. Valitse punainen kuvake **SharePoint-yhteydelle**.
1. Valitse Yhteydet-luettelossa kohde, jossa on käyttäjänimesi.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-sharepoint.png)

1. Valitse **Tallenna**.
1. Valitse punainen kuvake **hyväksyntäyhteydelle**.
1. Valitse Yhteydet-luettelossa kohde, jossa on käyttäjänimesi.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-approvals.png)

1. Valitse **Tallenna**.
1. Valitse punainen kuvake **Office 365 Outlook -yhteydelle**.
1. Valitse Yhteydet-luettelossa kohde, jossa on käyttäjänimesi.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-office365outlook.png)

1. Valitse **Tallenna**.

    > [!TIP] 
    > Kun olet valmis, se näyttää tältä:

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-done.png)

1. Napsauta **Tuo** ja odota sitten, kunnes prosessi on valmis.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-done.png)

## <a name="configure-the-app-to-use-the-sharepoint-lists"></a>Sovelluksen määrittäminen käyttämään SharePoint-luetteloita

1. Valitse verkkoselaimessa **Sovellukset**.
2. Napsauta kolmea pistettä Kuluraportti-sovelluksen vieressä.
3. Valitse **Muokkaa verkossa** > **Salli**.

### <a name="delete-connections"></a>Yhteyksien poistaminen
1. Valitse **Näytä**-välilehdessä **Tietolähteet**.
1. Valitse **Tiedot**-ruudussa kolme pistettä (...) **Kulut**-kohdan vieressä ja valitse sitten **Poista**.
1. Toista edellinen vaihe, jotta voit poistaa **LineItems**- tietolähteen.

### <a name="expenses-list"></a>Kulut-luettelo

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.
1. Valitse **Tiedot**-ruudussa **Lisää tietolähde** > **Uusi yhteys** > **SharePoint** > **Luo**.
1. Valitse **Viimeisimmät sivustot** -luettelosta SharePoint-sivusto, jossa loit Kulut-luettelon.

    > [!TIP] 
    > Jos sivusto ei näy luettelossa, kirjoita tai liitä SharePoint-sivuston URL-osoite tekstiruutuun ja valitse sitten **Siirry**.

1. Kirjoita tai liitä luettelon yläosassa olevaan **Haku**-ruutuun **Kulut**.
1. Valitse **Kulut**-kohdan viereinen valintaruutu ja valitse sitten **Yhdistä**.

### <a name="lineitems-list"></a>LineItems-luettelo

1. Valitse **Näytä**-välilehdessä **Tietolähteet**.
1. Valitse **Tiedot**-ruudussa **SharePoint**.
1. Valitse **Viimeisimmät sivustot** -luettelosta SharePoint-sivusto, jossa loit LineItems-luettelon.

    > [!TIP] 
    > Jos sivusto ei näy luettelossa, kirjoita tai liitä SharePoint-sivuston URL-osoite tekstiruutuun ja valitse sitten **Siirry**.

1. Kirjoita tai liitä luettelon yläosassa olevaan **Haku**-ruutuun **LineItems**.
1. Valitse **LineItems**-kohdan viereinen valintaruutu ja valitse sitten **Yhdistä**.
1. Valitse **Tiedosto** > **Tallenna** > **Julkaise** > **Julkaise tämä versio**.

## <a name="modify-the-flow"></a>Työnkulun muokkaaminen

1. Valitse vasemmassa siirtymispalkissa **Työnkulut**.
1. Jos sinua pyydetään kirjautumaan sisään, anna samat tunnistetiedot, joita käytit rekisteröityessäsi.
1. Valitse lähellä näytön yläreunaa **Omat työnkulut**.
1. Valitse **ApproveExpense**-työnkulun vieressä kynäkuvake.

    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow.png)

1. Laajenna **Hae kohteet** -toiminto. 
1. Muuta **Sivuston osoite** ja **Luettelonimi** vastaamaan SharePointissa luomaasi Kulut-luetteloa.

    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow-getitems.png)

    > [!TIP] 
    > Sinun ei tarvitse kirjoittaa sitä manuaalisesti; voit valita sen avattavasta luettelosta.

1. Laajenna **Ehto**.
1. Laajenna **Jos kyllä** -kohtaa.
1. Laajenna **Vaihda kohteen tilaksi Hyväksytty** -toimintoa.
1. Muuta **Sivuston osoite** ja **Luettelonimi** vastaamaan SharePointissa luomaasi Kulut-luetteloa.

    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow-condition-ifyes.png) 

    > [!TIP] 
    > Sinun ei tarvitse kirjoittaa sitä manuaalisesti; voit valita sen avattavasta luettelosta.

1. Laajenna **Jos ei** -kohtaa.
1. Laajenna **Vaihda kohteen tilaksi Avoin** -toimintoa.
1. Muuta **Sivuston osoite** ja **Luettelonimi** vastaamaan SharePointissa luomaasi Kulut-luetteloa. 

    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow-condition-ifno.png)

    > [!TIP] 
    > Sinun ei tarvitse kirjoittaa sitä manuaalisesti; voit valita sen avattavasta luettelosta.

14. Valitse **Päivitä työnkulku**.

## <a name="play-the-app"></a>Sovelluksen toistaminen

1. Valitse verkkoselaimessa **Sovellukset**.
1. Valitse kolme pistettä (...) Kuluraportti-sovelluksen vieressä ja valitse sitten **Avaa**.

## <a name="next-steps"></a>Seuraavat vaiheet
- [SharePoint-luettelolomakkeen mukauttaminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Ohjausobjektin lisääminen ja määrittäminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [SharePoint-luettelon tai -kirjaston käyttöoikeuksien muokkaaminen ja hallinta](https://support.office.com/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)