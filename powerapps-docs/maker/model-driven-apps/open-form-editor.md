---
title: Mallipohjaisen sovelluksen lomake-editorin avaaminen PowerAppsissa | MicrosoftDocs
ms.custom: ''
ms.date: 06/27/2018
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
ms.assetid: 8478a07a-c697-4784-874b-36958eb4f95d
caps.latest.revision: 63
ms.author: matp
manager: kvivek
ms.openlocfilehash: e0fe15df88fccbaee3c13a344416a434e1f92923
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39674960"
---
# <a name="open-the-model-driven-app-form-editor"></a>Mallipohjaisen sovelluksen lomake-editorin avaaminen 
Lomake-editorissa suunnittelet lomakkeita pudottamalla osia, kuten osioita, välilehtiä, kenttiä ja ohjausobjekteja, lomake-editorin pohjaan. Tässä ohjeaiheessa kerrotaan useista eri tavoista käyttää lomake-editoria.
 
Jos luot lomaketta muokatessasi uusia ratkaisuosia, esimerkiksi verkkoresursseja, osien nimissä käytetään ratkaisun julkaisijan mukautuksen etuliitettä oletusratkaisun osalta, ja nämä osat sisältyvät vain oletusratkaisuun. Jos haluat, että uudet ratkaisuosat sisältyvät tiettyyn hallitsemattomaan ratkaisuun, avaa lomake-editori kyseisen hallitsemattoman ratkaisun kautta.  

## <a name="access-the-form-editor-from-the-powerapps-site"></a>Lomake-editorin käyttäminen PowerApps-sivustosta

1. Kirjaudu sisään [PowerAppsiin](https://web.powerapps.com/). 

2. Valitse **Mallipohjainen** > **Tiedot** > **Entiteetit** > ja valitse sitten haluamasi entiteetti, kuten tilientiteetti. 

3. Valitse **Lomakkeet**-välilehti ja avaa sitten haluamasi lomake, kuten **Tili**-päälomake.

## <a name="access-the-form-editor-from-solution-explorer"></a>Lomake-editorin käyttäminen ratkaisunhallinnasta
  
1.  Avaa [ratkaisunhallinta](advanced-navigation.md#solution-explorer).
  
2.  Valitse **Osat**, laajenna **Entiteetit** ja sitten haluamasi entiteetti ja valitse **Lomakkeet**.  
  
3.  Valitse luettelosta lomake, jota haluat muokata.  
  

## <a name="access-the-form-editor-through-the-command-bar-within-a-model-driven-app"></a>Lomake-editorin käyttäminen mallipohjaisen sovelluksen komentopalkin kautta 
  
1.  Avaa tietue.  
  
2.  Jos entiteetille on useita päälomakkeita, tarkista, että lomake on se, jota haluat muokata. Jos se ei ole, valitse muokattava lomake lomakkeen valitsimella.  
  
3.  Valitse **Lisää komentoja** -painike ![Tapaamisaktiviteetin Lisää komentoja -painike](media/more-commands.gif "Tapaamisaktiviteetin Lisää komentoja -painike").  
  
4.  Valitse **Lomake-editori**.  

## <a name="access-the-form-editor-from-within-dynamics-365-customer-engagement"></a>Lomake-editorin käyttäminen Dynamics 365 Customer Engagementista
  
 Voit käyttää Dynamics 365 Customer Engagementin lomake-editoria komentopalkin tai valintanauhan kautta entiteetin mukaan. Kumpikin tavoista avaa lomakkeen oletusratkaisun kontekstissa. 

## <a name="access-the-form-editor-for-an-unmanaged-solution"></a>Hallitsemattoman ratkaisun lomake-editorin käyttäminen  
  
1.  Avaa [Ratkaisut](advanced-navigation.md#solutions).  
  
2.  Kaksoisnapsauta hallitsematonta ratkaisua, jota haluat käsitellä.  
  
3.  Etsi muokattavan lomakkeen sisältävä entiteetti. Jos entiteettiä ei löydy, sinun on lisättävä se. Lisätietoja: [Entiteetin lisääminen hallitsemattomaan ratkaisuun](#add-an-entity-to-an-unmanaged-solution) 
  
### <a name="add-an-entity-to-an-unmanaged-solution"></a>Entiteetin lisääminen hallitsemattomaan ratkaisuun  
  
1.  Valitse **Entiteetit**-solmu ja napsauta luettelon yläpuoliselta työkaluriviltä **Lisää olemassa oleva**.  
  
2.  **Valitse ratkaisuosia** -valintaikkunassa, jossa **Osan tyyppi** -valitsimen arvoksi on asetettu **Entiteetti**, valitse haluamasi entiteetti ja sitten **OK**.  
  
3.  Jos **Pakollisia osia puuttuu** -valintaikkuna tulee näyttöön, voit valita **Ei, älä lisää pakollisia osia**, jos et aio viedä tätä hallitsematonta ratkaisua toiseen ympäristöön. Jos et halua lisätä puuttuvia pakollisia osia tällä hetkellä, voit lisätä ne myöhemmin. Saat ilmoituksen uudelleen, jos viet tämän ratkaisun tulevaisuudessa.  
  
5.  Laajenna ratkaisunhallinnassa entiteetti, joka sisältää muokattavan lomakkeen, ja valitse **Lomakkeet**.  
  
6.  Valitse muokattava lomake luettelosta kaksoisnapsauttamalla.  

## <a name="next-steps"></a>Seuraavat vaiheet

[Luo ja suunnittele lomakkeita](create-design-forms.md)
