---
title: Nykyisen tietueen välittäminen tietokontekstina upotettuun kaaviosovellukseen | MicrosoftDocs
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
author: Aneesmsft
ms.author: matp
manager: kvivek
tags:
  - PowerApps maker portal impact
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="pass-the-current-record-as-data-context-to-an-embedded-canvas-app"></a>Nykyisen tietueen välittäminen tietokontekstina upotettuun kaaviosovellukseen
Tässä ohjeaiheessa käsitellään upotetun kaaviosovelluksen lisäämistä ja nykyisen (päälomakkeen) tietueen välittämistä tietokontekstina upotettuun kaaviosovellukseen.

> [!NOTE]
> Tämä ominaisuus on käytettävissä vain esiversiona. <br />
> [!INCLUDE [cc-preview-features-definition](../../includes/cc-preview-features-definition.md)] 

Oletetaan, että haluat lisätä kaaviosovelluksen asiakkaan päälomakkeeseen ja välittää nykyisen asiakastietueen upotettuun kaaviosovellukseen. Voit tehdä tämän seuraavasti: 

1.  Kirjaudu [PowerAppsiin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) ja avaa entiteetin päälomakkeen lomake-editori. Kyse voi olla vaikkapa asiakasentiteetistä. 
2.  Valitse lomakkeessa osa, jossa haluat upotetun kaaviosovelluksen näkyvän.
3.  Lisää kenttien hallintaruudussa pakollinen kenttä, kuten **Asiakkaan nimi**.
      > [!IMPORTANT]
      > Käytä aina pakollista kenttää, sillä siinä on varmasti arvo. Jos kentässä ei ole arvoa, upotettu kaaviosovellus ei päivity, kun mallipohjaisen isäntälomakkeen tiedot muuttuvat.
4.  Kun kenttä on valittu, valitse ensin **Aloitus**-välilehti **Muokkaa**-ryhmässä ja sitten **Muuta ominaisuuksia**.
5.  Valitse **Kentän ominaisuudet** -valintaikkunassa **Ohjausobjektit**-välilehti.
6.  Valitse **Ohjausobjektit**-välilehdessä **Lisää ohjausobjekti...**.
7.  Valitse **Lisää ohjausobjekti** -valintaikkunan käytettävissä olevien ohjausobjektien luettelossa ensin **Kaaviosovellus** ja sitten **Lisää**.
8.  Valitse **Kentän ominaisuudet** -valintaikkunan ohjausobjektiluettelossa ensin **Kaaviosovellus** ja sitten **Verkko**-asetus.
9.  Ohjausobjektiluettelon alla olevassa osassa on luettelo ominaisuuksista, jotka ovat kaaviosovelluksen ohjausobjektin käytettävissä.
     - **Entiteetin nimi** -ominaisuus määrittää entiteetin, josta saadaan tiedot upotettuun kaaviosovellukseen. Nimeksi valitaan entiteetti, joka sisältää aiemmassa vaiheessa lisätyn kentän.
         - Huomaa, että vaikka tämä ominaisuus näyttäisi olevan muutettavissa, sen muuttaminen ei vaikuta upotettuun kaaviosovellukseen. Se on tarkoitettu vain viitteeksi käyttäjälle.
     - **Sovelluksen tunnus** -ominaisuus määrittää upotetun kaaviosovelluksen tunnuksen. Se luodaan ja täytetään automaattisesti puolestasi kaaviosovellusta luotaessa.
         - Huomaa, että **Sovelluksen tunnus** -arvon muuttaminen katkaisee linkin mallipohjaisesta lomakkeesta upotettuun kaaviosovellukseen.
10. Luo kaaviosovellus tai muokkaa sitä valitsemalla **Mukauta**. PowerApps Studio avautuu nyt uuteen välilehteen.
       > [!NOTE]
       > Jos selaimen ponnahdusikkunan estotoiminto estää PowerApps Studion avaamisen, web.powerapps.com on otettava käyttöön tai ponnahdusikkunoiden estotoiminto on poistettava tilapäisesti käytöstä, ja **Mukauta** on valittava uudelleen.
11. Huomaa, että PowerApps Studion vasemmassa ruudussa on erityinen **ModelDrivenFormIntegration**-ohjausobjekti. Tämä ohjausobjekti tuo kontekstitiedot mallipohjaisesta lomakkeesta upotettuun kaaviosovellukseen.
12. Valitse **Gallery1**-ohjausobjekti. Huomaat, että **Kohteet**-ominaisuudeksi on määritetty **ModelDrivenFormIntegration.Data**.
      > [!NOTE]
      > ModelDrivenFormIntegration.Data on tietueluettelo. Tässä esimerkissä siinä on vain yksi tietue. Voit viitata suoraan tietueeseen käyttämällä First-funktiota. Esimerkki: *First(ModelDrivenFormIntegration.Data).Name*.
