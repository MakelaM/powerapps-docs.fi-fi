---
title: Funktiot EditForm, NewForm, SubmitForm, ResetForm ja ViewForm | Microsoft Docs
description: PowerAppsin funktioiden EditForm, NewForm, SubmitForm, ResetForm ja ViewForm viitetiedot, mukaan lukien syntaksi ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: gregli-msft
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 07/06/2017
ms.author: gregli
ms.openlocfilehash: 7e64426cfee2b72cd8fda51b889b99b285147fcc
ms.sourcegitcommit: 33099e6197c0139679cd08c42e9e2a5717904c92
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/12/2018
---
# <a name="editform-newform-submitform-resetform-and-viewform-functions-in-powerapps"></a>PowerAppsin funktiot EditForm, NewForm, SubmitForm, ResetForm ja ViewForm
Tarkastele, muokkaa tai luo kohde, tallenna sisältö ja palauta ohjausobjektit **[Muokkaa lomaketta](../controls/control-form-detail.md)** -ohjausobjektissa.

## <a name="overview"></a>Yleiskatsaus
Nämä funktiot muuttavat **Muokkaa lomaketta** -ohjausobjektin tilaa.  Lomakeohjausobjekti on jossain seuraavista tiloista:

| Tila | Kuvaus |
| --- | --- |
| **FormMode.Edit** |Lomake on täytetty olemassa olevalla tietueella ja käyttäjä voi muokata kenttien arvoja.  Kun käyttäjä on valmis, hän voi tallentaa muutokset tietueeseen. |
| **FormMode.New** |Lomake on täytetty oletusarvoilla ja käyttäjä voi muokata kenttien arvoja.  Kun käyttäjä on valmis, hän voi lisätä tietueen tietolähteeseen. |
| **FormMode.View** |Lomake on täytetty olemassa olevalla tietueella, mutta käyttäjä ei voi muokata kenttien arvoja. |

## <a name="description"></a>Kuvaus
Nämä funktiot käynnistetään usein **[painike](../controls/control-button.md)**- tai **[kuva](../controls/control-image.md)** ohjausobjektin **[OnSelect](../controls/properties-core.md)**-kaavalla, jolloin käyttäjä voi tallentaa tai hylätä muutokset tai luoda tietueen. Voit myös luoda kokonaisvaltaisen ratkaisun [käyttämällä ohjausobjekteja ja funktioita yhdessä](../working-with-forms.md).

Nämä funktiot eivät palauta arvoja.

### <a name="submitform"></a>SubmitForm
Tallenna lomakeohjausobjektiin tehdyt muutokset tietolähteeseen käyttämällä **SubmitForm**-funktiota painikeohjausobjektin **[OnSelect](../controls/properties-core.md)**-ominaisuudessa.

Ennen kuin funktio lähettää muutokset, se tarkistaa mahdolliset vahvistusongelmat pakolliseksi merkityissä kentissä ja kentissä, joiden arvolla on vähintään yksi rajoitus. Toiminta vastaa **[Validate](function-validate.md)**-funktiota.

**SubmitForm** tarkistaa myös lomakkeen **[Valid](../controls/control-form-detail.md)**-ominaisuuden. Se on kooste kaikista **[Card](../controls/control-card.md)**-ohjausobjektien **[Valid](../controls/control-card.md)**-ominaisuuksista, jotka lomakeohjausobjekti sisältää. Jos ongelma ilmenee, tietoja ei lähetetä ja lomakeohjausobjektin **[Error](../controls/control-form-detail.md)**- ja **[ErrorKind](../controls/control-form-detail.md)**-ominaisuudet määritetään vastaavasti.

Jos vahvistus menee läpi, **SubmitForm** lähettää muutoksen tietolähteeseen.

* Jos tämä onnistuu, lomakkeen **[OnSuccess](../controls/control-form-detail.md)**-toiminta suoritetaan ja **[Error](../controls/control-form-detail.md)**- sekä **[ErrorKind](../controls/control-form-detail.md)**-ominaisuudet tyhjennetään.  Jos lomake oli **FormMode.New**-tilassa, se palautetaan **FormMode.Edit**-tilaan.
* Jos muutoksen tallentaminen ei onnistu, lomakkeen **[OnFailure](../controls/control-form-detail.md)**-toiminta suoritetaan ja **[Error](../controls/control-form-detail.md)**- sekä **[ErrorKind](../controls/control-form-detail.md)**-ominaisuudet määritetään vastaavasti.  Lomakkeen tila ei muutu.  

### <a name="editform"></a>EditForm
**EditForm**-funktio muuttaa lomakeohjausobjektin tilaksi **FormMode.Edit**. Tässä tilassa lomake täytetään lomakeohjausobjektin **[Item](../controls/control-form-detail.md)**-ominaisuuden sisällöllä.  Jos **SubmitForm**-funktio suoritetaan, kun lomake on tässä tilassa, tietuetta muutetaan, ei luoda.  Lomakeohjausobjektin oletusarvo on **FormMode.Edit**.

### <a name="newform"></a>NewForm
**NewForm**-funktio muuttaa lomakeohjausobjektin tilaksi **FormMode.New**. Tässä tilassa lomakeohjausobjektin **[Item](../controls/control-form-detail.md)**-ominaisuuden sisältö ohitetaan. Lomake täytetään sen **[DataSource](../controls/control-form-detail.md)**-ominaisuuden oletusarvoilla. Jos **SubmitForm**-funktio suoritetaan, kun lomake on tässä tilassa, tietue luodaan, sitä ei muuteta.

