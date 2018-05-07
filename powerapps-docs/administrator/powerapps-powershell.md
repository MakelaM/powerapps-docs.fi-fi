---
title: PowerShell-tuki | Microsoft Docs
description: PowerAppsin PowerShell-tuki
services: powerapps
suite: powerapps
documentationcenter: na
author: jamesol-msft
manager: kfile
editor: ''
tags: ''
ms-topic: article
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/17/2018
ms.author: jamesol
ms.openlocfilehash: 274d34ca56cc993ec26fa4f4ced77bb2aba9985f
ms.sourcegitcommit: e3a2819c14ad67cc4ca6640b9064550d0f553d8f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/20/2018
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerAppsin PowerShell-tuki (esiversio)

Sovellusten tekijöille ja järjestelmänvalvojille tarkoitetulla PowerShell-cmdlet-komentojen esiversiolla voit automatisoida monia seuranta- ja hallintatehtäviä, jotka on tällä hetkellä mahdollista suorittaa vain manuaalisesti [PowerApps-sivustossa](https://web.powerapps.com) tai [PowerApps-hallintakeskuksessa](https://admin.powerapps.com).

## <a name="installation"></a>Asennus
Ennen sovellusten tekijöille tarkoitettujen PowerShell cmdlet-komentojen suorittamista sinun käytävä läpi seuraavat vaiheet:

1. Lataa PowerShell-komentosarjatiedosto [täältä](https://go.microsoft.com/fwlink/?linkid=872358).

2. Pura tiedosto kansioon.

3. Avaa PowerShell-komentoikkuna samassa kansiossa järjestelmänvalvojana.

4. Suorita sitten seuraava kertaluontoinen PowerShell-komento (olettaen, että et ole koskaan suorittanut PowerShell-komentoja nykyisessä koneessa):

    ```
    Set-ExecutionPolicy -ExecutionPolicy Unrestricted -Force
    ```

5. Tuo seuraavaksi tarvittavat moduulit seuraavilla komennoilla:

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6. Lopuksi ennen minkään komennon käyttöä sinun on annettava tunnistetietosi seuraavan komennon avulla. Näitä tunnistetietoja päivitetään enintään noin 8 tuntia, ennen kuin sinua pyydetään kirjautumaan sisään uudelleen cmdlet-komentojen käytön jatkamista varten.

    ```
    Add-PowerAppsAccount
    ```

## <a name="powerapps-cmdlets-for-app-makers-preview"></a>PowerApps cmdlet-komennot sovellusten tekijöille (esiversio)

### <a name="prerequisite"></a>Edellytys
Kuka tahansa käyttäjä, jolla on voimassa oleva PowerApps-käyttöoikeus, voi suorittaa näiden cmdlet-komentojen toimintoja. Käyttäjillä on kuitenkin pääsy vain niihin resursseihin (sovelluksiin, työnkulkuihin jne.), jotka on luotu tai jaettu heille.

### <a name="cmdlet-list"></a>Cmdlet-komentoluettelo
| Tarkoitus | Cmdlet-komento |
| --- | --- |
| Ympäristöjen luku | Get-PowerAppsEnvironment <br> Get-FlowEnvironment
| Kaaviosovelluksen lukeminen, päivittäminen ja poistaminen | Get-App <br> Remove-App <br> Publish-App <br> Set-AppDisplayName <br> Get-AppVersion <br> Restore-AppVersion
| Kaaviosovelluksen käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AppRoleAssignment <br> Set-AppRoleAssignment <br> Remove-AppRoleAssignment
| Työnkulun lukeminen, päivittäminen ja poistaminen | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow
| Työnkulun käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole
| Työnkulun hyväksyntöjen lukeminen ja niihin vastaaminen | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest
| Yhteyksien lukeminen ja poistaminen | Get-Connection <br> Remove-Connection
| Yhteyden käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-ConnectionRoleAssignment <br> Set-ConnectionRoleAssignment <br> Remove-ConnectionRoleAssignment
| Yhdistimien lukeminen ja poistaminen | Get-Connector <br> Remove-Connector
| Mukautettujen yhdistimien käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-ConnectorRoleAssignment <br> Set-ConnectorRoleAssignment <br> Remove-ConnectorRoleAssignment

> [!NOTE]
> Seuraavia komentoja voi käyttää syntaksin ymmärtämiseen ja kunkin cmdlet-komennon esimerkkien tarkasteluun:
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdlet-komennot järjestelmänvalvojille (esiversio)

### <a name="prerequisite"></a>Edellytys
Jotta voit suorittaa järjestelmänvalvojan cmdlet-komentojen hallintatoimia, tarvitset tilin, jolla on seuraavat oikeudet:

- Maksullisen PowerApps-palvelupaketin 2 käyttöoikeus tai PowerApps-palvelupaketin 2 kokeiluversion käyttöoikeus. Voit rekisteröityä 30 päivän maksuttoman kokeiluversion käyttäjäksi osoitteessa [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Kokeiluversion käyttöoikeudet voi uusia, jos ne ovat vanhentuneet.

- [Office 365:n yleisen järjestelmänvalvojan](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleisen järjestelmänvalvojan](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) oikeudet ovat myös pakollisia, jos haluat tehdä hakuja toisen käyttäjän resursseihin. Muussa tapauksessa sinulla on oikeudet vain niihin ympäristöihin ja ympäristön resursseihin, joihin sinulla on ympäristön järjestelmänvalvojan oikeudet.

### <a name="cmdlet-list"></a>Cmdlet-komentoluettelo
| Tarkoitus | Cmdlet-komennot
| --- | ---
| Ympäristöjen lukeminen ja poistaminen | Get-AdminEnvironment <br> Remove-AdminEnvironment
| Ympäristöjen oikeuksien lukeminen, päivittäminen ja poistaminen <br><br> *Nämä cmdlet-komennot toimivat ainoastaan ympäristöissä, joissa ei ole Common Data Service for Apps -tietokantaa.* | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| Kaaviosovellusten lukeminen ja poistaminen | Get-AdminApp <br> Remove-AdminApp
| Kaaviosovelluksen käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| Työnkulkujen lukeminen, päivittäminen ja poistaminen | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole

> [!NOTE]
> Seuraavia komentoja voi käyttää syntaksin ymmärtämiseen ja kunkin cmdlet-komennon esimerkkien tarkasteluun:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Onko sinulla kysyttävää?

Jos sinulla on kommentteja, ehdotuksia tai kysymyksiä, voit lähettää ne [Administering PowerApps -yhteisötauluun](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
