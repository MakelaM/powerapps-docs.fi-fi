---
title: Ratkaisujen tuominen. päivittäminen ja vieminen | MicrosoftDocs
description: 'Opettele ratkaisun tuominen, päivittäminen tai vieminen'
ms.custom: ''
ms.date: 06/18/2018
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
ms.assetid: 56363ea3-ea76-4311-9b7a-b71675e446fb
caps.latest.revision: 57
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="import-update-and-export-solutions"></a>Ratkaisujen tuominen. päivittäminen ja vieminen 

 Voit tuoda ratkaisuja manuaalisesti seuraavien ohjeiden mukaisesti. Tuo vain luotettavasta lähteestä saatuja ratkaisuja. Mukautukset voivat sisältää koodia, joka voi lähettää tietoja ulkoisiin lähteisiin. Voit tuoda oletusratkaisun vain organisaatioon, josta olet vienyt sen, mutta sitä ei liitetä toiseen organisaatioon.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.  
  
2.  Valitse ratkaisuluettelon valikosta **Tuo**.  
  
3.  Siirry **Tuo ratkaisu** -valintaikkunan **Valitse ratkaisupaketti** -kohdassa tuotavan ratkaisun sisältävään pakattuun tiedostoon (.zip tai .cab). 
  
4.  Valitse **Seuraava**.  
  
5.  Voit tarkastella ratkaisun tietoja, ennen kuin valitset **Tuo**.  
  
6.  Ratkaisun tuonti voi kestää hetken. Jos tuonti onnistuu, voit tarkastella tuloksia ja valita **Sulje**.  
  
 Jos olet tuonut julkaistavia muutoksia, mukautuksia ei voi käyttää, ennen kuin ne on julkaistu. 
  
 Jos tuonti ei onnistunut, avautuva raportti sisältää mahdolliset virheet tai varoitukset. Jos haluat nähdä tarkempia tietoja tuonnin epäonnistumisesta, valitse **Lataa lokitiedosto**. Ratkaisun tuonti epäonnistuu useimmin siksi, että ratkaisu ei sisältänyt pakollisia ratkaisun osia.  
  
 Ladattu lokitiedosto sisältää XML-tiedoston, jonka sisältöä voit tarkastella avaamalla sen Office Excelissä.  
  
> [!NOTE]
>  Aktiivista reitityssääntöjoukkoa ei voi muokata. Jos siis tuot ratkaisun, jonka aktiivinen reitityssääntöjoukko on määritetty organisaatioon, jossa on jo samalla tunnuksella luotu sääntö, ratkaisun tuonti epäonnistuu. Lisätietoja: [Palvelupyyntöjen automaattisten reitityssääntöjen luominen](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/create-rules-automatically-route-cases)  
  
<a name="BKMK_UpdateSolutions"></a>   

## <a name="update-solutions"></a>Ratkaisujen päivittäminen  
 Haluat ehkä joskus asentaa päivityksen nykyiseen hallittuun ratkaisuun. Asennus muistuttaa uuden hallitun ratkaisun asentamista, myös käytettävät asetukset ovat hieman erilaiset. Jos päivität muualta saatua ratkaisua, kysy ratkaisujulkaisulta lisätietoja käytettävistä asetuksista.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse ratkaisuluettelon valikossa **Tuo**.  
  
3.  Siirry **Tuo ratkaisu** -valintaikkunan **Valitse ratkaisupaketti** -kohdassa päivitettävän ratkaisun sisältävään pakattuun tiedostoon (.zip tai .cab).  
4.  Valitse **Seuraava**.  
  
5.  Voit tarkastella ratkaisun tietoja, ennen kuin valitset **Seuraava**. Sivulla on keltainen palkki, jossa lukee **Tämä ratkaisupaketti sisältää jo asennetun ratkaisun päivityksen**.  
  
6.  Käytettävissä on seuraavat vaihtoehdot:  
  
    - **Säilytä mukautukset (suositellaan)**  
  
         Jos tämä vaihtoehto valitaan, osille tehdyt ei-hallitut mukautukset säilyvät, mutta jotkin ratkaisuun sisältyvistä päivityksistä eivät tule voimaan.  
  
    - **Korvaa mukautukset**  
  
         Jos tämä vaihtoehto valitaan, tähän ratkaisuun sisältyville osille aiemmin suoritetut ei-hallitut mukautukset korvataan. Kaikki ratkaisuun sisältyvät päivitykset tulevat voimaan.  
  
     Valitse ensin sopiva vaihtoehto ja sitten **Seuraava**.  
  
7.  Ratkaisun tuonti voi kestää hetken. Jos tuonti onnistuu, voit tarkastella tuloksia ja valita **Sulje**.  
  
 Jos olet tuonut julkaistavia muutoksia, mukautuksia ei voi käyttää, ennen kuin ne on julkaistu. 
  
 Ratkaisujulkaisijat voivat pyytää sinua viemään nykyiset ei-hallitut mukautukset, päivittämään hallitut ratkaisut mukautusten korvausvaihtoehdolla ja tuomaan sitten ei-hallitut mukautukset uudelleen. Tällä tavoin varmistetaan, että odotetut muutokset otetaan käyttöön samalla, kun mukautukset säilyvät.  
  
