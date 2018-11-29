---
title: Pikanäkymän ohjausobjektin ominaisuudet mallipohjaisen sovelluksen päälomakkeille PowerAppsissa | MicrosoftDocs
description: Tietoja pikanäkymän ohjausobjektin ominaisuuksista pääikkunassa lomakkeille PowerAppsissa | MicrosoftDocs
Keywords: Quick view control properties; Dynamics 365; Main forms
author: Mattp123
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
ms.author: matp
manager: kvivek
ms.date: 06/06/2018
ms.service: crm-online
ms.topic: article
ms.assetid: 68f68d5b-6c71-4b95-bb46-d48c59d9008e
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="model-driven-app-quick-view-control-properties"></a>Mallipohjaisen sovelluksen pikanäkymä-ohjausobjektin ominaisuudet

Malliin perustuvan sovelluslomakkeen pikanäkymän ohjausobjekti näyttää lomakkeen valintatoiminnon avulla valitun tietueen tiedot. Ohjausobjektissa näkyvät tiedot määritetään pikalomakkeella. Näytettyjä tietoja ei voi muokata, mutta pikalomakkeeseen sisältyvästä ensisijaisesta kentästä tulee linkki, jolla liittyvän tietueen voi avata. Lisätietoja: [Pikalomakkeiden luominen ja muokkaaminen](create-edit-quick-view-forms.md)  

> [!div class="mx-imgBorder"] 
> ![Yhteyshenkilön pikalomake tililomakkeessa](media/quick-view-form-contact.png "Yhteyshenkilön pikalomake tililomakkeessa")  

Voit käyttää **Pikanäkymä-ohjausobjektin ominaisuudet** -kohtaa PowerApps-sivustossa. 
1.  Kirjaudu sisään [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) -sovellukseen.  


2.  Laajenna **Tiedot**, valitse **Entiteetit** ja valitse sitten haluamasi entiteetti. Valitse **Lomakkeet**-välilehti. 

3. Avaa lomakeluettelosta lomake, joka tyyppi on **Pää**. Valitse **Lisää**-välilehdessä **Pikalomake**, jos haluat tarkastella pikanäkymän ohjausobjektin ominaisuuksia.

    ![quick-view-control](media/quick-view-control.png)
  
|Ominaisuus|Kuvaus|  
|--------------|-----------------|  
|**Nimi**|**Pakollinen**: pikalomakkeen yksilöivä nimi, jolla siihen viitataan komentosarjoissa.|  
|**Otsikko**|**Pakollinen**: Pikalomakkeessa näytettävä otsikko.|  
|**Näytä otsikko lomakkeessa**|Näyttää otsikon lomakkeessa.|  
|**Valintakenttä**|Valitse jokin lomakkeen valintakentistä.|  
|**Liittyvä entiteetti**|Arvo määräytyy valitun **valintakentän** mukaan. Se on yleensä valintakentän 1:N-entiteettisuhteen ensisijainen entiteetti.<br /><br /> Jos entiteetissä on **Mahdollinen asiakas** -valintakenttä, joka hyväksyy arvoksi asiakkaan tai yhteyshenkilön, voit valita **Pikalomake**-kentässä sekä asiakkaan että yhteyshenkilön pikalomakkeen vaihtamalla tämän arvon ja valitsemalla sitten toisen pikalomakkeen.|  
|**Pikalomake**|Jos **liittyvällä entiteetillä** on pikalomakkeita, voit valita ne tässä. Luo muussa tapauksessa sellainen valitsemalla **Uusi**.<br /><br /> Voit muuttaa valittua pikalomaketta valitsemalla **Muokkaa**.|  
|**Lisäominaisuudet**|Voit määrittää oletushahmontamistyylin valitsemalla valintaruudun.|

## <a name="next-steps"></a>Seuraavat vaiheet

[Päälomakkeen ja osien käyttäminen](use-main-form-and-components.md)
 
