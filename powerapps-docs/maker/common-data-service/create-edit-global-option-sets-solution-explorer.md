---
title: Common Data Servicen yleisten asetusjoukkojen luominen ja muokkaaminen ratkaisunhallinnan avulla | MicrosoftDocs
ms.custom: ''
ms.date: 05/26/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-and-edit-global-option-sets-for-common-data-service-using-solution-explorer"></a>Common Data Servicen yleisten asetusjoukkojen luominen ja muokkaaminen ratkaisunhallinnan avulla

Ratkaisunhallinta on eräs tapa luoda Common Data Servicen yleisiä asetusjoukkoja ja muokata niitä.

[PowerApps-portaalin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) avulla voi määrittää yleisimmät asetukset, mutta jotkin asetukset on määritettävä ratkaisunhallinnan avulla. <br />Lisätietoja: 
- [Common Data Servicen yleisten asetusjoukkojen luominen ja muokkaaminen](create-edit-global-option-sets.md)
- [Asetusjoukon luominen](custom-picklists.md)

## <a name="open-solution-explorer"></a>Ratkaisunhallinnan avaaminen

Jokaisen luomasi yleisen asetusjoukon nimeen sisältyy mukautuksen etuliite. Tämä määritetään työn alla olevan ratkaisun ratkaisujulkaisijassa. Jos haluat käyttää mukautuksen etuliitettä, varmista, että käsittelyssä on hallitsematon ratkaisu, jonka mukautuksen etuliitteen haluat tälle yleiselle asetusjoukolle. Lisätietoja: [Ratkaisujulkaisijan etuliitteen muuttaminen](change-solution-publisher-prefix.md) 

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

## <a name="view-global-option-sets"></a>Yleisten asetusjoukkojen tarkasteleminen

Kun ratkaisunhallinta on avattu, valitse **Osat**-kohdassa **Asetusjoukot**.

![Yleisten asetusjoukkojen tarkasteleminen](media/view-global-option-sets-solution-explorer.png)

> [!NOTE]
> Jotkin järjestelmän yleiset asetusjoukot eivät ole mukautettavia. Päivitykset ja uudet versiot voivat muuttaa näitä asetuksia, joten niiden käyttöä ei suositella, ellet ole varma, että vaatimuksesi vastaavat Common Data Servicen tapaa käyttää näitä arvoja.

## <a name="create-a-global-option-set"></a>Yleisen asetusjoukon luominen

> [!NOTE]
> Sinun tarvitsee luoda yleinen asetusjoukko vasta sitten, kun käytät sitä mukautetussa kentässä. Kun luot uuden asetusjoukon kentän, voit luoda uuden yleisen asetusjoukon tai käyttää olemassa olevaa yleistä asetusjoukkoa. Katso [Asetusjoukkokentän asetukset](create-edit-field-solution-explorer.md#option-set-field-options)

Kun tarkastelet yleisiä asetusjoukkoja, valitse **Uusi** ja avaa lomake, jossa voit määrittää yleisen asetusjoukon.

![Yleisen asetusjoukon luominen](media/create-global-option-set-solution-explorer.png)

Kirjoita **näyttönimi**, joka näkyy järjestelmänvalvojan tai mukauttajan roolin omaaville käyttäjille. He valitsevat tämän yleisen asetusjoukon määrittäessään sitä käyttävät uudet kentät. Tämä nimi ei näy muille sovellusta käyttäville henkilöille.

**Nimi**-kentän arvo muodostetaan kirjoittamasi **näyttönimen** perusteella. Se sisältää ratkaisujulkaisijan mukautusetuliitteen ratkaisulle, jonka parissa työskentelet. Voit muuttaa luodun osan **Nimi**-kentän arvosta ennen tallentamista.

Kirjoita yleisen asetusjoukon **kuvaus**. 

> [!TIP]
> Kerro **kuvauksessa** tämän yleisen asetusjoukon merkitys. Tämä arvo ei näy sovelluksen käyttäjille. Se on tarkoitettu järjestelmänvalvojan tai mukauttajan roolin omaaville henkilöille. He saattavat haluta tietää, miksi tämä yleinen asetusjoukko on luotu.

### <a name="configure-options"></a>Asetusten määrittäminen

[!INCLUDE [cc_configure-option-set-options-solution-explorer](../../includes/cc_configure-option-set-options-solution-explorer.md)]

## <a name="edit-a-global-option-set"></a>Yleisen asetusjoukon muokkaaminen

Valitse yleisten asetusjoukkojen tarkastelemisen yhteydessä asetusjoukko, jota haluat muokata näyttöön avautuvassa paneelissa.

**Nimi**-kentän arvon ja **Arvo**-kentän numeron muuttamisen lisäksi voit tehdä seuraavia muutoksia yleisen asetusjoukon luomisen yhteydessä.

[!INCLUDE [cc_remove-option-warning](../../includes/cc_remove-option-warning.md)]

## <a name="delete-a-global-option-set"></a>Yleisen asetusjoukon poistaminen

Voit poistaa yleisen asetusjoukon valitsemalla luettelon tarkastelemisen yhteydessä ![Poista komento -komennon](media/delete.gif) komentopalkissa.

> [!IMPORTANT]
> Jos yleistä asetusjoukkoa on käytetty kentässä, et voi poistaa sitä ennen kentän poistamista.
  
### <a name="see-also"></a>Katso myös
 
[Common Data Servicen yleisten asetusjoukkojen luominen ja muokkaaminen](create-edit-global-option-sets.md)<br />
[Asetusjoukon luominen](custom-picklists.md)<br />
[Kenttien luominen ja muokkaaminen](create-edit-fields.md)<br />
[Sovelluskehittäjän dokumentaatio: Yleisten asetusjoukkojen mukauttaminen](/dynamics365/customer-engagement/developer/org-service/customize-global-option-sets)
