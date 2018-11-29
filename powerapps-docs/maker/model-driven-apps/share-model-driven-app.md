---
title: 'Opetusohjelma, jossa kerrotaan mallipohjaisen sovelluksen jakamisesta PowerAppsin avulla | Microsoft Docs'
description: 'Tässä opetusohjelmassa on lisätietoja siitä, miten mallipohjainen sovellus jaetaan'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="tutorial-share-a-model-driven-app-with-powerapps"></a>Opetusohjelma: Mallipohjaisen sovelluksen jakaminen PowerAppsin avulla

[!INCLUDE [powerapps](../../includes/powerapps.md)]-sovellukset käyttävät jakamisessa rooliin perustuvaa suojausta Rooliin perustuvan suojauksen peruskonsepti on se, että käyttöoikeusrooli sisältää oikeuksia, jotka määrittävät sovelluksessa suoritettavan toimintojoukon oikeudet. Kaikille sovelluksen käyttäjille on delegoitava vähintään yksi ennalta määritetty tai mukautettu rooli. Roolit voi myös delegoida ryhmille. Kun käyttäjä tai ryhmä delegoidaan johonkin näistä rooleista, henkilölle tai ryhmän jäsenille myönnetään roolille liitettyjen oikeuksien joukko. 

Tässä opetusohjelmassa suoritetaan mallipohjaisen sovelluksen jakamiseen liittyvät tehtävät. Jakamisen jälkeen muut voivat käyttää sovellusta. Saat lisätietoja seuraavista toiminnoista:
- Mukautetun käyttöoikeusroolin luominen
- Käyttäjien delegoiminen mukautetulle käyttöoikeusroolille
- Käyttöoikeusroolin delegoiminen sovellukselle

## <a name="prerequisites"></a>Edellytykset
Sovelluksen jakaminen edellyttää [!INCLUDE [powerapps](../../includes/powerapps.md)]-ympäristön järjestelmävalvojan tai järjestelmänvalvojan roolin. 

