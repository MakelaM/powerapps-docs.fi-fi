---
title: Järjestelmän entiteettiviestien muokkaaminen PowerAppsissa | MicrosoftDocs
description: Lue, miten voit muokata järjestelmän entiteettiviestejä
ms.custom: ''
ms.date: 05/15/2018
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
ms.assetid: 3ccbd8de-8d6f-4058-87f7-15463667cfc6
caps.latest.revision: 41
ms.author: matp
manager: kvivek
ms.openlocfilehash: 797d6855bea421abd90752dd9ae0ad73a9d92f38
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39678611"
---
# <a name="edit-system-entity-messages"></a>Järjestelmän entiteettiviestien muokkaaminen

Common Data Service for Apps käyttää joidenkin järjestelmäentiteettien oletusarvoisia näyttönimiä käyttöliittymän teksteissä ja virheilmoituksissa. Jos muutat jonkin näyttönimen, muista päivittää myös kaikki viestit, jotka käyttävät oletusarvoista näyttönimeä. Esimerkiksi jos muutat näyttönimen niin, että *Tili* on nyt *Yritys*, saatat silti nähdä virhesanomia, jotka käyttävät vanhaa nimeä.  

Et voi muokata järjestelmän viestejä PowerApps-portaalin kautta, vaan sinun on käytettävä ratkaisunhallintaa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Jos näet ratkaisunhallinnassa entiteetin alla olevan **Sanomat**-solmun, voit muokata tiettyjä tekstejä, jotka sisältävät viittauksia alkuperäiseen entiteetin näyttönimeen. 

![Entiteettisanomat](../model-driven-apps/media/entity-messages.png)

Tämän tekstin muokkaaminen on helppoa. Kaksoisnapsauta sanomaa, jonka jälkeen näytölle ilmestyy lomake, jossa on kolme kenttää:  
  
|Kenttä|Kuvaus|  
|-----------|-----------------|  
|**Oletusarvoinen näyttömerkkijono**|Näyttää alkuperäisen tekstin.|  
|**Mukautettu näyttömerkkijono**|Muokkaa tätä tekstiä muuttaaksesi näyttömerkkijonon.|  
|**Kommentti**|Valinnainen. Voit kirjoittaa kommentin siitä, mitä olet muuttanut ja miksi.|  
  
Jotkin sanomatekstit saattavat sisältää paikkamerkkejä. Nämä paikkamerkit ovat hakasulkeilla ympäröityjä numeroita. Esimerkiksi: `{0}`. Näitä paikkamerkkejä käytetään tekstin lisäämiseksi sanomiin. Jos muokkaat viestejä, muista säilyttää nämä paikkamerkit. 

Tallenna muutoksesi valitsemalla ![Tallenna](media/save-entity-icon-solution-explorer.png). Jos haluat sulkea lomakkeen tallennuksen jälkeen, valitse **Tallenna ja sulje**.

> [!NOTE]
> Järjestelmän entiteettiviestien muokkaamista varten näytetty käyttöliittymä sisältää lukuisia viittauksia entiteettinimiin, mutta se ei sisällä niitä kaikkia. Jos haluat tutustua kattavampaan lähestymistapaan, katso [Peruskielen lokalisoitavan tekstin päivittäminen](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language)

## <a name="programmatically-update-entity-display-strings"></a>Entiteetin näyttömerkkijonojen päivittäminen ohjelmallisesti

Jos olet kehittäjä ja haluat käsitellä näitä koodissasi, näyttömerkkijonot on tallennettu [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md)-entiteettiin. 

`DisplayString`-entiteetti ei sisällä oletusarvoisia näyttömerkkijonoja. Tämän entiteetin tekstiä sisältävät määritteet ovat [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) ja [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString). Oletusarvon mukaan nämä määritearvot ovat tyhjäarvoja, ellei näyttömerkkijonoja ole mukautettu ja julkaistu. `PublishedDisplayString`-arvo on vain luku -tilassa ja kuvastaa nykyistä julkaistua `CustomDisplayString`.
 
## <a name="see-also"></a>Katso myös
[Entiteetin muokkaaminen](edit-entities.md)<br />
[Mallipohjaisten sovellusten lokalisoitavan tekstin kääntäminen](../model-driven-apps/translate-localizable-text.md)
