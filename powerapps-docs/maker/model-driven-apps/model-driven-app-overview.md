---
title: Yleiskatsaus mallipohjaisen sovelluksen luomisesta PowerAppsin avulla | Microsoft Docs
description: Vaiheittaiset ohjeet entiteetin luomiseen ja määrittämiseen PowerApps-sovelluksessa käyttämistä varten.
documentationcenter: na
author: Mattp123
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/21/2018
ms.author: matp
ms.openlocfilehash: eceaf1886bf77b85d6d6b3faae3f32428223cb7e
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37899498"
---
# <a name="overview-of-building-a-model-driven-app"></a>Yleiskatsaus mallipohjaisen sovelluksen luomiseen

Mallipohjainen sovelluskehitys on komponenttikeskeinen sovelluskehitystapa. Mallipohjaisessa sovelluskehityksessä ei tarvitse käyttää koodia, ja luodut sovellukset voivat olla joko yksinkertaisia tai sitten hyvin monimutkaista.  Toisin kuin pohjaan perustuvat sovellukset, joissa suunnittelijalla on täydet oikeudet sovelluksen ulkoasuun, mallipohjaisissa sovelluksissa asettelu, jonka määrittävät pitkälti sovellukseen lisäämäsi osat, on määritetty puolestasi. 

![Mallipohjaisen sovelluksen esimerkki](media/model-driven-app-overview/model-app-sample.png)

Mallipohjaiset sovellukset tarjoavat seuraavat edut:
- monipuoliset, komponenttikeskeiset, koodittomat kehitysympäristöt 
- luo monipuolisia, hyvin reagoivia sovelluksia, joissa on samanlainen käyttöliittymä työpöydältä mobiililaitteisiin
- kehitysominaisuudet vastaavat Dynamics 365:ssä käytettävissä olevaa asiakkaan osallistumisen ympäristöä 
- sovellus voidaan jakaa ratkaisuna.

## <a name="the-approach-to-model-driven-app-making"></a>Mallipohjaisten sovellusten tekeminen
Periaatteessa mallipohjaisten sovellusten tekemisessä on kolme keskeistä aluetta.

- yritystietojen mallinnus 
- liiketoimintaprosessien määrittäminen 
- sovelluksen muodostaminen.

### <a name="modeling-business-data"></a>Yritystietojen mallinnus
Yritystietojen mallinnuksessa määrität, mitä tietoja sovelluksesi tarvitsee ja miten nämä tiedot liittyvät muihin tietoihin. Mallipohjaisessa suunnittelussa käytetään metatietopohjaista arkkitehtuuria, jotta suunnittelijat voivat mukauttaa sovelluksen koodia kirjoittamatta. Metatiedot tarkoittavat ”tietoja tiedoista”, ja ne määrittävät järjestelmään tallennettujen tietojen rakenteen. [Opetusohjelma: Luo komponentteja sisältävä mukautettu entiteetti PowerAppsissa](../common-data-service/create-custom-entity.md)

