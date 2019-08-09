---
title: 'Lomakkeiden osien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla | MicrosoftDocs'
ms.custom: ''
ms.date: 04/21/2019
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

# <a name="add-move-or-delete-sections-on-a-form"></a>Lomakkeen osioiden lisääminen, siirtäminen tai poistaminen 
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Lomakkeiden osien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla. 

> [!NOTE]
> Kun osioita lisätään tai siirretään Vedä ja pudota -toiminnon avulla, ota huomioon, että lomakkeen esikatselu on reagoiva ja voi muodostaa useita välilehden sarakkeita pinottuina. Voit varmistaa, että lisättävä tai siirrettävä osio on oikeassa välilehden sarakkeessa, pudottamalla tai liittämällä sen toiseen osioon, joka on jo kyseisen välilehden sarakkeessa.

## <a name="add-sections-to-a-form"></a>Osien lisääminen lomakkeeseen
Voit lisätä osioita lomakkeeseen **Asettelut**-ruudun avulla. 

> [!div class="mx-imgBorder"] 
> ![](media/layouts-pane.png "Asettelut-ruutu")

  > [!NOTE]
  >   Osia voi lisätä vain päälomakkeisiin ja pikanäkymien lomakkeisiin. Lisätietoja: [Lomaketyypit](types-forms.md)

### <a name="add-sections-to-a-form-using-drag-and-drop"></a>Osioiden lisääminen lomakkeeseen Vedä ja pudota -toiminnolla

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse komentopalkista **Lisää ohjausobjekti**. Vaihtoehtoisesti voit valita vasemmassa ruudussa **Asettelut**. 
3. Valitse **Asettelut**-ruudussa osion ohjausobjekti ja vedä se lomakkeen esikatseluun. Kun vedät osion lomakkeen esikatselussa, näkyviin tulee pudotuskohteet, joihin voit lisätä osion. 
4. Pudota osio haluamaasi paikkaan. Huomaa seuraavat asiat: 
    - Osiot voidaan pudottaa aiemmin luodun osion eteen tai jälkeen.
    - Osat voidaan myös pudottaa välilehden tyhjään alueeseen. Tässä tapauksessa osa lisätään käytettävissä olevaan tilaan, jotta osat jakautuvat tasaisesti välilehtien sarakkeisiin.
    - Kun viet osoittimen välilehden otsikon päälle, osio muuttuu valittuna olevassa välilehdessä, ja voit lisätä osion toiseen välilehteen.   
5. Jos haluat lisätä osioita, toista vaiheet 3 – 4.
6. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

### <a name="add-sections-to-a-form-using-selection"></a>Osioiden lisääminen lomakkeeseen valintaa käyttämällä 

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselussa toinen olemassa oleva osio tai välilehti. Huomaa seuraavat seikat:
    - Kun valitset olemassa olevan osan, uusi osa lisätään olemassa olevan osan jälkeen. 
    - Kun valitset välilehden, uusi osio lisätään käytettävissä olevaan osaan niin, että osiot jaetaan tasaisesti välilehden sarakkeisiin. 
3. Valitse komentopalkista **Lisää ohjausobjekti**. Vaihtoehtoisesti voit valita vasemmassa ruudussa **Asettelut**.  
4. Valitse **Asettelut**-ruudussa lomakkeeseen lisättävä osan ohjausobjekti. Vaihtoehtoisesti voit valita haluamasi osan ohjausobjektin vieressä olevan **...**-kohdan ja tämän jälkeen **Lisää valittuun välilehteen** -kohdan. 
5. Jos haluat lisätä osioita, toista vaiheet 2 – 4.
6. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

## <a name="move-sections-on-a-form"></a>Osioiden kenttien siirtäminen

