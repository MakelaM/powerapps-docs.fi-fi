---
title: Mallipohjaisia mallisovelluksia
description: Tutustu mallipohjaisten mallisovellusten hankkimiseen, muokkaamiseen ja poistamiseen.
documentationcenter: na
author: caburk
manager: kfile
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: caburk
ms.openlocfilehash: 36e5efec10a3f849b6366368eed7b3b9e7af3f8c
ms.sourcegitcommit: 79b8842fb0f766a0476dae9a537a342c8d81d3b3
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/07/2018
ms.locfileid: "37898371"
---
# <a name="model-driven-sample-apps"></a>Mallipohjaisia mallisovelluksia

Käytä [powerapps.comissa](https://powerapps.com) mallisovellusta suunnittelumahdollisuuksien tutkimiseen ja sellaisten ideoiden löytämiseen, joita voit käyttää omia sovelluksiasi suunnitellessasi. Jokainen mallisovellus käyttää kuvitteellisia tietoja reaalimaailman skenaarion esittämiseen. 

Katso lisätietoja tarkistamalla kutakin mallisovellusta koskeva dokumentaatio. 

![Varainkeruutapahtuman mallisovellus](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>Hanki mallisovelluksia

Jotta voit toistaa tai muokata mallipohjaisia mallisovelluksia, sovellukset täytyy ensin valmistella Common Data Service -tietokannassa. Luo ensin kokeiluympäristö ja tietokanta ja tarkista kohta **Sisällytä mallisovellukset ja tiedot**.

![Luo tietokanta](media/overview-model-driven-samples/create-database1.png)


> [!IMPORTANT]
> Tämä vaihtoehto asentaa kaikki käytettävissä olevat mallisovellukset tietokantaan. Mallisovellukset ovat koulutus- ja esittelytarkoituksia varten, emmekä suosittele niiden asentamista tuotantotietokantoihin. 

## <a name="customize-a-sample-app"></a>Mukauta mallisovellusta

1. Kirjaudu sisään osoitteeseen [powerapps.com](https://powerapps.com) ja valitse suunnittelutilaksi **Malliin perustuva**. 

    ![Valitse suunnittelutila](media/overview-model-driven-samples/choose-design-mode.png)

2. Pidä kohdistinta aloitussivulla mallisovelluksen kohdalla ja valitse **Mukauta**.
3. Sovelluksen suunnittelutoiminto avautuu. Siinä on useita sovelluksen mukautusvaihtoehtoja. 
4. Saat lisää mukautusasetuksia napsauttamalla portaalin vasemmassa siirtymisruudussa **Lisäasetukset**.

## <a name="remove-sample-apps-and-data"></a>Poista mallisovelluksia ja tietoja 
- Mallisovelluksen poistaminen edellyttää vastaavan [hallitun ratkaisun](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution) poistamista. 
- Ratkaisun poistaminen poistaa myös kaikki mallitiedot, jotka koskevat sovelluksen mukautettuja entiteettejä.
- Jos mallisovellukseen on tehty mukautuksia, on ehkä syntynyt [riippuvuuksia](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components), jotka on poistettava, ennen ratkaisun poistamista.

### <a name="steps"></a>Vaiheet
1. Kirjaudu sisään [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Valitse ympäristö.

3. Napsauta **Dynamics 365 -hallintakeskus** 

    ![Dynamics 365 -hallintakeskus](media/overview-model-driven-samples/admin-center.png)

4. Valitse tietokanta luettelosta ja valitse **AVAA**.

    ![Valitse tietokanta](media/overview-model-driven-samples/select-database.png)

5. Valitse **Asetukset/Ratkaisut**.

6. Valitse poistettavan sovelluksen ratkaisu ja napsauta **Poista**.

    ![Poista ratkaisu](media/overview-model-driven-samples/delete-solution.png)

<em>Voit myös siirtyä ratkaisujen luetteloon napsauttamalla tekijän portaalissa **Lisäasetukset</em>* ja poistamalla URL-osoitteesta kaiken tekstin .dynamics.com/-merkkijonon jälkeen*

> [!IMPORTANT]
> Älä poista muita järjestelmän ratkaisuja, ellet ole tietoinen niiden vaikutuksesta.

## <a name="install-or-uninstall-sample-data"></a>Asenna mallitietoja tai poista niiden asennus
1. Noudata edellisiä vaiheita 1–4.
2. Siirry kohtaan **Asetukset/Tiedonhallinta/Mallitiedot**.
3. Jos mallitietoja on asennettu, sen poistamisvalinta on käytettävissä. Muussa tapauksessa käytettävissä on asennusvalinta. 

    ![poista mallitiedot](media/overview-model-driven-samples/remove-sample-data.png)




