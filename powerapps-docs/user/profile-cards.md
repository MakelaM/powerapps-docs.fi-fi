---
title: Näytä yhteys henkilön tai käyttäjän profiili kortti | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 10/03/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 67441e506ba2715a9994f6b81cd08426e37e0fc8
ms.sourcegitcommit: 7c46e7ce889e2f1c5352ed2e705b0bb8968f2a89
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/04/2019
ms.locfileid: "71950906"
---
# <a name="view-the-profile-card-for-a-contact-or-user"></a>Näytä yhteys henkilön tai käyttäjän profiili kortti

Profiili kortin avulla saat nopeasti tietoja yhteys henkilöstä tai käyttäjästä. Kun valitset yhteys tieto-tai käyttäjä kentän mallipohjaisissa sovelluksissa Dynamics 365, kuten Dynamics 365 Sales-ja Dynamics 365-asiakas palvelussa, voit etsiä niihin liittyviä tietoja profiili kortiltasi. Lisä tietoja profiili korteista on kohdassa [profiili kortit Office 365](https://support.office.com/en-us/article/Profile-cards-in-Office-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501)-tieto kannassa.

> [!NOTE]
>  - Profiili kortti on käytettävissä **yhteys henkilölle** ja **käyttäjä** entiteetille. Lisä tietoja on kohdassa [profiili kortin ottaminen käyttöön (järjestelmänvalvojille)](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/enable-profile-card).
>  - Common Data Service profiili korttia ei näytetä, jos monimenetelmäinen todentaminen on otettu käyttöön Office Delve-palvelulle Azure Active Directory.

## <a name="view-a-contacts-profile"></a>Näytä yhteys henkilön profiili

1.  Siirry kohtaan **Aktiviteetit**.
2.  Valitse olemassa oleva tehtävä tai luo uusi.
3.  Vie hiiren osoitin kentän **kutsun** kohdalle, kun sillä on yhteyshenkilö tietue. 

Voit tarkastella sellaisen yhteys henkilön tietoja, joka sisältää yhteys henkilön kuvan, nimen, otsikon ja tilin.

4. Jos haluat nähdä lisä tietoja, Laajenna yhteys tiedon profiilia valitsemalla **Näytä lisää** .
 
    > [!div class="mx-imgBorder"] 
    > ![Laajenna yhteys henkilön profiili kortin]tiedot(media/profile1.png "Laajenna yhteys tieto profiili kortin tiedot")
   
 ## <a name="view-a-users-profile"></a>Käyttäjän profiilin tarkasteleminen
 
1.  Siirry kohtaan **accounts**.
2.  Valitse tili tietue.
3.  Vie hiiren osoitin omistaja-kentän päälle, kun sillä on käyttäjä tietue. Voit tarkastella sisäisen käyttäjän tietoja.
4.  Jos haluat nähdä lisä tietoja, kuten sähkö posti viestejä ja jaettuja tiedostoja, valitse **Näytä lisää** , jos haluat laajentaa yhteys henkilön profiilia.
 
    > [!div class="mx-imgBorder"] 
    > ![Laajenna käyttäjä profiili kortin]tiedot(media/profile2.png "Laajenna käyttäjä profiili kortin tiedot")


 ## <a name="faqs"></a>Usein kysyttyjä kysymyksiä
 
### <a name="where-can-i-see-profile-cards-in-dynamics-365"></a>Missä voin tarkastella profiili kortteja Dynamics 365?
Profiili kortteja voi nähdä yhteys henkilö-ja käyttäjä tietueissa. Voit tarkastella niitä vain, kun ne ovat haussa.

### <a name="where-is-information-shown-in-the-profile-card-coming-from"></a>Mistä profiili kortissa näytettävät tiedot ovat perä isin?
Yhteys tieto profiili kortissa näkyvät tiedot noudetaan Common Data Service (ei Microsoft Exchangesta). Tämä tarkoittaa, että yhteys tiedot ovat perä isin Dynamics 365.

Käyttäjä profiili kortissa näkyvät tiedot noudetaan Office 365 (Azure Active Directory)-palvelimesta. Lisä tietoja on kohdassa [profiili kortit Office 365-tieto kannassa (järjestelmänvalvoja-osa)](https://support.office.com/en-us/article/Profile-cards-in-Office-365-e80f931f-5fc4-4a59-ba6e-c1e35a85b501).

### <a name="how-can-i-customize-the-fields-shown-on-the-profile-card"></a>Miten voin mukauttaa profiili kortissa näkyviä kenttiä?
Tällä hetkellä profiili kortissa näkyvien kenttien luettelo ei ole avoinna muokkausta varten.

### <a name="why-is-the-start-chat-option-on-the-profile-card-disabled-greyed-out"></a>Miksi profiili kortin **Start chat** -vaihto ehto on poistettu käytöstä (harmaana)?
**Start chat** -ja **Lähetä Sähkö posti** -vaihto ehdot profiili kortissa avaavat oletusarvoisen pikaviestin ja Sähkö posti sovelluksesi. **Aloita keskustelu** -vaihto ehto on käytössä, jos henkilö, johon yrität muodostaa yhteyden, on samassa Azure Active Directory ympäristössä kuin sinä tai se on liittoutunut yhteys henkilö.


  
