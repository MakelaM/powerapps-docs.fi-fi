---
title: Laskennallisten kenttien määrittäminen PowerAppsissa | MicrosoftDocs
description: Laskennallisten kenttien määrittäminen
ms.custom: ''
ms.date: 05/25/2018
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
ms.assetid: 6d58a297-2ddf-4236-be3a-47249b49d5fa
caps.latest.revision: 67
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-calculated-fields-to-automate-manual-calculations"></a>Voit automatisoida manuaalisen laskennan laskettujen kenttien määrittämiseen

Voit käyttää laskennallisia kenttiä liiketoimintaprosessien manuaalisten laskentojen automatisointiin. 

Myyjä voi esimerkiksi haluta tietää mahdollisuuden painotetun tuoton, joka perustuu mahdollisuuden arvioituun tuottoon kerrottuna todennäköisyydellä. Tai he haluavat kohdistaa automaattisesti alennuksen, jos tilauksen arvo on suurempi kuin 500 €. Laskennallinen kenttä sisältää arvoja, jotka saadaan tuloksena yksinkertaisista laskutoimituksista tai ehdollisista operaattoreista, kuten esimerkiksi suurempi kuin- tai jos-muuten-rakenne. Tämä voidaan tehdä PowerAppsin avulla ilman koodin kirjoittamista.  
  
## <a name="capabilities"></a>Toiminnot
  
- Laskennallisissa kentissä käytetään nykyisen entiteetin tai liittyvien ylätason entiteettien kenttiä.  
- Lauseketuki on saatavana nykyiselle entiteetille ja liittyville pääentiteetin kentille **Ehto**- ja **Toiminto**-osassa. Sisäänrakennetut funktiot ovat seuraavat:  
 **ADDHOURS**, **ADDDAYS**, **ADDWEEKS**, **ADDMONTHS**, **ADDYEARS**, **SUBTRACTHOURS**, **SUBTRACTDAYS**, **SUBTRACTWEEKS**, **SUBTRACTMONTHS**, **SUBTRACTYEARS**, **DIFFINDAYS**, **DIFFINHOURS**, **DIFFINMINUTES**, **DIFFINMONTHS**, **DIFFINWEEKS**, **DIFFINYEARS**, **CONCAT**, **TRIMLEFT** ja **TRIMRIGHT**.  
- Monipuolinen ehtotuki mahdollistaa haarautumisen ja useat ehdot. Loogisia operaattoreita ovat **JA**- ja **TAI**-operaattorit.  
- Visuaalisia muokkausominaisuuksia ovat moderni käyttöliittymä ja IntelliSense **TOIMINTO**-osassa. 
- Laskennallisten kenttien ja lomakkeiden, näkymien, kaavioiden ja raporttien saumaton integrointi on käytettävissä reaaliaikaisena.  
- Voit määrittää laskennalliset kentät niin, että ne käyttävät mukautettuja ohjausobjekteja.  
  
  
## <a name="scenarios"></a>Skenaariot
  
- **Painotettu myyntituotto**: Arvioitu myyntituotto kerrottuna todennäköisyydellä  
- **Nettoarvo**: Omaisuudesta vähennetään annetun asiakkaan velat  
- **Työkustannukset**: Perushinta 40 tuntiin asti lisättynä ylityöllä  
- **Yhteyshenkilön numero**: Mahdollisuuden puhelinnumero asiakkaan tai yhteyshenkilön perusteella  
- **Liidin pisteet**: Kenttä, jossa on katsaus annetun liidin laatuun  
- **Seuranta mihin mennessä**: Toiminnon seuranta päivien tietyn lukumäärän mukaan prioriteetin perusteella  
  
> [!IMPORTANT]
>  Laskennallisen kentän luomiseen tarvitaan [kentän suojausprofiilientiteetin](/powerapps/developer/common-data-service/reference/entities/fieldsecurityprofile) kirjoitusoikeudet. Jos laskennallinen kenttä käyttää laskennassa suojattuja kenttiä, myös laskennallisen kentän suojaamista kannattaa harkita, sillä se estää käyttäjiä käyttämästä tietoja, joiden käyttöoikeuksia heillä ei ole. Jos olet luomassa laskennallista kenttää, joka käyttää laskennassa suojattuja kenttiä, laskennallisen kentän editori antaa varoituksen ja ehdottaa laskennallisen kentän suojaamista. Lisätietoja: [Käytön hallinta kenttätason suojauksen avulla](/dynamics365/customer-engagement/admin/field-level-security)  

## <a name="create-a-calculated-field"></a>Laskennallisen kentän luominen

