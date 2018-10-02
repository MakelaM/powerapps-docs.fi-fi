---
title: Muokkaa järjestelmän entiteettisanomia PowerAppsin avulla | MicrosoftDocs
description: 'Opi, miten järjestelmän entiteettisanomien muokataan'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="edit-system-entity-messages"></a>Järjestelmäentiteetin sanomien muokkaaminen

Joidenkin järjestelmäentiteettien oletusnäyttönimeä käytetään Common Data Service sovelluksille -ratkaisun käyttöliittymätekstissä ja virhesanomissa. Jos haluat muuttaa näyttönimeä, päivitä myös oletusnäyttönimeä käyttävät sanomat. Jos muutat esimerkiksi *Asiakas*-näyttönimen *Yritys*-näyttönimeksi, vanha nimi näkyy yhä virhesanomassa.  

Järjestelmäsanomia ei voi muokata PowerApps-portaalissa. Niiden muokkaamisessa on käytettävä ratkaisunhallintaa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Jos entiteetin alla olevassa ratkaisunhallinnassa näkyy **Sanomat**-solmu, voit muokata tiettyjä tekstejä, jotka sisältävät viittauksen entiteetin alkuperäiseen näyttönimeen. 

![Entiteettisanomat](../model-driven-apps/media/entity-messages.png)

Tämän tekstin muokkaaminen onnistuu helposti. Kaksoisnapsauta sanomaa, jonka jälkeen näyttöön tulee lomake, joka sisältää seuraavat kolme kenttää:  
  
|Kenttä|Kuvaus|  
|-----------|-----------------|  
|**Oletusnäyttömerkkijono**|Näyttää alkuperäisen tekstin.|  
|**Mukautettu näyttömerkkijono**|Muokkaa tätä tekstiä ja muuta näyttömerkkijonoa.|  
|**Kommentti**|Valinnainen. Lisää muutoksesta ja muutoksen syystä kertova kommentti.|  
  
Joidenkin sanomien teksteissä voi olla paikanvaraajia. Paikanvaraajat ovat numeroita, joiden molemmilla puolilla on hakasulkeet. Esimerkki: `{0}`. Paikanvaraajien avulla sanomaan voi lisätä tekstiä. Jos muokkaat sanomia, varmista, että paikanvaraajat säilyvät. 

Tallenna muutokset valitsemalla ![Tallenna](media/save-entity-icon-solution-explorer.png). Valitse **Tallenna ja sulje**, kun haluat sulkea tallentamisen yhteydessä.

> [!NOTE]
> Vaikka järjestelmäentiteettisanomien muokkauksessa käytettävä käyttöliittymä sisältää useita viittauksia entiteettien nimiin, se ei sisällä niitä kaikkia. Lisätietoja monipuolisesta näkökulmasta on kohdassa [Lokalisoitavan tekstin päivittäminen asennuskielellä](../model-driven-apps/translate-localizable-text.md#updating-localizable-text-in-the-base-language)

## <a name="programmatically-update-entity-display-strings"></a>Ohjelmoidusti päivitettävän entiteetin näyttömerkkijonot

Näyttömerkkijonot tallennetaan [DisplayString](../../developer/common-data-service/reference/entities/displaystring.md)-entiteettiin. Tämä on hyödyllinen tieto sovelluskehittäjille, jotka haluavat lisätietoja näiden koodien käyttämisestä. 

`DisplayString`-entiteetti ei sisällä oletusnäyttömerkkijonoja. Tämän entiteetin kaksi tekstiä sisältävää entiteettiä ovat [CustomDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_CustomDisplayString) ja [PublishedDisplayString](../../developer/common-data-service/reference/entities/displaystring.md#BKMK_PublishedDisplayString). Oletusarvoisesti nämä määritteiden arvot ovat nollia, jos näyttömerkkijonoa ei ole mukautettu ja julkaistu. `PublishedDisplayString`-arvo on vain luku -arvo. Se kuvaa parhaillaan julkaistavaa `CustomDisplayString`-arvoa.
 
## <a name="see-also"></a>Katso myös
[Entiteetin muokkaaminen](edit-entities.md)<br />
[Mallipohjaisten sovellusten lokalisoitavan tekstin kääntäminen](../model-driven-apps/translate-localizable-text.md)
