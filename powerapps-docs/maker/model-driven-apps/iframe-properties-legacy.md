---
title: Mallipohjaisen sovelluksen päälomakkeiden iFrame-ominaisuudet PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeiden iFrame-resurssin ominaisuuksista
Keywords: Main form; iFrame properties; Dynamics 365
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/18/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 1b7e6a0c-18a9-47e2-aa7d-0cffb8c93b19
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="iframe-properties-for-model-driven-app-main-forms"></a>Mallipohjaisten sovellusten päälomakkeiden iFrame-ominaisuudet

Voit lisätä iFrame-kehyksen integroimaan toisen sivuston sisältöä lomakkeeseen. 

Voit tarkastella iFrame-ominaisuuksia näiden ohjeiden avulla.

1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti. 

3. Avaa lomakeluettelosta lomake, joka on **päälomake**. Voit tarkastella IFRAME-ominaisuuksia valitsemalla **Lisää**-välilehdessä IFRAME.

![iframe-properties](media/iframe-properties.png)


> [!NOTE]
> Lomakkeita ei ole suunniteltu näytettäviksi iFrame-kehyksissä.  
  
|Välilehti|Ominaisuus|Kuvaus|  
|---------|--------------|-----------------|  
|**Yleiset**|**Nimi**|**Pakollinen**: iFrame-kehyksen yksilöivä nimi. Nimessä voi olla vain aakkosnumeerisia merkkejä ja alaviivoja.|  
||**URL-osoite**|**Pakollinen**: iFrame-kehyksessä näytettävän sivun URL-osoite.|  
||**Siirrä tietueen objektityyppikoodi ja yksilöivät tunnukset parametreina**|iFrame-kehykseen voidaan välittää tietoja organisaatiosta, käyttäjästä ja tietueesta. Lisätietoja: [Parametrien siirtäminen iFrames-kehyksiin](iframe-properties-legacy.md#BKMK_PassParametersToIFRAMEs)|  
||**Otsikko**|**Pakollinen**: iFrame-kehyksessä näytettävä otsikko.|  
||**Näytä otsikko lomakkeessa**|Valitaan, näytetäänkö otsikko.|  
||**Rajoita kehysten väliset komentosarjat silloin, kun sitä tuetaan**|Yhteyden muodostamista toisen sivuston sivuista Dynamics 365 -sovellukseen komentosarjojen avulla pidetään tietoturvariskinä. Voit rajoittaa tällä asetuksella kehysten välisiä komentosarjoja sivuilla, joita et hallitse.<br /><br />|  
||**Oletusarvoisesti näkyvissä**|iFrame-kehyksen näyttäminen on valinnaista, ja sitä voidaan hallinta komentosarjoilla. Lisätietoja: [Näkyvyysasetukset](visibility-options-legacy.md)|
||**Ota käyttöön mobiililaitteissa**|Ota mobiililaitteiden iFrame käyttöön valitsemalla valintaruutu.|  
|**Muotoilu**|**Valitse sarakkeiden määrä ohjausobjektia varten**|Kun iFrame-kehyksiä sisältävässä osassa on useita sarakkeita, voit määrittää kentän käyttämään enintään saman määrän sarakkeita kuin osassa on.|  
||**Valitse ohjausobjektin viemien rivien määrä**|Voit hallita iFrame-kehyksen korkeutta määrittämällä, kuinka monta riviä ohjausobjekti käyttää.|  
||**Laajenna automaattisesti käytettävissä olevaan tilaan**|Sen sijaan että korkeus määritettäisiin rivien määrän perusteella, voit sallia iFrame-kehyksen laajentumisen käytettävissä olevaan tilaan.|  
||**Valitse iFrame-kehyksen selaustapa**|Käytössä on kolme vaihtoehtoa:<br /><br /> - **Tarpeen mukaan**: näytä vierityspalkit, kun iFrame on suurempi kuin käytettävissä oleva tila.<br />- **Aina**: näytä vierityspalkit aina.<br />- **Ei koskaan**: älä näytä vierityspalkkeja koskaan.|  
||**Näytä reunaviiva**|Näytä reunaviivat iFrame-kehyksen ympärillä.|  
|**Riippuvuudet**|**Alisteiset kentät**|iFrame voi olla yhteydessä lomakkeen kenttiin komentosarjojen avulla. Jos kenttä poistetaan lomakkeesta, iFrame-kehyksen komentosarja voi katketa. Lisää kentät, joihin komentosarjat viittaavat iFrame-kehyksissä, **alisteisiin kenttiin**, jotta niitä ei voi poistaa vahingossa.|  
  
## <a name="pass-parameters-to-iframes"></a> Parametrien välittäminen iFrame-kehyksiin  
 Tietuetta koskevat tiedot voidaan välittää ottamalla **Siirrä tietueen objektityyppikoodi ja yksilöllinen tunnus parametreina** -asetus käyttöön. Välitetyt arvot:  
  
|Parametri|Kuvaus|  
|---------------|-----------------|  
|`orglcid`|Organisaation oletuskielen LCID-tunnus.|  
|`orgname`|Organisaation nimi.|  
|`userlcid`|Käyttäjän ensisijaisen kielen LCID-tunnus|  
|`type`|Entiteetin tyyppikoodi. Tämä arvo voi olla erilainen eri organisaatioiden mukautetuissa entiteeteissä. Käytä sen sijaan `typename`-parametria.|  
|`typename`|Entiteettityypin nimi.|  
|`id`|Tietueen tunnusarvo. Tällä parametrilla ei ole arvoa, ennen kuin entiteettitietue on tallennettu.|  

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)
