---
title: Virtuaalisen entiteetin OData v4 -tietopalvelun käyttäminen Common Data Service for Appsissa | MicrosoftDocs
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
ms.assetid: ''
caps.latest.revision: ''
author: Mattp123
ms.author: matp
manager: brycho
ms.openlocfilehash: 0bd2aed852b5d7eb9b354f30978725b1386a89aa
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679211"
---
# <a name="odata-v4-data-provider-configuration-requirements-and-best-practices"></a>OData v4 -tietopalvelun määrittäminen, vaatimukset ja parhaat käytännöt

Tässä aiheessa kuvataan, miten voit määrittää OData v4 -tietopalvelun sekä tarvittavat vaatimukset ja suositellut parhaat käytännöt OData v4 -tietopalvelun käyttämiseen, jotta voit yhdistää OData v4 verkkopalveluun. 

## <a name="odata-v4-data-provider-best-practices"></a>OData v4 -tietopalvelun parhaat käytännöt

- Common Data Service for Apps edellyttää, että kaikissa entiteeteissä on ID-määrite. Tällaista ID-määritettä kutsutaan yksilölliseksi tunnisteeksi ja sen arvon on oltava GUID-tunnus.  Voit yhdistää ID-kenttiä vain ulkoisiin kenttiin, jotka käyttävät tietotyyppiä `Edm.Guid`.  Et voi yhdistää tietotyyppiä `Edm.Int32` yksilöllinen tunniste -tietotyyppikenttään CDS for Appsissa.
-  OData-entiteetit, jotka sisältävät tyhjäarvoja tukevia ominaisuuksia, on määritettävä vastaamaan virtuaalisen entiteetin sisällä olevaa yhdistettyä kenttää. Esimerkiksi jos kyseessä on OData-entiteettiominaisuus, jolle on määritetty Nullable=False, sen CDS for Appsin **kenttien vaatimus** -määritteen yhdistetyn kentän on oltava **Yrityksen edellyttämä**. 
- Jos haluat noutaa useita kyselyitä, esimerkiksi kun lataat tietoja ruudukkoon, voit hallita ulkoisesta tietolähteestä palautetun tietojoukon kokoa käyttämällä valitse ja suodata kyselyparametrit -ominaisuutta.
- Jos laajennuksen jäljitys ei ole vielä käytössä, järjestelmänvalvojan tulisi ottaa se käyttöön. Kun tämä ominaisuus on käytössä, kaikki virheet OData-päätepisteestä kirjataan laajennuksen jäljityslokiin. Lisätietoja: [järjestelmänvalvojan opas: järjestelmän asetukset -valintaikkuna - Mukauttaminen-välilehti](/dynamics365/customer-engagement/admin/system-settings-dialog-box-customization-tab) 

## <a name="data-type-mapping"></a>Tietotyyppien yhdistäminen

Seuraavassa taulukossa on lueteltu OData-entiteettitietomallin (EDM) tietotyyppien yhdistämismääritykset CDS for Apps -tietotyyppeihin. 

|OData-tietotyyppi|CDS for Apps -tietotyyppi  |
|---------|---------|
|`Edm.Boolean`|Kaksi vaihtoehtoa|
|`Edm.DateTime`|Päivämäärä ja aika|
|`Edm.DateTimeOffset`|Päivämäärä ja aika|
|`Edm.Decimal`|Desimaaliluku tai valuutta|
|`Edm.Double`|Liukuluku|
|`Edm.Guid`|Yksilöllinen tunniste|
|`Edm.Int32`|Kokonaisluku|
|`Edm.Int64`|Kokonaisluku|
|`Edm.String`|Yksi tekstirivi tai useita tekstirivejä|


### <a name="odata-edm-data-types-that-are-not-supported-for-mapping-with-virtual-entities"></a>OData-EDM-tietotyypit, joita ei voi yhdistää virtuaalisiin entiteetteihin 

- `Edm.Binary `
- `Edm.Time` 
- `Edm.Float `
- `Edm.Single` 
- `Edm.Int16` 
- `Edm.Byte` 
- `Edm.SByte`

 
## <a name="add-a-data-source-using-the-odata-v4-data-provider"></a>Tietolähteen lisääminen OData v4 -tietopalvelun avulla

