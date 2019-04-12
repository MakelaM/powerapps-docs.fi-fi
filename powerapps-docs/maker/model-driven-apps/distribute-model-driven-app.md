---
title: Mallipohjaisen sovelluksen jakelu ratkaisun avulla | MicrosoftDocs
description: Tietoja mallipohjaisen sovelluksen jakelusta ratkaisujen avulla
keywords: ''
ms.date: 08/06/2018
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.assetid: e82e7f64-37ad-41e5-acd7-16309881c6a2
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 9
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="distribute-a-model-driven-app-using-a-solution"></a>Mallipohjaisen sovelluksen jakelu ratkaisun avulla

Mallin perustuvat sovellukset jaetaan ratkaisun osana. Kun mallipohjainen sovellus on luotu, voit tehdä sen käytettäväksi muissa ympäristöissä pakkaamalla sovelluksen ratkaisuksi ja viemällä sen zip-tiedostoksi. Kun ratkaisu (.zip-tiedosto) on tuotu kohdeympäristöön, pakattu sovellus on käytettävissä. 
  
## <a name="add-an-app-to-a-solution"></a>Sovelluksen lisääminen ratkaisuun
Luo ratkaisu, jotta voit jakaa sovelluksen. Tällöin sovellus voidaan pakata vientiä varten.

1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.

2. Valitse **Ratkaisut** ja valitse sitten **Uusi ratkaisu**.
3. Tee kentät valmiiksi **Uusi ratkaisu** -sivulla ja valitse **Tallenna**. Lisätietoja: [Ratkaisun luominen](../common-data-service/create-solution.md)
4. **Ratkaisu**-sivu tulee näkyviin. Valitse **Lisää aiemmin luotu** ja valitse sitten **Sovellus**. Valitse ratkaisuun lisättävä ratkaisu ja valitse sitten **OK**. 

    ![Valitse ratkaisun osat](media/select-solution-components.png)

5. Jos **Pakollisia osia puuttuu** -sivu tulee näyttöön, on suositeltavaa valita **Kyllä, lisää pakolliset osat**, kun lisäät sovelluksen osana olevat tarpeelliset osat, kuten entiteetit, näkymät, lomakkeet, kaaviot ja sivustokartan. Valitse **OK**.
6. Valitse **Ratkaisu**--sivulla **Tallenna ja sulje**.

## <a name="export-a-solution"></a>Ratkaisun vieminen
Voit jakaa sovelluksen niin, että se voidaan tuoda toiseen ympäristöön tai ottaa käyttöön [Microsoft AppSourcessa](https://appsource.microsoft.com/), kun vietä ratkaisun zip-tiedostoon. Tällöin zip-tiedosto, joka sisältää sovelluksen ja osat, voidaan tuoda toisiin ympäristöihin.

1. Avaa [Ratkaisut-sivu](advanced-navigation.md#solutions). 
2. Valitse vietävä ratkaisu ja valitse sitten työkalurivillä **Vie**. 
3. Valitse **Julkaise mukautukset** -sivulla **Seuraava**.
4. Jos **Pakollisia osia puuttuu** -sivu tulee näkyviin, valitse **Seuraava**. 
5. Valitse **Vie järjestelmäasetukset** -sivulla sisällytettävät valinnaiset ominaisuudet ja valitse sitten **Seuraava**. 
6. Valitse **Paketin tyyppi** -sivulla **Hallitsematon** tai **Hallittu** ja valitse sitten **Vie**. Lisätietoja ratkaisupaketin tyypeistä on kohdassa [Ratkaisun yleiskatsaus](../common-data-service/solutions-overview.md).
7. Selaimesta ja asetuksista riippuen .zip-pakettitiedoto luodaan ja kopioidaan latausten oletuskansioon. Paketin tiedostonimi perustuu ratkaisun yksilölliseen nimeen, johon liitetään alaviivat ja ratkaisun versionumero.

    > [!NOTE]
    > Kun viet sovelluksen ratkaisun avulla, sovelluksen URL-osoitetta ei viedä.
  
## <a name="import-a-solution"></a>Ratkaisun tuominen  
Kun saat ratkaisun zip-tiedoston, joka sisältää sovelluksen, jonka haluat tuoda, avaa Ratkaisujen osat -sivu ja tuo ratkaisu. Kun ratkaisu on tuotu onnistuneesti, sovellus on käytettävissä ympäristössä.

1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.

2. Valitse **Ratkaisut** ja valitse työkaluriviltä **Tuo**.
3. Etsi tuotava tiedosto selaamalla ja valitse **Seuraava**.
4. Valitse **Tuo**.

## <a name="see-also"></a>Katso myös
[Ratkaisujulkaisijan etuliitteen muuttaminen](../common-data-service/change-solution-publisher-prefix.md)
