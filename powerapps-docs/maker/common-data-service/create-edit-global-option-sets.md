---
title: Common Data Service sovelluksille -ratkaisun yleisten asetusjoukkojen luomisen ja muokkaamisen (valintaluettelot) yleiskuvaus | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: f06b8941-8dca-4601-b965-341cfb6fc3b2
caps.latest.revision: 11
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-global-option-sets-overview"></a>Yleisten asetusjoukkojen luomisen ja muokkaamisen yleiskatsaus 

Asetusjoukko (valintaluettelo) on kenttätyyppi, joka voidaan sisällyttää entiteettiin. Se määrittää asetusten joukon. Jos lomakkeessa näkyy asetusjoukko, siinä käytetään avattavan luettelon ohjausobjektia. Jos kyseessä on **Erikoishaku**-toiminto, käytössä on *valintaluettelon ohjausobjekti*. Joskus kehittäjät kutsuvat asetusjoukkoa valintaluetteloksi.  
  
Voit määrittää asetusjoukon käyttämään paikallisesti määritettyä asetusten joukkoa, tai se voi käyttää muualla (yleisesti) määritettyä asetusten joukkoa, jota muut asetusjoukkokentät voivat käyttää. 

Yleiset asetusjoukot ovat käteviä, jos käytät useissa kentissä samaa luokkajoukkoa. Kahden erillisen mutta samat arvot sisältävän asetusjoukon ylläpito on hankalaa, ja virheitä voi esiintyä, jos niitä ei synkronoida. Näin tapahtuu etenkin yhdistettäessä yksi moneen -entiteettisuhteen entiteettikenttiä. Lisätietoja: [Entiteettikenttien yhdistäminen](map-entity-fields.md)

> [!NOTE]
> Jos määrität jokaisen asetusjoukon yleiseksi asetusjoukoksi, yleisten asetusjoukkojen luettelo kasvaa. Tällöin sen hallinta voi olla vaikeaa. Jos tiedät, että asetusjoukkoa tullaan käyttämään vain yhdessä paikassa, käytä paikallista asetusjoukkoa.

Yleisiä asetusjoukkoja voi luoda kahden suunnitteluohjelman avulla seuraavasti:

|Suunnittelija| Kuvaus|
|--|--|
|[PowerApps-portaali](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Tarjoaa helpon ja nopean käyttökokemuksen, mutta jotkin erityisasetukset eivät ole käytettävissä.<br />Lisätietoja: [Asetusjoukon luominen](custom-picklists.md) |
|Ratkaisunhallinta|Tämä ei ole niin helppo tapa, mutta tarjoaa enemmän joustavuutta vähemmän yleisille vaatimuksille. <br />Lisätietoja: [Common Data Service sovelluksille -ratkaisun yleisten asetusjoukkojen luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-global-option-sets-solution-explorer.md) |

> [!NOTE]
> Voit luoda yleisiä asetusjoukkoja ympäristössä myös seuraavasti:
> - Tuo ratkaisu, joka sisältää yleisten asetusjoukkojen määrityksen.
> - Sovelluskehittäjä voi luoda niitä myös tekemällä ohjelman. <br />Lisätietoja: [Sovelluskehittäjän dokumentaatio: Yleisten asetusjoukkojen mukauttaminen](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets).

Tämän ohjeaiheen tietojen avulla voit valita käytettävän suunnitteluohjelman. 

Käytä yleisiä asetusjoukkoja [PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla, jos seuraavia vaatimuksia ei tarvitse ottaa huomioon:

- Värien määrittäminen asetuksille
- Asetusten järjestyksen muuttaminen
- Yleisen asetusjoukon luominen muussa kuin CDS-oletusratkaisussa
- Hallittujen ominaisuuksien määrittäminen
- Virtuaalisissa entiteeteissä käytettävien ominaisuuksien määrittäminen
- Riippuvuuksien tarkasteleminen

## <a name="see-also"></a>Katso myös

[Asetusjoukon luominen](custom-picklists.md)<br />
[Common Data Service sovelluksille -ratkaisun yleisten asetusjoukkojen luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-global-option-sets-solution-explorer.md)<br />
[Sovelluskehittäjän dokumentaatio: Yleisten asetusjoukkojen mukauttaminen](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)
  

 
