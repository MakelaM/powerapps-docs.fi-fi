---
title: Pikaopas entiteettien suhteisiin hakukentän kautta | Microsoft Docs
description: Pikaopas suhteen luomiseen entiteettien välille käyttämällä hakukenttää
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: cds
ms.date: 3/21/2018
ms.author: clwesene
ms.openlocfilehash: a607058d1e26f37a4bffa054d9dc148be8b6b011
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="quickstart-create-a-relationship"></a>Pikaopas: Luo suhde
Yhden entiteetin tiedot liittyvät usein toiseen entiteettiin. Käytössäsi voi olla esimerkiksi **opettajien** entiteetti ja **luokan** entiteetti. **Luokan** entiteetissä saattaa olla hakusuhde **opettajien** entiteettiin näyttämään, kuka opettaja opettaa luokkaa. Voit käyttää hakukenttää näyttämään tietoja **opettajien** entiteetistä. Tätä kutsutaan yleisesti hakukentäksi.

## <a name="define-a-relationship"></a>Määritä suhde
Voit luoda erityyppisiä suhteita yhdestä entiteetistä toiseen (tai entiteetin ja itsensä välille). Jokaisella entiteetillä voi olla suhde yhteen tai useampaan entiteettiin ja useampia suhteita toiseen entiteettiin. Yleisiä suhdetyyppejä ovat:


* **Monesta yhteen** – Tässä suhdetyypissä jokainen tietue entiteetissä A voi vastata useampaa kuin yhtä tietuetta entiteetissä B, mutta jokainen tietue entiteetissä B voi vastata vain yhtä tietuetta entiteetissä A. Esimerkiksi luokalla on yksi luokkahuone. Tämä on yleisin suhdetyyppi, ja se näkyy kenttäluettelossa nimellä **hakukenttä**
* **Yhdestä moneen** – Tässä suhdetyypissä jokainen tietue entiteetissä B voi vastata useampaa kuin yhtä tietuetta entiteetissä A, mutta jokainen tietue entiteetissä A voi vastata vain yhtä tietuetta entiteetissä B. Esimerkiksi yksi opettaja opettaa montaa luokkaa.
* **Monta-moneen** – Tässä suhdetyypissä jokainen tietue entiteetissä A voi vastata useampaa kuin yhtä tietuetta entiteetissä B ja päin vastoin. Esimerkiksi opiskelijat voivat osallistua useille luokille ja kullakin luokalla voi olla useita opiskelijoita.

## <a name="add-a-lookup-field-many-to-one-relationship"></a>Hakukentän lisääminen (monta yhteen -suhde)

Lisää hakusuhde entiteettiin luomalla suhde **Suhteet**-välilehdessä ja määrittämällä entiteetti, jonka kanssa haluat luoda suhteen.

1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

    ![Entiteetin tiedot] ja (./media/data-platform-cds-create-entity/entitylist.png "entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaa entiteettiä tai [Luo uusi entiteetti](data-platform-create-entity.md)

3. Napsauta kohtaa **Suhteet**

4. Napsauta **Lisää suhde**. Tämä avaa uuden paneelin, jossa voit valita entiteetin, johon haluat luoda suhteen. Valitse entiteetti avattavasta **Liittyvä entiteetti** valikosta.

    ![Monta yhteen -suhde](./media/data-platform-cds-newrelationship/manytoone-1.png "Monta yhteen -suhde")

5. Kun olet valinnut entiteetin, hakukentät näytetään ensisijaisen entiteetin kohdalla. Niillä on oletusarvoisesti entiteetin nimi (tässä esimerkissä luokkahuone), mutta voit muuttaa niitä tarvittaessa.

    ![Monta yhteen -suhde](./media/data-platform-cds-newrelationship/manytoone-2.png "Monta yhteen -suhde")

6. Valitse **Valmis** lisätäksesi suhteen entiteettiisi ja napsauta sitten **Tallenna entiteetti**.

    ![Monta yhteen -suhde](./media/data-platform-cds-newrelationship/manytoone-3.png "Monta yhteen -suhde")

## <a name="add-a-one-to-many-relationship"></a>Lisää yksi moneen -suhde

Lisää yksi moneen -suhde luomalla suhde **Suhteet**-välilehdessä ja määrittämällä entiteetti, jonka kanssa haluat muodostaa suhteen.

1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

    ![Entiteetin tiedot] ja (./media/data-platform-cds-create-entity/entitylist.png "entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaa entiteettiä tai [Luo uusi entiteetti](data-platform-create-entity.md)

3. Napsauta kohtaa **Suhteet**

4. Napsauta alanuolta, joka sijaitsee kohdan **Lisää suhde** oikealla puolella. Tämä antaa sinulle mahdollisuuden valita molempien suhdetyyppien välillä. Napsauta **yksi moneen**. Tämä avaa uuden paneelin, jossa voit valita entiteetin, johon haluat luoda suhteen. Valitse entiteetti avattavasta **Liittyvä entiteetti** valikosta.

    ![Yksi moneen -suhde](./media/data-platform-cds-newrelationship/onetomany-1.png "Yksi moneen -suhde")

5. Kun olet valinnut entiteetin, hakukentät näytetään ensisijaisen entiteetin kohdalla. Niillä on oletusarvoisesti entiteetin nimi (tässä esimerkissä luokka), mutta voit muuttaa niitä tarvittaessa.

    > [!NOTE]
    > Jos kyseessä yksi-moneen -suhteet, hakukenttä luodaan liittyvään entiteettiin, ei siihen entiteettiin, joka on parhaillaan valittuna. Jos tarvitset hakukentän nykyiseen entiteettiin, luo monta-yhteen-suhde.

    ![Yksi moneen -suhde](./media/data-platform-cds-newrelationship/onetomany-2.png "Yksi moneen -suhde")

6. Valitse **Valmis** lisätäksesi suhteen entiteettiisi ja napsauta sitten **Tallenna entiteetti**.

    ![Yksi moneen -suhde](./media/data-platform-cds-newrelationship/onetomany-3.png "Yksi moneen -suhde")

## <a name="add-a-many-to-many-relationship"></a>Lisää monta moneen -suhde

Tällä hetkellä tämän vaihtoehto on käytettävissä vain Lisäasetukset-valikon kautta. Napsauta PowerAppsin kotisivulla vasemmanpuoleisessa valikossa ”Lisäasetukset”. Lisätietoja siitä suhteen luomisesta on kohdassa [Luo N:N-suhteet](/dynamics365/customer-engagement/customize/create-and-edit-nn-many-to-many-relationships)

## <a name="use-a-lookup-field-in-an-app"></a>Hakukentän käyttäminen sovelluksessa
Jos [luot sovelluksen automaattisesti](../canvas-apps/data-platform-create-app.md) hakukentän sisältävästä entiteetistä, se näkyy **Avattava luettelo** -ohjausobjektina, joka sisältää tietoja entiteetin **Ensisijainen nimi**kentästä.

## <a name="next-steps"></a>Seuraavat vaiheet
* [Sovelluksen luominen käyttämällä Common Data Service -tietokantaa](../canvas-apps/data-platform-create-app.md)
* [Sovelluksen luominen alusta alkaen käyttämällä Common Data Service -tietokantaa](../canvas-apps/data-platform-create-app-scratch.md)

