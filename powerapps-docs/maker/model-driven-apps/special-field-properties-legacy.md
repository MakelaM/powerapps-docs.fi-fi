---
title: Malliin perustuvien sovellusten päälomakkeiden erikoiskenttien ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tutustu päälomakkeiden erityiskenttien ominaisuuksiin
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
ms.openlocfilehash: 0c4e67b14816ae6eaf100221ac0ac29269000f9b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674059"
---
# <a name="overview-of-model-driven-app-special-field-properties"></a>Malliin perustuvien sovellusten erikoiskenttien ominaisuuksien yleiskatsaus

 Kaikilla kentillä on [yleisissä kenttien ominaisuuksissa](common-field-properties-legacy.md) luetellut ominaisuudet, mutta tietyillä kentillä on lisäominaisuuksia, kuten alla esitetty oikeutuskenttä, joka voidaan avata tapausentiteetin päälomakkeesta.  

![special-properties-dialog](media/special-properties.png)
  
<a name="BKMK_LookupFieldProperties"></a>  
 
## <a name="lookup-field-properties"></a>Hakukentän ominaisuudet  
  
> [!NOTE]
>  Seuraavassa taulukossa kuvatut asetukset ovat käytettävissä vain yhden entiteetin hakukentille.  
  
|Osa|Ominaisuus|Kuvaus|  
|-------------|--------------|-----------------|  
|**Liittyvien tietueiden suodattaminen**|**Näytä vain tietueet, joissa**|Kun tämä asetus on käytössä, käyttäjän hakiessa tietuetta näkyviin tulevat ne tietueet, joissa käytetään lisäsuodatusta. Tämä auttaa saamaan osuvampia hakutuloksia, kun haun arvo määritetään.<br /><br /> Tämä asetus on oletusarvoisesti poissa käytöstä.<br /><br /> Suhdeyhdistelmät, jotka ovat mahdollisia liittyviä tietueita suodatettaessa, luetellaan tätä taulukkoa seuraavassa taulukossa.*<br /><br /> Ensimmäisessä luettelossa näkyvät kaikki mahdolliset suhteet, joita voit käyttää tämän haun suodattamisessa. Valitse niistä yksi.<br /><br /> Toiseen luetteloon tulevat nyt näkyviin kaikki suhteet, jotka yhdistävät liittyvän (ensimmäisestä luettelosta valitun) entiteetin kohde-entiteettiin. Valitse niistä yksi.<br /><br /> Valitse **Salli käyttäjille suodattimen poisto käytöstä** -valintaruutu, jos haluat antaa käyttäjille mahdollisuuden poistaa suodatin käytöstä.<br /><br /> Käyttäjä näkee tämän valintaikkunan, kun hän valitsee **Hae lisää tietueita** -vaihtoehdon haun arvoa määrittäessään.<br /><br /> ![look-up-more-records](media/crm-ua-v-8-1-look-up-more-records.png) <br /><br /> Jos valitsit **Salli käyttäjille suodattimen poisto käytöstä** -vaihtoehdon hakukenttää määrittäessäsi, käyttäjät näkevät valintaruudun, joka mahdollistaa suodattimen poistamisen käytöstä.  Tämä mahdollistaa käyttäjille laajemman tietuevalikoiman näkemisen. Jos haluat varmistaa, että käyttäjät näkevät vain tällä suodattimella määritetyn rajallisen tietuevalikoiman, poista valinta **Salli käyttäjille suodattimen poisto käytöstä** -valintaruudusta.|  
|**Lisäominaisuudet**|**Näytä hakuruutu valintaikkunassa**|Voit halutessasi poistaa hakuruudun näkyvistä valintaikkunassa.|  
||**Oletusnäkymä**|Tätä näkymää käytetään sisäisen haun tulosten suodattamiseen ja valintaikkunassa näkyvän oletusnäkymän määrittämiseen, kun käyttäjät valitsevat **Hae lisää tietueita** -vaihtoehdon.<br /><br /> Oletusnäkymä säätelee myös sitä, mitkä kentät sisältyvät sisäiseen hakuun.<br /><br /> Hauissa, jotka sallivat vain yhden entiteettityypin valinnan, sisäisessä haussa näkyviksi kentiksi määritetään kaksi ensimmäistä oletusnäkymään sisältyvää kenttää. Tässä esimerkissä **Ensisijainen puhelin** ja **Sähköposti** ovat oletusnäkymän kaksi ensimmäistä saraketta, jotka on määritetty asiakashakua varten.<br /><br /> Järjestelmän hauissa, jotka sallivat useita entiteettityyppejä, näytetään entiteetin hakunäkymän kaksi ensimmäistä saraketta.|  
||**Näkymän valitsin**|Valittavissa on kolme vaihtoehtoa:<br /><br /> -   **Ei käytössä**: käyttäjille ei sallita eri näkymän valintaa.<br />-   **Näytä kaikki näkymät**: kaikki näkymät ovat valittavissa.<br />-   **Näytä valitut näkymät**: Jos valitset tämän vaihtoehdon, voit valita näytettävät näkymät Ctrl-näppäimen ja kohdistimen avulla. Entiteetin hakunäkymän valintaa ei voida poistaa.|  
  
 **\*Mahdolliset suhdeyhdistelmät**  
  
|Ensimmäisen luettelon suhde|Toisen luettelon suhde|Käytettävissä?|  
|-----------------------------|------------------------------|----------------|  
|N:1|1:N|Kyllä|  
|N:1|N:1|Kyllä|  
|N:1|N:N|Kyllä|  
|1:N|1:N|Kyllä|  
|1:N|N:1|Ei|  
|1:N|N:N|Ei|  
|N:N|1:N|Kyllä|  
|N:N|N:1|Ei|  
|N:N|N:N|Ei|  
  
<a name="BKMK_TwoOptionProperties"></a>   

### <a name="two-option-field-properties"></a>Kahden vaihtoehdon kenttäominaisuudet  
 Muotoiluvälilehden kahdessa asetuskentässä on seuraavat muotoiluvaihtoehdot:  
  
- **Kaksi valintanappia**: Kaksi otsikoitua ohjausobjektia. Vain toinen niistä voidaan valita.  
  
- **Valintaruutu**: Yksittäinen valintaruutu, jolla arvoksi määritetään tosi. Muussa tapauksessa se on epätosi.  
  
- **Luettelo**: avattava luettelo, joka sisältää molemmat arvot.  
  
<a name="BKMK_MultipleLinesOfTextProperties"></a>   

### <a name="multiple-lines-of-text-field-properties"></a>Tekstikentän ominaisuuksien useat rivit  
 Useilla tekstiriveillä ja yksittäisellä sellaisten tekstikenttien rivillä, jotka käyttävät `Text Area` -muotoa, on **Riviasettelu**-ominaisuus. Tämän ominaisuuden avulla voit määrittää **Rivien määrä** -arvon tai valita **automaattisen laajennuksen käytettävissä olevan tilan hyödyntämiseksi**.  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja sen osien käyttäminen](use-main-form-and-components.md)
