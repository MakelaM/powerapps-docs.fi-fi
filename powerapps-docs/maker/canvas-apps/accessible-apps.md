---
title: Helppokäyttöisten sovellusten luominen | Microsoft Docs
description: Sovellusten luominen toimintarajoitteisille ihmisille
author: fikaradz
ms.service: powerapps
ms.topic: conceptual
ms.component: canvas
ms.date: 04/03/2018
ms.author: fikaradz
ms.openlocfilehash: 8a7139f6dbc39bc1585156802e30236aa2b68359
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803071"
---
# <a name="create-accessible-apps"></a>Helppokäyttöisten sovellusten luominen
Helppokäyttöisen sovelluksen avulla käyttäjät, joilla on näkö-, kuulo- tai muu rajoite, voivat käyttää sovellusta.  Sen lisäksi, että monet valtiot ja organisaatiot edellyttävät näiden sovellusten käyttöä, alla olevien ohjeiden noudattaminen parantaa käytettävyyttä kaikille käyttäjille.

## <a name="layout-and-color"></a>Asettelu ja väri
Terve järki ja yksinkertainen suunnittelu tekevät sovelluksista helpompia käyttää.  Kun teet merkittäviä sovellusmukautuksia, huomioi alla olevat ehdotukset.  PowerApps-teemat ovat oletusarvoisesti helppokäyttöisiä.
- Varmista, että kaikki elementit näkyvät selvästi ja että teksti on riittävän suurta.  Kaiken sisällön tulee olla helposti luettavissa ja ymmärrettävissä paljain silmin.
- Vältä kohteiden näkyvyysominaisuuden käyttöä elementin tuomiseen näkyville.  Jos sinun tarvitsee näyttää jotain ehdollisesti, luo sisältö uuteen näyttöön ja siirry siihen ja takaisin.
- Varmista, että syötteen elementit näytöllä on merkitty. **[AccessibilityLabel](controls/properties-accessibility.md)**-ominaisuus määrittää, mitä näytönlukuohjelma ilmoittaa.
- Jos mukautat värejä, varmista että text:background-ominaisuuden kontrasti on vähintään 4,5:1.  Tätä prosessia helpottavia ohjelmistotyökaluja on saatavilla helposti.
- Varmista, että asettelu noudattaa loogista työnkulkua luettaessa ylhäältä alas ja vasemmalta oikealle.


## <a name="keyboard-support"></a>Näppäimistön tuki
Kun testaat sovelluksen helppokäyttöisyyttä, varmista, että sovellusta voidaan käyttää pelkällä näppäimistöllä ja helppokäyttöisyystilassa iOS- ja Android-käyttöjärjestelmissä ja että siinä voidaan siirtyä, kun näytönlukuohjelma on käytössä.

Varmista näppäimistöllä käyttämistä (näytönlukuohjelmalla tai ilman sitä) varten, että siirryttäessä SARKAIN-näppäimen avulla syöttökenttiin käytetään loogista järjestystä, asettamalla kunkin ohjausobjektin **[TabIndex](controls/properties-accessibility.md)**-ominaisuus:
- Otsikko-, Kuva-, Kuvake- ja Muoto-ohjausobjektit – Jos ne edustavat interaktiivisia elementtejä (painikkeet), aseta TabIndex-arvoksi 0. Jos ne ovat koriste-elementtejä tai tekstiä, aseta TabIndex-arvoksi -1.
- Vältä sarkainindeksin asettamista suuremmaksi kuin 0.

## <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
Seuraavat ohjelmistoyhdistelmät ovat tuettuja suosituksia PowerAppsin käyttämiseen näytönlukuohjelmalla:

- **Windows**: Edge/Narrator
- **macOS**: Safari/VoiceOver
- **Android**: PowerApps-sovellus/Talkback
- **iOS**: PowerApps-sovellus/VoiceOver

Jotta voit varmistaa tyydyttävän käyttökokemuksen näytönlukuohjelman kanssa, suosittelemme seuraavia:

- Varmista, että kaikkien syöteohjausobjektien **[AccessibilityLabel](controls/properties-accessibility.md)**-ominaisuus on asetettu.
- Aseta kuvien **[AccessibilityLabel](controls/properties-accessibility.md)**-ominaisuudeksi sopiva kuvaus.
  - Jos kuvaa ei käytetä painikkeena tai linkkinä (kuvake on vain koristeena) eikä näytönlukuohjelman tule lukea kuvaa, varmista että **[AccessibilityLabel](controls/properties-accessibility.md)** on tyhjä tai että sitä ei ole asetettu.
  - Jos kuvaa tai kuvaketta käytetään painikkeena, aseta **[TabIndex](controls/properties-accessibility.md)**-arvoksi 0 ja **[AccessibilityLabel](controls/properties-accessibility.md)** linkin kuvaukseen.


## <a name="multimedia"></a>Multimedia
Varmista, että kaikissa videoissa on tekstitys ja että käyttäjä voi käyttää kaikkien äänitallenteiden tekstiversiota.  **Video**-ohjausobjekti tukee tekstityksiä WebVTT-muodossa **ClosedCaptionsUrl**-ominaisuuden kautta.

Huomaa, että näytönlukuohjelman ollessa käytössä **Ajastin** ei ilmoita painikkeen tekstiä vaan kuluneen ajan.  Ilmoituksia ei voi poistaa käytöstä, vaikka ajastin olisi piilotettu pienellä peittävyydellä.

## <a name="working-with-signatures"></a>Allekirjoitusten käsitteleminen
Jos sinulla on allekirjoituskenttä, jossa käytetään PenInput-ohjausobjektia, sinun on otettava käyttöön vaihtoehtoinen tapa syöttää allekirjoitus.  Suositeltu tapa on näyttää TextInput-ohjausobjekti, jossa käyttäjä voi kirjoittaa nimensä.  Varmista, että allekirjoitusohjeet on asetettu **[AccessibilityLabel](controls/properties-accessibility.md)**-ominaisuuteen ja että ohjausobjekti on asetettu lähelle kynäsyötettä – joko sen oikealle puolelle tai suoraan alle.



Aiheeseen liittyvää: **[Helppokäyttöisyysasetukset](controls/properties-accessibility.md)**
