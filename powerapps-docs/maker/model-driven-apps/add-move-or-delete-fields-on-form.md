---
title: 'Lomakkeen kenttien lisääminen, siirtäminen tai poistaminen | MicrosoftDocs'
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

# <a name="add-move-or-delete-fields-on-a-form"></a>Lomakkeen kenttien lisääminen, siirtäminen tai poistaminen  
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Lisää, siirrä ja poista kenttiä lomakkeensuunnitteluohjelman avulla.

> [!NOTE]
> Kun kenttiä lisätään tai siirretään Vedä ja pudota -toiminnon avulla, ota huomioon, että lomakkeen esikatselu on reagoiva ja voi muodostaa useita osan sarakkeita pinottuina. Voit varmistaa, että lisättävä tai siirrettävä kenttä on oikeassa osasarakkeessa, pudottamalla tai liittämällä sen toiseen kenttään, joka on jo kyseisen osan sarakkeessa.

## <a name="add-fields-to-a-form"></a>Kenttien lisääminen lomakkeeseen
Voit lisätä kenttiä lomakkeeseen **Kentät**-ruudun avulla. **Kentät**-ruudun haku ja suodatus auttaa löytämään kenttiä nopeasti. Se sisältää myös vaihtoehdon, jonka avulla voi näyttää vain käyttämättömät kentät. 

> [!div class="mx-imgBorder"] 
> ![](media/fields-pane.png "Kentät-ruutu")

### <a name="add-fields-to-a-form-using-drag-and-drop"></a>Kenttien lisääminen lomakkeeseen Vedä ja pudota -toiminnolla

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse komentopalkista **Lisää kenttä**. Vaihtoehtoisesti voit valita vasemmassa ruudussa **Kentät**.  **Kentät**-ruutu avautuu oletusarvoisesti, kun lomakkeen suunnitteluohjelma avataan. 
3. **Kentät**-ruudussa voit etsiä haluamasi kentän valitsemalla, suodattamalla tai selaamalla. Jos kenttää ei löydy, se voi olla jo lomakkeessa. Tyhjennä **Näytä vain käyttämättömät kentät** -kohta, jos haluat nähdä kaikki kentät (myös ne jotka jo ovat lomakkeessa). 
4. Valitse **Kentät**-ruudussa kenttä ja vedä se lomakkeen esikatseluun. Kun vedät kentän lomakkeen esikatselussa, näkyviin tulee pudotuskohteet, joihin voit lisätä kentän. 
5. Pudota kenttä haluamaasi paikkaan. Huomaa seuraavat asiat: 
    - Kentät voidaan pudottaa aiemmin luodun kentän eteen tai jälkeen.
    - Kentät voidaan myös pudottaa osion tyhjään alueeseen. Tässä tapauksessa, uusi kenttä lisätään käytettävissä olevaan osaan niin, että kentät jaetaan tasaisesti osion sarakkeisiin.
    - Kun viet osoittimen välilehden otsikon päälle, kenttä muuttuu valittuna olevassa välilehdessä, ja voit lisätä kentän toiseen välilehteen.   
6. Jos haluat lisätä kenttiä, toista vaiheet 3 – 5.
7. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

### <a name="add-fields-to-a-form-using-selection"></a>Kenttien lisääminen lomakkeeseen valintaa käyttämällä 

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselussa toinen olemassa oleva kenttä tai osa. Huomaa seuraavat asiat:
    - Kun valitset olemassa olevan kentän, uusi kenttä lisätään olemassa olevan kentän jälkeen. 
    - Kun valitset osan, uusi kenttä lisätään käytettävissä olevaan osaan niin, että kentät jaetaan tasaisesti osion sarakkeisiin. 
3. Valitse komentopalkista **Lisää kenttä**. Vaihtoehtoisesti voit valita vasemmassa ruudussa **Kentät**. **Kentät**-ruutu avautuu oletusarvoisesti, kun lomakkeen suunnitteluohjelma avataan. 
4. **Kentät**-ruudussa voit etsiä haluamasi kentän valitsemalla, suodattamalla tai selaamalla. Jos kenttää ei löydy, se voi olla jo lomakkeessa. Tyhjennä **Näytä vain käyttämättömät kentät** -kohta, jos haluat nähdä kaikki kentät (myös ne jotka jo ovat lomakkeessa). 
5. Valitse **Kentät**-ruudussa lomakkeeseen lisättävä kenttä. Vaihtoehtoisesti voit valita haluamasi kentän vieressä olevan **...**-kohdan ja tämän jälkeen **Lisää valittuun osaan** -kohdan. 
6. Jos haluat lisätä kenttiä, toista vaiheet 2 – 5.
7. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

