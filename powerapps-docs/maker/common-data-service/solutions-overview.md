---
title: Ratkaisujen kanssa työskentely PowerAppsissa | MicrosoftDocs
description: 'Tietoja siitä, miten ratkaisut jaetaan'
ms.custom: ''
ms.date: 05/28/2019
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
---
   
# <a name="solutions-overview"></a>Ratkaisujen yleiskatsaus  

  PowerAppsissa ratkaisuja käytetään siirtämään sovelluksia ja komponentteja ympäristöstä toiseen tai käyttämään mukautussarjoja aiemmin luoduissa sovelluksissa. Ratkaisuun sisältyy vähintään yksi sovellus ja muita osia, kuten entiteettejä ja asetusjoukkoja. Voit hankkia ratkaisun [AppSourcesta](https://appsource.microsoft.com/) tai riippumattomalta ohjelmistotoimittajalta (ISV).
  
Lisätietoja: [Raportti: Ratkaisun elinkaaren hallinta](https://www.microsoft.com/en-us/download/details.aspx?id=57777)  
  
> [!NOTE]
>  Jos olet riippumaton ohjelmistotoimittaja ja luot sovelluksen jaettavaksi, sinun on käytettävä ratkaisuja. Lisätietoja ratkaisujen käyttämisestä on kohdassa [Kehittäjän opas: Johdanto ratkaisuihin](/powerapps/developer/common-data-service/introduction-solutions).  
  

<a name="BKMK_SolutionComponents"></a>   
### <a name="components"></a>Osat  
 Osa viittaa mukautettavaan osaan. Osia ovat kaikki, mitä voidaan ottaa mukaan ratkaisuun. Seuraavassa luettelossa on osia, joita voi tarkastella ratkaisussa:  
  
-   Sovelluksen valintanauha  
  
-   Artikkelimalli  
  
-   Liiketoimintasääntö  

-   Kaaviosovellus 
  
-   Kaavio  
  
-   Yhteysrooli  
  
-   Palvelusopimusmalli  
 
-   Mukautettu ohjausobjekti
  
-   Koontinäyttö  
  
-   Sähköpostimalli  
  
-   Entiteetti  
  
-   Entiteettisuhde  
  
-   Kenttä  
  
-   Kentän suojausprofiili  

-   Työnkulku
  
-   Lomake  
  
-   Yhdistämismalli  
  
-   Viesti  

-   Malliin perustuva sovellus
  
-   Asetusjoukko  
  
-   Laajennuskokoonpano  
  
-   Prosessi  
  
-   SDK-viestin käsittelyn osavaihe  
  
-   Käyttöoikeusrooli  
  
-   Palvelupäätepiste  
  
-   Sivustokartta  

-   Virtuaalisen entiteetin tietojen tarjoaja

-   Virtuaalisen entiteetin tietolähde
  
-   WWW-resurssi  
  
 Jotkin osat ovat muiden osien sisällä. Esimerkiksi entiteetti sisältää lomakkeita, näkymiä, kaavioita, kenttiä, entiteettisuhteita, viestejä ja liiketoimintasääntöjä. Kukin osa edellyttää entiteettiä. Kenttää ei ole olemassa entiteetin ulkopuolella. Kenttä on siis riippuvainen entiteetistä. Osia on itse asiassa kaksi kertaa enemmän kuin edellä olevassa luettelossa on mainittu, mutta useimmat niistä eivät ole sisäkkäisiä osia eivätkä näy sovelluksessa.  
  
 Osien tarkoitus on seurata mahdollisia rajoituksia siitä, mitä voi mukauttaa hallituissa ratkaisuissa ja mitä kaikki riippuvuudet ovat, jotta se voidaan viedä, tuoda ja (hallituissa ratkaisuissa) poistaa niin, ettei mitään jätetä pois.  
  
<a name="BKMK_ManagedAndUnmanagedSolutions"></a>   
### <a name="managed-and-unmanaged-solutions"></a>Hallitut ja ei-hallitut ratkaisut  
 Ratkaisut ovat joko **hallittuja** tai **ei-hallittuja**. **Hallittua** ratkaisua ei voi muokata, mutta sen asennus voidaan poistaa, kun se on tuotu. Ratkaisun asennuksen poistaminen poistaa kaikki kyseisen ratkaisun osat.  
  
 **Ei-hallittua** ratkaisua tuotaessa kyseisen ratkaisun kaikki osat lisätään ympäristöön. Ratkaisun asennuksen poistaminen ei poista osia.  
  
 Kun tuot **ei-hallitun** ratkaisun, joka sisältää mukautettuja osia, ei-hallitun ratkaisun mukautukset korvaavat aiemmat mukautukset. Sitä ei voi kumota.  
  
> [!IMPORTANT]
>  Asenna ei-hallittu ratkaisu vain, jos haluat lisätä kaikki osat ympäristöön ja korvata kaikki aiemmin luodut mukautukset.  
  
 Vaikka et aikoisi jakaa sovelluksia tai mukautuksia, ei-hallitun luomalla ja sitä käyttämällä saat erillisen näkymän, joka sisältää vain mukauttamasi sovelluksen osat. Aina kun mukautat jotakin, lisää se luomaasi ei-hallittuun ratkaisuun.  
  
 Voit viedä **oletusratkaisun** vain ei-hallittuna ratkaisuna.  
  
 Luo **hallittu** ratkaisu valitsemalla ratkaisun vientiasetukseksi **Hallittuna**. Jos luot hallitun ratkaisun, et voi tuoda sitä takaisin siihen ympäristöön, jossa loit sen. Voit tuoda sen vain eri ympäristöön.  
  
<a name="BKMK_HowSolutionsAreApplied"></a>   
### <a name="how-solutions-are-applied"></a>Ratkaisujen käyttäminen  
 Kaikki ratkaisut arvioidaan kerroksina. Tällä tavoin voidaan selvittää, miten sovellus tulee toimimaan. Seuraava kaavio osoittaa, miten hallittuja ja ei-hallittuja ratkaisuja arvioidaan ja miten niissä tehdyt muutokset näkyvät ympäristössä.  
  
 ![Ratkaisun pinoaminen](media/solution-layering.png "Ratkaisun pinoaminen")  
  
 Kaavio käsitellään alhaalta ylöspäin:  
  
 **Järjestelmäratkaisu**  
 Järjestelmäratkaisu on eräänlainen jokaisessa ympäristössä oleva hallittu ratkaisu. Järjestelmäratkaisu koostuu järjestelmän kaikista heti käytettävissä olevista osista.  
  
 **Hallitut ratkaisut**  
 Hallituilla ratkaisuilla voidaan muokata järjestelmäratkaisun osia ja lisätä uusia osia. Jos asennettuja hallittuja ratkaisuja on useita, ensimmäiseksi asennettu ratkaisu sijaitsee myöhemmin asennetun hallitun ratkaisun alapuolella. Käytännössä tämä tarkoittaa sitä, että toinen asennettu ratkaisu voi mukauttaa sitä ennen asennettua ratkaisua. Jos kahdessa hallitussa ratkaisussa on keskenään ristiriitaisia määritelmä, yleensä jälkimmäistä noudatetaan. Jos poistat hallitun ratkaisun asennuksen, sen alapuolella olevaa hallittua ratkaisua käytetään. Jos poistat kaikkien hallittujen ratkaisujen asennuksen, järjestelmäratkaisussa määritetty oletustoiminta otetaan käyttöön.  
  
 **Ei-hallitut mukautukset**  
 Ei-hallitut mukautukset ovat muutoksia, joita on tehty ympäristöön ei-hallitulla ratkaisulla. Järjestelmäratkaisu määrittää, mitä voidaan mukauttaa ja mitä ei käyttäen hallittuja ominaisuuksia. Hallittujen ratkaisujen julkaisijat voivat rajoittaa samalla tavoin ratkaisuun lisäämiensä ratkaisun osien mukauttamismahdollisuuksia. Voit mukauttaa kaikkia ratkaisun osia, joissa ei ole hallittuja ominaisuuksia, jotka estävät niiden mukauttamisen.  
  
 **Sovelluksen toimintatapa**  
 Tämä on se, mitä näet ympäristössä. Oletusjärjestelmäratkaisu ja mahdolliset hallitut ratkaisut sekä mahdolliset käyttöönotetut ei-hallitut mukautukset.  
  
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
 
