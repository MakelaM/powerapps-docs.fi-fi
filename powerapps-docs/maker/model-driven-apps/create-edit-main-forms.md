---
title: Mallipohjaisen sovelluksen päälomakkeiden luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Tietoja päälomakkeen luomisesta tai muokkaamisesta.
ms.custom: ''
ms.date: 05/23/2018
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
ms.assetid: <needs new guid>
caps.latest.revision: 18
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="create-or-edit-a-model-driven-app-main-form-for-an-entity"></a>Entiteetin mallipohjaisen sovelluksen päälomakkeen luominen tai muokkaaminen 

Tässä ohjeaiheessa on tietoja siitä, entiteetin päälomake luodaan ja miten sitä muokataan.

Entiteetille luodun uuden lomakkeen lomaketyyppi on Ensisijainen. Kun uusi lomake avataan ensimmäisen kerran, se on samanlainen kuin lomake nimeltä Tieto. Voit lisätä tai muokata kenttiä, osia, välilehtiä ja siirtymistoimintoja sekä lomakkeeseen liittyviä ominaisuuksia että tallentaa lomakkeen.

Jokaisessa päälomakkeessa on vähintään yksi välilehti. Kussakin välilehdessä voi olla yksi tai useampi osa. Kussakin osassa voi puolestaan olla yksi tai useampi kenttä tai IFRAME-kehys. Jos haluat luoda uuden lomakkeen aiemmin luodun lomakkeen pohjalta, voit kloonata lomakkeen. 

Varmista, että sinulla on Järjestelmänvalvoja- tai Järjestelmän mukauttaja -käyttöoikeusrooli tai vastaavat käyttöoikeudet, jotta voit suorittaa tämän tehtävän.

## <a name="how-to-create-or-edit-a-main-form"></a>Päälomakkeen luominen tai muokkaaminen
  
1.   Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.


> [!IMPORTANT]
> Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).   
  
2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti. 

3. Jos haluat luoda uuden päälomakkeen, valitse työkaluriviltä **Lisää lomake** > **Päälomake**.  
    \-Vaihtoehtoisesti voit muokata olemassa olevaa päälomaketta valitsemalla minkä tahansa **lomakkeen**, joka on **Päälomake**.
  
3.  Muuta lomakkeen rakennetta millä tahansa seuraavista tavoista tarpeen mukaan:
    -   Välilehden lisääminen lomakkeeseen
    -   Osan lisääminen lomakkeeseen
    -   Kentän lisääminen lomakkeeseen
    -   Lomakkeen IFRAME-kehyksen lisääminen tai muokkaaminen
    -   Lomakkeella olevan aliruudukon muokkaaminen tai lisääminen
    -   Lomakkeen WWW-resurssin lisääminen ja muokkaaminen
    -   Lomakkeen siirtymisruudun lisääminen liittyviin entiteetteihin tai siirtymisruudun muokkaaminen
    -   Lomakkeen ylä- ja alatunnisteiden muokkaaminen
    -   Välilehden, osan, kentän tai IFRAME-kehyksen poistaminen
    -   Lomakeavustajan ottaminen käyttöön tai poistaminen käytöstä
    
4.  Muokkaa lomakkeen osien ominaisuuksia tarpeen mukaan:
    -   Lomakkeen ominaisuuksien muokkaaminen
    -   Lomakkeen kenttäominaisuuksien muokkaaminen
    -   Välilehden ominaisuuksien muokkaaminen
    -   Osan ominaisuuksien muokkaaminen

5.  Lisää tapahtumakomentosarjoja tarpeen mukaan. 

6.  Määritä käyttöoikeusroolit, joilla on lomakkeen tarkasteluoikeus. Lisätietoja: [Käyttöoikeusroolien määrittäminen lomakkeelle](https://docs.microsoft.com/dynamics365/customer-engagement/admin/assign-security-roles-form)

7.  Esikatsele päälomakkeen ulkoasua ja tapahtumien suorittamista:
    - Valitse **Aloitussivu**-välilehdessä ensin **Esikatsele** ja sitten **Luo lomake**, **Päivitä lomake** tai **Vain luku -lomake**.
    - Sulje esikatselulomake valitsemalla **Tiedosto**-valikossa **Sulje**.

8.  Kun olet tehnyt lomakkeeseen haluamasi muutokset, valitse **Tallenna nimellä**. Kirjoita lomakkeen nimi ja valitse **OK**.

9.  Kun olet tehnyt haluamasi mukautukset, julkaise ne:
    -   Jos haluat julkaista mukautuksen vain osalle, jota juuri muokkaat, napsauta siirtymisruudun siirtymispalkissa muokkaamaasi entiteettiä kohdassa **Osat**, ja napsauta sitten **Julkaise**.
    -   Jos haluat julkaista kaikkien julkaisemattomien komponenttien mukautukset yhtä aikaa, napsauta **Osat**-kohdassa **Entiteetit** ja sitten komentopalkissa **Julkaise kaikki mukautukset**.
    
 
### <a name="next-steps"></a>Seuraavat vaiheet  
[Lomake-editorin käyttöliittymän yleiskatsaus](form-editor-user-interface-legacy.md)
 
