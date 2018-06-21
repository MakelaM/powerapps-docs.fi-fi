---
title: Tuo tai vie tietoja Common Data Service for Appsista
description: Tietojen joukkotuonti ja vienti Excelistä tai CSV-tiedostoista Common Data Service (CDS) for Appsin entiteetteihin tietojen Excelistä hakemisen ja tietojen viemisen avulla
author: sabinn-msft
ms.service: powerapps
ms.topic: conceptual
ms.component: cds
ms.date: 05/14/2018
ms.author: sabinn
ms.openlocfilehash: 7f3e16be5bba1874759e0f9e40dc455f1e29c2bc
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697459"
---
# <a name="import-or-export-data-from-the-common-data-service-for-apps"></a>Tuo tai vie tietoja Common Data Service for Appsista

Jos haluat mahdollisuuden tietojen joukkotuontiin ja vientiin Excelistä tai CSV-tiedostoista, voit käyttää Hae tiedot Excel-tiedostosta- ja Vie tiedot -ominaisuuksia päivitetyissä Common Data Service (CDS) for Apps -ympäristöissä.

Voit tuoda tiedoston entiteettiin Excelistä tai csv-tiedostosta kahdella tapaa

## <a name="option-1-import-by-creating-and-modifying-a-file-template"></a>Vaihtoehto 1: Tuo luomalla tiedostomalli ja muokkaamalla sitä

Jokaisella entiteetillä on pakolliset kentät, jotka on oltava syötetiedostossa. Sujuvampi menetelmä on luoda malli viemällä ensin tiedot entiteetistä ja tuomalla ne entiteettiin käyttämällä samaa tiedostoa (joka on muokattu tiedoillasi). Säästät aikaa ja vaivaa, kun jokaisen entiteetin pakollisia kenttiä ei tarvitse ottaa huomioon.

1. Valmistele tiedostomalli

    - Aloita viemällä entiteettitiedot csv-tiedostoon noudattamalla kohdassa Tietojen vieminen CSV-tiedostoon olevien ohjeiden mukaisesti
    - Määritä suunnitelma tietojen yksilöllisyyden varmistamiseksi käyttämällä joko perusavaimia tai vaihtoehtoisia avaimia.
    - Alla olevassa osassa tietoja siitä, miten yksilöllisyys varmistetaan ennen tietojen tuomista entiteettiin

1. Muokkaa tiedosto tiedoillasi

    - Kopioi tiedot Excel- tai CSV-tiedostosta juuri luomaasi malliin

