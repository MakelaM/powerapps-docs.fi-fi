---
title: Funktiot EditForm, NewForm, SubmitForm, ResetForm ja ViewForm | Microsoft Docs
description: PowerAppsin funktioiden EditForm, NewForm, SubmitForm, ResetForm ja ViewForm viitetiedot, mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 07/06/2017
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 20515a65a66dc3fea1236924d9c29574f63e16a8
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992696"
---
# <a name="editform-newform-submitform-resetform-and-viewform-functions-in-powerapps"></a>PowerAppsin funktiot EditForm, NewForm, SubmitForm, ResetForm ja ViewForm
Tarkastele ja muokkaa kohdetta, luo kohde, tallenna sisältö ja palauta ohjausobjektit **[Muokkaa lomaketta](../controls/control-form-detail.md)** -ohjausobjektissa.

## <a name="overview"></a>Yleiskatsaus
Nämä funktiot muuttavat **Muokkaa lomaketta** -ohjausobjektin tilaa.  Lomakeohjausobjekti on jossain seuraavista tiloista:

| Tila | Kuvaus |
| --- | --- |
| **FormMode.Edit** |Lomake on täytetty olemassa olevalla tietueella ja käyttäjä voi muokata kenttien arvoja.  Kun käyttäjä on valmis, hän voi tallentaa muutokset tietueeseen. |
| **FormMode.New** |Lomake on täytetty oletusarvoilla ja käyttäjä voi muokata kenttien arvoja.  Kun käyttäjä on valmis, hän voi lisätä tietueen tietolähteeseen. |
| **FormMode.View** |Lomake on täytetty olemassa olevalla tietueella, mutta käyttäjä ei voi muokata kenttien arvoja. |

## <a name="description"></a>Kuvaus
Nämä funktiot käynnistetään usein **[Painike](../controls/control-button.md)** - tai **[Kuva](../controls/control-image.md)** -ohjausobjektin **[OnSelect](../controls/properties-core.md)** -kaavalla, jolloin käyttäjä voi tallentaa tai hylätä muutokset tai luoda tietueen. Voit myös luoda kokonaisvaltaisen ratkaisun [käyttämällä ohjausobjekteja ja funktioita yhdessä](../working-with-forms.md).

Nämä funktiot eivät palauta arvoja.

### <a name="submitform"></a>SubmitForm
Tallenna Lomake-ohjausobjektiin tehdyt muutokset tietolähteeseen käyttämällä **SubmitForm**-funktiota Painike-ohjausobjektin **[OnSelect](../controls/properties-core.md)** -ominaisuudessa.

Ennen kuin funktio lähettää muutokset, se tarkistaa mahdolliset vahvistusongelmat pakolliseksi merkityissä kentissä ja kentissä, joiden arvolla on vähintään yksi rajoitus. Toiminta vastaa **[Validate](function-validate.md)** -funktiota.

**SubmitForm** tarkistaa myös lomakkeen **[Valid](../controls/control-form-detail.md)** -ominaisuuden. Se on kooste kaikista **[Kortti](../controls/control-card.md)** -ohjausobjektien **[Valid](../controls/control-card.md)** -ominaisuuksista, jotka Lomake-ohjausobjekti sisältää. Jos ongelma ilmenee, tietoja ei lähetetä ja Lomake-ohjausobjektin **[Error](../controls/control-form-detail.md)** - ja **[ErrorKind](../controls/control-form-detail.md)** -ominaisuudet määritetään vastaavasti.

Jos vahvistus menee läpi, **SubmitForm** lähettää muutoksen tietolähteeseen.

* Jos tämä onnistuu, lomakkeen **[OnSuccess](../controls/control-form-detail.md)** -toiminta suoritetaan ja **[Error](../controls/control-form-detail.md)** - sekä **[ErrorKind](../controls/control-form-detail.md)** -ominaisuudet tyhjennetään.  Jos lomake oli **FormMode.New**-tilassa, se palautetaan **FormMode.Edit**-tilaan.
* Jos muutoksen tallentaminen ei onnistu, lomakkeen **[OnFailure](../controls/control-form-detail.md)** -toiminta suoritetaan ja **[Error](../controls/control-form-detail.md)** - sekä **[ErrorKind](../controls/control-form-detail.md)** -ominaisuudet määritetään vastaavasti.  Lomakkeen tila ei muutu.  

### <a name="editform"></a>EditForm
**EditForm**-funktio muuttaa lomakeohjausobjektin tilaksi **FormMode.Edit**. Tässä tilassa lomake täytetään Lomake-ohjausobjektin **[Item](../controls/control-form-detail.md)** -ominaisuuden sisällöllä.  Jos **SubmitForm**-funktio suoritetaan, kun lomake on tässä tilassa, tietuetta muutetaan, ei luoda.  Lomake-ohjausobjektin oletusarvo on **FormMode.Edit**.

### <a name="newform"></a>NewForm
**NewForm**-funktio muuttaa Lomake-ohjausobjektin tilaksi **FormMode.New**. Tässä tilassa Lomake-ohjausobjektin **[Item](../controls/control-form-detail.md)** -ominaisuuden sisältö ohitetaan. Lomake täytetään sen **[DataSource](../controls/control-form-detail.md)** -ominaisuuden oletusarvoilla. Jos **SubmitForm**-funktio suoritetaan, kun lomake on tässä tilassa, tietue luodaan, sitä ei muuteta.

