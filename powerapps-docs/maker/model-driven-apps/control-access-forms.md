---
title: Mallipohjaisen sovelluksen lomakkeiden käytön hallinta PowerAppsissa | MicrosoftDocs
description: Päälomakkeiden käytön hallinta
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 15d123e0-b604-45dd-ab34-0b37787a04bb
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
# <a name="control-access-to-model-driven-app-forms"></a>Mallipohjaisen sovelluksen lomakkeiden käytön hallinta

 Voit valvoa päälomakkeiden käyttöä kahdella tavalla:  
  
- **Tee päälomakkeesta passiivinen**  
  
     Voit määrittää päälomakkeen tilan aktiiviseksi tai passiiviseksi. Tämä ominaisuus sisältyi ensisijaisesti uusien lomakkeiden hallintaan kun Dynamics 365 Customer Engagement -organisaatioiden päivitysten yhteydessä, mutta sen avulla voidaan estää käyttäjiä käyttämästä mitään päälomaketta.   
  
- **Käyttöoikeusroolien liittäminen päälomakkeeseen**  
  
     Tämän avulla voit tehdä päälomakkeen käytettäväksi tietyissä ryhmissä.  
  
 Eri henkilöt organisaatiossasi voivat käsitellä samoja tietoja eri tavoin. Johtajat saattavat voida skannata nopeasti tietueen tiedot ja palvelun ihmiset voivat vaatia lomaketta, joka tehostaa tietojen syöttöä. Voit määrittää erilaisia vaatimuksia määrittämällä lomakkeet käyttöoikeusrooleille, jotka kuuluvat eri käyttäjäryhmille.  
  
 Vaiheittaiset ohjeet [Määritä käyttöoikeusroolit lomakkeisiin](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form).  
  
 Kun sinulla on useampi kuin yksi pää- tai mobiili-lomake määritettynä entiteetille, voit valita mitä lomakkeita käyttäjät voivat käyttää perustuen näiden käyttöoikeusrooleihin. Koska kunkin entiteetin on voitava näyttää lomake kaikille käyttäjille, vähintään yksi lomake on nimettävä "varalomakkeeksi" – lomake näkyy käyttäjille, joiden käyttöoikeusrooleilla ei ole lomakkeita, jotka olisi määrätty nimenomaan heille.  
  
> [!NOTE]
>  Pikalomakkeita ja pikaluontilomakkeita ei voida määrittää käyttöoikeusrooleille.  
  
 Voit määrittää lomake-editorissa tai lomaketaulukossa lomakkeen käyttöoikeusroolit. Jos entiteetillä on vain yksi lomake, et voi poistaa **Käytössä varalomakkeena** -vaihtoehtoa **Määritä käyttöoikeusroolit** -valintaikkunassa. Tällöin vaikka olisit määrittänyt lomakkeelle käyttöoikeusrooleja, kuka tahansa käyttäjä, jolla on jokin muu käyttöoikeusrooli, pystyy siitä huolimatta tarkastelemaan lomaketta, koska se on otettu käyttöön varalomakkeena.  
  
 Kun olet luonut entiteetille toisenkin pää- tai mobiililomakkeen, voit poistaa **Käytössä varalomakkeena** -asetuksen toisesta lomakkeesta. Järjestelmä varmistaa aina, että varalomakkeeksi on määritetty vähintään yksi lomake.  
  
 Kun sinulla on useampi kuin yksi päälomake, voit määrittää lomaketilauksen, joka ohjaa, mikä lomakkeista, joita henkilö voi tarkastella, on se, joka tulee näkyviin oletusarvon mukaan. Jos he voivat käyttää useita lomakkeita, he voivat muuttaa lomakkeita ja se lomake, jonka he valitsevat, on oletuslomake, kunnes he valitsevat uuden lomakkeen. Tämä asetus tallennetaan selaimeen. Jos he käyttävät eri tietokonetta tai selainta, he näkevät alkuperäisen oletusarvon mukaisen lomakkeen.  
  
## <a name="strategies-to-manage-the-fallback-form"></a>Varalomakkeen hallintastrategioita  
 Varalomakkeen hallintastrategiat ovat seuraavat:  
  
<a name="BKMK_DoNotUseMultipleForms"></a>   
### <a name="all-users-view-the-same-form"></a>Kaikki käyttäjät näkevät saman lomakkeen.  
 Jos entiteetissä ei tarvita useita lomakkeita, et tarvitse varalomaketta.  
  
