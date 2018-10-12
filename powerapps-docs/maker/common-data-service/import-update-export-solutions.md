---
title: Ratkaisujen tuominen, päivittäminen ja vieminen | MicrosoftDocs
description: Opi tuomaan, päivittämään ja viemään ratkaisuja
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
ms.openlocfilehash: 89907e80085fe2bfcf3c38972724a0f9b55836c7
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675523"
---
# <a name="import-update-and-export-solutions"></a>Ratkaisujen tuominen, päivittäminen ja vieminen 

 Voit tuoda ratkaisuja manuaalisesti noudattamalla alla olevia ohjeita. Tuo vain ratkaisuja, jotka olet hankkinut luotetusta lähteestä. Mukautukset voivat sisältää koodia, joka lähettää tietoja ulkoisiin lähteisiin. Voit tuoda oletusratkaisun vain organisaatioon, josta veit sen, et muuhun organisaatioon.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.  
  
2.  Valitse ratkaisuluettelovalikosta **Tuo**.  
  
3.  Valitse **Tuo ratkaisu** -valintaikkunassa **Valitse ratkaisupaketti**, ja siirry sen pakatun (.zip tai .cab) tiedoston kohdalle, joka sisältää tuotavan ratkaisun. 
  
4.  Valitse **Seuraava**.  
  
5.  Voit tarkastella ratkaisun tietoja, ennen kuin valitset **Tuo**.  
  
6.  Voit joutua odottamaan hetken, kunnes ratkaisun tuonti on valmis. Jos tuonti onnistuu, voit tarkastella tuloksia ja valita sitten **Sulje**.  
  
 Jos olet tuonut muutoksia, jotka edellyttävät julkaisemista, sinun täytyy julkaista mukautukset, ennen kuin ne ovat käytettävissä. 
  
 Jos tuonti ei onnistu, näet raportin, jossa on havaitut virheet tai varoitukset. Voit valita **Lataa lokitiedosto** tallentaaksesi tiedot tuonnin epäonnistumisen syystä. Yleisin syy ratkaisun tuonnin epäonnistumiseen on, että ratkaisu ei sisällä joitakin vaadittuja ratkaisun osia.  
  
 Kun lataat lokitiedoston, voit avata sen (XML-muodossa) Office Excelissä sisällön katselua varten.  
  
