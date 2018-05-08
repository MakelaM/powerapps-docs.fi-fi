---
title: Ympäristöjen hallinta | Microsoft Docs
description: Hallitse ympäristöjä PowerAppsissa, mukaan lukien luominen, nimeäminen uudelleen, poistaminen ja suojaus
services: powerapps
suite: powerapps
documentationcenter: na
author: manasmams
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: c11c1d2122cf4306aede621e3c98a95a6ec9a967
ms.sourcegitcommit: 078ba325480147e6e4da61e319ed53219f1c5cfc
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/06/2018
---
# <a name="administer-environments-in-powerapps"></a>Ympäristöjen hallinta PowerAppsissa
[PowerApps-hallintakeskuksessa][1] voit hallita ympäristöjä, jotka olet luonut tai joissa olet ympäristön järjestelmänvalvojan ja järjestelmänvalvojan roolissa. Hallintakeskuksessa voit tehdä seuraavia toimintoja:

* ympäristöjen luominen
* ympäristöjen nimeäminen uudelleen
* ympäristön järjestelmänvalvojan tai ympäristön tekijän roolin lisääminen tai poistaminen käyttäjältä ja ryhmältä
* Common Data Service -tietokannan valmisteleminen ympäristölle
* tietojen menetyksen estämiskäytäntöjen määrittäminen
* tietokannan suojauskäytäntöjen määrittäminen (avoin tai tietokantarooleilla rajoitettu)
* Azure AD -vuokraajat, joilla on yleinen järjestelmänvalvoja -rooli (myös yleinen Office 365 -järjestelmänvalvojan rooli), voivat myös hallita kaikkia ympäristöjä, jotka on luotu heidän vuokraajakäytännöissään ja määritetyissä vuokraajan laajuisissa käytännöissä.

## <a name="access-the-powerapps-admin-center"></a>PowerApps-hallintakeskuksen käyttäminen
Pääset PowerApps-hallintakeskukseen näin:

* Siirry suoraan osoitteeseen [admin.powerapps.com][1] TAI

* Siirry osoitteeseen [powerapps.com][2] ja valitse siirtymisotsikossa oleva rataskuvake.

    ![](./media/environment-admin/powerapps-gear-dropdown.png)

Tarvitset jonkin seuraavista rooleista ympäristön hallitsemiseen PowerApps-hallintakeskuksessa:

* Ympäristön järjestelmänvalvojan tai järjestelmänvalvojan rooli kyseisessä ympäristössä TAI

* Azure AD- tai Office 365 -vuokraajan yleinen järjestelmänvalvoja -rooli.

Hallintakeskukseen pääsemiseen tarvitaan myös joko PowerAppsin palvelupaketti 2 tai Microsoft Flow -palvelupaketti 2. Lisätietoja saat [PowerAppsin hinnoittelusivulta][3].

> [!IMPORTANT]
> Kaikki PowerApps-hallintakeskuksessa tehdyt muutokset vaikuttavat [Microsoft Flow -hallintakeskukseen][4] ja päinvastoin.

## <a name="create-an-environment"></a>Ympäristön luominen
Ympäristön luomisen ohjeet ovat kohdassa [Pikaopas: ympäristön luominen](create-environment.md).

## <a name="view-your-environments"></a>Ympäristöjen tarkasteleminen
Kun avaat hallintakeskuksen, oletusarvoisesti näkyviin tulee Ympäristöt-välilehti. Välilehdessä on lueteltu kaikki ympäristöt, joiden ympäristön järjestelmänvalvoja olet (kuten alla):

![](./media/environment-admin/environment-list-new.png)

Jos sinulla on Azure AD- tai Office 365 -vuokraajan yleinen järjestelmänvalvoja -rooli, näet kaikkien vuokraajan käyttäjien luomat ympäristöt, koska olet automaattisesti niiden kaikkien ympäristön järjestelmänvalvoja.

## <a name="rename-your-environment"></a>Ympäristön nimeäminen uudelleen
1. Avaa [PowerApps-hallintakeskus][1] ja valitse luettelosta ympäristö, jonka nimen haluat muuttaa.

    ![](./media/environment-admin/environment-list-updated3.png)

2. Napsauta tai napauta **Tiedot**.

    ![](./media/environment-admin/environment-rename-details-2.png)
3. Kirjoita uusi nimi **Nimi**-tekstiruutuun ja valitse **Tallenna**.

    ![](./media/environment-admin/environment-rename-2.png)

    Jos loit tietokannan ympäristössä, et näe tätä vaihtoehtoa. Voit nimetä ympäristön uudelleen Dynamics 365 -hallintakeskuksessa napsauttamalla **Tiedot**-välilehdessä olevaa linkkiä.

    ![](./media/environment-admin/Delete-D365AdminCenter.png)