Määritä laskennallinen kenttä kenttäeditorin avulla. Tässä esimerkissä käytetään [PowerAppsia](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), mutta ratkaisunhallinnan käyttämisen vaiheet ovat samanlaiset. Lisätietoja: [Kenttien luominen ja muokkaaminen](create-edit-fields.md)
  
1. Avaa [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)
1. Laajenna **Tiedot** > **Entiteetit**.  
1. Valitse haluamasi entiteetti ja valitse sitten **Kentät**. Valitse **Lisää kenttä**.  
1. Anna vaadittavat kentän tiedot, mukaan lukien **näyttönimi**, **nimi** ja **tietotyyppi**. 
1. Jos tietotyyppi on jokin laskennallisia kenttiä tukevista tyypeistä, voit määrittää kentän laskennalliseksi kentäksi valitsemalla **Lisää** > **Laskutoimitus**.

    ![Kentän määrittäminen laskennalliseksi](media/make-field-calculated-maker.png)

    Laskutoimituksia tukevat kenttätyypit ovat seuraavat:
    - Teksti
    - Asetusjoukko  
    - Kaksi asetusta  
    - Kokonaisluku  
    - Desimaaliluku  
    - Valuutta  
    - Päivämäärä ja aika

1. Kun valitset **Laskutoimitus**, entiteetin muutokset on tallennettava. Jatka valitsemalla **Tallenna** **Odottavat muutokset** -valintaikkunassa.
1. Laskennallisen kentän määrityseditori avautuu. Siinä on luotu laskennallinen kenttä, mutta kaavaa ei ole määritetty. Laskennallisen kentän määritys sisältää kaksi osaa, jotka ovat **EHTO** ja **TOIMINTO**.  
  ![Uuden kentän laskutoimituslomake](media/empty-field-calculation.png)
- Voit määrittää **Ehto**-osassa entiteetin, kentän, operaattorin, tyypin ja arvon. **Entiteetti**-luetteloruudusta valitaan nykyinen entiteetti tai liittyvä entiteetti. **Kenttä**-luetteloruutu sisältää entiteetin kaikki käytettävissä olevat kentät. Tyyppi ja arvo on määritettävä valitusta operaattorista riippuen. Voit määrittää useita ehtoja `AND`- tai `OR`-operaattoreilla.  
- **Toiminto**-osassa määritetään laskennallisen kentän kaava.  
  
> [!NOTE]
>  Voit käyttää valintatietueiden tietoja toiminnossa. Valitse ensin hakukenttä ja kirjoita sitten kausi. Tämän jälkeen voit valita jonkin liittyvässä entiteetissä käytettävissä olevan kentän. Jos kysymyksessä on *`<LookupFieldName>.<RelatedFieldName>`*, voit valita seuraavan: `ParentAccountId.AccountNumber`.  
>   
>  Huomaa, että kenttätason suojaus ohitetaan liittyvässä entiteetissä, joten jos käytettävässä kentässä on luottamuksellisia tietoja, kannattaa suojata myös laskettu kenttä.  


<a name="BusinessScenarios"></a> 
  
## <a name="examples"></a>Esimerkit  

Esittelemme esimerkkejä laskennallisista kentistä tarkemmin. 
  
### <a name="weighted-revenue-of-opportunity"></a>Mahdollisuuden painotettu myyntituotto

Tässä esimerkissä painotetun myyntituoton laskemiseen käytetään mahdollisuusentiteetin kenttiä mahdollisuuden todennäköisyyden mukaan. Mahdollisuusentiteetin kenttäeditorissa luodaan kenttä nimeltä **Painotettu myyntituotto** ja määritetään kentän tyypiksi **Laskennallinen**. Tietotyyppi on **Valuutta**.

Määritetään laskennallisen kentän määrityseditorin **Ehto**-osan mahdollisuuden tilaksi Avoin. Kaava laskee **TOIMINTO**-osassa painotetun myyntituoton mahdollisuuden todennäköisyydellä kerrotun mahdollisuuden arvioidun myyntituoton perusteella.  Seuraavissa näyttökuvissa esitetään **painotetun myyntituoton** laskennallisen kentän määritys vaihe vaiheelta.  
  
#### <a name="set-the-condition-on-the-opportunities"></a>Määritä mahdollisuuksien ehto:
  
![Painotetun myyntituoton määrittäminen Dynamics 365:ssä](media/calc-field-open-opportunity.png)  
  
#### <a name="provide-the-formula-for-the-weighted-revenue"></a>Määritä painotetun myyntituoton kaava: 
  
