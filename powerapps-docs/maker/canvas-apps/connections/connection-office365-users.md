---
title: Yleiskuvaus Office 365 -käyttäjät -yhteydestä | Microsoft Docs
description: Ohjeet Office 365 -käyttäjien yhteyden luomiseen, muutama esimerkki ja kaikki funktiot
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 06/07/2016
ms.author: lanced
ms.openlocfilehash: a1e0ddd7dad50ec269a0946163cc7b822ddb0681
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34803476"
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
2. Määritä funktiopalkissa sen **[Text](../controls/properties-core.md)**-ominaisuudeksi jokin seuraavista kaavoista:
   
    `Office365Users.MyProfile().Department`  
    `Office365Users.MyProfile().DisplayName`  
    `Office365Users.MyProfile().GivenName`  
    `Office365Users.MyProfile().Id`  
    `Office365Users.MyProfile().JobTitle`  
    `Office365Users.MyProfile().Mail`  
    `Office365Users.MyProfile().MailNickname`  
    `Office365Users.MyProfile().Surname`  
    `Office365Users.MyProfile().TelephoneNumber`  
    `Office365Users.MyProfile().UserPrincipalName`  
    `Office365Users.MyProfile().AccountEnabled`  

Otsikko näyttää tiedot, jotka syötit nykyisestä käyttäjästä.

### <a name="show-information-about-another-user"></a>Toisen käyttäjän tietojen näyttäminen
1. Valitse **Lisää**-valikosta **Teksti** ja valitse sitten **Tekstisyöte**. Anna sille nimi **InfoAbout**:  
   
    ![Ohjausobjektin nimeäminen uudelleen](./media/connection-office365-users/renameinfoabout.png)
2. Kirjoita tai liitä **InfoAbout**-kohtaan jonkin organisaatiosi käyttäjän sähköpostiosoite. Kirjoita esimerkiksi *omanimi*@*yourCompany.com*.
3. Lisää **Otsikko** (**Lisää**-valikko) ja aseta sen **[Text](../controls/properties-core.md)**-ominaisuudeksi jokin seuraavista kaavoista:
   
   * Toisen käyttäjän tietojen näyttäminen:  
     
       `Office365Users.UserProfile(InfoAbout.Text).Department`  
       `Office365Users.UserProfile(InfoAbout.Text).DisplayName`  
       `Office365Users.UserProfile(InfoAbout.Text).GivenName`  
       `Office365Users.UserProfile(InfoAbout.Text).Id`  
       `Office365Users.UserProfile(InfoAbout.Text).JobTitle`  
       `Office365Users.UserProfile(InfoAbout.Text).Mail`  
       `Office365Users.UserProfile(InfoAbout.Text).MailNickname`  
       `Office365Users.UserProfile(InfoAbout.Text).Surname`  
       `Office365Users.UserProfile(InfoAbout.Text).TelephoneNumber`  
       `Office365Users.UserProfile(InfoAbout.Text).UserPrincipalName`  
       `Office365Users.UserProfile(InfoAbout.Text).AccountEnabled`  
   * Toisen käyttäjän esimiehen tietojen näyttäminen:  
     
       `Office365Users.Manager(InfoAbout.Text).Department`  
       `Office365Users.Manager(InfoAbout.Text).DisplayName`  
       `Office365Users.Manager(InfoAbout.Text).GivenName`  
       `Office365Users.Manager(InfoAbout.Text).Id`  
       `Office365Users.Manager(InfoAbout.Text).JobTitle`  
       `Office365Users.Manager(InfoAbout.Text).Mail`  
       `Office365Users.Manager(InfoAbout.Text).MailNickname`  
       `Office365Users.Manager(InfoAbout.Text).Surname`  
       `Office365Users.Manager(InfoAbout.Text).TelephoneNumber`  
       `Office365Users.Manager(InfoAbout.Text).UserPrincipalName`  
       `Office365Users.Manager(InfoAbout.Text).AccountEnabled`  

Otsikko näyttää määrittämäsi käyttäjän tai tämän esimiehen tiedot.

> [!NOTE]
> Jos kehität sovellusta Common Data Service -entiteetin perusteella, voit määrittää käyttäjän tunnuksella sähköpostin sijaan.

Voit esimerkiksi [luoda sovelluksen automaattisesti](../data-platform-create-app.md), lisätä ruudun, joka sisältää **Otsikko**-ohjausobjektin, ja asettaa ohjausobjektin **Text**-ominaisuudeksi tämän kaavan:
<br>**Office365Users.UserProfile(BrowseGallery1.Selected.CreatedByUser).DisplayName**

Jos luot yhteystiedon ja valitset sen sovelluksen selausnäytöllä, **Otsikko**-ohjausobjekti näyttää näyttönimesi.

