---
title: 'Sarakkeiden ohjausobjekti: viitetiedot | Microsoft Docs'
description: Tässä aiheessa on tietoja Microsoft PowerAppsin Sarake-ohjausobjektista.
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 06/05/2017
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: e1c8ba704a01c989da990fd1b2b17f7b5def5541
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42850851"
---
# <a name="column-control-in-powerapps"></a>Sarake-ohjausobjekti PowerAppsissa
Tarjoaa näyttökokemuksen yhdessä kentässä [**Tietotaulukko**](control-data-table.md)-ohjausobjektissa.

## <a name="description"></a>Kuvaus
[**Tietotaulukko**](control-data-table.md)-ohjausobjekti näyttää tietojoukon taulukkomuotoisena, ja kutakin saraketta kyseisessä taulukkomuodossa edustaa **Sarake**-ohjausobjekti. **Sarake**-ohjausobjekti tarjoaa ominaisuudet, joita sovelluksen laatija voi käyttää sarakkeen ulkonäön ja käyttäytymisen muokkaamiseen.

## <a name="capabilities"></a>Ominaisuudet
### <a name="now-available"></a>Nyt käytettävissä
* Muuta **Sarake**-ohjausobjektin leveyttä.
* Muuta **Sarake**-ohjausobjektin tekstiä.
* Siirry napsauttamalla tai napauttamalla **Sarake**-ohjausobjektissa olevaa arvoa.

### <a name="not-yet-available"></a>Ei ole vielä käytettävissä
* Muokkaa **Sarake**-ohjausobjektin ulkoasua.

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
2. Napsauta tai napauta **Lisää**-välilehdessä **Tietotaulukkoa** ja muuta sitten **Tietotaulukko**-ohjausobjektin kokoa siten, että se peittää koko näytön.
3. Napsauta tai napauta alanuolta, joka on oikeanpuoleisessa ruudussa olevan tekstin **Tietolähdettä ei ole valittu** oikealla puolella, ja napsauta tai napauta kohtaa **Lisää tietolähde**.
4. Napsauta tai napauta yhteysluettelossa yhteyttä, jonka haluat luoda Common Data Service -tietokantaasi.
5. Napsauta tai napauta entiteettiluettelosta **Tili** ja napsauta tai napauta **Yhdistä**.
   
    **Tietotaulukko**-ohjausobjekti on alustettu, ja se näyttää oletuskenttien joukon.
6. Napsauta tai napauta **Koko nimi** -saraketta.
   
    ![Sarake-ohjausobjekti on valittuna](./media/control-column/pre-resize-column.png)
7. Vetämällä oikealla puolella olevaa säädintä voit muuttaa kentän kokoa.
   
    ![Sarake-ohjausobjektin koko on muutettu](./media/control-column/post-resize-column.png)


## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet
### <a name="screen-reader-support"></a>Näytönlukuohjelman tuki
* **DisplayName** on oltava olemassa.