![Painotetun myyntituoton arvioidun arvon asettaminen Dynamics 365:ssä](media/calc-field-open-opportunities-3.png)  
  
#### <a name="altogether"></a>Yhteensä:
  
![Painotettu myyntituotto arvioiduksi myyntituotoksi Dynamics 365:ssä](media/calculated-field-open-opportunity.png)  
  
### <a name="follow-up-date-of-opportunity"></a>Mahdollisuuden seurantapäivä 
 
Tässä esimerkissä lasketaan mahdollisuudelle sopiva seurantapäivä mahdollisuuden alkuperäisen liidin kenttien avulla. 

Mahdollisuusentiteetin kenttäeditorissa luodaan kenttä nimeltä **Seurantapäivä** ja määritetään tyypiksi **Laskennallinen** . Tietotyyppi on **Päivämäärä ja aika**.  

Laskennallisen kentän määrityseditorin **Ehto**-osassa määritetään kaksi ehtoa, jotka ovat ostoaikataulu ja liidin arvioitu arvo. 

**ACTION**-kohdassa on kaksi kaavaa:
 - Välittömän mahdollisuuden seuraaminen viikon kuluttua
 - Seuraaminen kuukauden kuluttua, jos mahdollisuus ei tapahdu heti. 

Seuraavissa näyttökuvissa esitetään **seurantapäivän** laskennallisen kentän määritys vaihe vaiheelta.  
  
#### <a name="set-the-two-conditions-on-the-originating-lead"></a>Määrittää alkuperäisen liidin kaksi ehtoa:
  
![Mahdollisuuden seurantapäivämäärä Dynamics 365:ssä](media/calc-field-follow-update-2.PNG)  
  
![Mahdollisuuden seurantapäivämäärä Dynamics 365:ssä](media/calc-field-follow-update-3.PNG)  
  
#### <a name="provide-the-formula-to-follow-up-in-one-week"></a>Määritä kaava viikon kuluttua tapahtuvaa seurantaa varten:
  
![Mahdollisuuden seurantapäivämäärä Dynamics 365:ssä](media/calc-field-follow-update-4.PNG)  
  
#### <a name="provide-the-formula-to-follow-up-in-one-month"></a>Määritä kaava kuukauden kuluttua tapahtuvaa seurantaa varten:
  
![Aseta seurantapäivämäärä Dynamics 365:ssä](media/calc-field-follow-update-5.PNG)  
  
#### <a name="altogether"></a>Yhteensä:
  
 ![Aseta seurantapäivämäärä joko-tai-sitten -logiikalla Dynamics 365:ssä](media/calc-field-follow-update-6.PNG)  
  
### <a name="days-from-a-record-creation"></a>Tietueen luonnin jälkeisten päivien määrä 
 
Tässä esimerkissä lasketaan tietueen luontiajankohdan ja kuluvan päivän välisten päivien määrä **DIFFINDAYS**-funktion avulla. 

Luo uusi Kokonaisluku-kenttä, jonka nimi on **Laskettu ero päivinä**.
  
#### <a name="provide-the-formula-for-computing-the-difference-in-days"></a>Määritä päivien eron laskemiselle kaava
  
![Laskennallinen kenttä, DIFFINDAYS-funktio](media/custom-calc-field-diff-days.png)  
  
#### <a name="altogether"></a>Yhteensä:
  
![Ero päivinä tietueen luomisen jälkeen](media/calc-field-diff-days-complete.png)  
  
<a name="Syntax"></a> 
  
## <a name="functions-syntax"></a>Funktioiden syntaksi  

Seuraavassa taulukossa on tietoja laskennallisen kentän **TOIMINTO**-osassa olevista funktioista.  
  
> [!TIP]
>  Funktioiden nimet on kirjoitettu isoilla kirjaimilla.  
  
