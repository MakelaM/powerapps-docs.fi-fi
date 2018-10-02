---
title: Tarkistaa ja julkaista mallin perustuva sovellus sovellusten suunnitteluohjelman avulla | MicrosoftDocs
description: 'Tietoja siitä, miten voit tarkistaa ja julkaista malliin perustuva sovelluksen'
keywords: ''
ms.date: 06/08/2018
ms.service: crm-online
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: 5a9ec120-9ddc-4d92-b48c-0fee8c57d3c3
ms.author: matp
manager: kvivek
ms.reviewer: null
ms.suite: null
ms.tgt_pltfrm: null
caps.latest.revision: 10
topic-status: Drafting
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="validate-and-publish-a-model-driven-app-using-the-app-designer"></a>Mallipohjaisen sovelluksen tarkistaminen ja julkaiseminen sovellusten suunnitteluohjelman avulla

Sovellusta tarkistettaessa tarkistetaan sovelluksen toiminnan kannalta välttämättömät resurssien riippuvuudet, joita ei ole vielä lisätty sovellukseen. Kun tarkistus on tehty, voit julkaista sovelluksen. 
  
Ajatellaan, että olet lisännyt sovellukseen Customer Service -suorituskyvyn koontinäytön, joka käyttää Palvelupyyntöyhdistelmä (prioriteetin mukaan)- tai Palvelupyyntöjen ratkaisutrendi (päivän mukaan) -kaavioita, joita et ole lisännyt. Kun tarkistat tämän sovelluksen, saat tuloksena puuttuvien ja pakollisten resurssien luettelon.  
  
Kun tarkistat sovelluksen, sovelluksen suunnitteluohjelman pohja sisältää tiedot puuttuvista resursseista.  
  
1.  Valitse sovelluksen suunnitteluohjelmassa **Tarkista**.  
  
     Näyttöön tulee ilmoituspalkki, jossa näkyvät sovelluksen virheet ja varoitukset. Ilmoituspalkissa näkyvät varoitukset esimerkiksi tilanteista, joissa entiteetillä ei ole lomakkeita tai näkymiä tai sovelluksella ei ole yhtään komponentteja. Virhesanoma voi tulla näkyviin, jos sovellukselle ei ole määritetty sivustokarttaa. Voit julkaista sovelluksen, vaikka varoituksia ei käsiteltäisi, mutta virheet on korjattava ennen julkaisua.  
  
     ![Ilmoituspalkki, joka näyttää varoituksia sovelluksessa](media/app-designer-warning-notification.png "Ilmoituspalkki, joka näyttää varoituksia sovelluksessa")  
  
     Sovelluksen suunnitteluohjelmassa näkyy myös varoituskuvake ja kunkin sellaisen artefaktin tai resurssiruudun riippuvuuksien määrä, joista puuttuu pakollinen resurssi.  
  
     ![Puuttuvan komponentin varoitus suunnitteluohjelman ruudussa](media/warning--button-on-app-designer-tile.png "Puuttuvan komponentin varoitus suunnitteluohjelman ruudussa")  
  
2.  Voit lisätä pakolliset resurssit valitsemalla kaavion oikealla puolella olevan **Pakollinen**-välilehden. **Pakollinen**-välilehti on näkyvissä, kun sovelluksesta puuttuu vähintään yksi pakollinen resurssi.  
  
     Välilehti sisältää pakollisten komponenttien luettelon.  
  
     ![Pakollinen välilehti, jossa näkyy puuttuvien sovellusten luettelo](media/app-designer-required-components-tab.png "Pakollinen välilehti, jossa näkyy puuttuvien sovellusten luettelo")  
  
3.  Valitse resurssit, jotka haluat lisätä, ja valitse sitten **Lisää riippuvuudet**. Kun pakollinen resurssi on lisätty ruutuun, ruudun määrää pienennetään.  
  
    > [!NOTE]
    >  Jos erilaisissa sovellusosissa tarvitaan yhteistä resurssia, kun vaikkapa lomake tarvitaan että koontinäytössä että entiteetissä, ja lisäät kyseisen resurssin vain kerran koontinäytön riippuvuuspuusta, riippuvuusmäärä vähenee vain koontinäytön ruudussa mutta ei entiteetin ruudussa. Riippuvuus kuitenkin ratkaistaan molempien ruutujen osalta.  
    >   
    >  Valitse **Hae viimeisimmät riippuvuudet** -painike ![Hae viimeisimmät riippuvuudet -painike sovellusten suunnitteluohjelmassa](media/app-designer-get-latest-dependencies.png "Hae viimeisimmät riippuvuudet -painike sovellusten suunnitteluohjelmassa") tai valitse **Vahvista** uudelleen, jos haluat riippuvuuksien uusimman joukon. Sovelluksen tallentamisen jälkeen näkyvissä ovat vain nämä painikkeet.  
  
     Valitse**Piilota riippuvuudet**, jos et halua lisätä ehdotettuja pakollisia komponentteja. Kaikki ratkaisemattomat varoitukset näkyvät uudelleen, kun avaat sovelluksen sovelluksen suunnitteluohjelmassa ja painat **Vahvista** tai **Hae viimeisimmät riippuvuudet** painiketta ![Hae viimeisimmät riippuvuudet -painike sovelluksen suunnitteluohjelmassa](media/app-designer-get-latest-dependencies.png "Hae viimeisimmät riippuvuudet -painike sovelluksen suunnitteluohjelmassa").  
  
    > [!NOTE]
    >  Jos piilotat riippuvuudet nyt ja haluat myöhemmin viedä tämän sovelluksen, kaikki kyseiset riippuvuudet tulevat uudelleen näkyviin.  
  
## <a name="publish-an-app-using-the-app-designer"></a>Julkaise sovellus sovellusten suunnitteluohjelman avulla

Julkaise sovellus, jotta se on muiden käyttäjien käytettävissä.  
  
 Kun olet lisännyt komponentit sekä tarkistanut ja tallentanut sovelluksen, valitse komentopalkissa **Julkaise**. Voit julkaista sovelluksen myös [Omat sovellukset](advanced-navigation.md#my-apps) -sivun sovellusruudusta. Valitse **Muokattavat sovellukset** -näkymän julkaistava sovelluksen ruudun oikeasta alakulmasta **Lisää vaihtoehtoja** -painike (**...**). Valitse sitten **Julkaise.**.  
  
 Sovelluksen tilaksi tulee Julkaistu. Tila näkyy sovelluksen suunnitteluohjelman oikeassa yläkulmassa. Sovellus siirtyy **Muokattavat sovellukset** -näkymästä **Julkaistut sovellukset** -näkymään. Julkaisupäivämäärä näkyy sovellusruudussa.  
  
> [!NOTE]
> - Jos sovelluksessa on tarkistusvirheitä, virhe näkyy ilmoituspalkissa. Sovelluksen voi julkaista vasta sitten, kun virhe on ratkaistu.  
> - Sovellus on tallennettava ennen julkaisemista.  

## <a name="next-steps"></a>Seuraavat vaiheet  
[Mallipohjaisen sovelluksen jakaminen PowerAppsin avulla](https://docs.microsoft.com/powerapps/maker/model-driven-apps/share-model-driven-app) <br/>
 [Mallipohjaisen sovelluksen käyttäminen mobiililaitteessa](https://docs.microsoft.com/powerapps/user/run-app-client-model-driven)   
 