### <a name="resetform"></a>ResetForm
**ResetForm**-funktio palauttaa lomakkeen sisällön sen alkuarvoihin, jotka edelsivät käyttäjän tekemiä muutoksia. Jos lomake on **FormMode.New**-tilassa, se palautetaan **FormMode.Edit**-tilaan. Myös lomakeohjausobjektin **[OnReset](../controls/control-form-detail.md)**-toiminta suoritetaan.  Voit myös palauttaa yksittäisiä ohjausobjekteja **[Reset](function-reset.md)**-funktiolla, mutta vain lomakkeen kautta.

### <a name="viewform"></a>ViewForm
**ViewForm**-funktio muuttaa lomakeohjausobjektin tilaksi **FormMode.View**. Tässä tilassa lomake täytetään lomakeohjausobjektin **[Item](../controls/control-form-detail.md)**-ominaisuuden sisällöllä.  **SubmitForm**- ja **RestForm**-funktioilla ei ole tässä tilassa vaikutusta.

### <a name="displaymode-poperty"></a>DisplayMode-ominaisuus
Nykyinen tila voidaan lukea **Mode**-ominaisuuden kautta.  Tila myös määrittää **DisplayMode**-ominaisuuden arvon, jota tietokortit ja ohjausobjektit voivat käyttää lomakeohjausobjektissa.  Usein tietokortin **DisplayMode**-ominaisuuden arvoksi määritetään **Parent.DisplayMode** (viittaa lomakkeeseen), samoin kuin ohjausobjektin **DisplayMode**-ominaisuus (viittaa tietokorttiin): 

| Tila | DisplayMode | Kuvaus |
| --- | --- | --- |
| **FormMode.Edit** |**DisplayMode.Edit** |Tietokortit ja ohjausobjektit ovat muokattavissa ja valmiit hyväksymään muutoksia tietueeseen. |
| **FormMode.New** |**DisplayMode.Edit** |Tietokortit ja ohjausobjektit ovat muokattavissa ja valmiit hyväksymään uuden tietueen. |
| **FormMode.View** |**DisplayMode.View** |Tietokortit ja ohjausobjektit eivät ole muokattavissa vaan optimoituja tarkastelemista varten. |

## <a name="syntax"></a>Syntaksi
**SubmitForm**( *FormName* )

* *FormName* – pakollinen. Lomakeohjausobjekti tietolähteeseen lähettämiseen.

**EditForm**( *FormName* )

* *FormName* – pakollinen.  Lomakeohjausobjekti **FormMode.Edit**-tilaan vaihtamiseen.

**NewForm**( *FormName* )

* *FormName* – pakollinen. Lomakeohjausobjekti **FormMode.New**-tilaan vaihtamiseen.

**ResetForm**( *FormName* )

* *FormName* – pakollinen. Lomakeohjausobjekti alkuarvojen palauttamiseen. Vaihtaa myös lomakkeen **FormMode.New**-tilasta **FormMode.Edit**-tilaan.

**ViewForm**( *FormName* )

* *FormName* – pakollinen.  Lomakeohjausobjekti **FormMode.View**-tilaan vaihtamiseen.

## <a name="examples"></a>Esimerkkejä
Täydellisiä esimerkkejä löytyy kohdasta [Tietolomakkeiden ymmärtäminen](../working-with-forms.md).

1. Lisää painikeohjausobjekti, määritä sen **[Text](../controls/properties-core.md)**-ominaisuus näyttämään **Tallenna** ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **SubmitForm (EditForm)**
2. Määritä lomakeohjausobjektin **[OnFailure](../controls/control-form-detail.md)**-ominaisuudeksi tyhjä ja sen **[OnSuccess](../controls/control-form-detail.md)** -ominaisuudeksi tämä kaava:
   
    **Back()**
3. Nimeä **[Selite](../controls/control-text-box.md)**-ohjausobjektin **ErrorText** ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **EditForm.Error**
   
    Kun käyttäjä valitsee **Tallenna**-painikkeen, kaikki lomakeohjausobjektiin tehdyt muutokset lähetetään pohjana olevaan tietolähteeseen.
   
   * Jos lähetys onnistuu, muutokset tallentuvat, mutta jos lomakeohjausobjekti on **New**-tilassa, luodaan tietue. **ErrorText** on *tyhjä* ja edellinen näyttö tulee näkyviin uudelleen.
   * Jos lähetys epäonnistuu, **ErrorText** näyttää käyttäjäystävällisen virhesanoman. Nykyinen näyttö pysyy näkyvissä, jotta käyttäjä voi korjata ongelman ja yrittää uudelleen.
4. Lisää painikeohjausobjekti, määritä sen **[Text](../controls/properties-core.md)**-ominaisuus näyttämään **Peruuta** ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **ResetForm (EditForm); Back()**
   
    Kun käyttäjä valitsee **Peruuta**-painikkeen, lomakeohjausobjektin arvot palautetaan muokkausta edeltävään tilaan. Edellinen näyttö tulee näkyviin uudelleen ja lomakeohjausobjekti palautetaan **Edit**-tilaan, mikäli se oli **New**-tilassa.
5. Lisää painikeohjausobjekti, määritä sen **[Text](../controls/properties-core.md)**-ominaisuus näyttämään **Uusi** ja määritä sen **[OnSelect](../controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   
    **NewForm( EditForm ); Navigate( EditScreen, None )**
   
    Kun käyttäjä valitsee **Uusi**-painikkeen, lomakeohjausobjekti vaihtuu **New**-tilaan. Lomakeohjausobjekti täytetään sen tietolähteen oletusarvoilla, ja näkyviin tulee näyttö, joka sisältää lomakeohjausobjektin. Kun **SubmitForm**-funktio suoritetaan, tietue luodaan päivittämisen sijaan.

