---
title: Ylätunnisteen ominaisuuksien määrittäminen lomakkeiden suunnitteluohjelmassa | MicrosoftDocs
ms.custom: ''
ms.date: 08/02/2019
ms.reviewer: ''
ms.service: crm-online
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

# <a name="configure-header-properties-in-the-form-designer"></a>Ylätunnisteen ominaisuuksien määrittäminen lomakkeiden suunnitteluohjelmassa
Tekijät voivat hallinnoida mallipohjaisen sovelluksen lomakkeen ylätunnisteiden tiheyttä niin, että se vastaa lomaketta käyttävien käyttäjien tarpeita.

## <a name="high-density-header"></a>Suuren tiheyden ylätunniste
Suuren tiheyden lomakkeen ylätunniste varmistaa, että tärkeät tiedot näkyvät käyttäjille aina. Jos käytössä on suuren tiheyden ylätunniste, tietueen otsikkoa ei koskaan katkaista. Jopa pitkät tietueiden otsikot näytetään. Niissä käytetään useita rivejä. Suuren tiheyden ylätunniste myös varmistaa, että enintään neljän kentän arvot näkyvät suoraan ylätunnisteessa. Niitä ei koskaan katkaista eikä piiloteta.  

Jotta tärkeiden tietojen näkyminen varmistetaan, kehys näyttää vain luku -kenttien arvot eivätkä käyttäjät voi muokata kenttien arvoja suoraan ylätunnisteessa. Visualisoinnit, kuten mukautetut ohjausobjektit ja verkkoresurssit, eivät myöskään ole sallittuja.

Kun lomake ei määritä ylätunnisteen tiheyttä tai kun uusi lomake luodaan, kehyksessä käytetään suuren tiheyden ylätunnisteen oletusarvoja.

> [!div class="mx-imgBorder"] 
> ![Suuren tiheyden lomakkeen ylätunniste](media/form-header-high-density.png "Suuren tiheyden lomakkeen ylätunniste")
    
## <a name="low-density-header"></a>Pienen tiheyden ylätunniste
Pienen tiheyden lomakkeen ylätunnisteen avulla käyttäjät voivat muokata kenttien arvoja suoraan ylätunnisteessa. Se sallii myös visualisoinnit, kuten mukautetut ohjausobjektit ja verkkoresurssit.  
  
Tämän vuoksi tärkeät tiedot voidaan katkaista, eivätkä ne välttämättä ole näkyvissä. Pienen tiheyden ylätunniste katkaisee tietueen otsikon sekä ylätunnisteessa näkyvien kenttien arvot. Usein ylätunnisteessa on näkyvissä vain yksi kenttä tai kaksi kenttää. Muut kentät määritetään ylivuotoon. Ne näkyvät pikaikkunassa, jonka saa näkyviin ylimääräisellä napsautuksella.

> [!div class="mx-imgBorder"] 
> ![Pienen tiheyden lomakkeen ylätunniste](media/form-header-low-density.png "Pienen tiheyden lomakkeen ylätunniste")

### <a name="configuring-header-density"></a>Ylätunnisteen tiheyden määrittäminen

Voit määrittää mallipohjaisen lomakkeen ylätunnisteen tiheyden seuraavien vaiheiden avulla.
1.  Avaa lomakkeen suunnitteluohjelma, [jos haluat luoda lomakkeen tai muokata sitä](create-and-edit-forms.md).
2.  Valitse lomakkeen ylätunniste valitsemalla ylätunniste lomakkeen esikatselussa tai käyttämällä [puunäkymää](using-tree-view-on-form.md).
3.  Valitse ominaisuusruudussa **Suuri tiheys**, jos haluat käyttää suuren tiheyden lomakkeen ylätunnistetta. Poista valinta, jos haluat käyttää pienen tiheyden lomakkeen ylätunnistetta.
4.  Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi.

> [!NOTE]
> Käytä uutta lomakkeiden suunnitteluohjelmaa. Perinteinen lomakkeiden suunnitteluohjelmassa ei voi määrittää ylätunnisteen tiheyttä.