13. Valitse oikeassa ominaisuusruudussa **Kentät**-kohdan vieressä **Muokkaa**.
14. Vaihda tietoruudussa **Title1**-ohjausyksikköön yhdistetyksi kentäksi **Nimi** tai jokin muu kenttä, jossa on tietoja.
15. Huomaa, että valikoimassa näkyvät tiedot on välitetty valikoimaan mallipohjaisesta lomakkeesta ModelDrivenFormIntegration-ohjausobjektin kautta. Sulje tietoruutu.
16. Valitse ensin **Tiedosto**-väliehti ja sitten **Sovelluksen asetukset**.
17. Määritä **Lisäasetukset**-välilehden **Kokeelliset toiminnot** -osassa **Ota sovelluksen upotuskäyttökokemus käyttöön** -asetukseksi **Käytössä**.
18. Valitse **Tallenna**. 
19. Valitse **Pilvi**-välilehti. Anna sovellukselle yksilöivä nimi ja valitse sitten alhaalla oikealla **Tallenna**. Huomaa seuraavat asiat: 
    -  Sovellus julkaistaan automaattisesti, kun se tallennetaan ensimmäisen kerran.
      -  Kun sovellus tallennetaan jatkossa, muutokset ovat käytettävissä, kun valitse ensin **Julkaise** ja sitten **Julkaise tämä versio**.
20. Valitse valikossa **Takaisin** ja valitse sitten selainvälilehti, jossa on lomake-editori on avoinna. Huomaa, että kaaviosovelluksen ohjausobjektin **Sovelluksen tunnus** -ominaisuudessa on nyt arvo. Huomaa seuraavat asiat: 
    -   Lomake-editorista on suora linkki PowerApps Studioon, joka avattiin aiemmassa vaiheessa toisessa selainvälilehdessä.
    -   Lomake-editori tarkkailee siihen lähetettävää **sovelluksen tunnusta**.
    -   **Sovelluksen tunnus** lähetetään lomake-editoriin, kun sovellus tallennetaan.
21. Valitse **Kentän ominaisuudet** -valintaikkunassa **Näytä**-välilehti.
22. Tyhjennä **Näytä otsikko lomakkeessa** ja valitse sitten **OK**.
    -   Jos tähän lomakkeeseen on jo upotettu kaaviosovellus, saat seuraavan ilmoituksen: Lomakkeessa voidaan ottaa käyttöön vain yksi pohjasovellus. Uuden kaaviosovelluksen lisääminen edellyttää, että ensin [nykyinen upotettu kaaviosovellus poistetaan käytöstä](embedded-canvas-app-guidelines.md#disable-an-embedded-canvas-app). Sen jälkeen [uusi upotettu kaaviosovellus voidaan ottaa käyttöön](embedded-canvas-app-guidelines.md#enable-an-embedded-canvas-app).
23. Valitse **Aloitussivu**-välilehdessä ensin **Tallenna** ja sitten **Julkaise**.

Kun olet lisännyt upotetun kaaviosovelluksen mallipohjaiseen lomakkeeseen, voit jakaa sen muiden käyttäjien kanssa. Lisätietoja: [Upotetun kaaviosovelluksen jakaminen](share-embedded-canvas-app.md).

Kun käyttäjät avaavat mallipohjaisen sovelluksen (vain Unified Interface), joka sisältää muokatun lomakkeen, he näkevät upotetun kaaviosovelluksen lomakkeessa. Päälomakkeessa näkyvän tietueen muuttaminen muuttaa lomakkeeseen välitettyä tietokontekstia ja upotettu sovellus päivittyy näyttämään kyseiset tiedot.

Tässä ohjeaiheessa käsiteltiin, miten pääset alkuun kaaviosovelluksen upottamisessa mallipohjaiseen lomakkeeseen. Voit mukauttaa upotettua kaaviosovellusta entisestään yhdistämällä sen erilaisiin tietolähteisiin tuomaan niistä tietoja. Voit suodattaa ja etsiä tiettyjä tietueita kyseisistä tietolähteistä käyttämällä Filter-, Search- ja LookUp-funktioita sekä mallipohjaisesta isäntälomakkeesta välitettyä kontekstia. WYSIWYG-kaaviosovelluseditorin avulla on helppo suunnitelma tarpeita vastaava käyttöliittymä.

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Liittyvien tietueiden luettelon välittäminen tietokontekstina upotettuun kaaviosovellukseen](pass-related-embedded-canvas-app.md) <br />
[Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa](embedded-canvas-app-actions.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md) <br />
[Upotettujen kaaviosovellusten käsittelyohjeita](embedded-canvas-app-guidelines.md)
