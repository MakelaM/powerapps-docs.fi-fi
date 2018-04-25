---
title: PowerAppsin uudet ominaisuudet | Microsoft Docs
description: PowerApps-päivitykset järjestettynä julkaisupäivän mukaan
services: powerapps
suite: powerapps
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: sharik
ms.openlocfilehash: e9e5c156e9cb3ad47375be9a237a757a6db1158b
ms.sourcegitcommit: a9d33322228c398d29964429602dc3fe19fa67d2
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/28/2018
---
# <a name="whats-new-in-powerapps"></a>PowerAppsin uudet ominaisuudet
Lisätietoja tunnetuista rajoituksista on artikkelissa [Yleisiä ongelmia ja ratkaisuja](common-issues-and-resolutions.md).


> [!NOTE]
> Julkaisut annetaan tiedoksi muutaman päivän kuluessa. Uudet tai päivitetyt toiminnot eivät ehkä näy heti.

## <a name="announcing-the-business-applications-spring-18-release-notes"></a>Esittelyssä Business Applications -sovellusten kevään 2018 julkaisutiedot

Tutustu Microsoftin yrityssovellusten uusimpiin päivityksiin ja kokoelmaan uusia ominaisuuksia omien sovellusten ja laajennusten kehittämistä varten ympäristössämme. [Lataa kevään 2018 julkaisutiedot-PDF](https://aka.ms/businessappsreleasenotes), joka kattaa Dynamics 365:n, PowerAppsin, Microsoft Flow'n ja Power BI:n.

**Tulossa pian:** Jatkamme julkaisutietojen PDF-tiedostojen päivittämistä sitä mukaa, kun ominaisuudet ovat saatavilla, ja tarjoamme tiedot myös verkkosivullamme.

## <a name="mar-21"></a>21. maaliskuuta
1. Laadi [mallipohjaisia sovelluksia](../model-driven-apps/model-driven-app-overview.md), joiden lähtökohta on oman organisaatiosi tietomallissa. Sovellus kehitetään keskeisten liiketoimintatietojenne ja -prosessienne perusteella Common Data Servicessä, ja sitä käytetään lomakkeiden, näkymien ja muiden osien mallintamiseen. Mallipohjaiset sovellukset luovat automaattisesti erinomaisen, kaikkiin laitteisiin sopivan käyttöliittymän.
2. [Luo tietokanta](../../administrator/create-database.md) ympäristössä käyttämällä Common Data Servicen uusinta versiota.
3. Common Data Service for Apps sisältää nyt:

    - **Lisää tietotyyppejä**, jotka tukevat monimutkaisempia kohteiden määritelmiä ja tarjoavat monipuolisempia kokemuksia. (Koskee kangas- ja mallipohjaisia sovelluksia.)
    - [Luo ja mukauta kohteita](../common-data-service/data-platform-create-entity.md) Common Data Service for Appsille suoraan PowerApps-sivustosta. **Päivitetty käyttökokemus** sisältää entistä paremman suorituskyvyn, helppokäyttöisemmän käyttöliittymän ja hyödyllisiä ominaisuuksia, kuten yhdenmukaisen asetusjoukkojen luomisen. (Koskee kangas- ja mallipohjaisia sovelluksia.)
    - Luo **palvelinpuolen liiketoimintasääntöjä** Common Data Service for Appsiin syötettyjen tietojen vahvistamista varten. (Koskee kangas- ja mallipohjaisia sovelluksia.)
    - Luo **laskettuja ja koontikenttiä** Common Data Service for Apps -kohteille suoraan PowerApps-sivustosta. (Koskee kangas- ja mallipohjaisia sovelluksia.)  
    - Kehittäjät voivat käyttää Common Data Service for Apps **Software Development Kit** -työkalua (SDK) koodipohjaisten muokkausten luomiseksi Common Data Serviceen.
    - Kehittyneet käyttäjät voivat käyttää Common Data Service for Appsiin tallennettuja tietoja uuden **OData Web API**:n kautta.
    - [Tuo tietoja](../common-data-service/data-platform-cds-newentity-pq.md) Common Data Serviceen **Power Queryn** avulla. Käytä Power Queryä verkossa tietojen tuomiseen suoraan Common Data Serviceen useista lähteistä

## <a name="mar-5"></a>5. maaliskuuta
1. Lisää (ja poista) [liitteitä](controls/control-attachments.md) SharePoint-luetteloihin.
2. Avaa ulkoisia [PDF](controls/control-pdf-viewer.md)-tiedostoja selaimessa. (Kokeellinen ominaisuus)

## <a name="feb-12"></a>12. helmikuuta
* Upotetun [videon](controls/control-audio-video.md) ja [äänen](controls/control-audio-video.md) toistovoimakkuuden säätö on nyt sisäinen. Käyttäjien on nyt käytettävä voimakkuuden säätöä voimakkuuden vähentämiseen sen sijaan, että he vaientaisivat toiston napsauttamalla tai napauttamalla painiketta.

## <a name="feb-7"></a>7. helmikuuta
1. Poistettu zoomaus-, kirkkaus- ja kontrastiominaisuudet [kameran](controls/control-camera.md) ja [viivakoodiskannerin](controls/control-barcodescanner.md) ohjausobjekteista.
2. Korjattu ongelma, jossa [tekstinsyötön](controls/control-text-input.md) ohjausobjektien tyhjennä-painikkeet rajoittavat tilaa, joka on varattu käyttäjän syötettä varten. Tämän korjauksen tuloksena tekstinsyötön ohjausobjektin [tyhjennä](controls/control-text-input.md#additional-properties)-ominaisuutta tuetaan vain Microsoft Edge- (uusin versio) ja Internet Explorer 11 -selaimissa.
3. Lisätty helppokäyttötoimintojen parannuksia [multimedian](add-images-pictures-audio-video.md) ohjausobjekteihin.

## <a name="jan-31"></a>31. tammikuuta
1. Lisätty tekstitykset [Videon](controls/control-audio-video.md) ohjausobjekteihin.
2. Parannettu virheenkäsittelyä [PDF-katseluohjelman](controls/control-pdf-viewer.md) ohjausobjekteissa.

## <a name="jan-18"></a>18. tammikuuta
1. PowerApps for iOS ja PowerApps for Android tukevat nyt Microsoft Authenticator -integrointia.
2. [Yhdistelmäruutu](controls/control-combo-box.md) korvaa [SharePoint-hakuohjausobjektin](sharepoint-lookup-fields.md) lomakkeissa, ja uusi [tietokortti](working-with-cards.md)malli yksittäisen valinnan hakukenttiä varten on valittuna oletusarvoisesti PowerApps Studiossa.
3. [Yhdistelmäruudussa](controls/control-combo-box.md) näet kaikki kohteet pitkänä luettelona parannetussa lukutilassa.
4. Säädä paikallista tietuerajoitusta niin, että tallennetaan korkeintaan 2000 tietuetta [kyselyille, joita ei voi delegoida](delegation-overview.md#non-delegable-limits). (Kokeellinen ominaisuus)

## <a name="jan-5"></a>5. tammikuuta
* Toimi suoraan Power BI-raportin tai koontinäytön tietojen perusteella integroimalla [PowerAppsin mukautettu visualisointi (esikatseluversio)](https://powerapps.microsoft.com/blog/powerbi-powerapps-visual/), joka hakee tilannekohtaisia tietoja Power BI-raportista.

## <a name="dec-8"></a>8. joulukuuta
1. [Ehtomallit](working-with-rules.md) sääntöjä varten päättelevät ohjausobjektin yleisiä ominaisuuksia (kuten **teksti** tai **arvo**).
2. Lopeta [**toimintojen määrittämisen** vahvistusikkunan näyttäminen](working-with-rules.md) määritettäessä sääntöjen toimintoja.

## <a name="nov-13"></a>13. marraskuuta
1. Valitse samaan kenttään useita arvoja SharePoint-luetteloissa.
2. [Tarkastele ja lataa liitteitä](controls/control-attachments.md) SharePoint-luetteloissa.
3. [Mukauta SharePoint-luettelolomakkeita](customize-list-form.md) PowerAppsin avulla.

## <a name="nov-10"></a>10. marraskuuta
* [Nimeä sääntöjä uudelleen](working-with-rules.md) sovelluksessa ja näytä säännöt valitun ohjausobjektin ollessa säännön ehto.

## <a name="oct-30"></a>30. lokakuuta
1. [Näytä kaikki säännöt](working-with-rules.md) sovelluksessa, ei ainoastaan niitä, jotka koskevat valittua ohjausobjektia.
2. Lisätty kuvakkeita, joita sovellusten laatijat ovat eniten pyytäneet.
3. Parannettu sovellusten suorituskykyä Android- ja iOS-laitteissa.
