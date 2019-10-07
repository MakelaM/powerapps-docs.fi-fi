---
title: 'Liiteohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja liiteohjausobjektista, kuten ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 04/23/2018
ms.author: fikaradz
ms.reviewer: tapanm
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: bc46f2a01e76741ccb046f382b0dd2829d23b368
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71987012"
---
# <a name="attachments-control-in-powerapps"></a>Liiteohjausobjekti PowerAppsissa
Ohjaus objekti, jonka avulla käyttäjät voivat ladata tiedostoja laitteiinsa sekä ladata ja poistaa tiedostoja SharePoint-listasta tai Common Data Service-entiteetistä.

## <a name="limitations"></a>Rajoitukset
Liiteohjausobjektilla on seuraavat rajoitukset:
1. Liitteitä tuetaan SharePoint-luetteloissa ja Common Data Service entiteeteissä.

1. Palvelimeen lataamisen ja poistamisen toiminnot toimivat vain lomakkeen sisällä. Liite ohjaus objekti näkyy poissa käytöstä muokkaus tilassa, ei lomakkeen sisällä. Jos haluat tallentaa tiedostojen lisäykset ja poistot, sovelluksen käyttäjän on tallennettava lomake. Tämän rajoituksen vuoksi liite-ohjaus objekti ei ole käytettävissä **Lisää** -väli lehdestä, mutta se näkyy lomakkeessa, kun liite lomake-kenttä on otettu käyttöön SharePointissa tai Common Data Service lomakkeessa.

1. Voit ladata tiedostoja vain, jos ne ovat enintään 10 Mega tavua.  

## <a name="description"></a>Kuvaus
**Liite** ohjaus objektin avulla voit avata, lisätä ja poistaa tiedostoja SharePoint-listasta tai Common Data Service-entiteetistä.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
**[Items](properties-core.md)**  – Ladattavia tiedostoja kuvaava lähde.

**MaxAttachments** – Ohjausobjektin hyväksymien tiedostojen enimmäismäärä.

**MaxAttachmentSize** – Jokaisen uuden liitteen suurin sallittu tiedostokoko megatavuina.  Tällä hetkellä enimmäiskoko on 10 megatavua.

**OnAttach** – Miten sovellus reagoi, kun käyttäjä lisää uuden liitetiedoston.

**OnRemove** – Miten sovellus reagoi, kun käyttäjä poistaa olemassa olevan liitetiedoston.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napsauttaa liitetiedostoa.

## <a name="additional-properties"></a>Lisäominaisuudet
**[AccessibleLabel](properties-accessibility.md)** – Näytönlukuohjelmien nimi. Tulee kuvata liitteiden käyttötarkoituksen.

**AddAttachmentText** – Uuden liitteen lisäämiseen käytetyn linkin nimen teksti.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[FocusedBorderColor](properties-color-border.md)**  – Ohjausobjektin reunan väri, kun ohjausobjekti on kohdistettu.

**[FocusedBorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus, kun ohjausobjekti on kohdistettu.

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**MaxAttachmentsText** – Teksti, joka korvaa Liitä tiedosto -linkin, kun ohjausobjekti sisältää enimmäismäärän sallittuja tiedostoja.

**NoAttachmentsText** – Tiedottava teksti, joka näytetään käyttäjälle, kun tiedostoja ei ole liitetty.

**[TabIndex](properties-accessibility.md)** – Näppäimistön siirtymisjärjestys suhteessa muihin ohjausobjekteihin.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvä vai piilotettu.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).


## <a name="example"></a>Esimerkki
1. Luo sovellus tiedoista käyttämällä SharePoint-luetteloa tietolähteenä. Vaihtoehtoisesti voit lisätä sovellukseesi lomakkeen ja määrittää SharePoint-luettelon sen tietolähteeksi.

2. Valitse **lomake**ohjausobjekti vasemmassa reunassa olevasta puunäkymästä.

3. Napsauta vasemmalla olevan Asetukset-paneelin Ominaisuudet-välilehdeltä **Tiedot**.

4. Ota **Liitteet**-kenttä käyttöön kohdasta **Kentät**.

    SharePoint-luetteloon liittyvä Liitteet-kenttä tulee näkyviin lomakkeeseen.

[Lue, miten voit lisätä ja määrittää ohjausobjektin].(../add-configure-controls.md)


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="color-contrast"></a>Värikontrasti
Seuraavien kohteiden välillä on oltava asianmukainen värikontrasti:
* **ItemColor** ja **ItemFill**
* **ItemHoverColor** ja **ItemHoverFill**
* **ItemPressedColor** ja **ItemPressedFill**
* **AddedItemColor** ja **AddedItemFill**
* **RemovedItemColor** ja **RemovedItemFill**
* **ItemErrorColor** ja **ItemErrorFill**
* **AddAttachmentColor** ja **Täyttö**
* **MaxAttachmentsColor** ja **Täyttö**
* **NoAttachmentsColor** ja **Täyttö**

Tämä tulee [värikontrastin vakiovaatimusten lisäksi](../accessible-apps-color.md).

### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
Seuraavat ominaisuudet on oltava käytössä:
* **[AccessibleLabel](properties-accessibility.md)**
* **AddAttachmentsText**
* **MaxAttachmentsText**
* **NoAttachmentsText**

### <a name="keyboard-support"></a>Näppäimistön tuki
* **[TabIndex](properties-accessibility.md)** -kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
