---
title: Tapaamisen, sähköpostin, puhelun, huomautuksen tai tehtävän lisääminen aikajanaan mallipohjaisessa sovelluksessa | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 9ba051395e99dc6f2079d033c10a727a2e95da67
ms.sourcegitcommit: 9a16bb75c856f7c84cd385811b7135ab2804ae69
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/03/2019
ms.locfileid: "71924580"
---
# <a name="add-an-appointment-email-phone-call-note-or-task-activity-to-the-timeline"></a>Tapaamisen, sähköpostin, puhelun, huomautuksen tai tehtävän lisääminen aikajanaan 


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
    > Jos haluat luetella keskustelu näkymässä olevat Sähkö posti viestit, valitse **asetukset** > **mukautus asetukset** > **Sähkö posti** -väli lehti ja valitse sitten **Näytä Sähkö posti viesti keskusteluna aika janalla**. Lisä tietoja henkilökohtaisista asetuksista on kohdassa [henkilökohtaisten asetusten asetukset](https://docs.microsoft.com/en-us/powerapps/user/set-personal-options#email-tab-options). Kun se on käytössä, voit avata minkä tahansa lomakkeen, jolla on aika Jana, ja sähkö postisi ryhmitellään keskustelu säikeiksi, joissa on uusin Sähkö posti viesti ylimpänä.

   > [!div class="mx-imgBorder"]
   > Henkilökohtaisten ![asetusten asetus](media/emailsettings1.png "henkilökohtaisten asetusten") asetus
   
    > [!div class="mx-imgBorder"]
    > ![Henkilökohtaisten asetusten asetus sähkö postin](media/emailsettings2.png "henkilökohtaisten asetusten asetus sähkö postiin")

  
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