Seuraavassa kuvataan, miten voit käyttää valmista OData-tietopalvelua virtuaalisen entiteetin tietolähteenä.   
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Hallinta** > **Virtuaalisen entiteetin tietolähteet**.  
1. Valitse toiminnot-työkaluriviltä **Uusi**.  
1. Valitse **Valitse tietopalvelu** -valintaikkunassa jokin seuraavista tietolähteistä ja valitse sitten **OK**.  
  
    - **OData v4 -tietopalvelu**. CDS for Apps sisältää OData v4 -tietopalvelun, jonka avulla voit muodostaa yhteyden tietolähteisiin, jotka tukevat OData v4 -avointa standardia.  
    - *Mukautettu tietopalvelu*. Jos olet tuonut tietopalvelun laajennuksen, tietopalvelu näkyy tässä. Lisätietoja: [Kehittäjädokumentaatio: Aloita virtuaalisten entiteettien käyttäminen](/dynamics365/customer-engagement/developer/virtual-entities/get-started-ve)  
    
1. Täytä seuraavat kentät **Uuden tietolähteen** ominaisuudet -sivulla ja tallenna sitten tietue.  
  
    - **Nimi**. Kirjoita tietolähdettä kuvaava nimi.  
    - **URI**. Jos käytät OData-tietopalvelua, anna OData-verkkopalvelun URI. Esimerkiksi jos käytät OData-palvelua muodostaaksesi yhteyden Azuressa isännöitävään verkkopalveluun, URI voi näyttää seuraavan kaltaiselta: *`http://contosodataservice.azurewebsites.net/odata/`*.  
    - **Aikakatkaisu sekunteina**. Syötä verkkopalvelun vastauksen odotukseen käytettävä aika sekunteina, jonka jälkeen tietopyyntö aikakatkaistaan. Jos syötät esimerkiksi luvun 30, maksimiodotusaika ennen aikakatkaisua on 30 sekuntia.  
    - **Sivutustila**. Valitse sivutetaanko kyselytulokset asiakaspuolen vai palvelinpuolen sivutusta käyttämällä. Oletusarvo on asiakaspuolen sivutus. Kun käytät palvelinpuolen sivutusta, palvelin ohjaa tulosten sivutusta kyselymerkkijonoon lisättävän $skiptoken-parametrin avulla. Lisätietoja: [Ohita tunnusjärjestelmän kyselyasetus ($skiptoken)](https://msdn.microsoft.com/library/dd942121.aspx)  
        -  **Palauta sisäinen määrä**. Palauttaa tulosjoukossa olevien tietueiden kokonaislukumäärän. Käytä tätä asetusta, jos haluat ottaa seuraavan sivun toiminnon käyttöön silloin, kun tiedot palautetaan ruudukkoon. Käytä arvoa False, jos OData-päätepiste ei tue OData $inclinecount -parametria. Oletusarvo on False.
    - **Pyynnön parametrit**. Voit halutessasi lisätä mukautettuja ylätunniste- tai kyselymerkkijonoparametreja, joita käytetään yhteyden muodostamiseksi OData-verkkopalveluun, kuten todentamisparametreja ulkoiseen palveluun. Valitse **Kyselymerkkijono** vaihtaaksesi ylätunniste- ja kyselymerkkijonoparametrin välillä sekä määrittääksesi sen arvon. Voit lisätä korkeintaan 10 ylätunniste- tai kyselymerkkijonoa. 
        ![Virtuaalisen entiteetin tietolähdetietue](media/virtual-entity-data-source.png) 


## <a name="see-also"></a>Katso myös  

[Ulkoisesta tietolähteestä peräisin olevia tietoja sisältävien virtuaalisten entiteettien luominen ja muokkaaminen](create-edit-virtual-entities.md) <br/>
[TechNet-blogi: Ulkoisten järjestelmien tietojen käsitteleminen uusien virtuaalisten entiteettien avulla](https://blogs.technet.microsoft.com/lystavlen/2017/09/08/virtual-entities/)