<a name="BKMK_Contingecyform"></a>   
### <a name="create-a-contingency-form"></a>Luo varalomake  
 Jos käytät roolipohjaisia lomakkeita, koska haluat rajoittaa tietoja, joita ihmiset voivat tarkastella tai muokata, harkitse lomakkeen luomista, jossa näytetään minimitiedot. Valitse seuraavaksi **Määritä käyttöoikeusroolit** -valintaikkunassa **Näytä vain näille valitut käyttöoikeusroolit**, mutta älä valitse mitään roolia, paitsi järjestelmänvalvoja, ja valitse **Käytössä varalomakkeena**. Tuloksena on, että tätä lomaketta ei koskaan voi nähdä kukaan paitsi järjestelmänvalvoja eikä kukaan, jonka käyttöoikeusrooleja ei ole liitetty tiettyyn lomakkeeseen. HTML-WWW-resurssin voi sisällyttää lomakkeeseen tietojen kera, miksi vähän tietoa on näkyvissä lomakkeessa ja linkin lisätietoihin, kuinka pyydetään lisätietoja käyttöoikeusroolin lisäämisestä, joka on liitetty lomakkeeseen tai kuinka sisällytetään uusi käyttöoikeusrooli lomakkeeseen.  
  
> [!NOTE]
>  WWW-resurssia ei voi sisällyttää lomakkeen ylä- tai alatunnisteeseen.  
  
<a name="BKMK_CreateGenericForm"></a>   
## <a name="create-a-generic-form"></a>Luo uusi yleislomake  
 Roolipohjaisten lomakkeiden avulla voit tarjota mukautetun käyttökokemuksen perustuen käyttäjän rooliin, voit määrittää viimeisimmän erikoistuneen lomakkeen varalomakkeeksi ja määrittää sen näkymään kaikille. Sitten luo tietyille käyttöoikeusrooleille mukautettuja lomakkeita ka määritä ne näyttämään vain käyttöoikeusrooleja, jotka tarvitsevat niitä. Älä ota näitä lomakkeita varalomakkeeksi. Lopuksi **Lomakkeet** -luettelossa käytä **Lomaketilaus** -valintaikkunaa määrittääksesi mitä lomakkeita näytetään luokiteltuina kaikkein vaativimmasta vähiten vaativaan. Varalla oleva lomake on luettelon alaosassa. Tämä strategia aiheuttaa sen, että ihmiset näkevät lomakkeen, joka on mukautettu heidän rooliensa oletuslomakkeeksi, he voivat edelleen käyttää lomakkeen valitsinta valitakseen yleisimmän lomakkeen, jos he haluavat. Minkä tahansa lomakkeen he valitsevatkaan, se säilyy heidän oletuslomakkeenaan, kunnes he valitsevat eri lomakkeen.  
  
<a name="BKMK_UseFormScripting"></a>   
## <a name="use-form-scripting"></a>Käytä lomakkeen komentosarjaa  

 Lopuksi verkkosovelluksessa on mahdollista, mutta ei suositeltavaa, että kehittäjä käyttää komentosarjoja lomakkeen Onload-tapahtumassa käyttääkseen [Xrm.Page.ui.formSelector.items -kokoelmaa](http://go.microsoft.com/fwlink/p/?LinkID=513300) kyselläkseen käytettäviä lomakkeita ja käyttää navigointimenetelmää ohjatakseen käyttäjät tiettyyn lomakkeeseen. Muista, että [navigointimenetelmä](http://go.microsoft.com/fwlink/p/?LinkID=513301) aiheuttaa sen, että lomake ladataan uudelleen (ja Onload-tapahtuma toteutuu uudelleen). Tapahtumakäsittelijän oman logiikan tulee aina tarkistaa jokin ehto ennen kuin navigointimenetelmää käytetään, jotta vältetään päättymätön silmukka tai tarpeettomasti rajoitetaan käyttäjien asetuksia navigoida lomakkeiden välillä.  
  
 Tämä lähestymistapa ei toimi Dynamics 365 for tablets -sovelluksessa, koska useita lomakkeita ei ole valittavissa.  

### <a name="next-steps"></a>Seuraavat vaiheet  

[Käyttöoikeusroolien liittäminen lomakkeisiin](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)
