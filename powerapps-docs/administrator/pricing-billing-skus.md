---
title: Yleiskatsaus käyttöoikeuksiin | Microsoft Docs
description: Yleiskatsaus käyttöoikeuksiin PowerAppsissa.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 04/24/2018
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 4eb1cdb3fb54780c693bb764bdf6d9de1e7088b5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864375"
---
# <a name="licensing-overview"></a>Käyttöoikeuksien yleiskatsaus
PowerAppsin käyttöoikeudet myönnetään käyttäjäkohtaisesti. Jokainen käyttäjä, joka luo tai suorittaa sovelluksia palvelun avulla, tarvitsee käyttöoikeuden. Office 365- ja Dynamics 365 -asiakkaat hyötyvät heti PowerApps- ja Microsoft Flow -ominaisuuksista, jotka sisältyvät näihin palveluihin. Asiakkaat, jotka haluavat kehittää sovelluksia ja työnkulkuja, jotka käyttävät Office 365:n ja Dynamics 365:n ulkopuolisia tietolähteitä tai tarvitsevat lisätoimintoja, voivat ostaa erilliset PowerApps- ja Microsoft Flow -tilaukset. Näiden eri käyttöoikeusryhmien välillä on merkittäviä eroja.

## <a name="pricing"></a>Hinnoittelu
Katso [PowerAppsin hinnoittelusivulla][2] kaikkien PowerApps-käyttöoikeuksien uusimmat hintatiedot.
Katso [Microsoft Flow:n hinnoittelusivulla][1] kaikkien Microsoft Flow -käyttöoikeuksien uusimmat hintatiedot.

## <a name="licenses"></a>Käyttöoikeudet
### <a name="powerapps-for-office-365-and-dynamics-365"></a>PowerApps for Office 365 ja PowerApps for Dynamics 365
Office 365:n ja Dynamics 365:n PowerApps-ominaisuuksien avulla käyttäjät voivat luoda ja suorittaa näihin palveluihin liittyviä sovelluksia. Näitä sovelluksia voidaan myös laajentaa hyödyntämään yleisiin pilvipalveluihin, kuten Box.comiin, Facebookiin ja moniin muihin tallennettuja tietoja. Käyttäjät, joilla on PowerApps-käyttöoikeus Office 365:n tai Dynamics 365:n kautta, eivät voi luoda tai käyttää sovelluksia, jotka käyttävät Microsoft Common Data Service -tietokantoja. Seuraavassa Office 365- ja Dynamics 365 -palvelupakettien luettelossa on mainittu PowerApps-ominaisuudet.

|  | Sisältyvät palvelupaketit |
| --- | --- |
| Mitkä Microsoft Office 365 -palvelupaketit sisältävät PowerAppsin? |Nämä palvelupaketit sisältävät PowerApps for Office 365:n: <br><br>Office 365 Business Essentials <br>Office 365 Business Premium <br>Office 365 Education <br>Office 365 Education Plus <br>Office 365 Enterprise E1 <br>Office 365 Enterprise E3 <br>Office 365 Enterprise E5<br><br>*Office 365 Enterprise E2 sisältää samat ominaisuudet kuin Office 365 Enterprise E1, ja Office 365 Enterprise E4 sisältää samat ominaisuudet kuin Office 365 Enterprise E3.*<br><br>Office 365 Enterprise F1 sisältää PowerApps for Office 365 Enterprise F1:n. |
| Mitkä Microsoft Dynamics 365 -sovellukset ja palvelupaketit sisältävät PowerAppsin? |Nämä sovellukset sisältävät PowerApps for Dynamics 365:n:<br><br>Dynamics 365 for Team Members Enterprise edition <br>Dynamics 365 for Financials Business edition <br>Dynamics 365 for Team Members Business edition<br>Dynamics 365 for Talent <br><br>Nämä palvelupaketit sisältävät PowerAppsin palvelupaketin 2:<br><br>Dynamics 365 Customer Engagement Plan Enterprise Edition<br>Dynamics 365 Plan Enterprise Edition <br>Dynamics 365 for Sales Enterprise edition <br>Dynamics 365 for Customer Service Enterprise edition<br>Dynamics 365 for Case Management Enterprise Edition <br>Dynamics 365 for Operations Enterprise edition <br>Dynamics 365 for Field Service Enterprise edition <br>Dynamics 365 for Project Service Automation Enterprise edition<br>Microsoft Relationship Sales Solution <br><br>*PowerApps for Dynamics 365 sisältyy myös Dynamics CRM Online Enterprisen, Professionalin, Basicin ja Essentialin tilauksiin.* |

