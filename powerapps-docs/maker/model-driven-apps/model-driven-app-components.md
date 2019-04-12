---
title: Tietoja mallipohjaisen sovelluksen osista PowerAppsissa | MicrosoftDocs
description: 'Tietoja mallipohjaisen sovelluksen eri osista, kuten tiedoista, käyttöliittymästä, logiikasta ja visualisoinnista.'
Keywords: 'kentät, määritteet, mallipohjainen sovellus'
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: powerapps
ms.topic: article
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="understand-model-driven-app-components"></a>Tietoja mallipohjaisen sovelluksen osista
Hyvin suunniteltu mallipohjainen sovellus sisältää useita osia, jotka valitaan suunnitteluohjelman avulla. Lopullisen sovelluksen ulkonäkö ja toiminnot muodostuvat näistä osista. Osista ja osien ominaisuuksista, joita suunnittelijat käyttävät sovelluksen muodostamisessa, tulee metatietoja. 

Osat jaotellaan tässä *tietojen*, *käyttöliittymän*, *logiikan* ja *visualisoinnin* luokkiin. Tällöin on helpompi ymmärtää, miten osat liittyvät sovelluksen suunnitteluun. 

## <a name="data"></a>Tiedot
Nämä osat määrittävät, mihin tietoihin sovellus perustuu.


|Osa  |Kuvaus  |Suunnittelija  |
|---------|---------|---------|
|Entiteetti     |Kohde, jolla on seurattavia ominaisuuksia, kuten yhteyshenkilö tai asiakas. Käytettävissä on useita vakioentiteettejä. Voit mukauttaa muun kuin järjestelmän vakioentiteetin (tuotantoentiteetin) tai luoda mukautetun entiteetin alusta alkaen.     | [!INCLUDE [powerapps](../../includes/powerapps.md)]in entiteetin suunnitteluohjelma        |
|Kenttä     | Ominaisuus, joka on liitetty entiteettiin. Kenttä määritetään tietotyypin mukaan. Tietotyyppi määrittää annettavien tai valittavien tietojen tyypin. Esimerkkejä ovat teksti, numero, päivämäärä ja aika, valuutta ja haku (luo suhteen toisen entiteetin kanssa). Kenttiä käytetään yleensä lomakkeiden, näkymien ja hakujen kanssa.        | [!INCLUDE [powerapps](../../includes/powerapps.md)]in entiteetin suunnitteluohjelma   |
|Suhde     | Entiteettisuhteet määrittävät, millaisia entiteettien väliset suhteet voivat olla. Suhdetyyppejä ovat 1:N (yksi moneen), N:1 (monta yhteen) ja N:N (monta moneen). Esimerkiksi valintakentän lisääminen entiteetille luo uuden 1:N-suhteen kahden entiteetin välille ja mahdollistaa kentän laittamisen lomakkeeseen.   | [!INCLUDE [powerapps](../../includes/powerapps.md)]in entiteetin suunnitteluohjelma        |
|Asetusjoukkokenttä     | Tämä on erityinen kenttä, joka sisältää ennalta määritettyjen asetusten joukon. Kullakin asetuksella on numeerinen arvo ja otsikko. Lomakkeeseen lisättynä kenttä näyttää ohjausobjektin, jonka avulla käyttäjä voi valita asetuksen.  Asetusjoukkoja on kaksi. Toisessa käyttäjä voi valita vain yhden asetuksen. Monivalinta-asetusjoukoissa käyttäjä voi valita useita kohtia.  | [!INCLUDE [powerapps](../../includes/powerapps.md)]in asetusjoukon suunnitteluohjelma     |

Lisätietoja: [Mallipohjaisen sovelluksen tietojen määrittäminen](define-data-model-driven-app.md) 

## <a name="ui"></a>Käyttöliittymä
Nämä osat määrittävät, miten käyttäjät käyttävät sovellusta. 

|Osa  |Kuvaus  |Suunnittelija  |
|---------|---------|---------|
|Sovellus     | Määrittää sovelluksen perustiedot, kuten osat, ominaisuudet, asiakasohjelman tyypin ja sovelluksen URL-osoitteen.      | Sovellusten suunnitteluohjelma   |
|Sivustokartta     | Määrittää sovelluksessa siirtymisen.        | Sivustokartan suunnitteluohjelma        |
|Lomake     | Sen annetun entiteetin tietojen syöttökenttien joukko, joka vastaa organisaation seuraaman entiteetin kohteita. Esimerkiksi tietojen syöttökenttien joukko, joihin käyttäjä syöttää tärkeitä tietoja, joiden avulla asiakkaan edellisiä tilauksia ja tiettyjä pyydettyjä uudelleentilauspäivämääriä seurataan.        | Lomakkeiden suunnitteluohjelma        |
|Näkymä     | Näkymät määrittävät, miten tietyn entiteetin tietueluettelo näytetään sovelluksessa. Näkymä määrittää näytettävät sarakkeet, kunkin sarakkeen leveyden, lajittelutoiminnan ja oletussuodattimet.   |  Näkymän suunnitteluohjelma       |

