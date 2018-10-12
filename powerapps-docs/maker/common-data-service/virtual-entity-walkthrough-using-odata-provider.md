---
title: Ohjeet virtuaalisen entiteetin OData-tietopalvelun käyttämiseen Common Data Service for Appsissa | MicrosoftDocs
description: Opi käyttämään OData v4 -tietopalvelua virtuaalisen entiteetin kanssa
ms.custom: ''
ms.date: 06/04/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
ms.assetid: ''
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
ms.openlocfilehash: ebdd8f80aad2d353d017626b7c403da93803c19b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675411"
---
# <a name="virtual-entity-walkthrough-using-the-odata-v4-data-provider"></a>Ohjeet virtuaalisen entiteetin OData v4 -tietopalvelun käyttämiseen

Kuvittele, että haluat käyttää lipputietoja ulkoisesta tietolähteestä mallipohjaisessa sovelluksessasi tai Dynamics 365 for Customer Engagementin palvelualueella. Tässä yksinkertaisessa ohjeessa mallinnat virtuaalisen entiteetin, jonka kentät on liitetty ulkoiseen kaavioon, joka noutaa lipputiedot OData-verkkopalvelusta suorituksen aikana.

## <a name="data-source-details"></a>Tietolähteen tiedot

Koska tässä ohjeessa käytettävässä tietolähteessä on OData v4 -verkkopalvelu, voimme käyttää ympäristöösi sisältyvää OData v4 -tietopalvelua.

Verkkopalvelun URL-osoite: `http://contosowebservice.azurewebsites.net/odata/` 

> [!IMPORTANT]
> Tässä ohjeessa käytettävä verkkopalvelu ei ole toiminnassa oleva verkkopalvelu.

Tarvitsemme tätä ohjetta varten yksittäisen virtuaalisen entiteetin, joka sisältää seuraavat kolme kenttää:

|Ulkoisen kentän nimi |Ulkoinen tietotyyppi |Virtuaalisen entiteetin tietotyyppi |Tarkoitus |
|---------|---------|---------|---------|
|TicketID |`Edm.Guid` |Perusavain |Entiteetin perusavain |
|Otsikko  |`Edm.String` |Yksi tekstirivi |Lipun otsikko |
|Vakavuus |`Edm.Int32`| Kokonaisluku |Numeroarvo asteikolla 0-4, joka osoittaa lipun vakavuuden |

Ulkoisen tietolähteen Lippu-entiteetin OData-metatiedot:

```xml
<EntityType Name="Ticket">
  <Key>
    <PropertyRef Name="TicketID" />
  </Key>
  <Property Name="TicketID" Nullable="false" Type="Edm.Guid" />
  <Property Name="Title" Type="Edm.String" />
  <Property Name="Severity" Nullable="false" Type="Edm.Int32" />
</EntityType>
```

## <a name="create-the-data-source"></a>Luo tietolähde

Luo tietolähde OData v4 -tietopalvelulle, joka käyttää OASIS Open Data Protocol (Odata) -malliverkkopalvelua.

1. Siirry kohtaan **Asetukset** > **Hallinta** > **Virtuaalisen entiteetin tietolähteet**.
1. Valitse **UUSI**, valitse **OData v4 -tietopalvelu**, ja valitse sitten **OK**.
1. Anna tai valitse seuraavat tiedot:

    |Kenttä|Arvo|
    |--|--|
    |**Nimi**|Contoso-mallitietolähde|
    |**URL-osoite**|`http://contosowebservice.azurewebsites.net/odata` |
    |**Aikakatkaisu**|30|
    |**Palauta sisäinen määrä**|True|

Jätä muut kentät ennalleen ja valitse **Tallenna ja sulje**.

> [!TIP]
> Jos käytät omaa verkkopalvelua, varmista, että URL-osoite on kelvollinen liittämällä se selaimeen. 

## <a name="open-solution-explorer"></a>Avaa ratkaisunhallinta

