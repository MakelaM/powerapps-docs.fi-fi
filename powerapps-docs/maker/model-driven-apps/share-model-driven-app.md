---
title: Opetusohjelma mallipohjaisen sovelluksen jakamiseen PowerAppsin avulla | Microsoft Docs
description: Tässä opetusohjelmassa neuvotaan, miten mallipohjainen sovellus jaetaan
documentationcenter: ''
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: 4068bbc4e67adee344544c0ba69895244d3dab83
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "32330372"
---
# <a name="tutorial-share-a-model-driven-app-with-powerapps"></a>Opetusohjelma: mallipohjaisen sovelluksen jakaminen PowerAppsilla

Tyypin [!INCLUDE [powerapps](../../includes/powerapps.md)] sovellukset käyttävät jakamisessa roolipohjaista suojausta. Roolipohjainen suojaus perustuu siihen, että käyttöoikeusroolin sisältämät oikeudet määrittävät, mitä toimintojoukkoja sovelluksessa voidaan suorittaa. Kaikille sovelluksen käyttäjille on määritettävä vähintään yksi ennalta määritetty tai mukautettu rooli. Rooleja voidaan määrittää myös tiimeille. Kun rooli on määritetty, käyttäjä tai tiimi saa kyseiseen rooliin liittyvät käyttöoikeudet. 

Tässä opetusohjelmassa suoritat vaiheet, joilla mallipohjainen sovellus jaetaan muiden käyttöön. Ohjeet:
- Mukautetun käyttöoikeusroolin luominen
- Mukautetun käyttöoikeusroolin käyttäjien määrittäminen
- Käyttöoikeusroolin lisääminen sovellukseen

## <a name="prerequisites"></a>Edellytykset
Sovelluksen voi jakaa vain [!INCLUDE [powerapps](../../includes/powerapps.md)]ympäristön järjestelmänvalvojan tai järjestelmänvalvojan roolissa. 

