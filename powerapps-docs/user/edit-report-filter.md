---
title: Raportin oletus suodattimen muokkaaminen | Microsoft Docs
description: Raportin oletussuodattimen muokkaaminen
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 06/27/2019
ms.author: mkaur
ms.custom: ''
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 53e4f2fc61bb72b4c3fc6fed188b513641c2034d
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420210"
---
# <a name="edit-the-default-filter-of-a-report"></a>Raportin oletussuodattimen muokkaaminen

Kun raportti on SQL Server Reporting Services raportti, se on otettu käyttöön esisuodattamiseen ja sillä on oletus suodatin, voit muuttaa oletus suodatinta näyttämään raportissa näytettävät tiedot. Tätä suodatinta käytetään aina, kun käyttäjä suorittaa raportin.

1. Valitse vasemmasta siirtymis ruudusta raportti alue
2. Valitse raportti ja valitse sitten commbar-palkki **Muokkaa oletus suodatinta**.

     > [!div class="mx-imgBorder"]
     > ![Muokkaa oletus raportti suodatinta](media/edit_filter.png "Muokkaa oletus raportti suodatinta")
  
3. Muokkaa suodatus ehtoja.  
  
   Ehdot on ryhmitelty tietue tyyppien mukaan, joita voit käyttää suodattimessa, kuten **Asiakkaat** tai **yhteys henkilöt**.  
  
   ### <a name="to-edit-an-existing-row"></a>Olemassa olevan rivin muokkaaminen
   1. Valitse kyselyn vertailu operaattori ja valitse operaattori tai valitse alleviivattu arvo ja anna uusi arvo.  
  
   2. Valitse kyselyn vertailu operaattori ja valitse operaattori.  
  
   Ehto rivin lisääminen:  

   1.  Valitse **Valitse**ja Määritä kenttä, johon suodatetaan.  

   2.  Valitse kyselyn vertailu operaattori ja valitse operaattori.  

   3.  Valitse **Anna arvo**ja anna arvo, jota suodatetaan. Joidenkin arvojen osalta voit valita **Valitse tai muuta tämän kentän arvot** -painikkeen kolmen pisteen painikkeen ellipsi ![](media/ellipsis-button.png "painike, jolloin") **Valitse arvot** -valinta ikkuna avautuu ja valitse haluamasi arvo.  

   ### <a name="to-group-criteria"></a>Ehtojen ryhmittely
   Sinun täytyy valita vähintään kaksi riviä samalle tietue tyypille. Rivejä, joilla on kenttien arvoja eri tietue tyypeistä, kuten **asiakkuus** -ja **yhteyshenkilö** tietue tyypeistä, ei kuitenkaan voi ryhmitellä.  

   1.  Valitse jokaiselle riville, jonka haluat ryhmitellä, yksityiskohtaisessa tilassa kyseisen rivin **Asetukset-valikko** painike ja valitse sitten **Valitse rivi**.  

   2.  Valitse suodatin-työkalu riviltä **ryhmä ja** tai **Ryhmä tai**.  

   3.  Jos haluat poistaa rivin ryhmästä, valitse kyseisen rivin **Asetukset-valikko** painike ja valitse sitten **Poista**.  

   4.  Jos haluat valita ryhmän, valitse kyseisen ryhmän **Asetukset-valikko** painike ja valitse sitten **Valitse ryhmä**.  

   5.  Jos haluat lisätä ehto-lauseen ryhmään, valitse kyseisen ryhmän **Asetukset-valikko** painike, valitse **Lisää lause**ja valitse sitten kenttä, kyselyn vertailu operaattori ja arvo.  

   6.  Jos haluat poistaa aiemmin valitun ryhmän valinnan, valitse kyseisen ryhmän **Asetukset-valikko** painike ja valitse sitten **Poista ryhmän valinta**.  

   7.  Jos haluat purkaa ryhmän ryhmittelyn, valitse kyseisen ryhmän **Asetukset-valikko** painike ja valitse sitten **Pura ryhmittely**.  

   8.  Jos haluat vaihtaa  ryhmän **tai** ryhmän ryhmään tai ryhmään tai ryhmään tai ryhmään ryhmään **tai** ryhmään, valitse **Asetukset-valikko** painike kyseiseen ryhmään ja valitse  sitten **muuta kohteeseen tai** tai **muuta kohteeseen ja**.  

   > [!TIP]
   > - Jos haluat tyhjentää kaikki ehdot ja aloittaa alusta, valitse suodatin-työkalu riviltä **Tyhjennä**ja valitse sitten **Vahvista**.  
   > - Jos haluat poistaa rivin, valitse kyseisen rivin **Asetukset-valikko** painike ja valitse sitten **Poista**.  
  
4. Kun olet tehnyt tämän, valitse **Tallenna oletus suodatin**.



### <a name="see-also"></a>Katso myös
[Raporttien käsitteleminen](work-with-reports.md) 

[Luo raportti ohjatulla raportin luonti toiminnolla](create-report-with-wizard.md)

[Lisää olemassa oleva raportti](add-existing-report.md)

[Sellaisten tietojen vian määritys, joita ei näytetä raportissa](troubleshoot-reports.md)

