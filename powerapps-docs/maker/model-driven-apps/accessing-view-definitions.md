---
title: Mallipohjaisen sovelluksen näkymämäärityksen käyttäminen | MicrosoftDocs
description: Tässä ohjeaiheessa on tietoja entiteettinäkymien käyttämisestä
ms.custom: ''
ms.date: 06/12/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Mattp123
ms.assetid: 034c8bef-0d1c-4ef9-8da7-f81343c4553a
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="access-a-model-driven-app-view-definition-in-powerapps"></a>Mallipohjaisen sovelluksen näkymämäärityksen käyttäminen PowerAppsissa

 Tässä ohjeaiheessa avataan näkymämääritys ja näytetään ominaisuudet ja asetuksen näkymän määrittämistä varten. Näkymämäärityksiä voi käyttää eri tavoilla PowerAppsissa. 
  
  
## <a name="open-a-view-in-powerapps"></a>Näkymän avaaminen PowerAppsissa

1.  Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

    ![Mallipohjainen suunnittelutila](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten **Asiakas**-entiteetti.   
3. Valitse **Näkymät**-välilehti ja valitse sitten **Poista suodatin**.

    > [!div class="mx-imgBorder"] 
    > ![Asiakasnäkymän määritykset](media/account-view-definitions.png)

4. Valitse avattava näkymä, esimerkiksi asiakasentiteetin **Kaikki asiakkaat** -näkymä.

    > [!div class="mx-imgBorder"] 
    > ![Kaikki asiakkaat -näkymä](media/all-accounts-view.png)

5. Näkymäeditorissa voi suorittaa esimerkiksi seuraavia tehtäviä: 
 
- [Näkymän tietueiden lajittelu](configure-sorting.md)
- [Näkymien sarakkeiden valitseminen ja määrittäminen](choose-and-configure-columns.md)
- [Mukautettujen ohjausobjektien käyttö tietojen visualisointiin](use-custom-controls-data-visualizations.md) 

## <a name="open-a-view-from-an-app"></a>Näkymän avaaminen sovelluksessa

Missä tahansa entiteetin luettelonäkymässä, komentopalkista löydät seuraavat komennot, kun valitset painikkeen, jossa on kolme pistettä (...):  
- **Näytä**: oletusratkaisussa avautuu nykyisen näkymän määritykset.  
  
- **Uusi järjestelmänäkymä**: Avaa uuden ikkunan uuden näkymän nykyiselle entiteetille oletusratkaisussa.  
  
- **Mukauta entiteettiä**: Voit siirtyä oletusratkaisussa nykyisen entiteetin määritykseen, jossa voit sitten valita **näkymät**.  
  
- **Järjestelmänäkymät**: avaa saman ikkunan kuin **entiteetin mukauttaminen**, paitsi kun**näkymät** on valittu.  

## <a name="open-a-view-in-solution-explorer"></a>Näkymän avaaminen ratkaisunhallinnassa 
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Laajenna **Osat**-kohdasta **Entiteetit** ja laajenna sitten haluamasi entiteetti.  
  
3.  Valitse **Näkymät**.  
  
4.  Kaksoisnapsauta avattavaa näkymää.  
  
 Tässä luettelonäkymissä on neljä suodatinta, joiden avulla voit etsiä haluamasi näkymät helpommin:  
  
    - **Kaikki aktiiviset näkymät**  
  
    - **Aktiiviset julkiset näkymät**  
  
    - **Passiiviset julkiset näkymät**  
  
    - **Aktiiviset järjestelmänäkymät**  
  
 Jos entiteetti, johon näkymä liittyy, on osa hallitsematonta ratkaisua, voit edelleen luoda tai muokata näkymiä kyseiselle entiteetille oletuarvoisessa ratkaisussa. Järjestelmänäkymät liittyvät entiteettiin, eivätkä ne ole käytettävissä erillisen ratkaisun osia. Toisin kuin kentät, näkymät eivät käytä mukautuksen etuliitettä yksilöivässä nimessä, jonka tulisi olla yhdenmukainen ratkaisussa, joten sinun ei tarvitse luoda näkymiä ratkaisun yhteydessä. 
 
## <a name="next-steps"></a>Seuraavat vaiheet
[Tietoja näkymistä](create-edit-views.md)