## <a name="sign-in-to-powerapps"></a>Kirjautuminen PowerAppsiin
Kirjaudu sisään [PowerAppsiin](https://powerapps.microsoft.com/). Jos sinulla ei ole vielä [!INCLUDE [powerapps](../../includes/powerapps.md)]tiliä, napsauta tai napauta **Aloita maksutta** -linkkiä.

## <a name="share-an-app"></a>Sovelluksen jakaminen 
Opetusohjelman esimerkkitapauksena on lemmikkieläinten hoitoyritys Contoso, joka tarjoaa kissojen ja koirien trimmauspalveluja. Lemmikkieläinten hoitoyrityksen liiketoimintaa seuraavan mukautetun entiteetin sisältävä sovellus on jo luotu ja julkaistu. Nyt sovellus on jaettava, jotta yrityksen henkilökunta voi käyttää sitä. Sovelluksen jakamista varten järjestelmänvalvoja tai sovelluksen tekijä määrittää sovellukselle ja jokaiselle käyttäjälle vähintään yhden käyttöoikeusroolin. 

## <a name="create-or-configure-a-security-role"></a>Käyttöoikeusroolin luominen tai määrittäminen
[!INCLUDE [powerapps](../../includes/powerapps.md)]Ympäristöt sisältävät [ennalta määritettyjä käyttöoikeusrooleja](#about-predefined-security-roles), jotka pohjautuvat yleisiin käyttäjien tehtäviin. Niiden käyttöoikeustasot on määritetty tietoturvan parhaiden käytäntöjen tavoitteiden mukaisesti tarjoamaan käyttöoikeuden vain niihin liiketoiminnan tietoihin, joita sovelluksen käyttö vaatii. Muista, että Contoson lemmikkienhoitosovellus perustuu mukautettuun entiteettiin. Koska entiteetti on mukautettu, käyttöoikeudet on määritettävä erikseen, ennen kuin käyttäjät voivat käyttää sovellusta työssään. Se voidaan tehdä jollain seuraavista tavoista.
- Laajenna olemassa olevaa, ennalta määritettyä käyttöoikeusroolia niin, että se sisältää mukautettuun entiteettiin pohjautuvien tietueiden käyttöoikeudet. 
- Luo mukautettu käyttöoikeusrooli sovelluksen käyttäjien käyttöoikeuksien hallintaa varten. 

Koska lemmikkienhoitotietueita ylläpitävää ympäristöä käytetään myös muiden Contoso-yrityksen sovellusten suorittamiseen, lemmikkienhoitosovellukselle on luotava erillinen mukautettu käyttöoikeusrooli. Lisäksi tarvitaan kaksi eri käyttöoikeusjoukkoa.
- Lemmikkieläinten trimmaajien tarvitsee työssään vain lukea, päivittää ja liittää tietueita, joten heidän käyttöoikeusroolinsa sisältää lukemisen, kirjoittamisen ja liittämisen oikeudet. 
- Lemmikkienhoidon varaushenkilökunta tarvitsee trimmaajien oikeuksien lisäksi mahdollisuuden luoda, laajentaa, poistaa ja jakaa tietueita, joten heidän käyttöoikeusroolinsa sisältää luomisen, lukemisen, kirjoittamisen, liittämisen, poistamisen, määrittämisen, laajentamisen ja jakamisen oikeudet.

Lisätietoja käyttö- ja vaikutusalueoikeuksista on kohdassa [Käyttöoikeusroolit](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles).

## <a name="create-a-custom-security-role"></a>Mukautetun käyttöoikeusroolin luominen
1. Valitse [!INCLUDE [powerapps](../../includes/powerapps.md)] sivustolla **Mallipohjaiset** > **sovellukset** > **...** >  **Jaa linkki**.
2. Valitse **Jaa sovellus** -valintaikkunan **Luo käyttöoikeusrooli** -kohdasta **Suojausasetus**.
3. Valitse **Asetukset**-sivulla **Uusi**.  

4. Käyttöoikeusroolien hallintatyökalussa voit valita erilaisia toimintoja, kuten lukeminen, kirjoittaminen tai poistaminen, ja näiden toimintojen vaikutusalueen. Vaikutusalue määrittää, miten pitkälle tai laajalle käyttäjän käynnistämä toiminto vaikuttaa ympäristön hierarkiassa. Kirjoita **Roolin nimi** -kenttään *Lemmikkien trimmaajat*.
5. Valitse **Mukautetut entiteetit** -välilehti ja etsi haluamasi mukautettu entiteetti. Tässä esimerkissä käytetään mukautettua entiteettiä nimeltä **Pet** (lemmikki). 
6. Valitse **Pet**-riviltä seuraavat oikeudet neljä kertaa, kunnes ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittu: **lukeminen, kirjoittaminen, liittäminen**
![Uusi käyttöoikeusrooli](media/share-model-driven-app/custom-security-role.png)
7. Koska lemmikkienhoitosovellus on yhteydessä myös tilientiteettiin, valitse **Ydintietueet**-välilehden **Tili**-riviltä **Lukeminen** neljä kertaa, kunnes ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittuna. 
8. Valitse **Tallenna ja sulje**. 
9. Kirjoita käyttöoikeusroolin hallintatyökalussa **Roolin nimi** -kenttään *Lemmikkienhoidon varaushenkilökunta*. 
10. Valitse **Mukautetut entiteetit** -välilehti ja etsi **Pet**-entiteetti. 
11. Valitse **Pet**-riviltä seuraavat oikeudet neljä kertaa, kunnes ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittu: **luominen, lukeminen, kirjoittaminen, poistaminen, liittäminen, laajentaminen, määrittäminen, jakaminen**
12. Koska lemmikkienhoitosovellus on yhteydessä myös tilientiteettiin ja varaushenkilökunnan on voitava luoda ja muokata tilitietueita, valitse **Ydintietueet**-välilehden **Tili**-riviltä seuraavat käyttöoikeudet neljä kertaa, kunnes ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittuna. 
    **Luominen, lukeminen, kirjoittaminen, poistaminen, liittäminen, laajentaminen, määrittäminen, jakaminen**
13. Valitse **Tallenna ja sulje**.

## <a name="assign-security-roles-to-users"></a>Käyttäjien käyttöoikeusroolien määrittäminen
Käyttöoikeusroolit hallitsevat erilaisilla käyttöoikeustasoilla ja oikeuksilla, mitä tietoja käyttäjä voi käyttää. Käyttöoikeusroolin käyttöoikeustasojen ja oikeuksien yhdistelmä rajoittaa käyttäjän näkemiä tietoja ja vuorovaikutusta tietojen kanssa.

### <a name="assign-a-security-role-to-pet-grooming-technicians"></a>Lemmikkien trimmaajien käyttöoikeusroolin määrittäminen
1. Valitse **Jaa sovellus** -valintaikkunan **Määritä käyttöoikeusroolin käyttäjät** -kohdasta **Security Users** (käyttöoikeuden käyttäjät).
2. Valitse esiin tulevasta luettelosta lemmikkien trimmaajat.
3. Valitse **Roolien hallinta**.

    ![Roolien hallinta](media/share-model-driven-app/select-users-for-security-roles.png)

4. Valitse **Käyttäjien roolien hallinta** -valintaikkunasta aikaisemmin luotu **Lemmikkien trimmaajat** -käyttöoikeusrooli ja napsauta sitten **OK**-painiketta.

### <a name="assign-a-security-role-to-pet-grooming-schedulers"></a>Lemmikkienhoidon varaushenkilökunnan käyttöoikeusroolin määrittäminen
1. Valitse **Jaa sovellus** -valintaikkunan **Määritä käyttöoikeusroolin käyttäjät** -kohdasta **Security Users** (käyttöoikeuden käyttäjät).
2. Valitse esiin tulevasta luettelosta lemmikkienhoidon varaushenkilökunta.
3. Valitse **Roolien hallinta**.
4. Valitse **Käyttäjien roolien hallinta** -valintaikkunasta aikaisemmin luotu **Lemmikkienhoidon varaushenkilökunta** -käyttöoikeusrooli ja napsauta sitten **OK**-painiketta.


## <a name="add-security-roles-to-the-app"></a>Käyttöoikeusroolien lisääminen sovellukseen
Seuraavaksi sovellukselle on määritettävä vähintään yksi käyttöoikeusrooli. Käyttäjille myönnetyt käyttöoikeusroolit määrittävät, mitä sovelluksia he voivat käyttää.
1. Valitse **Jaa sovellus** -valintaikkunan **Lisää käyttöoikeusrooli sovellukseen** -kohdasta **Omat sovellukset**.
2. Valitse Contoson lemmikkienhoitosovelluksen sovellusruudun oikeasta alakulmasta **Lisää vaihtoehtoja (...)** ja sitten **Roolien hallinta**.

    ![Sovelluksen roolien hallinta](media/share-model-driven-app/manage-roles.png)

4. **Roolit**-osiossa voit valita, onko sovellus kaikkien käyttöoikeusroolien käytettävissä vai vain tiettyjen. Valitse aikaisemmin luomasi roolit **Lemmikkienhoidon varaushenkilökunta** ja **Lemmikkien trimmaajat**.

    ![Valitse sovelluksen käyttöoikeusroolit](media/share-model-driven-app/app-security-roles.png)

5. Valitse **Tallenna**.
 
## <a name="share-the-link-to-your-app"></a>Sovelluksen linkin jakaminen
1. Siirry **Jaa sovellus** -valintaikkunan kohtaan **Jaa sovelluksen linkki suoraan käyttäjien kanssa** ja kopioi siellä näkyvä URL-osoite.
 
2. Valitse **Sulje**.
3. Liitä sovelluksen URL-osoite paikkaan, jossa se on käyttäjien käytettävissä. Voit esimerkiksi julkaista sen SharePoint-sivustolla tai lähettää sen sähköpostilla.

![Linkin jakaminen](media/share-model-driven-app/share-model-driven-URL.PNG)

Sovelluksen URL-osoite on myös sovelluseditorin **Ominaisuudet**-välilehdessä. 
    
![Sovelluksen URL-osoitteen kopioiminen](media/share-model-driven-app/app-designer-copy-web-url.png)

## <a name="about-predefined-security-roles"></a>Tietoja ennalta määritetyistä käyttöoikeusrooleista
Nämä ennalta määritetyt roolit ovat käytettävissä ympäristössä [!INCLUDE [powerapps](../../includes/powerapps.md)].


|Käyttöoikeusrooli  |*Oikeudet  |Kuvaus |
|---------|---------|---------|
|Ympäristön tekijä     |  Ei mitään       | Voi luoda ympäristöön liittyviä uusia resursseja, kuten sovelluksia, yhteyksiä, mukautettuja ohjelmointirajapintoja, yhdyskäytäviä ja työnkulkuja Microsoft Flow -palvelun avulla. Ei kuitenkaan omista mitään oikeuksia ympäristössä olevien tietojen käyttöön. Lisätietoja: [Ympäristöjen yleiskuvaus](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|Järjestelmänvalvoja     |  Luominen, lukeminen, kirjoittaminen, poistaminen, mukautukset, käyttöoikeusroolit       | Täydet ympäristön mukauttamis- ja hallintaoikeudet, mukaan lukien käyttöoikeusroolien luominen, muokkaaminen ja määrittäminen. Pystyy tarkastelemaan kaikkia ympäristössä olevia tietoja. Lisätietoja: [Mukauttamiseen tarvittavat oikeudet](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Järjestelmämukauttaja     | Luominen (itse), lukeminen (itse), kirjoittaminen (itse), poistaminen (itse), mukautukset         | Täydet oikeudet ympäristön mukauttamiseen. Voi kuitenkin tarkastella vain itse luotujen ympäristöentiteettien tietueita. Lisätietoja: [Mukauttamiseen tarvittavat oikeudet](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Common Data Servicen käyttäjä     |  Lukeminen, luominen (itse), kirjoittaminen (itse), poistaminen (itse)       | Voi suorittaa sovelluksen ympäristössä ja suorittaa yleisiä tehtäviä omille tietueilleen.        |
|Edustaja     | Toisen käyttäjän puolesta toimiminen        | Mahdollistaa koodin suorittamisen toisena käyttäjänä tai toiseksi käyttäjäksi tekeytyneenä.  Käytetään yleensä toisen käyttöoikeusroolin yhteydessä, jotta tietueita voidaan käyttää. Lisätietoja: [Toiseksi käyttäjäksi tekeytyminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*Oikeuden vaikutusalue on yleinen, ellei toisin määritetä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Pikaopas: Mallipohjaisen sovelluksen suorittaminen mobiililaitteella](../../user/run-app-client-model-driven.md)