![Sovellusten suunnitteluohjelma ja lomakkeen suunnitteluohjelma](media/model-driven-app-overview/app-and-form-designers.png)

## <a name="logic"></a>Logiikka
Määrittää sovelluksen liiketoimintaprosessit, -säännöt ja automatisoinnin. [!INCLUDE [powerapps](../../includes/powerapps.md)]in tekijät käyttävät suunnitteluohjelmaa, joka koskee tiettyä prosessi- tai sääntötyyppiä. 


|Logiikan tyyppi  |Kuvaus  |Suunnittelija  |
|---------|---------|---------|
|Liiketoimintaprosessi     | Online-tilan prosessi, joka auttaa käyttäjiä kulkemaan tavanomaisen yritysprosessin läpi. Voit käyttää esimerkiksi liiketoimintaprosessin kulkua, jos haluat kaikkia asiakaspalvelupyyntöjä käsiteltävän samalla tavalla tai vaatia henkilöstöä hankkimaan laskun hyväksyntä ennen tilauksen lähettämistä.        | Liiketoimintaprosessin suunnitteluohjelma        |
|Työnkulku     |  Työnkulut automatisoivat liiketoimintaprosessit ilman käyttöliittymää. Suunnittelijat käyttävät työnkulkuja sellaisten automaattisten prosessien käynnistämiseksi, jotka eivät vaadi käyttäjän toimia.       | Työnkulkujen suunnitteluohjelma        |
|Toiminnot    |  Toiminnot ovat prosessityyppejä, joiden avulla voit manuaalisesti suoraan työnkulusta käynnistää toimintoja, kuten mukautettuja toimintoja.       |  Prosessin suunnittelija       |
|Liiketoimintasääntö     | Käytetään, kun säännön tai suosituksen logiikka kohdistetaan lomakkeeseen, kuten kentän vaatimusten määrittämiseen, kenttien piilottamiseen tai tietojen vahvistamiseen. Sovellusten suunnittelijat käyttävät yksinkertaista käyttöliittymää, jossa voi ottaa käyttöön ja ylläpitää nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä.         |  Liiketoimintasäännön suunnitteluohjelma       |
|Työnkulku     | Työnkulku on pilvipohjainen palvelu, jonka avulla voit luoda automaattisia työnkulkuja sovellusten ja palveluiden välille. Tämä mahdollistaa esimerkiksi ilmoitusten saamisen, tiedostojen synkronoimisen ja tietojen keräämisen.        | Microsoft Flow        |

![Työnkulun, toiminnon ja liiketoimintaprosessin suunnitteluohjelmat](media/model-driven-app-overview/designer-mash.png)

Lisätietoja: [Liiketoimintalogiikan käyttäminen mallipohjaisessa sovelluksessa](guide-staff-through-common-tasks-processes.md)

## <a name="visualizations"></a>Visualisoinnit
Määrittää sovelluksen tietojen visualisointien ja raportoinnin tyypin.


|Osa  |Kuvaus  |Suunnittelija  |
|---------|---------|---------|
|Kaavio     | Yksi graafinen visualisointi, joka voidaan näyttää näkymässä tai lomakkeessa tai lisätä koontinäyttöön.        | Kaavion suunnitteluohjelma        |
|Koontinäyttö     | Vähintään yhden toimintaan johtavien tietojen graafisen visualisoinnin yleiskuvauksen sisältävä toiminto.        | Koontinäytön suunnitteluohjelma        |
|Upotettu Power BI     | Lisää sovellukseen upotetut Power BI -ruudut ja -koontinäytöt. Power BI on pilvipohjainen palvelu, joka sisältää liiketoimintatietoja.        |  Kaavion suunnitteluohjelman, koontinäytön suunnitteluohjelman ja Power BI:n yhdistelmä       |

![Esimerkkikoontinäyttö](media/model-driven-app-overview/dashboard-designer.png)

## <a name="advanced-model-driven-app-making"></a>Mallipohjaisen edistyneen sovelluksen tekeminen
Ratkaisunhallinta on kattava työkalu, jota voi käyttää mallipohjaisen edistyneen sovelluksen luomisessa. Ratkaisunhallinnassa avulla voi siirtyä työkalun vasemmalla puolella olevan siirtymisruudun avulla hierarkiassa, joka sisältää kaikki sovelluksen osat.

![Ratkaisunhallinta](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Voit avata ratkaisunhallinnan valitsemalla [!INCLUDE [powerapps](../../includes/powerapps.md)]in vasemmassa ruudussa **Mallipohjainen**.

  ![Mallipohjaisen valitseminen](media/model-driven-app-overview/app-type-picker-mod.png)

Valitse sitten **Lisäasetukset**-välilehti.

Lisätietoja: [Edistyneen sovelluksen tekeminen ja mukauttaminen](advanced-navigation.md)

## <a name="related-topics"></a>Asiaan liittyviä aiheita

[Mallipohjaisen sovelluksen tarkistaminen ja julkaiseminen](validate-app.md)

[Mallipohjaisen sovelluksen jakaminen](share-model-driven-app.md)
