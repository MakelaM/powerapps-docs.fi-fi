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
ms.openlocfilehash: 166fea9e02ebdaa490b400274c971f0c7268ec76
ms.sourcegitcommit: e64344548d607767e495a6b9526900bb5975226a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/21/2019
ms.locfileid: "58330282"
---
# <a name="install-and-configure-the-expense-report-sample-for-canvas-apps-in-powerapps"></a>Kuluraportti-mallin asentaminen ja määrittäminen pohjaan perustuvassa sovelluksessa PowerAppsissa

Tässä artikkelissa annetaan vaiheittaiset ohjeet Kuluraportti-mallin asentamista ja määrittämistä varten. Voit myös esikatsella mallisovellusta [täältä](https://aka.ms/previewmyexpenses).

Vaiheiden arvioitu kesto: **10‒15 minuuttia**

> [!TIP]
> Katso [tästä videosta](https://youtu.be/kJXZPILfbwU) esittely siitä, miten voit käyttää kuluraporttimallisovellusta. 

Seuraa kuluraportteja niiden lähettämisestä hyväksymiseen. Kirjaa nimikkeitä yksittäisiksi kulukertymiksi ja lähetä ne hyväksyntään, kun ne ovat valmiita. Tämä sovellus edellyttää jonkin verran määrittämistä, jotta saat siitä haluamasi kaltaisen.

![Kuluraportti-PowerAppsin näytön avaaminen](./media/expense-report-install/expense-report-powerapp.png)

> [!TIP]
> Katso [tästä](https://youtu.be/h6E9cdrOvMU) videosta, miten voit käyttää kuluraportti-PowerApps-mallia.

## <a name="prerequisites"></a>Edellytykset

- [Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin.

## <a name="create-the-expenses-sharepoint-list"></a>Kulujen SharePoint-luettelon luominen

Tähän luetteloon tallennetaan kuluraportit.

1. Avaa selain ja siirry kohteeseen https://admin.microsoft.com.
2. Kirjaudu sisään tilillä, jolla on oikeus luoda luetteloita.
3. Siirry sivustokokoelmaan, johon haluat sijoittaa kululuettelon.
4. Napsauta **hammaspyöräkuvaketta** verkkosivun yläosassa oikealla.
5. Napsauta kohtaa **Lisää sovellus**.
6. Syötä **Etsi sovellus** -tekstiruutuun **Mukautettu**.
7. Napsauta **hakukuvaketta**.
8. Napsauta **Custom List** -sovellusta.
9. Syötä **Nimi**-tekstiruutuun **Kulut**.

    > [!IMPORTANT]
    > Jos valitset luettelolle eri nimen, muista kirjoittaa se ylös, sillä sinun täytyy korvata se Kulujen tilalle kaikkialla, missä näet sen asennus- ja määritysprosessin aikana.

10. Napsauta **Luo**.

### <a name="create-cost-center-column"></a>Kustannuskeskus-sarakkeen luominen

1. Napsauta **Kulut**-luetteloa.
2. Napsauta **hammaspyöräkuvaketta** verkkosivun yläosassa oikealla.
3. Napsauta **Luetteloasetukset**.
4. Napsauta **Luo sarake**.
5. Syötä **Sarakkeen nimi** -tekstikenttään**Kustannuskeskus**.
6. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
7. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstikenttään seuraavat arvot, kukin omalle rivilleen: 
    - Microsoft
    - Contoso
8. Syötä **Oletusarvo**-tekstiruutuun **Microsoft**.
9. Napsauta **OK**.

### <a name="create-comments-column"></a>Kommentit-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään **Kommentit**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Useita tekstirivejä**.
4. Napsauta **OK**.

### <a name="create-status-column"></a>Tila-sarakkeen luominen

1. Napsauta **Kulut**-luetteloa.
2. Napsauta **hammaspyöräkuvaketta** verkkosivun yläosassa oikealla.
3. Napsauta **Luetteloasetukset**.
4. Napsauta **Luo sarake**.
5. Syötä **Sarakkeen nimi** -tekstikenttään **Tila**.
6. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Valinta**.
7. Syötä **Kirjoita kukin vaihtoehto omalle rivilleen** -tekstikenttään seuraavat arvot, kukin omalle rivilleen: 
    - Avaa
    - Odottaa
    - Hyväksytty
8. Syötä **Oletusarvo**-tekstiruutuun **Avaa**.
9. Napsauta **OK**.

### <a name="create-approvername-column"></a>ApproverName-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään**ApproverName**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Henkilö tai ryhmä**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-datesubmitted-column"></a>DateSubmitted-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään **DateSubmitted**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Päivämäärä ja aika**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-startdate-column"></a>StartDate-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään **StartDate**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Päivämäärä ja aika**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

### <a name="create-enddate-column"></a>EndDate-sarakkeen luominen

1. Napsauta **Luo sarake**.
2. Syötä **Sarakkeen nimi** -tekstikenttään **EndDate**.
3. Valitse **Tämän sarakkeen tietotyyppi on** -valintanappiluettelossa **Päivämäärä ja aika**.
4. Valitse **Edellytä, että sarake sisältää tietoa** -valintanappiluettelossa **Kyllä**.
5. Napsauta **OK**.

## <a name="create-the-line-items-sharepoint-list"></a>Nimikkeiden SharePoint-luettelon luominen

Tähän luetteloon tallennetaan kuluraportteihin liittyvät nimikkeet.

1. Siirry samaan sivustokokoelmaan, johon loit kululuettelon.
2. Napsauta **hammaspyöräkuvaketta** verkkosivun yläosassa oikealla.
3. Napsauta kohtaa **Lisää sovellus**.
4. Syötä **Etsi sovellus** -tekstiruutuun **Mukautettu**.
5. Napsauta **hakukuvaketta**.
6. Napsauta **Custom List** -sovellusta.
7. Syötä **Nimi**-tekstiruutuun **LineItems**.

    > [!IMPORTANT] 
    > Jos valitset luettelolle eri nimen, muista kirjoittaa se ylös, sillä sinun täytyy korvata se Kulun tilalle kaikkialla, missä näet sen asennus- ja määritysprosessin aikana.

8. Napsauta **Luo**.
 
### <a name="create-category-column"></a>Luokka-sarakkeen luominen

1. Napsauta **LineItems**-luetteloa.
2. Napsauta **hammaspyöräkuvaketta** verkkosivun yläosassa oikealla.
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

## <a name="download-the-expense-report-powerapp"></a>Kuluraportti-PowerAppsin lataaminen

1.  Siirry selaimella seuraavaan linkkiin:

    [http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip](http://pappsfeprodwestuscontent.blob.core.windows.net/sampleapps/myexpenses/docs/MyExpenses(SP_List).zip).

2.  Lataa Kuluraportti-PowerApps-mallipaketti ja tallenna se laitteeseesi.

## <a name="create-connections"></a>Yhteyksien luominen

1.  Siirry selaimella osoitteeseen [web.powerapps.com](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2.  Kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
3.  Valitse vasemmasta valikosta **Yhteydet**.

### <a name="create-approvals-connection"></a>Hyväksynnät-yhteyden luominen

1.  Napsauta kohtaa **+ Uusi yhteys**.
2.  Syötä **Haku**-tekstikenttään **Hyväksynnät**.
3.  Valitse luettelossa **Hyväksynnät**.
4.  Napsauta **Luo**.
    
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

## <a name="import-the-expense-report-powerapp"></a>Kuluraportti-PowerAppsin tuominen

1. Siirry selaimella osoitteeseen https://web.powerapps.com.
2. Kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
3. Valitse vasemmasta valikosta **Sovellukset**. 
4. Napsauta kohtaa **Tuo paketti (esikatselu)**.
    
   ![Tuo paketti -näyttö](./media/expense-report-install/import-package.png)

5. Napsauta **Lataa palvelimeen**-painiketta ja valitse PowerApp-paketti, jonka latasit edellisten vaiheiden aikana.
6. Määritä **App**- ja **Flow**-resurssityypeille **Tuonnin määritykset** -arvoksi **Luo uusina**.
7. Määritä **SharePoint**- ja **Outlook**-yhteyksille **Tuonnin määritykset** -arvoksi **Valitse tuonnin aikana**.
    
   ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings.png)

8. Napsauta **SharePoint-yhteyden** **punaista kuvaketta**.
9. Napsauta yhteydet-luettelossa kohdetta, jossa on käyttäjänimesi.

   ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-sharepoint.png)

10. Napsauta **Tallenna**.
11. Napsauta **Hyväksynnän yhteyden** **punaista kuvaketta**.
12. Napsauta yhteydet-luettelossa kohdetta, jossa on käyttäjänimesi.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-approvals.png)

13. Napsauta **Tallenna**.
14. Napsauta **Office 365 Outlook -yhteyden** **punaista kuvaketta**.
15. Napsauta yhteydet-luettelossa kohdetta, jossa on käyttäjänimesi.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-office365outlook.png)

16. Napsauta **Tallenna**.

    > [!TIP] 
    > Kun olet valmis, se näyttää tältä:

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-settings-done.png)

17. Napsauta **Tuo** ja odota, kunnes prosessi on valmis.

    ![Tuonnin asetukset -näyttö](./media/expense-report-install/import-done.png)

## <a name="configure-the-powerapp-to-use-the-sharepoint-lists"></a>Määritä PowerApp käyttämään SharePoint-luetteloa

1. Napsauta selaimessa kohtaa **Sovellukset**.
2. Napsauta **kolmea pistettä** Kuluraportti-PowerAppsin vieressä.
3. Napsauta **Muokkaa verkossa**.
4. Napsauta **Salli**.

### <a name="delete-connections"></a>Yhteyksien poistaminen
1. Napsauta **Näkymä**.
2. Napsauta **Tietolähteet**.
3. Napsauta **Tiedot**-ruudussa **kolmea pistettä** kohdan **Kulut** vieressä.
4. Napsauta **Poista**.
5. Napsauta **Tiedot**-ruudussa **kolmea pistettä** kohdan **LineItems** vieressä.
6. Napsauta **Poista**.

### <a name="expenses-list"></a>Kulut-luettelo

1. Napsauta **Näkymä**.
2. Napsauta **Tietolähteet**.
3. Napsauta **Tiedot**-ruudussa **+ Lisää tietolähde**.
4. Napsauta **+ Uusi yhteys**.
5. Valitse **SharePoint**.
6. Napsauta **Luo**.
7. Valitse **Viimeisimmät sivustot** -luettelosta SharePoint-sivusto, jossa loit Kulut-luettelon.

    > [!TIP] 
    > Jos sivusto ei näy luettelossa, kirjoita SharePoint-sivuston URL-osoite tekstikenttään ja napsauta **Siirry**.

8. Syötä luettelon yläosassa olevaan **Haku**-tekstikenttään **Kulut**.
9. Valitse **Kulut**-luettelon vieressä oleva valintaruutu.
10. Napsauta **Yhdistä**.

### <a name="lineitems-list"></a>LineItems-luettelo

1. Napsauta **Näkymä**.
2. Napsauta **Tietolähteet**.
3. Napsauta **Tiedot**-ruudussa **+ Lisää tietolähde**.
4. Napsauta **+ Uusi yhteys**.
5. Valitse **SharePoint**.
6. Napsauta **Luo**.
7. Valitse **Viimeisimmät sivustot** -luettelosta SharePoint-sivusto, jossa loit LineItems-luettelon.

    > [!TIP] 
    > Jos sivusto ei näy luettelossa, kirjoita SharePoint-sivuston URL-osoite tekstikenttään ja napsauta **Siirry**.

8. Syötä luettelon yläosassa olevaan **Haku**-tekstikenttään **LineItems**.
9. Valitse **LineItems**-luettelon vieressä oleva valintaruutu.
10. Napsauta **Yhdistä**.
11. Napsauta **Tiedosto**.
12. Napsauta **Tallenna**.
13. Napsauta **Julkaise**.
14. Napsauta **Julkaise tämä versio**.

## <a name="modify-the-flow"></a>Työnkulun muokkaaminen

1.  Valitse vasemmasta valikosta **Työnkulut**.
2.  Jos sinua pyydetään kirjautumaan sisään, kirjaudu sisään antamalla samat tunnistetiedot, joita käytit rekisteröityessäsi.
3.  Valitse yläreunan valikosta **Omat työnkulut**.
4.  Napsauta **ApproveExpense**-työnkulun vieressä olevaa **kynäkuvaketta**.
 
    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow.png)