<a name="BKMK_ExportSolutions"></a>   

## <a name="export-solutions"></a>Ratkaisujen vieminen  
 On suositeltavaa viedä ei-hallitut mukautukset säännöllisesti varmuuskopioiksi mahdollisia ongelmatilanteita varten. Hallittuja ratkaisuja ei voi viedä.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse ensin luettelosta vietävä ratkaisu ja sitten **Vie**.  
  
3.  **Julkaise mukautukset** -vaiheessa sinua muistutetaan, että vain julkaistut mukautukset viedään ja että voit valita **Julkaise kaikki mukautukset**, ennen kuin valitset **Seuraava**.  
  
4.  Jos ratkaisu sisältää puuttuvia pakollisia osia, näet **Pakollisia osia puuttuu** -vaiheen. Jätä tämä varoitus huomioimatta vain, jos aiot tuoda ratkaisun ei-hallittuna ratkaisuna takaisin alkuperäiseen organisaation. Peruuta muussa tapauksessa vienti valintaikkunan ohjeiden mukaisesti ja lisää pakolliset osat.  
  
5.  Voit sisällyttää tiettyjä järjestelmäasetuksia ratkaisuun **Vie järjestelmäasetukset (lisäasetukset)** -vaiheessa. Jos ratkaisu tarvitsee jotakin järjestelmäasetusten ryhmää, valitse ensin se ja sitten **Seuraava**.  
  
     Katso alla olevasta **Ratkaisun viennin asetusvaihtoehdot** -kohdasta lisätietoja asetuksista, jotka ovat mukana vaihtoehdoissa.  
  
6.  Sinun on valittava **Paketin tyyppi**-vaiheessa, viedäänkö ratkaisu **ei-hallittuna** vai **hallittuna** ratkaisuna.  
  
7.  Voit valita seuraavassa vaiheessa tietyn Dynamics 365 -version kohderatkaisun. Yleensä tätä asetusta käyttävät riippumattomat ohjelmistovalmistajat, jotka haluavat viedä edellisen version kanssa yhteensopivan ratkaisun. Hyväksy oletusasetus, ellet aio tuoda ratkaisua organisaatioon, jota ei ole päivitetty käyttämääsi organisaatioversioon.   
  
8.  Lataa ratkaisutiedosto valitsemalla **Vie**.  
  
 Lataustapahtuma määräytyy selaimen mukaan.  

<a name="BKMK_SettingsOptionsOnSolutionExport"></a>  
 
## <a name="settings-options-for-solution-export"></a>Ratkaisun viennin asetusvaihtoehdot  
 Seuraavassa taulukossa on ratkaisun viennissä käytettävissä olevat vaihtoehdot:  
  
