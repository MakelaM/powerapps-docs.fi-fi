---
title: Raportin luominen ohjatulla raportin luonti toiminnolla | Microsoft Docs
description: Luo raportti ohjatulla raportin luonti toiminnolla Powerappsissa
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
ms.openlocfilehash: 0f953c44d81742baca39058cd68180ca63833eb6
ms.sourcegitcommit: e9671e018c1ee4b640528915350a367758991b6a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/27/2019
ms.locfileid: "67420279"
---
# <a name="create-a-report-using-the-report-wizard"></a>Raportin luominen Raportin ohjatun toiminnon avulla


Ohjatulla raportin luomisella voit luoda raportteja, joissa on kaavioita ja taulu koita, joiden avulla voit helposti analysoida tietojasi. 

Kaikki raportit, jotka on luotu ohjatulla raportin luomis toiminnolla, ovat Fetch-pohjaisia raportteja. Ota huomioon, että kaikki ohjatulla raportin luonti toiminnolla luodut raportit tulostetaan vaaka suunnassa.

## <a name="create-a-new-report"></a>Luo uusi raportti

1. Valitse vasemmassa siirtymis ruudussa raportit-alue.  
2. Valitse komento palkissa **Uusi**.

    > [!div class="mx-imgBorder"]
    > ![Luo uusi raportti](media/newreport.png "Luo uusi raportti")
  
3. **Raportti: uusi raportti** -näyttö tulee näkyviin. Jätä raportti **tyypille** oletus valinta-, **Ohjattu raportin luominen-raportti** ja valitse **Ohjattu raportin luominen** -painike. 

    > [!div class="mx-imgBorder"]
    > ![Ohjattu raportin luominen](media/report_wizard.png "Ohjattu raportin luominen-näyttö")
  
4. Jätä seuraavassa näytössä oletus valinnat ja valitse sitten **Seuraava**.
 
    > [!div class="mx-imgBorder"]
    > ![Ohjattu raportin luominen](media/report_wizard_1.png "Ohjattu raportin luominen-näyttö")
   
4. Kirjoita raportin **Ominaisuudet** -näyttöön raportin nimi ja valitse sitten raporttiin sisällytettävä tietue ja valitse sitten **Seuraava**.
 
    > [!div class="mx-imgBorder"]
    > ![Raportin ominaisuudet-näyttö](media/report_wizard_2.png "Raportin ominaisuudet-näyttö")
  
5.  Valitse raportti-näytössä **sisällytettävien tietueiden Valitse** suodattimet määrittääksesi, mitkä tietueet sisällytetään raporttiin. Jos haluat esimerkiksi vain tarkastella tuloksia tietueille, jotka on muokattu viimeisten 60 päivän aikana, voit määrittää tämän suodattimen tässä näytössä. Jos et halua suodattaa tietoja, valitse **Tyhjennä**.

    > [!div class="mx-imgBorder"]
    > ![Valitse raporttiin sisällytettävät tietueet *](media/report_wizard_3.png "Valitse raporttiin sisällytettävät tietueet")
  
6. Valitse **Asettele kentät** -näytössä raportin asettelu. Valitse **napsauttamalla tätä voit lisätä ryhmittelyn** ja valita, miten haluat ryhmitellä tiedot.

    > [!div class="mx-imgBorder"]
    > ![Asettele kentät](media/report_wizard_4.png "Asettele kentät")

7. Valitse **tietue tyyppi** ja **sarake** tiedoille, jotka haluat ryhmitellä raporttiin. Kun olet tehnyt haluamasi valinnat, valitse **OK**.

    > [!div class="mx-imgBorder"]
    > ![DD-ryhmittely näyttö](media/report_wizard_5.png "Lisää ryhmittely näyttö")
  
8. Valitse **napsauttamalla tätä voit lisätä sarakkeen** edellisessä vaiheessa valitsemaasi tietue tyyppiin liittyvien tietojen sarakkeisiin.  

    > [!div class="mx-imgBorder"]
    > ![Lisää ryhmittely näyttö](media/report_wizard_6.png "Lisää ryhmittely näyttö")

9. Valitse **Lisää sarake** -näytössä tiedot, jotka haluat näyttää sarakkeelle, ja valitse sitten **OK**. 

    > [!div class="mx-imgBorder"]
    > ![Lisää sarake-näyttö](media/report_wizard_7.png "Lisää sarake-näyttö")
  
10. Toista edellinen vaihe kaikille lisä sarakkeille, jotka haluat lisätä. Kun olet tehnyt niin, **Aseta kentät** -näytössä Slect **Next**.
 
    > [!div class="mx-imgBorder"]
    > ![Lisää Lisää sarake-näyttö](media/report_wizard_8.png "Lisää Lisää sarake-näyttö")
  
11. Valitse **Muotoile raporttia** -näytössä, miten voit muotoilla raporttiasi, ja valitse sitten **Seuraava**.
 
    > [!div class="mx-imgBorder"]
    > ![Muotoile raportti](media/report_wizard_9.png "Muotoile raportti näyttöä")

12. Tarkista raportin yhteenveto ja valitse **Seuraava** ja valitse sitten **valmis**. Voit nyt tarkastella tätä raporttia järjestelmän raportti luettelon avulla.

    > [!div class="mx-imgBorder"]
    > ![Tarkastele raporttiasi](media/report_wizard_10.png "Tarkastele raporttiasi")

### <a name="see-also"></a>Katso myös
[Raporttien käsitteleminen](work-with-reports.md) 

[Lisää olemassa oleva raportti](add-existing-report.md)

[Muokkaa raportti suodatinta](edit-report-filter.md)

[Sellaisten tietojen vian määritys, joita ei näytetä raportissa](troubleshoot-reports.md)


