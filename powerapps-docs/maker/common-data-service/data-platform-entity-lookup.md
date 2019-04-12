---
title: Entiteettien välisen suhteen luominen hakukentän avulla | Microsoft Docs
description: Vaiheittaiset ohjeet entiteettien välisen suhteen luomiseksi PowerAppsissa hakukentän avulla.
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 02/21/2019
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-relationship-between-entities"></a>Entiteettien välisen suhteen luominen
Yhden entiteetin tiedot liittyvät usein toisen entiteetin tietoihin. Jos käytettävissä on esimerkiksi **Opettajat**- ja **Kurssi**-entiteetti, **Kurssi**-entiteetillä voi olla hakusuhde **Opettajan**-entiteettiin. Se osoittaa, kuka kurssilla opettaa. Voit käyttää hakukenttää näyttämään **Opettajat**-entiteetin tiedot. Tätä kutsutaan yleisesti hakukentäksi.

## <a name="define-a-relationship"></a>Suhteen määrittäminen
Voit luoda yhdestä entiteetistä toiseen (tai entiteetille itsensä kanssa) useita suhdetyyppejä. Jokaisella entiteetillä voi olla useita entiteettejä ja jokaisella entiteetillä voi olla useita suhteita toiseen entiteettiin. Yleisiä suhdetyyppejä ovat esimerkiksi seuraavat:

* **Monta yhteen** - Tässä suhdetyypissä jokainen entiteetin A tietue voi vastata useaa entiteetin B tietuetta, mutta jokainen entiteetin B tietue voi vastata vain yhtä entiteetin A tietuetta. Esimerkki: luokalla on yksi luokkahuone. Tämä on yleisin suhdetyyppi. Se löytyy kenttäluettelosta **hakukenttänä**
* **Yksi moneen** - Tässä suhdetyypissä jokainen entiteetin B tietue voi vastata useaa entiteetin A tietuetta, mutta jokainen entiteetin A tietue voi vastata vain yhtä entiteetin B tietuetta. Esimerkki: yksi opettaja opettaa useilla kursseilla.
* **Monta moneen** - Tässä suhdetyypissä jokainen entiteetin A tietue voi vastata useita entiteetin B tietueita ja päinvastoin. Esimerkki: opiskelijat voivat ottaa osaa useille kursseille ja jokaisella kurssilla voi olla useita opiskelijoita.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>Hakukentän lisääminen (monta yhteen -suhde)

Voit lisätä hakusuhteen entiteettiin luomalla suhteen **Suhteet**-välilehdessä. Määritä entiteetti, jolle haluat luoda suhteen.

1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Entiteetit**-kohtaa vasemmanpuoleisessa siirtymisruudussa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/entitylist.png "Entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaan entiteettiä tai [luo uusi entiteetti](data-platform-create-entity.md)

3. Valitse **Suhteet**

4. Valitse **Lisää suhde**. Näyttöön tulee uusi paneeli, jossa voit valita entiteetin, jolle uusi suhde luodaan. Valitse entiteetti avattavasta **Liittyvä entiteetti** -luettelosta.

    > [!div class="mx-imgBorder"] 
    > ![Monta yhteen -suhde](./media/data-platform-cds-newrelationship/manytoone-1.png "Monta yhteen -suhde")

5. Kun entiteetti on valittu, hakukentissä näkyy ensisijainen entiteetti. Nimiksi tulee entiteettien oletusnimet (tässä esimerkissä Luokkahuone). Voit muuttaa niitä tarvittaessa.

    ![Monta yhteen -suhde](./media/data-platform-cds-newrelationship/manytoone-2.png "Monta yhteen -suhde")

6. Valitse **Valmis** ja lisää entiteettiin suhde. Valitse sitten **Tallenna entiteetti**.

    > [!div class="mx-imgBorder"] 
    > ![Monta yhteen -suhde](./media/data-platform-cds-newrelationship/manytoone-3.png "Monta yhteen -suhde")

## <a name="add-a-one-to-many-relationship"></a>Yksi moneen -suhteen lisääminen

Voit lisätä yksi moneen -suhteen luomalla suhteen **Suhteet**-välilehdessä. Määritä entiteetti, jolle haluat luoda suhteen.

1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Entiteetit**-kohtaa vasemmanpuoleisessa siirtymisruudussa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/entitylist.png "Entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaan entiteettiä tai [luo uusi entiteetti](data-platform-create-entity.md)

3. Valitse **Suhteet**

4. Valitse **Lisää suhde** -kohdan oikealla puolella oleva alanuoli. Tämän jälkeen voit valita jommankumman suhdetyypin. Valitse **Yksi moneen**. Näyttöön tulee uusi paneeli, jossa voit valita entiteetin, jolle uusi suhde luodaan. Valitse entiteetti avattavasta **Liittyvä entiteetti** -luettelosta.

    ![Yksi moneen -suhde](./media/data-platform-cds-newrelationship/onetomany-1.png "Yksi moneen -suhde")

5. Kun entiteetti on valittu, hakukentissä näkyy ensisijainen entiteetti. Nimiksi tulee entiteettien oletusnimet (tässä esimerkissä Kurssi). Voit muuttaa niitä tarvittaessa.

    > [!NOTE]
    > Jos kyseessä ovat yksi moneen -suhteet, hakukenttä luodaan liittyvälle entiteetille, ei nykyiselle valittuna olevalle entiteetille. Jos haluat nykyiselle entiteetille hakukentän, luo monta yhteen -suhde.

    > [!div class="mx-imgBorder"] 
    > ![Yksi moneen -suhde](./media/data-platform-cds-newrelationship/onetomany-2.png "Yksi moneen -suhde")

6. Valitse **Valmis** ja lisää entiteettiin suhde. Valitse sitten **Tallenna entiteetti**.

    > [!div class="mx-imgBorder"] 
    > ![Yksi moneen -suhde](./media/data-platform-cds-newrelationship/onetomany-3.png "Yksi moneen -suhde")

## <a name="add-a-many-to-many-relationship"></a>Monta moneen -suhteen lisääminen

Tällä hetkellä Lisäasetukset-valikossa on vain tämä. Valitse PowerApps-kotisivulla vasemmanpuoleisesta valikosta Lisäasetukset. Lisätietoja suhteen luomisesta on kohdassa [N:N-suhteen luominen](/dynamics365/customer-engagement/customize/create-and-edit-nn-many-to-many-relationships)

## <a name="use-a-lookup-field-in-an-app"></a>Hakukentän käyttäminen sovelluksessa
Jos [sovellus luodaan automaattisesti](../canvas-apps/data-platform-create-app.md) entiteetistä, jossa on hakukenttä, se näkyy **avattavan valikon** ohjausobjektina, joka sisältää entiteetin **Ensisijainen nimi** -kentän tiedot.

## <a name="add-1n-and-nn-relationships-for-canvas-apps"></a>Kaaviosovellusten 1:N- ja N:N-suhteiden lisääminen
Linkitä kaksi tietuetta **Liitä**-toiminnolla käyttämällä Common Data Servicen yksi moneen- tai monta yhteen -suhdetta. Lisätietoja: [PowerAppsin Relate- ja Unrelate-toiminnot](../canvas-apps/functions/function-relate-unrelate.md)

## <a name="next-steps"></a>Seuraavat vaiheet
* [Sovelluksen luominen Common Data Service -tietokannan avulla](../canvas-apps/data-platform-create-app.md)
* [Sovelluksen luominen alusta Common Data Service sovelluksille -tietokannan avulla](../canvas-apps/data-platform-create-app-scratch.md)

