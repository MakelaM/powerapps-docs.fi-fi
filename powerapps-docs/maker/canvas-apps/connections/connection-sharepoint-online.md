---
title: SharePoint-yhteyden yleiskatsaus | Microsoft Docs
description: Katso SharePointin käytettävissä olevat funktiot, vastaukset ja esimerkit
author: sarafankit
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/12/2017
ms.author: ankitsar
ms.openlocfilehash: 8019068155c88465f0f4202807fe763f2e4787b6
ms.sourcegitcommit: 0e9af8cace2bdc04750f4c5a70a3c4af8e3d2292
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/22/2018
ms.locfileid: "39195515"
---
# <a name="connect-to-sharepoint-from-powerapps"></a>Yhdistä PowerAppsista SharePointiin
![SharePoint](./media/connection-sharepoint-online/sharepointicon.png)

Yhdistämällä SharePoint-sivustoon voit luoda sovelluksen automaattisesti luettelosta, rakentaa sovelluksen alusta alkaen tai päivittää olemassa olevan sovelluksen.

## <a name="known-issues"></a>Tunnetut ongelmat
Voit lisätä tietoa mukautetusta luettelosta mutta et kirjastosta. Kaikentyyppisiä sarakkeita ei tueta, ja kaikentyyppiset sarakkeet eivät tue kaikentyyppisiä kortteja.

| Saraketyyppi | Tuki | Oletuskortit |
| --- | --- | --- |
| Yksi tekstirivi |Kyllä |Näytä teksti |
| Useita tekstirivejä |Kyllä |Näytä teksti |
| Valinta |Kyllä |Näytä haku<br>Muokkaa hakua<br>Näytä monivalinta<br>Muokkaa monivalintaa |
| Luku |Kyllä |Näytä prosenttiosuus<br>Näytä luokitus<br>Näytä teksti |
| Valuutta |Kyllä |Näytä prosenttiosuus<br>Näytä luokitus<br>Näytä teksti |
| Päivämäärä ja aika |Kyllä |Näytä teksti |
| Haku |Kyllä |Näytä haku<br>Muokkaa hakua<br>Näytä monivalinta<br>Muokkaa monivalintaa |
| Totuusarvo (kyllä/ei) |Kyllä |Näytä teksti<br>Näkymän vaihto |
| Henkilö tai ryhmä |Kyllä |Näytä haku<br>Muokkaa hakua<br>Näytä monivalinta<br>Muokkaa monivalintaa |
| Hyperlinkki |Kyllä |Näytä URL-osoite<br>Näytä teksti |
| Kuva |Kyllä (vain luku) |Näytä kuva<br>Näytä teksti |
| Liite |Kyllä (vain luku) |Näytä liitteet|
| Laskettu |Kyllä (vain luku) | |
| Tehtävän tulos |Ei | |
| Ulkoiset tiedot |Ei | |
| Hallitut metatiedot |Kyllä (vain luku) | |
| Luokitus |Ei | |

PowerApps voi lukea sarakkeita, jotka sisältävät välilyöntejä, mutta välilyönnit korvataan heksadesimaalikoodilla **"\_x0020\_"**. Esimerkiksi **Sarakkeen nimi** SharePointissa näkyy muodossa **Sarakkeen_x0020_Nimi** PowerAppsissa, kun se näytetään tietoasettelussa tai sitä käytetään kaavassa.

## <a name="prerequisites"></a>Edellytykset
1. [Rekisteröidy](../../signup-for-powerapps.md) PowerAppsiin.

