---
title: Mallipohjaisen sovelluksen lomake-editorin käytön hallinta PowerAppsissa | MicrosoftDocs
description: Ohjeet päälomakkeiden käytön hallintaan
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
tags: ''
ms.openlocfilehash: a895bd9ea0257585f942840924a7044a4dcc23fb
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675032"
---
# <a name="control-access-to-model-driven-app-forms"></a>Mallipohjaisen sovelluksen lomakkeiden käytön hallinta

 Voit hallita päälomakkeiden käyttöä kahdella tavalla:  
  
- **Tee päälomakkeesta passiivinen**  
  
     Voit määrittää päälomakkeiden tilan aktiiviseksi tai passiiviseksi. Tämä ominaisuus lisättiin ensisijaisesti uusien lomakkeiden hallintaa varten Dynamics 365 Customer Engagement -organisaatioiden päivitysten yhteydessä, mutta sen avulla voidaan estää käyttäjiä käyttämästä mitään päälomaketta.   
  
- **Liitä käyttöoikeusrooleja päälomakkeeseen**  
  
     Tämän avulla voit tehdä päälomakkeen käytettäväksi tietyissä ryhmissä.  
  
 Eri henkilöt organisaatiossasi voivat käsitellä samoja tietoja eri tavoin. Esimiesten on saatettava pystyä tarkistamaan nopeasti tietueen tiedot, ja palveluhenkilöstö voi edellyttää lomaketta, joka helpottaa tietojen syöttämistä. Voit vastata erilaisiin vaatimuksiin määrittämällä lomakkeita käyttöoikeusrooleille, joihin eri käyttäjäryhmät kuuluvat.  
  
 Vaiheittaiset ohjeet ovat kohdassa [Käyttöoikeusroolien määrittäminen lomakkeille](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form).  
  
 Kun entiteetille on määritetty useampi kuin yksi pää- tai mobiililomake, voit valita, mitä lomakkeita käyttäjät voivat käyttää käyttöoikeusrooliensa perusteella. Koska kunkin entiteetin on voitava näyttää lomake kaikille käyttäjille, vähintään yksi lomake on nimettävä varalomakkeeksi – lomake näkyy käyttäjille, joiden käyttöoikeusrooleilla ei ole nimenomaan niille määritettyjä lomakkeita.  
  
> [!NOTE]
>  Pikaluontia ja pikalomakkeita ei voi määrittää käyttöoikeusrooleille.  
  
 Voit määrittää lomakkeelle käyttöoikeusrooleja lomake-editorissa tai lomakeruudukossa. Kuitenkin jos entiteetillä on vain yksi lomake, et voi poistaa **Käytössä varalomakkeena** -vaihtoehtoa **Määritä käyttöoikeusroolit** -valintaikkunassa. Tällöin vaikka olisit määrittänyt lomakkeelle käyttöoikeusrooleja, kuka tahansa käyttäjä, jolla on jokin muu käyttöoikeusrooli, pystyy siitä huolimatta tarkastelemaan lomaketta, koska se on otettu käyttöön varalomakkeena.  
  
 Kun olet luonut entiteetille toisenkin pää- tai mobiililomakkeen, voit poistaa **Käytössä varalomakkeena** -asetuksen toisesta lomakkeesta. Järjestelmä varmistaa aina, että varalomakkeeksi on määritetty vähintään yksi lomake.  
  
 Kun sinulla on useampi kuin yksi päälomake, voit määrittää lomakejärjestyksen, joka ohjaa, mikä lomakkeista, jotka henkilö voi nähdä, näkyy oletusarvoisesti. Jos he voivat käyttää useita lomakkeita, he voivat muuttaa lomakkeita, ja heidän valitsemansa lomake on oletuslomake uuden lomakkeen valintaan asti. Tämä asetus tallennetaan selaimeen. Jos he käyttävät eri tietokonetta tai selainta, he näkevät alkuperäisen oletuslomakkeen.  
  
## <a name="strategies-to-manage-the-fallback-form"></a>Varalomakkeen hallintastrategiat  
 Varalomakkeen hallintastrategioita ovat seuraavat:  
  
