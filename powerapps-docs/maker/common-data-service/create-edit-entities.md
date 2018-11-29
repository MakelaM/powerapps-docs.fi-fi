---
title: Entiteettien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa | MicrosoftDocs
description: Tietoja entiteettien luomisesta ja muokkaamisesta
ms.custom: ''
ms.date: 05/11/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: fa04f99d-a5f9-48cb-8bfb-f0f50718ccee
caps.latest.revision: 41
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-entities-in-common-data-service-for-apps"></a>Entiteettien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa

Arvioi ennen mukautetun entiteetin luomista, vastaako jokin aiemmin luotu entiteetti vaatimuksiasi. Lisätietoja: [Luodaanko uusia metatietoja vai käytetäänkö olemassa olevia metatietoja?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Entiteettejä voi luoda kahden suunnitteluohjelman avulla:

|Suunnittelija| Kuvaus|
|--|--|
|[PowerApps-portaali](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Tarjoaa helpon ja nopean käyttökokemuksen, mutta jotkin erityisasetukset eivät ole käytettävissä.<br />Lisätietoja: <br />[Opetusohjelma: Osia sisältävän mukautetun entiteetin luominen PowerAppsissa](/powerapps/maker/common-data-service/create-custom-entity)<br />[Entiteettien luominen ja muokkaaminen PowerApps-portaalin avulla](create-edit-entities-portal.md)|
|Ratkaisunhallinta|Tämä ei ole niin helppo tapa, mutta tarjoaa enemmän joustavuutta vähemmän yleisille vaatimuksille. <br />Lisätietoja on kohdassa [Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-entities-solution-explorer.md)|

> [!NOTE]
> Voit luoda entiteettejä ympäristössä myös seuraavasti:
> - Tuo ratkaisu, joka sisältää entiteettien määrityksen.
> - Luo uusia entiteettejä Power Queryn avulla ja anna niiden tiedot. Lisätietoja: [Tietojen lisääminen Common Data Service -ratkaisun entiteettiin Power Queryn avulla](/powerapps/maker/common-data-service/data-platform-cds-newentity-pq).
> - Sovelluskehittäjä voi käyttää ohjelman kirjoittamisessa [metatietopalveluita](/powerapps/developer/common-data-service/use-web-services#metadata-services).


## <a name="entity-options-not-available-in-the-powerapps-portal"></a>Entiteettivalinnat eivät ole käytettävissä PowerApps-portaalissa

Tämän ohjeaiheen tietojen avulla voit valita käytettävän suunnitteluohjelman. Luo entiteetti PowerApps-portaalin avulla, jos seuraavia vaatimuksia ei tarvitse ottaa huomioon.

- Mukautuksen etuliitteen hallinta

  Jokaisen luomasi mukautetun entiteetin nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle entiteetille. Lisätietoja on kohdassa [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md).

- Organisaation omistaman entiteetin luominen

  Oletusarvoisesti PowerApps-portaali luo **käyttäjän tai ryhmän** luomat entiteetit. Määritä **organisaation** omistajuus ratkaisunhallinnan avulla. Lisätietoja: [Entiteetin omistus](types-of-entities.md#entity-ownership)

- Aktiviteettientiteetin luominen

  Aktiviteettientiteetti on erityinen entiteetti, joka seuraa toimintoja, joista voidaan tehdä merkintä kalenteriin. Lisätietoja: [Aktiviteettientiteetit](types-of-entities.md#activity-entities).

- Mukautetun entiteetin kuvakkeiden muuttaminen

  Oletusarvoisesti kaikilla mallipohjaisten sovellusten mukautetuilla entiteeteillä on sama kuvake. Voit luoda kuvan WWWresursseja kuvakkeille, jotka haluat mukautetuille entiteeteille. Lisätietoja: [Mukautettujen entiteettien kuvakkeiden muuttaminen](../model-driven-apps/change-custom-entity-icons.md). 

- Muuta mitä tahansa seuraavaa ominaisuutta, jotka voidaan ottaa vain käyttöön:

  [!INCLUDE [cc_entity-set-once-options-table](../../includes/cc_entity-set-once-options-table.md)]

- Muuta mitä tahansa seuraavista ominaisuuksista:

  <!-- Based on ../../includes/cc_entity-changeable-options-table.md 
Removed these:

  /|**Description**/|Provide a meaningful description of the purpose of the entity./|

  /|**Primary Image**/|System entities that support images will already have an **Image** field. You can choose whether to display data in this field as the image for the record by setting this field to **[None]** or **Default Image**.<br /><br /> For custom entities you must first create an image field. Each entity can have only one image field. After you create one, you can change this setting to set the primary image. More information: [Image fields](../maker/common-data-service/types-of-fields.md#image-fields) /|-->

  |Asetus   |Kuvaus  |
  |---------|---------|
  |**Käyttöoikeusryhmät**|Entiteetin ryhmän mallien luominen |
  |**Salli pikaluonti**|Sen jälkeen, kun olet luonut ja julkaissut tälle entiteetille **Pikaluontilomakkeen**, käyttäjät voivat luoda uuden tietueen siirtymisruudun **Luo**-painikkeen avulla. Lisätietoja: [Lomakkeiden luominen ja suunnittelu](../model-driven-apps/create-design-forms.md)<br /><br /> Kun tämä otetaan käyttöön mukautetussa aktiviteettientiteetissä, mukautettu aktiviteetti näkyy aktiviteettientiteettien ryhmässä, kun käyttäjät käyttävät siirtymisruudun **Luo**-painiketta. Koska aktiviteetit eivät tue pikaluontilomakkeita, mukautetun entiteetin kuvakkeen napsautuksen jälkeen käytetään päälomaketta.|
  |**Alueet, joissa tämä entiteetti näkyy**|Valitse WWW-sovelluksessa jokin käytettävissä olevista sivustokartan alueista, jolla tämä entiteetti näytetään. Tämä ei koske mallipohjaisia sovelluksia.|
  |**Seuranta**|Jos seuranta on käytössä organisaatiossa, voit tallentaa eri aikoina tehtävät entiteettitietueiden muutokset. Kun otat käyttöön entiteetin seurannan, järjestelmä alkaa seurata myös kaikkia entiteetin kenttiä. Voit valita tai poistaa kenttiä, joiden seurannan haluat ottaa käyttöön.|
  |**Muutosten seuranta**|Mahdollistaa tietojen synkronoinnin tehokkaasti havaitsemalla tiedot, joita on muutettu tietojen ensimmäisen purkamisen tai edellisen synkronoinnin jälkeen.  |
  |**Väri**|Määritä mallipohjaisten sovellusten entiteetissä käytettävä väri.|
  |**Tiedostojen hallinta**|Kun organisaation tiedostojen hallinnan käyttöönottoon liittyvät tehtävät on suoritettu, voit ottaa tämän ominaisuuden käyttöön. Sen avulla entiteetti ottaa osaa integrointiin SharePointin kanssa. |
  |**Kaksoiskappaleiden tunnistus**|Jos kaksoiskappaleiden tunnistaminen on käytössä organisaatiossa, tämän ominaisuuden ottaminen käyttöön mahdollistaa kaksoiskappaleiden tunnistussääntöjen luomisen entiteetille.|
  |**Ota käyttöön mobiililaitteissa**|Määritä tämä entiteetti Dynamics 365 for phones- ja Dynamics 365 for tablets -sovellusten käytettäväksi. Voit määrittää tämän entiteetin myös **vain luku -tilaan mobiililaitteessa**.<br /><br /> Jos entiteetin lomakkeet vaativat laajennuksen, jota Dynamics 365 for phones- ja Dynamics 365 for tablets -sovellukset eivät tue, tämän asetuksen avulla voit määrittää, että mobiilisovelluksen käyttäjät eivät voi muokata näitä entiteettejä.|
  |**Ota käyttöön Phone Expressissä**|Määritä tämä entiteetti Dynamics 365 for phones -sovellusten käytettäväksi.|
  |**Yhdistäminen**|Tätä entiteettiä voi käyttää yhdistämistoiminnon kanssa.|
  |**Dynamics 365 for Outlookin offline-ominaisuudet**|Määrittää, ovatko tämän entiteetin tiedot käytettävissä silloin, kun Dynamics 365 for Outlook -sovelluksessa ei ole Internet-yhteyttä.|
  |**Outlookin lukuruutu Dynamics 365 for Outlookissa**|Määrittää, näytetäänkö entiteetti Dynamics 365 for Outlook -sovelluksen lukuruudussa.|
  |**Käytä mukautettua ohjetta**|Kun tämä on käytössä, voit määrittää ohjeen URL-osoitteen, joka määrittää, minkä sivun käyttäjät näkevät valitessaan ohjepainikkeen sovelluksessa. Tämän avulla saat yrityksen prosessikohtaisia ohjeita entiteetille.|


### <a name="see-also"></a>Katso myös

[Entiteettien luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-entities-solution-explorer.md)<br />
[Opetusohjelma: Osia sisältävän mukautetun entiteetin luominen PowerAppsissa](/powerapps/maker/common-data-service/create-custom-entity)<br />
[Entiteetin muokkaaminen](edit-entities.md)<br />
[Sovelluskehittäjän dokumentaatio: Mukautetun entiteetin luominen](/dynamics365/customer-engagement/developer/org-service/create-custom-entity)
