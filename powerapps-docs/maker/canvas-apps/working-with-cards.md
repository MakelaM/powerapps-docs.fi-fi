---
title: Tutustu yhteyskortteihin | Microsoft Docs
description: Lomakkeen korttien avulla voit kerätä ja näyttää tietoja tietolähteestä.
documentationcenter: na
author: gregli-msft
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/26/2016
ms.author: gregli
ms.openlocfilehash: 074e40dd2fc19279bef36ac91196c61b050abda3
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="understand-data-cards"></a>Tutustu yhteyskortteihin
**[Korttiohjausobjektit](controls/control-card.md)** ovat  **[lomakkeen muokkaamisen](controls/control-form-detail.md)** ja **[näyttämisen](controls/control-form-detail.md)** ohjausobjektien rakenneosia. Lomake edustaa koko tietuetta ja jokainen kortti kyseisen tietueen yksittäistä kenttää.

Kortteja on kätevintä käsitellä oikeanpuoleisessa ruudussa sen jälkeen, kun olet valinnut lomakkeen ohjausobjektin suunnittelutyötilassa. Tässä ruudussa voit valita, mitä kenttiä näytetään, miten ne näytetään ja missä järjestyksessä ne näytetään. Tässä esimerkissä näkyy **lomakkeen muokkauksen** ohjausobjekti sovelluksessa, joka luotiin SharePoint-luettelossa nimeltä **Assets**.

![](./media/working-with-cards/first-screen.png)

Aloita katsomalla tietoja [lomakkeen lisäämisestä](add-form.md) ja tutustumalla [tietolomakkeisiin](working-with-forms.md). Tämän ohjeaiheen loppuosassa käsittelemme tarkemmin korttien toimintaa ja opimme, miten niitä voidaan mukauttaa ja jopa luoda itse.

## <a name="predefined-cards"></a>Ennalta määritetyt kortit
PowerApps tarjoaa esimääritettyjä kortteja merkkijonoja, numeroita ja muita tietotyyppejä varten. Oikeanpuoleisessa ruudussa näkyvät käytettävissä olevat muunnelmat ja siellä voit muuttaa kentässä käytettyä korttia:

![](./media/working-with-cards/selected-card.png)

Tässä esimerkissä on valittuna yksirivinen tekstikortti, mutta URL-osoitteen teksti on pidempi kuin yhdellä rivillä voidaan näyttää. Muunnamme tämän moniriviseksi tekstikortiksi, jotta käyttäjillä on enemmän muokkaustilaa:

![](./media/working-with-cards/multiline-edit.png)

Useita tämän tietolähteen kenttiä ei ole näkyvissä, mutta voit näyttää tai piilottaa kentän valitsemalla sen valintaruudun. Tässä esimerkissä kuvataan, miten **SecurityCode**-kenttä näytetään.

![](./media/working-with-cards/add-security-code.png)

## <a name="customize-a-card"></a>Mukauta kortti
Kortit sisältävät muita ohjausobjekteja. Käyttäjä lisää **lomakkeen muokkauksen** ohjausobjektiin tietoja **[tekstinsyötön](controls/control-text-input.md)** vakio-ohjausobjektilla, joka lisätään **Lisää**-välilehdestä.  

Katsotaan nyt esimerkkiä, jossa tutustutaan kortin ulkoasun muuttamiseen sen ohjausobjekteja käsittelemällä.

1. Palataan ensin korttiin, jonka viimeksi lisäsimme, ja sen **SecurityCode**-kenttään. Valitse tämä kortti napsauttamalla tai napauttamalla sitä kerran:
   
    ![](./media/working-with-cards/select-security-code.png)
2. Valitse kortin sisällä oleva **[tekstinsyötön](controls/control-text-input.md)** ohjausobjekti napsauttamalla tai napauttamalla itse syöteohjausobjektia.
   
    ![](./media/working-with-cards/select-text-input.png)
3. Siirrä tätä ohjausobjektia kortin sisällä vetämällä valintakehystä, ja muuta ohjausobjektin kokoa vetämällä valintakehyksen reunassa olevia kahvoja:
   
    ![](./media/working-with-cards/customize-text-input.png)  

