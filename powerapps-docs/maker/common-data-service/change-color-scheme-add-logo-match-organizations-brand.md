---
title: Värimallin muuttaminen tai logon lisääminen organisaation tuotemerkkiä vastaavaksi | MicrosoftDocs
ms.custom: ''
ms.date: 06/18/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
author: Mattp123
ms.assetid: 21a166a0-d25e-4260-a1e4-2ddc528787c2
caps.latest.revision: 17
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-a-theme"></a>Teeman luominen

Voit luoda sovelluksellesi mukautetun ulkoasun (teeman) muuttamalla mukauttamattoman järjestelmän oletusvärejä ja visuaalisia elementtejä. Voit esimerkiksi luoda oman tuotemerkin lisäämällä yrityksen logon ja määrittämällä entiteettikohtaiset värit. Teema luodaan käyttöliittymän mukautustyökalujen avulla ilman, että kehittäjän tarvitsee kirjoittaa koodia. Voit luoda, muuttaa tai poistaa organisaatiosi käytössä olevia teemoja. Dynamics 365 for Outlookin WWW-lomakkeet tukevat teeman mukautuksia. Voit määrittää useita teemoja, mutta vain yksi voidaan asettaa ja julkaista oletusteemana.  
  
<a name="UseThemes"></a>   
## <a name="use-themes-to-enhance-the-user-interface-and-create-your-product-branding"></a>Teemojen käyttäminen käyttöliittymän parantamisessa ja tuotemerkin luomisessa  
 Teeman määrittäminen on tarkoitettu sovelluksen käyttöliittymän parantamiseen eikä sen merkittävään muuttamiseen. Teeman värit ovat käytössä koko sovelluksessa. Voit parantaa esimerkiksi seuraavia käyttöliittymän visuaalisia elementtejä:  
  
-   Tuotemerkin luominen tuotteen logojen ja siirtymisen värien muuttamisen avulla  
  
-   Muokkaa korostuksen värejä, kuten valintavärejä  
  
-   Määritä entiteettikohtainen väritys  
    
-   Logo  
  
-   Logon työkaluvihje  
  
-   Siirtymispalkin väri  
  
-   Siirtymispalkin toinen väri

-   Unified Interfacen pääkomentopalkin väri
  
-   Otsikon väri  
  
-   Yleinen linkin väri  
  
-   Valittu linkki -tehoste  
  
-   Kohdistin linkin päällä -tehoste  
  
-   Prosessin ohjausobjektin väri  
  
-   Entiteetin oletusväri  
  
-   Mukautetun entiteetin oletusväri  
  
-   Ohjausobjektin sävy  
  
-   Ohjausobjektin reunat  
  
<a name="Solution"></a>   
## <a name="solution-awareness"></a>Ratkaisukeskeisyys  
 Teema ei ole ratkaisukohtainen. Organisaation teemaan tehdyt muutokset eivät sisälly organisaatiosta vietyihin ratkaisuihin. Tiedot tallennetaan teeman entiteettiin, jonka voi viedä ja tuoda uudelleen toiseen ympäristöön. Tuotu teema on julkaistava, jotta se otetaan käyttöön.  
  
<a name="CloneAlter"></a>   
## <a name="copy-and-alter-the-existing-theme"></a>Aiemmin määritetyn teeman kopioiminen ja muuttaminen  
 Helpoin ja nopein tapa luoda uusi teema on kopioida aiemmin määritetty teema ja muokata sitä. Tämän jälkeen se tallennetaan, esikatsellaan ja julkaistaan. 
 
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.

2.  Valitse **mallin perustuva** (alavasemmalla). 

3.  Valitse ![Asetukset-kuvake](../model-driven-apps/media/powerapps-gear.png) (oikealla yläosassa) > **Lisämukautukset**. 

4. Valitse **Teemat**-kohdassa **Kaikki teemat**. 

5. Valitse **CRM-oletusteema**. 

Seuraavassa näyttökuvassa on osa oletusteeman asetuksista.  
  
