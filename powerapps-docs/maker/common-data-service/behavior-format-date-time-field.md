---
title: Päivämäärä ja aika -kentän toiminta ja muoto Common Data Service for Apps -palvelussa | MicrosoftDocs
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
ms.assetid: 73d691c7-344e-4c96-8979-c661c290bf81
caps.latest.revision: 47
ms.author: matp
manager: kvivek
ms.openlocfilehash: 2f62f2433fe959e3713df544628db186b801731e
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39680475"
---
# <a name="behavior-and-format-of-the-date-and-time-field"></a>Päivämäärä ja aika -kentän toiminta ja muoto

Common Data Service for Apps käyttää Päivämäärä ja aika -tietotyyppiä monissa vakioentiteettikentissä. Päivämääräkentän edustamien tietojen perusteella voit valita kentälle erilaisia asetuksia: **Käyttäjän paikallinen**, **Vain päivämäärä** tai **Aikavyöhykkeestä riippumaton**.  
  
<a name="Behavior"></a>   

## <a name="date-and-time-field-behavior-and-format"></a>Päivämäärä ja aika -kentän toiminta ja muoto  

Seuraava taulukko sisältää tietoja Päivämäärä ja aika -kentän toiminnasta ja muodosta.  
  
|Toiminta|Muoto|Kuvaus|  
|--------------|------------|-------------------------------|  
|**Käyttäjän paikallinen** |**Vain päivämäärä**<br />- tai -<br />**Päivämäärä ja aika**|Tämä on mukautettujen Päivämäärä ja aika -kenttien oletustoiminta.<br /><br />Kentän arvot näytetään nykyisen käyttäjän paikallisessa ajassa.<br />Verkkopalveluissa nämä arvot palautetaan yleisen UTC-aikavyöhykkeen muodossa.<br /><br />Jos valitset oletustoiminnan, voit muuttaa tätä kerran. Lisätiedot: [Muokkaa käyttäjän paikallista toimintaa](#change-user-local-behavior)|  
|**Vain päivämäärä**|**Vain päivämäärä**|Aikavyöhykettä ei muunneta.<br /><br />Arvon aikaosan arvo on aina 12:00AM.<br />Arvon päivämääräosa tallennetaan ja haetaan käyttöliittymässä ja verkkopalveluissa määritetyllä tavalla.|  
|**Aikavyöhykkeestä riippumaton**|**Vain päivämäärä**<br />- tai -<br />**Päivämäärä ja aika**|Aikavyöhykettä ei muunneta.<br /><br />Päivämäärä ja kellonaika tallennetaan ja haetaan käyttöliittymässä ja verkkopalveluissa määritetyllä tavalla.|  

## <a name="change-user-local-behavior"></a>Muokkaa käyttäjän paikallista toimintaa:

Ellei hallitun ratkaisijan julkaisija tätä estä, voit vaihtaa olemassa olevien mukautettujen päivämääräkenttien **Käyttäjän paikallinen** -asetuksen **Vain päivämäärä**- tai **Aikavyöhykkeestä riippumaton** -asetukseksi. Tämän muutoksen voi tehdä kerran.

Kentän toiminnan muuttaminen vaikuttaa kenttien arvoihin, jotka lisätään tai joita muokataan sen jälkeen, kun kentän toimintaa on muutettu. Tietokannan olemassa olevat kenttien arvot pysyvät UTC-aikavyöhykemuodossa. Jos haluat vaihtaa olemassa olevien kenttien toiminnan UTC-muodosta Vain päivämäärä -muotoon, tarvitset ehkä kehittäjän apua, jotta voit toteuttaa tämän ohjelmallisesti. Lisätiedot: [Tietokannan olemassa olevien päivämäärä- ja aika-arvojen toiminnan muuttaminen](/dynamics365/customer-engagement/developer/behavior-format-date-time-attribute#convert-behavior-of-existing-date-and-time-values-in-the-database). 

> [!WARNING]
> Ennen kuin vaihdat olemassa olevan Päivämäärä ja aika -kentän toimintaa, tarkista kaikki kentän riippuvuudet, esimerkiksi liiketoimintasäännöt, työnkulut, lasketut kentät ja koostekentät. Näin varmistat, että toiminnan muuttamisesta ei koidu ongelmia. Kun olet muuttanut Päivämäärä ja aika -kentän toimintaa, avaa jokainen liiketoimintasääntö, työnkulku, laskettu kenttä ja koostekenttä, joka on riippuvainen muuttamastasi kentästä, tarkista niiden tiedot ja tallenna ne. Näin varmistat, että käytössä ovat uusimmat Päivämäärä ja aika -kentän arvot sekä kentän uusin toiminta. 

### <a name="change-behavior-during-a-solution-import"></a>Toiminnan vaihtaminen ratkaisun tuomisen yhteydessä

Kun tuot ratkaisua, joka sisältää **Käyttäjän paikallinen** -toimintaa käyttävän päivämääräkentän, voit ehkä vaihtaa toiminnaksi **Vain päivämäärä** tai **Aikavyöhykkeestä riippumaton**.  

### <a name="prevent-changing-behavior"></a>Toiminnan muuttamisen estäminen

Jos jakelet mukautetun päivämääräkentän sisältävää hallittua ratkaisua, voit estää ratkaisusi käyttäjiä muuttamasta toimintaa. Voit tehdä tämän määrittämällä hallitun **CanChangeDateTimeBehavior**-ominaisuuden arvoksi **False**. Lisätiedot: [Kenttien hallitut ominaisuudet](set-managed-properties-metadata.md#field-managed-properties)
  
## <a name="use-cases"></a>Käyttötilanteet

Alla on esitelty muutama tilanne, joissa käytetään **Vain päivämäärä** ja **Aikavyöhykkeestä riippumaton** -toimintaa.

### <a name="date-only-scenario-birthdays-and-anniversaries"></a>Vain päivämäärä -toiminta: syntymäpäivät ja vuosipäivät

Vain päivämäärä -toiminta sopii tilanteisiin, joissa tietoja kellonajasta tai aikavyöhykkeestä ei tarvita. Tällaisia tilanteita ovat esimerkiksi syntymäpäivät ja vuosipäivät. Tällä valinnalla kaikki käyttäjät kaikkialla maailmassa näkevät täysin saman päivämääräarvon.  
  
### <a name="time-zone-independent-scenario-hotel-check-in"></a>Aikavyöhykkeestä riippumaton -toiminto: hotelliin kirjautuminen

Voit käyttää tätä toimintaa, kun aikavyöhyketietoja ei tarvita, esimerkiksi hotelliin kirjautumisaikaa ilmaistaessa. Tällä valinnalla kaikki käyttäjät kaikkialla maailmassa näkevät saman päivämäärän ja kellonajan arvon.  


## <a name="date-and-time-query-operators-not-supported-for-date-only-behavior"></a>Päivämäärän ja ajan kyselyoperaattorit, joita ei tueta Vain päivämäärä -toiminnoissa  

**Vain päivämäärä** -toiminta ei tue seuraavia päivämäärään ja aikaan liittyviä operaattoreita. Jos kyselyssä käytetään jotain näistä operaattoreista, saat virheellisen operaattorin poikkeuksen virheilmoituksen.  
  
- Vanhempi kuin X minuuttia  
- Vanhempi kuin X tuntia  
- Edelliset X tuntia  
- Seuraavat X tuntia  

  
### <a name="see-also"></a>Katso myös

[Kenttien luominen ja muokkaaminen](create-edit-fields.md)<br />
[Manuaalisten laskutoimitusten automatisointi lasketuilla kentillä](define-calculated-fields.md)<br />
[Kentän hallitut ominaisuudet](set-managed-properties-metadata.md#field-managed-properties)<br />
[Hallitut ominaisuudet](solutions-overview.md#managed-properties)

