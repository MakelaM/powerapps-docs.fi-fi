---
title: SharePoint-lomakkeiden integrointi | Microsoft Docs
description: Tutustu siihen, miten mukautetut lomakkeet toimivat SharePointissa
author: sarafankit
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 11/11/2017
ms.author: ankitsar
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 341d6973504ba50dbeeb058019a32196f72ec8c5
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42864925"
---
# <a name="understand-sharepoint-forms-integration"></a>Tutustu SharePoint-lomakkeiden integrointiin
Nyt voit helposti [mukauttaa mitä tahansa SharePoint-luettelolomakkeita](customize-list-form.md) PowerAppsissa. Näissä ohjeissa neuvomme vaiheittain, miten nämä lomakkeet toimivat ja miten niitä voi mukauttaa lisää.

Jos olet mukauttanut lomakkeen SharePoint-luetteloa varten, huomasit luultavasti, että oletuslomake toimii kaikissa toiminnoissa, kuten kohteen luomisessa, näyttämisessä ja muokkaamisessa. Tämä saavutetaan luotujen kaavojen ja **SharePointIntegration**-ohjausobjektin avulla.

## <a name="understand-the-default-generated-form"></a>Oletuslomake

Oletuslomake muodostuu seuraavista ohjausobjekteista ja niiden oletusarvoista:

* **FormScreen1** – Lomakkeen sisältävä [näyttö](controls/control-screen.md).

* **SharePointForm1** – Luettelokohteen luontiin, näyttämiseen ja muokkaukseen käytetty [lomake](working-with-forms.md).

    * **Data Source** – Luettelo, jota varten lomake on mukautettu.

    * **Kohde** – Luettelosta valittu kohde. Tämän oletusarvona on First(), joka valitsee luettelon ensimmäisen kohteen PowerApps Studiossa.

        **If(IsBlank(SharePointIntegration.Selected) || IsEmpty(SharePointIntegration.Selected),First('*YourListName*'),SharePointIntegration.Selected)**

    * **OnSuccess** – Kun kohteen luominen tai tallentaminen onnistuu, lomake nollataan ja SharePoint piilottaa lomakkeen.

        **ResetForm(SharePointForm1); RequestHide()**

* **SharePointIntegration** – Ohjausobjekti, joka vastaa käyttäjien toimiin liittyvästä tiedonsiirrosta SharePointin ja PowerAppsin välillä.

    * **Data Source** – Luettelo, jota varten lomake on mukautettu.

        **'*YourListName*'**

    * **OnNew** – Asettaa **SharePointForm1**-lomakkeen Uusi-tilaan.

        **NewForm(SharePointForm1)**

    * **OnView** – Asettaa **SharePointForm1**-lomakkeen tarkastelutilaan.

        **ViewForm(SharePointForm1)**

    * **OnEdit** – Asettaa **SharePointForm1**-lomakkeen muokkaustilaan.

        **EditForm(SharePointForm1)**

    * **OnSave** – Lähettää **SharePointForm1**-lomakkeen muutokset. Kun lomakkeen lähetys onnistuu, suoritetaan kaava **SharePointForm1.OnSuccess**.

        **SubmitForm(SharePointForm1)**

    * **OnCancel** – Nollaa **SharePointForm1**-lomakkeen muutokset. SharePoint piilottaa lomakkeen aina, kun käyttäjä napsauttaa tai napauttaa **Peruuta**-kohtaa SharePointissa.

        **ResetForm(SharePointForm1)**

Nämä oletusarvot varmistavat, että SharePointissa suoritettava lomake toimii. Ne muuttavat PowerApps-lomakkeen tilan, kun käyttäjä käyttää lomaketta SharePointissa. Lisäksi ne varmistavat, että muutokset lähetetään SharePointiin.

## <a name="understand-the-sharepointintegration-control"></a>SharePointIntegration-ohjausobjekti
**SharePointIntegration**-ohjausobjekti siirtää käyttäjien toimiin liittyvät tiedot SharePointin ja PowerAppsin välillä.

![](./media/sharepoint-form-integration/sharepointintegration-object.png)

