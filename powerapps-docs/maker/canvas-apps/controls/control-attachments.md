---
title: 'Liiteohjausobjekti: viittaus | Microsoft Docs'
description: Tietoja liiteohjausobjektista, kuten ominaisuudet ja esimerkkejä
services: ''
suite: powerapps
documentationcenter: na
author: fikaradz
manager: anneta
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/29/2017
ms.author: fikaradz
ms.openlocfilehash: 5bb7e4f27ed7ee0a30fb028d4d8dfd20a5fc250b
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
---
# <a name="attachments-control-in-powerapps"></a>Liiteohjausobjekti PowerAppsissa
Ohjausobjekti, jolla käyttäjät voivat ladata tiedostoja laitteeseen sekä ladata ja poistaa tiedostoja SharePoint-luettelosta.

## <a name="limitations"></a>Rajoitukset
Liiteohjausobjektia koskevat tilapäisesti seuraavat rajoitukset:
1. Internet Explorer ei tue liitteen latausta.

1. Liitteen lataaminen toimii vain SharePoint-luettelon tietolähteiden kanssa.  Muiden tietolähteiden tuki lisätään asteittain, alkaen CDS:stä.

1. Lataaminen ja poistaminen toimivat vain lomakkeen sisällä.  Liiteohjausobjekti näyttää käytöstä poistetulta, kun käyttäjä on Muokkaa-tilassa eikä lomakkeen sisällä.   Huomaa, että loppukäyttäjän on tallennettava lomake, jos tiedoston lisäykset ja poistot halutaan tallentaa taustatietokantaan.

1. Voit ladata enintään 10 Mt:n kokoisia tiedostoja.  

## <a name="description"></a>Kuvaus
**Liite**ohjausobjektin avulla voit avata tietolähteeseen tallennettuja tiedostoja sekä lisätä ja poistaa tiedostoja SharePoint-luettelosta.

## <a name="key-properties"></a>Keskeiset ominaisuudet
**[Items](properties-core.md)**  – Ladattavia tiedostoja kuvaava lähde.

**MaxAttachments** – Ohjausobjektin hyväksymien tiedostojen enimmäismäärä.

**MaxAttachmentSize** – Jokaisen uuden liitteen suurin sallittu tiedostokoko megatavuina.  Tällä hetkellä enimmäiskoko on 10 megatavua.

**OnAttach** – Miten sovellus reagoi, kun käyttäjä lisää uuden liitetiedoston.

**OnRemove** – Miten sovellus reagoi, kun käyttäjä poistaa olemassa olevan liitetiedoston.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napsauttaa liitetiedostoa.

## <a name="additional-properties"></a>Lisäominaisuudet
**AccessibleLabel** – Näytönlukuohjelman ilmoittama selite.

**AddAttachmentText** – Uuden liitteen lisäämiseen käytetyn linkin nimen teksti.

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus pois käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**MaxAttachmentsText** – Teksti, joka korvaa Liitä tiedosto -linkin, kun ohjausobjekti sisältää enimmäismäärän sallittuja tiedostoja.

**NoAttachmentsText** – Tiedottava teksti, joka näytetään käyttäjälle, kun tiedostoja ei ole liitetty.

**[Visible](properties-core.md)** – Määrittää, onko ohjausobjekti näkyvä vai piilotettu.

**[Width](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön vasemman reunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).


## <a name="example"></a>Esimerkki
1. Luo sovellus tiedoista käyttämällä SharePoint-luetteloa tietolähteenä.  Vaihtoehtoisesti voit lisätä lomakkeen sovellukseesi ja määrittää SharePoint-luettelon sen tietolähteeksi.

2. Valitse **lomake**ohjausobjekti vasemmassa reunassa olevasta puunäkymästä.

3. Napsauta vasemmalla olevan Asetukset-paneelin Ominaisuudet-välilehdeltä **Tiedot**.

4. Ota **Liitteet**-kenttä käyttöön kohdasta **Kentät**.

    SharePoint-luetteloon liittyvä Liitteet-kenttä tulee näkyviin lomakkeeseen.

Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?