Luomasi mukautetun entiteetin nimeen sisältyy mukautusetuliite. Etuliite määräytyy käytössäsi olevan ratkaisun julkaisijan mukaan. Jos mukautusetuliitteellä on sinulle merkitystä, varmista, että käytät hallitsematonta ratkaisua, jossa mukautusetuliite on se, jota haluat käyttää kyseiselle entiteetille. Lisätietoja: [Ratkaisun julkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="create-the-virtual-entity"></a>Luo virtuaalinen entiteetti

1. Valitse ratkaisunhallinnan vasemmanpuoleisesta siirtymisruudusta **Entiteetit** ja sitten pääruudusta **Uusi**.
2. Valitse **Entiteetti: Uusi** -lomakkeessa **Virtuaalinen entiteetti** -vaihtoehto ja anna seuraavat tiedot: 

    |Kenttä|Arvo|
    |--|--|
    |**Tietolähde**|Contoso-mallitietolähde|
    |**Näyttönimi**|Lippu|
    |**Monikkomuotoinen nimi**|Liput|
    |**Nimi**|new_ticket|
    |**Ulkoinen nimi**|Lippu|
    |**Ulkoisen kokoelman nimi**|Liput|
    |**Huomautukset (mukaan lukien liitteet)**|valittu|
    |**Toiminnot**|valittu|

1. Valitse **Alueet, jotka näyttävä tämän entiteetin** -kohdassa **Palvelu**, ja valitse sitten **Tallenna** (mutta älä sulje entiteettilomaketta).
    ![Lipun entiteettimääritys](media/ticket-entity.png)

## <a name="create-the-fields-for-the-virtual-entity"></a>Luo virtuaalisen entiteetin kentät

Valitse **Entiteetti: Lippu** -sivun vasemmanpuoleisessa ruudussa **Kentät**. Tässä ohjeessa muokkaat kahta olemassa olevaa kenttää ja lisäät kolmannen kentän.

> [!IMPORTANT]
> Ulkoisissa nimissä kirjainkoko on merkitsevä. Tarkista verkkopalvelusi metatiedot varmistaaksesi, että käytät oikeaa nimeä.
> Tyhjä false-arvo tarkoittaa, että määrite vaaditaan. Huomaa, että ensisijaisen avaimen kentät vaaditaan aina järjestelmässä.

1. Avaa **new_ticketid**-kenttä ja muuta seuraava määrite tässä annetulla arvolla: **Ulkoinen nimi**: TicketID ![TicketID-kenttä](media/ticketid-field.png)
1. Valitse **Tallenna ja sulje**.
1. Avaa **new_name**-kenttä ja muuta seuraavat määritteet tässä annetuilla arvoilla:
    - **Näyttönimi**: Otsikko
    - **Ulkoinen nimi**: Otsikko ![Otsikkokenttä](media/title-field.png)
1. Valitse **Tallenna ja sulje**.
1. Valitse **Uusi** ja anna seuraavat tiedot **Kenttä: Uusi lipulle** -sivulla:

    |Kenttä|Arvo|
    |--|--|
    |**Näyttönimi**|Vakavuus|
    |**Nimi**|new_severity|
    |**Ulkoinen nimi**|Vakavuus|
    |**Kenttä on pakollinen**|Yritys on pakollinen|
    |**Tietotyyppi**|Kokonaisluku|
    |**Vähimmäisarvo**|0|
    |**Enimmäisarvo**|4|

  ![Vakavuus-kenttä](media/severity-field.png)
1. Valitse **Tallenna ja sulje**.

## <a name="add-the-fields-to-the-main-form"></a>Lisää kentät päälomakkeeseen

1. Valitse Lipun entiteetti -ikkunassa **Lomakkeet**.
1. Avaa päälomake, vedä ja pudota **Vakavuus**-kenttä oikeanpuoleisesta ruudusta lomakkeen **Yleiset**-osioon **Otsikko**-kentän alle. 
    ![Vakavuus-kenttä lisätään päälomakkeeseen](media/drop-severity-field.png)
1. Valitse Lipun entiteetti -ikkunassa **Tallenna ja sulje**.

## <a name="configure-the-default-view"></a>Määritä oletusnäkymä

1. Valitse ratkaisunhallinnan vasemmanpuoleisen ruudun **Lipun entiteetti** -kohdassa **Näkymät**.
1. Avaa **Kaikki liput** -näkymä.
1. Valitse **Yleiset tehtävät** -ruudussa **Lisää sarakkeita**.
    ![Lisää sarakkeita näkymään](media/addcolumns.png)
1. Valitse **Vakavuus**, ja valitse sitten **OK**.
1. Valitse **Näytä: Kaikki liput** -ikkunassa **Tallenna ja sulje**.
1. Valitse ratkaisunhallinnan ikkunassa **Julkaise kaikki mukautukset**.
    ![Julkaise kaikki mukautukset](media/publishall.png)
1. Kun kaikki mukautukset on julkaistu, sulje ratkaisunhallinnan ikkuna.

## <a name="view-the-virtual-entity-in-action-with-dynamics-365-customer-engagement"></a>Tarkastele virtuaalista entiteettiä toiminnassa Dynamics 365 Customer Engagementin kanssa

1. Siirry kohtaan **Palvelu** > **Laajennukset** > **Liput**.
    
    ![Lippualue](media/ticket-area.png)

    **Kaikki liput** -näkymä avautuu. Huomaa, että voit joutua päivittämään selaimen ikkunan, jotta **Palvelu**-alue tulee näkyviin.

    ![Kaikki liput -näkymä](media/all-tickets-view.png)
1. Avaa **Lippu**-tietue näyttääksesi lomakkeen, joka sisältää tietueen **Otsikko**- ja **Vakavuus**-kentät.
    ![Lipputietue](media/ticket-record.png)

### <a name="see-also"></a>Katso myös

[OData v4 -tietopalvelun määrittäminen, vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)<br />
[Ulkoisesta tietolähteestä peräisin olevia tietoja sisältävien virtuaalisten entiteettien luominen ja muokkaaminen](create-edit-virtual-entities.md)