## <a name="move-fields-on-a-form"></a>Lomakkeen kenttien siirtäminen

### <a name="move-fields-on-a-form-using-drag-and-drop"></a>Kenttien siirtäminen lomakkeessa Vedä ja pudota -toiminnolla

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselukentästä kenttä, jonka haluat siirtää, ja aloita vetotoiminto. Kun vedät kentän lomakkeen esikatselussa, näkyviin tulee pudotuskohteet, joihin voit siirtää kentän. 
3. Pudota kenttä haluamaasi paikkaan. Huomaa seuraavat asiat: 
    - Kentät voidaan pudottaa aiemmin luodun kentän eteen tai jälkeen.
    - Kentät voidaan myös pudottaa osion tyhjään alueeseen. Tässä tapauksessa, uusi kenttä lisätään käytettävissä olevaan osaan niin, että kentät jaetaan tasaisesti osion sarakkeisiin.
    - Kun viet osoittimen välilehden otsikon päälle, kenttä muuttuu valittuna olevassa välilehdessä, ja voit lisätä kentän toiseen välilehteen.   
4. Jos haluat siirtää kenttiä, toista vaiheet 2 – 3.
5. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

    > [!NOTE]
    >   Kenttien siirtämistä ylä- ja alatunnisteeseen ei vielä tueta vedä ja pudota -toiminnossa. 

### <a name="move-fields-on-a-form-using-cut-and-paste"></a>Kenttien siirtäminen lomakkeessa Leikkaa ja liitä -toiminnolla

1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselusta siirrettävä kenttä.
3. Valitse komentopalkista **Leikkaa**.
4. Valitse lomakkeen esikatselussa toinen olemassa oleva kenttä tai osa. Voit myös siirtyä tarpeen mukaan toiseen välilehteen.
5. Valitse komentopalkissa **Liitä** tai valitse nuolenkärki ja valitse sitten **Liitä ennen**. Huomaa seuraavat asiat:
    - Kun valitset **Liitä**, siirrettävä kenttä liitetään aiemmin luodun kentän jälkeen. 
    - Kun valitset **Liitä ennen**, siirrettävä kenttä liitetään aiemmin luodun kentän eteen.
    - Kun valitset osan, siirrettävä kenttä lisätään käytettävissä olevaan osaan niin, että kentät jaetaan tasaisesti osion sarakkeisiin. **Liitä ennen** -toimintoa ei voi käyttää, joten se ei ole käytettävissä tässä palvelutilanteessa.
6. Jos haluat siirtää kenttiä, toista vaiheet 2 – 5.
7. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

## <a name="delete-fields-on-a-form"></a>Lomakkeen kenttien poistaminen
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](create-and-edit-forms.md#create-a-form) tai [Lomakkeen muokkaaminen](create-and-edit-forms.md#edit-a-form)
2. Valitse lomakkeen esikatselussa lomakkeesta poistettava kenttä. 
3. Valitse komentopalkista **Poista**. 
4. Jos haluat poistaa kenttiä, toista vaiheet 2 – 3.
5. Valitse komentopalkista **Tallenna**, jos haluat tallentaa lomakkeen tai valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

     > [!NOTE]
     >   -  Jos poistat kentän vahingossa, valitse komentopalkista **Peruuta**. Tällöin lomake palautetaan sen edelliseen tilaan. 
     >   -  Pakollista tai lukittua kenttää ei voi poistaa. 

### <a name="see-also"></a>Katso myös
[Mallipohjaisen sovelluksen lomakkeen suunnitteluohjelman yleiskatsaus](form-designer-overview.md)  
[Lomakkeiden luominen tai muokkaaminen lomakkeiden suunnitteluohjelman avulla](create-and-edit-forms.md)  
[Lomakkeiden osien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-sections-on-form.md)  
[Lomakkeiden välilehtien lisääminen, siirtäminen tai poistaminen lomakkeiden suunnitteluohjelman avulla](add-move-or-delete-tabs-on-form.md)  
[Lomakkeiden suunnitteluohjelmassa käytettävissä olevat ominaisuudet](form-designer-properties.md)  
[Lomakkeen suunnitteluohjelman puunäkymän käyttäminen](using-tree-view-on-form.md)  
[Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-field-portal.md)