## <a name="header-flyout"></a>Ylätunnisteen pikaikkuna
Ylätunnisteen pikaikkuna näytetään, kun käyttäjät valitsevat nuolenkärkipainikkeen lomakkeen ylätunnisteessa. Sen avulla käyttäjät voivat muokata kenttien arvoja ja näyttää visualisointeja, kuten lomakkeen ylätunnisteen mukautettuja ohjausobjekteja ja verkkoresursseja.

Ylätunnisteen pikaikkunan toiminta muuttuu ylätunnisteen tiheyden määrityksen mukaan.

### <a name="high-density-header-flyout"></a>Suuren tiheyden ylätunnisteen pikaikkuna
Suuren tiheyden lomakkeen ylätunnisteessa pikaikkuna sisältää kaikki ylätunnisteen kentät, myös ne neljä kenttää, jotka näytetään suoraan ylätunnisteessa. Kehys sisältää oletusarvoisesti ylätunnisteen pikaikkunan, kun käytössä on suuren tiheyden ylätunniste. Tekijät voivat hallinnoida ylätunnisteen pikaikkunan näkyvyyttä suuren tiheyden ylätunnisteen avulla.

> [!div class="mx-imgBorder"] 
> ![Ylätunnisteen pikaikkuna ja suuren tiheyden ylätunniste](media/form-header-flyout-high-density.png "Ylätunnisteen pikaikkuna ja suuren tiheyden ylätunniste")

### <a name="low-density-header-flyout"></a>Pienen tiheyden ylätunnisteen pikaikkuna
Pienen tiheyden lomakkeen ylätunnisteen pikaikkunassa näkyvät vain ylivuotokentät, kuten kentät, joita lomake ei voi näyttää suoraan ylätunnisteessa lomakkeen leveyden vuoksi. Ylätunnisteen pikaikkuna näytetään tai piilotetaan automaattisesti ylätunnisteen kenttien määrän ja lomakkeen leveyden perusteella. Tekijät eivät voi hallinnoida ylätunnisteen pikaikkunan näkyvyyttä, kun käytössä on pienen tiheyden ylätunniste.

> [!div class="mx-imgBorder"] 
> ![Ylätunnisteen pikaikkuna ja pienen tiheyden ylätunniste](media/form-header-flyout-low-density.png "Ylätunnisteen pikaikkuna ja pienen tiheyden ylätunniste")

### <a name="show-or-hide-the-header-flyout"></a>Ylätunnisteen pikaikkunan näyttäminen tai piilottaminen
Voit näyttää tai piilottaa mallipohjaisen lomakkeen ylätunnisteen pikaikkunan seuraavasti.

1.  Avaa lomakkeen suunnitteluohjelma, [jos haluat luoda lomakkeen tai muokata sitä](create-and-edit-forms.md).
2.  Valitse lomakkeen ylätunniste lomakkeen esikatselusta tai käytä [puunäkymää](using-tree-view-on-form.md) sen valitsemiseen.
3.  Valitse ominaisuusruudussa **Suuri tiheys**, jos haluat käyttää suuren tiheyden lomakkeen ylätunnistetta. 
4.  Valitse ominaisuusruudussa **Näytä ylätunnisteen pikaikkuna**, jos haluat näyttää ylätunnisteen pikaikkunan. Poista valinta, jos haluat piilottaa ylätunnisteen pikaikkunan.
5.  Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi.

> [!NOTE]
> - Käytä uutta lomakkeiden suunnitteluohjelmaa. Perinteinen lomakkeiden suunnitteluohjelma ei mahdollista ylätunnisteen pikaikkunan näyttämistä ja piilottamista.   
> - Ylätunnisteen pikaikkunan näkyvyyttä voi hallinnoida vain, kun käytössä on suuren tiheyden lomakkeen ylätunniste. Kun käytössä on pienen tiheyden ylätunniste, ylätunnisteen pikaikkuna näytetään tai piilotetaan automaattisesti ylätunnisteen kenttien määrän ja lomakkeen leveyden perusteella.

