---
title: Työnkulun luominen projektin hyväksyntien hallintaan | Microsoft Docs
description: Tässä tehtävässä luomme työnkulun, joka ohjaa projektien hyväksyntäprosessia.
author: stepsic-microsoft-com
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: ''
ms.date: 01/09/18
ms.author: stepsic
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: d41807bedf85c151c8e115456b9fb3e23756629d
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/26/2019
ms.locfileid: "57799613"
---
# <a name="create-a-flow-to-manage-project-approvals"></a>Työnkulun luominen projektin hyväksyntien hallintaan
> [!NOTE]
> Tämä artikkeli on osa opetusohjelmasarjaa, joka käsittelee PowerAppsin, Microsoft Flow’n ja Power BI:n käyttämistä SharePoint Onlinen kanssa. Lukemalla [sarjan esittelyn](sharepoint-scenario-intro.md) saat paremman käsityksen kokonaiskuvasta sekä aiheeseen liittyvät ladattavat tiedostot.

Tässä tehtävässä luomme työnkulun, joka ohjaa projektien hyväksyntäprosessia. Microsoft Flow on integroitu SharePointin kanssa, jolloin työnkulku on helppo luoda suoraan luettelosta. Luomamme työnkulku käynnistyy, kun kohde lisätään **projektipyyntöjen** luetteloon. Työnkulku lähettää sähköpostiviestin projektin hyväksyjälle, joka hyväksyy tai hylkää pyynnön suoraan sähköpostiviestissä. Työnkulku lähettää sitten hyväksyntä- tai hylkäyssähköpostiviestin projektin pyytäjälle ja päivittää SharePoint-luettelot tämän mukaan.

## <a name="step-1-configure-the-flow-template"></a>Vaihe 1: Työnkulkumallin määrittäminen
1. Napsauta tai napauta **projektipyyntöjen** luettelossa **Työnkulku** ja sitten **Luo työnkulku**.
   
    ![Työnkulun luominen](./media/sharepoint-scenario-approval-flow/03-01-01-create-flow.png)
2. Napsauta tai napauta oikeanpuoleisessa ruudussa **Aloita hyväksyminen, kun uusi kohde lisätään**.
   
    ![Hyväksynnän työnkulun luominen](./media/sharepoint-scenario-approval-flow/03-01-02-approval-flow.png)
3. Jos et ole vielä kirjautunut, kirjaudu SharePointiin ja Outlookiin ja napsauta tai napauta sitten **Jatka**.
   
    ![Kirjautuminen ja mallin käyttäminen](./media/sharepoint-scenario-approval-flow/03-01-03-continue.png)
   
    Näet nyt tämän työnkulun mallin, joka on valmis täytettäväksi. Työnkulun ruudut edustavat vaiheita. Ne saavat tiedot aiemmista vaiheista sekä antamistasi tiedoista. Kukin vaihe voi näin ollen tuottaa tietoja seuraavia vaiheita varten.
   
    ![Hyväksyntämalli](./media/sharepoint-scenario-approval-flow/03-01-04-template.png)
4. Kirjoita **Vastuuhenkilö**-ruutuun nimi, joka on kelvollinen vuokraajassa.
   
    ![Hyväksyntäsähköpostiviestin yhteyshenkilö](./media/sharepoint-scenario-approval-flow/03-01-05-approval-email.png)
   
    Työnkulun Seuraava ruutu edustaa työnkulun jompaankumpaan kahdesta projektin hyväksyjän päätöstä ja *haaroja*: **Jos Kyllä** tai **Jos ei**.
   
    ![Hyväksynnän ehto](./media/sharepoint-scenario-approval-flow/03-01-06-condition.png)

## <a name="step-2-create-actions-for-approve--yes"></a>Vaihe 2: Hyväksynnän toimintojen luominen = Kyllä
Tämä haara lähettää oletusarvoisesti hyväksyntäsähköpostiviestin pyytäjälle. Päivitämme myös **projektipyyntöjen** luettelon ja lisäämme kohteen **projektitietojen** luetteloon, koska projekti on hyväksytty.

1. Napsauta tai napauta **Jos kyllä** -haarassa **Inform item creator of approval** (Ilmoita hyväksynnästä kohteen tekijälle) ja sitten **Muokkaa**, niin näet pyytäjälle lähetetyn sähköpostiviestin oletusasetukset.
   
    ![Sähköpostiasetusten muokkaaminen](./media/sharepoint-scenario-approval-flow/03-01-07-yes-email.png)
