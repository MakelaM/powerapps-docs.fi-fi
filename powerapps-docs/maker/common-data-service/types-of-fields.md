---
title: Common Data Servicen kenttien tietotyypit | MicrosoftDocs
description: Tietoja sovelluksen käytettävissä olevista kenttien tietotyypeistä
keywords: ''
ms.date: 06/27/2018
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 734b4ffa-5543-4f88-8517-299589f433f7
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="types-of-fields"></a>Kenttätyypit

Tyyppien nimet riippuvat käytetystä suunnitteluohjelmasta. [PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) käytäntö sisältää tietojen muotoilutavan. Ratkaisunhallinnan tyyppi käyttää nimeä, joka on kohdistettu tietokannan tietotyypin ja muodon muokkaajan kanssa. Seuraavassa taulukossa on vastaava `AttributeTypeDisplayName`-ohjelmointirajapinnan tyyppi

|Portaalin tietotyyppi |Ratkaisunhallinnan tyyppi| Ohjelmointirajapinnan tyyppi|
|--|--|--|
|**Suuri kokonaisluku**|**Aikaleima**|`BigIntType`|
|**Valuutta**|**Valuutta**|`MoneyType`|
|**Asiakas**|**Asiakas**|`CustomerType`|
|**Päivämäärä ja aika**|**Päivämäärä ja aika**<br />*Päivämäärä ja aika* -muoto|`DateTimeType`|
|**Vain päivämäärä**|**Päivämäärä ja aika**<br />*Vain päivämäärä* -muoto|`DateTimeType`|
|**Desimaaliluku**|**Desimaaliluku**|`DecimalType`|
|**Kesto**|**Kokonaisluku**<br />*Kesto*-muoto|`IntegerType`|
|**Sähköposti**|**Yksi tekstirivi**<br />*Sähköposti*-muoto|`StringType`|
|**Liukuluku**|**Liukuluku**|`DoubleType`|
|**Kuva**|**Kuva**|`ImageType`|
|**Kieli**|**Kokonaisluku**<br />*Kieli*-muoto|`IntegerType`|
|**Valinta**|**Valinta**|`LookupType`|
|**Monivalinta-asetusjoukko**|**MultiSelect-asetusjoukko (monivalinta)**|`MultiSelectPicklistType`|
|**Monirivinen teksti**|**Useita tekstirivejä**|`MemoType`|
|**Asetusjoukko**|**Asetusjoukko**|`PicklistType`|
|**Omistaja**|**Omistaja**|`OwnerType`|
|**Puhelin**|**Yksi tekstirivi**<br />*Puhelin*-muoto|`StringType`|
|**Tilan syy**|**Tilan syy**|`StatusType`|
|**Tila**|**Tila**|`StateType`|
|**Tekstialue**|**Yksi tekstirivi**<br />*Tekstialue*-muoto|`StringType`|
|**Teksti**|**Yksi tekstirivi**<br />*Teksti*-muoto|`StringType`|
|**Osaketunnus**|**Yksi tekstirivi**<br />Kaupankäyntitunnus-muoto|`StringType`|
|**Aikavyöhyke**|**Kokonaisluku**<br />*Aikavyöhyke*-muoto|`IntegerType`|
|**Kaksi asetusta**|**Kaksi asetusta**|`BooleanType`|
|**Yksilöllinen tunnus**|**Yksilöllinen tunnus** tai **perusavain**|`UniqueidentifierType`|
|**URL-osoite**|**Yksi tekstirivi**<br />*URL-osoite*-muoto|`StringType`|
|**Kokonaisluku**|**Kokonaisluku**<br />*Ei mitään* -muoto|`IntegerType`|

