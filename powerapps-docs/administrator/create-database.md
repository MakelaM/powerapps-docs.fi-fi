---
title: Common Data Service (CDS) for Apps -tietokannan luominen | Microsoft Docs
description: Ohjeet Common Data Service (CDS) for Apps -tietokannan luomiseen.
services: powerapps
author: manasmams
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: conceptual
ms.date: 03/21/2018
ms.author: manasma
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 9b62d72cf04b56c945d0c85038e2264e9685828b
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42837581"
---
# <a name="create-a-common-data-service-for-apps-database"></a>Common Data Service for Apps -tietokannan luominen
Voit luoda tietokannan ja rakentaa sovelluksia käyttämällä Common Data Service (CDS) for Apps -palvelua tietosäilönä. Voit joko luoda omia mukautettuja entiteettejä tai käyttää ennalta määritettyjä entiteettejä. Jotta voit luoda tietokannan, sinun on ensin joko luotava ympäristö tai saatava olemassa olevan ympäristön **Ympäristön järjestelmänvalvoja** -rooli. Lisäksi sinulle on määritettävä sopiva käyttöoikeus. Lisätietoja CDC for Appsin käyttöön tarvittavan palvelupaketin ostamisesta on kohdassa [Hinnoittelutiedot](pricing-billing-skus.md).

Voit luoda tietokannan eri tavoin:

* PowerApps-hallintakeskuksessa
* Powerapps.com-sivun **Entiteetit**-ruudussa

## <a name="create-a-database-in-the-admin-center"></a>Tietokannan luominen hallintakeskuksessa
1. Valitse [hallintakeskuksen](https://admin.powerapps.com) vasemmasta siirtymisruudusta **Ympäristöt**.
    
2. Valitse ympäristö, jossa haluat luoda tietokannan.
    
    ![](./media/create-database/environment-list-new.png)

3. Valitse **Tiedot**-välilehdessä **Luo tietokanta**. 
    
    ![](./media/create-database/Create-DB-From-Details.png)

4. Valitse valuutta ja kieli. 
    
    ![](./media/create-database/DB-Choose-options.png)



## <a name="create-a-database-in-the-entities-pane-of-powerapps"></a>Tietokannan luominen PowerAppsin Entiteetit-ruudussa
1. Suurenna [powerapps.com](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

2. Luo tietokanta napsauttamalla kohtaa **Luo tietokanta**.

    ![](./media/create-database/Create-DB-From-Entities.png)

> [!NOTE]
> Tällä hetkellä ei ole mahdollista luoda tietokantaa Azure AD-alueen ulkopuolella. Tietokannan luominen eri alueella kuin Azure AD -kotialueesi tulee pian mahdolliseksi, mutta toistaiseksi varmista, että luot tietokannan ympäristössä, jonka alue on sama kuin Azure AD -kotialueesi.

## <a name="security-model-for-the-databases"></a>Tietokantojen suojausmalli
Käyttäjät, joille on määritetty ympäristörooleja, säilyttävät kaikki samat oikeudet tietokannan luomisen yhteydessä.  
    **Ympäristön järjestelmänvalvojan** roolissa olevat käyttäjät määritetään nyt **järjestelmänvalvojan** rooliin. **Ympäristön tekijä** -rooliin kuuluvat käyttäjät jatkavat samassa roolissa.

Voit määrittää ennalta määritettyihin rooleihin lisää käyttäjiä tai luoda [mukautettuja rooleja][1]. Lisätietoja saat kohdasta [Tietokannan suojaus](database-security.md).

> [!NOTE]
> Tietokannan luomisen yhteydessä kaikki ympäristön järjestelmänvalvojan tai ympäristön tekijän rooliin määritetyt käyttöoikeusryhmät menettävät roolinsa. Tietokannan oikeuksien määritys ei tällä hetkellä tue Microsoft Azure Active Directory -käyttöoikeusryhmää.


## <a name="license-and-security-permissions"></a>Käyttö- ja suojausoikeudet
Jotta voit luoda tietokannan, sinun on oltava valitun ympäristön järjestelmänvalvoja ja omattava asianmukaiset käyttöoikeudet. Ympäristössä voit lisäksi määrittää **Suojaus**-välilehdellä muiden käyttäjien suojausoikeuksia. Lisätietoa saat kohdasta [Tietokannan suojauksen määritys](database-security.md) ja [Suojausmalli](https://docs.microsoft.c../maker/common-data-service/entity-reference/security-model).

## <a name="privacy-notice"></a>Tietosuojailmoitus
Microsoft PowerApps Common Data Model kerää ja tallentaa mukautettuja entiteettejä ja kenttien nimiä diagnostiikkajärjestelmäämme.  Näiden tietojen avulla parannamme asiakkaille tarjottavaa yleistä tietomallia. Tekijöiden luomat entiteettien ja kenttien nimet auttavat meitä ymmärtämään skenaarioita, jotka ovat yleisiä Microsoft PowerApps -yhteisössä, sekä kehittämään palveluja, jos entiteettien vakiotarjonnassa ilmenee puutteita esimerkiksi organisaatioihin liittyvissä rakenteissa. Microsoft ei käytä näihin entiteetteihin liittyvissä tietokantataulukoissa olevia tietoja, eikä jäljennä niitä tietokannan käyttöoikeusalueen ulkopuolelle. Huomaa kuitenkin, että mukautetut entiteettien nimet ja kentät voidaan jäljentää alueelta toiselle, ja niiden poistamisessa noudatetaan tietojen säilytyskäytäntöjämme. Microsoft on sitoutunut takaamaan käyttäjien tietosuojan [luottamuskeskuksessamme](https://www.microsoft.com/trustcenter/Privacy/default.aspx) kuvaillulla tavalla.


<!--Reference links in article-->
[1]: https://technet.microsoft.com/library/dn531130.aspx
