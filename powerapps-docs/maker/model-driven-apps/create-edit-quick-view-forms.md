---
title: Mallipohjaisen sovelluksen pikalomakkeiden luominen tai muokkaaminen PowerAppsissa | MicrosoftDocs
description: Tietoja pikalomakkeen luomisesta tai muokkaamisesta.
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
ms.assetid: 9b101734-cc11-4d05-bd45-eb611eae9931
caps.latest.revision: 14
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="create-a-model-driven-app-quick-view-form-to-view-information-about-a-related-entity"></a>Mallipohjaisen sovelluksen pikalomakkeen luominen liittyvän entiteetin tietojen katselua varten

Tässä ohjeaiheessa on tietoja pikalomakkeen luomisesta ja pikalomakeohjausobjektin lisäämisestä päälomakkeeseen. 

Pikalomake voidaan lisätä toiseen lomakkeeseen pikanäkymän ohjausobjektina. Se tarjoaa mallin tarkastella entiteettitietueen tietoja toisen entiteettitietueen lomakkeessa. Tällöin sovelluksen käyttäjien ei tarvitse siirtyä toiseen tietueeseen nähdäkseen työssään tarvitsemiaan tietoja.  
  
 Pikanäkymän ohjausobjektit liittyvät hakukenttään, joka sisältyy lomakkeeseen. Jos hakukentän arvoa ei ole määritetty, pikanäkymän ohjausobjekti ei näy. Pikanäkymän ohjausobjektien tietoja ei voi muokata eivätkä pikalomakkeet tue lomakkeen komentosarjoja.  
  
 Koska pikalomakkeita katsellaan pikanäkymän ohjausobjektien avulla lomakkeessa, ne eivät sisällä ylätunniste-, alatunniste- tai siirtymäalueita. Pikalomakkeisiin ei voi määrittää käyttöoikeusrooleja eikä niitä voi aktivoida tai poistaa käytöstä.  
  
<a name="BKMK_CreateQFV"></a>   
## <a name="create-a-quick-view-form"></a>Luo pikalomake  
 Voit luoda pikalomakkeet lomake-editorilla samoin kuin luot muita lomakkeita. Pikalomakkeet ovat vain luku -tilassa. Voit luoda niiden avulla lomakkeita, jotka on tarkoitettu vain lukemista varten.  
  
1. Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

    ![Mallipohjainen suunnittelutila](media/model-driven-switch.png)

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2. Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti. 
  
3. Valitse työkaluriviltä **Lisää lomake** > **Pikalomake**.  
  
4. Valitse lomake-editorin työkaluriviltä **Lomakkeen ominaisuudet**.  
  
5. Kirjoita **Lomakkeen ominaisuudet** -valintaikkunaan **Lomakkeen nimi** ja **Kuvaus** erottaaksesi muista tämän pikalomakkeen muista. Sulje **Lomakkeen ominaisuudet** -valintaikkuna valitsemalla **OK**.  
  
6. Vedä mitkä tahansa kentät lomakkeen suunnitteluohjelmassa **kenttien hallinnasta** lomakkeen osaan. 
  
    > [!IMPORTANT]
    >  Jos lisäät kentän ja valitset **Kenttävaatimus** > **Pakollinen** ja sitten tallennat sen, et voi poistaa kenttää.  
  
7. Voit tallentaa lomakkeen ja sulkea lomake-editorin valitsemalla **Tallenna**.  

8. Valitse **Julkaise**, kun haluat nähdä sovelluksen uuden lomakkeen.
  
<a name="BKMK_EditQVF"></a>   
## <a name="edit-a-quick-view-form"></a>Muokkaa pikalomaketta  
 Pikalomakkeissa on yksinkertaistettu asettelu, koska ne on suunniteltu tarkasteltaviksi lomakkeen osan sisällä. Vain yksi yksittäinen sarake-välilehti on käytettävissä. Voit lisätä vain yhden sarakkeen osia, kenttiä, aliruudukoita ja osasarakkeita.   
  
> [!NOTE]
>  Et voi poistaa **Pakollinen**-kenttää. Tämä sanoma tulee näyttöön, jos yrität poistaa kentän: "Kenttä, jota yrität poistaa on pakollinen järjestelmä- tai liiketoimintakenttä." Jos et halua käyttää kenttää lomakkeessa, sinun on poistettava koko lomake ja luotava se uudelleen.  
  
 Pikalomaketta muokattaessa muutokset on julkaistava, ennen kuin ne näkyvät sovelluksessa.  
  
<a name="BKMK_AddQVF"></a>   
## <a name="add-a-quick-view-control-to-a-main-form"></a>Lisää päälomakkeeseen pikanäkymän ohjausobjekti  
 Pikalomakkeita voi lisätä vain päälomakkeeseen, jossa hakukenttä on olemassa, ja joka on suunnattu pikalomakkeen entiteetille.  
  
1.  Valitse [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc)-sivustossa **Mallipohjainen** (siirtymisruudun alaosassa vasemmalla).  

    > [!IMPORTANT]
    > Jos **mallipohjainen** suunnittelutila ei ole käytettävissä, sinun on [luotava ympäristö](https://docs.microsoft.com/powerapps/administrator/create-environment).     
  
2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti.  

3. Valitse lomake, joka on **tyypiltään** **päälomake**.

4. Valitse lomakkeen suunnitteluohjelmassa **Lisää**-välilehti ja valitse sitten työkaluriviltä **Pikalomake**.  
  
5.  Määritä **Pikanäkymän ohjausobjektin ominaisuudet** -valintaikkunassa pikanäkymän ohjausobjektin ominaisuudet, kuten **nimi**, **otsikko** ja **pikalomake**. Lisätietoja: [Pikanäkymän ohjausobjektin ominaisuudet](quick-view-control-properties-legacy.md).  
  
6.  Sulje **Pikanäkymän ohjausobjektin ominaisuudet**-valintaikkuna valitsemalla **OK**.  
  
7.  Valitse **Koti**-välilehti ja valitse sitten **Julkaise**, kun haluat pikanäkymän ohjausobjektin näkyvän lomakkeessa.  
  
## <a name="next-steps"></a>Seuraavat vaiheet   
 [Luo ja suunnittele lomakkeita](create-design-forms.md)   
 [Luo tai muokkaa pikaluontilomakkeita nopeasti](create-edit-quick-create-forms.md)
