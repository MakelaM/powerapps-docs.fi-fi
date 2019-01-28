---
title: PowerShell-tuki (esikatselu) | Microsoft Docs
description: Powershell-cmdlet-komentojen kuvaus ja niiden asennus- ja suoritusohjeet.
author: jamesol-msft
manager: kvivek
ms.service: powerapps
ms.component: pa-admin
ms.topic: reference
ms.date: 01/18/2019
ms.author: jamesol
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: 0152296adbe01abae2b831576c312a43d1f2a2b8
ms.sourcegitcommit: 3ce7c17f90f87756a072210c8abfbd93733a6d4c
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/18/2019
ms.locfileid: "54397763"
---
# <a name="powershell-support-for-powerapps-preview"></a>PowerAppsin PowerShell-tuki (esiversio)
Sovellusten tekijöille ja järjestelmänvalvojille tarkoitetulla PowerShell-cmdlet-komentojen esiversiolla voit automatisoida monia seuranta- ja hallintatehtäviä, jotka on tällä hetkellä mahdollista suorittaa vain manuaalisesti [PowerAppsissa](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) tai [PowerApps-hallintakeskuksessa](https://admin.powerapps.com).

## <a name="cmdlets"></a>Cmdlet-komennot
[Cmdlet-komennot](https://docs.microsoft.com/powershell/developer/cmdlet/writing-a-windows-powershell-cmdlet) ovat PowerShell-komentosarjakielellä kirjoitettuja funktioita, jotka suorittavat komentoja Windows PowerShell -ympäristössä. Suorittamalla PowerApps-cmdlet-komentoja voit suorittaa toimintoja yrityssovellusympäristössä ilman selaimen järjestelmänvalvojaportaalia. Voit yhdistellä cmdlet-komentoja muiden PowerShell-funktioiden kanssa ja luoda siten monimutkaisia komentosarjoja työnkulkujen optimointiin. Voit käyttää cmdlet-komentoja vaikket olisi vuokraajan järjestelmänvalvoja, mutta vain omistamissasi resursseissa. Admin-sanalla alkavat cmdlet-komennot on tarkoitettu käytettäviksi järjestelmänvalvojan tilillä.

Cmdlet-komennot ovat käytettävissä PowerShell-valikoimassa kahdessa eri moduulissa: 
- [Järjestelmänvalvoja](https://www.powershellgallery.com/packages/Microsoft.PowerApps.Administration.PowerShell/2.0.1)
- [Tekijä](https://www.powershellgallery.com/packages/Microsoft.PowerApps.PowerShell/1.0.1) 

## <a name="installation"></a>Asennus
Suorita sovellusten luojille tarkoitetut PowerShell-cmdlet-komennot seuraavasti:

1. Suorita PowerShell järjestelmänvalvojana.

   > [!div class="mx-imgBorder"] 
   > ![Suorita PowerShell järjestelmänvalvojana](media/open-powershell-as-admin75.png "Suorita PowerShell järjestelmänvalvojana")

2. Tuo tarvittavat moduulit seuraavilla komennoilla:

    ```
    Install-Module -Name Microsoft.PowerApps.Administration.PowerShell
    Install-Module -Name Microsoft.PowerApps.PowerShell -AllowClobber
    ```
3. Jos sinua pyydetään hyväksymään säilön *InstallationPolicy*-arvon muutos, hyväksy ([A] Kyllä kaikkiin) moduulit kirjoittamalla ”A” ja painamalla **Enter** kunkin moduulin kohdalla.

   ![Hyväksy InstallationPolicy-arvo](media/accept-installationpolicy-value75.png "Hyväksy InstallationPolicy-arvo")

4. Ennen komentojen käyttöä sinulla on mahdollisuus antaa tunnistetietosi seuraavan komennon avulla. Näitä tunnistetietoja päivitetään enintään noin 8 tuntia, ennen kuin sinua pyydetään kirjautumaan sisään uudelleen cmdlet-komentojen käytön jatkamista varten.

    ```
    # This call opens prompt to collect credentials (Azure Active Directory account and password) used by the commands 
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

### <a name="cmdlet-list---maker-cmdlets"></a>Luettelo cmdlet-komennoista – Tekijän cmdlet-komennot
> [!NOTE]
> Jotkin cmdlet-komentojen funktioiden nimet on päivitetty uusimmassa versiossa, jotta voidaan lisätä tarvittavat etuliitteet ristiriitojen estämiseksi. Seuraavassa taulukossa on yleiskatsaus muutoksista.

| Tarkoitus | Cmdlet-komento |
| --- | --- |
| Ympäristöjen luku | Get-PowerAppEnvironment *(aiemmin Get-PowerAppsEnvironment)* <br> Get-FlowEnvironment |
| Kaaviosovelluksen lukeminen, päivittäminen ja poistaminen | Get-PowerApp *(aiemmin Get-App)* <br> Remove-PowerApp *(aiemmin Remove-App)* <br> Publish-PowerApp *(aiemmin Publish-App)* <br> Set-AppDisplayName *(aiemmin Set-PowerAppDisplayName)*<br> Get-PowerAppVersion *(aiemmin Get-AppVersion)* <br> Restore-PowerAppVersion *(aiemmin Restore-AppVersion)* |
| Kaaviosovelluksen käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-PowerAppRoleAssignment *(aiemmin Get-AppRoleAssignment)* <br> Set-PowerAppRoleAssignment *(aiemmin Set-AppRoleAssignment)* <br> Remove-PowerAppRoleAssignment *(aiemmin Remove-AppRoleAssignment)* |
| Työnkulun lukeminen, päivittäminen ja poistaminen | Get-Flow <br> Get-FlowRun <br> Enable-Flow <br> Disable-Flow <br> Remove-Flow |
| Työnkulun käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-FlowOwnerRole <br> Set-FlowOwnerRole <br> Remove-FlowOwnerRole |
| Työnkulun hyväksyntöjen lukeminen ja niihin vastaaminen | Get-FlowApprovalRequest <br> Get-FlowApproval <br> RespondTo-FlowApprovalRequest |
| Yhteyksien lukeminen ja poistaminen | Get-PowerAppConnection *(aiemmin Get-Connection)* <br> Remove-PowerAppConnection *(aiemmin Remove-Connection)* |
| Yhteyden käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-PowerAppConnectionRoleAssignment *(aiemmin Get-ConnectionRoleAssignment)* <br> Set-PowerAppConnectionRoleAssignment *(aiemmin Set-ConnectionRoleAssignment)* <br> Remove-PowerAppConnectionRoleAssignment *(aiemmin Remove-ConnectionRoleAssignment)* |
| Yhdistimien lukeminen ja poistaminen | Get-PowerAppConnector *(aiemmin Get-Connector)* <br> Remove-PowerAppConnector *(aiemmin Remove-Connector)* |
| Mukautettujen yhdistimien käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-PowerAppConnectorRoleAssignment *(aiemmin Get-ConnectorRoleAssignment)* <br> Set-PowerAppConnectorRoleAssignment *(aiemmin Set-ConnectorRoleAssignment)* <br> Remove-PowerAppConnectorRoleAssignment *(aiemmin Remove-ConnectorRoleAssignment)* |

## <a name="powerapps-cmdlets-for-administrators-preview"></a>PowerApps-cmdlet-komennot järjestelmänvalvojille (esiversio)

### <a name="prerequisite"></a>Edellytys
Jotta voit suorittaa järjestelmänvalvojan cmdlet-komentojen hallintatoimia, sinulla on oltava seuraavat käyttöoikeudet:

* Maksullisen PowerApps-palvelupaketin 2 käyttöoikeus tai PowerApps-palvelupaketin 2 kokeiluversion käyttöoikeus. Voit rekisteröityä 30 päivän maksuttoman kokeiluversion käyttäjäksi osoitteessa [http://web.powerapps.com/trial](http://web.powerapps.com/trial). Kokeiluversion käyttöoikeudet voi uusia, jos ne ovat vanhentuneet.

* [Office 365:n yleisen järjestelmänvalvojan](https://support.office.com/article/assign-admin-roles-in-office-365-for-business-eac4d046-1afd-4f1a-85fc-8219c79e1504) tai [Azure Active Directoryn yleisen järjestelmänvalvojan](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles-azure-portal) oikeudet ovat myös pakollisia, jos haluat tehdä hakuja toisen käyttäjän resursseihin. (Huomioi, että ympäristön järjestelmänvalvojilla on pääsy vain niihin ympäristöihin ja ympäristön resursseihin, joihin heillä on oikeudet.)

### <a name="cmdlet-list---admin-cmdlets"></a>Luettelo cmdlet-komennoista – Järjestelmänvalvojan cmdlet-komennot

| Tarkoitus | Cmdlet-komennot
| --- | ---
| Lue, päivitä ja poista ympäristöjä ja Common Data Service sovellusten tietokannoille | New-AdminPowerAppEnvironment <br> Set-AdminPowerAppEnvironmentDisplayName <br> Get-AdminPowerAppEnvironment *(aiemmin Get-AdminEnvironment)* <br> Remove-AdminPowerAppEnvironment *(aiemmin Remove-AdminEnvironment)* <br> New-AdminPowerAppCdsDatabase <br> Get-AdminPowerAppCdsDatabaseLanguages <br> Get-AdminPowerAppCdsDatabaseCurrencies <br> Get-AdminPowerAppEnvironmentLocations |
| CDS-tietokannan poistaminen | Remove-LegacyCDSDatabase **\*Uusi\*** | 
| Ympäristöjen oikeuksien lukeminen, päivittäminen ja poistaminen <br><br> *Nämä cmdlet-komennot toimivat tänään ainoastaan ympäristöissä, joissa ei ole Common Data Service for Apps -tietokantaa.* | Get-AdminPowerAppEnvironmentRoleAssignment *(aiemmin Get-AdminEnvironmentRoleAssignment)* <br> Set-AdminPowerAppEnvironmentRoleAssignment *(aiemmin Set-AdminEnvironmentRoleAssignment)* <br> Remove-AdminPowerAppEnvironmentRoleAssignment *(aiemmin Remove-AdminEnvironmentRoleAssignment)* |
| Kaaviosovellusten lukeminen, päivittäminen ja poistaminen | Get-AdminPowerApp *(aiemmin Get-AdminApp)* <br> Remove-AdminPowerApp *(aiemmin Remove-AdminApp)* <br> Get-AdminPowerAppConnectionReferences <br> Set-AdminPowerAppAsFeatured <br> Clear-AdminPowerAppAsFeatured <br> Set-AdminPowerAppAsHero <br> Clear-AdminPowerAppAsHero <br> Set-AdminPowerAppApisToBypassConsent <br> Clear-AdminPowerAppApisToBypassConsent |
| Kaaviosovelluksen käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminPowerAppRoleAssignment *(aiemmin Get-AdminAppRoleAssignment)* <br> Remove-AdminPowerAppRoleAssignment *(aiemmin Remove-AdminAppRoleAssignment)* <br> Set-AdminPowerAppRoleAssignment *(aiemmin Set-AdminAppRoleAssignment)* <br> Set-AdminPowerAppOwner *(aiemmin Set-AdminAppOwner)* |
| Työnkulkujen lukeminen, päivittäminen ja poistaminen | Get-AdminFlow <br> Enable-AdminFlow <br> Disable-AdminFlow <br> Remove-AdminFlow <br> Remove-AdminFlowApprovals |
| Työnkulun käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminFlowOwnerRole <br> Set-AdminFlowOwnerRole <br> Remove-AdminFlowOwnerRole |
| Yhteyksien lukeminen ja poistaminen | Get-AdminPowerAppConnection *(aiemmin Get-AdminConnection)* <br> Remove-AdminPowerAppConnection *(aiemmin Remove-AdminConnection)* |
| Yhteyden käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminPowerAppConnectionRoleAssignment *(aiemmin Get-AdminConnectionRoleAssignment)* <br> Set-AdminPowerAppEnvironmentConnectionRoleAssignment *(aiemmin Set-AdminConnectionRoleAssignment)* <br> Remove-AdminPowerAppConnectionRoleAssignment *(aiemmin Remove-AdminConnectionRoleAssignment)* |
| Mukautettujen liittimien lukeminen ja poistaminen | Get-AdminPowerAppConnector *(aiemmin Get-AdminConnector)* <br> Remove-AdminPowerAppConnector *(aiemmin Remove-AdminConnector)* |
| Mukautettujen yhdistimien käyttöoikeuksien lukeminen, päivittäminen ja poistaminen | Get-AdminPowerAppConnectorRoleAssignment *(aiemmin Get-AdminConnectorRoleAssignment)*<br> Set-AdminPowerAppConnectorRoleAssignment *(aiemmin Set-AdminConnectorRoleAssignment)* <br> Remove-AdminPowerAppConnectorRoleAssignment *(aiemmin Remove-AdminConnectorRoleAssignment)* |
| PowerAppsin käyttäjäasetusten, käyttäjäsovelluksen asetusten ja ilmoitusten lukeminen | Get-AdminPowerAppsUserDetails |
| Sellaisten käyttäjän Microsoft Flow -asetusten lukeminen ja poistaminen, jotka eivät näy käyttäjälle, mutta jotka tukevat työnkulun suorittamista | Get-AdminFlowUserDetails <br> Remove-AdminFlowUserDetails |
| Tietojen menetyksen estämiskäytäntöjen luominen, lukeminen, päivittäminen ja poistaminen organisaatiossasi | Get-AdminDlpPolicy *(aiemmin Get-AdminApiPolicy)* <br> New-AdminDlpPolicy *(aiemmin Add-AdminApiPolicy)* <br> Remove-AdminDlpPolicy *(aiemmin Remove-AdminApiPolicy)* <br> Set-AdminDlpPolicy *(aiemmin Set-AdminApiPolicy)* <br> Add-ConnectorToBusinessDataGroup <br>  Remove-ConnectorFromBusinessDataGroup <br/>Add-CustomConnectorToPolicy<br/> Remove-CustomConnectorFromPolicy|

## <a name="tips"></a>Vinkkejä

- Komennolla Get-Help ‘Cmdlet-komennonNimi’ saat luettelon esimerkeistä.

     ![Get-Help-komento](media/get-help-cmdlet.png "Get-Help-komento")

- Voit selata käytettävissä olevia syötetunnisteita painamalla sarkainnäppäintä, kun olet kirjoittanut yhdysmerkin (-) cmdlet-komennon nimen perään.

Esimerkkikomennot:

```
Get-Help Get-AdminPowerAppEnvironment
Get-Help Get-AdminPowerAppEnvironment -Examples
Get-Help Get-AdminPowerAppEnvironment -Detailed
```

## <a name="operation-examples"></a>Toimintoesimerkkejä

Alla on joitakin yleisiä skenaarioita, joissa esitellään uusien ja vanhojen PowerApps-cmdlet-komentojen käyttöä.

- [Ympäristökomennot](#environments-commands)
- [PowerApps-komennot](#powerapps-commands)
- [Flow-komennot](#flow-commands)
- [Ohjelmointirajapintayhteyskomennot](#api-connection-commands)
- [Tietojen menetyksen estokäytännön (DLP) komennot](#data-loss-prevention-dlp-policy-commands)

### <a name="environments-commands"></a>Ympäristökomennot

Näiden komentojen avulla voit hakea tietoa vuokraajan ympäristöistä ja päivittää niitä.

#### <a name="display-a-list-of-all-environments"></a>Kaikkien ympäristöjen luettelon näyttäminen

```
Get-AdminPowerAppEnvironment
```

Palauttaa luettelon kaikista vuokraajassa olevista ympäristöistä sekä kunkin ympäristön yksityiskohtaiset tiedot (esim. ympäristön nimen (GUID-tunnus), näyttönimen, sijainnin, tekijän jne.).

#### <a name="display-details-of-your-default-environment"></a>Oletusympäristön tietojen näyttäminen

```
Get-AdminPowerAppEnvironment –Default
```

Palauttaa vain vuokraajan oletusympäristön tiedot.

#### <a name="display-details-of-a-specific-environment"></a>Tietyn ympäristön tietojen näyttäminen

```
Get-AdminPowerAppEnvironment –EnvironmentName ‘EnvironmentName’
```

**Huomautus**: *EnvironmentName*-kenttä on yksilöllinen tunniste ja eri asia kuin *DisplayName* (ks. seuraavan kuvan tuloksen ensimmäinen ja toinen kenttä).

![Get-AdminEnvironment-komento](media/get-adminenvironment.png "Get-AdminEnvironment-komento")

### <a name="powerapps-commands"></a>PowerApps-komennot

Näillä komennoilla luetaan ja muokataan vuokraajan PowerApps-tietoja.

#### <a name="display-a-list-of-all-powerapps"></a>Kaikkien PowerApps-sovellusten luettelon näyttäminen

```
Get-AdminPowerApp
```

Palauttaa luettelon kaikista vuokraajan PowerApps-sovelluksista ja niiden tiedoista (esim. sovelluksen nimi (GUID-tunnus), näyttönimi, tekijä jne.).

#### <a name="display-a-list-of-all-powerapps-that-match-the-input-display-name"></a>Kaikkien annettua näyttönimeä vastaavien PowerApps-sovellusten luettelon näyttäminen

```
Get-AdminPowerApp 'DisplayName'
```

Palauttaa luettelon kaikista näyttönimeä vastaavista vuokraajan PowerApps-sovelluksista. 

**Huomautus**: Käytä lainausmerkkejä (”) välilyöntejä sisältävien syötearvojen ympärillä.

#### <a name="feature-an-application"></a>Sovelluksen esittely

```
Set-AdminPowerAppAsFeatured –AppName 'AppName'
```

Esitellyt sovellukset ryhmitellään ja nostetaan PowerApps-mobiiliohjelman luettelon yläreunaan.

**Huomautus**: Kuten ympäristöissäkin, *AppName* on yksilöllinen tunniste ja eri asia kuin *DisplayName*. Jos haluat tehdä näyttönimeen perustuvia toimintoja, voit käyttää putkittamista tietyissä funktioissa (ks. seuraava funktio).

#### <a name="make-an-application-a-hero-app-using-the-pipeline"></a>Sovelluksen muuntaminen Hero-sovellukseksi putkittamisen avulla

```
Get-AdminPowerApp 'DisplayName' | Set-AdminPowerAppAsHero
```

Hero-sovellus näkyy PowerApps-mobiiliohjelman luettelon yläreunassa. Hero-sovelluksia voi olla vain yksi.

Putki (jota merkitään |-merkillä kahden cmdlet-komennon välissä) ottaa ensimmäisen cmdlet-komennon tulosarvon ja käyttää sitä toisen funktion syöttöarvona, olettaen, että funktio on kirjoitettu niin, että se voi hyödyntää putkittamista.

**Huom.** Sovelluksen on oltava esitelty sovellus ennen Hero-sovellukseksi muuttamista.

#### <a name="display-the-number-of-apps-each-user-owns"></a>Kunkin käyttäjän omistamien sovellusten lukumäärän näyttäminen

```
Get-AdminPowerApp | Select –ExpandProperty Owner | Select –ExpandProperty displayname | Group
```

Voit käsitellä tietoja vieläkin perusteellisemmin yhdistämällä PowerShell-alkuperäisfunktioita PowerApps-cmdlet-komentoihin. Tässä käytetään Select-funktiota erottamaan Owner-määrite (objekti) Get-AdminApp-objektista. Sitten omistajaobjektin nimi eristetään putkittamalla sen antama tulos toiseen Select-funktioon. Kun toisen Select-funktion tulos siirretään Group-funktioon, saadaan taulukko, jossa on kunkin omistajan sovellusten lukumäärä.

![Get-AdminPowerApp-komento](media/get-adminpowerapp.png "Get-AdminPowerApp-komento")

#### <a name="display-the-number-of-apps-in-each-environment"></a>Kunkin ympäristön sovellusten lukumäärän näyttäminen

```
Get-AdminPowerApp | Select -ExpandProperty EnvironmentName | Group | %{ New-Object -TypeName PSObject -Property @{ DisplayName = (Get-AdminPowerAppEnvironment -EnvironmentName $_.Name | Select -ExpandProperty displayName); Count = $_.Count } }
```

![Get-AdminPowerApp-komento](media/get-adminpowerapp-environment.png "Get-AdminPowerApp-komento")

#### <a name="download-powerapps-user-details"></a>PowerApps-käyttäjien tietojen lataaminen

```
Get-AdminPowerAppsUserDetails -OutputFilePath '.\adminUserDetails.txt' –UserPrincipalName ‘admin@bappartners.onmicrosoft.com’
```

Yllä oleva komento tallentaa PowerApps-käyttäjätiedot (peruskäyttötiedot käyttäjästä täydellisen käyttäjänimen kautta) määritettyyn tekstitiedostoon. Jos annetulla nimellä ei löydy tiedostoa, komento luo uuden tiedoston. Jos tiedosto on olemassa, komento korvaa sen.

#### <a name="set-logged-in-user-as-the-owner-of-a-powerapp"></a>Kirjautuneen käyttäjän määrittäminen PowerApp-sovelluksen omistajaksi

```
Set-AdminPowerAppOwner –AppName 'AppName' -AppOwner $Global:currentSession.userId –EnvironmentName 'EnvironmentName'
```

Antaa PowerApp-sovelluksen omistajan roolin senhetkiselle käyttäjälle ja määrittää alkuperäiselle omistajalle voi tarkastella -roolityypin.

**Huomautus**: AppName- ja EnvironmentName-kentät ovat yksilöiviä tunnisteita (GUID). Näyttönimet eivät ole.

### <a name="flow-commands"></a>Flow-komennot

Näiden komentojen avulla voit tarkastella ja muokata Microsoft Flow -tietoja.

#### <a name="display-all-flows"></a>Kaikkien työnkulkujen näyttäminen

```
Get-AdminFlow
```

Palauttaa luettelon kaikista vuokraajan työnkuluista.

#### <a name="display-flow-owner-role-details"></a>Työnkulun omistajaroolin tietojen näyttäminen

```
Get-AdminFlowOwnerRole –EnvironmentName 'EnvironmentName' –FlowName ‘FlowName’
```

Palauttaa määritetyn työnkulun omistajan tiedot.

**Huomautus**: Kuten *Ympäristöt*- ja *PowerApps*-komennoissa, *FlowName* on yksilöivä tunniste (GUID) ja eri asia kuin työnkulun näyttönimi.

#### <a name="display-flow-user-details"></a>Työnkulun käyttäjätietojen näyttäminen

```
Get-AdminFlowUserDetails –UserId $Global:currentSession.userId
```

Palauttaa työnkulun käyttöä koskevat tiedot. Tässä esimerkissä syötteenä käytetään PowerShell-istunnon kirjautuneen käyttäjän käyttäjätunnusta.

#### <a name="remove-flow-user-details"></a>Työnkulun käyttäjätietojen poistaminen

```
Remove-AdminFlowUserDetails –UserId 'UserId'
```

Poistaa työnkulun käyttäjän tiedot kokonaan Microsoftin tietokannasta. Kaikki käyttäjän omistamat työnkulut tulee poistaa ennen työnkulun käyttäjätietojen tyhjentämistä.

**Huomautus**: UserId-kenttä on käyttäjän Azure Active Directory -tietueen objektitunnus, joka löytyy [Azure-portaalista](https://portal.azure.com) kohdasta **Azure Active Directory** > **Käyttäjät** > **Profiili** > **Objektitunnus**. Tietojen tarkastelu tätä kautta edellyttää, että olet järjestelmänvalvoja.

#### <a name="export-all-flows-to-a-csv-file"></a>Kaikkien työnkulkujen vieminen CSV-tiedostomuotoon

```
Get-AdminFlow | Export-Csv -Path '.\FlowExport.csv'
```

Vie kaikki vuokraajan työnkulut taulukkomuotoiseen .csv-tiedostoon.

### <a name="api-connection-commands"></a>Ohjelmointirajapintayhteyskomennot

Tarkastele ja hallinnoi vuokraajan ohjelmointirajapintayhteyksiä.

#### <a name="display-all-native-connections-in-your-default-environment"></a>Oletusympäristön kaikkien alkuperäisten yhteyksien näyttäminen

```
Get-AdminPowerAppEnvironment -Default | Get-AdminConnection
```

Näyttää luettelon kaikista oletusympäristön ohjelmointirajapintayhteyksistä. Alkuperäiset yhteydet löytyvät tekijäportaalin **Tietoyhteydet** > **-välilehdestä**.

#### <a name="display-all-custom-connectors-in-the-tenant"></a>Kaikkien vuokraajan mukautettujen yhdistimien näyttäminen

```
Get-AdminPowerAppConnector
```

Palauttaa luettelon kaikkien vuokraajan mukautettujen yhdistimien tiedoista.

### <a name="data-loss-prevention-dlp-policy-commands"></a>Tietojen menetyksen estokäytännön (DLP) komennot

Näillä cmdlet-komennoilla voit määrittää vuokraajan DLP-käytännöt.

#### <a name="display-all-policies"></a>Kaikkien käytäntöjen näyttäminen

```
Get-AdminDlpPolicy
```

Palauttaa kaikkien käytäntöjen luettelon.

#### <a name="display-a-filtered-list-of-policies"></a>Suodatetun käytäntöluettelon näyttäminen

```
Get-AdminDlpPolicy 'DisplayName'
```

Suodattaa käytännöt näyttönimen mukaan

#### <a name="display-all-business-data-only-api-connectors-in-a-policy"></a>Käytännön kaikkien Vain yritystiedot -ohjelmointirajapintayhteyksien näyttäminen

```
Get-AdminDlpPolicy 'PolicyName' | Select –ExpandProperty BusinessDataGroup
```

Näyttää luettelon kaikista ohjelmointirajapintayhteyksistä, jotka ovat annetun käytännön *Vain yritystiedot* (tai *BusinessDataGroup*) -kentässä.

#### <a name="add-a-connector-to-the-business-data-only-group"></a>Yhdistimen lisääminen Vain yritystiedot -ryhmään

```
Add-ConnectorToBusinessDataGroup -PolicyName 'PolicyName' –ConnectorName 'ConnectorName'
```

Lisää yhdistimen annetun DLP-käytännön Vain yritystiedot -ryhmään. Katso luettelo yhdistimistä *DisplayName*- ja *ConnectorName*-arvojen (käytetty syötteenä) mukaan täältä.

## <a name="version-history"></a>Versiohistoria
| Versio | Date | Päivitykset |
| --- | --- | --- |
| 1.0 | 23.4.2018 | <ol> <li> PowerAppsin cmdlet-komentojen ensijulkaisu sovelluskehittäjille (esiversio) sisältää cmdlet-hallintakomennot ympäristöille, sovelluksille, työnkuluille, työnkulun hyväksynnille, yhteyksille ja mukautetuille liittimille </li> <li> PowerAppsin cmdlet-komentojen ensijulkaisu järjestelmänvalvojille (esiversio) sisältää cmdlet-hallintakomennot ympäristöille, sovelluksille ja työnkuluille </li></ol>|
| 2.0 | 24.5.2018 | <ol> <li> Pieniä ohjelmavirhekorjauksia sovelluskehittäjien ja järjestelmänvalvojien cmdlet-komentoihin </li> <li> Seuraavat uudet cmdlet-hallintakomennot on lisätty: <br> Get-AdminConnection <br> Remove-AdminConnection <br> Get-AdminConnectionRoleAssignment <br> Set-AdminConnectionRoleAssignment <br>Remove-AdminConnectionRoleAssignment <br>Get-AdminConnector  <br>Remove-AdminConnector <br>Set-AdminConnectorRoleAssignment  <br>Get-AdminConnectorRoleAssignment  <br>Remove-AdminConnectorRoleAssignment <br>Get-AdminPowerAppsUserDetails <br>Get-AdminFlowUserDetails <br>Remove-AdminFlowUserDetails <br>Get-AdminApiPolicy  <br>Add-AdminApiPolicy <br>Remove-AdminApiPolicy <br>Set-AdminApiPolicy <br>Add-ConnectorToBusinessDataGroup  <br>Remove-ConnectorFromBusinessDataGroup </li> </ol>
| 3.0 | 30.7.2018 | <ol> <li> Lisätty mahdollisuus välittää tunnistetiedot Add-PowerAppsAccount-komentoon (toistuvien komentosarjojen mahdollistamiseksi) </li> <li>  Pieniä ohjelmavirhekorjauksia sovelluskehittäjien ja järjestelmänvalvojien cmdlet-komentoihin </li> <li> Lisätty etuliite PowerApp tai Flow jokaiseen cmdlet-komentoon sovelluskehittäjiä varten </li> <li>  Lisätty etuliite AdminPowerApp tai AdminFlow jokaiseen cmdlet-komentoon järjestelmänvalvojia varten </li> <li> Seuraavat uudet cmdlet-hallintakomennot on lisätty: <br> New-AdminPowerAppEnvironment <br> Set-AdminPowerAppEnvironmentDisplayName <br> New-AdminPowerAppCdsDatabase <br> Get-AdminPowerAppCdsDatabaseLanguages <br> Get-AdminPowerAppCdsDatabaseCurrencies <br> Get-AdminPowerAppEnvironmentLocations <br> Get-AdminPowerAppConnectionReferences <br> Set-AdminPowerAppAsFeatured <br> Clear-AdminPowerAppAsFeatured <br> Set-AdminPowerAppAsHero <br> Clear-AdminPowerAppAsHero <br> Set-AdminPowerAppApisToBypassConsent <br> Clear-AdminPowerAppApisToBypassConsent <br> Remove-AdminFlowApprovals </li></ol>
| 4.0 | 15.8.2018 | Lisätty valinnainen parametri New-AdminPowerAppCdsDatabase-komentoon, jotta funktio on synkroninen oletusarvoisesti (eli se ei palaudu ennen kuin tietokanta on valmisteltu)
| 5.0 | 24.8.2018 | Korjattu ongelma, jossa Flow-järjestelmänvalvojan cdmlet-komennot eivät palauttaneet tietoja suojausasetusten perusteella
| 6.0 | 9.1.2019 | <ol><li>Cmdlet-komennot ovat nyt käytettävissä PowerShell-valikoimassa kahdessa eri moduulissa: järjestelmänvalvojan ja tekijän.</li> <li>Lisätty järjestelmänvalvojan cmdlet-komento: Remove-LegacyCDSDatabase</li><li> Lisätty toimintoesimerkkejä</li><li>Lisätty mahdollisuus hallinnoida HTTP-yhdistimiä ja mukautettuja yhdistimiä tietojen menetyksen estämisessä (DLP)</li></ol>|

## <a name="questions"></a>Onko sinulla kysyttävää?

Jos sinulla on kommentteja, ehdotuksia tai kysymyksiä, voit lähettää ne [Administering PowerApps -yhteisötauluun](https://powerusers.microsoft.com/t5/Administering-PowerApps/bd-p/Admin_PowerApps).
