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
ms.openlocfilehash: b6ee687fdfe6da8550d76193a7c9219aae5ae291
ms.sourcegitcommit: 0b051bba173353d7ceda3b60921e7e009eb00709
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/24/2018
ms.locfileid: "39218828"
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerAppsin PowerShell-tuki (esiversio)
Sovellusten tekijöille ja järjestelmänvalvojille tarkoitetulla PowerShell-cmdlet-komentojen esiversiolla voit automatisoida monia seuranta- ja hallintatehtäviä, jotka on tällä hetkellä mahdollista suorittaa vain manuaalisesti [PowerAppsissa](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) tai [PowerApps-hallintakeskuksessa](https://admin.powerapps.com).

## <a name="installation"></a>Asennus
Suorita sovellusten luojille tarkoitetut PowerShell-cmdlet-komennot seuraavasti:

1. Lataa[PowerShell-komentosarjatiedosto](https://go.microsoft.com/fwlink/?linkid=2006349).

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
    # This call will open a prompt to collect the credentials (AAD account & password) that will be used by the commands
    Add-PowerAppsAccount
    ```

    ```
    # Here is how you can pass in credentials (avoiding opening a prompt)
    $pass = ConvertTo-SecureString "password" -AsPlainText -Force
    Add-PowerAppsAccount -Username foo@bar.com -Password $pass
    ```


## <a name="powerapps-cmdlets-for-app-creators-preview"></a>PowerAppsin cmdlet-komennot sovellusten luojille (esiversio)

### <a name="prerequisite"></a>Edellytys
Käyttäjät, joilla on kelvollinen PowerApps-käyttöoikeus, voivat suorittaa toiminnot näissä cmdlet-komennoissa, mutta heillä on käytettävissään vain ne resurssit (esimerkiksi sovellukset, työnkulut jne.), jotka on luotu tai jaettu heidän kanssaan.

### <a name="cmdlet-list"></a>Cmdlet-komentoluettelo
> [!NOTE]
> Jotkin cmdlet-komentojen funktioiden nimet on päivitetty uusimmassa versiossa, jotta voidaan lisätä tarvittavat etuliitteet ristiriitojen estämiseksi. Seuraavassa taulukossa on yleiskatsaus muutoksista.

| Tarkoitus | Cmdlet-komento |
| --- | --- |
| Ympäristöjen luku | Get-PowerAppEnvironment *(aiemmin Get-PowerAppsEnvironment)* <br> Get-FlowEnvironment
| Kaaviosovelluksen lukeminen, päivittäminen ja poistaminen | Get-App <br> Remove-App <br> Publish-App <br> Set-AppDisplayName <br> Get-AppVersion <br> Restore-AppVersion
| Kaaviosovelluksen käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-PowerAppRoleAssignment *(aiemmin Get-AppRoleAssignment)* <br> Set-PowerAppRoleAssignment *(aiemmin Set-AppRoleAssignment)* <br> Remove-PowerAppRoleAssignment *(aiemmin Remove-AppRoleAssignment)*
| Työnkulun lukeminen, päivittäminen ja poistaminen | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow
| Työnkulun käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole
| Työnkulun hyväksyntöjen lukeminen ja niihin vastaaminen | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest
| Yhteyksien lukeminen ja poistaminen | Get-PowerAppConnection *(aiemmin Get-Connection)* <br> Remove-PowerAppConnection *(aiemmin Remove-Connection)*
| Yhteyden käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-PowerAppConnectionRoleAssignment *(aiemmin Get-ConnectionRoleAssignment)* <br> Set-PowerAppConnectionRoleAssignment *(aiemmin Set-ConnectionRoleAssignment)* <br> Remove-PowerAppConnectionRoleAssignment *(aiemmin Remove-ConnectionRoleAssignment)*
| Yhdistimien lukeminen ja poistaminen | Get-PowerAppConnector *(aiemmin Get-Connector)* <br> Remove-PowerAppConnector *(aiemmin Remove-Connector)*
| Mukautettujen yhdistimien käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-PowerAppConnectorRoleAssignment *(aiemmin Get-ConnectorRoleAssignment)* <br> Set-PowerAppConnectorRoleAssignment *(aiemmin Set-ConnectorRoleAssignment)* <br> Remove-PowerAppConnectorRoleAssignment *(aiemmin Remove-ConnectorRoleAssignment)*


> [!NOTE]
> Käytä seuraavia komentoja syntaksin ymmärtämiseen ja kunkin cmdlet-komennon esimerkkien tarkasteluun:
>```
>Get-Help Get-PowerAppEnvironment
>Get-Help Get-PowerAppEnvironment -Examples
>Get-Help Get-PowerAppEnvironment -Detailed
>```

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdlet-komennot järjestelmänvalvojille (esiversio)

### <a name="prerequisite"></a>Edellytys
Jotta voit suorittaa järjestelmänvalvojan cmdlet-komentojen hallintatoimia, sinulla on oltava seuraavat käyttöoikeudet:

* Maksullisen PowerApps-palvelupaketin 2 käyttöoikeus tai PowerApps-palvelupaketin 2 kokeiluversion käyttöoikeus. Voit rekisteröityä 30 päivän maksuttoman kokeiluversion käyttäjäksi osoitteessa [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Kokeiluversion käyttöoikeudet voi uusia, jos ne ovat vanhentuneet.

* [Office 365:n yleisen järjestelmänvalvojan](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleisen järjestelmänvalvojan](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) oikeudet ovat myös pakollisia, jos haluat tehdä hakuja toisen käyttäjän resursseihin. (Huomioi, että ympäristön järjestelmänvalvojilla on pääsy vain niihin ympäristöihin ja ympäristön resursseihin, joihin heillä on oikeudet.)

### <a name="cmdlet-list"></a>Cmdlet-komentoluettelo
> [!NOTE]
> Jotkin cmdlet-komentojen funktioiden nimet on päivitetty uusimmassa versiossa, jotta voidaan lisätä tarvittavat etuliitteet ristiriitojen estämiseksi. Seuraavassa taulukossa on yleiskatsaus muutoksista.

| Tarkoitus | Cmdlet-komennot
| --- | ---
| Lue, päivitä ja poista ympäristöjä ja Common Data Service sovellusten tietokannoille | New-AdminPowerAppEnvironment **\*Uusi\*** <br> Set-AdminPowerAppEnvironmentDisplayName **\*Uusi\*** <br> Get-AdminPowerAppEnvironment *(aiemmin Get-AdminEnvironment)* <br> Remove-AdminPowerAppEnvironment *(aiemmin Remove-AdminEnvironment)* <br> New-AdminPowerAppCdsDatabase **\*Uusi\*** <br> Get-AdminPowerAppCdsDatabaseLanguages **\*Uusi\*** <br> Get-AdminPowerAppCdsDatabaseCurrencies **\*Uusi\*** <br> Get-AdminPowerAppEnvironmentLocations **\*Uusi\***
| Ympäristöjen oikeuksien lukeminen, päivittäminen ja poistaminen <br><br> *Nämä cmdlet-komennot toimivat tänään ainoastaan ympäristöissä, joissa ei ole Common Data Service for Apps -tietokantaa.* | Get-AdminPowerAppEnvironmentRoleAssignment *(aiemmin Get-AdminEnvironmentRoleAssignment)* <br> Set-AdminPowerAppEnvironmentRoleAssignment *(aiemmin Set-AdminEnvironmentRoleAssignment)* <br> Remove-AdminPowerAppEnvironmentRoleAssignment *(aiemmin Remove-AdminEnvironmentRoleAssignment)*
| Kaaviosovellusten lukeminen, päivittäminen ja poistaminen | Get-AdminPowerApp *(aiemmin Get-AdminApp)* <br> Remove-AdminPowerApp *(aiemmin Remove-AdminApp)* <br> Get-AdminPowerAppConnectionReferences **\*Uusi\*** <br> Set-AdminPowerAppAsFeatured **\*Uusi\*** <br> Clear-AdminPowerAppAsFeatured **\*Uusi\*** <br> Set-AdminPowerAppAsHero **\*Uusi\*** <br> Clear-AdminPowerAppAsHero **\*Uusi\*** <br> Set-AdminPowerAppApisToBypassConsent **\*Uusi\*** <br> Clear-AdminPowerAppApisToBypassConsent **\*Uusi\***
| Kaaviosovelluksen käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminPowerAppRoleAssignment *(aiemmin Get-AdminAppRoleAssignment)* <br> Remove-AdminPowerAppRoleAssignment *(aiemmin Remove-AdminAppRoleAssignment)* <br> Set-AdminPowerAppRoleAssignment *(aiemmin Set-AdminAppRoleAssignment)* <br> Set-AdminPowerAppOwner *(aiemmin Set-AdminAppOwner)*
| Työnkulkujen lukeminen, päivittäminen ja poistaminen | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow <br> Remove-AdminFlowApprovals **\*Uusi\***
| Työnkulun käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminFlowOwnerRole <br> Set-AdminFlowOwnerRole <br> Remove-AdminFlowOwnerRole
| Yhteyksien lukeminen ja poistaminen | Get-AdminPowerAppConnection *(aiemmin Get-AdminConnection)* <br> Remove-AdminPowerAppConnection *(aiemmin Remove-AdminConnection)*
| Yhteyden käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminPowerAppConnectionRoleAssignment *(aiemmin Get-AdminConnectionRoleAssignment)* <br> Set-AdminPowerAppEnvironmentConnectionRoleAssignment *(aiemmin Set-AdminConnectionRoleAssignment)* <br> Remove-AdminPowerAppConnectionRoleAssignment *(aiemmin Remove-AdminConnectionRoleAssignment)*
| Mukautettujen liittimien lukeminen ja poistaminen | Get-AdminPowerAppConnector *(aiemmin Get-AdminConnector)* <br> Remove-AdminPowerAppConnector *(aiemmin Remove-AdminConnector)*
| Mukautettujen yhdistimien käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminPowerAppConnectorRoleAssignment *(aiemmin Get-AdminConnectorRoleAssignment)*<br> Set-AdminPowerAppConnectorRoleAssignment *(aiemmin Set-AdminConnectorRoleAssignment)* <br> Remove-AdminPowerAppConnectorRoleAssignment *(aiemmin Remove-AdminConnectorRoleAssignment)*
| PowerAppsin käyttäjäasetusten, käyttäjäsovelluksen asetusten ja ilmoitusten lukeminen | Get-AdminPowerAppsUserDetails
| Sellaisten käyttäjän Microsoft Flow -asetusten lukeminen ja poistaminen, jotka eivät näy käyttäjälle, mutta jotka tukevat työnkulun suorittamista | Get-AdminFlowUserDetails <br> Remove-AdminFlowUserDetails
| Tietojen menetyksen estämiskäytäntöjen luominen, lukeminen, päivittäminen ja poistaminen organisaatiossasi | Get-AdminDlpPolicy *(aiemmin Get-AdminApiPolicy)* <br> Add-AdminDlpPolicy *(aiemmin Add-AdminApiPolicy)* <br> Remove-AdminDlpPolicy *(aiemmin Remove-AdminApiPolicy)* <br> Set-AdminDlpPolicy *(aiemmin Set-AdminApiPolicy)* <br> Add-ConnectorToBusinessDataGroup <br>  Remove-ConnectorFromBusinessDataGroup

> [!NOTE]
> Käytä seuraavia komentoja syntaksin ymmärtämiseen ja kunkin cmdlet-komennon esimerkkien tarkasteluun:
>```
>Get-Help Get-AdminEnvironment
>Get-Help Get-AdminEnvironment -Examples
>Get-Help Get-AdminEnvironment -Detailed
>```

## <a name="questions"></a>Onko sinulla kysyttävää?

Jos sinulla on kommentteja, ehdotuksia tai kysymyksiä, voit lähettää ne [Administering PowerApps -yhteisötauluun](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
