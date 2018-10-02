---
title: Vaihtoehtoisten avainten määrittäminen PowerApps-portaalin avulla | MicrosoftDocs
description: Tietoja vaihtoehtoisten avainten määrittämisestä PowerApps-portaalin avulla
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
# <a name="define-alternate-keys-using-powerapps-portal"></a>Vaihtoehtoisten avainten määrittäminen PowerApps-portaalin avulla

[PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) on helppo tarkastella ja luoda entiteetin vaihtoehtoisia avaimia Common Data Service sovelluksille -ratkaisun avulla.

Portaalin avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. <br />Lisätietoja: 
- [Tietueisiin viittaavien vaihtoehtoisten avainten määrittäminen](define-alternate-keys-reference-records.md)
- [Vaihtoehtoisten avainten määrittäminen ratkaisunhallinnan avulla](define-alternate-keys-solution-explorer.md)

## <a name="view-alternate-keys"></a>Vaihtoehtoisten avainten tarkasteleminen

1. Valitse [PowerApps-portaalissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) joko **Mallipohjainen**- tai **Kaavio**-suunnittelutila.
2. Valitse **Tiedot** > **Entiteetit** ja valitse sitten entiteetti, jota haluat tarkastella.
3. Valitse **Avaimet**, kun haluat tarkastella määritettyjen vaihtoehtoisten avainten luetteloa.

    ![Vaihtoehtoisten avainten tarkasteleminen](media/view-alternate-keys-portal.png)

## <a name="create-an-alternate-key"></a>Vaihtoehtoisen avaimen luominen

1. Valitse [vaihtoehtoisten avainten tarkastelemisen](#view-alternate-keys) yhteydessä **Lisää avain**.
2. Määritä **näyttönimi** paneelissa ja valitse vaihtoehtoisen avaimen luomisessa käytettävät kentät.

    **Nimi** kenttä täytetään valikkonimen perusteella.

    ![Esimerkki vaihtoehtoisen avaimen määrityksestä](media/alternate-key-account-number-sic-code.png)

1. Sulje paneeli valitsemalla **Valmis**.
2. Luo vaihtoehtoinen avain valitsemalla **Tallenna entiteetti**.

> [!NOTE]
> Vaihtoehtoinen avain ei ole heti käytettävissä. Järjestelmätyö käynnistetään, kun tallennat entiteetin vaihtoehtoista avainta tukevien tietokantaindeksien luomista varten.

## <a name="delete-an-alternate-key"></a>Vaihtoehtoisen avaimen poistaminen

Valitse [vaihtoehtoisten avainten tarkastelemisen](#view-alternate-keys) yhteydessä poistettava avain ja valitse sitten komentopalkista **Delete-näppäin**.

### <a name="see-also"></a>Katso myös

[Tietueisiin viittaavien vaihtoehtoisten avainten määrittäminen](define-alternate-keys-reference-records.md)<br />
[Vaihtoehtoisten avainten määrittäminen ratkaisunhallinnan avulla](define-alternate-keys-solution-explorer.md)<br />
[Sovelluskehittäjän dokumentaatio: Entiteetin vaihtoehtoisten avainten määrittäminen](/dynamics365/customer-engagement/developer/define-alternate-keys-entity)
