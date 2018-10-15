---
title: PowerApps-koontinäytön sisältämän mallipohjaisen sovelluksen kaavion tai luettelon määrittäminen | MicrosoftDocs
description: Lue, miten voit määrittää ominaisuudet kaavio- koontinäytön kaaviota tai luetteloa varten
ms.custom: ''
ms.date: 06/06/2018
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
ms.assetid: 50fb2ab0-5c1a-4a5e-8ebc-5603fecc4da0
caps.latest.revision: 26
ms.author: matp
manager: kvivek
ms.openlocfilehash: c88fef0412060516ef448c89f5ddfdc9cad00e20
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679587"
---
# <a name="set-properties-for-a-model-driven-app-chart-or-list-included-in-a-dashboard"></a>Koontinäytön sisältämän mallipohjaisen sovelluksen kaavion tai luettelon määrittäminen

Muokkaa kaavion tai luettelon osaa koontinäytön suunnittelutyökalusta valitsemalla haluamasi kaavion tai luettelon ja valitse sitten Muokkaa osa koontinäytön suunnittelutoiminnon työkaluriviltä.   

  ![Koontinäytön suunnittelutyökalun kaavion muokkausosa](media/dashboard-chart-select.png)

Tämä avaa **Ominaisuuksien määrittäminen** -valintaikkunan.

  ![Määritä kaavion ominaisuudet](media/set-properties-chart.png)  
 
Voit määrittää seuraavat kaavion ominaisuudet **Ominaisuuksien määrittäminen** -valintaikkunassa:  
  
- **Nimi** Kaavion yksilöivä nimi. Järjestelmä ehdottaa arvoa, mutta voit muuttaa sitä.  
  
- **Selite**. Selite, joka näytetään kaavion yläreunassa.  
  
- **Näytä selite koontinäytössä**. Valitse tai poista tämä valintaruutu, jos haluat näyttää tai piilottaa kaavion selitteen.  
  
- **Entiteetti**. Valitse entiteetti (tietuetyyppi), jolle kaavio pohjautuu. Tämä asetus määrittää oletusnäkymän käytettävissä olevat arvot ja oletuskaavion ominaisuudet.  
  
- **Oletusnäkymä** Valitse näkymä, jota käytetään kaavion tietojen noutamiseen.  
  
- **Oletuskaavio** Valitse oletuskaavio, jonka haluat näyttää, kun koontinäyttö avataan ensimmäisen kerran. Käytettävissä olevat arvot määritetään entiteetille asetetun ominaisuuden arvolla. Tämä ominaisuus toimii yhdessä Näytä kaavion valinta -ominaisuuden kanssa. Käyttäjä voi muuttaa kaaviotyyppiä, jos **Näytä kaavion valinta** -asetus on käytössä, mutta kaavio palautuu oletuskaavioksi seuraavan kerran koontinäyttöä avattaessa.  
  
- **Näytä vain kaavio** Valitse tämä valintaruutu, jos haluat näyttää vain kaavion. Poista valinta tästä valintaruudusta, jos haluat näyttää kaavion ja siihen liittyvät tiedot.  
  
- **Näytä kaavion valinta** Valitse tämä valintaruutu, jotta käyttäjät voivat muuttaa kaaviotyyppiä (sarake, palkki, ympyräkaavio jne.), kun he käyttävät koontinäyttöä. Jos käyttäjä muuttaa kaavion tyyppiä, asetuksia ei tallenneta. Kaaviotyyppi palautuu oletuskaavioasetuksiin, kun koontinäyttö suljetaan.  
  
Voit määrittää seuraavat luettelon ominaisuudet **Ominaisuuksien määrittäminen** -valintaikkunassa:  
  
- **Nimi** Luettelon yksilöivä nimi. Järjestelmä ehdottaa arvoa, mutta voit muuttaa sitä.  
  
- **Selite** Selite, joka näytetään luettelon yläreunassa.  
  
- **Näytä selite koontinäytössä** Valitse tai poista valinta tästä valintaruudusta, jos haluat näyttää tai piilottaa luettelon selitteen.  
  
- **Entiteetti**. Valitse entiteetti (tietuetyyppi), jolle luettelo pohjautuu. Tämä asetus määrittää oletusnäkymän ominaisuudet.  
  
- **Oletusnäkymä** Valitse näkymä, jota käytetään luettelon tietojen noutamiseen. Käyttäjä voi muuttaa näkymää, mutta luettelo palautuu oletusnäkymään seuraavan kerran koontinäyttöä avattaessa.  
  
- **Näytä hakuruutu** Valitse tämä valintaruutu, jos haluat näyttää haku-ruudun luettelon yläosassa. Jos hakuruutu on käytössä, sinä ja muut käyttäjät voitte etsiä tietueita luettelosta ajon aikana.  
  
- **Indeksin näyttö** Valitse tämä valintaruutu, jos haluat näyttää A-Z-suodattimet luettelon alaosassa. Kun A-Z-suodattimet näkyvät, sinä tai muut käyttäjät voitte valita kirjaimen, jolla siirrytään tällä kyseisellä kirjaimella alkavaan tietueeseen.  
  
- **Näkymän valitsin** Valitse jokin seuraavista arvoista:  
  
    - **Ei käytössä** Älä näytä näkymän valitsinta. Sinä tai muut käyttäjät eivät voi vaihtaa näkymää ajon aikana.  
  
    - **Näytä kaikki näkymät** Antaa täydellisen luettelon näkymistä, jotka liittyvät entiteetti-ominaisuudessa asetettuun arvoon.  
  
    - **Näytä valitut näkymät** Valitse tämä asetus rajoittamaan näkymien luetteloa ajon aikana. Valitse tietyt näkymät pitämällä Ctrl-näppäintä ja napauttamalla tai valitsemalla jokaisen näkymän, jonka haluat sisällyttää mukaan.  
 
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Luo tai mukauta koontinäyttöjä](create-edit-dashboards.md)
