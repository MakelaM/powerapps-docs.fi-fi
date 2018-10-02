---
title: Mallipohjaisen sovelluksen näkymien sarakkeiden valitseminen ja määrittäminen PowerAppsissa | MicrosoftDocs
description: Tietoja sovelluksen näkymien valitsemisesta ja määrittämisestä
keywords: ''
ms.date: 06/11/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: 31bfcf18-58c3-491c-91b5-f9b0f5424852
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 25
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-choose-and-configure-columns-in-model-driven-app-views"></a>Opetusohjelma: Mallipohjaisen sovelluksen näkymien sarakkeiden valitseminen ja määrittäminen

<a name="BKMK_ChooseAndConfigureColumns"></a>   

 Suodatusehtojen lisäksi PowerAppsin näkymässä näkyvät sarakkeet ovat erittäin tärkeitä näkymässä annetulle arvolle. Tässä opetusohjelmassa luodaan ja muokataan näkymiä seuraavien tehtävien avulla:  

-   [Näkymäeditorin avaaminen](choose-and-configure-columns.md#open-the-view-editor)  
   
-   [Sarakkeiden lisääminen](choose-and-configure-columns.md#BKMK_AddColumns)  
  
-   [Sarakkeiden poistaminen](choose-and-configure-columns.md#BKMK_RemoveColumns)  
  
-   [Sarakeleveyden muuttaminen](choose-and-configure-columns.md#BKMK_ChangeColumnWidth)  
  
-   [Sarakkeen siirtäminen](choose-and-configure-columns.md#BKMK_MoveAColumns)  
  
-   [Ota käyttöön tavoitettavuus tai poista se käytöstä sarakkeelle](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence)  
  
-   [Lisää hakusarakkeita](choose-and-configure-columns.md#BKMK_AddFindColumns)  

### <a name="open-the-view-editor"></a>Näkymäeditorin avaaminen

1.  Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

    ![Mallipohjainen suunnittelutila](../model-driven-apps/media/model-driven-switch.png)

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Näkymät**-välilehti. 

    > [!div class="mx-imgBorder"] 
    > ![Näkymät](media/available-views.png)

3. Avaa olemassa oleva näkymä valitsemalla se tai valitsemalla työkaluriviltä **Lisää näkymä**. 

<a name="BKMK_AddColumns"></a>   
### <a name="add-columns"></a>Sarakkeiden lisääminen  
 Voit lisätä nykyisen entiteetin tai jonkin liitetyistä entiteeteistä, joilla on 1:N entiteettisuhde nykyisen entiteetin kanssa.  
  
 Esimerkiksi haluat ehkä näyttää käyttäjän omistamien entiteettien omistajat sarakkeessa. Voit valita nykyisen entiteetin **Omistaja** -kentän omistajan nimen esittämiseksi. Tämä näkyy linkkinä, josta avautuu **Käyttäjä**-tietue henkilölle, joka on omistaja. Tällöin voit myös halutessasi [ottaa käyttöön tai poistaa käytöstä tavoitettavuussarakkeen](choose-and-configure-columns.md#BKMK_EnableOrDisablePresence).  
  
 Jos haluat näyttää tietueen omistajan puhelinnumeron, sinun on valittava **omistajakäyttäjä (User)** **tietuetyypin** avattavasta valikosta ja valitse sitten **Ensisijainen puhelin** -kenttä.  
  
#### <a name="add-columns-to-views"></a>Sarakkeiden lisääminen näkymään  
  
1.  Valitse näkymien luomisen ja muokkaamisen aikana **Lisää sarakkeita**. 

    > [!div class="mx-imgBorder"] 
    > ![Näkymäeditorin sarakkeiden lisääminen](media/view-editor.png)

    Näyttöön tulee **Lisää sarakkeita** -valintaikkuna.

    > [!div class="mx-imgBorder"] 
    > ![Sarakkeiden lisääminen](media/add-columns.png)
  
2.  Valitse **Tietuetyyppi** , jos haluat sisällyttää liittyvien entiteettien kentät.  
  
3.  Voit valita useita kenttiä, vaikka liitetyistä entiteeteistä.  
  
4.  Kun olet valinnut haluamasi kentät, valitse **OK** sulkeaksesi **Lisää sarakkeet** -valintaikkuna.  
  
 Kun lisäät sarakkeita, kasvatat näkymän leveyttä. Jos näkymän leveys ylittää tilan, jolla sivu on näkyvissä, vaakasuorat vierityspalkit sallivat ihmisille piilotettujen sarakkeiden vierittämisen ja näkemisen.  
  
> [!TIP]
>  Jos näkymä suodattaa tietyn kentän tiedot siten, että näkyvissä ovat vain ne tietueet, joilla on tietty arvo, älä sisällytä sitä saraketta näkymään. Esimerkiksi jos näkyvissä ovat vain aktiiviset tietueet, älä sisällytä tilasaraketta näkymään. Sen sijaan nimeä näkymä niin, että kaikki näkymässä näkyvät tietueet ovat aktiivisia.  
  
> [!NOTE]
>  Kun lisäät sarakkeita päivitettyjen kohteiden valintanäkymille, vain kolme ensimmäistä saraketta näytetään.  
  
<a name="BKMK_RemoveColumns"></a>   
### <a name="remove-columns"></a>Sarakkeiden poistaminen  
  
1.  Kun luot ja muokkaat näkymiä, valitse sarake, jonka haluat poistaa.  
  
2.  Valitse **Yleiset tehtävät** -alueella **Poista**.  
  
3.  Valitse vahvistussanomassa **OK**.  
  
<a name="BKMK_ChangeColumnWidth"></a>   
### <a name="change-column-width"></a>Sarakeleveyden muuttaminen  
  
1.  Kun luot ja muokkaat näkymiä, valitse sarake, jonka haluat muuttaa.  
  
2.  Valitse **Yleiset tehtävät** -alueella **Ominaisuuksien muuttaminen**.  
  
3.  Valitse **Muuta sarakkeen ominaisuudet** -valintaikkunassa vaihtoehto sarakeleveyden määrittämiseksi ja valitse sitten **OK**.  
  
<a name="BKMK_MoveAColumns"></a>   
### <a name="move-a-column"></a>Sarakkeen siirtäminen  
  
1.  Kun luot ja muokkaat näkymiä, valitse sarake, jonka haluat siirtää.  
  
2.  Voit siirtää saraketta **Yleiset tehtävät** -alueessa vasemmalle tai oikealle nuolipainikkeiden avulla.  
  
<a name="BKMK_EnableOrDisablePresence"></a>   
### <a name="enable-or-disable-presence-for-a-column"></a>Ota käyttöön tavoitettavuus tai poista se käytöstä sarakkeelle  
 Kun seuraavat ehdot toteutuvat, käyttäjät näkevät Skype for Businessin online-tilan luettelot, joista voi tarkistaa, onko tietty henkilö tavoitettavissa, ja joissa henkilöihin voi olla yhteydessä pikaviestinnällä:  
  
-   Henkilöt käyttävät Edge- tai Internet Explorer -selainta.  
  
-   Henkilöt ovat asentaneet Skype for Businessin.  
  
-   Henkilöt ovat ottaneet Microsoft ActiveX:n käyttöön Internet Explorerissa.  
  
-   Organisaatiossa on otettu käyttöön järjestelmän esiintyminen järjestelmäasetuksissa.  
  
 Läsnäolo-ohjaus ja -asetus, jotta se on käytettävissä, on vain sarakkeissa, joissa näkyy ensisijaiset kentät sähköpostientiteeteille (käyttäjät, yhteystiedot, mahdollisuuksia, liidejä tai mukautettuja entiteettejä).  
  
#### <a name="enable-or-disable-skype-for-business-presence-for-a-column"></a>Sarakkeen Skype for Business -tavoitettavuuden ottaminen käyttöön tai poistaminen käytöstä  
  
1.  Kun luot ja muokkaat näkymiä, valitse sarake, jonka haluat muuttaa.  
  
2.  Valitse **Yleiset tehtävät** -alueella **Ominaisuuksien muuttaminen**.  
  
3.  Valitse **Muuta sarakkeen ominaisuudet** -valintaikkunassa **Ota käyttöön tavoitettavuus tälle sarakkeelle** tai poista sen valinta ja valitse sitten **OK**.  
  
<a name="BKMK_AddFindColumns"></a>   
### <a name="add-find-columns"></a>Lisää hakusarakkeita  
 Hakusarakkeet ovat sarakkeita, joita sovellus on etsinyt, kun ihmiset käyttävät saraketta **tietueiden etsiminen** -muokkausruutua, joka näkyy luetteloita varten tai aina, kun on mahdollisuus etsiä sovelluksen entiteettiä, kuten kun ihmiset etsivät tietuetta hakuruutua varten.  
  
1.  Avaa **pikahakunäkymä**. Lisätietoja pikahakunäkymistä on kohdassa [Näkymien tyypit](create-edit-views.md#types-of-views).  
  
2.  Valitse **Lisää hakusarakkeet**, kun haluat avata valintaikkunan.  
  
3.  Valitse kentät, jotka sisältävät tietoja, joita haluat etsiä.  
  
4.  Valitse **OK**, kun haluat sulkea **Lisää hakusarakkeet** -valintaikkunan.  

## <a name="community-tools"></a>Yhteisön työvälineet

**Näkymän asettelun replikoija** ja **Näkymän suunnitteluohjelma** ovat XrmToolbox-yhteisön Dynamics 365 Customer Engagement -sovellukselle kehittämiä työkaluja. Katso [Kehitystyökalut](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools) ohjeaihetta yhteisön kehittämistä työkaluista.

> [!NOTE]
> Yhteisön työkalut eivät ole Microsoft Dynamics -tuotteita. Yhteisön työkaluja ei tueta. Jos sinulla on kysymyksiä työkalusta, ota yhteyttä julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com). 

## <a name="next-steps"></a>Seuraavat vaiheet
[Näkymien luominen tai muokkaaminen](create-edit-views.md)
