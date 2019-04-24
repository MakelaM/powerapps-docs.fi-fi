---
title: Select-funktio | Microsoft Docs
description: PowerAppsin Select-funktion viitetiedot, mukaan lukien syntaksi
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/11/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 74584e5855c6c72c619b4baefc2652f9ccc68997
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61520613"
---
# <a name="select-function-in-powerapps"></a>PowerAppsin Select-funktio
Simuloi valintatoiminnon käyttämistä ohjausobjektiin, aiheuttaen **OnSelect**-kaavan laskennan.

## <a name="description"></a>Kuvaus
**Select**-funktio simuloi ohjausobjektin valittua toimintoa aivan kuin käyttäjä olisi klikannut tai napauttanut ohjausobjektia. Tämän vuoksi kohdeohjausobjektin **OnSelect**-kaava lasketaan.

Käytä **Select**-funktiota levittääksesi valittu toiminto pääohjausobjektiin. Tämän tyyppinen välitys on oletusarvon mukaista esimerkiksi valikoimissa. Oletuksena kaikkien **[Valikoima](../controls/control-gallery.md)** -ohjausobjektien **OnSelect**-ominaisuus arvoksi on määritetty **Select( Parent )**. Näin voit määrittää valikoima-ohjausobjektin **OnSelect**-ominaisuuden arvon itse, ja kyseinen kaava lasketaan riippumatta siitä, missä kohtaa valikoimaa käyttäjä on klikannut tai napauttanut.

Jos haluat yhden tai useamman valikoima-ohjausobjektin suorittavan eri toimintoja itse valikoimasta, aseta niiden **OnSelect** -ominaisuuden arvoksi muu kuin oletusarvo. Voit jättää useimpien valikoima-ohjausobjektien **OnSelect**-ominaisuuden arvoksi oletusarvon, jos haluat niiden suorittavan saman toiminnon kuin itse valikoima.

**Select** laittaa **OnSelect**-kohteen jonoon myöhempää käsittelyä varten, joka voi tapahtua sen jälkeen, kun nykyisen kaavan laskeminen on lopetettu. **Select** ei aiheuta **OnSelect**-kohteen välitöntä laskemista, eikä **Select** myöskään odota, että **OnSelect** lopettaa laskemisen.

**Select** ei voi ylittää säilöohjausobjektin, kuten valikoiman tai muodon, rajoja. Säilöohjausobjektin ohjausobjektit voivat olla vain **Select**-funktion aihe kaavoissa, jotka ovat saman säilöohjausobjektin sisällä. Et voi käyttää **Select**-funktiota kaikissa näytöissä.

Voit käyttää **Select**-funktiota vain ohjausobjekteissa, joissa on **OnSelect**-ominaisuus.

Voit käyttää **Select**-funktiota vain [toimintakaavoissa](../working-with-formulas-in-depth.md).

Ohjausobjekti ei voi **Valita** itseään suoraan tai epäsuorasti muiden ohjausobjektien kautta.

## <a name="syntax"></a>Syntaksi
**Select**( *Control* )

* *Control* – Pakollinen.  Ohjausobjektin valinta käyttäjän puolesta.

## <a name="examples"></a>Esimerkkejä

#### <a name="basic-usage"></a>Peruskäyttö

1. Lisää **[painike](../controls/control-button.md)** -ohjausobjekti ja nimeä se nimellä **Button1**, jos sillä on eri nimi.

1. Määritä **Button1:n** **OnSelect**-ominaisuudeksi tämä kaava:

    **Notify( ”Hei maailma” )**

1. Lisää samassa ruudussa toinen **Painike**-ohjausobjekti ja määritä sen **OnSelect**-ominaisuudeksi tämä kaava:

    **Valitse ( Button1 )**

1. Pidät Alt-näppäintä pohjassa ja valitse toinen painike.

    Sovelluksesi yläreunaan tulee ilmoitus. **Button1:n** **OnSelect**-ominaisuus loi tämän ilmoituksen.

    ![Esitettävä animaatio näyttää OnSelect-ominaisuusasetukset kahdelle painikkeelle ja ilmoituksen, kun toista painiketta napsautetaan](media/function-select/basic-select.gif)

#### <a name="gallery-control"></a>Valikoima-ohjausobjekti

1. Lisää pystysuora **[Valikoima](../controls/control-gallery.md)**-ohjausobjekti, joka sisältää muita ohjausobjekteja.

    ![Valitse pystysuora valikoima, joka sisältää ohjausobjekteja](media/function-select/select-gallery.png)

2. Määritä valikoiman **OnSelect**-ominaisuudeksi tämä kaava:
 
    **Notify( ”Valikoima valittu” )**

3. Pidä Alt-näppäintä pohjassa, napsauta tai napauta valikoiman taustaa tai mitä tahansa valikoima-ohjausobjektia.

    Kaikki toiminnot näyttävät **Valikoima valittu** -ilmoituksen sovelluksen yläreunassa.

    Käytä valikoiman **OnSelect**-ominaisuutta määrittääksesi oletusarvoisen toiminnon, joka suoritetaan, kun käyttäjä napsauttaa tai napauttaa kohdetta valikoimassa.

5. Määritä kuvanhallinnan **OnSelect**-ominaisuudeksi tämä kaava:

    **Notify( ”Kuva valittu”, Onnistui )**

6. Pidä Alt-näppäintä pohjassa, napsauta tai napauta valikoiman eri elementtejä.

    Kun napsautat tai napautat mitä tahansa valikoiman ohjausobjektia, paitsi kuvaa, **Valikoima valittu** -ilmoitus tulee näkyviin. Kun napsautat tai napautat kuvaa, **Kuva valittu** -ilmoitus tulee näkyviin.
 
    Käytä valikoiman yksittäisiä ohjausobjekteja suorittaaksesi toimintoja, jotka eroavat valikoiman oletustoiminnosta.

    ![Esitettävä animaatio näyttää valikoimaohjausobjektin OnSelect-ominaisuuden oletusarvon, sekä ohjausobjektin, joka suorittaa eri toiminnon](media/function-select/gallery-select.gif)
