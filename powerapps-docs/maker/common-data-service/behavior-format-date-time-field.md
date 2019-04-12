---
title: Päivämäärän ja kellonajan kentän toimintatapa ja muoto Common Data Servicessä | MicrosoftDocs
ms.custom: ''
ms.date: 05/25/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 73d691c7-344e-4c96-8979-c661c290bf81
caps.latest.revision: 47
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="behavior-and-format-of-the-date-and-time-field"></a>Päivämäärän ja kellonajan kentän toimintatapa ja muoto

Common Data Servicessä päivämäärän ja ajan tietotyyppiä käytetään useissa vakioentiteettikentissä. Voit valita erilaisia kenttien toimintatapoja kentän päivämäärän tarkoituksesta riippuen: **Käyttäjän paikallinen**, **Vain päivämäärä** tai **Aikavyöhykkeestä riippumaton**.  
  
<a name="Behavior"></a>   

## <a name="date-and-time-field-behavior-and-format"></a>Päivämäärän ja kellonajan kentän toimintatapa ja muoto  

Seuraava taulukko sisältää tietoja päivämäärän ja kellonajan kentän toimintatavasta ja muodosta.  
  
|Toimintatapa|Muotoilu|Kuvaus|  
|--------------|------------|-------------------------------|  
|**Käyttäjän paikallinen** |**Vain päivämäärä**<br />- tai -<br />**Päivämäärä ja aika**|Tämä on mukautettujen päivämäärän ja ajan kenttien oletustoimintatapa.<br /><br />Kentän arvot näytetään käyttäjän paikallisessa ajassa.<br />WWW-palveluissa nämä arvot palautetaan käyttäen yhteistä UTC-aikavyöhykkeen muotoa.<br /><br />Voit muuttaa tätä kerran, jos valitset oletustoimintatavan. Lisätietoja; [Käyttäjän paikallisen toimintatavan muuttaminen](#change-user-local-behavior)|  
|**Vain päivämäärä**|**Vain päivämäärä**|Ei aikavyöhykkeen muuntamista.<br /><br />Arvon kellonaikaosa on aina 00.00.<br />Arvon päivämääräosa tallennetaan ja haetaan käyttöliittymässä ja WWW-palvelussa määritetyllä tavalla.|  
|**Aikavyöhykkeestä riippumaton**|**Vain päivämäärä**<br />- tai -<br />**Päivämäärä ja aika**|Ei aikavyöhykkeen muuntamista.<br /><br />Päivämäärän ja kellonajan arvot tallennetaan ja haetaan käyttöliittymässä ja WWW-palvelussa määritetyllä tavalla.|  

## <a name="change-user-local-behavior"></a>Käyttäjän paikallisen toimintatavan muuttaminen:

Voit muuttaa olemassa olevien mukautettujen päivämääräkenttien toimintatavan**Käyttäjän paikallinen** -arvosta **Vain päivämäärä**- tai **Aikavyöhykkeestä riippumaton** arvoksi, jos hallitun ratkaisun julkaisija ei estä tätä. Tämän muutoksen voi tehdä vain kerran.

Kentän toimintatavan muuttaminen vaikuttaa niiden kenttien arvoihin, jotka on lisätty tai joita on muokattu kentän toimintatavan muuttamisen jälkeen. Aiemmin määritetyt kenttien arvot säilyvät tietokannassa UTC-aikavyöhykkeen muodossa. Jos haluat muuttaa aiemmin luodun kentän UTC-arvon Vain päivämäärä -arvoksi, saatat tarvita kehittäjän apua muutoksen ohjelmallisessa suorittamisessa. Lisätietoja: [Aiemmin määritetyn päivämäärän ja ajan arvojen muuntaminen tietokannassa](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute#convert-behavior-of-existing-date-and-time-values-in-the-database). 

> [!WARNING]
> Tarkista ennen olemassa olevan päivämäärän ja kellonajan kentän toimintatavan muuttamista kaikki kentän riippuvuudet, kuten liiketoimintasäännöt, työnkulut sekä laskennalliset kentät tai koontikentät. Näin varmistat, että toimintatavan muuttamisesta ei aiheudu ongelmia. Kun päivämäärän ja kellonajan kentän toimintatapaa on muutettu, avaa jokainen liiketoimintasääntö, laskennallinen kenttä ja koontikenttä, jolla on riippuvuus muutettuun kenttään, tarkista tiedot ja tallenna kohde. Näin varmistat, että käytössä ovat uusimmat päivämäärän ja kellonajan kentän toimintatapa ja arvo. 

### <a name="change-behavior-during-a-solution-import"></a>Toimintatavan muuttaminen ratkaisun tuomisen aikana

Kun tuot päivämääräkentän sisältävän ratkaisun **Käyttäjän paikallinen** -toimintatavan avulla, voit muuttaa tomintatavaksi **Vain päivämäärä** tai **Aikavyöhykkeestä riippumaton**.  

### <a name="prevent-changing-behavior"></a>Toimintatavan muuttamisen estäminen

Jos jaat mukautetun päivämääräkentän hallitussa ratkaisussa, voit estää ratkaisun käyttämisen muuttamalla toimintatapaa. Voit määrittää hallitun ominaisuuden **CanChangeDateTimeBehavior** arvoksi **Epätosi**. Lisätietoja: [Kentän hallitut ominaisuudet](set-managed-properties-metadata.md#field-managed-properties)
  
## <a name="use-cases"></a>Käyttötapaukset

Voit käyttää **Vain päivämäärä**- ja **Aikavyöhykkeestä riippumaton** -toimintatavoilla seuraavia käyttötapauksia.

### <a name="date-only-scenario-birthdays-and-anniversaries"></a>Vain päivämäärä -skenaario: syntymäpäivät ja vuosipäivät

Vain päivämäärä -toimintaa kannattaa käyttää silloin, kun kellonajan ja aikavyöhykkeen tietoja ei tarvita (esimerkiksi syntymäpäivissä ja vuosipäivissä). Kun valinta on tämä, kaikki sovelluksen käyttäjät ympäri maailman näkevät täsmälleen saman päivämäärän arvon.  
  
### <a name="time-zone-independent-scenario-hotel-check-in"></a>Aikavyöhykkeestä riippumaton -skenaario: kirjautuminen hotelliin sisään

Tätä toimintaa voi käyttää, kun aikavyöhykkeen tietoja ei tarvita (esimerkiksi hotelliin sisäänkirjautumisajassa). Kun valinta on tämä, kaikki sovelluksen käyttäjät ympäri maailman näkevät saman päivämäärän ja kellonajan arvon.  


## <a name="date-and-time-query-operators-not-supported-for-date-only-behavior"></a>Päivämäärän ja kellonajan kyselyoperaattorit, joita Vain päivämäärä -toimintatapa ei tue  

Seuraavat päivämäärään ja kellonaikaan liittyvät kyselyoperaattorit ovat virheellisiä **Vain päivämäärä** -toimintatavalle. Virheellinen operaattori aiheuttaa poikkeuksen, kun jotakin näistä operaattoreista käytetään kyselyssä.  
  
- Yli X minuuttia vanhat  
- Yli X tuntia vanhat  
- Edelliset X tuntia  
- Seuraavat X tuntia  

  
### <a name="see-also"></a>Katso myös

[Kenttien luominen ja muokkaaminen](create-edit-fields.md)<br />
[Voit automatisoida manuaalisen laskennan laskettujen kenttien määrittämiseen](define-calculated-fields.md)<br />
[Kentän hallitut ominaisuudet](set-managed-properties-metadata.md#field-managed-properties)<br />
[Hallitut ominaisuudet](solutions-overview.md#managed-properties)

