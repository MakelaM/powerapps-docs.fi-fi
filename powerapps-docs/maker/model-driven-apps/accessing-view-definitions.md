---
title: Mallipohjaisen sovelluksen näkymämäärityksen käyttäminen | MicrosoftDocs
description: Tässä ohjeaiheessa on tietoja entiteettinäkymien käyttämisestä
ms.custom: ''
ms.date: 11/27/2018
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
  
  
## <a name="open-a-view-for-editing-in-the-latest-view-designer"></a>Näkymän avaaminen muokkausta varten uusimmassa näkymän suunnitteluohjelmassa

> [!IMPORTANT]
> Näkymän suunnitteluohjelman uusin versio on tällä hetkellä esiversiotilassa. Joitakin toimintoja, kuten tarkennettua suodatusta, mukautettuja ohjausobjekteja ja sarakkeen ominaisuuksia, ei vielä tueta. Jos haluat suorittaa näitä tehtäviä, [avaa perinteisen näkymän suunnitteluohjelma](#open-a-view-in-solution-explorer).

1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  


    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti, esimerkiksi **Asiakas**-entiteetti.   
3. Valitse **Näkymät**-välilehti.

    > [!div class="mx-imgBorder"] 
    > ![Asiakasnäkymän määritykset](media/account-view-definitions.png)

4. Valitse avattava näkymä, esimerkiksi asiakasentiteetin **Kaikki asiakkaat** -näkymä.

    > [!div class="mx-imgBorder"] 
    > ![Kaikki asiakkaat -näkymä](media/account-view-designer.png)

5. Näkymäeditorissa voi suorittaa esimerkiksi seuraavia tehtäviä: 
 
- [Näkymän tietueiden lajittelu](configure-sorting.md)
- [Näkymien sarakkeiden valitseminen ja määrittäminen](choose-and-configure-columns.md)

## <a name="open-a-view-for-editing-from-a-legacy-web-app"></a>Näkymän avaaminen muokkausta varten vanhasta verkkosovelluksesta
Minkä tahansa vanhan verkkosovelluksen entiteetin luettelonäkymän komentopalkissa ovat seuraavat komennot, kun valitset painikkeen, jossa on kolme pistettä (...):  

- **Näytä**: oletusratkaisussa avautuu nykyisen näkymän määritykset.  
  
- **Uusi järjestelmänäkymä**: Avaa uuden ikkunan uuden näkymän nykyiselle entiteetille oletusratkaisussa.  
  
- **Mukauta entiteettiä**: Voit siirtyä oletusratkaisussa nykyisen entiteetin määritykseen, jossa voit sitten valita **näkymät**.  
  
- **Järjestelmänäkymät**: avaa saman ikkunan kuin **entiteetin mukauttaminen**, paitsi kun**näkymät** on valittu.  

   ![Näkymän editorin avaaminen vanhasta verkkosovelluksesta](media/open-view-editor-from-view.png)

## <a name="open-a-view-for-editing-in-solution-explorer"></a>Näkymän avaaminen muokkausta varten ratkaisunhallinnassa 
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).  
  
2.  Laajenna **Osat**-kohdasta **Entiteetit** ja laajenna sitten haluamasi entiteetti.  
  
3.  Valitse **Näkymät**.  
  
4.  Kaksoisnapsauta avattavaa näkymää. Tämä avaa perinteisen näkymän suunnitteluohjelman.
    
    > [!div class="mx-imgBorder"] 
    > ![Kaikki asiakkaat -näkymä](media/all-accounts-view.png)

 Tässä luettelonäkymissä on neljä suodatinta, joiden avulla voit etsiä haluamasi näkymät helpommin:  
  
- **Kaikki aktiiviset näkymät**  

- **Aktiiviset julkiset näkymät**  

- **Passiiviset julkiset näkymät**  

- **Aktiiviset järjestelmänäkymät**  
  
 Jos entiteetti, johon näkymä liittyy, on osa hallitsematonta ratkaisua, voit edelleen luoda tai muokata näkymiä kyseiselle entiteetille oletuarvoisessa ratkaisussa. Järjestelmänäkymät liittyvät entiteettiin, eivätkä ne ole käytettävissä erillisen ratkaisun osia. Toisin kuin kentät, näkymät eivät käytä mukautuksen etuliitettä yksilöivässä nimessä, jonka tulisi olla yhdenmukainen ratkaisussa, joten sinun ei tarvitse luoda näkymiä ratkaisun yhteydessä. 
 
## <a name="next-steps"></a>Seuraavat vaiheet
[Tietoja näkymistä](create-edit-views.md)


