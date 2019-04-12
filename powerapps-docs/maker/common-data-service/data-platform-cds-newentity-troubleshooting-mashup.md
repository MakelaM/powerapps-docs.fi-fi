---
title: Power Queryn vianmääritys | Microsoft Docs
description: Ongelmien ratkaiseminen luomalla Common Data Servicessä mukautettu entiteetti Power Queryn avulla.
author: mllopis
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: conceptual
ms.date: 05/16/2018
ms.author: millopis
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="troubleshoot-power-query"></a>Power Query -vianmääritys
Kun luot ulkoisten lähteiden tietoja mukautetun entiteetin Power Query for Excel -sovelluksella, tämä virhe voi tapahtua:

>”Azure Active Directory -järjestelmänvalvoja on määrittänyt käytännön, joka estää tämän toiminnon käyttämisen. Ota yhteyttä järjestelmänvalvojaan, joka voi myöntää tämän toiminnon käyttöoikeudet puolestasi."

Tämä virhe tapahtuu, jos Power Query ei voi käyttää organisaation tietoja PowerAppsissa tai Common Data Servicessä. Tämä tapahtuu seuraavissa kahdessa tilanteessa:

* Azure Active Directory (Azure AD) -vuokraajan järjestelmänvalvoja on poistanut käytöstä käyttäjän mahdollisuuden antaa suostumus sovelluksille, jotka käyttävät yrityksen tietoja heidän puolestaan.
* Hallitsemattoman Active Directory -vuokraajan käyttäminen. Hallitsematon vuokraaja on hakemisto, jolla ei ole yleistä järjestelmänvalvojaa. Se on luotu itsepalvelun rekisteröitymistarjouksen viimeistelemiseksi. Jos käyttäjä haluaa korjata tämän skenaarion, hänen on ensin muunnettava hallittu vuokraaja ja seurattava toista ongelmaan määritettyä ratkaisua. Ratkaisut on kuvattu seuraavassa osassa.

Azure Active Directory -järjestelmänvalvojan on seurattava jompaakumpaa tämän artikkelin proseduuria ongelman ratkaisemiseksi.

## <a name="allow-users-to-consent-to-apps-that-access-company-data"></a>Käyttäjillä on mahdollisuus antaa suostumus yrityksen tietoja käyttäville sovelluksille
Tämä tapa on ehkä helpompi kuin seuraava, mutta se antaa laajemmat oikeudet.

1. Avaa [Azure-portaalissa](https://portal.azure.com) **Azure Active Directory** -ruutu ja valitse **Käyttäjän asetukset**.
2. Valitse **Käyttäjät voivat antaa sovelluksille suostumuksen käyttää yrityksen tietoja heidän puolestaan** -kohdan vieressä **Kyllä** ja valitse sitten **Tallenna**.

## <a name="allow-power-query-to-access-company-data"></a>Yrityksen tietojen käyttöoikeuksien antaminen Power Querylle
Vaihtoehtoisesti vuokraajan järjestelmänvalvoja voi antaa suostumuksen Power Querylle ilman koko vuokraajaa koskevien oikeuksien muokkaamista.

1. Asenna [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-azurerm-ps).
2. Suorita PowerShell-komennot:
   * Kirjautuminen sisään AzureRmAccount (ja kirjautuminen sisään vuokraajan järjestelmänvalvojana)
   * Uusi-AzureRmADServicePrincipal -ApplicationId f3b07414-6bf4-46e6-b63f-56941f3f4128

Tämä tavan etu (koko vuokraajaa koskevaan ratkaisuun verrattuna) on se, että ratkaisu on hyvin kohdistettu. Se valmistelee vain **Power Query** -palvelun päänimen, mutta ei muita vuokraajaan tehtyjä oikeuteen liittyviä muutoksia.

## <a name="update-personal-data"></a>Henkilökohtaisten tietojen päivittäminen

Käyttäjät voivat päivittää koostesovelluksia ja muita tietoja (kuten kyselyjen nimiä ja koostesovelluksen metatietoja) kyselyeditorissa ja **Asetukset**-valintaikkunassa, jota voi käyttää kyselyeditorissa.

Voit käyttää kyselyeditoria PowerAppsissa seuraavasti:
1. Siirry **Tiedot**-ruutuun, laajenna se ja valitse **Entiteetit**. 
2. Valitse kolme pistettä (...) ja valitse sitten **Muokkaa kyselyjä**.
3. Valitse valintanauhan **Asetukset**-painike ja valitse sitten **Vie diagnostiikka** -painike.


## <a name="delete-personal-data"></a>Henkilökohtaisten tietojen poistaminen

Useimmat tiedot poistetaan automaattisesti 30 päivän kuluessa. Käyttäjien on poistettava kaikki koostesovellusten tiedot ja metatiedot PowerAppsin avulla. Kaikki liitetyt tiedot ja metatiedot poistetaan 30 päivän aikana.

Voit poistaa koostesovellukset PowerAppsista seuraavasti:
1. Poista tietojen integrointiohjelman projektit, jotka voidaan poistaa samannimisestä välilehdestä.
2. Valitse kolme pistettä (...), ja valitse sitten **Poista**-asetus.

Jos olet luonut koostesovelluksen Uudet entiteetit tiedoista (tekninen esikatselu) -toiminnon avulla, voit poistaa sen seuraavasti:
1. Valitse kolme pistettä (...) ja valitse sitten **Muokkaa kyselyjä**.
2. Valitse valintanauhan **Asetukset**-painike.
3. Valitse **Poista kaikki kyselyt** -painike.  
    Kun olet vahvistanut kyselyjen poistamisen, ne poistetaan.

## <a name="export-personal-data"></a>Henkilökohtaisten tietojen vieminen

Käyttäjät voivat viedä henkilökohtaisia tietoja seuraavasti:
1. Avaa kyselyeditori.
2. Valitse valintanauhan **Asetukset**-painike.
3. Valitse **Vie diagnostiikka** -painike.

Voit käyttää kyselyeditoria PowerAppsissa seuraavasti:
1. Siirry **Tiedot**-ruutuun, laajenna se ja valitse **Entiteetit**.
2. Valitse kolme pistettä (...) ja valitse sitten **Muokkaa kyselyjä**. 
3. Valitse valintanauhan **Asetukset**-painike ja valitse sitten **Vie diagnostiikka** -painike.

Käyttöliittymän järjestelmän luomia käyttäjän toimintojen lokeja voi käyttää Azure-portaalissa.



