---
title: Entiteettikenttien yhdistäminen PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten voit linkittää entiteettikentät'
ms.custom: ''
ms.date: 05/29/2018
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
ms.assetid: 7c5aa1c3-bde9-43f1-a369-fdcdbf14dec0
caps.latest.revision: 33
ms.author: matp
manager: kvivek
tags: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="map-entity-fields"></a>Entiteettikenttien yhdistäminen
 
Voit yhdistää määritteet entiteettien välillä, joilla on entiteettisuhde. Näin voit määrittää oletusarvot tietueelle, joka luodaan yhteydessä toiseen tietueeseen. 

## <a name="easier-way-to-create-new-records-in-model-driven-apps"></a>Helpompi tapa luoda uusia tietueita mallipohjaisissa sovelluksissa

Oletetaan, että käyttäjä haluaa lisätä uuden yhteyshenkilötietueen henkilölle, joka on tietyn asiakkaan työntekijä. Tämän voi tehdä kahdella seuraavalla tavalla:  
  
### <a name="the-hard-way"></a>Vaikea tapa

Käyttäjä voi siirtyä sovelluksessa ja luoda uuden yhteystietotietueen tyhjästä. Mutta silloin käyttäjän on asetettava pääasiakas ja syötettävä sille useita tietoja (kuten osoite ja puhelinnumero), jotka ovat luultavasti samoja kuin pääasiakkaalla. Tämä voi olla aikaavievää ja lisää virheiden mahdollisuuksia.  
  
### <a name="the-easier-way"></a>Helpompi tapa

Helpompi tapa on aloittaa Asiakas-entiteetistä ja käyttämällä **yhteystiedot** aliruudukkoa lomakkeessa valitsemalla **+** yhteyshenkilön lisäämiseksi. Tämä tapa ohjaa käyttäjää hakemaan esiin olemassa olevat liittyvät yhteystiedot, ettei käyttäjä vahingossa luo kaksoiskappaletta. Jos käyttäjä ei löydä aiemmin luotua tietuetta, hän voi valita **Uusi**-kohdan ja luoda uuden yhteyshenkilötietueen. 

Uusi yhteyshenkilötietuelomake sisältää mitä tahansa yhdistetyn määritteen arvoja asiakkaasta (kuten osoitteen ja puhelimen tiedot) oletusarvoina. Käyttäjä voi muokata näitä arvoja ennen tietueen tallentamista.

## <a name="how-this-works"></a>Toiminta

Kun yhdistät entiteettikentät 1:n-suhteelle, tietyt ensisijaisen entiteettitietueen tietojen kohteet kopioidaan uuteen liittyvään entiteettilomakkeeseen. Näin voidaan määrittää oletusarvot, joita käyttäjät voivat muokata ennen tallentamista.
 
  
> [!NOTE]
> Yhdistämismääritykset asettavat ainoastaan oletusarvot tietuelle ennen kuin se tallennetaan. Käyttäjät voivat muokata arvoja ennen tallentamista. Siirrettävät tiedot ovat senhetkisiä. Tietoja ei synkronoida, jos lähdetietoja muutetaan myöhemmin.
>   
> Näitä yhdistämismäärityksiä ei käytetä työnkulku- tai dialogiprosessien avulla luotuihin liittyviin tietueisiin. Niitä ei oteta automaattisesti käyttöön uusille tietueille, jotka on luotu käyttämällä koodia, vaikka kehittäjät voivat käyttää erityistä viestiä, jonka nimi on `InitializeFrom` ([InitializeFrom-toiminto](/dynamics365/customer-engagement/web-api/initializefrom?view=dynamics-ce-odata-9) tai [InitializeFromRequest-luokka](/dotnet/api/microsoft.crm.sdk.messages.initializefromrequest?view=dynamics-general-ce-9)), luodakseen uuden tietueen käytettävillä yhdistämismäärityksillä.  

## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Ainoa tapa yhdistää entiteettikentät on käyttää ratkaisunhallintaa.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]
  
