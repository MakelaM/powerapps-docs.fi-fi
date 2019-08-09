---
title: Tapaamisen, sähköpostin, puhelun, huomautuksen tai tehtävän lisääminen aikajanaan mallipohjaisessa sovelluksessa | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 8/02/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 8f061078b4401ee1ea2db9a2e7e6a4443bd053b6
ms.sourcegitcommit: 4e4f7945c3f24faf9bb8a856a5f3892cbfd113be
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/05/2019
ms.locfileid: "68783770"
---
# <a name="add-an-appointment-email-phone-call-note-or-task-activity-to-the-timeline"></a>Tapaamisen, sähköpostin, puhelun, huomautuksen tai tehtävän lisääminen aikajanaan 

[!INCLUDE [cc-beta-prerelease-disclaimer](../includes/cc-beta-prerelease-disclaimer.md)]

Lisää **Aktiviteetit** **Aikajana**-seinälle seurataksesi viestintää asiakkaan tai yhteyshenkilön kanssa. Voit esimerkiksi tehdä muistiinpanoja, lisätä julkaisuja ja tehtäviä, lähettää sähköpostiviestejä, lisätä puhelutietoja tai määrittää tapaamisia. Järjestelmä lisää aikaleiman automaattisesti jokaiseen aktiviteettiin ja näyttää, kuka sen on luonut. Sinä ja muut ryhmäsi jäsenet voitte selata aktiviteetteja ja tarkastella historiaa työskentelyn aikana asiakkaan kanssa. 

- Tietueesta lisätyt aktiviteetit näkyvät tietueen **Aikajana**-seinällä. 
- Jos aktiviteetin **Liittyy**-kenttä on määritetty, aktiviteetti näkyy siinä tietueessa, johon se on liitetty. 
- Voit myös suodattaa aktiviteetit tietuetyypin ja päivämäärän mukaan valitsemalla suodatusruudun. 
- Kun uusi tehtävä luodaan, saat **Huomaamatta jääneet** -ilmoituksen **Aikajana**-seinälle.
- Sähkö posti viesti, jossa on liitetty kuva, näytetään Sähkö posti viestin leipä tekstin sisällä.

  > [!div class="mx-imgBorder"]
  > ![Aktiviteettien aikajananäkymä PowerAppsissa](media/TimelineViewOfActivity.png "Aktiviteettien aikajananäkymä PowerAppsissa")  
 
## <a name="add-an-activity-from-the-nav-bar"></a>Toiminnon lisääminen siirtymispalkista
 
Nopein tapa lisätä aktiviteetti on käyttää siirtymispalkissa olevaa pikakuvaketta ja sitten linkittää se tietueeseen. Voit esimerkiksi luoda puheluaktiviteetin ja sitten linkittää sen järjestelmässä olevaan yhteyshenkilöön käyttämällä **Liittyy**-kenttää.

1. Valitse siirtymispalkissa **plusmerkki** ![Luo tietue -painike](media/create-record-button.png "Luo tietue -painike") ja valitse sitten **Aktiviteetit**. 

   > [!div class="mx-imgBorder"]
   > ![Pikakuvake aktiviteetin lisäämiseen PowerAppsissa](media/QuickCreate.png "Pikakuvake aktiviteetin lisäämiseen PowerAppsissa")  
 
2. Valitse lisättävän aktiviteetin tyyppi.

3. Lisää tarvittavat tiedot. Liitä aktiviteetti tietueeseen **Liittyy**-kenttää käyttämällä.

4. Kun olet valmis, valitse **Tallenna**.

 
## <a name="add-a-phone-call"></a>Puhelun lisääminen  
  
1. Avaa tietue, johon haluat lisätä aktiviteetin. Esimerkiksi yhteystietotietue.
  
2. Valitse **Aikajana**-seinällä **plusmerkki** > **Puhelu**. 


   > [!div class="mx-imgBorder"]
   > ![Puheluaktiviteetin lisääminen PowerAppsissa](media/addphonecall.png "Puheluaktiviteetin lisääminen PowerAppsissa")
  
3. Määritä puhelun **aihe**.

     Anna **Huomautukset**-alueella yhteenveto keskustelusta asiakkaan kanssa. 
  
     **Puhelun kohde** -kenttä täytetään automaattisesti tietueella, johon lisäsit puheluaktiviteetin. Voit tarvittaessa valita eri tietueen.  
  
4. Oletusarvon mukaan suunnaksi on määritetty **Lähtevä**. Voit muuttaa sen arvoon **Saapuva** valitsemalla **Lähtevä**. 
  
5. Kun olet täyttänyt lomakkeen, tallenna aktiviteetti valitsemalla **Tallenna**.  
  
## <a name="add-a-task"></a>Tehtävän lisääminen  
  
1. Avaa tietue, johon haluat lisätä aktiviteetin. Esimerkiksi yhteystietotietue.
  
2. Valitse **Aikajana**-seinällä **plusmerkki** > **Tehtävä**.
  
3. **Omistaja**-kentän arvoksi määritetään oletusarvoisesti nykyinen käyttäjä. Jos haluat määrittää tehtävän uudelleen, valitse hakukuvake ja valitse sitten toinen käyttäjä tai ryhmä.  
  
4. Kun olet täyttänyt lomakkeen, tallenna aktiviteetti valitsemalla **Tallenna**. 
  
## <a name="add-an-email"></a>Sähköpostin lisääminen  

Jos haluat lisätä tietueeseen sähköpostiaktiviteetin, sinun on ensin tallennettava tietue, johon aktiviteetti lisätään.  
  
1. Avaa tietue, johon haluat lisätä aktiviteetin. Esimerkiksi yhteystietotietue.
  
