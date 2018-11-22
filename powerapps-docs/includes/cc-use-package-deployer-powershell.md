Package Deployer -työkalun PowerShell -tiedostot ovat saatavilla [NuGet-pakettina](https://go.microsoft.com/fwlink/?linkid=859211). Voit ladata ja purkaa paketin tietokoneeseesi käyttämällä **nuget.exe**-tiedostoa.<br/><br/>

Lataa **nuget.exe** osoitteesta <https://www.nuget.org/downloads> ja tallenna se tietokoneeseesi, esimerkiksi polkuun **d:\\**. Seuraavaksi voit purkaa paketin sisällön tietokoneesi kansioon (esimerkiksi **PD-PowerShell**) suorittamalla komentokehotteessa seuraavan komennon:<br/>

`d:\nuget install Microsoft.CrmSdk.XrmTooling.PackageDeployment.PowerShell -Version [VERSION] -O d:\PD-PowerShell`<br/><br/>
    
Kun olet purkanut Package Deployer -työkalun PowerShell-tiedostot, siirry kansioon `[ExtractedLocation]\tools`, josta löydät tarvittavat tiedostot. 