### <a name="defining-business-processes"></a>Liiketoimintaprosessien määrittäminen
Yhdenmukaisten liiketoimintaprosessien määrittäminen ja ottaminen pakotetusti käyttöön on mallipohjaisten sovellusten keskeinen osa. Yhdenmukaiset prosessit auttavat käyttäjiä keskittymään työtehtäviinsä sen sijaan, että he joutuisivat muistelemaan työnkulkuun liittyviä manuaalisia vaiheita. Prosessit voivat olla yksinkertaisia tai monimutkaisia ja muuttua usein ajan myötä. Luo prosessi avaamalla [ratkaisunhallinta](#advanced-model-driven-app-making) ja valitsemalla **Lisäasetukset**. Valitse sitten ratkaisunhallinnan vasemmanpuoleisesta siirtymisruudusta **Prosessit** ja sitten **Uusi**. Lisätietoja: [Työskenteleminen liiketoimintalogiikan parissa](#working-with-business-logic)  

### <a name="composing-the-model-driven-app"></a>Mallipohjaisen sovelluksen muodostaminen
Kun tietojen mallinnus ja prosessien määrittäminen on tehty, luo sovelluksesi valitsemalla ja määrittämällä tarvitsemasi osat sovelluksen suunnittelutoiminnolla.

![Sovelluksen suunnittelutoiminto](media/model-driven-app-overview/app-designer.png)

## <a name="model-driven-app-components-and-designers"></a>Mallipohjaisen sovelluksen osat ja suunnittelutyökalut
Hyvin suunniteltu mallipohjainen sovellus koostuu useista suunnittelijan valitsemista osista, joilla luodaan lopullisen sovelluksen ulkoasu ja toiminnallisuus. Osista ja niiden ominaisuuksista, joita suunnittelijat käyttävät sovelluksen muodostamiseen, tulee sovelluksen metatietoja. Niiden kunkin osan yhteys sovelluksen suunnitteluun käy selväksi alla olevasta taulukosta, jossa ne on jaettu *tietojen*, *käyttöliittymän*, *logiikan* ja *visualisoinnin* luokkiin. 

### <a name="data"></a>Tiedot
Nämä osat määrittävät, mihin tietoihin sovellus perustuu.



|Osa  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Entiteetti     |Kohde, jossa on ominaisuuksia, joita seurataan, kuten yhteyshenkilö tai tili. Monet vakioentiteetit ovat käytettävissä. Voit mukauttaa järjestelmään kuulumatonta vakioentiteettiä (tuotantoentiteettiä) tai luoda mukautetun entiteetin alusta.     | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteettisuunnittelutyökalu        |
|Kenttä     | Ominaisuus, joka liittyy entiteettiin. Kentän määrittää tietotyyppi, joka määrittää tietotyypin, joka voidaan lisätä tai valita. Esimerkkejä ovat teksti, luku, päivämäärä ja aika, valuutta tai haku (luo yhteyden toisen entiteetin kanssa). Kenttiä käytetään yleensä lomakkeiden, näkymien ja hakujen yhteydessä.        | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteettisuunnittelutyökalu   |
|Yhteydet     | Entiteettiyhteydet määrittävät, miten entiteetit voivat liittyä toisiinsa. Yhteystyyppejä ovat 1:N (yksi moneen), N:1 (monta yhteen) ja N:N (monta moneen). Esimerkiksi hakukentän lisääminen entiteettiin luo uuden 1:N-yhteyden kahden entiteetin välille, ja sen avulla voit sijoittaa kyseisen hakukentän lomakkeeseen.   | [!INCLUDE [powerapps](../../includes/powerapps.md)]-entiteettisuunnittelutyökalu        |
|Asetusjoukko-kenttä     | Tämä on erityinen kenttä, jossa annetaan käyttäjän käyttöön joukko esimääritettyjä asetuksia. Kussakin asetuksessa on numeroarvo ja otsikko. Kun kenttä lisätään lomakkeeseen, siinä näkyy ohjausobjekti, jonka avulla käyttäjä voi valita asetuksen.  Asetusjoukkoja on kahdenlaisia: joukkoja, joista käyttäjä voi valita vain yhden asetuksen, ja monivalintaisia joukkoja, joista voidaan valita useita asetuksia.  | [!INCLUDE [powerapps](../../includes/powerapps.md)]-asetusjoukkosuunnittelutyökalu     |

### <a name="ui"></a>Käyttöliittymä
Nämä osat määrittävät, miten käyttäjät ovat yhteydessä sovellukseen. 

|Osa  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Sovellus     | Määrittää sovelluksen perustoiminnot, kuten sovelluksen osat, ominaisuudet, asiakastyypin ja URL-osoitteen.      | Sovelluksen suunnittelutoiminto   |
|Sivustokartta     | Määrittää navigoinnin sovelluksessa.        | Sivustokartan suunnitteluohjelma        |
|Lomake     | Tiedonsyötön kenttiä tietylle entiteetille, joka vastaa entiteetin kohteita, joita organisaatiosi seuraa. Tiedonsyöttökenttiä ovat esimerkiksi kentät, joihin käyttäjät lisäävät tarvittavia tietoja seuratakseen asiakkaan aiempia tilauksia ja pyydettyjen uusintatilausten päivämääriä.        | Lomakkeiden suunnitteluohjelma        |
|Näkymä     | Näkymät määrittävät, miten tietyn entiteetin tietueluettelo näytetään sovelluksessa. Näkymä määrittää näytettävät sarakkeet, niiden leveyden, lajittelutoiminnan ja oletussuodattimet.   |  Näkymän suunnitteluohjelma       |

![Sovelluksen suunnittelutoiminto ja lomakkeiden suunnitteluohjelma](media/model-driven-app-overview/app-and-form-designers.png)

### <a name="logic"></a>Logiikka
Määrittää sovelluksen liiketoimintaprosessit, säännöt ja automaation. [!INCLUDE [powerapps](../../includes/powerapps.md)]-käyttäjät voivat käyttää suunnittelutoimintoa, joka liittyy prosessin tai säännön tyyppiin. 


|Logiikkatyyppi  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Liiketoimintaprosessin työnkulku     | Verkkopohjainen prosessi, joka ohjaa käyttäjät vakioliiketoimintaprosessin läpi. Käytä liiketoimintaprosessin työnkulkua esimerkiksi silloin, kun haluat kaikkien käsittelevän asiakaspalvelupyyntöjä samalla tavalla tai henkilökunnan hankkivan hyväksynnän laskulle ennen tilauksen lähettämistä.        | Liiketoimintaprosessin työnkulun suunnittelutyökalu        |
|Työnkulku     |  Työnkulkujen avulla automatisoidaan liiketoimintaprosesseja ilman käyttöliittymää. Työnkulkujen avulla suunnittelutyökalut käynnistävät automaatioita, jotka eivät edellytä käyttäjän toimia.       | Työnkulun suunnittelutyökalu        |
|Toiminnot    |  Toiminnot ovat prosessityyppi, joiden avulla voit manuaalisesti käynnistää toimintoja, kuten mukautettuja toimintoja, suoraan työnkulusta.       |  Prosessin suunnittelutyökalu       |
|Liiketoimintasääntö     | Käytetään sääntö- tai suosituslogiikan soveltamiseen lomakkeessa, kuten määritettyihin kentän vaatimuksiin, kenttien piilottamiseen tai tietojen varmistamiseen. Sovellussuunnittelijat käyttävät yksinkertaista käyttöliittymää toteuttamaan ja ylläpitämään nopeasti muuttuvia ja yleisesti käytettyjä sääntöjä.         |  Liiketoimintasäännön suunnittelutyökalu       |
|Työnkulku     | Työnkulku on pilvipohjainen palvelu, jonka avulla voidaan luoda automatisoituja työnkulkuja sovellusten ja palveluiden välille esimerkiksi ilmoitusten saamiseksi, tiedostojen synkronoimiseksi ja tietojen keräämiseksi.        | Microsoft Flow        |

![Työnkulun, toiminnon ja liiketoiminnan prosessin kulun suunnittelutyökalut](media/model-driven-app-overview/designer-mash.png)

### <a name="visualizations"></a>Visualisoinnit
Määrittää, millaisia tietojen visualisointeja ja raportointeja sovelluksella on käytettävissään.


|Osa  |Kuvaus  |Suunnittelutyökalu  |
|---------|---------|---------|
|Kaavio     | Yksittäinen graafinen visualisointi, joka voidaan näyttää näkymässä tai lomakkeessa tai lisätä koontinäyttöön.        | Kaavion suunnitteluohjelma        |
|Koontinäyttö     | Toimii yhden tai usean graafisen visualisoinnin palettina, joka näyttää yleiskatsauksen toimintoa vaativista yritystiedoista.        | Raporttinäkymät-ikkunan suunnittelusovellus        |
|Upotettu Power BI     | Lisää sovellukseen upotettuja Power BI -ruutuja ja koontinäyttöjä. Power BI on pilvipohjainen palvelu, joka tarjoaa liiketoimintatietoa.        |  Kaavion suunnitteluohjelman, raporttinäkymät-ikkunan suunnittelusovelluksen ja Power BI:n yhdistelmä       |

![Esimerkkikoontinäyttö](media/model-driven-app-overview/dashboard-designer.png)

### <a name="advanced-model-driven-app-making"></a>Kehittynyttä mallipohjaisten sovellusten suunnittelua
Ratkaisunhallinta on kattava työkalu, jota käytetään mallipohjaisten sovellusten kehittyneeseen muodostamiseen. Ratkaisunhallinnassa voi liikkua työkalun vasemmalla puolella olevan siirtymisruudun avulla hierarkiassa, joka koostuu kaikista sovelluksen osista.

![Ratkaisunhallinta](media/model-driven-app-overview/solutionexplorer-entitiescollapsed.png)

Avaa ratkaisunhallinta valitsemalla [!INCLUDE [powerapps](../../includes/powerapps.md)]vasemmanpuoleisessa ruudussa **Malliin perustuva**.

  ![Valitse Malliin perustuva](media/model-driven-app-overview/app-type-picker-mod.png)

Valitse sitten **Lisäasetukset**-välilehti. 

## <a name="model-driven-app-development-resources"></a>Mallipohjaisten sovellusten kehitysresurssit
Saat lisätietoja mallipohjaisten sovellusten kehittämisestä näistä ohjeaiheista.
### <a name="modeling-your-data"></a>Tietojen mallintaminen
- [Suunnittele mukautettuja yrityssovelluksia sovelluksen suunnittelutoiminnolla](https://docs.microsoft.com/dynamics365/customer-engagement/customize/design-custom-business-apps-using-app-designer)
- [Luo ja suunnittele lomakkeita](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-design-forms)
- [Luo tai muokkaa näkymiä](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-views)  

### <a name="modeling-and-composing-your-app"></a>Sovelluksen mallinnus ja muodostaminen
- [Luo tai muokkaa entiteettejä](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entities)
- [Luo ja muokkaa yhteyksiä](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-entity-relationships) 
- [Luo ja muokkaa kenttiä](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-fields)
- [Luo ja muokkaa yleisiä asetusjoukkoja](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-global-option-sets)

### <a name="working-with-business-logic"></a>Työskenteleminen liiketoimintalogiikan parissa
- [Liiketoimintaprosessin työnkulkujen yleiskatsaus](https://docs.microsoft.com/dynamics365/customer-engagement/customize/business-process-flows-overview)
- [Työnkulkuprosessien käyttö prosessien automatisointiin](https://docs.microsoft.com/dynamics365/customer-engagement/customize/workflow-processes)
- [Toimintojen yleiskatsaus](https://docs.microsoft.com/dynamics365/customer-engagement/customize/actions)
- [Luo liiketoimintasääntöjä ja suosituksia logiikan soveltamiseksi](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-business-rules-recommendations-apply-logic-form)

### <a name="using-visualizations-in-your-app"></a>Visualisointien käyttö sovelluksessa
- [Luo tai muokkaa järjestelmäkaavioita](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-system-chart)
- [Luo tai muokkaa koontinäyttöjä](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-edit-dashboards)


### <a name="distributing-your-app"></a>Sovelluksen jakaminen
[Ratkaisun luominen](https://docs.microsoft.com/dynamics365/customer-engagement/customize/create-solution)

## <a name="next-steps"></a>Seuraavat vaiheet
[Pika-aloitusopas: Mukautetun entiteetin luominen](../common-data-service/data-platform-create-entity.md)

[Opetusohjelma: Luo osia sisältävä mukautettu entiteetti PowerAppsissa](../common-data-service/create-custom-entity.md)

