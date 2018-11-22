Package Deployer -työkalu on saatavilla [NuGet-pakettina](https://go.microsoft.com/fwlink/?linkid=859205). Voit käyttää Package Deployer -työkalua lataamalla ja purkamalla paketin tietokoneeseesi käyttämällä **nuget.exe**-tiedostoa.<br/><br/>

Lataa **nuget.exe** osoitteesta <https://www.nuget.org/downloads> ja tallenna se tietokoneeseesi, esimerkiksi polkuun **d:\\**. Seuraavaksi voit purkaa paketin sisällön tietokoneesi kansioon (esimerkiksi **PD**) suorittamalla komentokehotteessa seuraavan komennon:<br/>

`d:\nuget install Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf -Version [VERSION] -O d:\PD`<br/><br/>
    
Kun olet purkanut Package Deployer -työkalun, siirry kansioon `[ExtractedLocation]\tools`, josta löydät **PackageDeployer.exe**-tiedoston. 
