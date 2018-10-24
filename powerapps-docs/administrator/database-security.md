---
title: Konfiguroi ympäristön turvallisuus | Microsoft Docs
description: Tässä aiheessa kerrotaan, miten ympäristön tietoturva määritetään.
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 10/10/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 3c8bdcb855b1e15cbebeb2a51fedf8aea7684286
ms.sourcegitcommit: c4369e5f31bb08716f1af1416f3f7510a4b926d5
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/10/2018
ms.locfileid: "49072515"
---
# <a name="configure-environment-security"></a>Konfiguroi ympäristön turvallisuus
Common Data Service (CDS) for Apps käyttää roolipohjaista tietoturvamallia tietokantaan pääsyn suojaamiseksi. Tässä ohjeaiheessa kerrotaan, miten luodaan suojausartefaktit, jotka ovat sovelluksen suojaamisen kannalta välttämättömiä. Käyttäjäroolit hallitsevat käytönaikaista tietojen käyttöä ja eroavat ympäristörooleista, jotka ohjaavat ympäristön järjestelmänvalvojia ja ympäristön tekijöitä. Katso ympäristöjen yleiskatsaus kohdassa [Ympäristöjen yleiskatsaus](environments-overview.md).

## <a name="assign-security-roles-to-users"></a>Käyttäjien käyttöoikeusroolien määrittäminen
Käyttöoikeusroolit hallitsevat erilaisilla käyttöoikeustasoilla ja oikeuksilla, mitä tietoja käyttäjä voi käyttää. Käyttöoikeusroolin käyttöoikeustasojen ja oikeuksien yhdistelmä rajoittaa käyttäjän näkemiä tietoja ja vuorovaikutusta tietojen kanssa.

Ympäristön järjestelmänvalvoja voi määrittää ympäristön roolin käyttäjälle tai käyttöoikeusryhmälle [PowerApps-hallintakeskuksessa][1] seuraavalla tavalla:

1. Valitse ympäristö ympäristöt-taulukosta.

    ![](./media/environment-admin/environment-list-new.png)

2. Valitse **Suojaus**-välilehti.

3. Tarkista, onko käyttäjä lisätty ympäristöön, valitsemalla **Näytä ympäristössä olevien käyttäjien luettelo**.
    
    ![](./media/database-security/security-viewuser.png)

4. Jos käyttäjää ei löydy, voit lisätä käyttäjän PowerAppsin hallintakeskuksessa. Lisää käyttäjä antamalla tämän sähköpostiosoite organisaatiossasi ja valitsemalla **Lisää käyttäjä**.

    ![](./media/database-security/security-adduser.png)

    Odota muutama minuutti, ennen kuin tarkistat, löytyykö käyttäjä ympäristön käyttäjien luettelosta.
  
5. Valitse käyttäjä ympäristön käyttäjäluettelosta.

    ![](./media/environment-admin/D365-Select-User.png)

6. Määritä rooli käyttäjälle.

    ![](./media/environment-admin/D365-Assign-Role.png)

    > [!NOTE]
    > Tällä hetkellä rooleja voidaan määrittää vain käyttäjille. Roolin määrittäminen käyttöoikeusryhmälle ei vielä ole mahdollista.

7. Päivitä määritykset ympäristön rooliin valitsemalla **OK**.

## <a name="predefined-security-roles"></a>Ennalta määritetyt käyttöoikeusroolit
PowerApps-ympäristö sisältää ennalta määritettyjä käyttöoikeusrooleja, jotka pohjautuvat yleisiin käyttäjien tehtäviin. Niiden käyttöoikeustasot on määritetty tietoturvan parhaiden käytäntötavoitteiden mukaisesti tarjoamaan käyttöoikeuden vain niihin liiketoiminnan tietoihin, joita sovelluksen käyttö vaatii.

