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
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9d24094bfbc596c232e7455ef3d8b8dcdfc5be5c
ms.sourcegitcommit: 9b2648a9066fe5d3b27b3d893daacba9b18eb75e
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/14/2019
ms.locfileid: "65609376"
---
# <a name="attachments-control-in-powerapps"></a>Liiteohjausobjekti PowerAppsissa
Ohjausobjekti, jonka avulla käyttäjät voivat ladata tiedostoja laitteensa, sekä ladata ja poistaa tiedostoja SharePoint-luetteloon tai Common Data Service-entiteetistä.

## <a name="limitations"></a>Rajoitukset
Liiteohjausobjektilla on seuraavat rajoitukset:
1. SharePoint-luetteloiden ja Common Data Service-entiteettejä tuetaan liitteet.

1. Lataaminen ja poistaminen toimivat vain lomakkeen sisällä. Liiteohjausobjekti näkyy käytöstä Kun muokkaustilassa ja lomakkeen sisällä. Jos haluat tallentaa tiedoston lisäykset ja poistot, sovelluksen käyttäjälle on tallennettava lomake. Tämän rajoituksen vuoksi liitetiedosto-ohjausobjektilla ei ole käytettävissä **Lisää** välilehti näkyvät lomakkeessa mutta, kun liite lomakekenttä on käytössä SharePoint- tai Common Data Service-muodossa.

1. Voit ladata vain, jos ne ovat 10 Mt tai pienempiä tiedostoja.  

## <a name="description"></a>Kuvaus
**Liitteet** ohjausobjektin avulla voit avata, lisätä ja poistaa tiedostoja SharePoint-luetteloon tai Common Data Service-entiteetistä.

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
* **[TabIndex](properties-accessibility.md)**-kohteen on oltava nolla tai yli, jotta näppäimistön käyttäjät voivat siirtyä siihen.
* Kohdistuksen ilmaisinten on oltava selvästi näkyvissä. Voit tehdä tämän kohteiden **[FocusedBorderColor](properties-color-border.md)** ja **[FocusedBorderThickness](properties-color-border.md)** avulla.
