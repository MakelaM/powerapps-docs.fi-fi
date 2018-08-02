---
title: Sovellusten siirtäminen ympäristöjen ja vuokraajien välillä | Microsoft Docs
description: Ohjeet PowerApps-sovellusten siirtämiseen ympäristöjen ja vuokraajien välillä
author: jamesol-msft
manager: kvivek
ms-topic: conceptual
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.author: jamesol
ms.openlocfilehash: 3a4aeda30f8d4f01e2a85e186a769fa19ac29883
ms.sourcegitcommit: 2e7b621066cdc3e7be329d5213ecfee0b4223641
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/30/2018
ms.locfileid: "39349589"
---
# <a name="environment-and-tenant-app-migration-through-packaging"></a>Sovellusten siirtäminen ympäristöjen ja vuokraajien välillä paketoinnin avulla
Lue, miten resursseja voidaan siirtää yhdestä ympäristöstä toiseen paketoinnin avulla. Nämä ympäristöt voivat olla samassa vuokraajassa tai eri vuokraajissa.

## <a name="the-scenario"></a>Skenaario
Yksi yleinen skenaario, jossa voi olla tarpeen siirtää resursseja, on sellainen, jossa käytössä on testaus- ja kehitysympäristöt sekä tuotantoympäristö. Kehittäjillä ja testaajilla on laajat käyttöoikeudet ympäristöjensä sovelluksiin. Toisaalta, kun on aika siirtää uusi sovellus tuotantoon, kyseisessä ympäristössä on tarkat käyttöoikeussäännöt sovelluksen päivitykseen tai muuttamiseen.

Toinen skenaario on sellainen, jossa eri asiakkailla on omat ympäristöt ja tiedot. Kun lisätään uusi asiakas, hänelle luodaan uusi ympäristö, ja tässä skenaariossa sovellukset siirrettäisiin kyseiseen ympäristöön.

## <a name="which-resources-can-i-migrate-through-packaging"></a>Mitä resursseja voin siirtää paketoinnin avulla?
Kun viet sovelluksen, siihen liittyvät resurssit siirretään myös pakettiin.  Aluksi tuetaan vain osaa kaikista resurssityypeistä alla olevan taulukon mukaisesti.

| Resurssin tyyppi | Tuetaan | Tuontivaihtoehdot |
| --- | --- | --- |
| Sovellus |Kyllä |Sovelluksen tuomiseksi ympäristöön on kaksi vaihtoehtoa: <ol><li><b>Luo uusi</b> – Sovellus luodaan uutena sovelluksena ympäristössä, johon paketti tuodaan.</li> <li><b>Päivitä</b> – Sovellus on jo olemassa ympäristössä ja se päivitetään, kun tämä paketti tuodaan.</li></ol> |
| Työnkulku |Kyllä |Työnkulun tuomiseksi ympäristöön on kaksi vaihtoehtoa: <ol><li><b>Luo uusi</b> – Työnkulku luodaan uutena työnkulkuna ympäristössä, johon paketti tuodaan.</li> <li><b>Päivitä</b> – Työnkulku on jo olemassa ympäristössä ja päivitetään, kun tämä paketti tuodaan.</li></ol> <b>Huom.: </b>Kaikki resurssit, jotka työnkulku vaatii, sisällytetään myös vietävään sovelluspakettiin ja ne täytyy määrittää, kun paketti tuodaan. |
| Mukautetut liittimet |Ei |Jos sovellus vaatii mukautetun liittimen, sen viemistä osana pakettia <b>ei tällä hetkellä tueta</b>. <p></p> Jos sinulla on sovellus, joka vaatii mukautetun liittimen, tällä hetkellä ainoa vaihtoehto on luoda liitin uudelleen tai päivittää se manuaalisesti kohdeympäristössä ja valita se, kun tuot paketin. |
| Yhteydet |Ei |Jos sovellus vaatii liittimen (kuten SQL-liittimen tunnistetietojen kanssa), yhteyden tai tunnistetietojen viemistä osana pakettia ei tällä hetkellä tueta. <p></p> Jos sinulla on sovellus, joka vaatii jaetun yhteyden (kuten SQL), tällä hetkellä ainoa vaihtoehto on luoda yhteys uudelleen kohdeympäristössä asianmukaisilla tunnistetiedoilla ja valita yhteys, kun tuot paketin. |
| CDS-mukautukset |Ei |CDS-mukautusten viemistä osana pakettia ei enää tueta. Tätä tuetaan nyt ympäristön oletusratkaisun viemisen ja tuomisen kautta alla olevan artikkelin mukaisesti. |
| Yhdyskäytävät |Ei |Yhdyskäytäviä tuetaan vain oletusympäristöissä (ja {vuokraajan nimi} (esikatselusta) -ympäristöissä), joten viemistä/siirtämistä ei tueta. |