Lisätietoja lisättävistä ja muokattavista tyypeistä on vastaavan suunnitteluohjelman ohjeaiheessa:
 - [Common Data Servicen kenttien luominen ja muokkaaminen PowerApps-portaalin avulla: Kentän tietotyypit](create-edit-field-portal.md#field-data-types)
 - [Common Data Servicen kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla: Kentän tietotyypit](create-edit-field-solution-explorer.md#field-data-types)

Lisätietoja kentän tietotyyppien määrittämisestä ohjelmointirajapinnassa on kohdassa [Määritteen metatiedot](/powerapps/developer/common-data-service/entity-attribute-metadata)

## <a name="field-types-used-by-the-system"></a>Järjestelmän käyttämät kenttätyypit

Järjestelmässä on käytössä joitakin kenttiä, joita ei voi lisätä suunnitteluohjelman avulla.

|Tyyppi|Kuvaus|
|--|--|
|**Suuri kokonaisluku** tai **Aikaleima**|Järjestelmän käytössä entiteetin päivitysten hallinnan versionumeron sieppaamista varten.|
|**Asiakas**|Hakukenttä, jonka avulla voit määrittää asiakkaan, joka voi olla asiakkuus tai yhteyshenkilö.<br />**Huomautus**: Tämä määrite voidaan lisätä ratkaisunhallinnan suunnitteluohjelman avulla.|
|**Omistaja**|Järjestelmän valintakenttä, joka viittaa käyttäjän tai ryhmän omistamaan tietueeseen, jolle on delegoitu käyttäjä tai ryhmä.|
|**Tilan syy**|Järjestelmäkenttä, jonka asetuksilla saa lisätietoja Tila-kentästä. Kukin asetus on liitetty yhteen käytettävissä olevaan tila-asetukseen. Voit lisätä asetuksia ja muokata niitä. <br /><br /> Voit myös sisällyttää mukautettuja tilasiirtymiä tiettyjen entiteettien tilavaihtoehtojen hallitsemiseksi. Lisätietoja: [Muokattujen entiteettien tilan syyn siirtojen määrittäminen](define-status-reason-transitions.md)|
|**Tila**|Järjestelmäkenttä, jonka asetukset yleensä vastaavat aktiivista ja passiivista tilaa. Joissakin järjestelmämääritteissä on lisäasetuksia mutta mukautetuissa määritteissä on vain tila-asetukset **Aktiivinen** ja **Passiivinen**.  |
|**Yksilöllinen tunnus**|Järjestelmäkenttä tallentaa kunkin tietueen GUID-tunnuksen arvon.|

  
## <a name="multiselect-option-set"></a>MultiSelect-asetusjoukko (monivalinta)

Voit mukauttaa lomakkeita (pää, pikaluonti ja pikanäkymä) ja sähköpostimalleja lisäämällä monivalintakenttiä. Kun lisäät monivalinta-asetusjoukkokentän, voit määrittää kentälle useita arvoja käyttäjien valittaviksi. Kun käyttäjät täyttävät lomakkeen, he voivat valita yhden arvon, useita arvoja tai kaikki arvot avattavasta luettelosta.

Jos organisaatio esimerkiksi toimii useilla alueilla tai useissa maissa, voit sisällyttää useita sijainteja tai maita Toiminta-alue-kenttään. Käyttäjä voi siten valita valittavista olevista arvoista yhden arvon tai useita arvoja.

Monivalinta-asetusjoukkoa on käytettävissä ainoastaan vain luku -ruudukoissa, muokattavissa ruudukoissa ja lomakkeissa. Monivalinta-asetusjoukkoa ei tueta 
- työnkuluissa, toiminnoissa, valintaikkunoissa, koonneissa, kaavioissa eikä laskennallisissa kentissä
- raporteissa, palvelutasosopimuksissa eikä reitityssäännöissä.

Monivalinta-asetusjoukkoa tuetaan seuraavissa lomaketyypeissä:

|Lomaketyyppi|Käytettävyys|
|--|--|
|**Turbolomake**|Kyllä|
|**Päivityslomake**|Vain luku (kenttä on käytettävissä mutta ei muokattavissa)|
|**Vanha lomake**|No|
|**Joukkomuokkauslomake**|No|

Voit määrittää monivalinta-asetusjoukkojen arvot organisaatiossa määritettyjen yleisten asetusjoukkojen avulla.


<a name="BKMK_UsingTheRightTypeOfNumber"></a>
  
## <a name="using-the-right-type-of-number"></a>Oikean numerotyypin käyttäminen

Oikeanlaista numerokenttää valittaessa **Kokonaisluku**- tai **Valuutta**-tyypin käyttöön valitsemisen pitäisi olla melko yksinkertaista. **Liukuluku**- tai **Desimaali**-asetuksen valitseminen sen sijaan edellyttää hieman enemmän harkintaa.  
  
Desimaaliluvut tallennetaan tietokantaan täsmälleen määritetyssä muodossa. Liukuluvut tallentavat arvon erittäin tarkan likiarvon. Miksi kannattaa valita erittäin tarkka likiarvo, kun käytössä on tarkka arvo? Selitys liittyy järjestelmän erilaiseen suorituskykyyn.  
  
Käytä desimaaleja, kun sinun on tehtävä raportteja, joissa on käytettävä erittäin tarkkoja laskutoimituksia, tai jos käytät yleensä kyselyjä, joissa valitaan arvoja, jotka ovat yhtä suuria tai eri suuria kuin jokin toinen arvo.  
  
Käytä liukulukuja, kun tallennat tietoja, jotka edustavat murtolukuja tai arvoja, joista yleensä haluat tehdä kyselyn vertaamalla niitä toiseen arvoon käyttämällä suurempi kuin- tai pienempi kuin -operaattoreita. Useimmissa tapauksissa desimaali- ja liukuluvun välistä eroa ei huomaa. Jos sinun ei tarvitse käyttää erittäin tarkkoja laskutoimituksia, liukuluvut toimivat luultavasti odotetusti.  
  
<a name="BKMK_UsingCurrencyFields"></a>
 
## <a name="using-currency-fields"></a>Valuuttakenttien käyttäminen

Organisaatiot voivat määrittää valuuttakentissä useita valuuttoja käytettäväksi organisaation tietueissa. Kun organisaatioissa on useita valuuttoja, ne haluavat yleensä käyttää perusvaluuttaa suorittaessaan laskutoimituksia, joilla saadaan arvoja. Kun lisäät valuuttakentän entiteettiin, jossa ei ole muita valuuttakenttiä, lisätään myös kaksi muuta kenttää:  
  
- **Valuutta**-valintakenttä, jonka arvoksi voit määrittää minkä tahansa organisaatiolle määritetyn aktiivisen valuutan. Voit määrittää organisaatioon useita aktiivisia valuuttoja valitsemalla **Asetukset** > **Yrityksen hallinta** > **Valuutat**. Voit sitten määrittää valuutan ja vaihtokurssin organisaatioon määritettyyn perusvaluuttaan verrattuna. Jos aktiivisia valuuttoja on useita, voit lisätä lomakkeeseen valuuttakentän, jolloin käyttäjät voivat määrittää, mitä valuuttaa on käytettävä tämän tietueen raha-arvoissa. Tämä muuttaa lomakkeen valuuttakentissä näkyvän rahayksikön tunnuksen.  
  
  Käyttäjät voivat myös muuttaa omat asetuksensa valitsemaan oletusvaluutan luomissaan tietueissa.
  
- **Vaihtokurssi**-desimaalikenttä ilmoittaa valitun, entiteettiin liitetyn valuutan vaihtokurssin suhteessa perusvaluuttaan. Jos tämä kenttä on lisätty lomakkeeseen, käyttäjät näkevät arvon mutta eivät voi muokata sitä. Vaihtokurssi tallennetaan valuutan kanssa.  
  
Aina kun lisäät uuden valuuttakentän, lisätään myös uusi valuuttakenttä, jonka nimessä on jälkiliitteenä `_Base`. Tähän kenttään tallennetaan lisätyn valuuttakentän laskettu arvo ja perusvaluutta. Jos tämä kenttä lisätään lomakkeeseen, myöskään sitä ei voi muokata.  
  
Voit valita valuuttakenttää määritettäessä tarkkuusarvon. Seuraavassa taulukossa on kolme vaihtoehtoa.  
  
|Asetus|Kuvaus|  
|------------|-----------------|  
|Hinnoittelussa käytettävä desimaalien määrä|Tätä yhden organisaation tarkkuutta käytetään hinnoissa ja sen voi hakea valitsemalla **Asetukset** > **Hallinta** > **Järjestelmäasetukset** > **Yleinen välilehti**.|  
|Rahasummien desimaalien määrä|Tämä asetus koskee tietueen valuutan tarkkuuden määritystä.|  
|Tarkat tarkkuusarvot|Näiden asetusten avulla voi määrittää tarkan tarkkuusarvon käyttämällä arvoja 0 ja 4.|  
  
<a name="BKMK_DifferentTypesOfLookups"></a> 
  
## <a name="different-types-of-lookups"></a>Erityyppiset valintakentät  

Uuden valintakentän luominen luo uuden N:1 (monta yhteen) -entiteettisuhteen käsiteltävän entiteetin ja valintakentälle määritetyn **kohdetietuetyypin** välille. Tätä suhdetta koskevia määrityksen lisäasetuksia esitellään kohdassa [Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md). Kaikista mukautetuista valintakentistä voi kuitenkin viitata vain yhden kohdetietuetyypin yhteen tietueeseen.  
  
Muista kuitenkin, että kaikki valintakentät eivät toimi tällä tavalla. Seuraavaksi esitellään erilaisia järjestelmän valintakenttätyyppejä.  
  
|Valintatyyppi|Kuvaus|  
|-----------------|-----------------|  
|**Pelkistetty**|Sallii yhden viittauksen tiettyyn entiteettiin. Kaikki mukautetut valintakentät ovat tämän tyyppisiä.|  
|**Asiakas**|Sallii yhden viittauksen joko asiakas- tai yhteyshenkilötietueeseen.|  
|**Omistaja**|Sallii yhden viittauksen joko ryhmä- tai käyttäjätietueeseen. Kaikissa ryhmän tai käyttäjän omistamissa entiteeteissä on yksi näistä.|  
|**Osapuoliluettelo**|Sallii useat viittaukset useisiin entiteetteihin. Nämä valintakentät sijaitsevat sähköpostientiteetin **Vastaanottaja-** and **Kopio**-kentissä. Niitä käytetään myös puhelinnumero- ja tapaaminen-entiteeteissä.|  
|**Liittyy**|Sallii yhden viittauksen useisiin entiteetteihin. Nämä valintakentät sijaitsevat aktiviteeteissa käytetyssä Liitteyen-kentässä.|  

<a name="BKMK_ImageFields"></a>

## <a name="image-fields"></a>Kuvakentät  

Käytä kuvakenttää näyttämään sovelluksessa yksi kuva tietuetta kohden. Kussakin entiteetissä voi olla vain yksi kuvanäkymä. Voit lisätä kuvakentän mukautettuihin entiteetteihin, mutta et vakioentiteetteihin. Joillekin vakioentiteeteille on määritetty kuvakenttiä.
  
Vaikka entiteetissä on kuvakenttä, kuvan näyttäminen mallin perustuvassa sovelluksessa edellyttää yhden lisävaiheen tekemistä. Entiteettimääritelmän **Ensisijainen kuva** -kentän arvot ovat joko **[Ei mitään]** tai **Entiteetin kuva**. Valitse **Entiteetin kuva**, jos haluat näyttää kuvan sovelluksessa.  
  
Kun kuvan näyttö on otettu käyttöön entiteetissä, kaikissa tietueissa, joissa ei ole kuvaa, näkyy paikkamerkkikuva. Esimerkkejä:

![Paikkamerkkikuva](../common-data-service/media/lead-entity-form.PNG)
  
Käyttäjät voivat ladata kuvan tietokoneesta valitsemalla oletuskuvan. Kuvien enimmäiskoko on 5 120 kt ja sen muodon on oltava jokin seuraavista:  
  
- jpg
- jpeg
- gif
- tif
- tiff
- bmp
- png
  
Ladattu kuva muunnetaan .jpg-muotoon, ja kaikki ladatut kuvat käyttävät tätä muotoa. Ladatusta animoidusta .gif-tiedostosta tallennetaan vain ensimmäinen ruutu.  
  
Ladattavan kuvan koko muutetaan 144 x 144 kuvapisteen enimmäiskokoon. Käyttäjät voivat muuttaa kuvien kokoa tai rajata niitä ennen lataamista, sillä ne näkyvät tämän kokoisina hyvin. Kaikki kuvat on rajattu neliönmuotoisiksi. Jos kuvan molemmat reunat ovat pienemmät kuin 144 kuvapistettä, kuva rajataan neliönmuotoiseksi käyttämällä pienemmän reunan mittoja.  

Seuraavassa on lisätietoja kuvatietoja käsitteleville sovelluskehittäjille:
- [Entiteetin metatiedot > Entiteettikuvat](/powerapps/developer/common-data-service/entity-metadata#entity-images)
- [Dynamics 365 Customer Engagementin sovelluskehittäjän opas: Kuvan määritteet](/dynamics365/customer-engagement/developer/image-attributes)
