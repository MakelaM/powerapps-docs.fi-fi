---
title: Mukautettujen kuvakkeiden näyttäminen luettelonäkymien arvojen sijaan PowerAppsilla | MicrosoftDocs
description: 'Tietoja siitä, miten voit näyttää näkymässä mukautettuja kuvakkeita'
ms.custom: ''
ms.date: 06/21/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: af866aed-2586-4b6f-bb1c-3519baae3645
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="display-custom-icons-instead-of-values-in-list-views"></a>Mukautettujen kuvakkeiden näyttäminen luettelonäkymien arvojen sijaan

<a name="GridIcons"></a>   

 PowerApps-ympäristön järjestelmänvalvojat ja mukauttajat voivat lisätä kuvia näkymään yhteyttä ja määrittää kuvan valinnassa käytettävän logiikan sarakkeen arvojen perusteella JavaScriptin avulla. Mahdollisuus näyttää luettelonäkymät, joiden joissakin sarakkeissa näkyy kuvakkeita teksti- tai numeroarvojen sijaan, lisättiin Liikesuhdetoimintoihin. 
  
> [!NOTE]
>  Ruudukkokuvakkeet näytetään vain WWW-liittymässä. Ne eivät näy [!INCLUDE[pn_Outlook_short](../../includes/pn-outlook-short.md)]issa ja mobiilisovelluksessa.  
  
### <a name="add-custom-graphics-and-javascript-as-web-resources"></a>Mukautetun grafiikan ja JavaScriptin lisääminen WWW-resursseina  
  
1.  Luo mukauttamisessa tarvittavat uudet grafiikkatiedostot. Suosittelemme kuvakkeen kooksi 16x16 kuvapistettä (suuremmat kuvat skaalataan pienemmiksi).  
  