### <a name="move-sections-on-a-form-using-drag-and-drop"></a>Osioiden siirtäminen lomakkeessa Vedä ja pudota -toiminnolla

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselussa osion otsikko tai tyhjä välilyönti sen osan sisällä, jonka haluat siirtää, ja käynnistä Vedä-toiminto. Kun vedät osion lomakkeen esikatselussa, näkyviin tulee pudotuskohteet, joihin voit siirtää osion. 
3. Pudota osio haluamaasi paikkaan. Huomaa seuraavat asiat: 
    - Osiot voidaan pudottaa aiemmin luodun osion eteen tai jälkeen.
    - Osat voidaan myös pudottaa välilehden tyhjään alueeseen. Tässä tapauksessa osa lisätään käytettävissä olevaan tilaan, jotta osat jakautuvat tasaisesti välilehtien sarakkeisiin.
    - Kun viet osoittimen välilehden otsikon päälle, osio muuttuu valittuna olevassa välilehdessä, ja voit lisätä osion toiseen välilehteen.   
4. Jos haluat siirtää osioita, toista vaiheet 2 – 3.
5. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

### <a name="move-sections-on-a-form-using-cut-and-paste"></a>Osioiden siirtäminen lomakkeessa Leikkaa ja liitä -toiminnolla

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselusta siirrettävä osio.
3. Valitse komentopalkista **Leikkaa**.
4. Valitse lomakkeen esikatselussa toinen aiemmin luotu osio tai välilehti. Voit myös siirtyä toiseen välilehteen tarpeen mukaan.
5. Valitse komentopalkissa **Liitä** tai valitse nuolenkärki ja valitse sitten **Liitä ennen**. Huomaa seuraavat asiat: 
    - Kun valitset **Liitä**, siirrettävä osa liitetään aiemmin luodun osion jälkeen. 
    - Kun valitset **Liitä ennen**, siirrettävä osa liitetään aiemmin luodun osion eteen.
    - Kun valitset välilehden, siirrettävä osio lisätään käytettävissä olevaan osaan niin, että osiot jaetaan tasaisesti välilehden sarakkeisiin. **Liitä ennen** -toimintoa ei voi käyttää, joten se ei ole käytettävissä tässä palvelutilanteessa.
6. Jos haluat siirtää osioita, toista vaiheet 2 – 5.
7. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

## <a name="delete-sections-on-a-form"></a>Osioiden kenttien poistaminen
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselussa lomakkeesta poistettava osio. 
3. Valitse komentopalkista **Poista**.
4. Jos haluat poistaa osioita, toista vaiheet 2 – 3.
4. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

    > [!NOTE]
    >   - Osia voi poistaa vain päälomakkeista ja pikanäkymien lomakkeista. Lisätietoja: [Lomaketyypit](types-forms.md)
    >   - Jos poistat osan vahingossa, valitse komentopalkista **Peruuta**. Tällöin lomake palautetaan sen edelliseen tilaan. 
    >   - Osaa, joka sisältää pakollisen tai lukitun kentän, ei voi poistaa. 
    >   - Lukittua osaa ei voi poistaa. 
    >   - Välilehdessä on oltava vähintään yksi osio kussakin välilehden sarakkeessa. Jos poistat välilehden sarakkeen viimeisen jäljellä olevan osan, järjestelmä lisää automaattisesti uuden osan. 

### <a name="see-also"></a>Katso myös
[Mallipohjaisen sovelluksen lomakkeen suunnitteluohjelman yleiskatsaus](form-designer-overview.md)  
[Lomakkeiden luominen tai muokkaaminen lomakkeiden suunnitteluohjelman avulla](create-and-edit-forms.md)  
[Lomakkeiden kenttien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-fields-on-form.md)  
[Lomakkeiden välilehtien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-tabs-on-form.md)  
[Lomakkeiden suunnitteluohjelmassa käytettävissä olevat ominaisuudet](form-designer-properties.md)  
[Lomakkeen suunnitteluohjelman puunäkymän käyttäminen](using-tree-view-on-form.md)  
[Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-field-portal.md) 
