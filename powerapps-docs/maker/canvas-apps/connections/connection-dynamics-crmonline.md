---
title: Dynamics 365 -yhteyden yleiskatsaus | Microsoft Docs
description: Luo sovellus tietojen hallintaa varten Dynamics 365:ssä
author: Mattp123
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 07/12/2017
ms.author: matp
ms.reviewer: ''
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 3c061d43a766bfdcd0a560c5959756f79751a7f2
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61547273"
---
# <a name="connect-to-dynamics-365-from-powerapps"></a>Yhdistä Dynamics 365:een PowerAppsista
PowerAppsin avulla voit nopeasti luoda, mukauttaa, jakaa ja suorittaa mobiilisovelluksia käyttäen vain vähän tai ei lainkaan koodia. Dynamics 365 -liittimen avulla voit luoda hyödyllisiä mobiilisovelluksia organisaatiollesi jaettaviksi vain muutamassa minuutissa.

Tämän artikkelin ohjeiden mukaisesti luot sovelluksen, jolla käyttäjät voivat selata, lisätä, poistaa ja tehdä päivityksiä yhteystietoihin Dynamics 365:ssä. Käyttäjät voivat suorittaa sovelluksen [selaimessa](../../../user/run-app-browser.md) tai [mobiililaitteessa](../../../user/run-app-client.md), kuten puhelimessa.

## <a name="prerequisite"></a>Edellytys
Jotta voit seurata tätä opetusohjelmaa, tarvitset Microsoft Office 365 -tilin, joka sisältää Dynamics 365 -tilauksen.

