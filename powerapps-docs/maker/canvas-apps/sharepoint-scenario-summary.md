---
title: SharePoint Online -integrointiskenaarion läpikäynti alusta loppuun | Microsoft Docs
description: Tutustu skenaarion alusta loppuun -läpikäyntiin, jonka olemme laatineet tässä opetusohjelmasarjassa.
author: NickWaggoner
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 06/12/2017
ms.author: niwaggon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 64a26fbd0e36937427bc679869d5bc942f254130
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61531360"
---
# <a name="walk-end-to-end-through-the-completed-sharepoint-online-integration-scenario"></a>Käydään läpi valmis SharePoint Onlinen integrointiskenaario alusta loppuun
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa, joka käsittelee PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämistä SharePoint Onlinen kanssa. Lukemalla [sarjan esittelyn](sharepoint-scenario-intro.md) saat paremman käsityksen kokonaiskuvasta sekä aiheeseen liittyvät ladattavat tiedostot.

Tämän sarjan opetusohjelmissa on käsitelty valtava määrä asioita kangassovellusten ja työnkulkujen laatimisesta raporttien luomiseen ja liittämiseen SharePointiin. Toivottavasti olet oppinut paljon ja olet nähnyt tarpeeksi, miten nämä tekniikat integroituvat toisiinsa, jotta voit integroida kangassovelluksia, työnkulkuja ja raportteja SharePointiin omien tarpeidesi mukaan. Ennen kuin lopetamme, haluamme käydä skenaarion läpi alusta loppuun ja nähdä, miten kaikki osat toimivat yhdessä.

## <a name="step-1-add-a-project-to-the-project-requests-list"></a>Vaihe 1: Lisää projekti projektipyynnöt-luetteloon
1. Napsauta tai napauta **Projektipyynnöt**-luettelossa kohtaa **Kaikki kohteet** ja sen jälkeen kohtaa **Projektipyyntöjen sovellus**.
   
    ![Projektipyyntöjen sovelluksen näkymä](./media/sharepoint-scenario-summary/09-00-01-view-app.png)
2. Valitse kohta **Avaa**, joka avaa sovelluksen selaimen uudessa välilehdessä.
   
    ![Avaa projektipyyntösovellus](./media/sharepoint-scenario-summary/09-00-02-open-app.png)
3. Napsauta tai napauta sovelluksessa ![Lisää kohde -kuvaketta](./media/sharepoint-scenario-summary/icon-add-item.png) uuden kohteen luomiseksi.
4. Täytä lomake käyttämällä seuraavia arvoja:
   
   * **Otsikko** = ”Mobiililaitteet suunnittelutiimille”

   * **Hyväksytty** = ”Odottaa”

   * **Kuvaus** = ”Suunnittelutiimi käyttää nyt Contoson toimittamia laitteita”

   * **Arvioidut päivät** = ”30”

   * **Projektin tyyppi** = ”Uudet laitteet”

   * **Pyynnön päivämäärä** = ”03/01/2017”

   * **Pyytäjä** = ”Emily Braun”
     
     ![Projektipyyntöjen muokkaus -luettelo](./media/sharepoint-scenario-summary/09-01-01-app-new.png)
5. Napsauta tai napauta ![Valintamerkki-kuvaketta](./media/sharepoint-scenario-summary/icon-check-mark.png)ja sulje sitten selaimen välilehti.
6. Siirry takaisin **Projektipyynnöt**-luetteloon, napsauta tai napauta **Projektipyyntöjen sovellusta** ja sen jälkeen kohtaa **Kaikki kohteet**.
   
    ![Näytä kaikki kohteet](./media/sharepoint-scenario-summary/09-01-01a-view-all.png)
7. Vahvista, että uusi kohde on luettelossa.
   
    ![SharePoint-luettelo, jossa on uusi kohde](./media/sharepoint-scenario-summary/09-01-02-list-new.png)

## <a name="step-2-approve-the-project"></a>Vaihe 2: Hyväksy projekti
1. Kun lisäät kohteen vaiheessa 1, työnkulun tulisi toimia ja lähettää hyväksyntäsähköposti. Tarkista hyväksyjän sähköpostitilin Saapuneet-kansio.
   
    ![Hyväksymispyyntösähköposti](./media/sharepoint-scenario-summary/09-02-01-allan-email.png)