1. Tuo tiedosto
    - Suurenna [powerapps.com](https://web.powerapps.com/)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa
    - Valitse entiteetti, johon haluat tuoda tiedot
    - Napsauta kolmea pistettä tai yläreunan valikkoa ja valitse **Nouda tiedot** ja napsauta tai napauta **Hae tiedot Excelistä**

> [!NOTE]
> Jos tietoja tuodaan useampaan kuin yhteen entiteettiin, valitse yläreunan valikossa **Nouda tiedot** ja napsauta tai napauta **Hae tiedot Excelistä**. Sinun pitäisi pystyä valitsemaan useita entiteettejä ja valitsemaan **Seuraava**

![Esimerkki tietojen tuomisesta Tili-entiteettiin](./media/data-platform-import-export/import-data-to-account.png)

- Näin pääset **Tuo tiedot** -näyttöön, jossa voit valita, tuodaanko tiedot Excel- vai CSV-tiedostolla
- Napsauta tai napauta **Lataa**
- Valitse tiedosto ja aloita tiedoston lataaminen ohjeita noudattamalla

![Esimerkki tiedoston lataamisesta Tili-entiteettiin](./media/data-platform-import-export/upload-account.png)

- Kun tiedosto on ladattu ja yhdistämisen tila on vihreä, valitse **Tuo** oikeassa yläkulmassa. Jos yhdistämisen aikana ilmenee virheitä, siirry yhdistämisvirheisiin ja korjaa ne alla olevan osion ohjeiden mukaisesti

![Esimerkki onnistuneesta yhdistämisen tilasta ja Tuo-painikkeesta](./media/data-platform-import-export/success-map-imp.png)

- Kun **tuonti tehtiin loppuun onnistuneesti**, näet lisäysten ja päivitysten kokonaismäärän

![Esimerkki onnistuneesta tuonnista ja lisäysten ja päivitysten määrästä](./media/data-platform-import-export/success-imp-insert.png)

> [!NOTE]
> Käytämme päivityslisäyksen (päivitys tai lisäys) logiikkaa jo olemassa olevan tietueen päivittämiseen tai uuden tietueen lisäämiseen.

## <a name="option-2-import-by-bringing-your-own-source-file"></a>Vaihtoehto 2: Tuo käyttämällä omaa lähdetiedostoasi

Jos olet edistynyt käyttäjä ja perehtynyt hyvin Common Data Service for Apps -entiteetin tietyn entiteetin pakollisiin kenttiin, voit määrittää oman Excel- tai CSV-lähdetiedoston ja noudata kohdassa **Tuo tiedosto** annettuja ohjeita

## <a name="navigating-mapping-errors"></a>Yhdistämisvirheisiin siirtyminen

Jos ilmenee yhdistämisvirheitä, valitse tiedoston lataamisen jälkeen **Yhdistämisen tila** ja tarkista ja korjaa kentän yhdistämisvirheet seuraavien vaiheiden avulla.

- Käytä oikeanpuoleista avattavaa luetteloa **Näytä**-kohdan alla ja käy läpi **Yhdistämättömät kentät**, **Kentät, joissa on virhe** tai **Pakolliset kentät**

> [!TIP]
> Sen mukaan, saatko varoituksen vai virheen, aloita tarkistamalla **Yhdistämättömät kentät** tai **Kentät, joissa on virhe** **Kenttien yhdistämismääritykset** -kohdan avattavan luettelon avulla

![Esimerkki osittaisesta vastaavuudesta kenttien yhdistämismäärityksiin liittyvien varoitusten vuoksi](./media/data-platform-import-export/partial-match.png)

![Esimerkki kenttien yhdistämismääritysongelmiin siirtymisestä](./media/data-platform-import-export/navigate-mappings.png)

![ Esimerkki kenttien yhdistämismäärityksiin liittyvien varoitusten tarkistamisesta ja korjaamisesta](./media/data-platform-import-export/inspect-warnings.png)

- Kun olet korjannut kaikki virheet ja/tai varoitukset, valitse **Tallenna muutokset** oikeassa yläkulmassa, jolloin palaat takaisin **Tuo tiedot** -näyttöön
- Kun **Yhdistämisen tila** -sarakkeessa näkyy **Valmis** vihreänä, valitse **Tuo** oikeassa yläkulmassa
- Kun saat **Tuonti tehtiin loppuun onnistuneesti** -viestin, näet lisäysten ja päivitysten kokonaismäärän

## <a name="ensuring-uniqueness-while-importing-data-into-entity-from-excel-or-csv"></a>Yksilöllisyyden varmistaminen tuotaessa tietoja Excelistä tai CSV-tiedostosta entiteettiin

Common Data Service for Apps -entiteetit käyttävät perusavainta CDS-entiteetin taulukon sisältämien tietueiden tunnistamiseen yksilöivästi. CDS-entiteetin perusavain on GUID-tunnus ja oletusarvoinen perusta tietueen tunnistamiselle. Tietotoiminnot, kuten tietojen tuominen CDS-entiteettiin, näyttävät oletusarvoiset perusavaimet.

Esimerkki: Tili-entiteetin perusavain on accountid

![Esimerkkivientitiedosto Tili-entiteetistä, jossa accountid näkyy perusavaimena](./media/data-platform-import-export/export-pk.png)

Joskus perusavain ei välttämättä riitä ja/tai vastaa tarvetta integroitaessa tietoja ulkoisesta lähteestä. Tätä varten CDS mahdollistaa vaihtoehtoisten avaimien määrittämisen perusavaimen paikalla olevan tietueen tunnistamiseksi yksilöivästi.

Esimerkki: Voit määrittää Tili-entiteetin vaihtoehtoiseksi avaimeksi transactioncurrencyid käyttämällä luonnolliseen avaimeen perustuvaa tunnistamista (esimerkiksi Yhdysvaltain dollari yllä näkyvän GUID-arvon *88c6c893-5b45-e811-a953-000d3a33bcb9* sijaan). Voit myös valita valuuttasymbolin tai valuutan nimen avaimeksi.

![Esimerkki vaihtoehtoisen avaimen luomisesta Valuutta-entiteetissä](./media/data-platform-import-export/create-ak.png)

![Esimerkkivientitiedosto Tili-entiteetistä, jossa valuutan nimi näkyy luonnollisena avaimena](./media/data-platform-import-export/export-nk.png)

Käyttäjä voi edelleen käyttää perusavaimia tunnisteena vaihtoehtoisten avainten määrittämisen jälkeen. Yllä olevassa esimerkissä ensimmäinen tiedosto on siis yhä kelvollinen, mikäli GUID-tunnukset ovat kelvollisia tietoja.

## <a name="export-data-to-csv"></a>Tietojen vieminen CSV-tiedostoon

Voit suorittaa tietojen kertaluontoisen viennin vakioentiteetistä tai mukautetusta entiteetistä ja voit viedä tietoja useammasta entiteetistä kerrallaan. Jos viet tietoja useammasta kuin yhdestä entiteetistä, jokainen entiteetti viedään omaan Microsoft csv -tiedostoonsa.

1. Suurenna [powerapps.com](https://web.powerapps.com/)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa
1. Valitse entiteetti, josta haluat viedä tiedot
1. Napsauta kolmea pistettä tai yläreunan valikkoa ja valitse **Vie** ja napsauta tai napauta **Tiedot**

    ![Esimerkki tietojen viemisestä Tili-entiteetistä](./media/data-platform-import-export/export-account.png)

    > [!NOTE]
    > Jos tietoja viedään useasta entiteetistä, valitse yläreunan valikossa **Vie** ja napsauta tai napauta **Tiedot**. Sinun pitäisi pystyä valitsemaan useita entiteettejä

1. Kun vienti on valmis, sinun pitäisi pystyä **lataamaan viedyt tiedot**, jolloin sinun pitäisi saada linkki ladattavaan CSV-tiedostoon

    ![Esimerkki viennistä, jossa näkyy onnistunut vienti ja linkki ladattavaan tiedostoon](./media/data-platform-import-export/export-success.png)

## <a name="unsupported-data-types"></a>Tietotyypit, joita ei tueta

Seuraavia tietotyyppejä ei tällä hetkellä tueta

- Aikavyöhyke
- Monivalinta-asetusjoukko
- Kuva
