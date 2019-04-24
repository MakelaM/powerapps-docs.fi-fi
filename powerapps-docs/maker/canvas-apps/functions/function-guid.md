---
title: GUID-funktio | Microsoft Docs
description: PowerAppsin GUID-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/14/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9415ab67b93ef64f5caa025af5ac685ca2363305
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61563107"
---
# <a name="guid-function-in-powerapps"></a>PowerAppsin GUID-funktio
Muuntaa GUID ([Globally Unique Identifier](https://en.wikipedia.org/wiki/Universally_unique_identifier)) -merkkijonon GUID-arvoksi tai luo uuden GUID-arvon.

## <a name="description"></a>Kuvaus
**GUID**-funktiolla muunnetaan GUID-tunnuksen heksadesimaalimuotoisen esityksen sisältävä merkkijono GUID-arvoksi, joka voidaan välittää tietokantaan. GUID-arvoja käytetään avaimet tietokannan järjestelmien, kuten Common Data Service-ja SQL Server.

Välitetty merkkijono voi sisältää isoja tai pieniä kirjaimia. Siinä on oltava 32 heksadesimaalimerkkiä jommassakummassa seuraavista muodoista:

- **123e4567-e89b-12d3-a456-426655440000** (väliviivat vakiopaikoissaan)
- **123e4567e89b12d3a456426655440000** (ilman väliviivoja)

Jos et määritä argumenttia, tämä funktio luo uuden GUID-tunnuksen.

GUID-arvon muuntaminen merkkijonoksi edellyttää vain, että käytät sitä merkkijonon kontekstissa. GUID-arvo muunnetaan heksadesimaalimuotoiseksi merkkijonoksi, joka sisältää väliviivoja ja pieniä kirjaimia. 

Luotaessa uusi GUID-tunnus, tämä funktio käyttää pseudosatunnaislukugeneraattorin satunnaisluvun luoda versiota 4 [IETF RFC 4122](https://www.ietf.org/rfc/rfc4122.txt) GUID-tunnus. Muunnettaessa merkkijonoa GUID-tunnus Tämä funktio tukee hyväksymällä 32 heksadesimaalimerkkinä mitä tahansa merkkijonoa GUID-versiolla.

## <a name="volatile-functions"></a>Muuttuvat funktiot
**GUID-tunnus** on muuttuva funktio, kun sitä käytetään ilman argumenttia. Aina, kun funktiota arvioidaan, se palauttaa eri arvon.  

Kun muuttuvaa funktiota käytetään tietotyönkulun kaavassa, muuttuva funktio palauttaa eri arvon vain arvioitaessa uudelleen kaavaa, jossa se esiintyy. Jos mitään muuta ei muuteta kaavassa, sillä on sama arvo koko sovelluksesi suorittamisen ajan.

Esimerkiksi otsikko-ohjausobjekti, jonka **tekstiominaisuudeksi** on asetettu **GUID()**, ei muutu sovelluksen aktiivisena olon aikana. Erilainen arvo luodaan vain sulkemalla sovellus ja avaamalla se uudelleen.

Funktio arvioidaan uudelleen, jos se on osa kaavaa, jossa jotakin muuta kohtaa on muutettu. Jos asetamme esimerkiksi **otsikko-ohjausobjektin** **tekstiominaisuuden** tähän kaavaan, GUID-tunnus luodaan aina, kun käyttäjä muuttaa **tekstisyöte-ohjausobjektin** arvoa:

**TextInput1.Text & " " & GUID()**

Kun sitä käytetään [käytöskaavassa](../working-with-formulas-in-depth.md), **GUID**-funktiota arvioidaan uudelleen aina arvioitaessa kaavaa. Lisätietoja saat tässä aiheessa myöhempänä olevista esimerkeistä.

## <a name="syntax"></a>Syntaksi
**GUID**( [ *GUIDString* ] )

* *GUIDString* – valinnainen.  Tekstimerkkijono, joka sisältää heksadesimaalimuotoisen esityksen GUID-tunnuksesta. Jos merkkijonoa ei anneta, luodaan uusi GUID-tunnus.

## <a name="examples"></a>Esimerkkejä

#### <a name="basic-usage"></a>Peruskäyttö

Palauta heksadesimaalimerkkijonoon perustuva GUID-arvo seuraavasti:

* **GUID( "0f8fad5b-d9cb-469f-a165-70867728950e" )**

Voit myös antaa GUID-merkkijonon ilman väliviivoja. Tämä kaava palauttaa saman GUID-arvon:

* **GUID( "0f8fad5bd9cb469fa16570867728950e" )**

Tässä kontekstissa määritetään uuden tietokantatietueen **Tila**-kentälle vakiintunut arvo:

* **Patch (tuotteet, oletus (tuotteet), {tila: GUID( "F9168C5E-CEB2-4faa-B6BF-329BF39FA1E4" ) } )**

Et todennäköisesti halua näyttää GUID-tunnuksia käyttäjille, mutta ne voivat auttaa sovelluksen virheenkorjauksessa. Jos haluat näyttää **Tila**-kentän arvon tietueessa, jonka loit edellisessä esimerkissä, määritä **otsikko-ohjausobjektin** **tekstiominaisuudeksi** tämä kaava:

* **First( Products ).Status**

**Otsikko-ohjausobjekti** näyttää: **f9168c5e-ceb2-4faa-b6bf-329bf39fa1e4**.

#### <a name="create-a-table-of-guids"></a>GUID-tunnustaulukon luominen

1. Määritä **[painikeohjausobjektin](../controls/control-button.md)** **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:

    **ClearCollect( NewGUIDs, ForAll( [ 1, 2, 3, 4, 5 ], GUID() ) )**

    Tämä kaava luo yksisarakkeisen taulukon, joka toistetaan viisi kertaa, ja tuloksesi saadaan viisi GUID-tunnusta.

1. Lisää **[tietotaulukko-ohjausobjekti](../controls/control-data-table.md)**, määritä sen **Items**-ominaisuudeksi **NewGUIDs** ja näytä **Arvo**-kenttä.

1. Kun pidät alhaalla Alt-näppäintä, valitse painike napsauttamalla tai napauttamalla sitä.

    Tietotaulukko näyttää GUID-tunnusten luettelon:

    ![Näyttö, jossa näytetään tietotaulukko, jossa on viisi erilaista GUID-arvoa](media/function-guid/guid-collection-1.png)

1. Valitse painike uudelleen, jos haluat näyttää eri GUID-tunnusten luettelon:

    ![Näyttö, jossa näytetään tietotaulukko, jossa on viisi erilaista GUID-arvoa](media/function-guid/guid-collection-2.png)

Luo yksittäinen GUID-tunnus taulukon sijaan tällä kaavalla:

**Set( NewGUID, GUID() )**
