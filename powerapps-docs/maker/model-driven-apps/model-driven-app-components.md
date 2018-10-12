---
title: Mallipohjaisen sovelluksen osat PowerAppsissa | MicrosoftDocs
description: Tutustu mallipohjaisen sovelluksen eri osiin, kuten tietoihin, käyttöliittymään, logiikkaan ja visualisointiin.
Keywords: fields, attributes, model-driven app
author: Mattp123
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.author: matp
manager: kvivek
ms.date: 06/27/2018
ms.service: crm-online
ms.topic: article
ms.openlocfilehash: 249f0d35ce9eb466303ef16658aa01198632875e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674744"
---
# <a name="understand-model-driven-app-components"></a>Mallipohjaisen sovelluksen osat
Hyvin suunniteltu mallipohjainen sovellus koostuu useista suunnittelijaohjelmalla valitsemistasi osista, joilla luodaan lopullisen sovelluksen ulkoasu ja toiminnallisuus. Osista ja niiden ominaisuuksista, joita suunnittelijat käyttävät sovelluksen muodostamiseen, tulee sovelluksen metatietoja. 

Niiden kunkin osan yhteys sovelluksen suunnitteluun käy selväksi alla olevasta taulukosta, jossa ne on jaettu *tietojen*, *käyttöliittymän*, *logiikan* ja *visualisoinnin* luokkiin. 

## <a name="data"></a>Tiedot
Nämä osat määrittävät, mihin tietoihin sovellus perustuu.


|Osa  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Entiteetti     |Kohde, jossa on ominaisuuksia, joita seurataan, kuten yhteyshenkilö tai tili. Monet vakioentiteetit ovat käytettävissä. Voit mukauttaa järjestelmään kuulumatonta vakioentiteettiä (tuotantoentiteettiä) tai luoda mukautetun entiteetin alusta.     | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteettisuunnittelutyökalu        |
|Kenttä     | Ominaisuus, joka liittyy entiteettiin. Kentän määrittää tietotyyppi, joka määrittää tietotyypin, joka voidaan lisätä tai valita. Esimerkkejä ovat teksti, luku, päivämäärä ja aika, valuutta tai haku (luo yhteyden toisen entiteetin kanssa). Kenttiä käytetään yleensä lomakkeiden, näkymien ja hakujen yhteydessä.        | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteettisuunnittelutyökalu   |
|Yhteydet     | Entiteettiyhteydet määrittävät, miten entiteetit voivat liittyä toisiinsa. Yhteystyyppejä ovat 1:N (yksi moneen), N:1 (monta yhteen) ja N:N (monta moneen). Esimerkiksi hakukentän lisääminen entiteettiin luo uuden 1:N-yhteyden kahden entiteetin välille, ja sen avulla voit sijoittaa kyseisen hakukentän lomakkeeseen.   | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteettisuunnittelutyökalu        |
|Asetusjoukko-kenttä     | Tämä on erityinen kenttä, jossa annetaan käyttäjän käyttöön joukko esimääritettyjä asetuksia. Kussakin asetuksessa on numeroarvo ja otsikko. Kun kenttä lisätään lomakkeeseen, siinä näkyy ohjausobjekti, jonka avulla käyttäjä voi valita asetuksen.  Asetusjoukkoja on kahdenlaisia: joukkoja, joista käyttäjä voi valita vain yhden asetuksen, ja monivalintaisia joukkoja, joista voidaan valita useita asetuksia.  | [!INCLUDE [powerapps](../../includes/powerapps.md)]-asetusjoukkosuunnittelutyökalu     |

Lisätietoja: [Mallipohjaisen sovelluksen tietojen määrittäminen](define-data-model-driven-app.md) 

## <a name="ui"></a>Käyttöliittymä
Nämä osat määrittävät, miten käyttäjät ovat yhteydessä sovellukseen. 

|Osa  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Sovellus     | Määrittää sovelluksen perustoiminnot, kuten sovelluksen osat, ominaisuudet, asiakastyypin ja URL-osoitteen.      | Sovelluksen suunnittelutoiminto   |
|Sivustokartta     | Määrittää navigoinnin sovelluksessa.        | Sivustokartan suunnitteluohjelma        |
|Lomake     | Tiedonsyötön kenttiä tietylle entiteetille, joka vastaa entiteetin kohteita, joita organisaatiosi seuraa. Tiedonsyöttökenttiä ovat esimerkiksi kentät, joihin käyttäjät lisäävät tarvittavia tietoja seuratakseen asiakkaan aiempia tilauksia ja pyydettyjen uusintatilausten päivämääriä.        | Lomakkeiden suunnitteluohjelma        |
|Näkymä     | Näkymät määrittävät, miten tietyn entiteetin tietueluettelo näytetään sovelluksessa. Näkymä määrittää näytettävät sarakkeet, niiden leveyden, lajittelutoiminnan ja oletussuodattimet.   |  Näkymän suunnitteluohjelma       |