## <a name="delete-your-environment"></a>Ympäristön poistaminen
1. Valitse [PowerApps-hallintakeskuksessa][1] ympäristö, jonka haluat poistaa.

    ![](./media/environment-admin/environment-list-updated3.png)
2. Napsauta tai napauta **Tiedot**.

    ![](./media/environment-admin/environment-rename-details-2.png)
3. Poista ympäristösi napsauttamalla tai napauttamalla **Poista ympäristö**.

    ![](./media/environment-admin/delete-environment-2.png)


## <a name="create-a-common-data-service-database-for-an-environment"></a>Common Data Service -tietokannan luominen ympäristölle
Jos ympäristöllä ei ole vielä tietokantaa, ympäristön järjestelmänhaltija voi luoda sellaisen [PowerApps-hallintakeskuksessa][1] seuraavalla tavalla. Common Data Service -tietokannan voi luoda vain käyttäjä, jolla on PowerAppsin palvelupaketti 2 -käyttöoikeus.

1. Valitse ympäristö ympäristöt-taulukosta.

    ![](./media/environment-admin/choose-environment-updated.png)
2. Valitse **Tiedot**-välilehti.
3. Valitse **Luo tietokanta**.

    ![](./media/environment-admin/Create-DB-From-Details.png)


Kun olet luonut tietokannan, valitse suojausmalli. Lisätietoja on kohdassa [Tietokannan suojauksen määritys](database-security.md).

## <a name="manage-security-for-your-environments"></a>Ympäristöjen suojauksen hallitseminen

### <a name="environment-permissions"></a>Ympäristön käyttöoikeudet
Ympäristössä kaikki Azure AD -vuokraajan käyttäjät ovat kyseisen ympäristön käyttäjiä. Jos käyttäjän rooli edellyttää laajempia käyttöoikeuksia, hänelle täytyy lisätä tietty ympäristön rooli. Ympäristöillä on kaksi sisäänrakennettua roolia, joilla voi hallita ympäristön käyttöoikeuksia:

* **Ympäristön järjestelmänvalvoja** (tai **järjestelmänvalvoja**) voi suorittaa kaikki ympäristön hallintatoiminnot, mukaan lukien seuraavat:
    * ympäristön järjestelmänvalvojan tai ympäristön tekijän roolin lisääminen käyttäjälle tai sen poistaminen

    * Common Data Service -tietokannan valmisteleminen ympäristölle

    * kaikkien ympäristössä luotujen resurssien tarkasteleminen ja hallitseminen

    * tietojen menetyksen estämiskäytäntöjen määrittäminen. Lisätietoja on kohdassa [Tietojen menetyksen estämiskäytännöt](prevent-data-loss.md).

  > [!NOTE]
  > Jos ympäristöllä on tietokanta, sinun on määritettävä käyttäjiä **järjestelmänvalvojan** rooliin **ympäristön järjestelmänvalvojan** roolin sijaan.

* **Ympäristön tekijä** -rooli voi luoda ympäristössä resursseja Microsoft Flow’n avulla. Resursseja ovat esimerkiksi sovellukset, yhteydet, mukautetut liittimet, yhdyskäytävät ja työnkulut. Ympäristön tekijät voivat myös jakaa ympäristössä kehittämiään sovelluksia organisaation muille käyttäjille. He voivat jakaa sovelluksen yksittäiselle käyttäjälle, käyttöoikeusryhmälle tai organisaation kaikille käyttäjille. Lisätietoja on kohdassa [Sovelluksen jakaminen PowerAppsissa](../maker/canvas-apps/share-app.md).

Ympäristön järjestelmänvalvoja voi määrittää ympäristön roolin käyttäjälle tai käyttöoikeusryhmälle [PowerApps-hallintakeskuksessa][1] seuraavalla tavalla:

1. Valitse ympäristö ympäristöt-taulukosta.

    ![](./media/environment-admin/choose-environment-updated.png)
2. Valitse **Suojaus**-välilehti.
3. Jos tietokantaa ei ole luotu ympäristössä:

    a. Valitse joko **ympäristön järjestelmänvalvoja**- tai **ympäristön tekijä** -rooli.

    ![](./media/environment-admin/choose-environment-role.png)

    b. Määritä vähintään yhden käyttäjän tai käyttöoikeusryhmän nimi Azure Active Directoryssa tai määritä, että haluat lisätä koko organisaatiosi.

    ![](./media/environment-admin/enter-name.png)

    c. Päivitä määritykset ympäristön rooliin valitsemalla **Tallenna**.

