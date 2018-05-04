---
title: 'Sarakkeiden ohjausobjekti: viitetiedot | Microsoft Docs'
description: Tässä aiheessa on tietoja Microsoft PowerAppsin sarake-ohjausobjektista.
services: powerapps
documentationcenter: na
author: jasongre
manager: kfend
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/05/2017
ms.author: kfend
ms.openlocfilehash: 0e9c04c4786ff4cee11d7aae75245054e93391fa
ms.sourcegitcommit: 59785e9e82da8f5bd459dcb5da3d5c18064b0899
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/22/2018
---
# <a name="column-control-in-powerapps"></a>Sarake-ohjausobjekti PowerAppsissa
Tarjoaa näyttökokemuksen yhdessä kentässä [**tietotaulukko**](control-data-table.md)-ohjausobjektissa.

## <a name="description"></a>Kuvaus
[**Tietotaulukko**](control-data-table.md)-ohjausobjekti näyttää tietojoukon taulukkomuotoisena ja kutakin saraketta kyseisessä taulukkomuodossa edustaa **sarake**-ohjausobjekti. **Sarake**-ohjausobjekti tarjoaa ominaisuudet, joita sovelluksen laatija voi käyttää sarakkeen ulkonäön ja käyttäytymisen muokkaamiseen.

## <a name="capabilities"></a>Ominaisuudet
### <a name="now-available"></a>Nyt käytettävissä
* Muuta **sarake**-ohjausobjektin leveyttä.
* Muuta **sarake**-ohjausobjektin tekstiä.
* Siirry napsauttamalla tai napauttamalla **sarake**-ohjausobjektissa olevaa arvoa.

### <a name="not-yet-available"></a>Ei ole vielä käytettävissä
* Muokkaa **sarake**-ohjausobjektin ulkoasua.

### <a name="known-issues"></a>Tunnetut ongelmat
* **Visible**-ominaisuutta ei vielä voi käyttää.

## <a name="properties"></a>Ominaisuudet
* **DisplayName** – sarakkeen otsikossa näkyvä teksti.
  
  > [!NOTE]
  > Tämän ominaisuuden nimeksi muutetaan pian **HeaderText**.
  > 
  > 
* **IsHyperlink** – arvo, joka ilmaisee, tuleeko sarakkeen tiedot alleviivata sen osoittamiseksi, että kyseessä on hyperlinkki.
* [**Width**](properties-size-location.md) – **Sarake**-ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

## <a name="examples"></a>Esimerkkejä
### <a name="resize-a-column"></a>Sarakkeen koon muuttaminen
1. Luo tyhjä tablettisovellus.
2. Napsauta tai napauta **Lisää**-välilehdessä **tietotaulukkoa** ja muuta sitten **tietotaulukko**-ohjausobjektin kokoa siten, että se peittää koko näytön.
3. Napsauta tai napauta alanuolta, joka on oikeanpuoleisessa ruudussa olevan tekstin **Tietolähdettä ei ole valittu** oikealla puolella, ja napsauta tai napauta kohtaa **Lisää tietolähde**.
4. Napsauta tai napauta yhteysluettelossa yhteyttä, jonka haluat luoda Common Data Service -tietokantaasi.
5. Napsauta tai napauta entiteettiluettelosta **Tili** ja napsauta tai napauta **Yhdistä**.
   
    **Tietotaulukko**-ohjausobjekti on alustettu ja se näyttää oletuskenttien joukon.
6. Napsauta tai napauta **Koko nimi** -saraketta.
   
    ![Sarake-ohjausobjekti on valittuna](./media/control-column/pre-resize-column.png)
7. Vetämällä oikealla puolella olevaa säädintä voit muuttaa kentän kokoa.
   
    ![Sarake-ohjausobjektin koko on muutettu](./media/control-column/post-resize-column.png)