1. [Kirjaudu sisään](http://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) PowerAppsiin antamalla samat tunnistetiedot kuin rekisteröityessäsi.

1. Valitse lähellä vasenta reunaa **Sovellukset** ja sitten **Luo sovellus** palkissa.

## <a name="create-an-app"></a>Sovelluksen luominen
* [Luo sovellus automaattisesti](../app-from-sharepoint.md) SharePoint-luettelon tietojen perusteella.

    Sovelluksessa on oletuksena kolme näyttöä: yksi tietueiden selaamiseen, yksi tietueen tietojen näyttämiseen ja yksi tietueen luomiseen tai päivittämiseen. Kun sovellus on luotu, haluat todennäköisesti mukauttaa [selausnäyttöä](../customize-layout-sharepoint.md) ja [tieto- ja muokkausnäyttöjä](../customize-forms-sharepoint.md) omien tarpeidesi mukaan.

    **Huomautus:** Jos SharePoint-luettelosi sisältää **Valinta**-, **Haku**- tai **Henkilö tai ryhmä** -sarakkeen, katso kohta [Tietojen näyttäminen valikoimassa](connection-sharepoint-online.md#show-data-in-a-gallery) jäljempänä tässä aiheessa.

* Luo oma sovelluksesi alusta alkaen [yhdistämällä SharePointiin](../connect-to-sharepoint.md), tutustumalla käsitteisiin kohdassa [Sovelluksen luominen alusta alkaen](../get-started-create-from-blank.md) ja käyttämällä niitä SharePointissa Excelin sijaan.

## <a name="add-a-sharepoint-list-to-an-existing-app"></a>SharePoint-luettelon lisääminen olemassa olevaan sovellukseen
1. Avaa PowerApps Studiossa sovellus, jonka haluat päivittää.

2. Napsauta tai napauta valintanauhan **Näkymä**-välilehdessä kohtaa **Tietolähteet**

3. Napsauta tai napauta oikean ruudun kohtaa **Lisää tietolähde**.

    ![Tietolähteen lisääminen](./media/connection-sharepoint-online/add-data-source.png)

4. Napsauta tai napauta **Uusi yhteys**, **SharePoint** ja sitten **Yhdistä**.

    ![SharePoint-yhteyden lisääminen](./media/connection-sharepoint-online/add-sharepoint.png)

5. Määritä SharePoint-sivuston tyyppi, johon haluat yhdistää:

    ![Määritä yhteystyyppi](./media/connection-sharepoint-online/choose-type.png)

   * Napsauta tai napauta **Yhdistä suoraan (pilvipalvelut)** yhdistääksesi SharePoint Onlineen.

   * Napsauta tai napauta **Yhdistä käyttäen paikallista tietoyhdyskäytävää** yhdistääksesi paikalliseen SharePoint-sivustoon.

       Määritä **Windows** todennustyypiksi ja määritä sitten tunnistetietosi. (Jos tunnistetietoihisi kuuluu toimialuenimi, anna käyttäjänimi muodossa *toimialue\alias*.)

       ![Määritä tunnistetiedot](./media/connection-sharepoint-online/specify-creds.png)

       **Huomautus:** Jos sinulla ei ole asennettuna paikallista tietoyhdyskäytävää, [asenna se](../gateway-reference.md) ja päivitä yhdyskäytäväluettelo napsauttamalla tai napauttamalla päivityskuvaketta.

       Napsauta tai napauta **Valitse yhdyskäytävä** -kohdassa yhdyskäytävää, jota haluat käyttää.

       ![Valitse yhdyskäytävä](./media/connection-sharepoint-online/choose-gateway.png)

6. Napsauta tai napauta **Yhdistä**.

7. Napsauta tai napauta **Yhdistä SharePoint-sivustoon** -kohdassa **Viimeisimmät sivustot** -luettelon merkintää (tai kirjoita tai liitä haluamasi sivuston URL-osoite) ja napsauta tai napauta **Siirry**.

    ![Valitse SharePoint-sivusto](./media/connection-sharepoint-online/select-sp-site.png)

8. Valitse kohdassa **Valitse luettelo** yhden tai useamman haluamasi luettelon valintaruutu ja napsauta tai napauta **Yhdistä**:  

    ![Valitse taulukot SharePointissa](./media/connection-sharepoint-online/select-sp-tables.png)

    Kaikkia luettelotyyppejä ei näytetä oletuksena. Jos käytettävän luettelon nimeä ei näy, vieritä näkymä alas ja kirjoita luettelon nimi laatikkoon, jossa lukee **Anna mukautettu luettelon nimi**.

    ![Mukautettu luettelo SharePointissa](./media/connection-sharepoint-online/custom-list.png)

    Tietolähteet lisätään sovellukseesi.

    ![Luettelo sovellukseen lisätyistä tietolähteistä](./media/connection-sharepoint-online/data-sources-list.png)

## <a name="show-data-in-a-gallery"></a>Tietojen näyttäminen valikoimassa
Näytä tietoja tämäntyyppisistä sarakkeista valikoimassa käyttämällä kaavariviä yhden tai useamman **Otsikko**-ohjausobjektin **Teksti**-ominaisuuden asettamiseen kyseisessä valikoimassa:

* Jos käytät **Valinta**- tai **Haku**-saraketta, määritä **ThisItem.[ColumnName].Value** tietojen näyttämiseksi tässä sarakkeessa.

    Määritä esimerkiksi **ThisItem.Location.Value**, jos sinulla on **Valinta**-sarake, jonka nimi on **Location**, ja määritä **ThisItem.PostalCode.Value**, jos sinulla on **Haku**-sarake, jonka nimi on **PostalCode**.

* Jos käytät **Henkilö tai ryhmä** -saraketta, määritä **ThisItem.[ColumnName].DisplayName** käyttäjän tai ryhmän näyttönimen näyttämiseksi.

    Määritä esimerkiksi **ThisItem.Manager.DisplayName** näyttämään näyttönimet **Henkilö tai ryhmä** -sarakkeesta, jonka nimi on **Manager**.

    Voit myös näyttää erilaista tietoa käyttäjistä, kuten sähköpostiosoitteet tai työnimikkeet. Voit näyttää luettelon kaikista valinnoista määrittämällä **ThisItem.[ColumnName].** (piste lopussa).

    **Huomautus:** Jos käytät **CreatedBy**-saraketta, määritä **ThisItem.Author.DisplayName** näyttämään luettelossa kohteita luoneiden käyttäjien näyttönimet. Jos käytät **ModifiedBy**-saraketta, määritä **ThisItem.Editor.DisplayName** näyttämään luettelon kohteita muuttaneiden käyttäjien näyttönimet.

* Jos käytät **Managed Metadata** -saraketta, määritä **ThisItem.[ColumnName].Label** näyttämään tiedot kyseisessä sarakkeessa.

    Määritä esimerkiksi **ThisItem.Languages.Label**, jos sinulla on **Managed Metadata** -sarake, jonka nimi on **Languages**.

## <a name="next-steps"></a>Seuraavat vaiheet
* Opi [näyttämään tietolähteen tietoja](../add-gallery.md).
* Opi [tarkastelemaan tietoja ja luomaan tai päivittämään tietueita](../add-form.md).
* Tutustu muuntyyppisiin [tietolähteisiin](../connections-list.md), joihin voit muodostaa yhteyden.