## <a name="create-a-connection"></a>Luo yhteys
1. [Kirjaudu sisään PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
2. Napsauta vasemmassa siirtymisruudussa **Yhteydet**.
   
    ![Yhteys-vaihtoehto Tiedosto-valikossa](./media/connection-dynamics-crmonline/file-connections.png)
3. Napsauta oikean yläkulman lähellä **Uusi yhteys**.
   
    ![Uusi yhteys](./media/connection-dynamics-crmonline/new-connection.png)
4. Napsauta yhteyksien luettelossa vaihtoehtoa **Dynamics 365**.
   
    ![Yhteys-vaihtoehto Tiedosto-valikossa](./media/connection-dynamics-crmonline/connection-d365.png)
5. Napsauta valintaikkunassa **Luo**.
   
    ![Yhteyden luominen](./media/connection-dynamics-crmonline/create-connection.png)
6. Kirjoita **Kirjaudu tilillesi** -valintaikkunassa Dynamics 365 (online) -vuokraajan tunnistetietosi.
   
    Yhteys on luotu.

## <a name="generate-an-app-automatically"></a>Luo sovellus automaattisesti
1. [Kirjaudu sisään PowerAppsiin](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja valitse sitten **Uusi sovellus** lähellä vasenta alakulmaa.
   
    ![Uusi sovellus](./media/connection-dynamics-crmonline/new-app.png)
2. Napsauta kohdassa **Aloita tiedoillasi** **Puhelinasettelu** **Dynamics 365** -ruudussa.
   
    ![PowerApps – valitse Dynamics 365 -liitin](./media/connection-dynamics-crmonline/phonelayout.png)
3. Valitse kohdassa **Yhteydet** haluamasi yhteys ja valitse sitten tietojoukko, joka vastaa Dynamics 365:n esiintymää, jota haluat hallita sovelluksessa.
4. Napsauta kohdassa **Valitse taulukko** **Yhteystiedot** ja valitse sitten **Yhdistä**.
5. Voit vaihtaa pikkukuvanäkymään napsauttamalla tai napauttamalla vasemman navigointipalkin oikeassa yläkulmassa olevaa kuvaketta.
   
    ![Näkymien vaihtaminen](./media/connection-dynamics-crmonline/toggle-view.png)

PowerApps luo kolmen näytön sovelluksen yhteyshenkilötietueiden perusteella.

* **BrowseScreen1**. Tämä näyttö näkyy oletusarvoisesti, kun käyttäjät avaavat sovelluksen. Tämän näytön pikkukuva ilmestyy vasempaan siirtymispalkkiin kahden muun näytön yläpuolelle.
* **DetailScreen1**. Tämä näyttö tulee näkyviin, kun käyttäjä napsauttaa **BrowseScreen1**-näytössä olevaa kohdetta.  Vasempaan siirtymispalkkiin tulee näkyviin näytön **DetailScreen1** pikkukuva kahden muun näytön väliin.
* **EditScreen1**. Tämä näyttö tulee näkyviin, kun käyttäjä napsauttaa kohteen muokkauskuvaketta **DetailScreen1**-näytössä. Vasempaan siirtymispalkkiin tulee näkyviin näytön **EditScreen1** pikkukuva kahden muun näytön alapuolelle.

Sovellus voi toimia alkutilassaan, mutta voimme tehdä siitä hyödyllisemmän jalostamalla kunkin näytön tietoja.

## <a name="customize-browsescreen1"></a>Mukauta BrowseScreen1
Tässä toimenpiteessä määrität **BrowseScreen1**:n näyttämään jokaisen yhteystiedon etu- ja sukunimet. Tiedot lajitellaan aakkosjärjestykseen sukunimen mukaan ja kuvat sisällytetään mukaan kahden sarakkeen ruudukossa.

1. Valitse **BrowseScreen1**:ssä valikoima napsauttamalla mitä tahansa sen tietueista ensimmäistä lukuun ottamatta.
   
    ![Asettelun valitseminen](./media/connection-dynamics-crmonline/select-gallery.png)
2. Napsauta tai napauta oikean ruudun välilehteä **Tiedot**.
3. Napsauta tai napauta asettelujen luettelossa asettelua, joka näyttää kuvia ja tekstiä kahden sarakkeen ruudukossa.
   
    Joudut ehkä vierittämään näyttöä alaspäin nähdäksesi tämän asetuksen.
   
    ![Asettelun valitseminen](./media/connection-dynamics-crmonline/select-layout.png)
4. Kopioi tämä kaava ja liitä se valikoiman ollessa edelleen valittuna kaavariville (**fx**-painikkeen oikealle puolelle):
   
    `SortByColumns(Search(Filter(Contacts,statuscode=1), TextSearchBox1.Text, "lastname"), "lastname", If(SortDescending1, Descending, Ascending))`
5. Valitse oikeanpuoleisessa ruudussa yläreunan avattavan luettelon kohta **firstname** ja keskimmäisen avattavan luettelon kohta **lastname**.
   
    ![Valitse Body1](./media/connection-dynamics-crmonline/firstname-lastname.png)
6. (valinnainen) Napsauta **Tiedosto**-valikon kohtaa **Tallenna nimellä**, kirjoita sovelluksen nimi ja valitse sitten **Tallenna**.
   
    Sovellus tallennetaan oletusarvoisesti pilveen. Napsauta **Tämä tietokone**, jos haluat tallentaa sovelluksen paikallisesti.

## <a name="customize-detailsscreen1-and-editscreen1"></a>Näyttöjen DetailsScreen1 ja EditScreen1 mukauttaminen
1. Valitse vasemmassa navigointipalkissa **DetailsScreen1** napsauttamalla keskimmäistä pikkukuvaa.
2. Napsauta **DetailScreen1**-näytössä mitä tahansa kohtaa otsikkorivin alapuolella nähdäksesi mukautusasetukset oikeanpuoleisessa ruudussa.
   
    ![Näytä lomakkeen mukauttaminen](./media/connection-dynamics-crmonline/show-customization.png)
3. Napsauta oikeanpuoleisessa ruudussa jokaisen kentän silmäkuvaketta piilottaaksesi ne.
   
    ![Piilota kentät](./media/connection-dynamics-crmonline/hide-field.png)
4. Napsauta mitä tahansa kohtaa otsikkorivin alla valitaksesi **Form1**-lomakkeen.
   
    ![Valitse Form1](./media/connection-dynamics-crmonline/select-form1.png)
5. Napsauta oikeanpuoleisessa ruudussa silmäkuvaketta kullekin näistä kentistä siten, että näytössä näkyy kuva (jos taulukko sisältää sellaisen) ja neljä muuta kenttää:
   
   * **entityimage**
   * **firstname**
   * **lastname**
   * **mobilephone**
   * **emailaddress1**
     
     Oikeanpuoleisen ruudun pitäisi muistuttaa tätä kaaviota:
     
     ![Valitse Form1](./media/connection-dynamics-crmonline/show-fields.png)
6. Valitse **EditScreen1** napsauttamalla vasemman siirtymispalkin alinta pikkukuvaa.
7. Toista tämän toimintosarjan vaiheet mukauttaaksesi **EditScreen1**-näyttöä samalla tavalla kuin mukautit **DetailsScreen1**-näyttöä.
8. (valinnainen) Tallenna sovellus.

## <a name="next-steps"></a>Seuraavat vaiheet
* Testaa sovellustasi esikatselutilassa napsauttamalla **BrowseScreen1**-näyttöä vasemmassa siirtymispalkissa ja painamalla sitten F5-näppäintä tai valitsemalla ![esikatselutilan](./media/connection-dynamics-crmonline/runpowerapp.png) oikean yläkulman läheltä.
* [Jaa sovelluksesi](../share-app.md).
* [Lisää toinen tietolähde](../add-data-connection.md).

