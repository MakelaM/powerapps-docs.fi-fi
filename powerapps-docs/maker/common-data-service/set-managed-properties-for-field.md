---
title: Hallitut ominaisuudet määrittäminen kentille PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten voit määrittää kentän hallitut ominaisuudet'
ms.custom: ''
ms.date: 06/19/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 4ddcfcf3-5604-4b93-a5ee-589d4fb97fa4
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="set-managed-properties-for-fields"></a>Kenttien hallittujen ominaisuuksien määrittäminen

<a name="BKMK_SettingManagedProperties"></a>   

 hallitut ratkaisut on käytössä vain, kun hallitussa ratkaisussa on kenttiä ja ratkaisu tuodaan toiseen ympäristöön. Näiden asetusten avulla ratkaisun tekijä pystyy jonkin verran hallitsemaan sitä, kuinka paljon heidän hallittua ratkaisua käyttävät henkilöt voivat mukauttaa tätä kenttää. Voit määrittää kentän hallitut ominaisuudet valitsemalla valikkorivillä **Hallitut ominaisuudet**.  
  
 **Voi mukauttaa** -asetus hallitsee kaikkia muita asetuksia. Jos asetukseksi on valittu `False`, muita asetuksia ei voi käyttää. Kun asetukseksi on valittu `True`, voit määrittää muita mukautettuja asetuksia.  
  
 Jos kenttää voi mukauttaa, määritä seuraavien asetuksen arvoiksi `True` tai `False`.  
  
- **Näyttönimeä voi muokata**  
  
- **Voi muuttaa vaatimustasoa**  
  
- **Voi muuttaa lisäominaisuuksia**  
  
 Näitä asetuksia ei tarvitse selvittää sen tarkemmin. Jos määrität kaikkien yksittäisten vaihtoehtojen arvoksi `False`, voit määrittää myös **Voi mukauttaa** -kohdan arvoksi `False`.  

 ## <a name="next-steps"></a>Seuraavat vaiheet

 [Kenttien luominen ja muokkaaminen](create-edit-fields.md)