|Funktion syntaksi|Kuvaus|Palautustyyppi|  
|---------------------|-----------------|-----------------|  
|**ADDDAYS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika sekä määritetty määrä päiviä.|Päivämäärä ja aika|  
|**ADDHOURS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika sekä määritetty määrä tunteja.|Päivämäärä ja aika|  
|**ADDMONTHS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika sekä määritetty määrä kuukausia.|Päivämäärä ja aika|  
|**ADDWEEKS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika sekä määritetty määrä viikkoja.|Päivämäärä ja aika|  
|**ADDYEARS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika sekä määritetty määrä vuosia.|Päivämäärä ja aika|  
|**SUBTRACTDAYS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika vähennettynä määritetyllä määrällä päiviä.|Päivämäärä ja aika|  
|**SUBTRACTHOURS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika vähennettynä määritetyllä määrällä tunteja.|Päivämäärä ja aika|  
|**SUBTRACTMONTHS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika vähennettynä määritetyllä määrällä kuukausia.|Päivämäärä ja aika|  
|**SUBTRACTWEEKS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika vähennettynä määritetyllä määrällä viikkoja.|Päivämäärä ja aika|  
|**SUBTRACTYEARS** (kokonaisluku, päivämäärä ja kellonaika)|Palauttaa uuden päivämäärän ja ajan, joka on sama kuin annettu päivämäärä ja aika vähennettynä määritetyllä määrällä vuosia.|Päivämäärä ja aika|  
|**DIFFINDAYS** (päivämäärä ja kellonaika, päivämäärä ja kellonaika)|Palauttaa kahden **Päivämäärä ja kellonaika** -kentän päivien lukumäärän eron. Jos päivämäärien ja kellonaikojen päivä on sama, ero on nolla.|Kokonaisluku|  
|**DIFFINHOURS** (päivämäärä ja kellonaika, päivämäärä ja kellonaika)|Palauttaa kahden **Päivämäärä ja kellonaika** -kentän tuntien lukumäärän eron.|Kokonaisluku|  
|**DIFFINMINUTES** (päivämäärä ja kellonaika, päivämäärä ja kellonaika)|Palauttaa kahden **Päivämäärä ja kellonaika** -kentän minuuttien lukumäärän eron.|Kokonaisluku|  
|**DIFFINMONTHS** (päivämäärä ja kellonaika, päivämäärä ja kellonaika)|Palauttaa kahden **Päivämäärä ja kellonaika** -kentän kuukausien lukumäärän eron. Jos päivämäärien ja kellonaikojen kuukausi on sama, ero on nolla.|Kokonaisluku|  
|**DIFFINWEEKS** (päivämäärä ja kellonaika, päivämäärä ja kellonaika)|Palauttaa kahden **Päivämäärä ja kellonaika** -kentän viikkojen lukumäärän eron. Jos päivämäärien ja kellonaikojen viikko on sama, ero on nolla.|Kokonaisluku|  
|**DIFFINYEARS** (päivämäärä ja kellonaika, päivämäärä ja kellonaika)|Palauttaa kahden **Päivämäärä ja kellonaika** -kentän vuosien lukumäärän eron. Jos päivämäärien ja kellonaikojen vuosi on sama, ero on nolla.|Kokonaisluku|  
|**CONCAT** (yksi tekstirivi, yksi tekstirivi, ... yksi tekstirivi)|Palauttaa merkkijonon, joka on seurausta vähintään kahden merkkijonon ketjuttamisesta.|Merkkijono|  
|**TRIMLEFT** (yksi tekstirivi, kokonaisluku)|Palauttaa merkkijonon, joka sisältää kopion määritetystä merkkijonosta ilman ensimmäistä N merkkiä.|Merkkijono|  
|**TRIMRIGHT** (yksi tekstirivi, kokonaisluku)|Palauttaa merkkijonon, joka sisältää kopion määritetystä merkkijonosta ilman viimeistä N merkkiä.|Merkkijono|  
  
> [!NOTE]
>  Kaikki DIFF-funktiot edellyttävät, että ensimmäisellä **Päivämäärä ja kellonaika** -kentällä ja toisella **Päivämäärä ja kellonaika** -kentällä on sama toimintatapa: **Käyttäjän paikallinen**, **Vain päivämäärä** tai **Aikavyöhykkeestä riippumaton**. Jos toisen kentän toimintatapa ei vastaa ensimmäisen kentän toimintatapaa, näyttöön tulevassa virhesanomassa kerrotaan, että toista kenttää ei voi käyttää kyseisessä funktiossa. Lisätietoja. [Päivämäärä ja aika -kentän toimintatapa ja muoto](behavior-format-date-time-field.md).  
  
> [!NOTE]
>  Et voi syöttää päivämäärää, 01/01/2015, päivämäärän arvoksi laskettuun kenttään. Päivä ja Päivämäärä ja aika -arvoja voidaan määrittää tai verrata vain muihin Päivämäärä ja aika -kenttiin.  
  
Voit käyttää **CONCAT**-funktiossa literaalimerkkijonoja yksinä tekstiriveinä, yhden tekstirivin sisältävinä entiteettikenttinä tai kummankin yhdistelmänä. Esimerkki: **CONCAT** (Etunimi, Sukunimi, on esimies). Jos literaalimerkkijono sisältää lainausmerkkejä, aseta kunkin merkin eteen kenoviiva (\\) -ohjausmerkki seuraavasti: `This string contains the \"quotation marks.\"` Tämä varmistaa sen, että merkkijonon sisällä olevia lainausmerkkejä ei käsitellä merkkijonoja erottavina erikoismerkkeinä.  
  
