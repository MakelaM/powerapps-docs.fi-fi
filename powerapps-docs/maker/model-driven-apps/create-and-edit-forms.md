---
title: Lomakkeiden luominen ja muokkaaminen mallipohjaisen lomakkeen suunnitteluohjelman avulla | MicrosoftDocs
ms.custom: ''
ms.date: 12/13/2018
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

# <a name="create-and-edit-forms-using-the-form-designer"></a>Lomakkeiden luominen ja muokkaaminen lomakkeiden suunnitteluohjelman avulla 
[!INCLUDE [cc-beta-prerelease-disclaimer](../../includes/cc-beta-prerelease-disclaimer.md)]

Käytä uutta lomakkeiden suunnitteluohjelmaa mallipohjaisten sovellusten lomakkeiden luomisessa ja suunnittelussa.

> [!IMPORTANT]
> Uusi mallipohjaisen lomakkeen suunnitteluohjelma tukee tällä hetkellä vain päälomakkeiden luomista ja muokkaamista. Lisätietoja: [Lomaketyypit](types-forms.md)

## <a name="create-a-form"></a>Lomakkeen luominen 
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen. 
2. Laajenna vasemmanpuoleisessa siirtymisruudussa **Tiedot** ja valitse sitten **Entiteetit**. 
3. Valitse entiteetti, kuten asiakasentiteetti, ja valitse sitten **Lomakkeet**-välilehti. 
4. Valitse **Lisää lomake** ja valitse sitten **Päälomake (esikatselu)**.     
    Uuden lomakkeen sisältö täytetään olemassa olevan päälomakkeen määrityksen avulla. Jos päälomakkeita on olemassa, lomakejärjestyksen luettelon yläosassa oleva lomaketta uuden lomakkeen täyttämisessä. 
5. Valitse **Tallenna**, jos haluat tallentaa lomakkeen. Valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset sovelluksen käyttäjien nähtäväksi.  

## <a name="edit-a-form"></a>Lomakkeen muokkaaminen 
1. Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen. 
2. Valitse ja laajenna vasemmanpuoleisessa siirtymisruudussa **Tiedot** ja valitse sitten **Entiteetit**. 
3. Valitse entiteetti, kuten asiakasentiteetti, ja valitse sitten **Lomakkeet**-välilehti.
4. Valitse muokattava lomake ja valitse sitten **Muokkaa lomaketta (esikatselu)**.  
   Vaihtoehtoisesti voit valita haluamasi lomakkeen vieressä olevan **...**-kohdan. Valitse sitten **Muokkaa lomaketta (esikatselu)**. 
5. Valitse **Tallenna**, jos haluat tallentaa lomakkeen. Valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset sovelluksen käyttäjien nähtäväksi. 

## <a name="add-and-remove-fields"></a>Kenttien lisääminen ja poistaminen 
Voit lisätä kentän tai poistaa kenttiä lomakkeesta Kentät-ruudun avulla. Kentät-ruudun haku ja suodatus auttaa löytämään kenttiä nopeasti. Se sisältää myös vaihtoehdon, jonka avulla voi näyttää vain käyttämättömät kentät. 