<a name="BKMK_DoNotUseMultipleForms"></a>   
### <a name="all-users-view-the-same-form"></a>Kaikki käyttäjät näkevät saman lomakkeen  
 Jos entiteetissä ei tarvita useita lomakkeita, et tarvitse varalomaketta.  
  
<a name="BKMK_Contingecyform"></a>   
### <a name="create-a-contingency-form"></a>Varalomakkeen luominen  
 Jos käytät roolipohjaisia lomakkeita, koska haluat rajoittaa tietoja, joita ihmiset voivat tarkastella tai muokata, harkitse sellaisen lomakkeen luomista, jossa näkyy mahdollisimman vähän tietoja. Valitse seuraavaksi **Määritä käyttöoikeusroolit** -valintaikkunassa **Näytä vain näille valituille käyttöoikeusrooleille**, mutta älä valitse mitään roolia järjestelmänvalvojaa lukuun ottamatta, ja valitse **Käytössä varalomakkeena**. Tällöin tätä lomaketta ei koskaan voi nähdä kukaan paitsi järjestelmänvalvoja eikä kukaan, jonka käyttöoikeusrooleja ei ole liitetty tiettyyn lomakkeeseen. Voit lisätä lomakkeeseen HTML-verkkoresurssin ja selityksen siihen, miksi lomakkeessa näkyy vain vähän tietoja, ja linkin tietoihin siitä, miten pyydetään lisäämistä lomakkeeseen liittyvään käyttöoikeusrooliin tai uuden käyttöoikeusroolin liittämistä lomakkeeseen.  
  
> [!NOTE]
>  Verkkoresurssia ei voi lisätä lomakkeen ylä- tai alatunnisteeseen.  
  
<a name="BKMK_CreateGenericForm"></a>   
## <a name="create-a-generic-form"></a>Yleislomakkeen luominen  
 Jos käytät roolipohjaisia lomakkeita tarjotaksesi mukautetun käyttökokemuksen käyttäjän rooliin perusteella, voit määrittää yleisimmän lomakkeen varalomakkeeksi ja määrittää sen näkymään kaikille. Luo sitten mukautettuja lomakkeita tietyille käyttöoikeusrooleille ja määritä ne näkymään vain niitä edellyttäville käyttöoikeusrooleille. Älä käytä näitä lomakkeita varalomakkeina. Määritä näytettävät lomakkeet **Lomakkeet**-luettelon **Lomakkeiden järjestys** -valintaikkunassa yksinomaisimmasta vähiten yksinomaiseen. Varalomake on alimpana luettelossa. Tällöin ihmiset näkevät oletuslomakkeena lomakkeen, joka on mukautettu heidän rooliinsa, mutta he voivat edelleen halutessaan valita yleisimmän lomakkeen lomakkeen valitsimella. Heidän valitsemansa lomake on heidän oletuslomakkeensa siihen asti, kunnes he valitsevat eri lomakkeen.  
  
<a name="BKMK_UseFormScripting"></a>   
## <a name="use-form-scripting"></a>Lomakkeen komentosarjan käyttäminen  

 Verkkosovelluksessa on mahdollista, mutta ei suositeltavaa, että kehittäjä käyttää komentosarjoja lomakkeen Onload-tapahtumassa [Xrm.Page.ui.formSelector.items-kokoelman](http://go.microsoft.com/fwlink/p/?LinkID=513300) käyttämiseksi, jotta käytettävissä olevista lomakkeista voidaan tehdä kyselyjä ja käyttäjiä voidaan ohjata tiettyyn lomakkeeseen navigointimenetelmän avulla. Muista, että [navigointimenetelmää](http://go.microsoft.com/fwlink/p/?LinkID=513301) käytettäessä lomake ladataan uudelleen (ja Onload-tapahtuma tapahtuu uudelleen). Tapahtumakäsittelyn logiikan on aina tarkistettava muutama ehto ennen navigointimenetelmän käyttämistä, jotta vältetään päättymätön silmukka tai lomakkeiden välillä siirtymisen vaihtoehtojen tarpeeton rajoittaminen.  
  
 Tämä lähestymistapa ei toimi Dynamics 365:n tablettisovelluksessa, koska useita lomakkeita ei voi valita.  

### <a name="next-steps"></a>Seuraavat vaiheet  

[Käyttöoikeusroolien määrittäminen lomakkeille](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)