## <a name="form-designer-messages-related-to-form-headers"></a>Lomakkeiden suunnitteluohjelman viestit, jotka liittyvät lomakkeen ylätunnisteisiin
Kun lomakkeita muokataan uuden tai perinteisen lomakkeiden suunnitteluohjelman avulla, näkyvissä voi olla joitakin lomakkeiden ylätunnisteisiin liittyviä viestejä. Alla on tietoja kustakin viestistä ja siitä, miksi se on näkyvissä.

### <a name="weve-upgraded-your-form-to-show-a-high-density-header-that-displays-more-data-you-can-edit-this-setting-in-the-properties-of-the-header"></a>Lomake on päivitetty niin, että se näyttää enemmän tietoja sisältävän suuren tiheyden ylätunnisteen. Voit muokata tätä asetusta ylätunnisteen ominaisuuksissa. 
Tämä viesti näytetään lomakkeiden suunnitteluohjelmassa silloin, kun tekijä luo uuden päälomakkeen (mukaan lukien Tallenna nimellä -toiminto) tai muokkaa päälomaketta, jolle ei ole aiemmin määritetty ylätunnisteen tiheyttä.  
  
Kehys saa oletusarvot suuren tiheyden ylätunnisteesta. Tämä viesti auttaa tekijöitä tunnistamaan tämän toiminnan. Tekijät voivat ohittaa kehyksen oletusarvon milloin tahansa määrittämällä lomakkeen ylätunnisteen tiheyden manuaalisesti aiemmin kerrotulla tavalla.

### <a name="this-form-isnt-using-high-density-header-access-the-setting-in-the-header-properties-high-density-header-helps-display-more-data"></a>Tässä lomakkeessa ei käytetä suuren tiheyden ylätunnistetta. Muokkaa ylätunnisteen ominaisuuksien asetusta. Suuren tiheyden ylätunniste auttaa näyttämään enemmän tietoja. 
Tämä viesti näytetään lomakkeiden suunnitteluohjelmassa, kun tekijä avaa muokkausta varten päälomakkeen, jossa on käytössä pienen tiheyden ylätunniste.      
  
Tämä viesti kertoo suuren tiheyden ylätunnisteesta ja sen eduista.

### <a name="field-moved-to-header-flyout-the-header-supports-displaying-up-to-four-read-only-field-values-the-field-field-display-name-will-now-only-be-available-from-the-flyout"></a>Kenttä siirrettiin ylätunnisteen pikaikkunaan: Ylätunniste tukee enintään neljän vain luku -kentän arvon näyttämistä. Kenttä *[kentän näyttönimi]* on nyt käytettävissä vain pikaikkunassa.
Tämä viesti näytetään lomakkeiden suunnitteluohjelmassa, kun lomakkeessa on käytössä suuren tiheyden ylätunniste ja ylätunnisteen pikaikkuna on näkyvissä.  
  
Suuren tiheyden ylätunnisteessa näkyvät ensimmäisten neljän kentän vain luku -arvot. Kun tekijät lisäävät kentän ylätunnisteen neljään suosituimpaan sijaintiin, suoraan ylätunnisteessa näkyvä olemassa oleva kenttä laajenee ja näkyy vain ylätunnisteen pikaikkunassa.      
  
Tämä viesti ilmoittaa tekijälle muutoksesta ja vahvistaa toiminnon jatkamisen.

### <a name="header-field-limit-exceeded-the-header-supports-displaying-up-to-four-read-only-field-values-remove-unused-fields-to-add-more"></a>Ylätunnisteen kentän rajoitus ylitetty: Ylätunniste tukee enintään neljän vain luku -kentän arvon näyttämistä. Poista käyttämättömät kentät, jos haluat lisätä kenttiä. 
Tämä viesti näytetään lomakkeiden suunnitteluohjelmassa, kun lomakkeessa on käytössä suuren tiheyden ylätunniste ja ylätunnisteen pikaikkuna on piilotettu.  
  