![Oletusteema](media/default-theme.png) 
  
 Olemme kopioineet oletusteeman ja muuttaneet värejä. Seuraavissa näyttökuvissa näkyvät uudet siirtymisen ja korostamisen värit. Voit myös valita tuotteelle uuden logon.  
  
 Seuraavassa näyttökuvassa näkyy uusi siirtymisen väri.  
  
 ![Hellävaraisen vihreät teemavärit](media/theme-gentle-green.png "Hellävaraisen vihreät teemavärit")  
  
 Seuraavassa näyttökuvassa näkyvät asiakkaan entiteetin ruudukko ja uusi korostusväri.  
  
 ![Hellävaraisen vihreä teeman tiliruutu](media/themes-gentle-green-account-grid.png "Hellävaraisen vihreä teeman tiliruutu")  
  
<a name="Publish"></a>   
## <a name="preview-and-publish-a-theme"></a>Teeman esikatseleminen ja julkaiseminen  
 Voit esikatsella ja julkaista teeman seuraavien vaiheiden avulla:  
  
-   Luo uusi teema alusta alkaen tai kopioi aiemmin luotu teema.  
  
-   Esikatsele uusi teema valitsemalla komentorivin **Esikatsele**-vaihtoehto. Voit poistua esikatselutilasta valitsemalla komentorivin **Esikatsele**-painikkeen vieressä oleva **Poistu esikatselusta**.  
  
-   Julkaise teema. Valitse komentorivin **JULKAISE TEEMA** -vaihtoehto.  
  
 Seuraavassa näyttökuvassa näkyvät komentorivin esikatselun ja julkaisun painikkeet.  
  
 ![Siirry esikatselutilaan / -tilasta pois esikatselupainikkeiden avulla](media/themes-preview-buttons.PNG "Siirry esikatselutilaan / -tilasta pois esikatselupainikkeiden avulla")  
  
<a name="BestPracticies"></a>   
## <a name="best-practices"></a>Parhaat käytännöt  
 Seuraavaksi esitellään teemojen kontrastien suunnittelun ja värien valinnan suositukset.  
  
### <a name="theme-contrast"></a>Teeman kontrasti  
 Suosittelemme kontrastien värejä käytettäväksi seuraavalla tavalla:  
  
-   Kontrastien värit kannattaa valita huolella. Kontrastien värit kannattaa valita huolella. Common Data Service sovelluksille -ratkaisun valmiissa oletusteemassa on optimaalista käytettävyyttä tukevat kontrastisuhteet. Käytä uusissa teemoissa samoja suhteita.  
  
-   Käytä suurissa kontrasteissa oletusväriasetuksia.  
  
### <a name="theme-colors"></a>Teemavärit  
 Suosittelemme, että käytössä ei ole samanaikaisesti useita eri värejä. Vaikka jokaiselle entiteetille voi määrittää eri värin, suosittelemme jommankumman seuraavan mallin käyttämistä:  
  
-   Käytä kaikissa entiteeteissä neutraaleja värejä ja käytä avainentiteeteissä korostusta.  
  
-   Käytä samanlaisissa tai toisiinsa liittyvissä entiteeteissä samaa väriä. Tällaisia entiteettejä voivat olla esimerkiksi jono ja jonon kohde tai tuoteluettelon entiteetit. Pidä ryhmien kokonaismäärä pienenä.  
  
<a name="Considerations"></a>   
## <a name="custom-theme-considerations"></a>Mukautettujen teemojen huomioon otettavat seikat  
 Ota huomioon seuraavat seikat, kun suunnittelet mukautettujen teemojen käyttöönottoa:  
  
-   Useimmat päivitetyt käyttöliittymäalueet näytetään mukautetuissa teemaväreissä.  
  
-   Vaikka teeman värejä käytetään yleisesti koko sovelluksessa, joillakin vanhoilla käyttöliittymäalueilla, kuten liukuväripainikkeissa, säilytetään oletusvärit.  
  
-   Tietyillä alueilla on käytettävä tummia tai vaaleita värejä, jotta kontrasti kuvakkeiden oletusvärien kanssa säilyy. Kuvakkeen väriä ei voi mukauttaa.  
  
-   Entiteettiä ei voi näyttää eri väreissä eri sivustokartan solmuissa.  
  
-   Sivustokartan solmujen värejä ei voi mukauttaa.  
  
## <a name="see-also"></a>Katso myös  
         
 [Video: Dynamics 365 Customer Engagementin teemat](http://go.microsoft.com/fwlink/p/?LinkId=529568) [Organisaation teeman kysely ja muokkaaminen](https://docs.microsoft.com/dynamics365/customer-engagement/developer/customize-dev/query-and-edit-an-organization-theme)

