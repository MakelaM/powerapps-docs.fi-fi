---
title: Ratkaisujen kanssa työskentely PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten ratkaisut jaetaan'
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
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

<a name="BKMK_Solutions"></a>   
# <a name="solutions-overview"></a>Ratkaisujen yleiskatsaus  

 Ratkaisut on luotu sen vuoksi, että malliin perustuva sovellus voidaan ostaa, jakaa tai muutoin siirtää organisaatiosta toiseen. Saat [AppSource](https://appsource.microsoft.com/)-ratkaisuja tai riippumattoman ohjelmistotoimittajan ratkaisuja (ISV: HEN). Ratkaisu on tiedosto, jonka voit tuoda ympäristöön sovelluksena tai käyttää mukautuksia aiemmin luotuun sovellukseen.  
  
Lisätietoja: [Julkaisu: Ratkaisun konfiguraattorien mallit ja käytännöt](http://go.microsoft.com/fwlink/p/?LinkID=533946)  
  
> [!NOTE]
>  Jos olet riippumaton ohjelmistotoimittaja ja luot sovelluksen jaettavaksi, sinun on käytettävä ratkaisuja. Lisätietoja ratkaisujen käyttämisestä on ohjeaiheessa [Ratkaisuja käyttävät paketit ja jaettavat laajennukset](https://msdn.microsoft.com/library/gg334530.aspx).  
  
 Seuraavassa on lisätietoja ratkaisuista, jos olet kiinnostunut luomaan PowerApps-sovelluksia organisaatiota varten tai muokkaamaan Dynamics 365:ttä:  
  
-   Ratkaisujen luominen on valinnaista. Voit luoda kaikki PowerApps-ympäristön sovellukset tai mukauttaa niitä suoraan ilman ratkaisun luomista.  
  
-   Kun mukautat PowerApps-ympäristöä suoraan, käsittelet erityisratkaisua, jonka nimi on **Common Data Services -oletusratkaisu**. Tämä ratkaisu sisältää kaikki järjestelmän komponentit.  
  
-   Voit viedä oletusratkaisun ja luoda varmuuskopion organisaatiossa määritetyistä mukautuksista. Se on hyvä olla olemassa varmuuden vuoksi.  
  
<a name="BKMK_SolutionComponents"></a>   
### <a name="solution-components"></a>Ratkaisun osat  
 Ratkaisun osa viittaa mukautettavaan osaan. Kaikki, mitä voidaan ottaa mukaan ratkaisuun, ovat ratkaisun osia. Seuraavassa luettelossa ratkaisun osia, joita voi tarkastella ratkaisussa:  
  
-   Sovelluksen valintanauha  

-   Sovellus 
  
-   Artikkelimalli  
  
-   Liiketoimintasääntö  
  
-   Kaavio  
  
-   Yhteysrooli  
  
-   Palvelusopimusmalli  
 
-   Mukautettu ohjausobjekti
  
-   Koontinäyttö  
  
-   Sähköpostimalli  
  
-   Entity  
  
-   Entiteettisuhde  
  
-   Kenttä  
  
-   Kentänsuojausprofiili  
  
-   Lomake  
  
-   Yhdistämismalli  
  
-   Viesti  
  
-   Asetusjoukko  
  
-   Laajennuskokoonpano  
  
-   Prosessi  
  
-   SDK-viestin käsittelyn osavaihe  
  
-   Käyttöoikeusrooli  
  
-   Palvelupäätepiste  
  
-   Sivustokartta  

-   Virtuaalisen entiteetin tietojen tarjoaja

-   Virtuaalisen entiteetin tietolähde
  
-   Verkkoresurssi  
  
 Useimmat ratkaisun osat ovat sisäkkäin ratkaisun muissa osissa. Esimerkiksi entiteetti sisältää lomakkeita, näkymiä, kaavioita, kenttiä, entiteettisuhteita, viestejä ja liiketoimintasääntöjä. Kukin ratkaisun osa edellyttää entiteettiä. Kenttää ei ole olemassa entiteetin ulkopuolella. Kenttä on siis riippuvainen entiteetistä. Ratkaisun osia on itse asiassa kaksi kertaa enemmän kuin edellä olevassa luettelossa on mainittu, mutta useimmat niistä eivät näy sovelluksessa.  
  
 Ratkaisun osien tarkoitus on seurata mahdollisia rajoituksia siitä, mitä voi mukauttaa hallituissa ratkaisuissa ja mitä kaikki Ratkaisujen riippuvuudet ovat, jotta se voidaan viedä, tuoda ja (hallituissa ratkaisuissa) poistaa niin, ettei mitään jätetä pois.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Hallitut ja ei-hallitut ratkaisut  
 **Hallitun** ratkaisun asennus voidaan poistaa, kun se on tuotu. Ratkaisun asennuksen poistaminen poistaa kaikki kyseisen ratkaisun osat.  
  
 **Ei-hallittua** ratkaisua tuotaessa lisäät kyseisen ratkaisun osat oletusratkaisuun. Ratkaisun asennuksen poistaminen ei poista osia.  
  
 Kun tuot **ei-hallitun** ratkaisun, joka sisältää mukautettuja ratkaisun osia, ei-hallitun ratkaisun mukautukset korvaavat aiemmat mukautukset. Sitä ei voi kumota.  
  
> [!IMPORTANT]
>  Asenna ei-hallittu ratkaisu vain, jos haluat lisätä kaikki oletusratkaisun osat ja korvata kaikki aiemmin luodut mukautukset.  
  
 Vaikka et aikoisi jakaa ratkaisua, luomalla ja käyttämällä ei-hallittua ratkaisua saat erillisen näkymän, joka sisältää vain mukauttamasi sovelluksen osat. Aina kun mukautat jotakin, lisää se luomaasi ei-hallittuun ratkaisuun.  
  
 Voit viedä oletusratkaisun vain ei-hallittuna ratkaisuna.  
  
 Luo **hallittu** ratkaisu valitsemalla ratkaisun vientiasetukseksi hallittu ratkaisu. Jos luot hallitun ratkaisun, et voi tuoda sitä takaisin organisaatioon, jossa loit sen. Voit tuoda sen vain eri organisaatioon.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Ratkaisujen käyttäminen  
 Kaikki ratkaisut arvioidaan kerroksina. Tällä tavoin voidaan selvittää, miten sovellus tulee toimimaan. Seuraavasta kaaviosta selviää, miten hallittuja ja ei-hallittuja ratkaisuja arvioidaan ja miten niissä tehdyt muutokset näkyvät organisaatiossa.  
  
 ![Ratkaisun pinoaminen](media/solution-layering.png "Ratkaisun pinoaminen")  
  
 Kaavio käsitellään alhaalta ylöspäin:  
  
 **Järjestelmäratkaisu**  
 Järjestelmäratkaisu on eräänlainen jokaisessa organisaatiossa oleva hallittu ratkaisu. Järjestelmäratkaisu koostuu järjestelmän kaikista heti käytettävissä olevista osista.  
  
 **Hallitut ratkaisut**  
 Hallituilla ratkaisuilla voidaan muokata järjestelmäratkaisun osia ja lisätä uusia osia. Jos asennettuja hallittuja ratkaisuja on useita, ensimmäiseksi asennettu ratkaisu sijaitsee myöhemmin asennetun hallitun ratkaisun alapuolella. Käytännössä tämä tarkoittaa sitä, että toinen asennettu ratkaisu voi mukauttaa sitä ennen asennettua ratkaisua. Jos kahdessa hallitussa ratkaisussa on keskenään ristiriitaisia määritelmä, yleensä jälkimmäistä noudatetaan. Jos poistat hallitun ratkaisun asennuksen, sen alapuolella olevaa hallittua ratkaisua käytetään. Jos poistat kaikkien hallittujen ratkaisujen asennuksen, järjestelmäratkaisussa määritetty oletustoiminta otetaan käyttöön.  
  
 **Ei-hallitut mukautukset**  
 Ei-hallitut mukautukset ovat muutoksia, joita on tehty organisaatioon ei-hallitulla ratkaisulla. Järjestelmäratkaisu määrittää, mitä voidaan mukauttaa ja mitä ei käyttäen hallittuja ominaisuuksia. Hallittujen ratkaisujen julkaisijat voivat rajoittaa samalla tavoin ratkaisuun lisäämiensä ratkaisun osien mukauttamismahdollisuuksia. Voit mukauttaa kaikkia ratkaisun osia, joissa ei ole hallittuja ominaisuuksia, jotka estävät niiden mukauttamisen.  
  
 **Sovelluksen toimintatapa**  
 Tämä on se, minkä näet organisaatiossa. Oletusjärjestelmäratkaisu ja mahdolliset hallitut ratkaisut sekä mahdolliset käyttöönotetut ei-hallitut mukautukset.  
  
<a name="BKMK_ManagedProperties"></a>   
### <a name="managed-properties"></a>Hallitut ominaisuudet  
 Joitakin osia ei voi mukauttaa. Näissä järjestelmäratkaisun osissa on metatietoja, jotka estävät niiden mukauttamisen. Niitä kutsutaan **hallitutuiksi ominaisuuksiksi**. Hallitun ratkaisun julkaisija voi määrittää myös hallittuja ominaisuuksia ja estää tällä tavoin ratkaisun mukauttamisen ei-toivotulla tavalla.  
  
<a name="BKMK_Dependencies"></a>   
### <a name="solution-dependencies"></a>Ratkaisujen riippuvuudet  
 Koska hallitut ratkaisut on sijoitettu kerroksittain, jotkin hallitut ratkaisut voivat olla riippuvaisia toisten hallittujen ratkaisujen osista. Osa ratkaisujulkaisijoita hyödyntää tätä ominaisuutta ja luoda modulaarisia ratkaisuja. Siinä tapauksessa hallittu perusratkaisu on asennettava ensin, jonka jälkeen asennetaan toinen hallittu ratkaisu, joka mukauttaa hallitun perusratkaisun osia. Toinen hallittu ratkaisu on riippuvainen ensimmäiseen ratkaisuun sisältyvistä ratkaisun osista.  
  
 Järjestelmä seuraa ratkaisujen välisiä riippuvuuksia. Jos yrität asentaa ratkaisun, jonka käyttö edellyttää perusratkaisua, jota ei ole asennettu, et voi asentaa ratkaisua. Näyttöön avautuu sanoma, jonka mukaan ratkaisu edellyttää toisen ratkaisun asentamista ensin. Et voi myöskään poistaa riippuvuuksien vuoksi perusratkaisua, kun siitä riippuvainen ratkaisu on edelleen asennettuna. Riippuvaisen ratkaisun asennus on siis poistettava ennen perusratkaisun asennuksen poistamista.  
  
  
## <a name="next-steps"></a>Seuraavat vaiheet  
[Ratkaisujen tuominen. päivittäminen ja vieminen](import-update-export-solutions.md) <br/>
[Siirtyminen tiettyyn ratkaisuun](navigate-specific-solution.md)
 
