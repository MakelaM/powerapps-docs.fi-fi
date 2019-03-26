---
title: Kenttien luominen ja muokkaaminen Common Data Service sovelluksille -ratkaisussa | MicrosoftDocs
ms.custom: ''
ms.date: 02/08/2019
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: d88677fa-2caf-47b0-aec6-10a25a7ec9c3
caps.latest.revision: 55
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="how-to-create-and-edit-fields"></a>Kenttien luominen ja muokkaaminen

Common Data Service sovelluksille -ratkaisun kentät määrittävät yksittäiset tieto-osat, joihin tietoja voidaan tallentaa entiteetissä. Sovelluskehittäjät kutsuvat kenttiä joskus *määritteiksi*. 
  
Arvioi ennen mukautetun kentän luomista, vastaisiko jokin aiemmin luotu kenttä vaatimuksiasi. Lisätietoja: [Luodaanko uusia metatietoja vai käytetäänkö olemassa olevia metatietoja?](create-edit-metadata.md#create-new-metadata-or-use-existing-metadata)

Kenttiä voi luoda kahden suunnitteluohjelman avulla:

|Suunnittelija| Kuvaus|
|--|--|
|[PowerApps-portaali](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)|Tarjoaa helpon ja nopean käyttökokemuksen, mutta jotkin erityisasetukset eivät ole käytettävissä.<br />Lisätietoja: [Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-portaalin avulla](create-edit-field-portal.md)|
|Ratkaisunhallinta|Tämä ei ole niin helppo tapa, mutta tarjoaa enemmän joustavuutta vähemmän yleisille vaatimuksille.<br />Lisätietoja: [Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md) |

> [!NOTE]
> Voit luoda kenttiä ympäristössä myös seuraavasti:
> - Valitse mallipohjaisten sovellusten lomake-editorissa **Uusi kenttä**.
> - Tuo ratkaisu, joka sisältää kenttien määrityksen.
> - Luo uusia entiteettejä Power Queryn avulla ja anna niiden tiedot.<br />Lisätietoja: [Tietojen lisääminen Common Data Service -ratkaisun entiteettiin Power Queryn avulla](/powerapps/maker/common-data-service/data-platform-cds-newentity-pq).
> - Sovelluskehittäjä voi käyttää [metatietopalveluita](/powerapps/developer/common-data-service/use-web-services#metadata-services) ohjelman kirjoittamisessa kenttien luomista ja päivittämistä varten.

Tämän ohjeaiheen tietojen avulla voit valita käytettävän suunnitteluohjelman. 

Käytä PowerApps-portaalia Common Data Service for Apps -ratkaisun kenttien luomisessa ja muokkaamisessa, jos seuraavia vaatimuksia ei tarvitse ottaa huomioon:

- Luo asiakkaan hakukenttä. 
   - Lisätietoja: [Erityyppiset haut](types-of-fields.md#different-types-of-lookups)
- Luo kenttä muussa kuin CDS-oletusratkaisussa. 
   - Lisätietoja: [Ratkaisujen yleiskatsaus](solutions-overview.md)
- Määritän tilan syyn siirtymät. 
   - Lisätietoja: [Palvelupyynnön tai muokattujen entiteettien tilan syyn siirtojen määrittäminen](define-status-reason-transitions.md)
- Muokkaa useita kenttiä samanaikaisesti.
- Ota seuranta käyttöön. 
   - Lisätietoja: [Seurannan yleiskatsaus](../../developer/common-data-service/auditing-overview.md)
- Ota kenttätason suojaus käyttöön. 
   - Lisätietoja: [Kentän suojausentiteetit](../../developer/common-data-service/field-security-entities.md)
- Valitse, näytetäänkö kenttä vuorovaikutteisen kokemuksen yleisessä suodatuksessa. 
   - Lisätietoja: [Vuorovaikutteisen kokemuksen mallipohjaisen sovelluksen määrittäminen](../model-driven-apps/configure-interactive-experience-dashboards.md)
- Valitse, voiko kentän lajitella vuorovaikutteisissa koontinäytöissä. 
   - Lisätietoja: [Vuorovaikutteisen kokemuksen mallipohjaisen sovelluksen määrittäminen](../model-driven-apps/configure-interactive-experience-dashboards.md)
- Määritä kentän vaatimustasoksi Suositeltava. 
   - Lisätietoja: [Liiketoimintasääntöjen ja suositusten luominen mallipohjaisen sovelluksen lomakkeen logiikan käyttämiseksi](../model-driven-apps/create-business-rules-recommendations-apply-logic-form.md)
- Määritä kentän hallitut ominaisuudet. 
   - Lisätietoja: [Kenttien hallittujen ominaisuuksien määrittäminen](set-managed-properties-for-field.md)

> [!NOTE]
> Voit luoda PowerApps-portaalissa tai ratkaisunhallinnassa hakukentän luomalla entiteetille yksi moneen -suhteen. Kuitenkin vain ratkaisunhallinnassa on mahdollisuus luoda tämä suhde kentän luomisen yhteydessä.

## <a name="community-tools"></a>Yhteisön työvälineet

**[Attribute Manager](https://www.xrmtoolbox.com/plugins/DLaB.Xrm.AttributeManager/)** on XrmToolbox-yhteisön CDS sovelluksille -ratkaisua varten kehittämä työkalu. Lisätietoja yhteisön kehittämistä työkaluista on ohjeaiheessa [Sovelluskehittäjän työkalut](https://docs.microsoft.com/dynamics365/customer-engagement/developer/developer-tools).

> [!NOTE]
> Yhteisön työkalut eivät ole Microsoftin tuotteita eivätkä laajenna tuen yhteisön työkaluille. Jos sinulla on kysymyksiä työkalusta, ota yhteyttä julkaisijaan. Lisätietoja: [XrmToolBox](https://www.xrmtoolbox.com).

### <a name="see-also"></a>Katso myös  
[Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-portaalin avulla](create-edit-field-portal.md)<br />
[Common Data Service sovelluksille -ratkaisun kenttien luominen ja muokkaaminen PowerApps-ratkaisunhallinnan avulla](create-edit-field-solution-explorer.md)<br />
[Kenttien tyypit ja kentän tietojen tyypit](types-of-fields.md)<br />
[Sovelluskehittäjän dokumentaatio: Määritteen metatietojen käsitteleminen](/dynamics365/customer-engagement/developer/org-service/work-attribute-metadata)
 