2. Napsauta **Hyväksy**. Työnkulku suorittaa toisen prosessin, ja saat seuraavan kaltaisen palautteen suoraan sähköpostilla.
   
    ![Toiminto on suoritettu](./media/sharepoint-scenario-summary/09-02-01a-action-complete.png)
3. Tarkista pyytäjän sähköpostitilin Saapuneet-kansio. Hyväksymissähköpostiviestin pitäisi olla näkyvissä.
   
    ![Hyväksymissähköpostiviesti pyytäjälle](./media/sharepoint-scenario-summary/09-02-02-megan-email.png)
4. Vahvista, että uusi kohde on luettelossa.
   
    ![SharePoint-luettelo, jossa on päivitetty kohde](./media/sharepoint-scenario-summary/09-02-03-yes.png)

## <a name="step-3-assign-a-manager-to-the-project"></a>Vaihe 3: Määritä esimies projektiin
1. Katsotaan ensin **Projektitiedot**-luetteloa SharePointissa. Uudella projektilla on arvo **Määrittämätön** sarakkeessa **PMAssigned**.
   
    ![Määrittämätön SharePoint-luettelokohde](./media/sharepoint-scenario-summary/09-03-01-unassigned.png)
2. Napsauta tai napauta **Projektinhallintasovellusta** SharePoint-sivuston vasemmassa siirtymisruudussa.
3. Napsauta tai napauta ensimmäisessä näytössä **Määritä esimies**.
   
    ![Esimiehen määrittäminen projektille](./media/sharepoint-scenario-summary/09-03-02-intro-screen.png)
4. **Määritä esimies** -näytössä näet kaksi määrittämätöntä projektia luettelossa. Valitse **Mobiililaitteet suunnittelutiimille** -projekti.
   
    ![Määrittämätön sovellus valittuna sovelluksessa](./media/sharepoint-scenario-summary/09-03-03-selected.png)
5. Kirjoita **Esimies**-tekstisyötteeseen ”Joni Sherman” ja valitse **OK**.
   
    Luetteloon tehdään muutos, ja valikoima päivittyy, joten vain jäljellä olevat määrittämättömät projektit ovat näkyvissä.
   
    ![Projektiin liitetty esimies](./media/sharepoint-scenario-summary/09-03-04-updated.png)
6. Sulje sovellus ja siirry takaisin SharePoint-luetteloon. Näet, että projektimerkintään on nyt päivitetty projektipäällikön nimi.
   
    ![Määritetty SharePoint-luettelokohde](./media/sharepoint-scenario-summary/09-03-05-assigned.png)

## <a name="step-4-add-time-estimates-for-the-project"></a>Vaihe 4: Lisää aika-arviot projektiin
1. Napsauta tai napauta ![takaisin-kuvaketta](./media/sharepoint-scenario-summary/icon-back.png) siirtyäksesi takaisin ensimmäiseen näyttöön ja napsauta tai napauta sitten **Päivitä tiedot**.
   
    ![Päivitä projektitiedot](./media/sharepoint-scenario-summary/09-04-00-intro-screen.png)
2. Kirjoita **Näytä projektit** -näytössä hakuruutuun ”Mobiili”.
   
    ![Hae sovelluksessa](./media/sharepoint-scenario-summary/09-04-01-search-mobile.png)
3. Napsauta ![tietojen nuolikuvaketta](./media/sharepoint-scenario-summary/icon-details-arrow.png) **Mobiililaitteet suunnittelutiimille** -kohteen kohdalla.
   
    ![Valitse päivitettävä projekti](./media/sharepoint-scenario-summary/09-04-02-select-project.png)
4. Määritä seuraavat arvot **Päivitä tiedot** -näytössä:
   
   * **Tila**-kenttä = ”ei aloitettu”

   * **Projektin aloituspäivämäärä** -kenttä = ”3/6/2017”

   * **Projektin lopetuspäivämäärä** -kenttä = ”3/24/2017”

   * **Ennakoidut päivät** -kenttä = ”15”
     
     ![Päivitä projektitiedot](./media/sharepoint-scenario-summary/09-04-03-update.png)
5. Napsauta tai napauta ![valintamerkki-kuvaketta](./media/sharepoint-scenario-summary/icon-check-mark.png) ottaaksesi muutoksen käyttöön SharePoint-luettelossa.
6. Sulje sovellus ja siirry takaisin luetteloon. Näet, että projektimerkintään on nyt päivitetty päivämäärä- ja päivämuutokset.
   
   ![Tiedot päivitettynä SharePoint-luettelossa](./media/sharepoint-scenario-summary/09-04-04-updated-list.png)