### <a name="powerapps-for-office-365-enterprise-f1"></a>PowerApps for Office 365 Enterprise F1
PowerApps sisältyy Office 365 Enterprise F1:een. Sen avulla käyttäjät voivat suorittaa sovelluksia ja automatisoida työnkulkuja. Käyttäjät eivät voi kuitenkaan luoda sovelluksia tässä palvelupaketissa (toisin kuin esimerkiksi Office 365 E1-, E3- ja E5-palvelupaketeissa). Tässä taulukossa on tarkemmat tiedot siitä, mitä käyttäjät voivat tehdä PowerApps for Office 365 Enterprise F1:llä:

| **Toiminnallisuudet** | **PowerApps for Office 365 Enterprise F1** |
| --- | --- |
| **Sovellusten luonti ja suorittaminen** | |
| Sovellusten suorittaminen |Kyllä |
| Sovellusten luominen |Ei |
| Sovellusten jakaminen |Ei |
| **Kapasiteetti** | |
| Työnkulun suorituksia kuukaudessa (käyttäjää kohti) |750 |
| Tietosäiliö Common Data Servicessä (käyttäjää kohti) |- |
| Tiedostosäiliö Common Data Servicessä (käyttäjää kohti) |- |
| **Yhteydet** | |
| Yhteyden muodostaminen Office 365:een, Dynamics 365:een ja vastaaviin tietolähteisiin |Kyllä |
| Yhteyden muodostaminen Azure SQL Serveriin, Dropboxiin, Twitteriin ja moniin muihin pilvipohjaisiin palveluihin |Kyllä |
| Yhteyden muodostaminen Salesforceen, DB2:een ja moniin muihin tietolähteisiin premium-liittimien kautta |Ei |
| Paikallisten tietojen käyttö yhdyskäytävän kautta |Ei |
| Mukautettujen liittimien luominen omissa järjestelmissäsi olevien tietojen hallitsemista varten |Ei |
| **Common Data Service** | |
| Sovellusten luominen ja suorittaminen Common Data Servicessä |Ei |
| Tietojesi mallintaminen Common Data Servicessä |Ei |
| Tietokannan luominen Common Data Servicessä |Ei |
| **Hallinta** | |
| Tukee tietokäytäntöjä, jotka Office 365:n järjestelmänvalvoja muodostaa |Kyllä |
| Työtovereiden lisääminen ympäristön tekijöiksi ja järjestelmänvalvojiksi |Ei |
| Lisää työtovereita tietokantarooleihin |Ei |
| Ympäristöjen tietokäytäntöjen muodostaminen |Ei |

### <a name="powerapps-standalone-plan-1-and-plan-2"></a>Erillinen PowerApps-palvelupaketti 1 ja 2
Täysien toimintojen PowerApps-palvelupaketit antavat käyttäjille mahdollisuuden luoda ja suorittaa sovelluksia eri tietolähteistä, jotka ulottuvat Office 365:tä ja Dynamics 365:tä pitemmälle, kuten Salesforceen ja paikallisiin tietolähteisiin sekä Microsoftin Common Data Serviceen. Nämä tilaukset sisältävät myös ominaisuuksia, jotka eivät ole käytettävissä Office 365- ja Dynamics 365 -palvelupaketeissa.

* Microsoft PowerApps-palvelupaketin 2 tilaukset on tarkoitettu käyttäjille ja järjestelmänvalvojille, jotka tarvitsevat täydet ominaisuudet sovellusten luomista ja suorittamista varten. Näillä käyttäjillä on pääsy tärkeisiin hallintaominaisuuksiin, kuten käyttötietojen tarkasteluun ja käytäntöjen määrittelyyn. PowerAppsin palvelupaketin 2 käyttäjät voivat mallintaa tietoja Common Data Servicessä.
* Microsoft PowerAppsin palvelupaketin 1 tilaukset on tarkoitettu käyttäjille, jotka pääasiassa suorittavat sovelluksia. Nämä käyttäjät voivat kuitenkin luoda sovelluksia ja työnkulkuja, mutta he eivät voi mallintaa tietoja Common Data Servicessä tai suorittaa hallintatehtäviä.