>[!NOTE]
>**SharePointIntegration**-ohjausobjektin ominaisuudet ovat käytettävissä vain, kun lomake suoritetaan SharePointissa. Niitä ei voi käyttää, kun lomaketta mukautetaan PowerApps Studiossa. Nämä ominaisuudet eivät ole ehkä käytettävissä **OnStartissa** tai **OnVisiblessa**. 

**SharePointIntegration**-ohjausobjektin ominaisuudet:

**Valittu** – SharePoint-luettelosta valittu kohde.

**OnNew** – Sovelluksen reagointitapa, kun käyttäjä napsauttaa tai napauttaa **Uusi**-painiketta tai avaa **Luo kohde** -lomakkeen SharePointissa.

**OnView** – Sovelluksen reagointitapa, kun käyttäjä napsauttaa tai napauttaa **kohdetta** tai avaa **Kohteen tiedot** -lomakkeen SharePointissa.

**OnEdit** – Sovelluksen reagointitapa, kun käyttäjä napsauttaa tai napauttaa **Muokkaa kaikkia** -painiketta tai avaa **Muokkaa kohdetta** -lomakkeen SharePointissa.

**OnSave** – Sovelluksen reagointitapa, kun käyttäjä napsauttaa tai napauttaa **Tallenna**-painiketta SharePointissa.

**OnCancel** – Sovelluksen reagointitapa, kun käyttäjä napsauttaa tai napauttaa **Peruuta**-painiketta SharePointissa.

**SelectedListItemID** – SharePoint-luettelosta valitun kohteen kohdetunnus.

**Data Source** – Luettelo, joka sisältää lomakkeen näyttämän, muokkaaman tai luoman tietueen. Ota huomioon, että jos käytät tätä ominaisuutta, **Valittu**- ja **SelectedItemID**-ominaisuudet eivät välttämättä enää toimi.

## <a name="customize-the-default-form"></a>Oletuslomakkeen mukautus
Nyt kun tunnet oletuslomakkeen ja **SharePointIntegration**-ohjausobjektin toimintaperiaatteen, voit muuttaa kaavoja ja siten mukauttaa lomakkeita edelleen. Lomakkeita mukautettaessa kannattaa huomioida seuraavat asiat:

* Jos haluat luoda erillisiä mukautettuja toimintoja kohteen luomista, tarkastelua ja muokkausta varten, määritä **SharePointIntegration**-ohjausobjektin **OnNew**-, **OnView**- tai **OnEdit**-kaavat tietyillä muuttujilla tai siirry eri näyttöihin.

* Määritä **SharePointIntegration**-ohjausobjektin **OnSave**-kaavalla, mikä mukautettu tapahtuma käynnistyy, kun käyttäjä napsauttaa tai napauttaa **Tallenna**-painiketta SharePointissa. Jos sinulla on useita lomakkeita, muista lähettää vain sillä hetkellä käytössä olevan lomakkeen muutokset.

  > [!TIP]
  >    Määritä **OnNew**-, **OnView**- ja **OnEdit**-kaavojen muuttujille eri arvot. Voit käyttää tätä muuttujaa **OnSave**-kaavassa sen määrittämiseen, mikä lomake on käytössä.

* Muista liittää **RequestHide()** kaikkien lomakkeidesi **OnSuccess**-kaavaan. Ilman sitä SharePoint ei tiedä, milloin lomake pitäisi piilottaa.

* Et voi piilottaa lomaketta, kun käyttäjä napsauttaa tai napauttaa **Peruuta**-painiketta SharePointissa. Muista sen vuoksi aina nollata lomakkeet **SharePointIntegration**-ohjausobjektin **OnCancel**-kaavassa.

* **SharePointIntegration**-ohjausobjektin ominaisuudet eivät ole ehkä käytettävissä **OnStartissa** tai **OnVisiblessa**, ja nämä tapahtumat suoritetaan vain kerran, kun luettelo on ladattu. Voit käyttää **OnNew**, **OnView**, tai **OnEdit** suorittaa logiikka, ennen kuin lomake näytetään käyttäjälle aina, kun kaavoja. 
