---
title: Upotetun kaaviosovelluksen lisääminen malliin perustuvaan lomakkeeseen | MicrosoftDocs
ms.custom: ''
ms.date: 06/25/2019
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

# <a name="add-an-embedded-canvas-app-on-a-model-driven-form"></a>Upotetun kaaviosovelluksen lisääminen malliin perustuvaan lomakkeeseen.
Tässä ohjeaiheessa kerrotaan, miten uusi kaaviosovellus voidaan upottaa mallipohjaiseen lomakkeeseen.

Kuvittele, että haluat luoda uuden kaaviosovelluksen ja upottaa sen päälomakkeeseen Asiakkuudet-entiteetille. Voit tehdä tämän seuraavasti: 

1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.
2.  [Luo tai muokkaa entiteetin päälomaketta](create-and-edit-forms.md), esimerkiksi Asiakkuus-entiteettiä. 
3.  Avaa lomake perinteisessä lomakkeen suunnitteluohjelmassa valitsemalla komentoriviltä **Vaihda perinteiseen**.
4.  Valitse perinteisessä suunnitteluohjelmassa lomakkeessa osa, jossa haluat upotetun kaaviosovelluksen näkyvän.
5.  Lisää kenttäruudussa pakollinen kenttä, kuten **Asiakkaan nimi**.
      > [!IMPORTANT]
      > Käytä aina pakollista kenttää, sillä siinä on varmasti arvo. Jos kentässä ei ole arvoa, upotettu kaaviosovellus ei päivity, kun mallipohjaisen isäntälomakkeen tiedot muuttuvat.
6.  Kun kenttä on valittu, valitse ensin **Aloitus**-välilehti **Muokkaa**-ryhmässä ja sitten **Muuta ominaisuuksia**.
7.  Valitse **Kentän ominaisuudet** -valintaikkunassa **Ohjausobjektit**-välilehti.
8.  Valitse **Ohjausobjektit**-välilehdessä **Lisää ohjausobjekti**.
9.  Valitse **Lisää ohjausobjekti** -valintaikkunan käytettävissä olevien ohjausobjektien luettelossa ensin **Kaaviosovellus** ja sitten **Lisää**.
10. Valitse **Kentän ominaisuudet** -valintaikkunan ohjausobjektiluettelossa ensin **Kaaviosovellus** ja sitten **Verkko**-asetus.
11. Ohjausobjektiluettelon alla olevassa osassa on luettelo ominaisuuksista, jotka ovat kaaviosovelluksen ohjausobjektin käytettävissä.
     - **Entiteetin nimi** -ominaisuus määrittää entiteetin, josta saadaan tiedot upotettuun kaaviosovellukseen. Nimeksi valitaan entiteetti, joka sisältää aiemmassa vaiheessa lisätyn kentän.
         - Huomaa, että vaikka tämä ominaisuus näyttäisi olevan muutettavissa, sen muuttaminen ei vaikuta upotettuun kaaviosovellukseen. Se on tarkoitettu vain viitteeksi käyttäjälle.
     - **Sovelluksen tunnus** -ominaisuus määrittää upotetun kaaviosovelluksen tunnuksen. Se luodaan ja täytetään automaattisesti puolestasi kaaviosovellusta luotaessa.
         - Huomaa, että **Sovelluksen tunnus** -arvon muuttaminen katkaisee linkin mallipohjaisesta lomakkeesta upotettuun kaaviosovellukseen.
12. Luo kaaviosovellus tai muokkaa sitä valitsemalla **Mukauta**. PowerApps Studio avautuu nyt uuteen välilehteen.
       > [!NOTE]
       > Jos selaimen ponnahdusikkunan estotoiminto estää PowerApps Studion avaamisen, web.powerapps.com on otettava käyttöön tai ponnahdusikkunoiden estotoiminto on poistettava tilapäisesti käytöstä, ja **Mukauta** on valittava uudelleen.
13. Huomaa, että PowerApps Studion vasemmassa ruudussa on erityinen **ModelDrivenFormIntegration**-ohjausobjekti. Tämä ohjausobjekti tuo kontekstitiedot mallipohjaisesta lomakkeesta upotettuun kaaviosovellukseen.
14. Ota huomioon, että [kaaviosovelluksen lomakeohjausobjekti](../canvas-apps/controls/control-form-detail.md) lisättiin automaattisesti upotettuun kaaviosovellukseen ja näyttää tiedot, jotka on välitetty mallipohjaisesta isäntälomakkeesta Modedrivenformintegration-ohjausobjektin kautta. 
15. Valitse **Näytä**-välilehti ja valitse sitten **Tietolähteet**. Huomaa, että mallipohjaisen lomakkeen isäntäentiteetin tietolähde, tässä tapauksessa asiakkuudet, lisättiin automaattisesti upotettuun kaaviosovellukseen.
16. Valitse **Lomake1**-ohjausobjekti. Huomaat, että **DataSource**-ominaisuudeksi on määritetty **Asiakkuudet**.
17. **Lomake1**-ohjausobjekti on edelleen valittuna. Huomaa, että **Kohde**-ominaisuudeksi on määritetty **ModelDrivenFormIntegration.Item**.
    > [!NOTE]
    > Upotetulla kaaviosovelluksella on täydet käyttöoikeudet, jotta se voidaan tallentaa mallipohjaisen lomakkeen avulla kohteen ModelDrivenFormIntegration.Item kautta. Jos esimerkiksi haluat saada kentän arvon nimellä **accountnumber** ja näyttönimellä **Tilinumero**, voit käyttää ominaisuuksia **ModelDrivenFormIntegration.Item.accountnumber** tai **ModelDrivenFormIntegration.Item.'Account Number**.