## <a name="step-5-review-report-data-for-existing-projects"></a>Vaihe 5: Tarkastele aiemmin luotujen projektien raporttitietoja
1. Napsauta tai napauta SharePoint online -tilassa **Sivuston sisältö** ja sen jälkeen **Sivuston sivut**.
2. Avaa **Projektianalyysi**-sivu, joka luotiin aiemmin.
   
    ![Upotettu projektin analyysiraportti](./media/sharepoint-scenario-summary/09-05-01-report-complete.png)
3. Tarkastele varianssin visualisointia.
   
    ![Varianssikaavio](./media/sharepoint-scenario-summary/09-05-02-chart-variance.png)
   
    Kuten tätä visualisointia luotaessa mainittiin, Irvin Sayersin johtamissa projekteissa on paljon enemmän varianssia Joni Shermaniin verrattuna.
4. Kun tutkit visualisointia tarkemmin, huomaat, että suuri osa varianssista johtuu kahdesta projektista, jotka kestivät odotettua kauemmin.
   
    ![Kaavio, jossa näkyvät varianssitiedot](./media/sharepoint-scenario-summary/09-05-03-chart-variance-drill.png)
5. Tarkastele taulukkoa, joka näyttää, kuinka kauan projekteilta kestää siirtyä hyväksynnästä arvioituun aloituspäivään.
   
    ![Taulukko, joka näyttää aloituspäivien erot](./media/sharepoint-scenario-summary/09-05-04-chart-diff-completed.png)
   
    Kuten tätä visualisointia luotaessa mainittiin, Irvin Sayersille määritetyissä projektissa aloittamiseen kului enemmän aikaa ja kaksi projektia vei paljon enemmän aikaa kuin muut.

## <a name="step-6-respond-to-pending-project-delays"></a>Vaihe 6: Projektiviiveisiin vastata
1. Napsauta tai napauta Power BI-palvelussa **Projektianalyysi**-tietojoukkoa ja napsauta tai napauta sen jälkeen **PÄIVITÄ NYT**. Päivitys käynnistää hälytyksen, jonka määritimme odottavia projekteja varten.
   
    ![Päivitä tietojoukko nyt](./media/sharepoint-scenario-summary/09-06-01-refresh.png)
2. Kun päivitys on valmis, **ilmoituskeskuksessa** oikeassa yläkulmassa näkyy uusi ilmoituskuvake.
   
    ![Power BI -ilmoituskeskus](./media/sharepoint-scenario-summary/09-06-02-alert.png)
   
    Tämä voi kestää jonkin aikaa, joten palaa tarkistamaan, jos et näe ilmoitusta heti.
3. Avaa ilmoitus ilmoituskeskuksessa, jotta näet annetun hälytyksen tiedot.
   
    ![Tietohälytyksen ilmoitus](./media/sharepoint-scenario-summary/09-06-03-notification.png)
4. Tarkista ilmoituksen luoneen henkilön (tässä tapauksessa Megan Bowenin) Saapuneet-kansio.
   
    ![Hälytyssähköpostiviesti Power BI:stä](./media/sharepoint-scenario-summary/09-06-04-email-powerbi.png)
5. Tarkista henkilön, jonka lisäsit tietohälytysten työnkulkuun (tässä tapauksessa Allan DeYoungin) Saapuneet-kansio.
   
    ![Hälytysviesti Microsoft Flow’sta](./media/sharepoint-scenario-summary/09-06-05-email-flow.png)
6. Nyt kun sinulla on tietoja odottavista projekteista, voit palata takaisin ja hyväksyä asiat, jotka odottavat huomiotasi.

Näin päättyy tämä alusta loppuun -läpikäynti ja tämä opetusohjelmasarja. Suosittelemme jatkamaan matkaasi seuraaville sivustoille:

* [PowerApps](http://www.powerapps.com/)
* [Microsoft Flow](http://flow.microsoft.com)
* [Power BI](http://www.powerbi.com)
* [Power Users Community](https://powerusers.microsoft.com/)
* [SharePoint](http://sharepoint.microsoft.com)
* [Microsoft Tech Community](https://techcommunity.microsoft.com/)

Kerro meille kommentteja, jos sinulla on palautetta tästä sarjasta tai ehdotuksia lisäsisällöstä, joka auttaisi sinua käyttämään käsittelemiämme tekniikoita työssäsi.

