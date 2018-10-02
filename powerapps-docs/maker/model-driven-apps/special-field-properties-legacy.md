---
title: Päälomakkeiden mallipohjaisen sovelluksen erityiskentän ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeiden erityiskenttäresurssin ominaisuuksista
Keywords: Main forms; Special field properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 6ad7e43c-b6a1-48c4-9dfb-ed830142a841
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>Mallipohjaisen sovelluksen erityiskentän ominaisuuksien yleiskatsaus

 Kaikissa kentissä on ominaisuuksia, jotka on esitetty [yleisissä kenttäominaisuuksissa](common-field-properties-legacy.md), mutta on tiettyjä kenttiä, joilla on muita ominaisuuksia, kuten oikeuskenttä, joka voidaan avata palvelupyynnön päälomakkeessa.  

![special-properties-dialog](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>Hakukentän ominaisuudet  
  
> [!NOTE]
>  Alla olevassa taulukossa kuvatut vaihtoehdot ovat käytettävissä vain yksittäisen entiteetin hakukenttiä varten.  
  
|Osa|Ominaisuus|Kuvaus|  
|-------------|--------------|-----------------|  
|**Liittyvien tietueiden suodattaminen**|**Näytä vain tietueet, joissa**|Kun tämä asetus on käytössä, tietuetta haettaessa näytettävissä tietueissa käytetään lisäsuodatusta. Tällä tavoin valinnan arvoa määritettäessä hauista saadaan tarkempia.<br /><br /> Tämä ominaisuus ei ole oletusarvon mukaan käytössä.<br /><br /> Tätä seuraavassa taulukossa on esitetty suhdeyhdistelmät, jotka ovat mahdollisia liittyvien tietueiden suodattamisessa.*<br /><br /> Ensimmäisessä luettelossa ovat kaikki mahdolliset suhteet, joita valinnan suodattamisessa voi käyttää. Valitse yksi.<br /><br /> Toisessa luettelossa ovat kaikki suhteet, jotka yhdistävät liittyvän entiteetin (ensimmäisestä luettelosta valitun) kohde-entiteettiin. Valitse yksi.<br /><br /> Valitse **Salli, että käyttäjät voivat poistaa suodattimen käytöstä** -valintaruutu, jos haluat, että käyttäjät voivat poistaa käytöstä tässä määrittämäsi suodattimen.<br /><br /> Kun käyttäjä napsauttaa **Valitse lisää tietueita** -vaihtoehtoa asettaessaan hakukentän arvon, tämä valintaikkuna tulee esiin.<br /><br /> ![look-up-more-records](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> Jos olet valinnut **Salli, että käyttäjät voivat poistaa suodattimen käytöstä** -vaihtoehdon määrittäessäsi hakukentän, käyttäjät näkevät valintaruudun, jolla suodatuksen voi poistaa käytöstä.  Näin käyttäjät voivat tarkastella tietueita laajemmalta alueelta. Jos haluat varmistaa, että käyttäjät näkevät vain suodattimen määrittämän rajoitetun määrän tietueita, poista **Salli, että käyttäjät voivat poistaa suodattimen käytöstä** -valintaruudun valinta.|  
|**Lisäominaisuudet**|**Näytä hakuruutu valintaikkunassa**|Voit halutessasi olla näyttämättä hakukenttää valintaikkunassa.|  
||**Oletusnäkymä**|Tällä näkymällä suodatetaan sidottua hakua ja määritetään valintaikkunan oletusnäkymä, kun käyttäjät valitsevat **Valitse lisää tietueita** -vaihtoehdon.<br /><br /> Oletusnäkymän määrittää myös sidottuun valintakenttään sisältyvät kentät.<br /><br /> Jos valintakentissä voi valita vain yhden entiteettityypin, sidotussa valintakentässä näkyviksi kentiksi määritetään oletusnäkymän kaksi ensimmäistä kenttää. Tässä esimerkissä asiakkaan valintakenttään määritetyn oletusnäkymän kaksi ensimmäistä kenttää ovat **Ensisijainen puhelin** ja **Sähköposti**.<br /><br /> Useita entiteettityyppejä sallivissa järjestelmän valintakentissä näytetään entiteetin valintanäkymän kaksi ensimmäistä saraketta.|  
||**Näkymän valitsin**|Valittavana on kolme vaihtoehtoa:<br /><br /> -   **Ei käytössä**: käyttäjät eivät voi valita toista näkymää.<br />-   **Näytä kaikki näkymät**: kaikki näkymät ovat käytettävissä.<br />-   **Näytä valitut näkymät**: Kun valitset tämän vaihtoehdon, voit valita näytettävän näkymän Ctrl-näppäimellä ja kohdistimella. Entiteetin valintanäkymän valintaa ei voi poistaa.|  
  
 **\*Mahdollisia suhdeyhdistelmiä**  
  
|Ensimmäisen luettelon suhde|Toisen luettelon suhde|Käytettävissä?|  
|-----------------------------|------------------------------|----------------|  
|N:1|1:N|Kyllä|  
|N:1|N:1|Kyllä|  
|N:1|N:N|Kyllä|  
|1:N|1:N|Kyllä|  
|1:N|N:1|No|  
|1:N|N:N|No|  
|N:N|1:N|Kyllä|  
|N:N|N:1|No|  
|N:N|N:N|No|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>Kahta vaihtoehtoa käyttävän kentän ominaisuudet  
 Kahden vaihtoehdon kentillä on muotoiluvälilehdessä seuraavat muotoiluvaihtoehdot:  
  
- **Kaksi valintanappia**: kaksi otsikollista ohjausobjektia, joista vain toinen voidaan valita.  
  
- **Valintaruutu**: yksi valintaruutu, jolla voi määrittää tosi-arvon, muutoin epätosi.  
  
- **Luettelo**: molemmat arvot sisältävä avattava luettelo.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>Useita tekstirivejä sisältävän kentän ominaisuudet  
 Kentillä, joissa on useita tekstirivejä ja yksirivinen tekstikenttä ja joissa on käytössä `Text Area`-muoto, on **Riviasettelu**-ominaisuus. Voit määrittää tällä ominaisuudella **Rivien lukumäärä** -arvon tai valita **Laajenna automaattisesti käytettävissä olevaan tilaan**.  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)