Seuraavissa esimerkeissä käytetään **TRIMLEFT**- ja **TRIMRIGHT**-funktioita. Ne sisältävät **TRIMLEFT**- ja **TRIMRIGHT**-funktioiden palauttamat alkuperäiset merkkijonot ja palautetut merkkijonot.  
  
**TRIMLEFT** ("RXX10-3456789", 3), palauttaa merkkijonon `10-3456789`    
**TRIMRIGHT** ("20-3456789RXX", 3), palauttaa merkkijonon `20-3456789` 
  
<a name="Considerations"></a> 
  
## <a name="considerations"></a>Huomioitavia seikkoja 
 
Sinun tulisi huomioida tietyt ehdot ja rajoitukset, kun työskentelet laskennallisten kenttien kanssa.  
  
- Tallennetuilla kyselyillä, kaavioilla ja visualisoinneilla voi olla enintään 10 yksilöllistä laskennallista kenttää.  
- Laskennallisten kenttien arvot eivät näy Outlook Client Offline -tilassa ruutunäkymässä tai entiteetin päälomakkeilla.  
- Ketjutettujen laskennallisten kenttien enimmäismäärä on 5.  
- Laskennallinen kenttä ei voi viitata itseensä eikä sillä voi olla syklisiä ketjuja.  
- Jos muutat usean ehdon lauseen ehto-operaattoreita, kaikki ehto-operaattorit muutetaan kyseiseksi ehdoksi. Jos esimerkiksi muutat lausekkeessa `IF (x > 50) OR (y ==10) OR (z < 5)` `OR`-operaattorin `AND`-operaattoriksi, kaikki lausekkeen `OR`-operaattorit muuttuvat `AND`-operaattoreiksi.  
- Voit käyttää pääkenttiä pääentiteetin, kuten *`<LookupFieldName>.<FieldName>`*, valintakentän kautta. Tämä ei ole mahdollista usean entiteetin hakukentissä, kuten asiakas, joka voi olla asiakas tai yhteyshenkilö. Joillakin entiteeteillä on kuitenkin yksilöllisiä valintakenttiä tietylle entiteetille, kuten `ParentAccountid.`*`<FieldName>`* tai `ParentContactid.`*`<FieldName>`*.  
- Lajittelu on poistettu käytöstä:  
  - Laskennallinen kenttä, joka sisältää päätietueen kentän.  
  - Laskennallinen kenttä, joka sisältää loogisen kentän (esimerkiksi osoitekenttä)
  - Laskennallinen kenttä, joka sisältää toisen laskennallisen kentän.  
- Laskennalliset kentät voivat kattaa vain kaksi entiteettiä.  
  - Laskennallinen kenttä voi sisältää kentän toisesta entiteetistä (kattaa kaksi entiteettiä, nykyisen entiteetin ja päätietueen).  
  - Laskettu kenttä ei voi sisältää toisen entiteetin laskettua kenttää, joka sisältää myös eri entiteetin kentän (kolme entiteettiä kattavan):   
    (Nykyinen entiteetti) Laskennallinen kenttä &larr; (ylätason tietue) laskennallinen kenttä 1 &larr; (ylätason tietue) laskennallinen kenttä 2.  
- Työnkulkuja tai laajennuksia ei voi käynnistää laskennallisissa kentissä.  
- Olemassa olevaa yksinkertaista kenttää ei voi muuttaa laskennalliseksi kentäksi. Jos nykyinen sovellus käyttää JavaScriptia tai laajennuksia kentän laskennassa, voit käyttää laskennallisten kenttien ominaisuutta vain, jos luot uuden kentän.  
- Kaksoiskappaleiden tunnistussäännöt eivät käynnisty laskennallisissa kentissä.  
- Koonti ei voi viitata laskennalliseen kenttään, joka käyttää toista laskennallista kenttää, vaikka kaikki toisen laskennallisen kentän kentät kuuluisivat nykyiseen entiteettiin.  
  
### <a name="see-also"></a>Katso myös
 
[Kenttien luominen ja muokkaaminen](create-edit-fields.md)<br />
[Määritä koontikenttiä, jotka kokoavat arvoja](define-rollup-fields.md)<br />
[Video: Koontikentät ja laskennalliset kentät](http://go.microsoft.com/fwlink/p/?LinkId=517727)