### <a name="powerapps-plan-2-free-trial"></a>PowerAppsin palvelupaketin 2 maksuton kokeiluversio
PowerApps ei tarjoa maksutonta tiliä, mutta käyttäjät voivat kokeilla PowerAppsin palvelupakettia 2 maksutta 90 päivää. Kokeilujakson aikana käyttäjät voivat käyttää PowerAppsin palvelupaketin 2 kaikkia toimintoja. Lisätietoja rekisteröitymisestä on kohdassa [PowerAppsin omatoiminen rekisteröinti][3].

Kun kokeilujakso päättyy, käyttäjillä on käytettävissään seuraavat vaihtoehdot:

* Käyttäjät, joilla on käyttöoikeus PowerAppsiin tai Microsoft Flow'hun Office 365:n tai Dynamics 365:n kautta, voivat edelleen käyttää PowerAppsia tai Microsoft Flow'ta.  Kyseiset käyttäjät kuitenkin menettävät käyttöoikeuden ominaisuuksiin, jotka ovat ainutlaatuisia palvelupaketille 2, kuten on esitetty [PowerAppsin hinnoittelusivulla][2].
* Käyttäjät, joilla ei ole käyttöoikeutta Office 365:n tai Dynamics 365:n kautta, voivat pyytää kokeilujakson jatkamista, tai he voivat ostaa erillisen palvelupaketin. Lisätietoja on kohdassa [Osta PowerApps organisaatiollesi][4].

> [!NOTE]
>   Jotta voit ostaa PowerAppsin organisaatiolle, sinun on oltava vuokraajan Office 365:n yleinen tai laskutuksen järjestelmänvalvoja tai sinun on luotava vuokraaja.
> 
> 

### <a name="powerapps-community-plan"></a>PowerAppsin yhteisön palvelupaketti
Jos haluat kehittää taitojasi ja oppia lisää PowerAppsista, Microsoft Flow'sta ja Common Data Servicestä, PowerAppsin yhteisön palvelupaketti on oikea paketti sinua varten. PowerAppsin yhteisön palvelupaketti antaa käyttöösi ilmaisen kehitysympäristön yksityiseen käyttöön PowerAppsin täyden toiminnallisuuden oppimista varten. Katso [tästä][5] tietoja PowerAppsin yhteisön palvelupaketista.

## <a name="powerapps-includes-flow"></a>PowerApps sisältää Flow'n
PowerApps-käyttöoikeudet sisältävät aina Microsoft Flow -ominaisuudet.  Sen lisäksi, että Microsoft Flow sisältyy PowerAppsin käyttöoikeuksiin, se on saatavilla myös erillisenä palveluna. Katso [PowerAppsin hinnoittelusivulta][2] lisätietoja tietyistä Microsoft Flow -ominaisuuksista, jotka sisältyvät kuhunkin PowerApps-käyttöoikeuteen.

## <a name="resource-capacity-is-included-with-each-license"></a>Kuhunkin käyttöoikeuteen sisältyy resurssikapasiteettia
Yllä esitettyihin käyttäjäkohtaisiin käyttöoikeuksiin sisältyy kapasiteettia resursseille, joita käytetään, kun sovellusta tai työnkulkua suoritetaan. Nämä resurssit sisältävät tietosäiliön, tiedostosäiliön ja työnkulun suoritukset. Käyttäjäkohtaisiin käyttöoikeuksiin sisältyvät kapasiteetit ovat varannossa vuokraajan tasolla. Kun vuokraajan kapasiteetti on lopussa, asiakkaat voivat ostaa lisäkapasiteettia lisäkäyttöoikeuksien kautta. Common Data Servicen enimmäiskapasiteetti on 10 Gt tietokantaa kohti ja 5 Tt tiedostojen tallentamiseen ympäristöä kohti. Jos ostat lisäkapasiteettia ja käytettävissä oleva kapasiteetti (käyttöoikeudet ja lisäkäyttöoikeudet yhteensä) on suurempi kuin enimmäiskapasiteetti, voit käyttää kokonaismäärää useissa ympäristöissä. Katso [PowerAppsin hinnoittelusivulta][2] lisätietoa kapasiteettimääristä, joita kukin PowerApps-käyttöoikeus sisältää.

