---
title: 'Kehittäjät: Asiakaspuolen komentosarjojen mallipohjaisten sovellusten parhaat käytännöt ja ohjeet | Microsoft Docs'
description: Asiakaspuolen komentosarjojen mallipohjaisten sovellusten parhaat käytännöt ja ohjeet kehittäjille PowerAppsissa.
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/12/2018
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: e2b43178882cb66abba2305f65f78855915591ed
ms.sourcegitcommit: 44ca0a386fce0c4a18310b515a4880065942dd05
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/12/2019
ms.locfileid: "59537823"
---
# <a name="best-practices-and-guidance-of-client-side-scripting-for-model-driven-apps"></a>Asiakaspuolen komentosarjojen mallipohjaisten sovellusten parhaat käytännöt ja ohjeet

Alla olevassa luettelossa on kaikki asiakaspuolen komentosarjojen mallipohjaisten sovellusten parhaat käytännöt ja ohjeet.

|Paras käytäntö  |Kuvaus  |
|---------|---------|
|[Vältä kohteen window.top käyttämistä](avoid-window-top.md)     |Kuvaa, miten voit välttää komentosarjavirheitä ja virheellisen käytön toimintaa, joka liittyy window.top-komennon käyttämiseen JavaScript-mukautuksissa.         |
|[Harkitse siirtymispalkin poistamista käytöstä, kun avaat ohjelmallisesti entiteettilomakkeita tai näkymiä](consider-disabling-navbar-programmatically-opening-entity-forms-views.md)|URL-osoitteen sisältävien entiteettilomakkeiden tai näkymien avaaminen saattaa hidastaa asiakkaan toimintaa suuren viiveen verkoissa, kun siirtymispalkki on käytössä.|
|[Parhaat käytännöt: Asiakkaan komentosarjat malliin perustuvissa sovelluksissa](../../clientapi/client-scripting-best-practices.md)     |Joitain parhaan käytännön vihjeitä, joita voit ottaa huomioon, kun kirjoitat mallipohjaisten sovellusten JavaScript-koodia.         |
|[Käytä HTTP- ja HTTPS-resursseja asynkronisesti](interact-http-https-resources-asynchronously.md)     |Käytä HTTP- ja HTTPS-resursseja asynkronisesti, kun kirjoitat JavaScript-asiakaslaajennuksia mallipohjaisille sovelluksille.         |
|[Poista mukautukset, jotka on poistettu käytöstä tai joiden aktivoinnit on poistettu](remove-deactivated-disabled-configurations.md)     |Käytöstä poistetut mukautukset tulee poistaa ratkaisusta ratkaisun hallinnan parantamiseksi ja vanhentuneen osan käytön tai hallinnan riskin pienentämiseksi.         |

# <a name="see-also"></a>Katso myös
[Asiakkaan komentosarjaa käyttävän liiketoimintalogiikan käyttäminen](../../client-scripting.md) <br />
 