### <a name="resetform"></a>ResetForm
**ResetForm**-funktio palauttaa lomakkeen sisällön sen alkuarvoihin, jotka edelsivät käyttäjän tekemiä muutoksia. Jos lomake on **FormMode.New**-tilassa, se palautetaan **FormMode.Edit**-tilaan. Myös Lomake-ohjausobjektin **[OnReset](../controls/control-form-detail.md)** -toiminta suoritetaan.  Voit myös palauttaa yksittäisiä ohjausobjekteja **[Reset](function-reset.md)** -funktiolla, mutta vain lomakkeen kautta.

### <a name="viewform"></a>ViewForm
**ViewForm**-funktio muuttaa lomakeohjausobjektin tilaksi **FormMode.View**. Tässä tilassa lomake täytetään Lomake-ohjausobjektin **[Item](../controls/control-form-detail.md)** -ominaisuuden sisällöllä.  **Submitform** -ja **resetform** -funktioilla ei ole vaikutusta tässä tilassa.

### <a name="displaymode-property"></a>DisplayMode-ominaisuus
Nykyinen tila voidaan lukea **Mode**-ominaisuuden kautta.  Tila myös määrittää **DisplayMode**-ominaisuuden arvon, jota tietokortit ja ohjausobjektit voivat käyttää Lomake-ohjausobjektissa.  Tieto kortin **DisplayMode** -ominaisuuden arvoksi asetetaan usein **Parent. DisplayMode** (viittaa lomakkeeseen), kuten ohjaus objektin **DisplayMode** -ominaisuus (tieto korttiin viittaava): 

| Tila | DisplayMode | Kuvaus |
| --- | --- | --- |
| **FormMode.Edit** |**DisplayMode.Edit** |Tietokortit ja ohjausobjektit ovat muokattavissa ja valmiit hyväksymään muutoksia tietueeseen. |
| **FormMode.New** |**DisplayMode.Edit** |Tietokortit ja ohjausobjektit ovat muokattavissa ja valmiit hyväksymään uuden tietueen. |
| **FormMode.View** |**DisplayMode.View** |Tietokortit ja ohjausobjektit eivät ole muokattavissa vaan optimoituja tarkastelemista varten. |

## <a name="syntax"></a>Syntaksi
**SubmitForm**( *FormName* )

* *FormName* – Pakollinen. Lomake-ohjausobjekti tietolähteeseen lähettämiseen.

**EditForm**( *FormName* )

* *FormName* – Pakollinen.  Lomake-ohjausobjekti **FormMode.Edit**-tilaan vaihtamiseen.

**NewForm**( *FormName* )

* *FormName* – Pakollinen. Lomake-ohjausobjekti **FormMode.New**-tilaan vaihtamiseen.

**ResetForm**( *FormName* )

* *FormName* – Pakollinen. Lomake-ohjausobjekti alkuarvojen palauttamiseen. Vaihtaa myös lomakkeen **FormMode.New**-tilasta **FormMode.Edit**-tilaan.

**ViewForm**( *FormName* )

* *FormName* – Pakollinen.  Lomake-ohjausobjekti **FormMode.View**-tilaan vaihtamiseen.

## <a name="examples"></a>Esimerkkejä
Täydellisiä esimerkkejä löytyy kohdasta [Tutustu tietolomakkeisiin](../working-with-forms.md).

1. Lisää Painike-ohjausobjekti, määritä sen **[Teksti](../controls/properties-core.md)** -ominaisuus näyttämään **Tallenna** ja määritä sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:
   
    **SubmitForm (EditForm)**
2. Määritä lomakeohjausobjektin **[OnFailure](../controls/control-form-detail.md)** -ominaisuudeksi tyhjä ja sen **[OnSuccess](../controls/control-form-detail.md)** -ominaisuudeksi tämä kaava:
   
    **Back()**
3. Nimeä **[Selite](../controls/control-text-box.md)** -ohjausobjektin **ErrorText** ja määritä sen **[Teksti](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:
   
    **EditForm.Error**
   
    Kun käyttäjä valitsee **Tallenna**-painikkeen, kaikki Lomake-ohjausobjektiin tehdyt muutokset lähetetään pohjana olevaan tietolähteeseen.
   
   * Jos lähetys onnistuu, muutokset tallentuvat, mutta jos Lomake-ohjausobjekti on **Uusi**-tilassa, luodaan tietue. **ErrorText** on *tyhjä* ja edellinen näyttö tulee näkyviin uudelleen.
   * Jos lähetys epäonnistuu, **ErrorText** näyttää käyttäjäystävällisen virhesanoman. Nykyinen näyttö pysyy näkyvissä, jotta käyttäjä voi korjata ongelman ja yrittää uudelleen.
4. Lisää Painike-ohjausobjekti, määritä sen **[Teksti](../controls/properties-core.md)** -ominaisuus näyttämään **Peruuta** ja määritä sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:
   
    **ResetForm (EditForm); Back()**
   
    Kun käyttäjä valitsee **Peruuta**-painikkeen, Lomake-ohjausobjektin arvot palautetaan muokkausta edeltävään tilaan. Edellinen näyttö tulee näkyviin uudelleen ja Lomake-ohjausobjekti palautetaan **Muokkaa**-tilaan, jos se oli **Uusi**-tilassa.
5. Lisää painikeohjausobjekti, määritä sen **[Teksti](../controls/properties-core.md)** -ominaisuus näyttämään **Uusi** ja määritä sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi tämä kaava:
   
    **NewForm( EditForm ); Navigate( EditScreen, None )**
   
    Kun käyttäjä valitsee **Uusi**-painikkeen, Lomake-ohjausobjekti vaihtuu **Uusi**-tilaan. Lomake-ohjausobjekti täytetään sen tietolähteen oletusarvoilla, ja näkyviin tulee näyttö, joka sisältää Lomake-ohjausobjektin. Kun **SubmitForm**-funktio suoritetaan, tietue luodaan päivittämisen sijaan.

