---
title: Yleiskuvaus Office 365 -käyttäjät -yhteydestä | Microsoft Docs
description: Ohjeet Office 365 -käyttäjien yhteyden luomiseen, muutama esimerkki ja kaikki funktiot
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/07/2016
ms.author: lanced
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: c9f7f0184f70643417154f229c1e957ea6218b34
ms.sourcegitcommit: fe18d82dbbd3972c472fd69f7feb3a35c3a31153
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/20/2019
ms.locfileid: "71150251"
---
# <a name="connect-to-office-365-users-connection-from-powerapps"></a>Yhdistäminen Office 365 -käyttäjät -yhteyteen PowerAppsissa
![Office 365 -käyttäjät](./media/connection-office365-users/office365icon.png)

Office 365 -käyttäjien avulla voit tarkastella organisaatiosi käyttäjäprofiileja Office 365 -tililläsi. Voit suorittaa erilaisia toimintoja, kuten hakea profiilisi, jonkin käyttäjän profiilin, käyttäjän esimiehen tai suorat alaiset.

Voit näyttää nämä tiedot sovelluksesi otsikossa. Voit näyttää yhden funktion, useita funktioita tai jopa yhdistää eri funktioita. Voit esimerkiksi luoda lausekkeen, joka yhdistää käyttäjänimen ja puhelinnumeron ja näyttää nämä tiedot sovelluksessasi.

Tässä artikkelissa näytetään Office 365 -käyttäjät -yhteyden lisääminen, Office 365 -käyttäjien lisääminen tietolähteenä sovellukseesi ja taulukkotietojen käyttäminen Valikoima-ohjausobjektissa.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="add-a-connection"></a>Yhteyden lisääminen
1. [Lisää tietoyhteys](../add-data-connection.md) ja valitse **Office 365 -käyttäjät**:  

    ![Yhteyden muodostaminen Office 365:een](./media/connection-office365-users/add-office.png)
2. Valitse **Yhdistä**, kirjaudu pyydettäessä sisään ja syötä työtilisi.

Office 365 -käyttäjät -yhteys on luotu ja lisätty sovellukseesi. Se on nyt valmis käytettäväksi.

## <a name="use-the-connection-in-your-app"></a>Yhteyden käyttö sovelluksessasi
### <a name="show-information-about-the-current-user"></a>Nykyisen käyttäjän tietojen näyttäminen
1. Valitse **Lisää**-valikosta **Otsikko**
2. Määritä funktiopalkissa sen **[Text](../controls/properties-core.md)** -ominaisuudeksi jokin seuraavista kaavoista:

   `Office365Users.MyProfile().City`  
   `Office365Users.MyProfile().CompanyName`  
   `Office365Users.MyProfile().Country`  
   `Office365Users.MyProfile().Department`  
   `Office365Users.MyProfile().DisplayName`  
   `Office365Users.MyProfile().GivenName`  
   `Office365Users.MyProfile().Id`  
   `Office365Users.MyProfile().JobTitle`  
   `Office365Users.MyProfile().Mail`  
   `Office365Users.MyProfile().MailNickname`  
   `Office365Users.MyProfile().mobilePhone`  
   `Office365Users.MyProfile().OfficeLocation`  
   `Office365Users.MyProfile().PostalCode`  
   `Office365Users.MyProfile().Surname`  
   `Office365Users.MyProfile().TelephoneNumber`  
   `Office365Users.MyProfile().UserPrincipalName`  
   `Office365Users.MyProfile().AccountEnabled`  
   `Office365Users.MyProfile().BusinessPhones`

Otsikko näyttää tiedot, jotka syötit nykyisestä käyttäjästä.

### <a name="show-information-about-another-user"></a>Toisen käyttäjän tietojen näyttäminen
1. Valitse **Lisää**-valikosta **Teksti** ja valitse sitten **Tekstisyöte**. Anna sille nimi **InfoAbout**:  

    ![Ohjausobjektin nimeäminen uudelleen](./media/connection-office365-users/renameinfoabout.png)