5.  Laajenna **Hae kohteet** -toiminto. 
6.  Muuta **Sivuston osoite** ja **Luettelonimi** vastaamaan luomaasi Kuluraportti-SharePoint-luetteloa.
    
    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow-getitems.png)

    > [!TIP] 
    > Sinun ei tarvitse kirjoittaa manuaalisesti, voit valita sen avattavasta luettelosta.

7.  Laajenna **Ehto**.
8.  Laajenna **Jos kyllä** -kohtaa.
9.  Laajenna **Vaihda kohteen tilaksi Hyväksytty** -toimintoa.
10. Muuta **Sivuston osoite** ja **Luettelonimi** vastaamaan luomaasi Kuluraportti-SharePoint-luetteloa.

    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow-condition-ifyes.png) 

    > [!TIP] 
    > Sinun ei tarvitse kirjoittaa manuaalisesti, voit valita sen avattavasta luettelosta.

11. Laajenna **Jos ei** -kohtaa.
12. Laajenna **Vaihda kohteen tilaksi Avoin** -toimintoa.
13. Muuta **Sivuston osoite** ja **Luettelonimi** vastaamaan luomaasi Kuluraportti-SharePoint-luetteloa. 

    ![Työnkulun muokkaaminen -näyttö](./media/expense-report-install/edit-flow-condition-ifno.png)

    > [!TIP] 
    > Sinun ei tarvitse kirjoittaa manuaalisesti, voit valita sen avattavasta luettelosta.

14. Napsauta **Päivitä työnkulku**.

## <a name="play-the-powerapp"></a>Toista PowerApp

1. Napsauta selaimessa kohtaa **Sovellukset**.
2. Napsauta **kolmea pistettä** Kuluraportti-PowerAppsin vieressä.
3. Napsauta **Avaa**.


## <a name="next-steps"></a>Seuraavat vaiheet
- [SharePoint-luettelolomakkeen mukauttaminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/customize-list-form)
- [Ohjausobjektin lisääminen ja määrittäminen](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-configure-controls)
- [SharePoint-luettelon tai -kirjaston käyttöoikeuksien muokkaaminen ja hallinta](https://support.office.com/en-us/article/edit-and-manage-permissions-for-a-sharepoint-list-or-library-02d770f3-59eb-4910-a608-5f84cc297782)