18. Valitse oikeassa ominaisuusruudussa **Kentät**-kohdan vieressä **Muokkaa kenttiä**.
19. Valitse **+ Lisää kenttä**, jos haluat lisätä toisen kentän kaaviosovelluslomakkeeseen tai järjestä aiemmin luodut kentät uudelleen vetämällä ja pudottamalla. Sulje tietoruutu, kun olet lopettanut kenttien lisäämisen ja uudelleenjärjestämisen.
20. Valitse **Tiedosto**-välilehti ja sitten **Tallenna**.
21. Valitse **Pilvi**-välilehti. Anna sovellukselle yksilöivä nimi ja valitse sitten alhaalla oikealla **Tallenna**. Huomaa seuraavat asiat: 
    -  Sovellus julkaistaan automaattisesti, kun se tallennetaan ensimmäisen kerran.
      -  Kun sovellus tallennetaan jatkossa, muutokset ovat käytettävissä, kun valitse ensin **Julkaise** ja sitten **Julkaise tämä versio**.
22. Valitse valikosta **Takaisin**.
23. Valitse selainvälilehti, jossa on perinteisen lomakkeen suunnitteluohjelma avoinna. Huomaa, että kaaviosovelluksen ohjausobjektin **Sovelluksen tunnus** -ominaisuudessa on nyt arvo.
    > [!NOTE]
    > - Lomakkeiden suunnitteluohjelmasta on suora linkki PowerApps Studioon, joka avattiin aiemmassa vaiheessa toisessa selainvälilehdessä.
    > - Lomakkeiden suunnitteluohjelma tarkkailee siihen lähetettävää sovelluksen tunnusta. 
    > - Sovelluksen tunnus lähetetään lomakkeiden suunnitteluohjelmaan, kun sovellus tallennetaan.
24. Valitse **Kentän ominaisuudet** -valintaikkunassa **Näytä**-välilehti.
25. Tyhjennä **Näytä otsikko lomakkeessa** ja valitse sitten **OK**.
    -   Jos tähän lomakkeeseen on jo upotettu kaaviosovellus, saat seuraavan ilmoituksen: Lomakkeessa voidaan ottaa käyttöön vain yksi pohjasovellus. Uuden kaaviosovelluksen lisääminen edellyttää, että ensin [nykyinen upotettu kaaviosovellus poistetaan käytöstä](embedded-canvas-app-guidelines.md#disable-an-embedded-canvas-app). Sen jälkeen [uusi upotettu kaaviosovellus voidaan ottaa käyttöön](embedded-canvas-app-guidelines.md#enable-an-embedded-canvas-app).
26. Valitse **Aloitussivu**-välilehdessä ensin **Tallenna** ja sitten **Julkaise**.

Kun olet lisännyt upotetun kaaviosovelluksen mallipohjaiseen lomakkeeseen, voit jakaa sen muiden käyttäjien kanssa. Lisätietoja: [Upotetun kaaviosovelluksen jakaminen](share-embedded-canvas-app.md).

Kun käyttäjät avaavat mallipohjaisen sovelluksen (vain Unified Interface), joka sisältää muokatun lomakkeen, he näkevät upotetun kaaviosovelluksen lomakkeessa. Päälomakkeessa näkyvän tietueen muuttaminen muuttaa lomakkeeseen välitettyä tietokontekstia ja upotettu sovellus päivittyy näyttämään kyseiset tiedot.

Tässä ohjeaiheessa käsiteltiin, miten pääset alkuun kaaviosovelluksen upottamisessa mallipohjaiseen lomakkeeseen. Voit mukauttaa upotettua kaaviosovellusta entisestään yhdistämällä sen erilaisiin tietolähteisiin tuomaan niistä tietoja. Voit suodattaa ja etsiä tiettyjä tietueita kyseisistä tietolähteistä käyttämällä Filter-, Search- ja LookUp-funktioita sekä mallipohjaisesta isäntälomakkeesta välitettyä kontekstia. WYSIWYG-kaaviosovelluseditorin avulla on helppo suunnitelma tarpeita vastaava käyttöliittymä.

## <a name="see-also"></a>Katso myös
[Kaaviosovelluksen upottaminen mallipohjaiseen lomakkeeseen](embed-canvas-app-in-form.md) <br />
[Upotetun kaaviosovelluksen muokkaaminen malliin perustuvaan lomakkeeseen](embedded-canvas-app-edit-classic-designer.md) <br />
[Mallin mukaiseen lomakkeeseen upotetun kaaviosovelluksen näytön koon ja suunnan mukauttaminen](embedded-canvas-app-customize-screen.md) <br />
[Ennalta määritettyjen toimintojen suorittaminen upotetun kaaviosovelluksen isäntälomakkeessa](embedded-canvas-app-actions.md) <br />
[ModelDrivenFormIntegration-ohjausobjektin ominaisuudet ja toiminnot](embedded-canvas-app-properties-actions.md) <br />
[Upotetun sovelluksen jakaminen](share-embedded-canvas-app.md) <br />
[Upotettujen kaaviosovellusten käsittelyohjeita](embedded-canvas-app-guidelines.md) <br />
[Upotettujen kaaviosovellusten siirtäminen mallipohjaisista lomakkeista, jotka on luotu julkista esikatseluversiota käyttäen uusimpaan](embedded-canvas-app-migrate-from-preview.md) <br />