2. Sähköpostiviesti lähetetään oletusarvoisesti luettelokohteen luoneelle henkilölle, ja se sisältää näkemäsi aiherivin ja viestin. Voit halutessasi päivittää niitä.
   
    ![Oletussähköpostiasetukset](./media/sharepoint-scenario-approval-flow/03-01-07a-yes-email-defaults.png)
3. Napsauta tai napauta **Lisää toiminto**.
   
    ![Toiminnon lisääminen](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
4. Etsi kohdasta **Valitse toiminto** ”SharePoint” ja napsauta tai napauta sitten **SharePoint – Päivitä kohde**.
   
    ![Kohteen toiminnon päivitys](./media/sharepoint-scenario-approval-flow/03-00-02-update.png)
5. Kirjoita SharePoint-sivuston URL-osoite ja luettelon nimi.
   
    ![Kohteen parametrien päivitys](./media/sharepoint-scenario-approval-flow/03-00-03-update-list.png)
6. Valitse **Tunnus**-ruutu ja napsauta tai napauta sitten *Dynaaminen sisältö* -valintaikkunassa **Tunnus**.
   
    ![Tunnus dynaamisen sisällön luettelossa](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
   
    Dynaaminen sisältö on käytettävissä koko työnkulun ajan edellisten vaiheiden perusteella. Tässä tapauksessa SharePoint-luettelotiedot ovat käytettävissä ja voimme käyttää niitä luomissamme toiminnoissa.
7. Valitse **Otsikko**-ruutu, etsi dynaamisen sisällön valintaikkunassa ”Otsikko” ja napsauta tai napauta sitten **Otsikko**.
   
    ![Otsikko dynaamisen sisällön luettelossa](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
8. Kirjoita **Hyväksytty**-ruutuun ”Kyllä”. Tämän työnkulun vaiheen pitäisi nyt näyttää samanlaiselta kuin seuraavassa kuvassa.
   
    ![Luettelon päivitys](./media/sharepoint-scenario-approval-flow/03-01-08-yes-update-complete.png)
9. Napsauta tai napauta uudelleen **Lisää toiminto**. Tällä kertaa lisäämme kohteen **projektitietojen** luetteloon hyväksytylle projektille.
   
    ![Toiminnon lisääminen](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
10. Etsi kohdasta **Valitse toiminto** ”SharePoint” ja valitse sitten **SharePoint – Luo kohde**.
    
    ![Kohteen luontitoiminto](./media/sharepoint-scenario-approval-flow/03-01-09-create.png)
11. Kirjoita SharePoint-sivuston URL-osoite ja luettelon nimi.
    
    ![Kohteen parametrien luonti](./media/sharepoint-scenario-approval-flow/03-01-10-yes-create-list.png)
12. Valitse **Otsikko**-ruutu, etsi dynaamisen sisällön valintaikkunassa ”Otsikko” ja napsauta tai napauta sitten **Otsikko**.
    
    ![Otsikko dynaamisen sisällön luettelossa](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
13. Valitse **RequestId**-ruutu ja napsauta tai napauta sitten dynaamisen sisällön valintaikkunassa **Tunnus**.
    
    ![Tunnus dynaamisen sisällön luettelossa](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
14. Kirjoita **PMAssigned**-ruutuun ”Määrittämätön”. Tämän työnkulun vaiheen pitäisi nyt näyttää samanlaiselta kuin seuraavassa kuvassa.
    
    ![Kohteen luonti valmis](./media/sharepoint-scenario-approval-flow/03-01-11-yes-create-complete.png)

## <a name="step-3-review-action-for-approve--no"></a>Vaihe 3: Hyväksyntätoiminnon tarkistaminen = ei
Tämä haara lähettää oletusarvoisesti hylkäyssähköpostiviestin pyytäjälle. Päivitämme myös **projektipyyntöjen** luettelon. Projekti ei etene, joten emme lisää kohdetta **projektitietojen** luetteloon.

1. Napsauta tai napauta **Jos ei** -haarassa **Inform item creator of rejection** (Ilmoita hylkäyksestä kohteen tekijälle) ja sitten **Muokkaa**, niin näet pyytäjälle lähetetyn sähköpostiviestin oletusasetukset.
   
    ![Sähköpostiasetusten muokkaaminen](./media/sharepoint-scenario-approval-flow/03-01-12-no-email.png)
2. Sähköpostiviesti lähetetään oletusarvoisesti luettelokohteen luoneelle henkilölle, ja se sisältää näkemäsi aiherivin ja viestin. Voit halutessasi päivittää niitä.
   
    ![Oletussähköpostiasetukset](./media/sharepoint-scenario-approval-flow/03-01-13-no-email-defaults.png)
3. Napsauta tai napauta **Lisää toiminto**.
   
    ![Toiminnon lisääminen](./media/sharepoint-scenario-approval-flow/03-00-01-add-action.png)
4. Etsi kohdasta **Valitse toiminto** ”SharePoint” ja napsauta tai napauta sitten **SharePoint – Päivitä kohde**.
   
    ![Kohteen toiminnon päivitys](./media/sharepoint-scenario-approval-flow/03-00-02-update.png)
5. Kirjoita SharePoint-sivuston URL-osoite ja luettelon nimi.
   
    ![Kohteen parametrien päivitys](./media/sharepoint-scenario-approval-flow/03-00-03-update-list.png)
6. Valitse **Tunnus**-ruutu ja napsauta tai napauta sitten dynaamisen sisällön valintaikkunassa **Tunnus**.
   
    ![Tunnus dynaamisen sisällön luettelossa](./media/sharepoint-scenario-approval-flow/03-00-04-list-id.png)
7. Valitse **Otsikko**-ruutu, etsi dynaamisen sisällön valintaikkunassa ”Otsikko” ja napsauta tai napauta sitten **Otsikko**.
   
    ![Otsikko dynaamisen sisällön luettelossa](./media/sharepoint-scenario-approval-flow/03-00-05-list-title.png)
8. Kirjoita **Hyväksytty**-ruutuun ”Ei”. Tämän työnkulun vaiheen pitäisi nyt näyttää samanlaiselta kuin seuraavassa kuvassa.
   
    ![Luettelon päivitys](./media/sharepoint-scenario-approval-flow/03-01-08-no-update-complete.png)
9. Napsauta tai napauta näytön oikeassa yläreunassa **Luo työnkulku**.
   
    Työnkulku on nyt valmis, ja sen pitäisi olla seuraavan kuvan mukainen, jos tiivistät ruudut.
   
    ![Valmis työnkulku](./media/sharepoint-scenario-approval-flow/03-01-16-flow-complete.png)

10. Napsauta tai napauta näytön oikeassa yläreunassa **Valmis**.
   
    ![Valmis-painike](./media/sharepoint-scenario-approval-flow/03-01-15a-done-button.png)

## <a name="step-4-run-the-approval-flow"></a>Vaihe 4: Suorita Hyväksyntätyönkulku
1. Napsauta tai napauta **projektipyyntöjen** luettelossa **Nopea muokkaus** ja lisää seuraava kohde:
   
   * **Otsikko** = "New monitor for Megan"

   * **Kuvaus** = "Megan needs a 24" monitor"

   * **ProjectType** = "New hardware"

   * **RequestDate** = "02/03/2017"

   * **Pyytäjä** = "Megan Bowen"

   * **EstimatedDays** = "1"

   * **Hyväksytty** = "Pending"

     ![Kohde lisätty luetteloon](./media/sharepoint-scenario-approval-flow/03-02-01-list-add.png)
2. Kun olet valmis, valitse sivun yläosasta **Valmis**.
   
    ![Valmis-valintamerkki](./media/sharepoint-scenario-approval-flow/03-02-02-done.png)
3. Tarkista hyväksyjän sähköpostitilin Saapuneet-kansio. Sinun pitäisi saada seuraavanlainen sähköpostiviesti.
   
    ![Sähköposti Allan Deyoungille](./media/sharepoint-scenario-approval-flow/03-02-03-allan-email.png)
4. Napsautettuasi **Hyväksy** tai **Hylkää** työnkulku suorittaa toisen prosessin, ja saat seuraavankaltaisen palautteen suoraan sähköpostilla.
   
    ![Hyväksyntätoiminto valmis](./media/sharepoint-scenario-approval-flow/03-02-04-action-complete.png)
5. Työnkulku lähettää Meganille sähköpostiviestin, joka sisältää Allanin vastauksen, kuten seuraavassa kuvassa. Tämä sähköpostiviesti on *peräisin* Meganilta, koska hän omistaa työnkulun.
   
    ![Sähköpostiviesti Megan Bowenille](./media/sharepoint-scenario-approval-flow/03-02-05-megan-email.png)

## <a name="next-steps"></a>Seuraavat vaiheet
Tämän opetusohjelmasarjan seuraava vaihe on [sovelluksen luominen projektien hallitsemista varten](sharepoint-scenario-build-app.md).