## <a name="powerapps-licensing-examples"></a>Esimerkkejä PowerAppsin käyttöoikeuksista
Tarkastellaan esimerkkiä. ABC Inc.:llä on 1 000 työntekijää, joista 700:lla on Office 365 Enterprise 3:n käyttöoikeus. Tehokäyttäjä luo varhaisessa vaiheessa toimialaa koskevan sovelluksen, joka yksinkertaistaa asiakastilausten seurantaa. Myöhemmin henkilöstöhallinto-osasto tekee IT-osaston kanssa yhteistyötä esitelläkseen sovelluksen vapaa-ajan ja poissaolojen raportointiin. Sovellus on kehitetty Common Data Servicessä.

### <a name="order-tracking-app"></a>Tilausten seurantasovellus
ABC Inc. alkaa kehittää sovellusta käyttäjille, joilla on Office 365:n käyttöoikeus. Sovellus yhdistää Office 365 SharePoint -luetteloihin tallennetut asiakas- ja tuotekokoonpanotiedot Box.comiin tallennettujen asiakastilausasiakirjojen kanssa. Koska tämä sovellus käyttää vain Office 365:een ja yleiseen pilvipalveluun tallennettuja tietoja, joita käytetään vakioliittimen kautta, heillä jo olevat Office 365 -käyttöoikeudet kattavat sekä tämän sovelluksen luomisen että käytön.

**Tarvittavat käyttöoikeudet**: 700 Office 365 Enterprise 3 -käyttöoikeutta, jotka heillä jo on, riittävät.

### <a name="time-and-absence-app"></a>Työaika- ja poissaolosovellus
Sen perusteella, miten nopeasti ja helposti tilauksen seurantasovellus käynnistettiin, ABC:n henkilöstöhallintoryhmä päättää laatia IT-osaston avulla ajan ja poissaolojen raportointisovelluksen, joka otetaan käyttöön koko yrityksessä.  Kaikkien työntekijöiden edellytetään käyttävän sovellusta työtuntiensa, lomiensa ja sairauspoissaolopäiviensä raportoimiseen.

Sovellusta varten IT-osasto valitsee Common Data Servicen järjestelmäksi, johon aika- ja poissaolotiedot tallennetaan. Common Data Service tarjoaa suojaus- ja tietokäytäntöominaisuudet, joita IT-osasto edellyttää työntekijöihin liittyville tiedoille. He määrittävät kaksi IT-työntekijää projektiin laatimaan tietokannan ja mallintamaan aika- ja poissaolotiedot Common Data Servicessä. Nämä työntekijät ovat myös vastuussa sovelluksen käytön seurannasta ja näitä tietoja koskevan käytännön muodostamisesta.

**Tarvittavat käyttöoikeudet**:

* PowerApps -palvelupaketti 2 – 10 käyttöoikeutta: 10 IT-järjestelmänvalvojaa, jotka määrittävät yritykselle ympäristöt sovelluksen testaamista ja käyttöönottoa varten, mallintavat tietoja Common Data Servicessä ja laativat tietoturvakäytännöt, tarvitsevat kukin oman PowerApps -palvelupaketin 2 näiden toimenpiteiden suorittamista varten.
* PowerApps -palvelupaketti 1 – 990 käyttöoikeutta: 700 Office 365:n käyttäjää tarvitsevat PowerApps palvelupaketin 1, koska sovellus käyttää Office 365:n ulkopuolelle tallennettuja tietoja (Common Data Serviceen tallennettuja tietoja). Muut 290 käyttäjää, joilla ei ole Office 365:n tai PowerAppsin palvelupaketin 2 käyttöoikeutta, tarvitsevat käyttöoikeuden saadakseen oikeudet sovelluksen suorittamiseen.

<!--Reference links in article-->
[1]: https://flow.microsoft.com/pricing/
[2]: https://powerapps.microsoft.com/pricing
[3]: https://powerapps.microsoft.com/tutorials/signup-for-powerapps/#try-powerapps-plan-2-for-free
[4]: https://powerapps.microsoft.com/tutorials/signup-for-powerapps-admin/
[5]: https://powerapps.microsoft.com/tutorials/dev-community-plan/
