---
title: Nykyisen käyttäjän tietojen näyttäminen pohjaan perustuvassa sovelluksessa | Microsoft Docs
description: Näytä PowerAppsissa pohjaan perustuvaan sovellukseen kirjautuneen käyttäjän nimen ja sähköpostiosoitteen
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/16/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 12a6cd6f3df6c83f39b08608e1057f5e31e7d46e
ms.sourcegitcommit: 90245baddce9d92c3ce85b0537c1ac1cf26bf55a
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/26/2019
ms.locfileid: "55072682"
---
# <a name="show-information-about-a-powerapps-user-in-a-canvas-app"></a>Hae tietoa PowerAppsin käyttäjästä pohjaan perustuvassa sovelluksessa

Näytä PowerAppsissa pohjaan perustuvaan sovellukseen kirjautuneen käyttäjän koko nimi, sähköpostiosoite ja kuva. Voit käyttää näitä tietoja esimerkiksi lomakkeen automaattiseen täyttämiseen.

Voit käyttää tätä ominaisuutta esimerkiksi seuraavasti:

* Luo ”kirjautumislomake” käyttäjille, jotka osallistuvat koulutukseen, ovat tarjoutuneet vapaaehtoisiksi tapahtumiin, kirjautuneet kioskipalveluun ja moniin muihin tarkoituksiin.
* Näytä koko nimi henkilöstöhallintosovelluksessa.
* Anna sähköpostiosoite automaattisesti, kun otat yhteyttä organisaatiosi tukipalveluun.

Periaatteessa voit käyttää tätä kaikissa tilanteissa, joissa käyttäjä hyötyy lomakkeiden tai selitteiden automaattisesta täyttämisestä

[!INCLUDE [app-customization-requirements](../../includes/app-customization-requirements.md)]

## <a name="show-user-details"></a>Käyttäjän tietojen näyttäminen

1. Napsauta tai napauta **Lisää**-välilehdeltä **Media** ja napsauta tai napauta **Kuva**.
   
   ![][2]
2. Määritä **[Image](controls/properties-visual.md)**-ominaisuudeksi tämä kaava:
   <br>**User().Image**
   
    ![][3]
3. Napsauta tai napauta **Lisää**-välilehdeltä **Text** ja napsauta tai napauta sitten **Selite**:  
   
    ![][4]
4. Aseta **[Text](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**User().FullName**
   
   ![][6]
   
   Kun toimit näin, selitteeseen täytetään automaattisesti koko nimesi. Siirrä selite Kuva-ohjausobjektin alapuolelle, kuten seuraavassa:
   
   ![][5]
5. Lisää toinen selite ja aseta sen **[Text](controls/properties-core.md)**-ominaisuudeksi tämä kaava:
   <br>**User().Email**  
   
    ![][8]
   
    Näin selitteeseen täytetään automaattisesti sähköpostiosoitteesi. Siirrä selite ensimmäisen selitteen alapuolelle, kuten seuraavassa:  
   
    ![][7]

[2]: ./media/show-current-user/add-image.png
[3]: ./media/show-current-user/imageproperty.png
[4]: ./media/show-current-user/insertlabel.png
[5]: ./media/show-current-user/label.png
[6]: ./media/show-current-user/textproperty.png
[7]: ./media/show-current-user/secondlabel.png
[8]: ./media/show-current-user/email.png
[9]: ./media/show-current-user/preview.png