|Ryhmä|Asetukset|Kuvaus|  
|-----------|-------------|-----------------|  
|Automaattinen numerointi|Kampanjan etuliite|Kampanjoiden numeroinnin etuliite.|  
|Palvelupyynnön etuliite|Etuliite, jota käytetään kaikissa sovelluksen palvelupyynnöissä.|  
|Palvelusopimuksen etuliite|Etuliite, jota käytetään kaikissa palvelusopimuksissa sovelluksessa.|  
|Laskun etuliite|Etuliite, jota käytetään kaikissa laskunumeroissa sovelluksessa.|  
|Artikkelin etuliite|Etuliite, jota käytetään kaikissa artikkeleissa sovelluksessa.|  
|Tilauksen etuliite|Etuliite, jota käytetään kaikissa tilauksissa sovelluksessa.|  
|Yksilöllinen merkkijonon pituus|Laskun, tarjouksen ja tilauksen numeroihin liitettävä merkkimäärä.|  
|Kalenteri|Kalenterityyppi|Järjestelmän kalenterityyppi. Oletusarvo on gregoriaaninen (USA).|  
|Päivämäärän muotokoodi|Tietoja siitä, miten päivämäärät näytetään Dynamics 365:ssä.|  
|Päivämääräerotin|Merkki, joka erottaa päivämäärien kuukausi-, päivä- ja vuosiarvot sovelluksessa.|  
|Tapaamisen enimmäiskesto|Tapaamisen enimmäiskesto päivinä.|  
|Näytä viikon numero|Tieto siitä, näytetäänkö sovelluksessa kalenterinäytöissä viikon numero.|  
|Aikamuodon koodi|Tieto siitä, miten kellonaika näytetään sovelluksessa.|  
|Viikon aloituspäivän koodi|Määritetty viikon ensimmäinen päivä sovelluksessa.|  
|Mukauttaminen|Sovelluksen tila on käytössä|Osoittaa, voiko sovelluksen ladata selainikkunaan, jossa ei ole käytössä osoite-, työkalu- ja valikkoriviä.|  
|Sähköpostiseuranta|Salli sähköpostin lähettäminen selvittämättömään osoitteeseen|Osoittaa, voivatko käyttäjät lähettää sähköpostia selvittämättömille osapuolille (osapuolilla on kuitenkin oltava sähköpostiosoite).|  
|Ohita sisäinen sähköposti|Osoittaa, seurataanko sovelluksen käyttäjien tai jonojen lähettämää saapuvaa sähköpostia.|  
|Suurin seurantanumero|Suurin mahdollinen seurantanumero ennen kierrätystä.|  
|Hahmonna suojattu kehys sähköpostille|Valitse tämä, jos haluat muuntaa sähköpostiviestin tekstin verkkolomakkeessa IFRAME-kehykseksi, jossa on määrite security='restricted'. Tämä lisäsuojaus voi johtaa siihen, että järjestelmä pyytää käyttäjän tunnistetietoja.|  
|Seurantaetuliite|Seurantatunnusten etuliitteiden historialuettelo.|  
|Seurantatunnuksen perusnumero|Perusnumero, jolla annetaan eri käyttöympäristöihin kuuluville käyttäjille erilliset seurantatunnukset.|  
|Seurantatunnuksen numerot|Seurantatunnuksessa käytettävä numeroiden määrä.|  
|Yleiset|Estä liitteet|Vaarallisiksi katsottujen liitetyyppien latauksen estäminen.|  
|Rahasumman muotokoodi|Tieto siitä, miten rahayksiköiden tunnukset sijoitetaan sovelluksessa.|  
|Rahayksikön tunnus|Rahayksikön tunnus|  
|Koko nimen näyttöjärjestys|Nimien näyttöjärjestys sovelluksessa.|  
|Tavoitettavuus otettu käyttöön|Tietoja siitä, onko IM-tavoitettavuus otettu käyttöön.|  
|Negatiivinen muoto|Osoittaa, miten negatiiviset valuutta-arvot näytetään sovelluksessa.|  
|Luvun muoto|Määrittää, miten luvut näytetään sovelluksessa.|  
|Hinnoittelussa käytettävä desimaalien määrä|Hintojen desimaalipaikkojen määrä.|  
|Jaa edelliselle omistajalle delegoitaessa|Tieto siitä, jaetaanko kohde edelliselle omistajalle delegoinnin yhteydessä.|  
|Markkinointi|Salli automaattisen vastauksen luonti|Osoittaa, sallitaanko automaattisen vastauksen luonti.|  
|Salli automaattinen tilaamisen lopettaminen|Osoittaa, sallitaanko automaattinen tilaamisen lopettaminen.|  
|Salli automaattinen tilaamisen lopettamisen kuittaus|Osoittaa, sallitaanko automaattisen tilaamisen lopettamisen kuittaussähköpostiviestin lähettäminen.|  
|Salli markkinointisähköpostiviestien suorittaminen|Osoittaa, sallitaanko markkinointisähköpostiviestien suorittaminen.|  
| Outlook-synkronointi|Salli osoitteiston synkronointi|Osoittaa, sallitaanko Microsoft Office Outlook -osoitteiston synkronointi taustalla.|  
|Salli aikataulutettu offline-synkronointi|Osoittaa, sallitaanko Outlookin offline-synkronointi taustalla.|  
|Salli aikataulutettu synkronointi|Osoittaa, sallitaanko aikataulutetut synkronoinnit Outlookiin.|  
|Sähköpostilähetyksen kyselyväli|Normaali kyselytiheys, jota käytetään lähetettäessä sähköpostia Outlookissa.|  
|Pienin osoitteen synkronointiväli|Normaali kyselytiheys osoitteiston synkronoinnissa Outlookissa.|  
|Pienin offline-synkronointiväli|Normaali kyselytiheys Outlookin offline-taustasynkronoinnissa.|  
|Pienin synkronointiväli|Pienin sallittu aika aikataulutettujen Outlook-synkronointien välillä.|  
|Enimmäiskierrot automaattisessa tunnisteiden luonnissa|Enimmäismäärä aggressiivisia kyselykiertoja, jotka suoritetaan sähköpostin automaattiselle tunnisteiden luonnille, kun uusi sähköpostiviesti vastaanotetaan.|  
|Automaattisen tunnisteiden luonnon väli|Normaali kyselytiheys sähköpostiviestien automaattisessa tunnisteiden luonnissa Outlookissa.|  
|Riippumattoman ohjelmistotoimittajan määritys|Palvelukalenterin ulkoasumääritys|Voit määrittää visuaalisia tyylejä palvelukalentereille.

Lisätietoja: [Palvelukalenterin ulkoasumääritys](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/service-calendar-appearance-configuration)|

  
## <a name="next-steps"></a>Seuraavat vaiheet

[Ratkaisujen ja korjaustiedostojen jakaminen](use-segmented-solutions-patches-simplify-updates.md)
