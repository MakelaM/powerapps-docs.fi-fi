---
title: Tiedoston ratkaisuhistorian tarkasteleminen | MicrosoftDocs
description: Tiedoston ratkaisuhistorian tarkastelemisen oppiminen
keywords: null
ms.date: 05/19/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 for Customer Engagement (online)
  - Dynamics 365 for Customer Engagement Version 9.x
  - powerapps
ms.assetid: null
author: Mattp123
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: null
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="view-the-history-of-a-solution"></a>Tiedoston ratkaisuhistorian tarkasteleminen
Voit tarkastella ratkaisun toimintojen tietoja mallipohjaisen sovelluksen **Ratkaisut**-alueella. Toiminto voi olla ratkaisun tuominen, vieminen tai poistaminen. Ratkaisuhistoria näyttää tietoja, kuten ratkaisun version, ratkaisun julkaisijan, toimintotyypin, toiminnon alkamis- ja päättymisajan sekä toiminnon tilan.

> [!div class="mx-imgBorder"] 
> ![](media/solutions-history-custom-view.png "Ratkaisujen historian mukautettu näkymä")

## <a name="view-solution-history"></a>Näytä ratkaisuhistoria
1. Valitse ensin **Asetukset** ja sitten **Ratkaisuhistoria**.

     > [!div class="mx-imgBorder"] 
     > ![](media/solution-history-sitemap.png "Ratkaisuhistorian alue")

     > [!NOTE]
     > Päästäksesi **Asetukset**-alueeseen PowerApps unified interface -mallipohjaisen sovelluksesta, valitse **Asetukset** ![Asetukset](../model-driven-apps/media/powerapps-gear.png) sovelluksen sovellustyökaluriviltä ja valitse sitten **Lisäasetukset**. 

2. Oletusarvon mukaan näkyviin tulee **Mukautettujen ratkaisujen historia** -näkymä. Seuraavat näkymät ovat käytettävissä **Ratkaisujen historia** -alueessa. 
- **Kaikkien ratkaisujen historia**. Näyttää ratkaisuhistorian sekä sisäisessä järjestelmässä että mukautetuissa ratkaisuissa. 
- **Mukautettujen ratkaisujen historia**. Näyttää ratkaisuhistorian vain mukautettuja ratkaisuja varten. 
- **Sisäisten ratkaisujen historia**. Näyttää ratkaisuhistorian vain sisäisen järjestelmän ratkaisuissa. 

Kukin ratkaisuhistoriatietue on vain luku -tilassa, ja se sisältää seuraavat ominaisuudet: 
- **Aloitusaika**. Aika, jolloin toiminto käynnistettiin. 
- **Päättymisaika**: Aika, jolloin toiminto päättyi. 
- **Ratkaisun versio**. Ratkaisun versio. 
- **Julkaisijan nimi**. Sen julkaisijan nimi, johon toiminto liittyy. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md)  
- **Toiminto**. Toiminto, kuten tuonti, vienti tai poisto. Lisätietoja: [Ratkaisujen tuominen. päivittäminen ja vieminen](import-update-export-solutions.md)
- **Alitoiminto**: Ilmaisee toiminnon tyypin, kuten uuden ratkaisun tuonnin tai aiemmin luodun ratkaisun päivityksen. 
- **Tila**. Toiminnon nykyinen tila, kuten **Valmis** tai **Ei valmis**. 
- **Tulos**. Toiminnon tulos, kuten **Onnistuminen** tai **Epäonnistuminen**. 
- **Virhekoodi**: Toiminnon palauttama virhekoodi. Virhekoodi 0 tarkoittaa, että toiminto suoritettiin onnistuneesti. 

### <a name="view-solution-operation-error-details"></a>Ratkaisun toiminnon virhetietojen tarkasteleminen 
Kun ratkaisun toiminto sisältää virheen, voit valita sen, jos haluat näyttää sivun, jossa on lisää virhetietoja. 

> [!div class="mx-imgBorder"] 
> ![](media/solution-history-with-failure.png "Ratkaisun historia ja toiminnon virhe")

Tiedot-sivu sisältää tietoja, kuten **Poikkeussanoman**, jonka avulla voidaan diagnosoida toiminnon epäonnistumisen perimmäinen syy. Jotkin virheet, kuten ratkaisun riippuvuuksien virheet, voivat sisältää myös linkkejä **Ratkaisun tasoihin**, jolloin ongelman vianmääritys on helpompaa. **Aktiviteetin tunnuksesta** voi olla hyötyä, jos sinun täytyy ottaa yhteyttä Microsoftin asiakastukeen. 

> [!div class="mx-imgBorder"] 
> ![](media/solution-history-error-details.png "Ratkaisun toiminnon virhetiedot")

### <a name="see-also"></a>Katso myös
[Ratkaisun tasojen tarkasteleminen](solution-layers.md)  <br />
[Ratkaisujen yleiskatsaus](solutions-overview.md) 