![Sovelluksen suunnittelutoiminto ja lomakkeiden suunnitteluohjelma](media/model-driven-app-overview/app-and-form-designers.png)

## <a name="logic"></a>Logiikka
Määrittää sovelluksen liiketoimintaprosessit, säännöt ja automaation. [!INCLUDE [powerapps](../../includes/powerapps.md)]-käyttäjät voivat käyttää suunnittelutoimintoa, joka liittyy prosessin tai säännön tyyppiin. 


|Logiikkatyyppi  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Liiketoimintaprosessin työnkulku     | Verkkopohjainen prosessi, joka ohjaa käyttäjät vakioliiketoimintaprosessin läpi. Käytä liiketoimintaprosessin työnkulkua esimerkiksi silloin, kun haluat kaikkien käsittelevän asiakaspalvelupyyntöjä samalla tavalla tai henkilökunnan hankkivan hyväksynnän laskulle ennen tilauksen lähettämistä.        | Liiketoimintaprosessin työnkulun suunnittelutyökalu        |
|Työnkulku     |  Työnkulkujen avulla automatisoidaan liiketoimintaprosesseja ilman käyttöliittymää. Työnkulkujen avulla suunnittelutyökalut käynnistävät automaatioita, jotka eivät edellytä käyttäjän toimia.       | Työnkulun suunnittelutyökalu        |
|Toiminnot    |  Toiminnot ovat prosessityyppi, joiden avulla voit manuaalisesti käynnistää toimintoja, kuten mukautettuja toimintoja, suoraan työnkulusta.       |  Prosessin suunnittelutyökalu       |
|Liiketoimintasääntö     | Käytetään sääntö- tai suosituslogiikan soveltamiseen lomakkeessa, kuten määritettyihin kentän vaatimuksiin, kenttien piilottamiseen tai tietojen varmistamiseen. Sovellussuunnittelijat käyttävät yksinkertaista käyttöliittymää toteuttamaan ja ylläpitämään nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä.         |  Liiketoimintasäännön suunnittelutyökalu       |
|Työnkulku     | Työnkulku on pilvipohjainen palvelu, jonka avulla voidaan luoda automatisoituja työnkulkuja sovellusten ja palveluiden välille esimerkiksi ilmoitusten saamiseksi, tiedostojen synkronoimiseksi ja tietojen keräämiseksi.        | Microsoft Flow        |

![Työnkulun, toiminnon ja liiketoiminnan prosessin kulun suunnittelutyökalut](media/model-driven-app-overview/designer-mash.png)

Lisätietoja: [Liiketoimintalogiikan käyttäminen mallipohjaisessa sovelluksessa](guide-staff-through-common-tasks-processes.md)

## <a name="visualizations"></a>Visualisoinnit
Määrittää, millaisia tietojen visualisointeja ja raportointeja sovelluksella on käytettävissään.


|Osa  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Kaavio     | Yksittäinen graafinen visualisointi, joka voidaan näyttää näkymässä tai lomakkeessa tai lisätä koontinäyttöön.        | Kaavion suunnitteluohjelma        |
|Koontinäyttö     | Toimii yhden tai usean graafisen visualisoinnin palettina, joka näyttää yleiskatsauksen toimintoa vaativista yritystiedoista.        | Raporttinäkymät-ikkunan suunnittelusovellus        |
|Upotettu Power BI     | Lisää sovellukseen upotettuja Power BI -ruutuja ja koontinäyttöjä. Power BI on pilvipohjainen palvelu, joka tarjoaa liiketoimintatietoa.        |  Kaavion suunnitteluohjelman, raporttinäkymät-ikkunan suunnittelusovelluksen ja Power BI:n yhdistelmä       |

![Esimerkkikoontinäyttö](media/model-driven-app-overview/dashboard-designer.png)

## <a name="advanced-model-driven-app-making"></a>Kehittynyttä mallipohjaisten sovellusten suunnittelua
Ratkaisunhallinta on kattava työkalu, jota käytetään mallipohjaisten sovellusten kehittyneeseen muodostamiseen. Ratkaisunhallinnassa voi liikkua työkalun vasemmalla puolella olevan siirtymisruudun avulla hierarkiassa, joka koostuu kaikista sovelluksen osista.

![Ratkaisunhallinta](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Avaa ratkaisunhallinta valitsemalla [!INCLUDE [powerapps](../../includes/powerapps.md)]vasemmanpuoleisessa ruudussa **Malliin perustuva**.

  ![Valitse Malliin perustuva](media/model-driven-app-overview/app-type-picker-mod.png)

Valitse sitten **Lisäasetukset**-välilehti.

Lisätietoja: [Kehittyneiden sovellusten luominen ja mukauttaminen ](advanced-navigation.md)

## <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Mallipohjaisen sovelluksen vahvistaminen ja julkaiseminen](validate-app.md)

[Mallipohjaisen sovelluksen jakaminen](share-model-driven-app.md)