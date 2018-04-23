---
title: Tietoryhmät | Microsoft Docs
description: Microsoft PowerAppsin tietoryhmien esittely.
services: powerapps
suite: powerapps
documentationcenter: na
author: manasmams
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 03/21/2018
ms.author: manasma
ms.openlocfilehash: 1adf0f4888d57b2d5636864e9bdd18e00848b9d8
ms.sourcegitcommit: c5e3991e0e4e9f22a1e094d699f35adabfb97c6c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/03/2018
---
# <a name="learn-all-about-data-groups"></a>Hanki kattavia tietoja tietoryhmistä
Tietoryhmät ovat yksinkertainen tapa luokitella palveluita [tietojen menetyksen estämisen (DLP) käytännössä](prevent-data-loss.md). Kaksi käytettävissä olevaa tietoryhmää ovat **vain yritystiedot** -ryhmä ja **yritystietoja ei sallita** -ryhmä. Organisaatiot voivat määrittää vapaasti, mitkä palvelut asetetaan tiettyyn tietoryhmään. Hyvä tapa luokitella palveluita on asettaa niitä ryhmiin sen perusteella, mikä niiden vaikutus organisaatioon on. Kaikki palvelut asetetaan oletusarvoisesti tietoryhmään **yritystietoja ei sallita**. Voit hallita tietoryhmän palveluita, kun luot tai muokkaat DLP-käytännön ominaisuuksia hallintokeskuksessa.

## <a name="how-data-is-shared-between-data-groups"></a>Tietojen jakaminen tietoryhmien välillä
Tietoja ei voi jakaa eri ryhmissä olevien palvelujen kesken. Esimerkiksi, jos asetat SharePointin ja Salesforcen **vain yritystiedot** -ryhmään ja Facebookin ja Twitterin **yritystietoja ei sallita** -ryhmään, et voi luoda PowerApp-sovellusta, joka siirtää tietietoja SharePointin ja Facebookin välillä. Vaikka tietoja ei voi jakaa eri ryhmissä olevien palvelujen välillä, voit jakaa tietoja tietyssä ryhmässä olevien palveluiden välillä. Palataan aiempaan esimerkkiin. Koska SharePoint ja Salesforce oli asetettu samaan tietoryhmään, loppukäyttäjiesi laatimat PowerApps-sovellukset voivat jakaa tietoja SharePoint- ja Salesforce-palvelun välillä. Olennaista tässä on se, että tiettyyn ryhmään asetetut palvelut voivat jakaa tietoja keskenään, mutta eri ryhmiin asetetut palvelut eivät.

Lisäksi ainakin yksi tietoryhmä on määritettävä *oletus*ryhmäksi. Aluksi **yritystietoja ei sallita** -ryhmä on *oletus*ryhmä ja kaikki palvelut ovat tietoryhmässä. Järjestelmänvalvoja voi muuttaa oletustietoryhmäksi **vain yritystiedot** -ryhmän. 

> [!NOTE]
> Kaikki uudet palvelut, jotka lisätään PowerAppsiin, asetetaan määritettyyn *oletus*ryhmään. Tästä syystä on suositeltavaa säilyttää **yritystietoja ei sallita** -ryhmä oletusryhmänä ja lisätä palveluja manuaalisesti **vain yritystiedot** -ryhmään sen jälkeen, kun organisaatiosi on arvioinut vaikutukset sille, että yritystietojen jakaminen sallitaan uuden palvelun kanssa.

## <a name="add-services-to-a-data-group"></a>Palveluiden lisääminen tietoryhmään
Tässä esittelyssä lisäämme SharePointin ja Salesforcen tietojen menetyksen estämisen (DLP) käytännön **vain yritystiedot** -ryhmään.

1. Valitse **+ Lisää** linkki, joka on DLP-käytännön **vain yritystiedot** -ryhmän ruudun sisällä:    
   ![Lisää kuva](./media/introduction-to-data-groups/add-to-data-group-1.png)  
2. Valitse SharePoint ja Salesforce ja sen jälkeen **Lisää palveluita** lisätäksesi molemmat vain yritystiedot -ryhmään:    
   ![Lisää palveluiden kuva](./media/introduction-to-data-groups/add-to-data-group-2.png)  
3. Valitse **Tallenna käytäntö** yläreunan valikosta:  
   ![Tallenna käytäntö](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. Huomaa, että sekä SharePoint että Salesforce ovat nyt vain yritystiedot -ryhmässä:  
   ![päivitetty yritystiedot-ryhmä](./media/introduction-to-data-groups/add-to-data-group-3.png)   

Tässä esittelyssä olet lisännyt SharePointin ja Salesforcen tietojen menetyksen estämisen (DLP) käytännön **vain yritystiedot** -ryhmään. Jos DLP-käytännön osana oleva henkilö laatii sovelluksen, joka jakaa tietoa SharePointin tai Salesforcen ja minkä tahansa **yritystietoja ei sallita** -tietoryhmässä olevan palvelun välillä, sovelluksen suorittamista ei sallita.

## <a name="remove-services-from-a-data-group"></a>Palvelujen poistaminen tietoryhmästä
Koska kaikkien palveluiden on oltava yhdessä käytettävissä olevista tietoryhmistä, voit poistaa palvelun tietystä ryhmästä yksinkertaisesti lisäämällä palvelun toiseen ryhmään ja sen jälkeen tallentamalla käytännön.  

## <a name="change-the-default-data-group"></a>Oletustietoryhmän muuttaminen
Tässä esityksessä muutamme oletustietoryhmän **yritystietoja ei sallita** -tietoryhmästä **vain yritystiedot** -tietoryhmään.  

> [!IMPORTANT]
> Kaikki uudet palvelut, jotka lisätään PowerAppsiin, asetetaan määritettyyn *oletus*ryhmään. Tästä syystä on suositeltavaa säilyttää ryhmä **yritystietoja ei sallita** oletusryhmänä ja lisätä palvelut manuaalisesti **vain yritystiedot** -ryhmään.

1. Valitse symboli **...**, joka sijaitsee sen tietoryhmän oikeassa yläkulmassa, jonka haluat määrittää oletustietoryhmäksi:    
   ![muuta oletusryhmä](./media/introduction-to-data-groups/default-data-group-0.png)  
2. Valitse **Aseta oletusryhmäksi**:  
   ![muuta oletusryhmä](./media/introduction-to-data-groups/default-data-group-1.png)   
3. Valitse **Tallenna käytäntö** yläreunan valikosta:  
   ![muuta oletusryhmä](./media/introduction-to-data-groups/add-to-data-group-4.png)
4. Huomaa, että tietoryhmä on nyt määritetty oletustietoryhmä:  
   ![muuta oletusryhmä](./media/introduction-to-data-groups/default-data-group-2.png)   

## <a name="next-steps"></a>Seuraavat vaiheet
* [Lisätietoja tietojen menetyksen estämisen (DLP) käytännöistä](prevent-data-loss.md)
* [Opi uutta ympäristöistä](environments-overview.md)
* [Lue lisätietoja Microsoft PowerAppsista](../maker/canvas-apps/getting-started.md)