Voit muuttaa ohjausobjektien kokoa, siirtää niitä ja tehdä muita muutoksia niihin kortissa, mutta et voi poistaa sitä, ennen kuin olet avannut sen lukituksen.

## <a name="unlock-a-card"></a>Kortin lukituksen avaaminen
Sen lisäksi, että kortit sisältävät ohjausobjekteja, ne ovat myös itse ohjausobjekteja, joilla on ominaisuuksia ja kaavoja samalla tavalla kuin muilla ohjausobjekteilla. Kun valitset lomakkeen kentän ja näytät sen, oikeanpuoleiseen ruutuun luodaan automaattisesti kortti tarvittavine kaavoineen.  Nämä kaavat näkyvät oikeanpuoleisen ruudun **Lisäasetukset**-välilehdessä:

![](./media/working-with-cards/advanced-locked.png)

Näkyvissä on heti yksi kortin tärkeimmistä ominaisuuksista: **[DataField](controls/control-card.md)**-ominaisuus. Tämä ominaisuus ilmaisee, minkä tietolähteen kentän käyttäjä näkee ja mitä kenttää hän voi muokata tässä kortissa.  

**Lisäasetukset**-välilehden yläreunassa oleva palkki ilmaisee, että tämän kortin ominaisuudet on lukittu. Lukkokuvake näkyy myös ominaisuuksien **[DataField](controls/control-card.md)**,  **[DisplayName](controls/control-card.md)** ja **[Pakollinen](controls/control-card.md)** kohdalla. Oikeanpuoleinen ruutu loi nämä kaavat, ja lukituksella estetään tahattomat muutokset näihin ominaisuuksiin.

![](./media/working-with-cards/lock-icons.png)

Avaa kortin lukitus napsauttamalla tai napauttamalla yläreunassa olevaa palkkia, jotta voit muokata näitä ominaisuuksia:

![](./media/working-with-cards/unlocked-card.png)

Muokataan nyt ohjausobjektia **[DisplayName](controls/control-card.md)** lisäämällä välilyönti **Resurssi**- ja **Tunnus**-kohtien väliin. Tällä muutoksella muutamme luotua korttia.  Oikeanpuoleisessa ruudussa tällä kortilla on eri selite:

![](./media/working-with-cards/change-display-name.png)

Olemme nyt ottaneet kortin hallintaamme ja voimme muokata sitä edelleen tarpeisiimme sopivaksi. Olemme kuitenkin menettäneet mahdollisuuden muuttaa kortin esitystapaa (esimerkiksi yksirivisestä tekstistä moniriviseen tekstiin), kuten teimme aiemminkin. Olemme muuntaneet esimääritetyn kortin mukautetuksi kortiksi, jota nyt hallitsemme.  

> [!IMPORTANT]
> Korttia ei voi lukita uudelleen sen jälkeen, kun sen lukitus on poistettu. Jos haluat siirtää kortin takaisin lukittuun tilaan, poista se ja aseta se uudelleen oikeanpuoleiseen ruutuun.

Voit muuttaa lukitsemattoman kortin ulkoasua ja toimintaa monin eri tavoin, kuten lisäämällä ja poistamalla sen sisältämiä ohjausobjekteja. Voit esimerkiksi lisätä tähtimuodon **Lisää**-välilehden **Kuvakkeet**-valikosta.

![](./media/working-with-cards/add-star.png)

Tähti on nyt osa korttia ja siirtyy sen mukana, jos esimerkiksi järjestät lomakkeen kortit uudelleen.

Toisena esimerkkinä voit avata kortin **ImageURL** lukituksen ja lisätä sitten **Lisää**-välilehdestä **Image**-ohjausobjektin siihen:

![](./media/working-with-cards/add-image.png)

Aseta kaavarivillä tämän ohjausobjektin **Kuva**-ominaisuudeksi *TextBox*.**Text**, jossa *TextBox* on nimi URL-osoitteen sisältämän **tekstinsyötön** ohjausobjektin nimi:

> [!TIP]
> Paina Alt-näppäintä, niin näet jokaisen ohjausobjektin nimen.

![](./media/working-with-cards/show-image.png)

Nyt näemme kuvat ja voimme muokata niiden URL-osoitteita. Huomaa, että olisimme voineet käyttää **Kuva**-ominaisuutena **Parent.Default**ia, mutta se ei olisi päivittynyt käyttäjän muuttaessa URL-osoitetta.