## <a name="sign-in-to-powerapps"></a>Kirjaudu sisään PowerApps -sovellukseen
Kirjaudu sisään [PowerApps](https://powerapps.microsoft.com/) -sovellukseen. Jos sinulla ei vielä ole [!INCLUDE [powerapps](../../includes/powerapps.md)]-tiliä, valitse **Aloita ilmaiseksi** -linkki.

## <a name="share-an-app"></a>Sovelluksen jakaminen 
Opetusohjelma seuraa yritystä, Contosoa, joka tarjoaa trimmauspalvelua koirille ja kissoille. Sovellus, joka sisältää trimmausyrityksen seurannan mukautetun entiteetin, on jo luotu ja julkaistu. Nyt sovellus on jaettava niin, että trimmausyrityksen henkilöstö voi käyttää sitä. Voit jakaa sovelluksen, jos järjestelmänvalvoja tai sovelluksen tekijä delegoi käyttäjille ja sovellukselle vähintään yhden käyttöoikeusroolin. 

## <a name="create-or-configure-a-security-role"></a>Käyttöoikeusroolin luominen tai määrittäminen
The [!INCLUDE [powerapps](../../includes/powerapps.md)]-ympäristö sisältää [ennalta määritettyjä käyttöoikeusrooleja](#about-predefined-security-roles), jotka vastaavat yleisiä käyttäjän tehtäviä ja käyttöoikeustasoja, jotka vastaavat suojauksen parhaiden käytäntöjen tavoitteita. Niissä tarjotaan käyttöoikeus pienimpään mahdolliseen yritystietomäärään, joka sovelluksen käyttö vaatii. Muista, että Contoson trimmaussovellus perustuu mukautettuun entiteettiin. Koska entiteetti on mukautettu, oikeudet on määritettävä tarkkaan, ennen kuin käyttäjät voivat käyttää sovellusta. Voit tehdä tämän suorittamalla jonkin seuraavista toiminnoista.
- Laajenna ennalta määritetty käyttöoikeusrooli niin, että se sisältää mukautettuun entiteettiin perustuvien tietueiden oikeudet. 
- Luo mukautettu käyttöoikeusrooli sovelluksen käyttäjien hallintaa varten. 

Koska trimmaustietueita ylläpitävää ympäristöä käytetään myös muissa kuin Contoson käyttämissä sovelluksissa, luodaan trimmaussovellukselle mukautettu käyttöoikeusrooli. Lisäksi vaaditaan kaksi eri käyttöoikeusjoukkoa.
- Trimmaajien on vain luettava, päivitettävä ja liitettävä tietueita, joten heidän käyttöoikeusroolinsa sisältää luku-, kirjoitus ja liittämisoikeudet. 
- Trimmausyrityksen ajanvaraajat tarvitsevat samat oikeudet kuin trimmaajat. Niiden lisäksi he tarvitsevat mahdollisuuden luoda, lisätä kohteeseen, poistaa ja jakaa, joten heidän käyttöoikeusroolinsa sisältää luonti-, luku-, lisäys-, poisto-, delegointi-, lisäys kohteeseen- ja jako-oikeudet.

Lisätietoja käyttöoikeuksista ja vaikutusalueen oikeuksista on kohdassa [Käyttöoikeusroolit](https://docs.microsoft.com/dynamics365/customer-engagement/admin/security-roles-privileges#security-roles).

## <a name="create-a-custom-security-role"></a>Mukautetun käyttöoikeusroolin luominen
1. Valitse [!INCLUDE [powerapps](../../includes/powerapps.md)] -sivustossa **Sovellukset** > **…**> **Jaa linkki**.
2. Valitse **Luo käyttöoikeusrooli** -kohdan **Jaa tämä sovellus** -valintaikkunassa **Käyttöoikeusasetus**.
3. Valitse **Asetukset**-sivulla **Uusi**.  

4. Käyttöoikeusroolien suunnitteluohjelmassa voi valita toiminnot, kuten lukemisen, kirjoittamisen tai poistamisen, ja kyseisen toiminnon suorituksen vaikutusalueen. Vaikutusalue määrittää, miten syvällä tai korkealla ympäristön hierarkiassa käyttäjä voi suorittaa tietyn toiminnon. Anna **Roolin nimi** -ruutuun *Trimmaajat*.
5. Valitse **Mukautetut entiteetit** -välilehti ja etsi haluamasi mukautettu entiteetti. Tässä esimerkissä mukautetun entiteetin nimi on **Lemmikki**. 
6. Valitse **Lemmikki**-rivillä kaikki seuraavat oikeudet neljä kertaa, kunnes organisaation yleinen vaikutusalue ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittu: **Luku, kirjoitus, liitos**
> [!div class="mx-imgBorder"] 
> ![Uusi käyttöoikeusrooli](media/share-model-driven-app/custom-security-role.png)
7. Koska trimmaussovelluksella on myös suhde asiakasentiteetin kanssa, valitse **Ydintietueet**-välilehti. Valitse **Asiakas**-rivillä **Luku** neljä kertaa, kunnes organisaation yleinen vaikutusalue ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittu. 
8. Valitse **Tallenna ja sulje**. 
9. Kirjoita käyttöoikeusroolin suunnitteluohjelman **Roolin nimi** -ruutuun *Trimmausyrityksen ajanvaraajat*. 
10. Valitse **Mukautetut entiteetit** -välilehti ja etsi **Lemmikki**-entiteetti. 
11. Valitse **Lemmikki**-rivillä kaikki seuraavat oikeudet neljä kertaa, kunnes organisaation yleinen vaikutusalue ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittu: **Luonti, luku, kirjoitus, poisto, liitos, liitos kohteeseen, delegointi, jako**
12. Koska trimmaussovelluksella on myös suhde asiakasentiteetin kanssa ja ajanvaraajilla on oltava asiakastietueiden luonti- ja muokkausmahdollisuus, valitse **Ydintietueet**-välilehti. Valitse **Asiakas**-rivillä seuraavat oikeudet neljä kertaa, kunnes organisaation yleinen vaikutusalue ![Organisaation yleinen vaikutusalue](media/share-model-driven-app/organizational-scope-privilege.png) on valittu. 
    **Luonti, luku, kirjoitus, poisto, liitos, liitos kohteeseen, delegointi, jako**
13. Valitse **Tallenna ja sulje**.

## <a name="assign-security-roles-to-users"></a>Käyttöoikeusroolien delegoiminen käyttäjille
Käyttöoikeusroolit hallitsevat käyttäjän käyttöön tulevia tietoja käyttöoikeustaso- ja oikeusjoukkojen perusteella. Tiettyyn käyttöoikeusrooliin sisältyvä käyttöoikeustasojen ja oikeuksien yhdistelmä rajaa, mitä tietoja käyttäjä näkee ja mitä hän voi niille tehdä.

### <a name="assign-a-security-role-to-pet-grooming-technicians"></a>Käyttöoikeusroolin delegoiminen trimmaajille
1. Valitse **Delegoi käyttäjiä käyttöoikeusroolille** -kohdan **Jaa tämä sovellus** -valintaikkunassa **Käyttöoikeuden käyttäjät**.
2. Valitse näyttöön tulevasta luettelosta trimmausyritykset.
3. Valitse **Hallitse rooleja**.

    > [!div class="mx-imgBorder"] 
    > ![Roolien hallinta](media/share-model-driven-app/select-users-for-security-roles.png)

4. Valitse **Käyttäjäroolien hallinta** -valintaikkunassa aiemmin luotu **trimmaajien** käyttöoikeusrooli ja valitse sitten **OK**.

### <a name="assign-a-security-role-to-pet-grooming-schedulers"></a>Käyttöoikeusroolin delegoiminen trimmausyrityksen ajanvaraajille
1. Valitse **Delegoi käyttäjiä käyttöoikeusroolille** -kohdan **Jaa tämä sovellus** -valintaikkunassa **Käyttöoikeuden käyttäjät**.
2. Valitse näyttöön tulevasta luettelosta trimmausyrityksen ajanvaraajat.
3. Valitse **Hallitse rooleja**.
4. Valitse **Käyttäjäroolien hallinta** -valintaikkunassa aiemmin luotu **trimmausyrityksen ajanvaraajien** käyttöoikeusrooli ja valitse sitten **OK**.


## <a name="add-security-roles-to-the-app"></a>Käyttöoikeusroolien lisääminen sovellukseen
Seuraavaksi on delegoitava sovellukselle vähintään yksi käyttöoikeusrooli. Käyttäjällä on sovellusten käyttöoikeus heille määritettyjen käyttöoikeusroolien mukaan.
1. Valitse **Lisää käyttöoikeusrooli sovellukseen** -kohdan **Jaa tämä sovellus** -valintaikkunassa **Omat sovellukset**.
2. Valitse Contoson trimmaussovelluksen ruudun oikeassa alaosassa oleva **Lisää vaihtoehtoja (...)** -painike (...) ja valitse sitten **Hallitse rooleja**.

    ![Sovelluksen roolien hallinta](media/share-model-driven-app/manage-roles.png)

4. **Roolit**-osassa voit määrittää, annetaanko sovelluksen käyttöoikeus kaikille käyttöoikeusrooleille vai valituille rooleille. Valitse aiemmin luodut **trimmausyrityksen ajanvaraajien** ja **trimmaajien** roolit.

    > [!div class="mx-imgBorder"] 
    > ![Sovelluksen käyttöoikeusroolien valinta](media/share-model-driven-app/app-security-roles.png)

5. Valitse **Tallenna**.
 
## <a name="share-the-link-to-your-app"></a>Sovelluksen linkin jakaminen
1. Kopioi **Jaa linkki sovellukseen suoraan käyttäjille** -kohdan **Jaa tämä sovellus** -valintaikkunassa näkyvissä oleva URL-osoite.
 
2. Valitse **Sulje**.
3. Liitä sovelluksen URL-osoite paikkaan, jossa käyttäjät voivat ottaa sen käyttöön. Voit esimerkiksi julkaista sen SharePoint-sivustossa tai lähettää sähköpostitse.

> [!div class="mx-imgBorder"] 
> ![Jaa linkki](media/share-model-driven-app/share-model-driven-URL.PNG)

Sovelluksen URL-osoite on myös sovellusten suunnitteluohjelman **Ominaisuudet**-välilehdessä. 

> [!div class="mx-imgBorder"] 
> ![Kopioi sovelluksen URL-osoite](media/share-model-driven-app/app-designer-copy-web-url.png)

## <a name="about-predefined-security-roles"></a>Tietoja ennalta määritetyistä käyttöoikeusrooleista
Nämä ennalta määritetyt roolit ovat käytettävissä [!INCLUDE [powerapps](../../includes/powerapps.md)]-ympäristössä


|Käyttöoikeusrooli  |*Oikeudet  |Kuvaus |
|---------|---------|---------|
|Ympäristön tekijä     |  Ei ole       | Voivat luoda ympäristöön liittyviä uusia resursseja, kuten sovelluksia, yhteyksiä, mukautettuja ohjelmointirajapintoja, yhdyskäytäviä ja työnkulkuja Microsoft Flow -sovelluksen avulla. Ympäristön tietojen käyttöoikeuksia ei kuitenkaan ole. Lisätietoja: [Ympäristöjen yleiskatsaus](https://powerapps.microsoft.com/blog/powerapps-environments/)        |
|Järjestelmänvalvoja     |  Luonti, luku, kirjoitus, poisto, mukautukset, käyttöoikeusroolit       | On täydet ympäristön mukauttamisen ja hallinnan käyttöoikeudet, esimerkiksi käyttöoikeusroolien luominen, muokkaaminen ja delegoiminen. Ympäristön kaikkien tietojen tarkastelumahdollisuus. LIsätietoja: [Mukauttamiseen vaaditut oikeudet](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Järjestelmän mukauttaja     | Luonti (itse), luku (itse), kirjoitus (itse), poisto (itse), mukauttamiset         | Ympäristön täysi mukauttamisoikeus. Voivat kuitenkin tarkastella vain niitä ympäristöentiteettejä, joita he luovat. LIsätietoja: [Mukauttamiseen vaaditut oikeudet](https://docs.microsoft.com/dynamics365/customer-engagement/customize/privileges-required-customization)        |
|Common Data Service -palvelun käyttäjä     |  Luku, luonti (itse), kirjoitus (itse), poisto (itse)       | Voivat suorittaa sovelluksen ympäristössä ja suorittaa yleisiä tehtäviä omistamilleen tietueille.        |
|Delegoi     | Toimii toisen käyttäjän puolesta        | Sallii koodin suorituksen toisena käyttäjänä tai tekeytyneenä käyttäjänä.  Käytetään yleensä toisen käyttöoikeusroolin kanssa tietueiden käyttöoikeuden antamiseksi. Lisätietoja: [Tekeytyminen toiseksi käyttäjäksi](https://docs.microsoft.com/dynamics365/customer-engagement/developer/org-service/impersonate-another-user)        |

*Oikeudella on yleinen vaikutusalue, ellei toisin määritetä.

## <a name="next-steps"></a>Seuraavat vaiheet
[Mallipohjaisen sovelluksen käyttäminen mobiililaitteessa](../../user/run-app-client-model-driven.md)



