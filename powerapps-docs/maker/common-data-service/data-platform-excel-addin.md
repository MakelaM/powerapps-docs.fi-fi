---
title: Entiteettitietojen avaaminen Excelissä | Microsoft Docs
description: Avaa entiteettitietoja Excelissä vuorovaikutteiseen tarkasteluun ja muokkaukseen.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: clwesene
ms.openlocfilehash: 8dbf6088104270d9251b70eec9adf0642de2f879
ms.sourcegitcommit: 68fc13fdc2c991c499ad6fe9ae1e0f8dab597139
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/04/2018
ms.locfileid: "34445853"
---
# <a name="open-entity-data-in-excel"></a>Entiteettitietojen avaaminen Excelissä
Kun avaat entiteettitiedot Microsoft Excelissä, voit tarkastella ja muokata niitä nopeasti ja helposti Microsoft PowerAppsin Excel-apuohjelmalla. PowerAppsin Excel-apuohjelma vaatii Microsoft Excel 2016 -ohjelman.

![Excel-apuohjelma](./media/data-platform-cds-excel-addin/ExcelAddin.png "PowerApps Excel -apuohjelma")

## <a name="open-entity-data-in-excel"></a>Entiteettitietojen avaaminen Excelissä
1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa. Kaikki entiteetit tulevat esiin.
2. Napsauta sinua kiinnostavan entiteetin oikealla puolella olevaa kolmea pistettä (...).
3. Valitse **Avaa Excelissä** ja avaa luotu työkirja. Työkirja sisältää entiteetin sidontatiedot sekä ympäristöösi ja PowerAppsin Excel-apuohjelmaan suuntautuvat osoittimet.  
4. Mahdollista PowerAppsin Excel-apuohjelman suorittaminen napsauttamalla Excelissä kohtaa **Ota muokkaus käyttöön**. Excel-apuohjelma toimii Excel-ikkunan oikealla puolella olevassa ruudussa.
5. Jos et ole aikaisemmin suorittanut PowerAppsin Excel-apuohjelmaa, salli Excel-apuohjelman suorittaminen napsauttamalla kohtaa **Luota tähän apuohjelmaan**.
6. Jos sinua pyydetään kirjautumaan sisään, valitse **Kirjaudu sisään** ja kirjaudu sitten sisään samoilla tunnistetiedoilla, joita käytit [powerapps.com](https://web.powerapps.com)-sivustossa. Excel-apuohjelma kirjaa sinut aina kun mahdollista automaattisesti sisään aikaisemman sisäänkirjautumiskontekstin avulla. Varmista sen vuoksi, että Excel-apuohjelman oikeassa yläkulmassa on oikea käyttäjänimi.

Excel-apuohjelma lukee valitsemasi entiteetin tiedot automaattisesti. Huomaa, että työkirjassa ei ole mitään tietoja, ennen kuin Excel-apuohjelma noutaa ne.

## <a name="view-and-refresh-data-in-excel"></a>Tietojen tarkasteleminen ja päivittäminen Excelissä
Kun Excel-apuohjelma on lukenut entiteettitiedot työkirjaan, voit päivittää tietoja milloin tahansa napsauttamalla **Päivitä**-painiketta Excel-apuohjelmassa.

## <a name="edit-data-in-excel"></a>Tietojen muokkaaminen Excelissä
Voit tarvittaessa muuttaa entiteettitietoja ja julkaista ne uudelleen napsauttamalla Excel-apuohjelman **Julkaise**-painiketta.

Jos haluat muokata tietuetta, valitse laskentataulukon solu ja muuta sitten solun arvoa.

Uuden tietueen lisäystapoja:

* Napsauta laskentataulukkoa ja valitse sitten Excel-apuohjelmassa **Uusi**.
* Napsauta laskentataulukon viimeistä riviä ja paina sitten sarkainnäppäintä, kunnes kohdistin siirtyy kyseisen rivin viimeisen sarakkeen ulkopuolelle ja uusi rivi luodaan.
* Napsauta heti taulukon alla olevaa riviä ja ala kirjoittaa tietoja soluun. Kun siirrät kohdistuksen kyseisen solun ulkopuolelle, laskentataulukko laajenee sisältämään uuden rivin.

Tietueen poistotapoja:

* Napsauta hiiren kakkospainikkeella laskentataulukon poistettavan rivin vieressä olevaa rivinumeroa ja valitse sitten **Poista**.
* Napsauta hiiren kakkospainikkeella poistettavaa taulukon riviä ja valitse sitten **Poista** > **taulukon rivit**.

## <a name="add-or-remove-columns"></a>Sarakkeiden lisääminen tai poistaminen
Voit säätää laskentataulukkoon automaattisesti lisättäviä sarakkeita ja entiteettejä suunnittelutyökalulla.

1. Ota tietolähteen suunnittelutyökalu käyttöön Excel-apuohjelmassa napsauttamalla **Asetukset**-painiketta (rataskuvake) ja valitsemalla sitten **Ota suunnittelutila käyttöön**  -valintaruutu.
2. Valitse Excel-apuohjelmassa **Suunnittele**. Kaikki tietolähteet näkyvät luettelossa.
3. Napsauta tietolähteen vieressä olevaa **muokkauspainiketta** (kynäkuvake).
4. Säädä tarvittaessa **Valitut kentät** -kentän luetteloa:
   * Jos haluat lisätä kentän **Käytettävissä olevat kentät** -kentän **Valitut kentät** -kenttään, napsauta kenttää ja valitse sitten **Lisää**. Vaihtoehtoisesti voit kaksoisnapsauttaa kenttää.
   * Jos haluat poistaa kentän **Valitut kentät** -kentästä, napsauta kenttää ja valitse sitten **Poista**. Vaihtoehtoisesti voit kaksoisnapsauttaa kenttää.
   * Jos haluat muuttaa kenttien järjestystä, napsauta kenttää **Valitut kentät** -kentässä ja valitse sitten **ylöspäin** tai **alaspäin**.
5. Ota tietolähteen muutokset käyttöön napsauttamalla **Päivitä** ja poistu sitten suunnittelutyökalusta valitsemalla **Valmis**. Jos olet lisännyt kentän (sarakkeen), nouda päivitetty tietojoukko napsauttamalla **Päivitä**-painiketta.

> [!NOTE]
> Varmista aina, että lisäät tunnuksen ja pakolliset kentät työkirjaasi, koska saatat saada virheitä julkaisemisen yhteydessä.

> [!NOTE]
> Kun lisäät hakukenttiä, muista lisätä sekä tunnus että näyttökentät.

## <a name="troubleshooting"></a>Vianmääritys
Osa ongelmista voidaan ratkaista muutamalla helpolla vaiheella.

* Kaikki entiteetit eivät tue muokkaamista ja uusien tietueiden luomista. Nämä entiteetit avautuvat Excelissä, ja niiden avulla voit tarkastella tietoja mutta julkaiseminen on poistettu käytöstä.
* Hakukenttiä on muokattava apuohjelman avulla, jotta voidaan varmistaa oikeaan tietueeseen viittaaminen. Näiden kenttien päivittämistä kopioimalla ja liittämällä tai suoraan kenttään kirjoittamalla ei tueta.


Jos kohtaamaasi ongelmaa ei ole kuvattu tässä, ota yhteyttä meihin [tukisivujen](https://powerapps.microsoft.com/support/) kautta.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Entiteetin kenttien hallinta](data-platform-manage-fields.md)
* [Entiteettien välisten suhteiden määrittely](data-platform-entity-lookup.md)
* [Sovelluksen luominen Common Data Service for Apps -palvelun avulla](../canvas-apps/data-platform-create-app.md)
* [Sovelluksen luominen alusta alkaen Common Data Service for Apps -palvelun avulla](../canvas-apps/data-platform-create-app-scratch.md)

