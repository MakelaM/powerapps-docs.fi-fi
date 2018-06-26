---
title: Power BI -yhteyden yleiskatsaus | Microsoft Docs
description: Näytä käytettävissä olevat Power BI -yhteydet
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 10/12/2016
ms.author: lanced
ms.openlocfilehash: a3a5d24efffd7cd3c9430cafd5050dc96632ee76
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34803163"
---
# <a name="connect-to-power-bi-from-powerapps"></a>Yhdistä Power BI:hin PowerAppsista
![Power BI](./media/connection-powerbi/powerbiicon.png)

Power BI on liiketoiminta-analytiikkatyökalujen ohjelmapaketti, jolla voi analysoida ja jakaa merkityksellisiä tietoja. Runsastoimintoisten koontinäyttöjen avulla on helppo seurata liiketoimintaa ja löytää vastauksia. Ne ovat saatavilla kaikenlaisiin laitteisiin. Sovelluksessa voit myös tarkistaa Power BI -palvelussa määritettyjen tietohälytysten tilan. Lisätietoja Power BI:n tietohälytyksistä saat [ohjesivulta](https://https://docs.microsoft.com/power-bi/service-set-data-alerts).

Näissä ohjeissa neuvotaan, miten voit käyttää Power BI -yhteyttä sovelluksessa, ja käytettävissä olevat toiminnot luetellaan.

## <a name="prerequisites"></a>Edellytykset
* [Rekisteröidy](https://web.powerapps.com).
* Lisää Power BI -[yhteys](https://powerapps.microsoft.com/tutorials/add-manage-connections/).
* Luo sovellus [mallista](https://powerapps.microsoft.com/tutorials/get-started-test-drive/), [tiedoista](https://powerapps.microsoft.com/tutorials/get-started-create-from-data/) tai itse [alusta alkaen](https://powerapps.microsoft.com/tutorials/get-started-create-from-blank/).

## <a name="use-the-power-bi-connection-in-your-app"></a>Power BI -yhteyden käyttö sovelluksessa
### <a name="list-the-alerts-that-youve-set-up-in-the-power-bi-service"></a>Luettele Power BI -palvelussa määrittämäsi hälytykset
1. Valitse **Lisää**-valikosta **Valikoima** ja lisää mikä tahansa **tekstivalikoima**.
2. Näytä nykyiset käyttäjän hälytykset määrittämällä valikoiman [Items](../controls/properties-core.md)-ominaisuudeksi seuraava kaava:
   
   `PowerBI.GetAlerts()`

Hälytysluettelo päivittyy valikoimaan. Saat tietää jokaisen hälytyksen nimen, tunnuksen ja hälytyksen luoneen ryhmätyötilan tunnuksen. Saat lisätietoja hälytyksestä hälytystunnuksen avulla.

### <a name="view-the-status-of-an-alert"></a>Hälytyksen tilan tarkastelu
Jos haluat nähdä hälytyksen tilan, käynnistä CheckAlertStatus-funktio edellisen kohdan hälytystunnuksella.

Voit syöttää hälytystunnuksen joko sellaisenaan merkkijonona (esim. "1234") tai valikoimaosion viitteenä GetAlerts()-kutsussa (esim. Valikoima1.Selected.alertId)

Jatka lisäämällä otsikko ja määrittämällä [Text](../controls/properties-core.md)-ominaisuudeksi jokin seuraavista kaavoista:

* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).alertTitle`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).currentTileValue`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).alertThreshold`
* `PowerBI.CheckAlertStatus( /* alert ID that you received from GetAlert */ ).isAlertTriggered`

Hälytyksen senhetkinen tila päivittyy otsikkoon.

## <a name="view-the-available-functions"></a>Näytä käytettävissä olevat funktiot
Tämä yhteys sisältää seuraavat funktiot:

| Funktion nimi | Kuvaus |
| --- | --- |
| GetAlerts |Luettele Power BI -palvelussa määrittämäsi hälytykset |
| CheckAlertStatus |Tarkista tietyn hälytyksen tila |

## <a name="getalerts"></a>GetAlerts
Luettele Power BI -palvelussa määrittämäsi hälytykset.

#### <a name="input-properties"></a>Syöteominaisuudet
Ei mitään.

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| arvo |matriisi |Ei |Power BI -palvelussa määrittämiesi tietohälytysten matriisi. Matriisin jokaisen osan sisältö: <ul><li>alertTitle: hälytyksen otsikko</li><li>alertId: hälytyksen tunnus</li><li>groupId: hälytyksen luoneen ryhmän tunnus</li></ul> |

## <a name="checkalertstatus"></a>CheckAlertStatus
Tarkista hälytyksen tila.

> [!NOTE]
> Jos tähän päätepisteeseen tulee pyyntöjä liian usein, ne rajoitetaan hälytyskohtaisiksi.

#### <a name="input-properties"></a>Syöteominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| alertId |kokonaisluku |Kyllä |GetAlertsin palauttama hälytystunnus |

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| tileValue |luku |Ei |Ruudun arvo hälytyksen käynnistyshetkellä |
| tileUrl |merkkijono |Ei |Hälytyksen kohderuudun URL-osoite |
| alertTitle |merkkijono |Ei |Hälytyksen nimi |
| isAlertTriggered |totuusarvo |Ei |Hälytyksen käynnistymisen tila |
| alertThreshold |luku |Ei |Hälytyksen käynnistymisen raja-arvo |

## <a name="helpful-links"></a>Hyödyllisiä linkkejä
Kaikki [käytettävissä olevat yhteydet](../connections-list.md).  
Lue, miten voit [lisätä yhteyksiä](../add-manage-connections.md) sovelluksiisi.

