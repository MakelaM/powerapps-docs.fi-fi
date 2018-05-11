---
title: Common Data Service -tietokannan luominen | Microsoft Docs
description: Common Data Service -tietokannan luominen.
services: powerapps
documentationcenter: na
author: manasmams
manager: kfend
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: c32be4dd25da1c2267043b061102b2714a109cc5
ms.sourcegitcommit: 8bd4c700969d0fd42950581e03fd5ccbb5273584
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/26/2018
---
# <a name="create-a-common-data-service-database"></a>Common Data Service -tietokannan luominen
Voit luoda tietokannan ja rakentaa sovelluksia käyttämällä Common Data Service -palvelua tietosäilönä. Voit joko luoda omia mukautettuja entiteettejä tai käyttää ennalta määritettyjä entiteettejä. Jotta voit luoda tietokannan, sinun on ensin joko luotava ympäristö tai saatava olemassa olevan ympäristön **Ympäristön järjestelmänvalvoja** -rooli. Lisäksi sinulle on määritettävä sopiva käyttöoikeus. Lisätietoja Common Data Servicen käyttöön tarvittavan palvelupaketin ostamisesta on kohdassa [Hinnoittelutiedot](pricing-billing-skus.md).

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



## <a name="create-a-database-in-the-entities-pane-of-powerappscom"></a>Tietokannan luominen powerapps.com-sivun Entiteetit-ruudussa
1. Suurenna [powerapps.com](https://web.powerapps.com)-sivuston **Tiedot**-osio ja napsauta tai napauta vasemman siirtymisruudun **Entiteetit**-kohtaa.

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
Jotta voit luoda tietokannan, sinun on oltava valitun ympäristön järjestelmänvalvoja ja omattava asianmukaiset käyttöoikeudet. Ympäristön **Suojaus**-välilehdessä voit lisäksi määrittää muiden käyttäjien suojausoikeuksia. Lisätietoa saat kohdasta [Tietokannan suojauksen määritys](database-security.md) ja [Suojausmalli](https://docs.microsoft.c../maker/common-data-service/entity-reference/security-model).

## <a name="privacy-notice"></a>Tietosuojailmoitus
Microsoft PowerApps Common Data Model kerää ja tallentaa mukautettuja entiteettejä ja kenttien nimiä diagnostiikkajärjestelmäämme.  Näiden tietojen avulla parannamme asiakkaille tarjottavaa yleistä tietomallia. Tekijöiden antamat entiteettien ja kenttien nimet auttavat meitä ymmärtämään Microsoft PowerApps -yhteisössä yleisiä skenaarioita ja havaitsemaan palvelun vakioentiteettitarjonnan puutteita, kuten organisaatioihin liittyviä rakenteita. Microsoft ei avaa eikä käytä näihin entiteetteihin liittyvien tietokantataulukoiden tietoja, eikä niitä replikoida tietokannan luomisalueen ulkopuolelle. Huomaa kuitenkin, että mukautetut entiteettien nimet ja kentät voidaan replikoida monelle alueelle ja poistetaan Microsoftin tietojen säilytyskäytäntöjemme mukaisesti. Microsoft on sitoutunut takaamaan käyttäjien tietosuojan [luottamuskeskuksessa](https://www.microsoft.com/trustcenter/Privacy/default.aspx) kuvaillulla tavalla.


<!--Reference links in article-->
[1]: https://technet.microsoft.com/library/dn531130.aspx