Suuren tiheyden ylätunnisteessa näkyvät korkeintaan neljän kentän vain luku -arvot. Koska ylätunnisteen pikaikkuna on piilotettu, käyttäjät eivät näe lisäkenttiä.  
  
Tässä viestissä kerrotaan tekijälle, että ylätunnisteessa on jo neljä kenttää. Ylätunnisteeseen ei voi enää lisätä kenttiä, joita käyttäjät eivät näe.

### <a name="header-does-not-display-custom-components-the-header-supports-displaying-up-to-four-read-only-field-values-remove-the-custom-component-from-the-field-before-adding-it-to-the-header"></a>Ylätunniste ei näytä mukautettuja osia: Ylätunniste tukee enintään neljän vain luku -kentän arvon näyttämistä. Poista mukautettu osa kentästä, ennen kuin lisäät sen ylätunnisteeseen.  
Tämä viesti näytetään lomakkeiden suunnitteluohjelmassa, kun lomakkeessa on käytössä suuren tiheyden ylätunniste ja ylätunnisteen pikaikkuna on piilotettu.  
  
Suuren tiheyden ylätunnisteessa näkyvät kenttien vain luku -arvot. Koska ylätunnisteen pikaikkuna on piilotettu, käyttäjät eivät näe ylätunnisteen kenttiin liitettyjä mukautettuja osia.  
  
Tässä viestissä kerrotaan tekijälle, että tämä yrittää lisätä ylätunnisteeseen kenttää, johon on liitetty mukautettu osa. Tekijän on poistettava mukautettu osa ennen kentän lisäämistä ylätunnisteeseen. Näin on tehtävä, koska käyttäjät eivät voi nähdä mukautettua osaa ylätunnisteessa.

### <a name="header-displays-read-only-field-values-the-header-supports-displaying-up-to-four-read-only-field-values-to-provide-editability-to-the-user-add-the-field-to-a-section-in-the-form"></a>Ylätunnisteessa näkyvät vain luku -kentän arvot: Ylätunniste tukee enintään neljän vain luku -kentän arvon näyttämistä. Jos haluat, että käyttäjä voi muokata kenttää, lisää kenttä lomakkeen osaan.  
Tämä viesti näytetään lomakkeiden suunnitteluohjelmassa, kun lomakkeessa on käytössä suuren tiheyden ylätunniste ja ylätunnisteen pikaikkuna on piilotettu.  
  
Suuren tiheyden ylätunnisteessa näkyvät kenttien vain luku -arvot. Koska ylätunnisteen pikaikkuna on piilotettu, käyttäjät eivät voi muokata kenttien arvoja.  
  
Tässä viestissä kerrotaan tekijälle, että ylätunnisteeseen lisätyt kentät ovat vain luku -muodossa. Jos tekijät haluavat käyttäjien voivan muokata kenttiä, ne on lisättävä lomakkeen osaan.

### <a name="header-field-values-are-not-editable-moving-a-field-from-the-body-to-the-header-will-display-as-a-read-only-value-to-maintain-editability-copy-the-field-to-the-header"></a>Ylätunnisteen kenttien arvoja ei voi muokata: Jos kenttä siirretään tekstiosasta ylätunnisteeseen, se näkyy vain luku -arvona. Jos haluat, että muokattavuus säilyy, kopioi kenttä ylätunnisteeseen.  
Tämä viesti näytetään lomakkeiden suunnitteluohjelmassa vain silloin, kun lomakkeessa on käytössä suuren tiheyden ylätunniste ja ylätunnisteen pikaikkuna on piilotettu.  
  
Suuren tiheyden ylätunnisteessa näkyvät kenttien vain luku -arvot. Koska ylätunnisteen pikaikkuna on piilotettu, käyttäjät eivät voi muokata kenttien arvoja.  
  