4. Jos tietokantaa on luotu ympäristössä:

    a. Napsauta linkkiä, jotta voit hallita ympäristön rooleja Dynamics 365:ssä.

    ![](./media/environment-admin/Security-Link-D365.png)

    b. Valitse käyttäjä ympäristön/esiintymän käyttäjäluettelosta.

    ![](./media/environment-admin/D365-Select-User.png)

    c. Määritä rooli käyttäjälle.

    ![](./media/environment-admin/D365-Assign-Role.png)

    d. Päivitä määritykset ympäristön rooliin valitsemalla **OK**.


> [!NOTE]
> Ympäristön rooleihin määritetyt käyttäjät tai ryhmät eivät saa automaattisesti käyttöoikeutta ympäristön tietokantaan (jos sellainen on olemassa), vaan tietokannan omistajan täytyy antaa se erikseen. Lisätietoja on kohdassa [Tietokannan suojauksen määritys](database-security.md).  
>
>

### <a name="database-security"></a>Tietokannan suojaus
Tietokannan käyttäjärooleilla ja käyttöoikeusjoukoilla hallitaan, kuka pystyy luomaan ja muokkaamaan tietokantarakennetta. Ne hallitsevat myös, kuka voi muodostaa yhteyden ympäristössäsi valmisteltuun tietokantaan tallennettuihin tietoihin. Voit hallita oman ympäristösi tietokannan käyttäjärooleja ja käyttöoikeusjoukkoja **Suojaus**-välilehden **Käyttäjäroolit**- ja **Käyttöoikeusjoukot**-osissa. Lisätietoja on kohdassa [Tietokannan suojauksen määritys](database-security.md).

![](./media/environment-admin/D365-Assign-Role.png)

## <a name="data-policies"></a>Tietokäytännöt
Organisaation tiedot on suojattava niin, ettei niitä jaeta käyttäjäryhmille, joilla ei ole niihin käyttöoikeutta. Voit suojata tiedot luomalla ja valvomalla käytäntöjä, jotka määrittävät, minkä kuluttajapalvelujen ja liitinten kanssa tiettyjä yritystietoja voidaan jakaa. Tietojen jakamista määrittäviin käytäntöihin viitataan nimellä tietojen menetyksen estämiskäytännöt (DLP-käytännöt, data loss prevention). Voit hallita ympäristöjesi DLP-käytäntöjä [PowerAppsin hallintakeskuksen][1] kohdassa **Tietokäytännöt**.  Lisätietoja on kohdassa [Tietojen menetyksen estämiskäytännöt](prevent-data-loss.md).

![](./media/environment-admin/data-policies.png)

