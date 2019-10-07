---
title: Helppokäyttöisten pohjaan perustuvien sovellusten luominen | Microsoft Docs
description: Pohjaan perustuvien sovellusten luominen toimintarajoitteisille ihmisille
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 04/03/2018
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5883e5f091d5454b00aead80a9daf919a2bcfc2c
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994284"
---
# <a name="create-accessible-canvas-apps-in-powerapps"></a>Helppokäyttöisten pohjaan perustuvien sovellusten luominen PowerAppsissa
Helppokäyttöisen pohjaan perustuvan sovelluksen avulla käyttäjät, joilla on näkö-, kuulo- tai muu rajoite, voivat käyttää sovellusta.  Sen lisäksi, että monet valtiot ja organisaatiot edellyttävät näiden sovellusten käyttöä, alla olevien ohjeiden noudattaminen parantaa käytettävyyttä kaikille käyttäjille.

Tarkista **[Helppokäyttöisyyden tarkistuksen](accessibility-checker.md)** avulla mahdolliset helppokäyttötoimintojen ongelmat sovelluksessasi. 

## <a name="layout-and-color"></a>Asettelu ja väri
Terve järki ja yksinkertainen suunnittelu tekevät sovelluksista helpompia käyttää.  Kun teet merkittäviä sovellusmukautuksia, huomioi alla olevat ehdotukset.  PowerApps-teemat ovat oletusarvoisesti helppokäyttöisiä.
- Varmista, että kaikki elementit näkyvät selvästi ja että teksti on riittävän suurta.  Kaiken sisällön tulee olla helposti luettavissa ja ymmärrettävissä paljain silmin.
- Vältä kohteiden näkyvyysominaisuuden käyttöä elementin tuomiseen näkyville.  Jos sinun tarvitsee näyttää jotain ehdollisesti, luo sisältö uuteen näyttöön ja siirry siihen ja takaisin.
- Varmista, että syötteen elementit näytöllä on merkitty. **[AccessibilityLabel](controls/properties-accessibility.md)** -ominaisuus määrittää, mitä näytönlukuohjelma ilmoittaa.
- Jos mukautat värejä, varmista että text:background-ominaisuuden kontrasti on vähintään 4,5:1.  Tätä prosessia helpottavia ohjelmistotyökaluja on saatavilla helposti.
- Varmista, että asettelu noudattaa loogista työnkulkua luettaessa ylhäältä alas ja vasemmalta oikealle.


## <a name="keyboard-support"></a>Näppäimistön tuki
Kun testaat sovelluksen helppokäyttöisyyttä, varmista, että sovellusta voidaan käyttää pelkällä näppäimistöllä ja helppokäyttöisyystilassa iOS- ja Android-käyttöjärjestelmissä ja että siinä voidaan siirtyä, kun näytönlukuohjelma on käytössä.

Varmista näppäimistöllä käyttämistä (näytönlukuohjelmalla tai ilman sitä) varten, että siirryttäessä SARKAIN-näppäimen avulla syöttökenttiin käytetään loogista järjestystä, asettamalla kunkin ohjausobjektin **[TabIndex](controls/properties-accessibility.md)** -ominaisuus:
- Otsikko, kuva, kuvake, muoto-ohjaus objektit – jos ne edustavat vuorovaikutteisia elementtejä (esimerkiksi painikkeita), valitse Tabindeksistä 0; Jos ne ovat koriste-elementtejä tai tekstiä, valitse Tabdex-arvoksi-1.
- Vältä sarkainindeksin asettamista suuremmaksi kuin 0.

## <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
Seuraavat ohjelmistoyhdistelmät ovat tuettuja suosituksia PowerAppsin käyttämiseen näytönlukuohjelmalla:

- **Windows**: Microsoft Edge/Narrator
- **MacOS**: Safari/VoiceOver
- **Android**: PowerApps-sovellus/TalkBack
- **iOS**: PowerApps-sovellus/VoiceOver

Jotta voit varmistaa tyydyttävän käyttökokemuksen näytönlukuohjelman kanssa, suosittelemme seuraavia:

- Varmista, että kaikkien syöteohjausobjektien **[AccessibilityLabel](controls/properties-accessibility.md)** -ominaisuus on asetettu.
- Aseta kuvien **[AccessibilityLabel](controls/properties-accessibility.md)** -ominaisuudeksi sopiva kuvaus.
  - Jos kuvaa ei käytetä painikkeena tai linkkinä (kuvake on vain koristeena) eikä näytönlukuohjelman tule lukea kuvaa, varmista että **[AccessibilityLabel](controls/properties-accessibility.md)** on tyhjä tai että sitä ei ole asetettu.
  - Jos kuvaa tai kuvaketta käytetään painikkeena, aseta **[TabIndex](controls/properties-accessibility.md)** -arvoksi 0 ja **[AccessibilityLabel](controls/properties-accessibility.md)** linkin kuvaukseen.


## <a name="multimedia"></a>Multimedia
Varmista, että kaikissa videoissa on tekstitys ja että käyttäjä voi käyttää kaikkien äänitallenteiden tekstiversiota.  **Video** -ohjaus objekti tukee WebVTT-formaatin suljettua tekstitystä **Closedcaptionsurl** -ominaisuuden kautta.

Huomaa, että näytönlukuohjelman ollessa käytössä **Ajastin** ei ilmoita painikkeen tekstiä vaan kuluneen ajan.  Ilmoituksia ei voi poistaa käytöstä, vaikka ajastin olisi piilotettu pienellä peittävyydellä.

## <a name="working-with-signatures"></a>Allekirjoitusten käsitteleminen
Jos sinulla on allekirjoituskenttä, jossa käytetään PenInput-ohjausobjektia, sinun on otettava käyttöön vaihtoehtoinen tapa syöttää allekirjoitus.  Suositeltu tapa on näyttää TextInput-ohjausobjekti, jossa käyttäjä voi kirjoittaa nimensä.  Varmista, että allekirjoitusohjeet on asetettu **[AccessibilityLabel](controls/properties-accessibility.md)** -ominaisuuteen ja että ohjausobjekti on asetettu lähelle kynäsyötettä – joko sen oikealle puolelle tai suoraan alle.



Aiheeseen liittyvää:
- [Helppokäyttöisyysasetukset](controls/properties-accessibility.md)
- [Helppokäyttöisyyden tarkistuksen käyttäminen](accessibility-checker.md)
- [Helppokäyttöisyysvärit PowerAppsissa](accessible-apps-color.md)