Tämä viesti kertoo tekijälle, että tämä yrittää siirtää kenttää lomakkeen tekstiosasta lomakkeen ylätunnisteeseen. Jos näin tehdään, kentästä tulee vain luku -kenttä. Tekijä voi siirtää kentän ylätunnisteeseen tai kopioida kentän ylätunnisteeseen. Jos kenttä siirretään ylätunnisteeseen, se ei ole käytettävissä lomakkeen tekstiosan alkuperäisessä sijainnissa eivätkä käyttäjät voi muokata sitä. Jos ylätunnisteeseen lisätään kentän kopio, kenttä säilyy alkuperäisessä sijainnissa. Näin varmistetaan, että käyttäjät voivat jatkaa kentän muokkaamista lomakkeen tekstiosassa.

### <a name="form-headers-now-default-to-high-density-to-display-more-data-use-the-new-form-designer-to-edit-header-density"></a>Lomakkeiden ylätunnisteet saavat nyt oletusarvoisesti suuren tiheyden ja näyttävät enemmän tietoja. Käytä uutta lomakkeiden suunnitteluohjelmaa ylätunnisteen tiheyden muokkaamisessa.  
Tämä viesti näytetään perinteisessä lomakkeiden suunnitteluohjelmassa, kun tekijä avaa muokkausta varten päälomakkeen, jossa on käytössä pienen tiheyden ylätunniste.  
  
Tässä viestissä on tietoja suuren tiheyden ylätunnisteesta ja sen eduista sekä siitä, että tekijöiden tulisi käyttää uutta lomakkeiden suunnitteluohjelmaa ylätunnisteen tiheyden määrittämisessä.  

### <a name="this-form-is-using-high-density-header-for-the-best-authoring-experience-with-this-form-use-the-new-form-designer"></a>Tässä lomakkeessa käytetään suuren tiheyden ylätunnistetta. Voit helpoimmin muokata tätä lomaketta uudella lomakkeiden suunnitteluohjelmalla. 
 Tämä viesti näytetään perinteisessä lomakkeiden suunnitteluohjelmassa, kun tekijä avaa muokkausta varten päälomakkeen, jossa on käytössä suuren tiheyden ylätunniste.  
  
Perinteinen lomakkeiden suunnitteluohjelma ei sisällä WYSIWYG-suunnittelukokemusta. Se ei myöskään havaitse ja estä lomakkeen ylätunnisteeseen tehtyjen muutosten vaikutuksia tai varoita niistä. Kun esimerkiksi muokkaat lomaketta, jossa on käytössä suuren tiheyden ylätunniste ja ylätunnisteen pikaikkuna on piilotettu, perinteinen lomakkeiden suunnitteluohjelma ei estä tekijöitä lisäämästä yli neljää kenttää ylätunnisteeseen, vaikka nämä kentät eivät ole käyttäjien käytettävissä.  
  
Tämä viesti kertoo tekijälle, että suuren tiheyden ylätunnisteen omaavan lomakkeen muokkaamisessa tulisi käyttää uutta lomakkeiden suunnitteluohjelmaa. Näin varmistetaan, että tekijä tietää lomakkeen ylätunnisteeseen tehtävien muutosten vaikutuksen.

## <a name="see-also"></a>Katso myös
[Mallipohjaisen sovelluksen lomakkeen suunnitteluohjelman yleiskatsaus](form-designer-overview.md)  
[Lomakkeiden luominen tai muokkaaminen lomakkeiden suunnitteluohjelman avulla](create-and-edit-forms.md)  
[Lomakkeiden kenttien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-fields-on-form.md)  
[Lomakkeiden osien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-sections-on-form.md)  
[Lomakkeiden välilehtien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-tabs-on-form.md)  
[Lomakkeiden suunnitteluohjelmassa käytettävissä olevat ominaisuudet](form-designer-properties.md)  
[Ylätunnisteen ominaisuuksien määrittäminen lomakkeiden suunnitteluohjelmassa](form-designer-header-properties.md)  
[Lomakkeen suunnitteluohjelman puunäkymän käyttäminen](using-tree-view-on-form.md)  
[Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-field-portal.md)