## <a name="frequently-asked-questions"></a>Usein kysytyt kysymykset
### <a name="how-many-environments-and-databases-can-i-create"></a>Kuinka monta ympäristöä ja tietokantaa voin luoda?
Voit luoda enintään kaksi kokeiluympäristöä ja kaksi tuotantoympäristöä niiden lisenssistä riippuen. Lisätietoja on [täällä](environments-overview.md#creating-an-environment). Jokainen käyttäjä voi valmistella tietokantoja kahdessa kokeiluympäristössä ja kahdessa tuotantoympäristössä niiden lisenssistä riippuen. 

### <a name="which-license-includes-common-data-service"></a>Mikä lisenssi sisältää Common Data Servicen?
PowerAppsin palvelupaketti 2.  Saat [PowerAppsin hinnoittelusivulta][3] lisätietoja kaikista palvelupaketeista, jotka sisältävät tämän käyttöoikeuden.

### <a name="while-trying-to-create-a-new-environment-i-am-getting-an-error-how-should-i-resolve-it"></a>Saan virhesanoman, kun yritän luoda uuden ympäristön. Miten voin ratkaista ongelman?
Virhesanoma ”palvelupakettisi ei tue valittua ympäristötyyppiä tai kyseisen ympäristötyypin enimmäisraja on saavutettu” voi tarkoittaa jompaakumpaa seuraavista:

1. Olet jo luonut kiintiösi salliman määrän tietyntyyppisiä ympäristöjä. Kuvitellaan, että olet luomassa kokeiluympäristöä ja saat tämän virhesanoman. Se tarkoittaa, että olet jo valmistellut kaksi kokeiluympäristöä. Voit tarkastella kaikkia ympäristöjä [PowerApps-hallintakeskuksessa][1].
Jos haluat, voit poistaa olemassa olevan samantyyppisen ympäristön ja luoda sen jälkeen uuden. Varmista kuitenkin, että et menetä tietoja, sovelluksia, työnkulkuja ja muita resursseja, jotka haluat säilyttää.

2. Kiintiösi ei riitä juuri tämäntyyppisen ympäristön luomiseen. Tarkista [täältä](environments-overview.md#creating-an-environment), minkä tyyppisen ympäristön voit luoda.

Jos saat muita virhesanomia tai sinulla on kysyttävää, ota meihin yhteyttä [täällä][5].

### <a name="while-trying-to-create-a-database-in-an-environment-i-am-getting-an-error-how-should-i-resolve-it"></a>Saan virhesanoman, kun yritän luoda tietokannan ympäristössä. Miten voin ratkaista ongelman?
Voit saada virhesanoman tietokannan luomisen yhteydessä seuraavissa skenaarioissa:

1. **Oletusympäristö**: vuokraajan oletusympäristö ei tällä hetkellä tue tietokannan luomista. 

2. **Henkilökohtaiseen käyttöön tarkoitettu ympäristö:** saat omaan käyttöön tarkoitetun ympäristön, kun rekisteröidyt PowerAppsin yhteisön palvelupaketissa. Jos et ole vielä luonut tietokantaa, et voi tällä hetkellä valmistella tietokantaa henkilökohtaiseen käyttöön tarkoitetussa ympäristössä. 

3. **Ympäristö on Azure Active Directory -vuokraajan kotialueesta poikkeavalla alueella**: tällä hetkellä voit valmistella tietokannan vain Azure Active Directory -vuokraajan kotialueella luoduissa ympäristöissä. Mahdollisuus valmistella tietokanta muilla alueilla on tulossa pian. Joten muista pitää alue vuokraajan oletussijainnin kanssa samana, jos haluat luoda tietokannan vuokraajan ympäristössä.

4. **Tietokantojen luomista ei tueta tietyillä alueilla**: On tiettyjä alueita, joilla tietokannan luominen ei ole käytettävissä. Esimerkiksi Etelä-Amerikan maat. Joten jos vuokraajan kotisijainti on Etelä-Amerikka, et voi tällä hetkellä valmistella tietokantaa missään ympäristössä. 
    
Pyrimme siihen, että tietokantoja voisi luoda kaikissa edellä mainituissa skenaarioissa.
Jos saat muita virhesanomia tai sinulla on kysyttävää, ota meihin yhteyttä [täällä][5].

### <a name="when-will-my-trial-environment-expire"></a>Milloin kokeiluversio vanhenee?   
Kokeiluversion ympäristö vanhenee 30 päivää sen luomisen jälkeen. Jos et halua ympäristösi vanhenevan, voit pian muuntaa sen tuotantoympäristöksi eri tavoin. Tämä toiminto on tulossa pian. Emme anna kokeiluympäristöjen vanhentua ennen sen julkaisua.

### <a name="does-my-current-database-created-with-previous-version-of-the-common-data-service-also-gets-counted-in-the-quota"></a>Lasketaanko nykyinen tietokantanikin (luotu Common Data Servicen aiemmalla versiolla) mukaan kiintiöön?
Myös aiemmat tietokantasi (luotu Common Data Servicen vanhemmalla versiolla) lasketaan mukaan tuotantoympäristöjen kiintiöön. Jos luot nyt tietokannan ympäristössä (luotu ennen 15. maaliskuuta 2018), sekin lasketaan tuotantoympäristöksi.

### <a name="can-i-rename-an-environment"></a>Voinko nimetä ympäristön uudelleen?
Kyllä, tämä toiminto on käytettävissä PowerApps-hallintakeskuksen kautta. Lisätietoja on kohdassa [Ympäristöjen hallitseminen](environments-administration.md#rename-your-environment).

### <a name="can-i-delete-an-environment"></a>Voinko poistaa ympäristön?
Kyllä, tämä toiminto on käytettävissä PowerApps-hallintakeskuksen kautta. Lisätietoja on kohdassa [Ympäristöjen hallitseminen](environments-administration.md#delete-your-environment).
Huomaa, että tällä hetkellä ei voi poistaa tietokannan sisältävää ympäristöä (Common Data Servicen uusimmassa versiossa). Tämä toiminto on tulossa pian!

### <a name="as-an-environment-admin-can-i-view-and-manage-all-resources-apps-flows-apis-etc-for-an-environment"></a>Olen ympäristön järjestelmänvalvoja – voinko tarkastella ja hallita kaikkia ympäristön resursseja (sovellukset, työnkulut, ohjelmointirajapinnat jne.)?
Kyllä, mahdollisuus tarkastella ympäristön sovelluksia ja työnkulkuja on käytettävissä PowerApps-hallintakeskuksen kautta. Lisätietoja saat kohdasta [Näytä sovellukset](admin-view-apps.md).



<!--Reference links in article-->
[1]: https://admin.powerapps.com
[2]: https://web.powerapps.com
[3]: https://powerapps.microsoft.com/pricing/
[4]: https://admin.flow.microsoft.com
[5]: https://go.microsoft.com/fwlink/?linkid=871628