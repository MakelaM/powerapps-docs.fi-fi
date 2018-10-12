---
title: Entiteettikenttien yhdistäminen PowerAppsissa | MicrosoftDocs
description: Lue ohjeet entiteettikenttien yhdistämiseen
ms.custom: ''
ms.date: 05/29/2018
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
ms.assetid: 7c5aa1c3-bde9-43f1-a369-fdcdbf14dec0
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: ''
ms.openlocfilehash: 7e84e10a824ea218063cb2dccdc15ed7ae2340da
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680619"
---
# <a name="map-entity-fields"></a>Entiteettikenttien yhdistäminen
 
Voit yhdistää määritteitä sellaisten entiteettien välillä, joilla on entiteettisuhde. Tällä tavalla voit määrittää oletusarvot tietueelle, joka on luotu toisen tietueen kontekstissa. 

## <a name="easier-way-to-create-new-records-in-model-driven-apps"></a>Helpompi tapa luoda uusia tietueita malliin perustuvissa sovelluksissa

Oletetaan, että käyttäjät haluavat luoda uuden yhteystietotietueen henkilölle, joka työskentelee tietyllä asiakkaalla. Tämä on mahdollista kahdella tavalla:  
  
### <a name="the-hard-way"></a>Vaikea tapa

Käyttäjät voivat siirtyä sovellukseen ja luoda uuden yhteystietotietueen kokonaan alusta asti. Mutta tällä tavalla heidän täytyy määrittää ylätason asiakastili ja antaa useita tietoja (esimerkiksi osoite- ja puhelintiedot), jotka ovat todennäköisesti samat kuin päätason asiakastilillä. Tämä voi viedä paljon aikaa ja aiheuttaa myös virheitä.  
  
### <a name="the-easier-way"></a>Helpompi tapa

Helpompi tapa on aloittaa tilin entiteetistä ja lisätä yhteystieto valitsemalla lomakkeen **yhteystietojen** alaruudukossa **+**. Tällä tavoin käyttäjät voivat etsiä olemassa olevia liittyviä yhteystietoja, jotta he eivät luo vahingossa päällekkäistä tietuetta. Jos olemassa olevaa tietuetta ei löydy, käyttäjä voi valita **Uusi** ja luoda uuden yhteystietotietueen. 

Uuden yhteystiedon tietueen lomake sisältää kaikki asiakastilin yhdistetyt määritearvot (esimerkiksi osoite- ja puhelintiedot) oletusarvoina. Käyttäjät voivat sitten muokata näitä arvoja ennen tietueen tallentamista.

## <a name="how-this-works"></a>Miten tämä toimii?

Kun yhdistät entiteettikenttiä 1:N-entiteettisuhteella, tietyt ensisijaisen entiteetin tietueen tietojen kohteet kopioidaan uuteen liittyvään entiteettilomakkeeseen. Näin voidaan määrittää oletusarvot, joita käyttäjät voivat muokata ennen tallentamista.
 
  
> [!NOTE]
> Nämä yhdistämismääritykset määrittävät oletusarvot tietueeseen vain ennen sen tallentamista. Käyttäjät voivat muokata arvoja ennen tallentamista. Tiedot, jotka siirretään, ovat tiedot sillä hetkellä. Niitä ei synkronoida, jos lähdetiedot muuttuvat myöhemmin.
>   
> Näitä yhdistämismäärityksiä ei käytetä tietueissa, jotka on luotu työnkulku- tai valintaikkunaprosessilla. Niitä ei oteta käyttöön automaattisesti uusissa koodin avulla luoduissa tietueissa. Kehittäjät voivat kuitenkin luoda uuden tietueen käytettävissä olevien yhdistämismääritysten avulla erikoisviestillä, joka on nimeltään `InitializeFrom` ([InitializeFrom Function](/dynamics365/customer-engagement/web-api/initializefrom?view=dynamics-ce-odata-9) tai [InitializeFromRequest Class](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9)).  

## <a name="open-solution-explorer"></a>Avaa ratkaisunhallinta

Entiteettikenttiä voi yhdistää vain ratkaisunhallinnassa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
Kenttien yhdistäminen tehdään 1:N- tai N:1-entiteettisuhteella, joten sinun täytyy ensin [tuoda 1:N- tai N:1-entiteettisuhteet näkyviin](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships).

## <a name="view-mappable-fields"></a>Yhdistettävissä olevien kenttien näyttäminen

Kenttien yhdistämismäärityksiä ei oikeastaan määritetä entiteettisuhteissa, mutta ne näytetään suhteiden käyttöliittymässä. Kaikilla 1:N-entiteettisuhteilla ei ole niitä. Kun tarkastelet entiteetin 1:N- tai N:1-entiteettisuhteiden luetteloa, voit suodattaa näytettävät suhteet tyypin perusteella. Voit valita suodatusasetukseksi **Kaikki**, **Mukautettu**, **Mukautettavissa** tai **Määritettävissä**. Määritettävissä olevat entiteettisuhteet mahdollistavat entiteettikenttien yhdistämisen. 