## <a name="how-do-i-get-access-to-packaging-for-my-app"></a>Kuinka voin käyttää paketointia sovellukselleni?
Sovelluksen vienti on käytettävissä käyttäjille, joilla on sovelluksen muokkausoikeus.

Sovelluksen tuonti on käytettävissä käyttäjille, joilla on ympäristön tekijä -käyttöoikeus kohdeympäristössä.

Käyttäjällä täytyy olla PowerAppsin palvelupaketti 2 tai PowerAppsin palvelupaketin 2 kokeilukäyttöoikeus sovellusten viemistä tai tuomista varten.

> [!NOTE]
> Kun paketointi on esikatselussa, kuka tahansa käyttäjä, jolla on kelvollinen PowerApps-käyttöoikeus, voi testata sovellustensa ja ympäristöjensä paketointia.

## <a name="exporting-an-app"></a>Sovelluksen vieminen
1. Napsauta tai napauta osoitteessa http://web.powerapps.com kohtaa **Sovellukset**, valitse vietävän sovelluksen kolme pistettä ja valitse **Vie (esiversio)**.

    ![Viennin valinta](./media/environment-and-tenant-migration/select-export.png)
2. Kun paketin vientisivu avautuu, anna paketille nimi ja kuvaus vastaaviin kohtiin.

    ![Paketin tietojen tarkistus](./media/environment-and-tenant-migration/package-details.png)
3. Käy läpi paketin sisältö -kohdassa voit valinnaisesti lisätä kommentteja tai huomautuksia tai muuttaa asetuksia yksittäisten resurssien tuomiselle kohdeympäristöön paketin tuomisen aikana.

    ![Paketin sisällön määritys](./media/environment-and-tenant-migration/export-package-content.png)

4. Kun olet valmis, valitse **Vienti**. Pakettitiedoston lataus alkaa muutaman sekunnin kuluttua.

## <a name="importing-an-app"></a>Sovelluksen tuominen
1. Napsauta tai napauta osoitteessa http://web.powerapps.com kohtaa **Sovellukset** ja valitse **Tuo paketti (esiversio)**.

    ![Tuonnin valinta](./media/environment-and-tenant-migration/select-import.png)
2. Valitse **Lataa** ja valitse sovelluspakettitiedosto, jonka haluat tuoda.

    ![Pakettitiedoston valinta](./media/environment-and-tenant-migration/select-file.png)
3. Kun paketti on ladattu palvelimeen, sinun täytyy tarkistaa paketin sisältö ja antaa lisätietoja kohteille, jotka on merkitty punaisella kuvakkeella, valitsemalla kohteiden jakoavainkuvakkeet ja antamalla vaaditut tiedot.

    ![Paketin sisällön läpikäynti](./media/environment-and-tenant-migration/import-package-content.png)
4. Kun olet antanut kaikki vaaditut tiedot, valitse **Tuonti**.

    ![Päivitetty paketin sisältö](./media/environment-and-tenant-migration/import-package-content-dirty.png)
