---
title: PowerShell-tuki (esikatselu) | Microsoft Docs
description: Powershell-cmdlet-komentojen kuvaus ja niiden asennus- ja suoritusohjeet.
author: jamesol-msft
manager: kfile
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 05/23/2018
ms.author: jamesol
ms.openlocfilehash: 788f9ec1ce1ac8604606d2d2ad836a0cd12360d4
ms.sourcegitcommit: 91a102426f1bc37504142cc756884f3670da5110
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/26/2018
ms.locfileid: "34552986"
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerAppsin PowerShell-tuki (esiversio)
Sovellusten tekijöille ja järjestelmänvalvojille tarkoitetulla PowerShell-cmdlet-komentojen esiversiolla voit automatisoida monia seuranta- ja hallintatehtäviä, jotka on tällä hetkellä mahdollista suorittaa vain manuaalisesti [PowerAppsissa](https://web.powerapps.com) tai [PowerApps-hallintakeskuksessa](https://admin.powerapps.com).

## <a name="installation"></a>Asennus
Suorita sovellusten luojille tarkoitetut PowerShell-cmdlet-komennot seuraavasti:

1. Lataa[PowerShell-komentosarjatiedosto](https://go.microsoft.com/fwlink/?linkid=872358).

2. Pura tiedosto kansioon.

3. Avaa PowerShell-komentoikkuna samassa kansiossa järjestelmänvalvojana.

4. Suorita seuraava kertaluontoinen PowerShell-komento (olettaen, että et ole koskaan suorittanut PowerShell-komentoja nykyisessä koneessa):

    ```
    Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Force
    ```

5. Tuo tarvittavat moduulit seuraavilla komennoilla:

    ```
    Import-Module .\Microsoft.PowerApps.Administration.PowerShell.psm1 -Force
    Import-Module .\Microsoft.PowerApps.PowerShell.psm1 -Force
    ```

6.  Järjestelmässä on tällä hetkellä [tunnettu ongelma](https://powerusers.microsoft.com/t5/Administering-PowerApps/Getting-errors-when-I-try-to-import-the-preview-powerapps/td-p/109036), joka saattaa vaatia sinua poistamaan manuaalisesti PowerShell-tiedostojen eston käyttämällä seuraavaa komentoa:

    ```
    dir . | Unblock-File
    ```
7. Ennen minkään komennon käyttöä sinun on annettava tunnistetietosi seuraavan komennon avulla. Näitä tunnistetietoja päivitetään enintään noin 8 tuntia, ennen kuin sinua pyydetään kirjautumaan sisään uudelleen cmdlet-komentojen käytön jatkamista varten.

    ```
    Add-PowerAppsAccount
    ```


## <a name="powerapps-cmdlets-for-app-creators-preview"></a>PowerAppsin cmdlet-komennot sovellusten luojille (esiversio)

### <a name="prerequisite"></a>Edellytys
Käyttäjät, joilla on kelvollinen PowerApps-käyttöoikeus, voivat suorittaa toiminnot näissä cmdlet-komennoissa, mutta heillä on käytettävissään vain ne resurssit (esimerkiksi sovellukset, työnkulut jne.), jotka on luotu tai jaettu heidän kanssaan.

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
> Käytä seuraavia komentoja syntaksin ymmärtämiseen ja kunkin cmdlet-komennon esimerkkien tarkasteluun:
>```
>Get-Help Get-PowerAppsEnvironment
>Get-Help Get-PowerAppsEnvironment -Examples
>Get-Help Get-PowerAppsEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdlet-komennot järjestelmänvalvojille (esiversio)

### <a name="prerequisite"></a>Edellytys
Jotta voit suorittaa järjestelmänvalvojan cmdlet-komentojen hallintatoimia, sinulla on oltava seuraavat käyttöoikeudet:

* Maksullisen PowerApps-palvelupaketin 2 käyttöoikeus tai PowerApps-palvelupaketin 2 kokeiluversion käyttöoikeus. Voit rekisteröityä 30 päivän maksuttoman kokeiluversion käyttäjäksi osoitteessa [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Kokeiluversion käyttöoikeudet voi uusia, jos ne ovat vanhentuneet.

* [Office 365:n yleisen järjestelmänvalvojan](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleisen järjestelmänvalvojan](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) oikeudet ovat myös pakollisia, jos haluat tehdä hakuja toisen käyttäjän resursseihin. (Huomioi, että ympäristön järjestelmänvalvojilla on pääsy vain niihin ympäristöihin ja ympäristön resursseihin, joihin heillä on oikeudet.)

### <a name="cmdlet-list"></a>Cmdlet-komentoluettelo
| Tarkoitus | Cmdlet-komennot
| --- | ---
| Ympäristöjen lukeminen ja poistaminen | Get-AdminEnvironment <br> Remove-AdminEnvironment
| Ympäristöjen oikeuksien lukeminen, päivittäminen ja poistaminen <br><br> *Nämä cmdlet-komennot toimivat ainoastaan ympäristöissä, joissa ei ole Common Data Service for Apps -tietokantaa.* | Get-AdminEnvironmentRoleAssignment <br> Set-AdminEnvironmentRoleAssignment <br> Remove-AdminEnvironmentRoleAssignment
| Kaaviosovellusten lukeminen ja poistaminen | Get-AdminApp <br> Remove-AdminApp
| Kaaviosovelluksen käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminAppRoleAssignment <br> Remove-AdminAppRoleAssignment <br> Set-AdminAppRoleAssignment <br> Set-AdminAppOwner
| Työnkulkujen lukeminen, päivittäminen ja poistaminen | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow  <br> Remove-AdminFlowOwnerRole
| Yhteyksien lukeminen ja poistaminen | Get-AdminConnection <br> Remove-AdminConnection
| Yhteyden käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminConnectionRoleAssignment <br> Set-AdminConnectionRoleAssignment <br> Remove-AdminConnectionRoleAssignment
| Mukautettujen liittimien lukeminen ja poistaminen | Get-AdminConnector <br> Remove-AdminConnector
| Mukautettujen yhdistimien käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminConnectorRoleAssignment <br> Set-AdminConnectorRoleAssignment <br> Remove-AdminConnectorRoleAssignment
| PowerAppsin käyttäjäasetusten, käyttäjäsovelluksen asetusten ja ilmoitusten lukeminen | Get-AdminPowerAppsUserDetails
| Sellaisten käyttäjän Microsoft Flow -asetusten lukeminen ja poistaminen, jotka eivät näy käyttäjälle, mutta jotka tukevat työnkulun suorittamista | Get-AdminFlowUserDetails <br> Remove-AdminFlowUserDetails
| Tietojen menetyksen estämiskäytäntöjen luominen, lukeminen, päivittäminen ja poistaminen organisaatiossasi | Get-AdminApiPolicy <br> Add-AdminApiPolicy <br> Remove-AdminApiPolicy <br> Set-AdminApiPolicy <br> Add-ConnectorToBusinessDataGroup <br>  Remove-ConnectorFromBusinessDataGroup

> [!NOTE]
> Käytä seuraavia komentoja syntaksin ymmärtämiseen ja kunkin cmdlet-komennon esimerkkien tarkasteluun:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Onko sinulla kysyttävää?

Jos sinulla on kommentteja, ehdotuksia tai kysymyksiä, voit lähettää ne [Administering PowerApps -yhteisötauluun](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
