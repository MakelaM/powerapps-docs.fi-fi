---
title: Vaihtoehtoisten avainten määrittäminen ratkaisunhallinnan avulla | MicrosoftDocs
description: Tietoja tietueisiin viittaavien vaihtoehtoisten avainten määrittämisestä Common Data Service sovelluksille -ratkaisussa ratkaisunhallinnan avulla
ms.custom: ''
ms.date: 05/31/2018
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
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="define-alternate-keys-using-solution-explorer"></a>Vaihtoehtoisten avainten määrittäminen ratkaisunhallinnan avulla

Ratkaisunhallinta on eräs tapa tarkastella ja luoda vaihtoehtoisia avaimia Common Data Service sovelluksille -ratkaisuun

[PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. <br />Lisätietoja: 
- [Tietueisiin viittaavien vaihtoehtoisten avainten määrittäminen](define-alternate-keys-reference-records.md)<br />
- [Vaihtoehtoisten avainten määrittäminen PowerApps-portaalin avulla](define-alternate-keys-portal.md)

## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luomasi vaihtoehtoisen avaimen nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle entiteetille. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-alternate-keys"></a>Vaihtoehtoisten avainten tarkasteleminen

1. Kun ratkaisunhallinta on auki, laajenna **Osat**-kohdassa **Entiteetit** ja valitse entiteetti, jonka vaihtoehtoisia avaimia haluat tarkastella.
2. Laajenna entiteetti ja valitse **Avaimet**.

    ![Vaihtoehtoisten avainten tarkasteleminen](media/view-alternate-keys-solution-explorer.png)

## <a name="create-an-alternate-key"></a>Vaihtoehtoisen avaimen luominen

1. Valitse [vaihtoehtoisten avainten tarkastelemisen](#view-alternate-keys) yhteydessä **Uusi**.
1. Kirjoita lomakkeeseen **näyttönimi**. **Nimi**-kentän arvo täytetään automaattisesti **näyttönimen** perusteella. 
2. Valitse **Käytettävissä olevat määritteet** -luettelossa määrite ja valitse sitten **Lisää >**, jolloin määrite siirretään **Valitut määritteet** -luetteloon.
    ![Vaihtoehtoisen avaimen luominen](media/create-alternate-key-solution-explorer.png)
1. Sulje lomake valitsemalla **OK**.

### <a name="optional-view-the-system-job-tracking-creation-of-indexes"></a>(Valinnainen) Järjestelmätyön seurannan indeksien luonnin tarkasteleminen
1. Kun olet luonut uuden vaihtoehtoisen avaimen ja [tarkastelet niitä](#view-alternate-keys), näyttöön tulee rivi, joka sisältää luodun avaimen.
2. **Järjestelmätyö**-sarakkeessa on linkki järjestelmätyöhön, joka seuraa vaihtoehtoista avainta tukevien indeksien luomista. 
    
    Järjestelmätyöllä on nimi, jonka muoto on seuraava: `Create index for {0} for entity {1}`, jossa `0` on vaihtoehtoisen avaimen **näyttönimi** ja `1` entiteetin nimi.

    Järjestelmätyön linkkiä ei näy sen jälkeen, kun järjestelmätyö on suoritettu onnistuneesti. Lisätietoja: [Järjestelmätöiden seuraaminen ja hallinta](/dynamics365/customer-engagement/admin/monitor-manage-system-jobs)


## <a name="delete-an-alternate-key"></a>Vaihtoehtoisen avaimen poistaminen

Valitse [vaihtoehtoisten avainten tarkastelemisen](#view-alternate-keys) yhteydessä ![Poista](media/delete.gif).

### <a name="see-also"></a>Katso myös

[Tietueisiin viittaavien vaihtoehtoisten avainten määrittäminen](define-alternate-keys-reference-records.md)<br />
[Vaihtoehtoisten avainten määrittäminen PowerApps-portaalin avulla](define-alternate-keys-portal.md)<br />
[Sovelluskehittäjän dokumentaatio: Entiteetin vaihtoehtoisten avainten määrittäminen](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)