### <a name="show-the-direct-reports-of-another-user"></a>Toisen käyttäjän suorien alaisten näyttäminen
1. Lisää **Tekstisyöte**-ohjausobjekti (**Lisää**-valikko > **Teksti**) ja anna sille nimi **InfoAbout**.
2. Syötä **InfoAbout**-kohtaan jonkin organisaatiosi käyttäjän sähköpostiosoite. Syötä esimerkiksi *esimiehennimi*@*yourCompany.com*
3. Lisää **Tekstin kanssa** -valikoima (**Lisää**-valikko > **Valikoima**) ja aseta sen **[Items](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    `Office365Users.DirectReports(InfoAbout.Text)`
   
    Valikoima näyttää tiedot syöttämäsi käyttäjän suorista alaisista.
   
    Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
4. Valitse toiseen luetteloon **JobTitle**. Valitse kolmanteen luetteloon **DisplayName**. Valikoima päivittyy ja näyttää nämä arvot.  
   
> [!NOTE]
> Ensimmäinen laatikko on todellisuudessa Kuva-ohjausobjekti. Jos sinulla ei ole kuvaa, voit poistaa Kuva-ohjausobjektin ja korvata sen otsikolla. [Ohjausobjektien lisääminen ja määrittäminen](../add-configure-controls.md) -artikkeli on tässä hyödyllinen.

### <a name="search-for-users"></a>Käyttäjien hakeminen
1. Lisää **Tekstisyöte**-ohjausobjekti (**Lisää**-valikko > **Teksti**) ja anna sille nimi **SearchTerm**. Kirjoita haettava nimi. Kirjoita esimerkiksi etunimesi.
2. Lisää **Tekstin kanssa** -valikoima (**Lisää**-valikko > **Valikoima**) ja aseta sen **[Items](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:
   
    `Office365Users.SearchUser({searchTerm: SearchTerm.Text})`
   
    Valikoima näyttää käyttäjät, joiden nimi sisältää syöttämäsi tekstin.
   
    Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
3. Valitse toiseen luetteloon **Mail**. Valitse kolmanteen luetteloon **DisplayName**.
   
    Valikoiman toinen ja kolmas otsikko päivitetään.

## <a name="view-the-available-functions"></a>Selaa käytettävissä olevia funktioita
Tämä yhteys sisältää seuraavat funktiot:

| Funktion nimi | Kuvaus |
| --- | --- |
| [MyProfile](connection-office365-users.md#myprofile) |Noutaa nykyisen käyttäjän profiilin |
| [UserProfile](connection-office365-users.md#userprofile) |Noutaa määritetyn käyttäjäprofiilin |
| [Esimies](connection-office365-users.md#manager) |Noutaa määritetyn käyttäjän esimiehen käyttäjäprofiilin |
| [DirectReports](connection-office365-users.md#directreports) |Palauttaa määritetyn käyttäjän suorat alaiset |
| [SearchUser](connection-office365-users.md#searchuser) |Noutaa käyttäjäprofiilien hakutulokset |

### <a name="myprofile"></a>MyProfile
Hae oma profiili: noutaa nykyisen käyttäjän profiilin.

#### <a name="input-properties"></a>Syöteominaisuudet
Ei mitään.

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Department |merkkijono |Käyttäjän osasto |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjätunnus |
| JobTitle |merkkijono |Käyttäjän tehtävänimike |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |

### <a name="userprofile"></a>UserProfile
Hae käyttäjän profiili: noutaa määritetyn käyttäjäprofiilin.

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Id |merkkijono |kyllä |Käyttäjän päänimi tai sähköpostitunnus |

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Department |merkkijono |Käyttäjän osasto |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjätunnus |
| JobTitle |merkkijono |Käyttäjän tehtävänimike |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |

### <a name="manager"></a>Esimies
Hae esimies: Noutaa määritetyn käyttäjän esimiehen käyttäjäprofiilin

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Id |merkkijono |kyllä |Käyttäjän päänimi tai sähköpostitunnus |

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Department |merkkijono |Käyttäjän osasto |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjätunnus |
| JobTitle |merkkijono |Käyttäjän tehtävänimike |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |

### <a name="directreports"></a>DirectReports
Hae suorat alaiset: Hae suorat alaiset

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Id |merkkijono |kyllä |Käyttäjän päänimi tai sähköpostitunnus |

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Department |merkkijono |Käyttäjän osasto |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjätunnus |
| JobTitle |merkkijono |Käyttäjän tehtävänimike |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |

### <a name="searchuser"></a>SearchUser
Etsi käyttäjiä: noutaa käyttäjäprofiilien hakutulokset

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| searchTerm |merkkijono |ei |Hakumerkkijono. Koskee seuraavia: näyttönimi, etunimi, sukunimi, sähköposti, lempinimi ja käyttäjän päänimi |

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| Department |merkkijono |Käyttäjän osasto |
| DisplayName |merkkijono |Käyttäjän näyttönimi |
| GivenName |merkkijono |Käyttäjän etunimi |
| Id |merkkijono |Käyttäjätunnus |
| JobTitle |merkkijono |Käyttäjän tehtävänimike |
| Mail |merkkijono |Käyttäjän sähköpostitunnus |
| MailNickname |merkkijono |Käyttäjän lempinimi |
| Surname |merkkijono |Käyttäjän sukunimi |
| TelephoneNumber |merkkijono |Käyttäjän puhelinnumero |
| UserPrincipalName |merkkijono |Käyttäjän päänimi |
| AccountEnabled |totuusarvo |Tili käytössä -merkintä |

## <a name="helpful-links"></a>Hyödyllisiä linkkejä
* Kaikki [käytettävissä olevat yhteydet](../connections-list.md).
* Lue, miten voit [lisätä yhteyksiä](../add-manage-connections.md) sovelluksiisi.

