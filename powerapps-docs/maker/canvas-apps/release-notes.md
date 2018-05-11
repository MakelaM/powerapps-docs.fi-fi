---
title: PowerAppsin uudet ominaisuudet | Microsoft Docs
description: PowerApps-päivitykset järjestettynä julkaisupäivän mukaan
documentationcenter: na
author: skjerland
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: canvas
ms.date: 04/23/2018
ms.author: sharik
ms.openlocfilehash: 00b80bd5b9e0953366dd58d6e3b3266ffe7956bd
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="whats-new-in-powerapps"></a>PowerAppsin uudet ominaisuudet
Lisätietoja tunnetuista rajoituksista on artikkelissa [Yleisiä ongelmia ja ratkaisuja](common-issues-and-resolutions.md).


> [!NOTE]
> Julkaisut annetaan tiedoksi muutaman päivän kuluessa. Uudet tai päivitetyt toiminnot eivät ehkä näy heti.

## <a name="announcing-the-business-applications-spring-18-release-notes"></a>Esittelyssä Business Applications -sovellusten kevään 2018 julkaisutiedot

Tutustu Microsoftin yrityssovellusten uusimpiin päivityksiin ja kokoelmaan uusia ominaisuuksia omien sovellusten ja laajennusten kehittämistä varten ympäristössämme. [Lataa kevään 2018 julkaisutiedot-PDF](https://aka.ms/businessappsreleasenotes), joka kattaa Dynamics 365:n, PowerAppsin, Microsoft Flow'n ja Power BI:n.

**Tulossa pian:** Jatkamme julkaisutietojen PDF-tiedostojen päivittämistä sitä mukaa, kun ominaisuudet ovat saatavilla, ja tarjoamme tiedot myös verkkosivullamme.

## <a name="apr-23"></a>23. huhti
* Lataa [liitteet](controls/control-attachments.md) Internet Explorerissa SharePointin mukautetuissa luettelolomakkeissa.

## <a name="apr-9"></a>9. huhti
* Leikkaa (Ctrl + X), kopioi (Ctrl + C) ja liitä (Ctrl + V) komentoja&mdash;, mukaan lukien niiden tyylejä, kaavoja ja ominaisuuksia &mdash;kaikkiin sovelluksiin selaimessa.

## <a name="mar-21"></a>21. maaliskuuta
1. Laadi [mallipohjaisia sovelluksia](../model-driven-apps/model-driven-app-overview.md), joiden lähtökohta on oman organisaatiosi tietomallissa. Sovellus kehitetään keskeisten liiketoimintatietojenne ja -prosessienne perusteella Common Data Service for Appsissa, ja sitä käytetään lomakkeiden, näkymien ja muiden osien mallintamiseen. Mallipohjaiset sovellukset luovat automaattisesti erinomaisen, kaikkiin laitteisiin sopivan käyttöliittymän.
2. [Luo tietokanta](../../administrator/create-database.md) CDS for Appsin uusimmalla versiolla.
3. CDS for Apps sisältää nyt:
    - **Lisää tietotyyppejä**, jotka tukevat monimutkaisempia kohteiden määritelmiä ja tarjoavat monipuolisempia kokemuksia. (Koskee kangas- ja mallipohjaisia sovelluksia.)
    - [Luo ja mukauta kohteita](../common-data-service/data-platform-create-entity.md) CDS for Appsille suoraan PowerApps-sivustosta. **Päivitetty käyttökokemus** sisältää entistä paremman suorituskyvyn, helppokäyttöisemmän käyttöliittymän ja hyödyllisiä ominaisuuksia, kuten yhdenmukaisen asetusjoukkojen luomisen. (Koskee kangas- ja mallipohjaisia sovelluksia.)
    - Luo **palvelinpuolen liiketoimintasääntöjä** CDS for Appsiin syötettyjen tietojen vahvistamista varten. (Koskee kangas- ja mallipohjaisia sovelluksia.)
    - Luo **laskettuja ja koontikenttiä** CDS for Apps -kohteille suoraan PowerApps-sivustosta. (Koskee kangas- ja mallipohjaisia sovelluksia.)  
    - Kehittäjät voivat käyttää CDS for Apps **Software Development Kit** -työkalua (SDK) koodipohjaisten muokkausten luomiseksi CDS for Appsiin.
    - Kehittyneet käyttäjät voivat käyttää CDS for Appsiin tallennettuja tietoja uuden **OData Web API**:n kautta.
    - [Tuo tietoja](../common-data-service/data-platform-cds-newentity-pq.md) CDS for Appsiin **Power Querylla**. Käytä Power Queryä verkossa tietojen tuomiseen suoraan CDS for Appsiin useista lähteistä

## <a name="mar-5"></a>5. maaliskuuta
1. Lisää [liitteitä](controls/control-attachments.md) SharePoint-luetteloihin (ja poista niitä).
2. Avaa ulkoisia [PDF](controls/control-pdf-viewer.md)-tiedostoja selaimessa. (Kokeellinen ominaisuus)

## <a name="feb-12"></a>12. helmikuuta
* Upotetun [videon](controls/control-audio-video.md) ja [äänen](controls/control-audio-video.md) toistovoimakkuuden säätö on nyt sisäinen. Käyttäjien on nyt käytettävä voimakkuuden säätöä voimakkuuden vähentämiseen sen sijaan, että he vaientaisivat toiston napsauttamalla tai napauttamalla painiketta.

## <a name="feb-7"></a>7. helmikuuta
1. Poistettu zoomaus-, kirkkaus- ja kontrastiominaisuudet [kameran](controls/control-camera.md) ja [viivakoodiskannerin](controls/control-barcodescanner.md) ohjausobjekteista.
2. Korjattu ongelma, jossa [tekstinsyötön](controls/control-text-input.md) ohjausobjektien Tyhjennä-painikkeet rajoittavat tilaa, joka on varattu käyttäjän syötettä varten. Tämän korjauksen tuloksena tekstinsyötön ohjausobjektin [Tyhjennä](controls/control-text-input.md#additional-properties)-ominaisuutta tuetaan vain Microsoft Edge- (uusin versio) ja Internet Explorer 11 -selaimissa.
3. Lisätty helppokäyttötoimintojen parannuksia [multimedian](add-images-pictures-audio-video.md) ohjausobjekteihin.

## <a name="jan-31"></a>31. tammikuuta
1. Lisätty tekstitykset [videon](controls/control-audio-video.md) ohjausobjekteihin.
2. Parannettu virheenkäsittelyä [PDF-katseluohjelman](controls/control-pdf-viewer.md) ohjausobjekteissa.

## <a name="jan-18"></a>18. tammikuuta
1. PowerApps for iOS ja PowerApps for Android tukevat nyt Microsoft Authenticator -integrointia.
2. [Yhdistelmäruutu](controls/control-combo-box.md) korvaa [SharePoint-hakuohjausobjektin](sharepoint-lookup-fields.md) lomakkeissa, ja uusi [tietokortti](working-with-cards.md)malli yksittäisen valinnan hakukenttiä varten on PowerApps Studiossa valittuna oletusarvoisesti.
3. [Yhdistelmäruudussa](controls/control-combo-box.md) näet kaikki kohteet pitkänä luettelona parannetussa lukutilassa.
4. Säädä paikallista tietuerajoitusta niin, että [kyselyille, joita ei voi delegoida](delegation-overview.md#non-delegable-limits), tallennetaan korkeintaan 2 000 tietuetta. (Kokeellinen ominaisuus)

## <a name="jan-5"></a>5. tammikuuta
* Toimi suoraan Power BI -raportin tai koontinäytön tietojen perusteella integroimalla [PowerAppsin mukautettu visualisointi (esikatseluversio)](https://powerapps.microsoft.com/blog/powerbi-powerapps-visual/), joka hakee tilannekohtaisia tietoja Power BI -raportista.

## <a name="dec-8"></a>8. joulukuuta
1. [Ehtomallit](working-with-rules.md) sääntöjä varten päättelevät ohjausobjektin yleisiä ominaisuuksia (kuten **teksti** tai **arvo**).
2. Lopeta [**toimintojen määrittämisen** vahvistusikkunan näyttäminen](working-with-rules.md) määritettäessä sääntöjen toimintoja.

## <a name="nov-13"></a>13. marraskuuta
1. Valitse samaan kenttään useita arvoja SharePoint-luetteloissa.
2. [Tarkastele ja lataa liitteitä](controls/control-attachments.md) SharePoint-luetteloissa.
3. [Mukauta SharePoint-luettelolomakkeita](customize-list-form.md) PowerAppsin avulla.

## <a name="nov-10"></a>10. marraskuuta
* [Nimeä sääntöjä uudelleen](working-with-rules.md) sovelluksessa ja näytä säännöt, kun valittu ohjausobjekti on säännön ehto.