Kenttien yhdistäminen tehdään 1:N- tai N:1-entiteettisuhteen kontekstissa, joten ensi täytyy [tarkastella 1:N- tai N:1-entiteettisuhteita](create-edit-1n-relationships-solution-explorer.md#view-entity-relationships).

## <a name="view-mappable-fields"></a>Yhdistettävissä olevien kenttien tarkasteleminen

Kenttien yhdistämisiä ei määritetä todellisuudessa entiteettisuhteissa, vaan ne näkyvät suhteen käyttöliittymässä. Kaikilla 1:N-entiteettisuhteilla ei ole niitä. Kun tarkastelen entiteetin 1:N (tai N:1)-suhteita, voit suodattaa niitä tyypin perusteella. Voit valita **Kaikki**, **Mukautettu**, **Mukautettavissa**, tai **Määritettävissä**. Määritettävissä olevat entiteettisuhteet mahdollistavat entiteettikenttien määrittämisen. 

![Yhdistettävien entiteettisuhteiden tarkasteleminen](media/mappable-entity-relationships.png) 

Kun avaat yhdistettävän entiteettisuhteen, valitse vasemmassa siirtymistoiminnossa **Yhdistämismääritykset**.

![Entiteettisuhteen yhdistämismääritysten valitseminen](media/map-entity-fields-ui-solution-explorer.png)

## <a name="delete-mappings"></a>Yhdistämismääritysten poistaminen

Jos olemassa on yhdistämismäärityksiä, joita et halua käyttää, voit valita ne ja valita sitten ![Poisto-kuvakkeen](media/delete.gif) -kuvaketta.

## <a name="add-new-mappings"></a>Uusien yhdistämismääritysten lisääminen

Jos haluat luoda uuden yhdistämismäärityksen, valitse työkaluriviltä **Uusi**. Näyttöön tulee **Luo kenttien yhdistämismääritys** -valintaikkuna.

![Luo kenttien yhdistämismääritys -valintaikkuna](media/create-field-mapping-dialog.png)

Valitse yksi lähde-entiteettikenttä ja yksi kohde-entiteettikenttä ja arvot, jotka haluat yhdistää. 

![Kentän yhdistämismäärityksen määrittäminen](media/configure-field-mapping.png)

Sulje sitten valintaikkuna valitsemalla **OK**.

Seuraavat säännöt määrittävät, minkälaisia tietoja voi yhdistää.  
  
- Kenttien on oltava samantyyppiset ja-muotoiset.  
- Kohdekentän on oltava vähintään yhtä pitkä kuin lähdekenttä.  
- Kohdekenttä ei saa olla yhdistettynä toiseen kenttään.  
- Lähdekentän on oltava näkyvissä lomakkeessa.  
- Kohdekentän on oltava kenttä, johon käyttäjä voi syöttää tietoja.  
- Osoitteiden tunnusarvoja ei voi yhdistää.
- Jos aiot luoda yhdistämismäärityksen kentälle, joka ei ole näkyvissä lomakkeessa, yhdistäminen ei onnistu, ennen kuin lisäät kentän lomakkeeseen.
- Jos kentät muodostavat asetusjoukon, kaikkien vaihtoehtojen kokonaislukuarvojen on oltava samat.  
  
> [!NOTE]
>  Jos haluat yhdistää asetusjoukkokenttiä, on suositeltavaa määrittää molemmat kentät käyttämään samaa yleistä asetusjoukkoa. Kahden eri asetusjoukon ylläpitäminen käsin olisi muutoin vaikeaa. Jos jokaisen asetuksen kokonaislukuarvoa ei ole määritetty oikein, tietojoukossasi voi seurauksena olla ongelmia. Lisätietoja: [Common Data Servicen yleisten asetusjoukkojen luominen ja muokkaaminen (valintaluettelot)](create-edit-global-option-sets.md)  
  
## <a name="automatically-generate-field-mappings"></a>Yhdistämismääritysten luominen automaattisesti  

Voit luoda yhdistämismäärityksiä myös automaattisesti valitsemalla **Luo yhdistämismääritykset** **Lisää toimintoja** -valikossa.

Ole varovainen, kun teet tämän järjestelmäentiteeteille. Käytä tätä, kun haluat luoda mukautettuja entiteettejä ja käyttää hyväksesi yhdistämismäärityksiä. 

> [!WARNING]
> Tämä poistaa kaikki aikaisemmat yhdistämismääritykset ja korvaa ne ehdotetuilla määrityksillä, jotka perustuvat vain kenttiin, joilla on samankaltaiset nimet ja tietotyypit. Jos käytät tätä järjestelmäentiteetille, jotkin odotettavat yhdistämismääritykset voivat kadota. Mukautetuille entiteeteille se säästää aikaa, koska voit helposti poistaa määritykset, joita et halua ja lisätä muita määrityksiä, joita automaattinen työkalu ei luonut.  


## <a name="publish-customizations"></a>Mukautusten julkaiseminen 

Koska kenttien yhdistämismääritykset eivät ole metatietoja, niiden muutokset otetaan käyttöön vasta julkaisemisen jälkeen. 
<!-- TODO Need a general topic about publishing to link to in situations like this -->

### <a name="see-also"></a>Katso myös
[1:N (yksi moneen)- ja N:1 (monta yhteen) -entiteettisuhteiden luominen ja muokkaaminen ratkaisunhallinnan avulla](create-edit-1n-relationships-solution-explorer.md)<br />
[Sovelluskehittäjän dokumentaatio: Entiteettien ja määritteiden yhdistämismääritysten mukauttaminen](/dynamics365/customer-engagement/developer/customize-entity-attribute-mappings)<br />
[Sovelluskehittäjän dokumentaatio: Web-ohjelmointirajapinnan uuden entiteetin luominen toisesta entiteetistä](/dynamics365/customer-engagement/developer/webapi/create-entity-web-api#create-a-new-entity-from-another-entity)
