---
title: Malliin perustuvan sovelluksen mukautettujen entiteettien kuvakkeiden muuttaminen PowerAppsissa | MicrosoftDocs
definition: Learn how to change the icon for a custom entity
ms.custom: ''
ms.date: 05/17/2018
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
ms.assetid: 477f9792-8207-49ef-8968-45274b5355a8
caps.latest.revision: 19
ms.author: matp
manager: kvivek
tags:
- Links to topic not migrated
ms.openlocfilehash: c625ac14905e49879eb6dc93eff706a7dab18433
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680563"
---
# <a name="change-model-driven-app-custom-entity-icons"></a>Malliin perustuvan sovelluksen mukautettujen entiteettien kuvakkeiden muuttaminen 

Kun luot mukautetun entiteetin, sille määritetään automaattisesti oletuskuvake. Kaikilla mukautetuilla entiteeteillä on oletusarvoisesti sama kuvake. Mukautetuilla kuvakkeilla voit luoda mukautetuille entiteeteille erottuvia ulkoasuja. Et voi muokata järjestelmäentiteeteille määritettyjä kuvakkeita.  
  
 Voit ladata kullekin mukautetulle entiteetille kolme erityyppistä entiteettikuvaketta. 

|Kuvaketyyppi  |Kuvaus  |
|---------|---------|
|**Unified Interface -kuvake**|Tämän täytyy olla .svg-kuvake. |
|**Kuvake WWW-sovelluksessa**|Tämä voi olla .svg-, .gif-, .png- tai .jpg-kuva, jonka koko on 16 x 16 kuvapistettä.|
|**Entiteettilomakkeiden kuvake**|Tämä voi olla .svg-, .gif-, .png- tai .jpg-kuva, jonka koko on 32 x 32 kuvapistettä.|

> [!NOTE]
> Kaikkien kuvatiedostojen suurin sallittu koko on enintään 10 kilotavua.
>
> Kun käytät .svg-kuvaa **kuvakkeena verkkosovelluksessa** tai **kuvakkeena entiteettilomakkeissa**, sille täytyy määrittää oletuskoko. Koska SVG on XML-tiedostomuoto, voit muokata [svg](https://developer.mozilla.org/docs/Web/SVG/Element/svg)-elementin [width](https://developer.mozilla.org/docs/Web/SVG/Attribute/width)- ja [height](https://developer.mozilla.org/docs/Web/SVG/Attribute/height)-arvoja tekstieditorilla. Näin voit määrittää kuvan oletuskoon.

Kaikki kuvaketyypit tallennetaan verkkoresursseina. Voit luoda ensin verkkoresurssit ja määrittää sitten kuvakkeet käyttämään niitä. Voit myös luoda uuden verkkoresurssin **Valintatietue**-valintaikkunassa valitsemalla **Uusi**, kun olet määrittämässä arvoa. Lisätiedot: [Sovelluksen laajentaminen verkkoresursseja luomalla tai muokkaamalla](create-edit-web-resources.md)

## <a name="set-the-icons-for-a-custom-entity"></a>Määritä mukautetun entiteetin kuvakkeet.

Sinun täytyy määrittää entiteettikuvakkeet ratkaisunhallinnassa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="set-entity-icons"></a>Entiteettikuvakkeiden määrittäminen

1. Valitse komentopalkista **Päivitä kuvakkeet**.  
  
2. Napsauta **Valitse uudet kuvakkeet** -valintaikkunan **WWW-asiakasohjelma**-välilehden **Kuvake WWW-sovelluksessa**- tai **Entiteettilomakkeiden kuvake** -kohdassa **Uusi kuvake** -kohdan oikealla puolella olevaa **Selaa**-painike ![Hakupainike](media/lookup-button-4.gif).
3. Valitse tai luo soveltuva verkkoresurssi ja valitse sitten **OK**. 
4. Tee **Unified Interface** -välilehdessä sama **Uusi kuvake** -kentälle.
5. Sulje **Valitse uudet kuvakkeet** -valintaikkuna valitsemalla **OK**.
6. Valitse komentopalkin **Tiedosto**-valikosta **Tallenna**.  
7. Kun muutoksesi ovat valmiita, julkaise ne. Kun entiteetti on valittuna ratkaisunhallinnassa, valitse komentopalkista **Julkaise**.
  
## <a name="community-tools"></a>Yhteisön työkalut

**[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)** on XrmToolBox-yhteisön kehittämä työkalu Dynamics 365 Customer Engagementille. Saat lisätietoja yhteisön kehittämistä työkaluista ohjeartikkelista [Common Data Service for Appsin kehittäjätyökalut](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools).

> [!NOTE]
> Yhteisön työkalut eivät ole Microsoftin tuotteita, joten se ei tarjoa tukea niille. Jos sinulla on kysyttävää työkalusta, ota yhteyttä sen julkaisijaan. Lisätiedot: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Seuraavat vaiheet  
[Entiteetin luominen](../common-data-service/create-edit-entities.md)<br />
[Entiteetin muokkaaminen](../common-data-service/edit-entities.md)
