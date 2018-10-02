---
title: Asetusjoukon luominen | Microsoft Docs
description: Asetusjoukon luomisen vaiheittaiset ohjeet.
author: clwesene
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: clwesene
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-an-option-set"></a>Asetusjoukon luominen

Asetusjoukkojen avulla voit sisällyttää kiinteiden arvojen avattavat luettelot sovelluksen käyttäjälle ja varmistat tietojen yhteensopivuuden. Näitä kutsutaan joskus valintaluetteloiksi tai valintakentiksi muissa sovelluksissa. Kuten entiteeteissäkin, käytettävissä on vakioasetusjoukkoja ja mukautettuja asetusjoukkoja, joita voi luoda sovelluksessa.

Asetusjoukkoja voidaan luoda kahdella eri tavalla: asetusjoukkoluettelosta portaalissa ja suoraan entiteetissä kentän luomisen yhteydessä. Lisätietoja entiteetin luomisesta on kohdassa [Entiteetin luominen](data-platform-create-entity.md).

## <a name="creating-an-option-set-while-adding-a-field"></a>Asetusjoukon luominen kentän lisäämisen yhteydessä.

1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Entiteetit**-kohtaa vasemmanpuoleisessa siirtymisruudussa.

    ![Entiteetin tiedot](./media/data-platform-cds-create-entity/entitylist.png "Entiteettiluettelo")

2. Napsauta tai napauta olemassa olevaan entiteettiä tai [luo uusi entiteetti](data-platform-create-entity.md)

3. Lisää uusi kenttä entiteettiin valitsemalla **Lisää kenttä**.

4. Anna Uusi kenttä -paneelissa kentän **näyttönimi**. **Nimi** täytetään automaattisesti. Sitä käytetään kentän yksilöllisenä nimenä. **Näyttönimeä** käytetään, kun tämä kenttä esitellään käyttäjille. **Nimeä** käytetään sovelluksen luomisen yhteydessä lausekkeissa ja kaavoissa.

    ![Uusi kenttä](./media/data-platform-cds-create-entity/newfieldpanel.png "Uusi kenttä -paneeli")

5. Valitse avattava **Tietotyyppi**-luettelo ja valitse sitten **Asetusjoukko** tai **Monivalinta-asetusjoukko**.

6. Valitse avattava **Asetusjoukko**-luettelo ja valitse sitten **Uusi asetusjoukko**

    > [!NOTE]
    > Jos entiteetissä voidaan käyttää olemassa olevaa asetusjoukkoa, voit valita sen luettelosta. Uutta asetusjoukkoa ei siis tarvitse luoda.

    ![Asetusjoukkoluettelo](./media/data-platform-cds-newoptionset/fieldpanel-1.png "Asetusjoukkoluettelo")

7. Näyttöön avautuu paneeli, jossa voi luoda asetusjoukon. **Näyttönimi** ja **nimi** saadaan kentän nimestä, mutta arvoja voi muuttaa tarvittaessa. Valitse **Lisää uusi kohde**, kun haluat aloittaa asetusluettelon luomisen. Toista tätä vaihetta, kunnes kaikki kohteet on luotu.

    ![Uusi asetusjoukko](./media/data-platform-cds-newoptionset/field-optionsetpanel.png "Uusi asetusjoukko")

8. Kun olet syöttänyt kohteet, valitse **Tallenna** ja luo asetusjoukko.

    ![Uusi asetusjoukko](./media/data-platform-cds-newoptionset/field-optionsetpanel-values.png "Uusi asetusjoukko")

9. Valitse **Valmis**, kun haluat sulkea kenttäpaneelin. Valitse sitten **Tallenna entiteetti**, kun haluat tallentaa entiteetin Common Data Service -sovellukseen.

    > [!NOTE]
    > Voit valita jonkin kohteista tämän kentän **oletusarvoksi**. Se valitaan oletusarvoksi, kun käyttäjät luovat entiteetille uusia tietueita.

    ![Uusi kenttä](./media/data-platform-cds-newoptionset/fieldpanel-2.png "Uusi kenttä -paneeli")

## <a name="creating-an-option-set-from-the-option-set-list"></a>Asetusjoukon luominen asetusjoukkoluettelosta

1. Laajenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osa ja napsauta tai napauta **Asetusjoukot**-kohtaa vasemmanpuoleisessa siirtymisruudussa.

    ![Asetusjoukot](./media/data-platform-cds-newoptionset/optionsetlist.png "Asetusjoukkoluettelo")

2. Valitse **Uusi asetusjoukko**

3. Uudessa näyttöön avautuvassa paneelissa luodaan asetusjoukko. Anna **näyttönimi** ja **nimi**. Valitse **Lisää uusi kohde**, kun haluat aloittaa asetusluettelon luomisen. Toista tätä vaihetta, kunnes kaikki kohteet on luotu.

    ![Asetusjoukon luominen](./media/data-platform-cds-newoptionset/optionset-create.png "Asetusjoukon luominen")

4. Kun olet syöttänyt kohteet, valitse **Tallenna** ja luo asetusjoukko.

    ![Uusi asetusjoukko](./media/data-platform-cds-newoptionset/optionset-create-values.png "Uusi asetusjoukko")

5. Nyt voit käyttää tätä asetusjoukkoa luomalla entiteetille uuden kentän.

## <a name="global-and-local-option-sets"></a>Yleiset ja paikalliset asetusjoukot

Oletusarvoisesti asetusjoukot luodaan yleisinä asetusjoukkoina, joita voidaan käyttää uudelleen useissa entiteeteissä. Voit valita **Näytä lisää** -asetuksen uuden asetusjoukon luomisen yhteydessä, kun haluat tehdä asetusjoukosta **paikallisen**. Tämä asetus on käytettävissä vain, kun asetusjoukkoa luodaan kentän lisäämisen yhteydessä. Se ei ole käytettävissä asetusjoukkoluettelon kautta. Paikallisia asetusjoukkoja voi käyttää vain entiteetissä ja kentässä, joille ne on tehty. Niitä ei voi käyttää uudelleen muissa entiteeteissä. Tätä tapaa suositellaan vain edistyneille käyttäjille, jotka tarvitsevat paikallista asetusjoukkoa.

> [!IMPORTANT]
> Asetusjoukon paikalliseksi tai yleiseksi määritystä ei voi muuttaa.
