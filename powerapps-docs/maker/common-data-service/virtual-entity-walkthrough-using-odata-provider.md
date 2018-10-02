---
title: Virtuaalinen entiteetin vaihekuvaus OData v4 -tietojen tarjoajan avulla Common Data Service sovelluksille -ratkaisussa | MicrosoftDocs
description: Opettele käyttämään OData v4 -tietojen tarjoajaa virtuaalientiteetin kanssa
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
ms.assetid: null
caps.latest.revision: 11
author: Mattp123
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="virtual-entity-walkthrough-using-the-odata-v4-data-provider"></a>Virtuaalinen entiteetin vaihekuvaus OData v4:n tietojen tarjoajan avulla

Oletetaan, että haluat käyttää ulkoisen tietolähteen palvelupyynnön tietoja mallipohjaisessa sovelluksessasi tai Dynamics 365 for Customer Engagement -sovelluksen palvelualueella. Tässä helpossa opastuksessa mallinnat virtuaalisen entiteetin, jossa on suorituksen aikana OData-verkkopalvelusta palvelupyynnön tiedot hakevaan ulkoiseen malliin yhdistetyt kentät.

## <a name="data-source-details"></a>Tietolähteen tiedot

Koska tässä opastuksessa käytetyllä tietolähteellä on OData v4 -verkkopalvelu, voimme käyttää ympäristöösi sisältyvää OData v4:n tietojen tarjoajaa.

WWW-palvelun url-osoite: `http://contosowebservice.azurewebsites.net/odata/` 

> [!IMPORTANT]
> Tässä opastuksessa käytettävä verkkopalvelun URL-osoite ei ole toimiva verkkopalvelu.

Tässä opastuksessa tarvitaan yksi virtuaalientiteetti, jossa on seuraavat kolme kenttää.

|Ulkoisen kentän nimi |Ulkoisten tietojen tyyppi |Virtuaalientiteetin tietotyyppi |Tarkoitus |
|---------|---------|---------|---------|
|TicketID |`Edm.Guid` |Ensisijainen avain |Entiteetin ensisijainen avain |
|Otsikko  |`Edm.String` |Yksi tekstirivi |Palvelupyynnön otsikko |
|Vakavuusaste |`Edm.Int32`| Kokonaisluku |Lukuarvo 0–4 ilmaisee palvelupyynnön vakavuustason |

Ulkoisen tietolähteen palvelupyyntöentiteetin OData-metatiedot:

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

## <a name="create-the-data-source"></a>Tietolähteen luominen

Luo OData v4:n tietojen tarjoajalle tietolähde, joka käyttää OData (OASIS Open Data Protocol) -näyteverkkopalvelua.

1. Siirry kohtaan **asetukset** > **hallinto** > **näennäisentiteettitietolähteet**.
1. Valitse ensin **UUSI**, sitten **OData v4 -tietojen tarjoaja** ja lopuksi **OK**.
1. Anna tai valitse seuraavat tiedot.

    |Kenttä|Arvo|
    |--|--|
    |**Nimi**|Contoso-näytetietolähde|
    |**URL-osoite**|`http://contosowebservice.azurewebsites.net/odata` |
    |**Aikakatkaisu**|30|
    |**Palauta sidottu määrä**|Tosi|

Älä muuta muiden kenttien tietoja ja valitse **TALLENNA JA SULJE**.

> [!TIP]
> Jos käytät omaa verkkopalvelua, tarkista URL-osoitteen kelvollisuus liittämällä se selaimeen. 

## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luomasi mukautetun entiteetin nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle entiteetille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]


## <a name="create-the-virtual-entity"></a>Virtuaalientiteetin luominen

1. Valitse ensin ratkaisunhallinnan vasemmassa siirtymisruudussa **Entiteetit** ja valitse sitten pääruudussa **Uusi**.
2. Valitse **Entiteetti: uusi** -lomakkeessa **Virtuaalinen entiteetti** ja anna sitten seuraavat tiedot: 

    |Kenttä|Arvo|
    |--|--|
    |**Tietolähde**|Contoso-näytetietolähde|
    |**Näyttönimi**|Palvelupyyntö|
    |**Monikkonimi**|Palvelupyynnöt|
    |**Nimi**|new_ticket|
    |**Ulkoinen nimi**|Palvelupyyntö|
    |**Ulkoinen kokoelman nimi**|Palvelupyynnöt|
    |**Muistiinpanot (myös liitteet)**|valittu|
    |**Aktiviteetit**|valittu|

1. Valitse **Alueet, joissa tämä entiteetti näkyy** -kohdan vieressä ensin **Palvelu** ja sitten **Tallenna** (mutta älä sulje entiteettilomaketta).
    ![Palvelupyynnön entiteettimääritys](media/ticket-entity.png)

