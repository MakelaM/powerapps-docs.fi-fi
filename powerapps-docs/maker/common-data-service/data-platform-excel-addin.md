---
title: Entiteetin tietojen avaaminen Excelissä | Microsoft Docs
description: Avaa entiteetin tiedot Excelissä vuorovaikutteista tarkastelua ja muokkaamista varten.
author: lancedMicrosoft
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/21/2018
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="open-entity-data-in-excel"></a>Entiteetin tietojen avaaminen Excelissä
Kun avaat entiteetin tiedot Microsoft Excelissä, voit nopeasti ja helposti tarkastella ja muokata tietoja Microsoft PowerApps Excel -apuohjelman avulla. PowerAppsin Excel-apuohjelma edellyttää, että käytössä on Microsoft Excel 2016.

![Excel-apuohjelma](./media/data-platform-cds-excel-addin/ExcelAddin.png "PowerAppsin Excel-apuohjelma")

## <a name="open-entity-data-in-excel"></a>Entiteetin tietojen avaaminen Excelissä
1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Entiteetit**-kohtaa vasemmanpuoleisessa siirtymisruudussa. Kaikki entiteetit näytetään.
2. Valitse sen entiteetin oikealla puolella olevat kolme pistettä (...), josta olet kiinnostunut.
3. Valitse **Avaa Excelissä** ja avaa luotu työkirja. Tämä työkirja sisältää entiteetin sidonnan tietoja, ympäristön osoittimen ja PowerAppsin Excel-apuohjelman osoittimen.  
4. Valitse Excelissä **Ota muokkaus käyttöön**, jolloin PowerAppsin Excel-apuohjelma voidaan suorittaa. Excel-apuohjelma suoritetaan Excel-ikkunan oikealla puolella olevassa ruudussa.
5. Jos tämä on ensimmäinen kerta, kun suoritat PowerAppsin Excel-apuohjelman, salli Excel-apuohjelman suoritus valitsemalla **Luota tähän apuohjelmaan**.
6. Jos sinua pyydetään kirjautumaan sisään, valitse **Kirjaudu sisään** ja anna samat tunnistustiedot kuin [powerapps.com](https:///?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa. Excel-apuohjelma käyttää edellistä sisäänkirjauksen kontekstia ja kirjaa sinut automaattisesti sisään, jos se on mahdollista. Tarkista tämän vuoksi käyttäjätunnus Excel-apuohjelman oikeassa yläkulmassa.

Excel-apuohjelma lukee valitsemasi entiteetin tiedot automaattisesti. Huomaa, että työkirjassa ei ole tietoja ennen kuin Excel-apuohjelma on lukenut ne sinne.

## <a name="view-and-refresh-data-in-excel"></a>Tietojen tarkasteleminen ja päivittäminen Excelissä
Kun Excel-apuohjelma on lukenut entiteetin tiedot työkirjaan, voit päivittää tiedot milloin tahansa valitsemalla Excel-apuohjelman **Päivitä**-kohdan.

## <a name="edit-data-in-excel"></a>Tietojen muokkaaminen Excelissä
Voit muuttaa entiteetin tietoja haluamallasi tavalla ja julkaista ne uudelleen valitsemalla Excel-apuohjelmassa **Julkaise**.

Voit muokata tietuetta valitsemalla solun työkirjassa ja muuttamalla sitten solun arvoa.

Voit lisätä uuden tietueen seuraavasti:

* Napsauta työkirjan mitä tahansa kohtaa ja valitse sitten Excel-apuohjelmassa **Uusi**.
* Valitse työkirjan viimeinen rivi ja paina sarkainnäppäintä niin kauan, kunnes osoitin siirtyy kyseisen rivin viimeiseen sarakkeeseen. Nyt uusi rivi on luotu.
* Valitse työkirjan alla oleva rivi ja syötä soluun tietoja. Kun siirrät kohdistuksen solusta pois, työkirja laajenee niin, että se sisältää uuden rivin.

Voit poistaa tietueen seuraavasti:

* Napsauta hiiren kakkospainikkeella työkirjan poistettavan rivin vieressä olevaa rivinumeroa ja valitse **Poista**.
* Napsauta hiiren kakkospainikkeella työkirjan poistettavaa riviä ja valitse **Poista** > **Taulukon rivit**.

## <a name="add-or-remove-columns"></a>Sarakkeiden lisääminen tai poistaminen
Voit muokata työkirjaan automaattisesti lisättäviä sarakkeita ja entiteettejä suunnitteluohjelman avulla.

1. Ota käyttöön Excel-apuohjelman tietolähteen suunnitteluohjelma valitsemalla **Asetukset**-painike (ratassymboli) ja valitsemalla sitten**Ota suunnittelu käyttöön** -valintaruutu.
2. Valitse Excel-apuohjelmassa **Suunnittelu**. Kaikki tietolähteet luetteloidaan.
3. Valitse tietolähteen vieressä oleva **Muokkaa**-painike (kynäsymboli).
4. Muokkaa luetteloa **Valitut kentät** -kentässä haluamallasi tavalla:
   * Voit lisätä kentän **Käytettävissä olevat kentät** -kentästä **Valitut kentät** -kenttään valitsemalla kentän ja valitsemalla sitten **Lisää**. Vaihtoehtoisesti voit kaksoisnapsauttaa kenttää.
   * Voit poistaa kentän **Valitut kentät** -kentästä valitsemalla kentän ja valitsemalla sitten **Poista**. Vaihtoehtoisesti voit kaksoisnapsauttaa kenttää.
   * Voit muuttaa kenttien järjestystä valitsemalla **Valitut kentät** -kentän ja valitsemalla sitten **Ylös** tai **Alas**.
5. Ota tietolähteen muutokset käyttöön valitsemalla **Päivitä**. Poistu suunnitteluohjelmasta valitsemalla **Valmis**. Jos olet lisännyt kentän (sarakkeen), valitse **Päivitä**, jolloin näkyviin tulee päivitetty tietojoukko.

> [!NOTE]
> Varmista, että työkirja sisältää aina tunnuksen ja pakolliset kentät, koska niiden vuoksi voi tulla useita virheitä julkaisemisen yhteydessä.

> [!NOTE]
> Kun hakukenttiä lisätään, varmista, että sekä tunnus että näyttökentät lisätään.

## <a name="troubleshooting"></a>Vianmääritys
Joitakin ongelmia voi ratkaista helppojen vaiheiden avulla.

* Kaikki entiteetit eivät tue uusien tietueiden muokkaamista ja luomista. Nämä entiteetit avataan Excelissä. Niiden avulla voi tarkastella tietoja, mutta julkaiseminen ei ole käytössä.
* Hakukenttiä on muokattava apuohjelman avulla. Näin varmistetaan, että viitatut tietueet ovat oikeita. Näiden kenttien päivittämistä kopioimalla ja liittämällä tai kirjoittamalla suoraan kenttään ei tueta.


Jos ongelmaa ei ole kuvattu tässä, ota yhteyttä [tukisivujen](https://powerapps.microsoft.com/support/) kautta.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Entiteetin kenttien hallinta](data-platform-manage-fields.md)
* [Entiteettien välisten suhteiden määrittäminen](data-platform-entity-lookup.md)
* [Sovelluksen luominen Common Data Servicen avulla](../canvas-apps/data-platform-create-app.md)
* [Sovelluksen luominen alusta Common Data Servicen avulla](../canvas-apps/data-platform-create-app-scratch.md)