5. Kun tuonti on valmis, sinut ohjataan automaattisesti (alla olevaa muistuttavalle) sivulle, jossa näytetään, onko tuonti onnistunut.

    ![Tuonnin tulosten tarkistus](./media/environment-and-tenant-migration/import-results.png)

> [!NOTE]
>  Jos tuot sovellusta ja valitsit olemassa olevan sovelluksen **päivittämisen**, uudet muutokset tallennetaan sovellusten luonnoksena.  Sinun tulee [julkaista](http://powerapps.microsoft.com/tutorials/save-publish-app/#publish-an-app) muutokset, jotta ne ovat saatavilla kaikille sovellusten käyttäjille.
>
>

## <a name="exporting-cds-customizations-and-model-driven-apps"></a>CDS-mukautusten ja mallipohjaisten sovellusten vieminen
Osoitteessa https://web.powerapps.com rakennettujen entiteettien, asetusjoukkojen mukautusten tai mallipohjaisten sovellusten viemistä tuetaan oletusympäristöratkaisun viemisellä seuraavasti:
> [!NOTE]
>  Jos haluat lisätietoja ratkaisuista PowerAppsissa, katso aihe [Ratkaisujen johdanto](../developer/common-data-service/introduction-solutions.md).
>
>

1. Valitse osoitteessa http://web.powerapps.com suunnittelutila **Malliin perustuva (esikatselu)** ympäristössäsi.

    ![Malliin perustuvan suunnittelutilan valinta](./media/environment-and-tenant-migration/select-model-driven.png)

2. Avaa tämän ympäristön oletusratkaisun ratkaisunhallinta valitsemalla vasemmasta siirtymispalkista **Lisäasetukset**.

    ![Lisäasetusten valinta](./media/environment-and-tenant-migration/select-advanced.png)

3. Valitse **Vie ratkaisu** ja suorita vaaditut vaiheet.  Ratkaisupakettitiedoston lataus alkaa muutaman sekunnin päästä.

    ![Viennin valinta](./media/environment-and-tenant-migration/select-export-solution.png)

## <a name="importing-cds-customization-and-model-driven-apps"></a>CDS-mukautusten ja mallipohjaisten sovellusten tuominen
CDS-ratkaisupaketin tuominen vaatii valitettavasti manuaalisen ratkaisun, jota pyrimme aktiivisesti korjaamaan:

1. Valitse osoitteessa http://web.powerapps.com suunnittelutila **Malliin perustuva (esikatselu)** ympäristössäsi.

    ![Malliin perustuvan suunnittelutilan valinta](./media/environment-and-tenant-migration/select-model-driven.png)

2. Avaa tämän ympäristön oletusratkaisun ratkaisunhallinta valitsemalla vasemmasta siirtymispalkista **Lisäasetukset**.

    ![Lisäasetusten valinta](./media/environment-and-tenant-migration/select-advanced.png)

3. Kopioi osoite selaimestasi, tee siihen seuraavat muutokset ja siirry uuteen osoitteeseen selaimessasi:

    * Osoitteen alkuperäinen rakenne: https://{organisaationyksilöivänimi}.crm.dynamics.com/tools/solution/edit.aspx?id={ratkaisunnimi}

        ![URL-osoitteen muokkaus](./media/environment-and-tenant-migration/edit-url.png)

    * Osoitteen uusi rakenne: https://{organisaationyksilöivänimi}.crm.dynamics.com/tools/solution/SolutionImportWizard.aspx

        ![Paketin valinta](./media/environment-and-tenant-migration/select-package.png)

4. Valitse tuotava CDS-ratkaisupakettitiedosto ja suorita ohjattu toiminto.

5. Jos tuonti onnistuu, sinulle näytetään seuraava vahvistusikkuna. Jotta ratkaisun muutokset olisivat saatavilla muille ympäristön mukauttajille, valitse **Julkaise kaikki mukautukset**

    ![Onnistunut tuonti](./media/environment-and-tenant-migration/successful-import.png)