## <a name="create-the-fields-for-the-virtual-entity"></a>Virtuaalientiteetin kenttien luominen

Valitse **Entiteetti: palvelupyyntö** -sivun vasemmassa siirtymisruudussa **Kentät**. Tässä opastuksessa muokataan kahta aiemmin luotua kenttää ja lisätään kolmas kenttä.

> [!IMPORTANT]
> Kirjainkoolla on merkitystä ulkoisissa nimissä. Varmista verkkopalvelujen metatiedoista, että käytät oikeaa nimeä.
> Tyhjä arvo epätosi ilmaisee, että määrite on pakollinen. Huomaa, että järjestelmä edellyttää aina ensisijaisia avainkenttiä.

1. Avaa **new_ticketid**-kenttä ja vaihda seuraavan määritteen arvoksi tässä ilmoitettu arvo: **Ulkoinen nimi**: TicketID  ![TicketID-kenttä](media/ticketid-field.png)
1. Valitse **Tallenna ja sulje**.
1. Avaa **new_name**-kenttä ja vaihda seuraavien määritteiden arvoksi tässä ilmoitetut arvot:
    - **Näyttönimi**: Otsikko
    - **Ulkoinen nimi**: Otsikko ![Otsikko-kenttä](media/title-field.png)
1. Valitse **Tallenna ja sulje**.
1. Valitse **Uusi** ja anna **Kenttä: palvelupyynnön uusi** -sivulla seuraavat tiedot:

    |Kenttä|Arvo|
    |--|--|
    |**Näyttönimi**|Vakavuusaste|
    |**Nimi**|new_severity|
    |**Ulkoinen nimi**|Vakavuusaste|
    |**Kenttävaatimus**|Pakollinen|
    |**Tietotyyppi**|Kokonaisluku|
    |**Vähimmäisarvo**|0|
    |**Enimmäisarvo**|4|

  ![Vakavuustaso-kenttä](media/severity-field.png)
1. Valitse **Tallenna ja sulje**.

## <a name="add-the-fields-to-the-main-form"></a>Kenttien lisääminen päälomakkeeseen

1. Valitse Palvelupyyntöentiteetti-ikkunassa **Lomakkeet**.
1. Avaa päälomake, vedä ja pudota **Vakavuustaso** oikeasta ruudusta lomakkeeseen, joka on **Otsikko**-kentän **Yleiset**-osassa. 
    ![Päälomakkeeseen lisätty vakavuustasokenttä](media/drop-severity-field.png)
1. Valitse Palvelupyyntöentiteetti-ikkunassa **Tallenna ja sulje**.

## <a name="configure-the-default-view"></a>Oletusnäkymän määrittäminen

1. Valitse ratkaisunhallinnan vasemman ruudun **Palvelupyyntöentiteetti**-kohdassa **Näkymät**.
1. Avaa **Kaikki palvelupyynnöt** -näkymä.
1. Valitse **Yleiset tehtävät**-ruudussa **Lisää sarakkeita**.
    ![Näkymän sarakkeiden lisääminen](media/addcolumns.png)
1. Valitse ensin **Vakavuustaso** ja sitten **OK**.
1. Valitse **Näkymä: kaikki palvelupyynnöt** -ikkunassa **Tallenna ja sulje**.
1. Valitse ratkaisunhallinnan ikkunassa **Julkaise kaikki mukautukset**.
    ![Kaikkien mukautusten julkaiseminen](media/publishall.png)
1. Kun kaikki mukautukset on julkaistu, sulje ratkaisunhallinnan ikkuna.

## <a name="view-the-virtual-entity-in-action-with-dynamics-365-customer-engagement"></a>Dynamics 365 Customer Engagementin virtuaalisen entiteetin tarkasteleminen

1. Valitse **Palvelu** > **Laajennukset** > **Palvelupyynnöt**.
    
    ![Palvelupyyntöalue](media/ticket-area.png)

    **Kaikki palvelupyynnöt** -näkymä avautuu. Huomaa, että entiteetti ei ehkä näy **Palvelu**-alueella, ennen kuin päivität selaimen.

    ![Kaikki palvelupyynnöt -näkymä](media/all-tickets-view.png)
1. Avaa **Palvelupyyntö**-tietue, jos haluat tarkastella tietyn tietueen **Otsikko**- ja **Vakavuustaso**-kentät sisältävää lomaketta.
    ![Palvelupyyntötietue](media/ticket-record.png)

### <a name="see-also"></a>Katso myös

[ OData v4 -tietojen tarjoajan määritys, vaatimukset ja parhaat käytännöt](virtual-entity-odata-provider-requirements.md)<br />
[Virtuaalisten entiteettien, jotka sisältävät ulkoisen tietolähteen tietoja, luominen ja muokkaaminen](create-edit-virtual-entities.md)