2. Valitse **Aikajana**-seinällä **plusmerkki** > **Sähköposti**. 

3. Lisää sähköpostiviestin aihe ja kirjoita sähköpostiviesti määritettyyn tilaan.
  
4. Jos haluat lisätä sähköpostiviestiin liitteen, tallenna sähköpostiviesti. Valitse sitten **Liitteet**-osassa **+** vaihtoehto liitteen lisäämiseen.  
  
5. Jos haluat käyttää mallia sähköpostiviestin leipätekstissä, valitse komentopalkissa **Lisää malli** ja valitse sitten malli.   
  
6. Kun olet täyttänyt lomakkeen,valitse **Lähetä**. 


    > [!NOTE]
    > Jos haluat luetella keskustelu näkymässä olevat Sähkö posti viestit, siirry kohtaan **Asetukset** > **mukautus asetukset** > **Sähkö posti** -väli lehti ja valitse sitten **Näytä Sähkö posti keskusteluna aika janalla**. Lisä tietoja henkilökohtaisista asetuksista on kohdassa [henkilökohtaisten asetusten asetukset](set-personal-options.md).

   > [!div class="mx-imgBorder"]
   > ![Henkilökohtaisten asetusten asetus](media/emailsettings1.png "Henkilökohtaisten asetusten asetus")
   
    > [!div class="mx-imgBorder"]
    > ![Henkilökohtaisten asetusten sähkö postin asetukset](media/emailsettings2.png "Henkilökohtaisten asetusten asetus Sähkö posti osoitteille")

  
## <a name="add-an-appointment"></a>Tapaamisen lisääminen  

Jos haluat lisätä tietueeseen tapaamisaktiviteetin, sinun on ensin tallennettava tietue, johon aktiviteetti lisätään.  
  
1. Avaa tietue, johon haluat lisätä aktiviteetin. Esimerkiksi yhteystietotietue.
  
2. Valitse **Aikajana**-seinällä **plusmerkki** > **Tapaaminen**.  
  
3. Täytä tarvittavat tiedot työkaluvihjeiden avulla.
  
4. Kun olet täyttänyt lomakkeen, tallenna tapaaminen valitsemalla **Tallenna**.

## <a name="add-notes"></a>Lisää huomautuksia

Voit myös helposti lisätä huomautuksia aktiviteettien alueelle.
  
1. Avaa tietue, johon haluat lisätä aktiviteetin. Esimerkiksi yhteystietotietue.
  
2. Aloita huomautusten lisääminen **Aikajana**-seinälle. Lisää mahdolliset liitteet huomautukseen valitsemalla **Lisää liite**.

3. Kun olet täyttänyt lomakkeen, tallenna huomautus valitsemalla **Lisää huomautus**.


> [!NOTE]
> Voit myös lisätä huomautuksen käyttämällä **plusmerkkiä** **Aikajana**-seinän yläosassa.

   > [!div class="mx-imgBorder"]
   > ![Huomautuksen lisääminen](media/addnote.png "Huomautuksen lisääminen")

Kun huomautus on lisätty, voit poistaa sen tai muokata sitä.


> [!div class="mx-imgBorder"]
> ![Huomautuksen päivittäminen](media/addnote2.png "Huomautuksen päivittäminen")

## <a name="add-a-post"></a>Julkaisun lisääminen 

1. Avaa tietue, johon haluat lisätä julkaisun. Esimerkiksi yhteystietotietue.

2. Valitse **Aikajana**-seinällä **plusmerkki** > **Julkaisu**. 

3. Lisää julkaisu tekstikenttään. 

4. Kun olet täyttänyt lomakkeen, tallenna julkaisu valitsemalla **Lisää**.

> [!div class="mx-imgBorder"]
> ![Julkaisun päivittäminen](media/post.png "Julkaisun lisääminen")
  
  Kun olet tallentanut julkaisun, se näkyy Aikajana-seinän yläreunassa.
  
## <a name="refresh-the-timeline"></a>Aikajanan päivittäminen 

Voit päivittää aikajanan näyttääksesi uusimmat tiedot.

Valitse **Aikajana**-seinällä ![Lisää-painike ](media/MoreButton.png "Lisää-painike") ja valitse sitten **Päivitä aikajana**.

> [!div class="mx-imgBorder"]
> ![Aikajanan päivittäminen ](media/refresh.png "Aikajanan päivittäminen")


## <a name="use-the-filter-pane"></a>Suodatinruudun käyttäminen

Suodatinruudun avulla voit suodattaa nopeasti aktiviteetteja, huomautuksia tai julkaisuja Aikajana-seinällä tietue- tai aktiviteettityypin sekä päivämäärän mukaan. Voit valita useita suodattimia ja suodatus asetuksia yhtä aikaa. Voit suodattaa ja tarkastella tehtävän määrä päivää, muokkaus päivämäärää tai tehtävän tilaa.

- Valitse **aika janalla** **Avaa suodatin ruudun** suppilo kuvake.

> [!div class="mx-imgBorder"]
> ![Suodatinruutu aikajanalla ](media/filterpane.png "Suodatinruutu aikajanalla")


## <a name="manage-activities"></a>Aktiviteettien hallinta
Voit hallita aktiviteetteja suoraan Aikajana-seinällä. Voit esimerkiksi määrittää aktiviteetin toiselle henkilölle, poistaa tai sulkea aktiviteetin, lisätä aktiviteetin jonoon, avata liittyvän tietueen tai muokata huomautuksia ja julkaisuja.


> [!div class="mx-imgBorder"]
> ![Hallitse aktiviteetteja.png](media/ManageActivities.png "Hallitse aktiviteetteja.png")