### <a name="add-a-field"></a>Kentän lisääminen
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](#create-a-form) ja [Lomakkeen muokkaaminen](#edit-a-form)
2. Valitse lomakkeen esikatselussa toinen olemassa oleva kenttä tai osa. 
    - Kun valitset olemassa olevan kentän, uusi kenttä lisätään olemassa olevan kentän alle. 
    - Kun valitset osan, uusi kenttä lisätään käytettävissä olevaan osaan niin, että kentät jaetaan tasaisesti sarakkeisiin. 
3. Valitse **Lisää kenttä**. Vaihtoehtoisesti voit valita vasemmassa ruudussa **Kentät**.  
   Kentät-ruutu avautuu oletusarvoisesti, kun lomakkeen suunnitteluohjelma avataan. 
4. **Kentät**-ruudussa voit etsiä haluamasi kentän valitsemalla, suodattamalla tai selaamalla. 
   Jos kenttää ei löydy, se voi olla jo lomakkeessa. Tyhjennä **Näytä vain käyttämättömät kentät** -kohta, jos haluat nähdä kaikki kentät (myös ne jotka jo ovat lomakkeessa). 
5. Valitse **Kentät**-ruudussa lomakkeeseen lisättävä kenttä. <br />
   Vaihtoehtoisesti voit valita haluamasi kentän vieressä olevan **...**-kohdan ja tämän jälkeen **Lisää valittuun osaan** -kohdan. 
6. Valitse **Tallenna**, jos haluat tallentaa lomakkeen. Valitse **Julkaise**, jos haluat tallentaa ja määrittää muutokset käyttäjien nähtäväksi. 

### <a name="remove-a-field"></a>Kentän poistaminen
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](#create-a-form) ja [Lomakkeen muokkaaminen](#edit-a-form)
2. Valitse lomakkeen esikatselussa lomakkeesta poistettava kenttä. 
3. Valitse **Poista**. <br />
4. Valitse **Tallenna**. 

    > [!NOTE]
    >   -  Jos poistat kentän vahingossa, valitse **Peruuta**. Tällöin toiminto peruutetaan. 
    >   -  Pakollista tai lukittua kenttää ei voi poistaa. 

## <a name="add-and-remove-tabs-and-sections"></a>Välilehtien ja osien lisääminen ja poistaminen 
Jos haluat lisätä tai poistaa välilehden tai osan lomakkeesta, käytä Asettelut-ruutua. 

### <a name="add-a-tab"></a>Välilehden lisääminen
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](#create-a-form) ja [Lomakkeen muokkaaminen](#edit-a-form) 
2. Valitse lomakkeen esikatselussa toinen olemassa oleva välilehti tai lomake. 
    - Kun valitset olemassa olevan välilehden, sen oikealle puolelle lisätään uusi välilehti. 
    - Kun valitset lomakkeen, uusi välilehti lisätään lomakkeen oikeanpuoleiseen välilehteen. 
3. Valitse **Lisää ohjausobjekti**. Vaihtoehtoisesti voit valita vasemmassa ruudussa **Asettelut**.  
4. Valitse **Asettelut**-ruudussa lomakkeeseen lisättävä välilehden ohjausobjekti, kuten **Kahden sarakkeen välilehti**. <br />
   Vaihtoehtoisesti voit valita haluamasi välilehden ohjausobjektin vieressä olevan **...**-kohdan ja tämän jälkeen **Lisää lomakkeeseen** -kohdan.  
5. Valitse **Tallenna**. 


### <a name="remove-a-tab"></a>Välilehden poistaminen
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](#create-a-form) ja [Lomakkeen muokkaaminen](#edit-a-form)
2. Valitse lomakkeen esikatselussa poistettava välilehti ja valitse sitten **Poista**. 
3. Valitse **Tallenna**. 
    > [!NOTE]
    >    - Jos poistat kentän vahingossa, valitse **Peruuta**. Tällöin poistotoiminto peruutetaan. 
    >     - Lomakkeessa on oltava vähintään yksi välilehti. Lomakkeen ainoaa välilehteä ei voi poistaa. 
    >    - Välilehteä, jossa on lukittuja osia, ei voi poistaa. 
    >    - Välilehteä, jossa on pakollisia tai lukittuja kenttiä sisältäviä osia, ei voi poistaa. 

### <a name="add-a-section"></a>Osan lisääminen 
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](#create-a-form) ja [Lomakkeen muokkaaminen](#edit-a-form)
2. Valitse lomakkeen esikatselussa toinen olemassa oleva osa tai välilehti. 
    - Jos valitset olemassa olevan osan, uusi osa lisätään olemassa olevan osan alle. 
    - Jos valitset välilehden, uusi osa lisätään välilehden ensimmäisen sarakkeen alaosaan. 
3. Valitse **Lisää ohjausobjekti**. Vaihtoehtoisesti voit valita vasemmassa ruudussa **Asettelut**.
4. Valitse **Asettelut**-ruudussa lomakkeeseen lisättävä osan ohjausobjekti. <br />
   Vaihtoehtoisesti voit valita haluamasi osan ohjausobjektin vieressä olevan **...**-kohdan ja tämän jälkeen **Lisää valittuun välilehteen** -kohdan.      
5. Valitse **Tallenna**. 
 

### <a name="delete-a-section"></a>Osan poistaminen 
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](#create-a-form) ja [Lomakkeen muokkaaminen](#edit-a-form) 
2. Valitse lomakkeen esikatselussa poistettava osa ja valitse sitten **Poista**.  
3. Valitse **Tallenna**. 
    > [!NOTE]
    >    - Jos poistat osan vahingossa, valitse **Peruuta**. Tällöin poistotoiminto peruutetaan. 
    >    - Kunkin sarakkeen välilehdellä on oltava vähintään yksi osa.  
    >    - Et voi poistaa osaa, jos se on välilehden sarakkeen ainoa osa. 
    >    - Lukittua osaa ei voi poistaa. 
    >    - Osaa, jossa on pakollisia tai lukittuja kenttiä, ei voi poistaa. 
 
## <a name="use-the-tree-view"></a>Käyttäminen puunäkymässä 
Puunäkymä-ruudussa näkyy lomakkeen ohjausobjektien ja kenttien visuaalinen hierarkia. Puunäkymän kuvakkeiden avulla kentän tai ohjausobjektin tyyppi on helppo määrittää. 

Voit käyttää puunäkymää myös lomakkeen kenttien ja ohjausobjektien valinnassa. Puunäkymä on kätevä silloin, kun haluat valita piilotettuja elementtejä, jotka eivät näy lomakkeen esikatselussa. 

Voit tarkastella tai piilottaa solmun elementtejä, kun laajennat tai kutistat puunäkymän solmut. Kun valitset elementin puunäkymässä, se näkyy lomakkeen esikatselussa korostettuna ja elementin ominaisuudet näkyvät ominaisuusruudussa. 

   ![Puunäkymä](media/tree-view.png)

### <a name="open-the-tree-view"></a>Puunäkymän avaaminen 
1. Avaa lomakkeen suunnitteluohjelma, jos haluat luoda lomakkeen tai muokata sitä. Lisätietoja: [Lomakkeen luominen](#create-a-form) ja [Lomakkeen muokkaaminen](#edit-a-form)  
2. Valitse vasemmassa ruudussa **Puunäkymä**.

## <a name="see-also"></a>Katso myös
[Mallipohjaisen sovelluksen lomakkeen suunnitteluohjelman yleiskatsaus](form-designer-overview.md) <br />
[Kenttien luominen ja muokkaaminen](../common-data-service/create-edit-field-portal.md)
