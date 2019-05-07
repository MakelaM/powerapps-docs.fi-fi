---
title: Ratkaisujen käyttö PowerAppsissa | MicrosoftDocs
description: Lue, miten ratkaisuja jaetaan
ms.custom: ''
ms.date: 01/28/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- powerapps
author: Mattp123
ms.assetid: ece68f5f-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
search.audienceType:
- maker
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: da6b44c4755fa42d6e946cfe5955bba0e78b91c2
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "65038601"
---
# <a name="solutions-overview"></a>Ratkaisujen yleiskuvaus  

  PowerAppsissa ratkaisuja käytetään siirtämään sovelluksia ja komponentteja ympäristöstä toiseen tai käyttämään mukautussarjoja aiemmin luoduissa sovelluksissa. Ratkaisuun sisältyy vähintään yksi sovellus ja muita osia, kuten entiteettejä ja asetusjoukkoja.  Voit hankkia ratkaisun [AppSourcesta](https://appsource.microsoft.com/) tai riippumattomalta ohjelmistotoimittajalta.
  
Lisätietoja: [Tekninen raportti: Ratkaisun elinkaaren hallinta](https://www.microsoft.com/en-us/download/details.aspx?id=57777)  
  
> [!NOTE]
>  Jos olet itsenäinen ohjelmistokehittäjä ja olet luomassa jaeltavaa sovellusta, sinun on käytettävä ratkaisuja. Jos haluat lisätietoja ratkaisuista, katso [Kehittäjän opas: Ratkaisuihin tutustuminen](/powerapps/developer/common-data-service/introduction-solutions)  
  
 Seuraavassa on lisätietoja ratkaisuista, jos olet kiinnostunut luomaan PowerApps-sovelluksia organisaatiota varten tai muokkaamaan Dynamics 365 for Customer Engagement -sovelluksia:  
  
-   Ratkaisujen luominen on valinnaista. Voit luoda tai mukauttaa sovelluksia suoraan PowerApps-ympäristössäsi luomatta ratkaisuja.  
  
-   Kun mukautat PowerApps-ympäristöä suoraan ratkaisua luomatta, käsittelet erityisratkaisua, jonka nimi on **Common Data Services -oletusratkaisu**. Tämä ratkaisu sisältää kaikki PowerApps-ympäristössä tekemäsi mukautukset.  
  
-   Käytössä on myös toinen erityisratkaisu, **Oletusratkaisu**. Tämä ratkaisu sisältää järjestelmän kaikki osat riippumatta siitä, kuka ne on luonut. Voit viedä **oletusratkaisun** ja luoda varmuuskopion organisaatiossa määritetyistä mukautuksista. Muutosten varmuuskopiointi varmuuden vuoksi on hyvä käytäntö.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="components"></a>Osat  
 Osa viittaa mukautettavaan osaan. Kaikki kohteet, joita ratkaisuun voidaan sisällyttää, ovat ratkaisun osia. Seuraavassa on luettelo osista, joita voit tarkastella ratkaisussa:  
  
-   Sovelluksen valintanauha  
  
-   Artikkelimalli  
  
-   Liiketoimintasääntö  

-   Kaaviosovellus 
  
-   Kaavio  
  
-   Yhteysrooli  
  
-   Sopimusmalli  
 
-   Mukautettu ohjausobjekti
  
-   Koontinäyttö  
  
-   Sähköpostimalli  
  
-   Entiteetti  
  
-   Entiteettisuhde  
  
-   Kenttä  
  
-   Kentän suojausprofiili  

-   Työnkulku
  
-   Lomake  
  
-   Sähköpostin yhdistämismalli  
  
-   Viesti  

-   Mallipohjainen sovellus
  
-   Asetusjoukko  
  
-   Laajennuskokoonpano  
  
-   Prosessi  
  
-   SDK-sanoman käsittelyvaihe  
  
-   Käyttöoikeusrooli  
  
-   Palvelupäätepiste  
  
-   Sivustokartta  

-   Näennäinen entiteetin tietopalvelu

-   Näennäinen entiteetin tietolähde
  
-   Verkkoresurssi  
  
 Jotkin osat ovat muiden osien sisällä. Esimerkiksi entiteetti sisältää lomakkeita, näkymiä, kaavioita, kenttiä, entiteettien välisiä suhteita, viestejä ja liiketoimintasääntöjä. Kaikki nämä osat edellyttävät entiteettiä. Kenttä ei voi olla entiteetin ulkopuolella. Sanotaan, että kenttä on riippuvainen entiteetistä. Osien tyyppejä on itse asiassa kaksi kertaa enemmän kuin edellä olevassa luettelossa on mainittu, mutta useimmat niistä eivät ole sisäkkäisiä eivätkä näy sovelluksessa.  
  
 Osien tarkoituksena on seurata rajoituksia siitä, mitä voidaan mukauttaa käyttämällä hallittuja ominaisuuksia ja riippuvuuksia niin, että ratkaisu voidaan viedä, tuoda ja (hallittujen ratkaisujen tapauksessa) poistaa jättämättä mitään jälkeä.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Hallitut ja hallitsemattomat ratkaisut  
 Ratkaisut voivat olla **hallittuja** tai **hallitsemattomia**. **Hallittu** ratkaisu voidaan poistaa, kun se on tuotu. Kaikki kyseisen ratkaisun osat poistetaan poistamalla ratkaisu.  
  
 Kun tuot **hallitsemattoman** ratkaisun, lisäät kaikki sen osat ympäristöösi. Et voi poistaa osia poistamalla ratkaisun.  
  
 Kun tuot **hallitsemattoman** ratkaisun, joka sisältää osia, jotka olet jo mukauttanut, mukautukset korvataan hallitsemattoman ratkaisun mukautuksilla. Et voi kumota tätä.  
  
> [!IMPORTANT]
>  Asenna hallitsematon ratkaisu vain, jos haluat lisätä kaikki osat ympäristöösi ja korvata aiemmin luodut mukautukset.  
  
 Vaikka et aikoisi jakaa sovelluksiasi tai mukautuksiasi, haluat ehkä luoda ja käyttää hallitsematonta ratkaisua, jotta saat erillisen näkymän, joka sisältää vain mukautetut sovelluksen osat. Kun mukautat jotakin, voit lisätä sen luomaasi hallitsemattomaan ratkaisuun.  
  
 Voit viedä **oletusratkaisusi** vain hallitsemattomana ratkaisuna.  
  
 Luo **hallittu** ratkaisu valitsemalla **Hallittuna** vaihtoehto, kun viet ratkaisun. Jos luot hallitun ratkaisun, et voi tuoda sitä takaisin samaan ympäristöön, jota käytit sen luomiseen. Voit tuoda sen vain muuhun ympäristöön.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Miten ratkaisuja otetaan käyttöön  
 Kaikki ratkaisut arvioidaan kerroksina sovelluksesi toimintojen määrittämiseksi. Seuraava kaavio näyttää, miten hallittuja ja hallitsemattomia ratkaisuja arvioidaan ja miten niiden muutokset näkyvät ympäristössäsi.  
  
 ![Ratkaisujen kerrostaminen](media/solution-layering.png "Ratkaisujen kerrostaminen")  
  
 Alhaalta ylöspäin:  
  
 **Järjestelmäratkaisu**  
 Järjestelmäratkaisu on kuin hallittu ratkaisu, joka jokaisella ympäristöllä on. Järjestelmäratkaisu on järjestelmän kaikkien käyttövalmiiden osien määritelmä.  
  
 **Hallitut ratkaisut**  
 Hallitut ratkaisut voivat muokata järjestelmän ratkaisun osia ja lisätä uusia osia. Jos useita hallittuja ratkaisuja asennetaan, niistä ensimmäinen on myöhemmin asennetun hallitun ratkaisun alla. Tämä tarkoittaa sitä, että toinen asennettu ratkaisu voi mukauttaa sitä ennen asennettua ratkaisua. Jos kahdella hallitulla ratkaisulla on ristiriitaisia määrityksiä, yleinen sääntö on ”uudempi voittaa”. Jos poistat hallitun ratkaisun, sen alapuolella oleva hallittu ratkaisu tulee voimaan. Jos poistat kaikki hallitut ratkaisut, käytetään järjestelmäratkaisun oletustoimintamallia.  
  
 **Hallitsemattomat mukautukset**  
 Hallitsemattomat mukautukset tarkoittavat ympäristöösi tekemiäsi muutoksia, jotka olet tehnyt hallitsemattoman ratkaisun kautta. Järjestelmäratkaisu määrittää, mitä voit tai et voi mukauttaa hallittujen ominaisuuksien avulla. Hallittujen ratkaisujen julkaisijat voivat samoin rajoittaa kykyäsi mukauttaa ratkaisun osia, jotka he lisäävät ratkaisuunsa. Voit mukauttaa mitä tahansa näistä ratkaisun osista, joilla ei ole hallittuja ominaisuuksia, jotka estävät niiden mukauttamisen.  
  
 **Sovelluksen toiminta**  
 Tämä on se, mitä itse asiassa näet ympäristössäsi. Järjestelmän oletusratkaisu, muut mahdolliset hallitut ratkaisut ja käyttöön ottamasi hallitsemattomat mukautukset.  
  
<a name="BKMK_ManagedProperties"></a>   
### <a name="managed-properties"></a>Hallitut ominaisuudet  
 Joitakin osia ei voi mukauttaa. Näissä järjestelmäratkaisun osissa on metatietoja, jotka estävät niiden mukauttamisen. Niitä kutsutaan **hallituiksi ominaisuuksiksi**. Hallitun ratkaisun julkaisija voi myös määrittää hallitut ominaisuudet estääkseen sinua mukauttamasta ratkaisua ei-toivotuilla tavoilla.  
  
<a name="BKMK_Dependencies"></a>   
### <a name="solution-dependencies"></a>Ratkaisun riippuvuudet  
 Hallittujen ratkaisujen kerrostuksesta johtuen jotkin hallitut ratkaisut voivat olla riippuvaisia muiden hallittujen ratkaisujen osista. Jotkin ratkaisun julkaisijat hyödyntävät tätä luodakseen modulaarisia ratkaisuja. Saatat joutua asentamaan ensin hallitun ”perusratkaisun” ja sitten toisen hallitun ratkaisun, joka mukauttaa perusratkaisun osia. Toinen hallittu ratkaisu on tällöin riippuvainen ensimmäisen ratkaisun osista.  
  
 Järjestelmä seuraa näitä riippuvuussuhteita ratkaisujen välillä. Jos yrität asentaa ratkaisua, joka vaatii perusratkaisun, jota ei ole asennettu, et pysty asentamaan ratkaisua. Näyttöön tulee sanoma, että ratkaisu edellyttää toisen ratkaisun asentamista. Vastaavasti riippuvuuksien vuoksi et voi poistaa perusratkaisun asennusta, jos siitä riippuvainen ratkaisu on asennettuna. Sinulla on poistettava riippuvaisen ratkaisun asennus, ennen kuin poistat perusratkaisun.  
  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
[Ratkaisujen tuominen, päivittäminen ja vieminen](import-update-export-solutions.md) <br/>
[Tiettyyn ratkaisuun siirtyminen](navigate-specific-solution.md)
 