Voimme tehdä samalla tavalla toisessa tämän sovelluksen näytössä, jossa näytämme tietueen tiedot **lomakkeen näyttämisen** ohjausobjektin avulla. Tässä tapauksessa haluamme ehkä piilottaa selitteen (aseta selitteen, ei kortin, **Näkyvissä**-ominaisuudeksi **false**), koska käyttäjä ei muokkaa URL-osoitetta kyseisessä näytössä:

![](./media/working-with-cards/show-image-display.png)

## <a name="interact-with-a-form"></a>Lomakkeen käsitteleminen
Avattuasi kortin lukituksen voit muuttaa tapaa, jolla se toimii sen sisältävän lomakkeen kanssa.

Alla on joitakin ohjeita siitä, miten ohjausobjektien on toimittava korttinsa kanssa ja miten korttien on toimittava lomakkeen kanssa. Nämä ovat vain suuntaviivoja. Voit luoda kaavoja, jotka viittaavat mihin tahansa PowerApps-ohjausobjektiin, samalla tavalla kuin kaikkien ohjausobjektien yhteydessä PowerAppsissa. Tämä koskee myös kortteja ja korttien ohjausobjekteja. Älä unohda luovuutta: sovelluksen voi luoda monella eri tavalla.  

### <a name="datafield-property"></a>DataField-ominaisuus
Kortin tärkein ominaisuus on **[DataField](controls/control-card.md)**-ominaisuus.  Tämä ominaisuus vaikuttaa vahvistukseen, kenttien päivitykseen ja muihin kortin ominaisuuksiin.

### <a name="information-flowing-in"></a>Työnkulun tiedot sisään
Säilönä lomake asettaa **ThisItem**-operaattorin kaikkien sen sisältämien korttien saataville. Tämä tietue sisältää kaikki kiinnostuksen kohteena olevan nykyisen tietueen kentät.  

Jokaisen kortin **[Oletus](controls/properties-core.md)**-ominaisuuden arvoksi on asetettava **ThisItem**. *FieldName*.  Joissakin tilanteissa haluat ehkä muuntaa tätä arvoa tietojen tullessa sisään. Saatat esimerkiksi haluta muotoilla merkkijonon tai kääntää arvon jostakin kielestä toiseen kieleen.

Kunkin kortissa olevan ohjausobjektin on viitattava **Parent.Default**-ominaisuuteen, jotta kentän arvoon päästään käsiksi. Tämä strategia tarjoaa kapseloinnin kortille niin, että kortin **[Oletus](controls/properties-core.md)**-ominaisuutta voidaan muuttaa muuttamatta kortin sisäisiä kaavoja.

Ominaisuudet **DefaultValue** ja **[Pakollinen](controls/control-card.md)** saadaan oletusarvoisesti tietolähteen metatiedoista **[DataField](controls/control-card.md)**-ominaisuuden perusteella. Voit ohittaa nämä kaavat käyttämällä omaa logiikkaa integroimalla tietolähteen metatiedot **[DataSourceInfo](functions/function-datasourceinfo.md)**-funktion avulla.

### <a name="information-flowing-out"></a>Työnkulun tiedot ulos
Kun käyttäjä on muokannut tietuetta kortin ohjausobjekteilla, **[SubmitForm](functions/function-form.md)**-funktio tallentaa kyseiset muutokset tietolähteeseen. Funktion suorittuessa lomakkeen ohjausobjektissa lukee jokaisen kortin **[DataField](controls/control-card.md)**-ominaisuuden arvot, mikä auttaa tunnistamaan muutettavat kentät.  

Lomakkeen ohjausobjektissa lukee myös jokaisen kortin **[Päivitä](controls/control-card.md)**-ominaisuus. Tämä arvo tallennetaan tietolähteeseen tälle kentälle. Tähän voidaan lisätä toinen muunnos, esimerkiksi sen muunnoksen peruutus, jota käytettiin kortin **[Oletus](controls/properties-core.md)**-kaavassa.