|Käyttöoikeusrooli  |*Tietokantaoikeudet  |Kuvaus |
|---------|---------|---------|
|Järjestelmänvalvoja     |  Luominen, lukeminen, kirjoittaminen, poistaminen, mukautukset, käyttöoikeusroolit       | Täydet ympäristön mukauttamis- ja hallintaoikeudet, mukaan lukien käyttöoikeusroolien luominen, muokkaaminen ja määrittäminen. Pystyy tarkastelemaan kaikkia ympäristössä olevia tietoja. Lisätietoja: [Mukauttamiseen tarvittavat oikeudet](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Järjestelmämukauttaja     | Luominen (itse), lukeminen (itse), kirjoittaminen (itse), poistaminen (itse), mukautukset         | Täydet oikeudet ympäristön mukauttamiseen. Voi kuitenkin tarkastella vain itse luotujen ympäristöentiteettien tietueita. Lisätietoja: [Mukauttamiseen tarvittavat oikeudet](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Ympäristön tekijä     |  Ei mitään       | Voi luoda ympäristöön liittyviä uusia resursseja, kuten sovelluksia, yhteyksiä, mukautettuja ohjelmointirajapintoja, yhdyskäytäviä ja työnkulkuja Microsoft Flow -palvelun avulla. Ei kuitenkaan omista mitään oikeuksia ympäristössä olevien tietojen käyttöön. Lisätietoja: [Ympäristöjen yleiskuvaus](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|Common Data Servicen käyttäjä     |  Lukeminen (itse), luominen (itse), kirjoittaminen (itse), poistaminen (itse)       | Voi suorittaa sovelluksen ympäristössä ja suorittaa yleisiä tehtäviä omille tietueilleen.        |
|Edustaja     | Toisen käyttäjän puolesta toimiminen        | Mahdollistaa koodin suorittamisen toisena käyttäjänä tai toiseksi käyttäjäksi tekeytyneenä.  Käytetään yleensä toisen käyttöoikeusroolin yhteydessä, jotta tietueita voidaan käyttää. Lisätietoja: [Toiseksi käyttäjäksi tekeytyminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*Oikeuden vaikutusalue on yleinen, ellei toisin määritetä.

- Ympäristön tekijät voivat resurssien luomisen lisäksi jakaa kehittämiään sovelluksia ympäristössä organisaation muille käyttäjille. He voivat jakaa sovelluksia yksittäisten käyttäjien kanssa. Lisätietoja on kohdassa [Sovelluksen jakaminen PowerAppsissa](../maker/canvas-apps/share-app.md).

- Käyttäjille, jotka tekevät tietokantaan yhteydessä olevia sovelluksia ja luovat tai päivittävät entiteettejä ja käyttöoikeusrooleja, on määritettävä sekä järjestelmänmukauttajan että ympäristön tekijän rooli, sillä ympäristön tekijällä ei ole tietokannan käyttöoikeutta.

## <a name="create-or-configure-a-custom-security-role"></a>Mukautetun käyttöoikeusroolin luominen tai määrittäminen
Jos sovelluksessasi käytetään mukautettua entiteettiä, sen oikeudet täytyy nimenomaisesti myöntää käyttöoikeusroolissa, ennen kuin sovellustasi voidaan käyttää.  Voit lisätä nämä oikeudet olemassa olevassa käyttöoikeusroolissa tai luoda mukautetun käyttöoikeusroolin. Käytössä on oltava vähimmäisoikeudet, jotta uutta käyttöoikeusroolia voidaan käyttää – katso [Vähimmäisoikeudet sovelluksen suorittamiseen](#minimum-privileges-to-run-app).

> [!TIP]
> Jos haluat luoda mukautetun käyttöoikeusroolin sovelluksen suorittamisen edellyttämillä vähimmäisoikeuksilla, tutustu alla olevaa osioon: [Vähimmäisoikeudet sovelluksen suorittamiseen](#minimum-privileges-to-run-app).

Ympäristö saattaa ylläpitää tietueita, joita useat sovellukset voivat käyttää. Tarvitset ehkä useita käyttöoikeusrooleja käyttämään tietoja, joihin tarvitaan eri käyttöoikeudet. esim.
- Joidenkin käyttäjien (tyyppi A) tarvitsee vain lukea, päivittää ja liittää muita tietueita, joten heidän käyttöoikeusroolinsa sisältää lukemisen, kirjoittamisen ja liittämisen oikeudet.
- Toiset käyttäjät puolestaan tarvitsevat edellisten käyttäjien oikeuksien lisäksi mahdollisuuden luoda, laajentaa, poistaa ja jakaa tietueita, joten heidän käyttöoikeusroolinsa sisältää luomisen, lukemisen, kirjoittamisen, liittämisen, poistamisen, määrittämisen, laajentamisen ja jakamisen oikeudet.

Lisätietoja käyttöoikeuksista ja oikeuksien laajuudesta on kohdassa [Käyttöoikeusroolit](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles).

1. Valitse [PowerAppsin hallintakeskuksessa][1] ympäristö, jossa haluat päivittää käyttöoikeusroolia.

    ![](./media/environment-admin/choose-environment-updated.png)

2. Hallinnoi ympäristöä Dynamics 365 -hallintakeskuksessa napsauttamalla **Lisätiedot**-välilehden linkkiä.

3. Valitse esiintymä (jolla on sama nimi kuin ympäristöllä) ja napsauta Avaa

    ![](./media/database-security/glados-instance-list.png)

4. Napsauta otsikossa **Asetukset** ja valitse **Suojaus**

    ![](./media/database-security/dyn365-settings-security.png)

5. Valitse **Käyttöoikeusroolit**

    ![](./media/database-security/dyn365-securityroles.png)

6. Napsauta **Uusi**

7. Käyttöoikeusroolien suunnittelutyökalusta voit valita toimintoja, kuten lukemisen, kirjoittamisen tai poistamisen sekä kyseisen toiminnon suorittamisen laajuuden.

8. Valitse välilehti ja hae entiteettiä, esim. **Mukautetut entiteetit** -välilehdessä mukautetun entiteetin käyttöoikeuden määrittämistä varten.

9. Määritä oikeudet **lukemiseen, kirjoittamiseen, lisäämiseen**

10. Valitse **Tallenna ja sulje**.

## <a name="minimum-privileges-to-run-app"></a>Vähimmäisoikeudet sovelluksen suorittamiseen
Kun luot mukautetun käyttöoikeusroolin, siihen pitää sisällyttää vähimmäisoikeudet, jotta käyttäjä voi suorittaa sovelluksen. Olemme luoneet ratkaisun, jonka voit tuoda ja joka tarjoaa vähimmäisoikeudet sisältävän käyttöoikeusroolin.  

Aloita lataamalla ratkaisu Download Centeristä: [CDS for Appsin vähimmäisoikeudet sisältävä käyttöoikeusrooli](http://download.microsoft.com/download/6/5/5/6552A30E-05F4-45F0-AEE3-9BB01E13118A/MinprivilegeSecRole_1_0_0_0.zip).

Tuo sitten ratkaisu noudattamalla ohjeita: [Ratkaisujen tuominen, päivittäminen ja vieminen](../maker/common-data-service/import-update-export-solutions.md).

Kun tuot ratkaisun, se luo **sovellusten käyttö väh.oikeuksilla** -roolin, jonka voit kopioida (katso: [Käyttöoikeusroolin luominen Kopioi rooli -toiminnolla](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/create-edit-security-role#create-a-security-role-by-copy-role)). Kun roolin kopioiminen on valmis, siirry jokaiseen välilehteen - Ydintietueet, Yrityksen hallinta, Mukauttaminen jne. - ja määritä tarvittavat oikeudet. 

> [!IMPORTANT]
> Kokeile ratkaisua kehitysympäristössä ennen tuomista tuotantoympäristöön. 

<!--Reference links in article-->
[1]: https://admin.powerapps.com