2.  Kirjoita vähintään yksi JavaScript-funktio, joka määrittää eri arvoille näytettävät kuvakkeet (yleensä tarvitaan yksi funktio jokaiselle mukautettavalle sarakkeelle). Kunkin funktion on hyväksyttävä rivin tieto-objektin ja kielen (LCID) koodi syöttönä ja palautettava matriisi joka sisältää kuvan nimen ja työkaluvihjeen tekstin. Löydät esimerkin myöhemmin tässä ohjeaiheessa olevasta kohdasta [Esimerkki JavaScript-funktio](#SampleJavascript).  
  
3.  Kirjautuminen järjestelmänvalvojana ympäristöösi ja [ratkaisunhallinnan](../model-driven-apps/advanced-navigation.md#solution-explorer) avaaminen.  
  
4.  **Oletusratkaisu**-ponnahdusikkuna avautuu. Siirry kohtaan **Komponentit** > **WWW-resurssit**.  
  
5.  Nyt mukautettu grafiikka ladataan kerralla WWW-resursseina. Valitse työkalurivin **Uusi**-painike ja luo uusi WWW-resurssi. Näyttöön avautuu toinen resurssin luomisessa auttava ponnahdusikkuna. Toimi seuraavasti:  
  
    1.  Anna uudelle resurssille merkityksellinen **nimi**. Se on nimi, johon grafiikkakohteeseen viitataan JavaScript-koodissa.  
  
    2.  Määritä grafiikkamuodolle **Tyyppi**, jota olet käyttänyt grafiikkatiedoston tallentamisessa (PNG, JPEG tai GIF).  
  
    3.  Valitse **Valitse tiedosto**, jotta voit avata tiedoston selainikkunassa. Käytetään grafiikkatiedoston etsimisessä ja valitsemisessa.  
  
    4.  Lisää halutessasi **näyttönimi** ja/tai **kuvaus**.  
  
    5.  Valitse **Tallenna** ja sulje **WWW-resurssi**-ikkuna.  
  
6.  Toista edellinen vaihe jokaisen grafiikkatiedoston kohdalla.  
  
7.  Nyt voit lisätä oman JavaScriptin viimeisenä WWW-resurssina. Valitse työkalurivin **Uusi**-painike ja luo uusi WWW-resurssi. Näyttöön avautuu toinen resurssin luomisessa auttava ponnahdusikkuna. Toimi seuraavasti:  
  
    1.  Anna uudelle resurssille merkityksellinen **nimi**.  
  
    2.  Määritä **tyypiksi** **Komentosarja (JScript)**.  
  
    3.  Valitse tekstieditori-ikkuna valitsemalla **Tekstieditori** (**Tyyppi**-asetuksen vieressä). Liitä JavaScript-koodi tähän ja tallenna se valitsemalla **OK**.  
  
    4.  Lisää halutessasi **näyttönimi** ja/tai **kuvaus**.  
  
    5.  Valitse **Tallenna** ja sulje **WWW-resurssi**-ikkuna.  
  
8.  Kun **Oletusratkaisu**-ponnahdusikkuna on yhä auki, laajennat **Komponentit** > **Entiteetit**-puurakenteen ja etsit mukautettavan entiteetin.  
  
9. Laajenna entiteetti ja valitse sen **Näkymät**-kuvake.  
  
10. Näkyville tulee valitun entiteetin näkymäluettelo. Valitse näkymä luettelosta. Avaa sitten työkalurivin avattava **Lisää toimintoja** -luettelo ja valitse **Muokkaa**.  
  
11. Näyttöön avautuu uusi ponnahdusikkuna, joka sisältää valitun näkymän ohjausobjektit muokkaamista varten. Ikkuna sisältää näkymän jokaisen sarakkeen. Valitse kohdesarake ja valitse sitten **Muuta ominaisuuksia** -painike **Yleiset tehtävät** -ruudussa. **Muuta sarakkeen ominaisuudet** -valintaikkuna avautuu. Tee siinä seuraavat asetukset:  
  
    - **WWW-resurssi**: Määritä sen luomasi WWW-resurssin nimi, joka sisältää JavaScript-funktiot (valitse se luettelosta **selainpainikkeen** avulla).  
  
    - **Funktion nimi**: Kirjoita sen kirjoittamasi funktion nimi, joka muokkaa valittua saraketta ja näkymää.  
  
12. Valitse **OK** ja sulje **Muuta sarakkeen ominaisuudet** -valintaikkuna.  
  
13. Sulje näkymä valitsemalla **Tallenna ja sulje**.  
  
14. Toista nämä vaiheet tarvittaessa jokaiselle entiteetille, näkymälle ja sarakkeelle.  
  
15. Kun olet valmis, julkaise muutokset valitsemalla **Julkaise kaikki mukautukset**. Sen jälkeen voit sulkea **Oletusratkaisu**-ponnahdusikkunan.  
  
<a name="SampleJavascript"></a>   

### <a name="sample-javascript-function"></a>JavaScript-mallifunktio  
 Mukautettujen kuvakkeiden ja työkaluvihjeiden näyttämisen JavaScript-funktio odottaa kahta argumenttia, jotka ovat layoutxml-kohdassa määritetty koko rivin objekti ja kutsuvan käyttäjän aluekohtaisten asetusten tunnus (LCID). LCID-parametrin avulla voit määrittää työkaluvihjeen tekstin useilla eri kielillä. Lisätietoja ympäristön tukemista kielistä on kohdassa [Kielten ottaminen käyttöön](https://docs.microsoft.com/dynamics365/customer-engagement/admin/enable-languages) ja [Dynamics 365:n kielipakettien asentaminen ja päivittäminen](https://technet.microsoft.com/library/hh699674.aspx). Lisätietoja koodissa käytettävien aluekohtaisten asetusten tunnuksen (LCID) arvoista on kohdassa [Microsoftin määrittämät aluekohtaisten asetusten tunnukset](https://go.microsoft.com/fwlink/?linkid=829588) .

  
 Oletetaan, että lisäät mukautettuja kuvakkeita asetusjoukolle, jonka tyyppi on Määrite. Sillä on rajattu määrä ennalta määritettyjä asetuksia. Varmista, että käytät kokonaislukuarvoa otsikon sijaan, jotta lokalisoinnissa ei tapahdu virheitä.  
  
 Seuraava mallikoodi näyttää kuvakkeet ja työkaluvihjeet yhden arvon perusteella kolmesta (1: kuuma, 2: lämmin, 3: kylmä) opportunityratingcode (luokitus) -määritteessä. Mallikoodi näyttää myös, miten lokalisoidun työkaluvihjeen teksti näytetään. Tätä mallia varten on luotava kolme kuva-WWW-resurssia, joiden koko on 16x16-ilmentymässä ja joiden nimet: new_Hot, new_Warm, and new_Cold.  
  
```  
function displayIconTooltip(rowData, userLCID) {      
    var str = JSON.parse(rowData);  
    var coldata = str.opportunityratingcode_Value;  
    var imgName = "";  
    var tooltip = "";  
    switch (parseInt(coldata,10)) { 
        case 1:  
            imgName = "new_Hot";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Hot";  
                    break;  
                default:  
                    tooltip = "Opportunity is Hot";  
                    break;  
            }  
            break;  
        case 2:  
            imgName = "new_Warm";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Warm";  
                    break;  
                default:  
                    tooltip = "Opportunity is Warm";  
                    break;  
            }  
            break;  
        case 3:  
            imgName = "new_Cold";  
            switch (userLCID) {  
                case 1036:  
                    tooltip = "French: Opportunity is Cold";  
                    break;  
                default:  
                    tooltip = "Opportunity is Cold";  
                    break;  
            }  
            break;  
        default:  
            imgName = "";  
            tooltip = "";  
            break;  
    }  
    var resultarray = [imgName, tooltip];  
    return resultarray;  
}  
```  
  
 Kuvakkeiden näyttäminen työkaluvihjeissä **Luokitus**-sarakkeessa riippuu kunkin rivin arvosta. Tulos saattaa olla tämä:  
  
 ![Mukautettuja kuvia esimerkki](media/custom-column-graphics-example.png "Mukautettuja kuvia esimerkki")  
 
 ### <a name="see-also"></a>Katso myös
 [Näkymien luominen tai muokkaaminen](../model-driven-apps/create-edit-views.md)
