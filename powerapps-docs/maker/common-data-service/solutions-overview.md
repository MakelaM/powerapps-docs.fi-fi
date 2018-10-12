---
title: Ratkaisujen käyttö PowerAppsissa | MicrosoftDocs
description: Lue, miten ratkaisuja jaetaan
ms.custom: ''
ms.date: 06/21/2018
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
ms.assetid: ece68f5f-ad40-4bfa-975a-3e5bafb854aa
caps.latest.revision: 55
ms.author: matp
manager: kvivek
ms.openlocfilehash: 47fb64e650da2f3e1a9e0cf523060cf7d9f5a03b
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39675408"
---
<a name="BKMK_Solutions"></a>   
# <a name="solutions-overview"></a>Ratkaisujen yleiskuvaus  

 Ratkaisujen avulla mallipohjainen sovellus voidaan ostaa, jakaa tai siirtää muulla tavalla organisaatiosta toiseen. Voit hankkia ratkaisuja [AppSourcesta](https://appsource.microsoft.com/) tai itsenäisiltä ohjelmistotoimittajilta (ISV). Ratkaisu on tiedosto, jonka voit tuoda ympäristöön sovelluksena tai jolla voit ottaa käyttöön joukon mukautuksia olemassa olevassa sovelluksessa.  
  
Lisätietoja: [Raportti: Patterns and Principles for Solution Builders](http://go.microsoft.com/fwlink/p/?LinkID=533946)  
  
> [!NOTE]
>  Jos olet itsenäinen ohjelmistokehittäjä ja olet luomassa jaeltavaa sovellusta, sinun on käytettävä ratkaisuja. Katso lisätietoja ratkaisujen käyttämisestä kohdasta [Laajennusten paketointi ja jakelu ratkaisujen avulla](https://msdn.microsoft.com/library/gg334530.aspx).  
  
 Jos olet vain kiinnostunut PowerApps-sovellusten luomisesta organisaation käyttöön tai Dynamics 365:n mukauttamisesta, sinun tulee tietää nämä seikat ratkaisuista:  
  
-   Ratkaisujen luominen on valinnaista. Voit luoda tai mukauttaa sovelluksia suoraan PowerApps-ympäristössäsi luomatta ratkaisuja.  
  
-   Kun mukautat PowerApps-ympäristöä suoraan, käytät siihen erityisratkaisua nimeltä **Yhteisten tietopalvelujen oletusratkaisu**. Tämä ratkaisu sisältää kaikki osat järjestelmässäsi.  
  
-   Voit viedä oletusratkaisusi ja luoda siten varmuuskopion mukautuksista, jotka olet määrittänyt organisaatiossasi. Tämä on hyvä tehdä pahimman varalta.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="solution-components"></a>Ratkaisun osat  
 Ratkaisun osa edustaa jotakin, jota voit ehkä mukauttaa. Kaikki kohteet, joita ratkaisuun voidaan sisällyttää, ovat ratkaisun osia. Seuraavassa on luettelo ratkaisun osista, jotka voit tarkastella ratkaisussa:  
  
-   Sovelluksen valintanauha  

-   Sovellus 
  
-   Artikkelimalli  
  
-   Liiketoimintasääntö  
  
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
  
-   Lomake  
  
-   Sähköpostin yhdistämismalli  
  
-   Viesti  
  
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
  
 Useimmat ratkaisun osat ovat sisäkkäin ratkaisun muiden osien kanssa. Esimerkiksi entiteetti sisältää lomakkeita, näkymiä, kaavioita, kenttiä, entiteettien välisiä suhteita, viestejä ja liiketoimintasääntöjä. Kaikki nämä ratkaisun osat edellyttävät entiteettiä. Kenttä ei voi olla entiteetin ulkopuolella. Sanotaan, että kenttä on riippuvainen entiteetistä. Ratkaisun osien tyyppejä on itse asiassa kaksi kertaa enemmän kuin edellä olevassa luettelossa, mutta useimmat niistä eivät näy sovelluksessa.  
  
 Ratkaisun osien tarkoituksena on seurata rajoituksia siitä, mitä voidaan mukauttaa käyttämällä hallittuja ominaisuuksia ja ratkaisun riippuvuuksia niin, että se voidaan viedä, tuoda ja (hallituissa ratkaisuissa) poistaa jättämättä mitään jälkeä.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Hallitut ja hallitsemattomat ratkaisut  
 **Hallittu** ratkaisu voidaan poistaa, kun se on tuotu. Kaikki kyseisen ratkaisun osat poistetaan poistamalla ratkaisu.  
  
 Kun tuot **hallitsemattoman** ratkaisun, lisäät kaikki sen osat oletusratkaisuusi. Et voi poistaa osia poistamalla ratkaisun.  
  
 Kun tuot **hallitsemattoman** ratkaisun, joka sisältää ratkaisun osia, jotka olet jo mukauttanut, mukautukset korvataan hallitsemattoman ratkaisun mukautuksilla. Et voi kumota tätä.  
  
> [!IMPORTANT]
>  Asenna hallitsematon ratkaisun vain, jos haluat lisätä kaikki osat oletusratkaisuusi ja korvata aiemmin luodut mukautukset.  
  
 Vaikka et aikoisi jakaa ratkaisuasi, haluat ehkä luoda ja käyttää hallitsematonta ratkaisua, jotta saat erillisen näkymän, joka sisältää vain mukautetut sovelluksen osat. Kun mukautat jotakin, voit lisätä sen luomaasi hallitsemattomaan ratkaisuun.  
  
 Voit viedä oletusratkaisusi vain hallitsemattomana ratkaisuna.  
  
 Luo **hallittu** ratkaisu valitsemalla hallitun ratkaisun vaihtoehto, kun viet ratkaisua. Jos luot hallitun ratkaisun, et voi tuoda sitä takaisin samaan organisaatioon jota käytit sen luomiseen. Voit tuoda sen vain muuhun organisaatioon.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Miten ratkaisuja otetaan käyttöön  
 Kaikki ratkaisut arvioidaan kerroksina sovelluksesi toimintojen määrittämiseksi. Seuraava kaavio näyttää, miten hallittuja ja hallitsemattomia ratkaisuja arvioidaan ja miten niiden muutokset näkyvät organisaatiossasi.  
  
 ![Ratkaisujen kerrostaminen](media/solution-layering.png "Ratkaisujen kerrostaminen")  
  
 Alhaalta ylöspäin:  
  
 **Järjestelmäratkaisu**  
 Järjestelmäratkaisu on kuin hallittu ratkaisu, joka jokaisella organisaatiolla on. Järjestelmäratkaisu on järjestelmän kaikkien käyttövalmiiden osien määritelmä.  
  
 **Hallitut ratkaisut**  
 Hallitut ratkaisut voivat muokata järjestelmän ratkaisun osia ja lisätä uusia osia. Jos useita hallittuja ratkaisuja asennetaan, niistä ensimmäinen on myöhemmin asennetun hallitun ratkaisun alla. Tämä tarkoittaa sitä, että toinen asennettu ratkaisu voi mukauttaa sitä ennen asennettua ratkaisua. Jos kahdella hallitulla ratkaisulla on ristiriitaisia määrityksiä, yleinen sääntö on ”uudempi voittaa”. Jos poistat hallitun ratkaisun, sen alapuolella oleva hallittu ratkaisu tulee voimaan. Jos poistat kaikki hallitut ratkaisut, käytetään järjestelmäratkaisun oletustoimintamallia.  
  
 **Hallitsemattomat mukautukset**  
 Hallitsemattomat mukautukset ovat organisaatioosi tehtyjä muutoksia, jotka on tehty hallitsemattoman ratkaisun kautta. Järjestelmäratkaisu määrittää, mitä voit tai et voi mukauttaa hallittujen ominaisuuksien avulla. Hallittujen ratkaisujen julkaisijat voivat samoin rajoittaa kykyäsi mukauttaa ratkaisun osia, jotka he lisäävät ratkaisuunsa. Voit mukauttaa mitä tahansa näistä ratkaisun osista, joilla ei ole hallittuja ominaisuuksia, jotka estävät niiden mukauttamisen.  
  
 **Sovelluksen toiminta**  
 Tämä on se, mitä itse asiassa näet organisaatiossasi. Järjestelmän oletusratkaisu, muut mahdolliset hallitut ratkaisut ja käyttöön ottamasi hallitsemattomat mukautukset.  
  
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
 
