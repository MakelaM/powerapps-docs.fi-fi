---
title: Mallipohjaisen sovelluksen mukautettujen entiteettien kuvakkeiden muuttaminen PowerAppsissa | MicrosoftDocs
definition: Learn how to change the icon for a custom entity
ms.custom: ''
ms.date: 05/17/2018
ms.reviewer: ''
ms.service: powerapps
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="change-model-driven-app-custom-entity-icons"></a>Mallipohjaisen sovelluksen mukautettujen entiteettien kuvakkeiden muuttaminen 

Kun mukautettu entiteetti luodaan, sille liitetään automaattisesti oletuskuvake. Kaikki mukautetut entiteetit käyttävät samaa kuvaketta oletusarvoisesti. Voit yksilöidä mukautettujen entiteettien ulkonäön mukautettujen kuvakkeiden avulla. Järjestelmäentiteettien kuvakkeita ei voi muokata.  
  
 Voit ladata kolmentyyppisiä entiteettikuvakkeita kullekin mukautetulle entiteetille. 

|Kuvaketyyppi  |Kuvaus  |
|---------|---------|
|**Unified Interface -kuvake**|Tämän on oltava skaalattava vektorikuva (.svg) |
|**Kuvake WWW-sovelluksessa**|.svg-, .gif-, .png- tai .jpg-muodon kuva, koko 16x16 kuvapistettä.|
|**Entiteettilomakkeiden kuvake**|.svg-, .gif-, .png- tai .jpg-muodon kuva, koko 32x32 kuvapistettä.|

> [!NOTE]
> Kaikkien kuvatiedostojen enimmäiskoko on 10 kilotavua.
>
> Kun käytössä on skaalattava vektorikuva (.svg) **Kuvake WWW-sovelluksessa**- tai **Entiteettilomakkeiden kuvake** -kohtana, oletuskoko on määritettävä. KOska SVG on XML-asiakirja, voit muokata [svg](https://developer.mozilla.org/docs/Web/SVG/Element/svg)-elementin [leveyden](https://developer.mozilla.org/docs/Web/SVG/Attribute/width) ja [korkeuden](https://developer.mozilla.org/docs/Web/SVG/Attribute/height) arvoja tekstieditorissa ja määrittää kuvan oletuskoon.

Kuvakkeen kukin tyyppi tallennetaan WWW-resurssina. Voit luoda WWW-resurssit ensin ja määrittää sitten niissä käytettävät kuvakkeet. Vaihtoehtoisesti voit luoda uuden WWW-resurssin **Valintatietue**-valintaikkunassa valitsemalla **Uusi** arvon määrittämisen aikana. Lisätietoja: [WWW-resurssien luominen tai muokkaaminen sovelluksen laajentamiseksi](create-edit-web-resources.md)

## <a name="set-the-icons-for-a-custom-entity"></a>Määrittää mukautetun entiteetin kuvakkeet.

Määritä entiteettien kuvakkeet ratkaisunhallinnan avulla.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

### <a name="set-entity-icons"></a>Entiteettien kuvakkeiden määrittäminen

1. Valitse komentopalkissa **Päivitä kuvakkeet**.  
  
2. Valitse **Valitse uudet kuvakkeet** -valintaikkunan **WWW-asiakasohjelma**-välilehden **Kuvake WWW-sovelluksessa**- tai **Entiteettilomakkeiden kuvake** -kohdan **Uusi kuvake** -kohdan oikealla puolella **Selaa**-painike ![Haku-painike](media/lookup-button-4.gif).
3. Valitse soveltuva WWW-resurssi tai luo se ja valitse sitten **OK**. 
4. Tee samat toiminnot **Unified Interface** -välilehden **Uusi kuvake** -kentässä.
5. Sulje **Valitse uudet kuvakkeet** -valintaikkuna valitsemalla **OK**.
6. Valitse komentopalkin **Tiedosto**-valikossa **Tallenna**.  
7. Kun olet tehnyt haluamasi muutokset, julkaise ne. Valitse komentopalkissa **Julkaise** samalla, kun entiteetti on valittuna ratkaisunhallinnassa.
  
## <a name="community-tools"></a>Yhteisön työvälineet

**[Iconator](https://www.xrmtoolbox.com/plugins/MscrmTools.Iconator/)** on työnkalu, jonka XrmToolbox-yhteisö on kehittänyt Dynamics 365 Customer Engagement -sovellusta varten. Lisätietoja yhteisön kehittämistä työkaluista on kohdassa [Common Data Servicen sovelluskehittäjän työkalut](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools).

> [!NOTE]
> Yhteisön työkalut eivät ole Microsoftin tuotteita eivätkä laajenna tuen yhteisön työkaluille. Jos sinulla on kysymyksiä työkalusta, ota yhteyttä julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com).

## <a name="next-steps"></a>Seuraavat vaiheet  
[Entiteetin luominen](../common-data-service/create-edit-entities.md)<br />
[Entiteetin muokkaaminen](../common-data-service/edit-entities.md)