> [!NOTE]
>  Et voi muokata aktiivista reitityssääntöjoukkoa. Tämän vuoksi, jos olet tuomassa aktiivisen reitityssääntöjoukon sisältävää ratkaisua organisaatioon, jossa sama sääntö on jo olemassa samalla tunnuksella, ratkaisun tuonti epäonnistuu. Lisätietoja: [Luo sääntöjä tapausten automaattista reititystä varten](https://docs.microsoft.com/dynamics365/customer-engagement/customer-service/create-rules-automatically-route-cases)  
  
<a name="BKMK_UpdateSolutions"></a>   

## <a name="update-solutions"></a>Päivitä ratkaisut  
 Joskus haluat ehkä asentaa päivityksen nykyiseen hallittuun ratkaisuun. Menettely on vastaava kuin uutta hallittua ratkaisua asennettaessa, mutta käytettävissä on joitakin eri asetuksia. Jos olet päivittämässä joltakulta muulta saatua ratkaisu, pyydä ratkaisun julkaisijalta ohjeita siitä, mitä asetuksia sinun pitää valita.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse ratkaisuluettelovalikosta **Tuo**.  
  
3.  Valitse **Tuo ratkaisu** -valintaikkunassa **Valitse ratkaisupaketti**, ja siirry sen pakatun (.zip tai .cab) tiedoston kohdalle, joka sisältää päivitettävän ratkaisun.  
4.  Valitse **Seuraava**.  
  
5.  Voit tarkastella ratkaisun tietoja, ennen kuin valitset **Seuraava**. Tällä sivulla näkyy keltainen palkki, jossa on ilmoitus **Tämä ratkaisupaketti sisältää päivityksen ratkaisuun, joka on jo asennettu**.  
  
6.  Käytettävissä on seuraavat vaihtoehdot:  
  
    - **Säilytä mukautukset (suositus)**  
  
         Jos valitset tämän vaihtoehdon, kaikki osille suoritetut hallitsemattomat mukautukset säilytetään, mutta kaikki ratkaisun päivitykset eivät tule voimaan.  
  
    - **Korvaa mukautukset**  
  
         Jos valitset tämän vaihtoehdon, kaikki tämän ratkaisun osille suoritetut hallitsemattomat mukautukset korvataan. Kaikki tämän ratkaisun sisältämät päivitykset tulevat voimaan.  
  
     Valitse sopiva vaihtoehto ja valitse sitten **Seuraava**.  
  
7.  Voit joutua odottamaan hetken, kunnes ratkaisun tuonti on valmis. Jos tuonti onnistuu, voit tarkastella tuloksia ja valita sitten **Sulje**.  
  
 Jos olet tuonut muutoksia, jotka edellyttävät julkaisemista, sinun täytyy julkaista mukautukset, ennen kuin ne ovat käytettävissä. 
  
 Ratkaisun julkaisijat saattavat pyytää sinua viemään olemassa olevat hallitsemattomat mukautuksesi, päivittämään niiden hallitun ratkaisun käyttämällä Korvaa mukautukset -vaihtoehtoa ja tuomaan sitten hallitsemattomat mukautuksesi uudelleen. Tämä auttaa varmistamaan, että odotetut muutokset tulevat voimaan ja mukautuksesi säilytetään.  
  
<a name="BKMK_ExportSolutions"></a>   

## <a name="export-solutions"></a>Vie ratkaisut  
 Suosittelemme, että viet hallitsemattomat mukautuksesi säännöllisesti, jotta sinulla on niistä varmuuskopio pahan päivän varalta. Et voi viedä hallittuja ratkaisuja.  
  
1. Siirry kohtaan **[Asetukset](../model-driven-apps/advanced-navigation.md#settings)** > **Ratkaisut**.   
  
2.  Valitse luettelosta ratkaisu, jonka haluat viedä, ja valitse sitten **Vie**.  
  
3.  **Julkaise mukautukset** -vaiheessa sinua muistutetaan siitä, että vain julkaistut mukautukset viedään ja sinulla on mahdollisuus **julkaista kaikki mukautukset** ennen kuin valitset  **Seuraava**.  
  
4.  Jos ratkaisusi sisältää puuttuvia vaadittuja osia, näkyviin tulee **Puuttuvat vaaditut osat** -vaihe. Voit ohittaa tämän varoituksen vain, jos aiot tuoda tämän hallitsemattoman ratkaisun takaisin alkuperäiseen organisaation. Muussa tapauksessa peruuta vienti noudattamalla valintaikkunassa annettuja ohjeita ja lisää vaaditut osat.  
  
5.  **Vie järjestelmäasetukset (Lisäasetukset)** -vaiheessa voit valita ratkaisuusi sisällytettävät tietyt järjestelmäasetukset. Jos ratkaisusi on riippuvainen mistä tahansa järjestelmäasetusryhmistä, valitse ne ja valitse **Seuraava**.  
  
     Katso lisätietoja kunkin vaihtoehdon asetuksista alla olevasta kohdasta **Ratkaisun vientiasetukset**.  
  
6.  **Paketin tyyppi** -vaiheessa sinun täytyy valita, haluatko viedä ratkaisun **hallitsemattomana** vai **hallittuna** ratkaisuna.  
  
7.  Seuraavassa vaiheessa voit valita kohderatkaisun tiettyä Dynamics 365 -versiota varten. Tätä asetusta käyttävät yleensä itsenäiset ohjelmistotoimittajat, jotka haluavat viedä aiemman version kanssa yhteensopivan ratkaisun. Ellet ole tuomassa ratkaisua organisaatioon, jota ei ole päivitetty samaan versioon kuin käyttämäsi organisaatio, käytä oletusarvoa.   
  
8.  Lataa ratkaisutiedosto valitsemalla **Vie**.  
  
 Tiedostojen lataustapa vaihtelee selainten välillä.  

<a name="BKMK_SettingsOptionsOnSolutionExport"></a>  
 
## <a name="settings-options-for-solution-export"></a>Ratkaisun vientiasetukset  
 Seuraavassa taulukossa on käytettävissä olevat vaihtoehdot, kun viet ratkaisua:  
  
|Ryhmä|Asetus|Kuvaus|  
|-----------|-------------|-----------------|  
|Automaattinen numerointi|Kampanjan etuliite|Kampanjan numeroinnin etuliite.|  
|Tapauksen etuliite|Etuliite, jota käytetään kaikissa tapauksissa koko sovelluksessa.|  
|Sopimuksen etuliite|Etuliite, jota käytetään kaikissa sopimuksissa koko sovelluksessa.|  
|Laskun etuliite|Etuliite, jota käytetään kaikissa laskunumeroissa koko sovelluksessa.|  
|Artikkelin etuliite|Etuliite, jota käytetään kaikissa artikkeleissa koko sovelluksessa.|  
|Tilauksen etuliite|Etuliite, jota käytetään kaikissa tilauksissa koko sovelluksessa.|  
|Yksilöllinen merkkijonon pituus|Laskun, tarjouksen ja tilausnumeroiden merkkimäärä.|  
|Kalenteri|Kalenterin tyyppi|Järjestelmän kalenterityyppi. Oletusarvoisesti Gregoriaaninen (US)|  
|Päivämäärämuodon koodi|Tieto siitä, miten päivämäärä näytetään Dynamics 365:ssä.|  
|Päivämääräerotin|Merkki, jolla erotetaan kuukauden, päivän ja vuoden päivämäärät koko sovelluksessa.|  
|Tapaamisen enimmäiskesto|Tapaamisen pisin kesto päivinä.|  
|Näytä viikkonumero|Tieto, joka määrittää, näytetäänkö viikkonumero kalenterissa koko sovelluksessa.|  
|Aikamuodon koodi|Tieto, joka määrittää, miten aika näytetään koko sovelluksessa.|  
|Viikon aloituspäivän koodi|Viikon ensimmäinen päivä koko sovelluksessa.|  
|Mukauttaminen|Onko sovellustila käytössä|Ilmaisee, onko sovelluksen lataus selainikkunassa ilman osoite-, työkalu- ja valikkorivejä käytettävissä.|  
|Sähköpostiseuranta|Salli sähköpostiviestin lähetys selvittämättömään osoitteeseen|Ilmaisee, voivatko käyttäjät lähettää sähköpostia selvittämättömille osapuolille (osapuolilla on silti oltava sähköpostiosoite).|  
|Ohita sisäinen sähköposti|Ilmaisee, seurataanko sovelluksen käyttäjien tai jonojen lähettämiä sähköpostiviestejä.|  
|Suurin seurantanumero|Suurin mahdollinen seurantanumero ennen kierrätystä.|  
|Hahmonna suojattu kehys sähköpostille|Merkintä, joka hahmontaa sähköpostiviestin leipätekstin IFRAMEssa määritteellä-= 'restricted'. Tämä on lisäsuojaustapa, mutta se saattaa tuoda näyttöön tunnistetietojen kehotteen.|  
|Seurannan etuliite|Historialuettelo seurantatunnusten etuliitteistä.|  
|Seurantatunnuskanta|Kantaluku, jolla erotellaan eri käyttöönottojen käyttäjien seurantatunnusten tunnisteet.|  
|Seurantatunnusnumerot|Seurantatunnuksen tunnisteen numeromäärä.|  
|Yleistä|Estä liitteet|Estä tietynlaisten vaaralliseksi katsottujen liitetiedostojen lähetys ja lataus.|  
|Valuuttamuotokoodi|Tieto siitä, miten valuuttasymbolit sijoitetaan koko sovelluksessa.|  
|Valuuttasymboli|Valuuttasymboli|  
|Koko nimen näyttöjärjestys|Järjestys, jossa nimet näytetään koko sovelluksessa.|  
|Tavoitettavuus käytössä|Tieto siitä, onko pikaviestillä tavoitettavuus käytössä.|  
|Negatiivinen muoto|Tieto, joka määrittää, miten negatiiviset luvut näytetään koko sovelluksessa.|  
|Lukumuotoilu|Lukujen näyttötavan määritystapa koko sovelluksessa.|  
|Hinnoittelussa käytettävä desimaalien määrä|Hinnoissa käytettävien desimaalien paikkamäärä.|  
|Jaa edelliselle omistajalle määritettäessä|Määrittää, jaetaanko kohde edelliselle omistajalle määritettäessä.|  
|Markkinointi|Salli automaattinen vastauksen luonti|Ilmaisee, onko automaattisen vastauksen luonti sallittu|  
|Salli automaattinen tilauksen peruutus|Ilmaisee, onko automaattinen tilauksen peruutus sallittu.|  
|Salli automaattinen tilauksen peruutuksen kuittaus|Ilmaisee, onko automaattinen tilauksen peruutuksen kuittaussähköpostin lähetys sallittu.|  
|Salli markkinointisähköpostin suorittaminen|Ilmaisee, onko markkinointisähköpostiviestien suorittaminen sallittu.|  
| Outlook-synkronointi|Salli osoitekirjan synkronointi|Ilmaisee, onko osoitekirjan synkronointi taustalla sallittu Microsoft Office Outlookissa.|  
|Salli ajoitettu offline-synkronointi|Ilmaisee, onko offline-synkronointi taustalla sallittu Outlookissa.|  
|Salli ajoitettu synkronointi|Ilmaisee, onko ajoitetut synkronoinnit Outlookiin sallittuja.|  
|Sähköpostin lähettämisen kyselytiheys|Normaali kyselytiheys, jota käytetään sähköpostin lähettämiseen Outlookissa.|  
|Pienin osoitteen synkronointitiheys|Normaali kyselytiheys osoitekirjan synkronointiin Outlookissa.|  
|Pienin offline-synkronointitiheys|Normaali kyselytiheys osoitekirjan offline-taustasynkronointiin Outlookissa.|  
|Pienin synkronointitiheys|Pienin sallittu aika ajoitettujen [! INCLUDEOutlooksynchronizations välillä.|  
|Automaattisten tunnisteiden enimmäisjaksot|Suurin aggressiivisten kyselyjaksojen suoritusmäärä sähköpostien automaattiseen merkintään, kun uusi sähköposti vastaanotetaan.|  
|Automaattisten tunnisteiden väli|Normaali kyselytiheys, jota käytetään sähköpostin automaattiseen merkintään Outlookissa.|  
|ISV-määritys|Palvelukalenterin ulkoasun määritys|Voit määrittää palvelunkalentereiden visuaaliset tyylit.

Lisätietoja: [Palvelukalenterin ulkoasun määritys](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/service-calendar-appearance-configuration)|

  
## <a name="next-steps"></a>Seuraavat vaiheet

[Ratkaisujen ja korjausten jakelu](use-segmented-solutions-patches-simplify-updates.md)