**Kelvollinen**-ominaisuus haetaan tietolähteen metatiedoista **[DataField](controls/control-card.md)**-ominaisuuden perusteella. Se perustuu myös **[Pakollinen](controls/control-card.md)**-ominaisuuteen ja siihen, sisältyykö **[Päivitys](controls/control-card.md)** -ominaisuuteen arvoa. Jos **[Päivitys](controls/control-card.md)**-ominaisuuden arvo ei ole kelvollinen, **Virhe**-ominaisuus antaa käyttöystävällisen virhesanoman.

Jos kortin **[DataField](controls/control-card.md)**-ominaisuus on *tyhjä*, kortti on vain ohjausobjektien säilö. Sen ominaisuudet **Kelvollinen** ja **[Päivitys](controls/control-card.md)** eivät osallistu lomakkeen lähettämiseen.

## <a name="dissecting-an-example"></a>Esimerkin analysointi
Tutustumme nyt ohjausobjekteihin, joista perustiedonsyöttökortti koostuu. Väliä ohjausobjektien välillä on suurennettu, jotta ne on helpompi nähdä:

![](./media/working-with-cards/dissect-card1.png)

Näytä niiden ohjausobjektien nimet, joista tämä kortti koostuu pitämällä Alt-näppäintä painettuna:

![](./media/working-with-cards/dissect-card2.png)

Tämä kortti koostuu neljästä ohjausobjektista:

| Nimi | Tyyppi | Kuvaus |
| --- | --- | --- |
| **TextRequiredStar** |**[Otsikon](controls/control-text-box.md)** ohjausobjekti |Näyttää tähden, jota käytetään usein tiedonsyöttölomakkeissa ilmoittamaan, että kenttä on pakollinen. |
| **TextFieldDisplayName** |**[Otsikon](controls/control-text-box.md)** ohjausobjekti |Näyttää tämän kentän kutsumanimen. Tämä nimi voi erota nimestä tietolähteen rakenteessa. |
| **InputText** |**Syötteen tekstin** ohjausobjekti |Näyttää kentän alkuarvon, jota käyttäjä voi muuttaa. |
| **TextErrorMessage** |**[Otsikon](controls/control-text-box.md)** ohjausobjekti |Näyttää käyttäjäystävällisen virhesanoman käyttäjälle, jos vahvistuksessa ilmenee ongelmia. Varmistaa myös, että kentässä on arvo, jos se on pakollinen. |

Näiden ohjausobjektien tiedot täytetään noutamalla niiden ominaisuudet kortin ominaisuuksista näillä keskeisillä kaavoilla. Huomaa, että mikään näistä kaavoista ei viittaa mihinkään tiettyyn kenttään. Kaikki tiedot ovat sen sijaan peräisin kortista.

| Ohjausobjektin ominaisuus | Kaava | Kuvaus |
| --- | --- | --- |
| **TextRequiredStar.Visible** |**Parent.Required** |Tähti näkyy vain, jos kenttä on pakollinen. Pakollinen on kaava, jota käyttäjä tai tietolähteen metatiedot ohjaavat. |
| **TextFieldDisplayName.Text** |**Parent.DisplayName** |Tekstiruudun ohjausobjekti näyttää kutsumanimen, jonka antaa käyttäjä tai tietolähteen metatiedot ja joka määritetään kortin **[DisplayName](controls/control-card.md)**-ominaisuudessa. |
| **InputText.Default** |**Parent.Default** |Tekstinsyöte-ohjausobjekti näyttää aluksi kentän arvon tietolähteestä kortin oletusarvon mukaisesti. |
| **TextErrorMessage.Text** |**Parent.Error** |Jos vahvistusongelma ilmenee, kortin **Virhe**-ominaisuus näyttää asianmukaisen virhesanoman. |

Käytämme seuraavia keskeisiä kaavoja tietojen hakemiseksi näistä ohjausobjekteista ja niiden siirtämiseksi takaisin tietolähteeseen:

| Ohjausobjektin nimi | Kaava | Kuvaus |
| --- | --- | --- |
| **DataCard.DataField** |**"ApproverEmail"** |Kentän nimi, jonka käyttäjä voi näyttää ja jota voi muokata tässä kortissa. |
| **DataCard.Update** |**InputText.Text** |Arvo, joka vahvistetaan ja siirretään takaisin tietolähteeseen, kun **[SubmitForm](functions/function-form.md)** suoritetaan. |