2. Kirjoita tai liitä **InfoAbout**-kohtaan jonkin organisaatiosi käyttäjän sähköpostiosoite. Kirjoita esimerkiksi *omanimi*@*yourCompany.com*.
3. Lisää **Otsikko** (**Lisää**-valikko) ja aseta sen **[Text](../controls/properties-core.md)** -ominaisuudeksi jokin seuraavista kaavoista:

   * Toisen käyttäjän tietojen näyttäminen:  

     `Office365Users.UserProfile(InfoAbout.Text).City`  
     `Office365Users.UserProfile(InfoAbout.Text).CompanyName`  
     `Office365Users.UserProfile(InfoAbout.Text).Country`  
     `Office365Users.UserProfile(InfoAbout.Text).Department`  
     `Office365Users.UserProfile(InfoAbout.Text).DisplayName`  
     `Office365Users.UserProfile(InfoAbout.Text).GivenName`  
     `Office365Users.UserProfile(InfoAbout.Text).Id`  
     `Office365Users.UserProfile(InfoAbout.Text).JobTitle`  
     `Office365Users.UserProfile(InfoAbout.Text).Mail`  
     `Office365Users.UserProfile(InfoAbout.Text).MailNickname`  
     `Office365Users.UserProfile(InfoAbout.Text).mobilePhone`  
     `Office365Users.UserProfile(InfoAbout.Text).OfficeLocation`  
     `Office365Users.UserProfile(InfoAbout.Text).PostalCode`  
     `Office365Users.UserProfile(InfoAbout.Text).Surname`  
     `Office365Users.UserProfile(InfoAbout.Text).TelephoneNumber`  
     `Office365Users.UserProfile(InfoAbout.Text).UserPrincipalName`  
     `Office365Users.UserProfile(InfoAbout.Text).AccountEnabled`  
     `Office365Users.UserProfile(InfoAbout.Text).BusinessPhones`

   * Toisen käyttäjän esimiehen tietojen näyttäminen:  

     `Office365Users.Manager(InfoAbout.Text).City`  
     `Office365Users.Manager(InfoAbout.Text).CompanyName`  
     `Office365Users.Manager(InfoAbout.Text).Country`  
     `Office365Users.Manager(InfoAbout.Text).Department`  
     `Office365Users.Manager(InfoAbout.Text).DisplayName`  
     `Office365Users.Manager(InfoAbout.Text).GivenName`  
     `Office365Users.Manager(InfoAbout.Text).Id`  
     `Office365Users.Manager(InfoAbout.Text).JobTitle`  
     `Office365Users.Manager(InfoAbout.Text).Mail`  
     `Office365Users.Manager(InfoAbout.Text).MailNickname`  
     `Office365Users.Manager(InfoAbout.Text).mobilePhone`  
     `Office365Users.Manager(InfoAbout.Text).OfficeLocation`  
     `Office365Users.Manager(InfoAbout.Text).PostalCode`  
     `Office365Users.Manager(InfoAbout.Text).Surname`  
     `Office365Users.Manager(InfoAbout.Text).TelephoneNumber`  
     `Office365Users.Manager(InfoAbout.Text).UserPrincipalName`  
     `Office365Users.Manager(InfoAbout.Text).AccountEnabled`  
     `Office365Users.Manager(InfoAbout.Text).BusinessPhones`

Otsikko näyttää määrittämäsi käyttäjän tai tämän esimiehen tiedot.

> [!NOTE]
> Jos kehität sovellusta Common Data Service -entiteetin perusteella, voit määrittää käyttäjän tunnuksella sähköpostin sijaan.

Voit esimerkiksi [luoda sovelluksen automaattisesti](../data-platform-create-app.md), lisätä ruudun, joka sisältää **Otsikko**-ohjausobjektin, ja asettaa ohjausobjektin **Text**-ominaisuudeksi tämän kaavan:
<br>**Office365Users.UserProfile(BrowseGallery1.Selected.CreatedByUser).DisplayName**

Jos luot yhteystiedon ja valitset sen sovelluksen selausnäytöllä, **Otsikko**-ohjausobjekti näyttää näyttönimesi.