![Yhdistettävissä olevien entiteettisuhteiden näyttäminen](media/mappable-entity-relationships.png) 

Kun avaat yhdistettävissä olevan entiteettisuhteen, valitse vasemman reunan siirtymistoiminnoista **Yhdistämismääritykset**.

![Entiteettisuhteen yhdistämismääritysten valitseminen](media/map-entity-fields-ui-solution-explorer.png)

## <a name="delete-mappings"></a>Yhdistämismääritysten poistaminen

Jos et halua käyttää joitain yhdistämismäärityksiä, voit valita ne ja napsauttaa sitten kuvaketta ![Poista-kuvake](media/delete.gif) .

## <a name="add-new-mappings"></a>Uusien yhdistämismääritysten lisääminen

Jos haluat luoda uuden yhdistämismäärityksen, valitse työkaluriviltä **Uusi**. Tämä avaa näyttöön **Luo kenttien yhdistämismääritys** -valintaikkunan.

![Luo kenttien yhdistämismääritys -valintaikkuna](media/create-field-mapping-dialog.png)

Valitse yhdistettävien arvojen lähde-entiteettikenttä ja kohde-entiteettikenttä. 

![Kenttien yhdistämismääritys](media/configure-field-mapping.png)

Sulje valintaikkuna valitsemalla **OK**.

Seuraavista säännöistä näet, millaisia tietoja voi yhdistää.  
  
- Molempien kenttien täytyy olla samaa muotoa ja samaa tyyppiä.  
- Kohdekentän pituuden täytyy olla vähintään yhtä suuri kuin lähdekentän.  
- Kohdekenttä ei saa olla jo yhdistetty johonkin muuhun kenttään.  
- Lähdekentän täytyy olla näkyvissä lomakkeessa.  
- Kohdekentän täytyy olla sellainen kenttä, johon käyttäjä voi antaa tietoja.  
- Osoitetunnusarvoja ei voi yhdistää.
- Jos yhdistät kenttään tai kentästä, jota ei näytetä lomakkeessa, yhdistämistä ei tehdä, ennen kuin kenttä lisätään lomakkeeseen.
- Jos kentät ovat asetusjoukkoja, jokaisen asetuksen kokonaislukuarvojen täytyy olla identtisiä.  
  
> [!NOTE]
>  Jos haluat yhdistää asetusjoukkokenttiä, suosittelemme, että määrität molemmat kentät käyttämään samaa yleistä asetusjoukkoa. Muussa tapauksessa kahden erillisen asetusjoukon pitäminen synkronoituna manuaalisesti voi olla hankalaa. Jos jokaisen asetuksen kokonaislukuarvoja ei yhdistetä oikein, saatat aiheuttaa ongelmia tietoihisi. Lisätiedot: [Yleisten asetusjoukkojen luominen ja muokkaaminen Common Data Service for Appsissa (valintaluettelot)](create-edit-global-option-sets.md)  
  
## <a name="automatically-generate-field-mappings"></a>Kenttien yhdistämismääritysten luominen automaattisesti  

Voit myös luoda yhdistämismääritykset automaattisesti valitsemalla **Lisää toimintoja** -valikosta **Luo määritykset**.

Ole varovainen, jos aiot tehdä tämän järjestelmäentiteeteille. Käytä tätä, kun luot mukautettuja entiteettejä ja haluat hyödyntää yhdistämismäärityksiä. 

> [!WARNING]
> Automaattinen luominen poistaa kaikki olemassa olevat yhdistämismääritykset ja korvaa ne ehdotetuilla yhdistämismäärityksillä, jotka perustuvat vain kenttiin, joilla on samankaltaiset nimet ja tietotyypit. Jos teet tämän järjestelmäentiteetille, saatat menettää joitain odotettuja yhdistämismäärityksiä. Mukautetuissa entiteeteissä tämä kuitenkin säästää aikaa, koska voit poistaa helpommin kaikki yhdistämismääritykset, joita et halua, ja lisätä muita, joita yhdistämismääritysten luontitoiminto ei luonut.  


## <a name="publish-customizations"></a>Mukautusten julkaiseminen 

Koska kenttien yhdistämismääritykset eivät ole metatietoja, sinun täytyy julkaista ne, jotta muutokset tulevat voimaan. 
<!-- TODO Need a general topic about publishing to link to in situations like this -->

### <a name="see-also"></a>Katso myös
[1:N (yksi moneen)- tai N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md)<br />
[Kehittäjädokumentaatio: entiteettien ja määritteiden yhdistämismääritysten mukauttaminen](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)<br />
[Kehittäjädokumentaatio: verkko-ohjelmointirajapinta – uuden entiteetin luominen toisesta entiteetistä](/dynamics365/customer-engagement/developer/webapi/create-entity-web-api#create-a-new-entity-from-another-entity)
