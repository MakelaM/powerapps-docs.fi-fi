---
title: Mallipohjaisen sovelluksen lomakkeen siirtymisruudun lisääminen liittyviin entiteetteihin PowerAppsissa | MicrosoftDocs
descriptoin: Learn how to add form navigation for related entities
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
  - PowerApps
author: Mattp123
ms.assetid: b4098c96-bce1-4f57-804f-8694e6254e81
caps.latest.revision: 15
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="add-model-driven-app-form-navigation-for-related-entities"></a>Mallipohjaisen sovelluksen lomakkeen siirtymisruudun lisääminen liittyviin entiteetteihin

Tässä ohjeaiheessa käytetään lomakkeen siirtymisruutua. Sen avulla lisätään liittyvien entiteettien linkit. Kun sovelluksen käyttäjä napsauttaa jotakin linkkiä tietueessa, näkyviin tulee entiteetin liitetty näkymä.   
  
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  

  
    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment). 

2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti. 
  
3.  Avaa luettelossa **päälomake** muokkaamista varten.  
  
4.  Voit lisätä linkin liittyvään entiteettiin valitsemalla **Etusivu**-välilehden **Valitse**-ryhmästä **Siirtyminen**.  
  
     **Suhteidenhallinta**-ruutu näkyy lomake-editorin oikeassa reunassa.  
  
5.  Valitse **Suhteidenhallinta** -ruudun **Suodatin**-luettelosta jokin seuraavista vaihtoehdoista:  
  
    - **Käytettävissä olevat suhteet**. Näyttää kaikki kohteet, jotka voidaan liittää lomakkeeseen, johon on liitetty entiteetti.  
  
    - **N:1-suhteet** Näyttää kaikki kohteet, jotka voidaan liittää 1:N-suhteessa entiteettiin, johon on liitetty lomake.  
  
    - **N:N-suhteet** Näyttää kaikki kohteet, jotka voidaan liittää N:N-suhteessa entiteettiin, johon on liitetty lomake.  
  
    > [!NOTE]
    >  Jos liittyviä entiteettejä ei näy **Suhteidenhallinta**-ruudussa, et voi luoda linkkiä tässä lomakkeessa liittyvään entiteettiin.  
  
6.  Valitse liittyvä entiteetti, johon haluat linkittää, vedä se siirtymisruutuun ja pudota se sitten kohtaan, jossa haluat sen näkyvän.  
  
    > [!TIP]
    >  Voit luoda uuden suhteen myös valitsemalla **Uusi 1:N** tai **Uusi N:N** **Suhteidenhallinta**-ruudussa.   
  
7. Jos haluat muokata tätä tai jotakin toista siirtymisruudussa olevaa liittyvän entiteetin linkkiä, valitse linkki ja valitse sitten **Etusivu**-välilehdestä **Vaihda ominaisuuksia**.  
  
8. Kirjoita uusi näyttöotsikko **Suhteen ominaisuudet** -valintaikkunan **Näyttö**-välilehteen.  
  
9. Valitse **Nimi**-välilehdellä **Muokkaa** ja tarkastele tai muokkaa tietoja, jotka liittyvät suhteen tietueeseen.  
  
10. Valitse **OK**.  
  
11. Esikatsele päälomakkeen ulkoasua ja tapahtumien suorittamista:  
  
    1.  Valitse **Etusivu**-välilehdestä **Esikatsele** ja valitse sitten **Luo lomake**, **Päivitä lomake** tai **Vain luku -lomake**.  
  
    2.  Sulje **Esikatsele**-lomake valitsemalla **Tiedosto**-valikosta **Sulje**.  
  
12. Kun olet tehnyt lomakkeeseen haluamasi muutokset, sulje lomake valitsemalla **Tallenna ja sulje**.  
  
13. Kun olet tehnyt haluamasi mukautukset, julkaise ne:  
  
    -   Jos haluat julkaista mukautuksen vain osalle, jota juuri muokkaat, valitse siirtymisruudun siirtymispalkissa muokkaamaasi entiteettiä, ja valitse sitten **Julkaise**.  
  
    -   Jos haluat julkaista kaikkien julkaisemattomien osien mukautukset yhtä aikaa, valitse siirtymisruudussa **Entiteetit** ja valitse sitten komentopalkissa **Julkaise kaikki mukautukset**.  
  
> [!NOTE]
> Ratkaisun asentaminen tai mukautusten julkaiseminen saattaa häiritä järjestelmän normaalikäyttöä. Suosittelemme, että ajoitat ratkaisun tuonnin ajankohtaan, jolloin siitä on vähiten häiriötä käyttäjille.
  
## <a name="next-steps"></a>Seuraavat vaiheet  
 [Common Data Service sovelluksille -ratkaisun entiteettisuhteiden luominen ja muokkaaminen](../common-data-service/create-edit-entity-relationships.md)