### <a name="show-the-direct-reports-of-another-user"></a>Toisen käyttäjän suorien alaisten näyttäminen
1. Lisää **Tekstisyöte**-ohjausobjekti (**Lisää**-valikko > **Teksti**) ja anna sille nimi **InfoAbout**.
2. Syötä **InfoAbout**-kohtaan jonkin organisaatiosi käyttäjän sähköpostiosoite. Syötä esimerkiksi *esimiehennimi*@*yourCompany.com*
3. Lisää **Tekstin kanssa** -valikoima (**Lisää**-valikko > **Valikoima**) ja aseta sen **[Items](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:

    `Office365Users.DirectReports(InfoAbout.Text)`

    Valikoima näyttää tiedot syöttämäsi käyttäjän suorista alaisista.

    Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
4. Valitse toiseen luetteloon **JobTitle**. Valitse kolmanteen luetteloon **DisplayName**. Valikoima päivittyy ja näyttää nämä arvot.  

> [!NOTE]
> Ensimmäinen laatikko on todellisuudessa Kuva-ohjausobjekti. Jos sinulla ei ole kuvaa, voit poistaa Kuva-ohjausobjektin ja korvata sen otsikolla. [Ohjausobjektien lisääminen ja määrittäminen](../add-configure-controls.md) -artikkeli on tässä hyödyllinen.

### <a name="search-for-users"></a>Käyttäjien hakeminen
1. Lisää **Tekstisyöte**-ohjausobjekti (**Lisää**-valikko > **Teksti**) ja anna sille nimi **SearchTerm**. Kirjoita haettava nimi. Kirjoita esimerkiksi etunimesi.
2. Lisää **Tekstin kanssa** -valikoima (**Lisää**-valikko > **Valikoima**) ja aseta sen **[Items](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:

    `Office365Users.SearchUser({searchTerm: SearchTerm.Text})`

    Valikoima näyttää käyttäjät, joiden nimi sisältää syöttämäsi tekstin.

    Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
3. Valitse toiseen luetteloon **Mail**. Valitse kolmanteen luetteloon **DisplayName**.

    Valikoiman toinen ja kolmas otsikko päivitetään.

## <a name="view-the-available-functions"></a>Selaa käytettävissä olevia funktioita
Tämä yhteys sisältää seuraavat funktiot:

| Funktion nimi | Kuvaus |
| --- | --- |
| [DirectReports](connection-office365-users.md#directreports) |Palauttaa määritetyn käyttäjän suorat raportit. |
| [Esimies](connection-office365-users.md#manager) |Noutaa määritetyn käyttäjän esimiehen käyttäjä profiilin. |
| [MyProfile](connection-office365-users.md#myprofile) |Noutaa nykyisen käyttäjän profiilin. |
| [SearchUser](connection-office365-users.md#searchuser) |Noutaa käyttäjä profiilien haku tulokset. |
| [UserProfile](connection-office365-users.md#userprofile) |Noutaa tietyn käyttäjä profiilin. |

### <a name="myprofile"></a>MyProfile
Hae profiilini: Noutaa nykyisen käyttäjän profiilin.

#### <a name="input-properties"></a>Syöteominaisuudet
Ei mitään.

#### <a name="output-properties"></a>Tulosteominaisuudet

| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Postitoimipaikka | merkkijono |Käyttäjä kaupunki. |
| CompanyName | merkkijono |Käyttäjän yritys. |
| Maa | merkkijono |Käyttäjän maa. |
| Department |merkkijono |Käyttäjän osasto. |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjä tunnus. |
| JobTitle |merkkijono |Käyttäjän työnimike. |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Matka Puhelin varustus | merkkijono |Käyttäjän matka puhelin. |
| OfficeLocation | merkkijono |Käyttäjän toimiston sijainti.|
| PostalCode | merkkijono |Käyttäjän posti numero.|
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |
| BusinessPhones | merkkijono |Käyttäjän yrityksen Puhelin numerot.|

### <a name="userprofile"></a>UserProfile
Hae käyttäjä profiili: Noutaa tietyn käyttäjä profiilin.

#### <a name="input-properties"></a>Syöteominaisuudet

| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Id |merkkijono |kyllä |Käyttäjän päänimi tai sähkö posti tunnus. |

#### <a name="output-properties"></a>Tulosteominaisuudet

| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Postitoimipaikka | merkkijono |Käyttäjä kaupunki. |
| CompanyName | merkkijono |Käyttäjän yritys. |
| Maa | merkkijono |Käyttäjän maa. |
| Department |merkkijono |Käyttäjän osasto. |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjä tunnus. |
| JobTitle |merkkijono |Käyttäjän työnimike. |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |
| BusinessPhones | merkkijono |Käyttäjän yrityksen Puhelin numerot.|

### <a name="manager"></a>Esimies
Hae esimies: Noutaa määritetyn käyttäjän esimiehen käyttäjä profiilin.

#### <a name="input-properties"></a>Syöteominaisuudet

| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Id |merkkijono |kyllä |Käyttäjän päänimi tai sähkö posti tunnus. |

#### <a name="output-properties"></a>Tulosteominaisuudet

| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Postitoimipaikka | merkkijono |Käyttäjä kaupunki. |
| CompanyName | merkkijono |Käyttäjän yritys. |
| Maa | merkkijono |Käyttäjän maa. |
| Department |merkkijono |Käyttäjän osasto. |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjä tunnus. |
| JobTitle |merkkijono |Käyttäjän työnimike. |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Matka Puhelin varustus | merkkijono |Käyttäjän matka puhelin. |
| OfficeLocation | merkkijono |Käyttäjän toimiston sijainti.|
| PostalCode | merkkijono |Käyttäjän posti numero.|
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |
| BusinessPhones | merkkijono |Käyttäjän yrityksen Puhelin numerot.|

### <a name="directreports"></a>DirectReports
Hae suorat raportit: Hae suoria raportteja.

#### <a name="input-properties"></a>Syöteominaisuudet

| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Id |merkkijono |kyllä |Käyttäjän päänimi tai sähkö posti tunnus. |

#### <a name="output-properties"></a>Tulosteominaisuudet

| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Postitoimipaikka | merkkijono |Käyttäjä kaupunki. |
| CompanyName | merkkijono |Käyttäjän yritys. |
| Maa | merkkijono |Käyttäjän maa. |
| Department |merkkijono |Käyttäjän osasto. |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjä tunnus. |
| JobTitle |merkkijono |Käyttäjän työnimike. |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Matka Puhelin varustus | merkkijono |Käyttäjän matka puhelin. |
| OfficeLocation | merkkijono |Käyttäjän toimiston sijainti.|
| PostalCode | merkkijono |Käyttäjän posti numero.|
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |
| BusinessPhones | merkkijono |Käyttäjän yrityksen Puhelin numerot.|

### <a name="searchuser"></a>SearchUser
Hae käyttäjiä: Noutaa käyttäjä profiilien haku tulokset.

#### <a name="input-properties"></a>Syöteominaisuudet

| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| searchTerm |merkkijono |ei |Hakumerkkijono. Koskee seuraavia: näyttö nimi, etunimi, suku nimi, sähkö posti, sähkö postin lempi nimi ja täydellinen käyttäjä tunnus. |

#### <a name="output-properties"></a>Tulosteominaisuudet

| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Postitoimipaikka | merkkijono |Käyttäjä kaupunki. |
| CompanyName | merkkijono |Käyttäjän yritys. |
| Maa | merkkijono |Käyttäjän maa. |
| Department |merkkijono |Käyttäjän osasto. |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjä tunnus. |
| JobTitle |merkkijono |Käyttäjän työnimike. |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Matka Puhelin varustus | merkkijono |Käyttäjän matka puhelin. |
| OfficeLocation | merkkijono |Käyttäjän toimiston sijainti.|
| PostalCode | merkkijono |Käyttäjän posti numero.|
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |
| BusinessPhones | merkkijono |Käyttäjän yrityksen Puhelin numerot.|

## <a name="helpful-links"></a>Hyödyllisiä linkkejä
* Kaikki [käytettävissä olevat yhteydet](../connections-list.md).
* Lue, miten voit [lisätä yhteyksiä](../add-manage-connections.md) sovelluksiisi.

