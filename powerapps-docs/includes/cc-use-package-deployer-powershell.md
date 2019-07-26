---
ms.openlocfilehash: 215a6d9fb0890bd6d93843b0b649ada4203e5600
ms.sourcegitcommit: ad203331ee9737e82ef70206ac04eeb72a5f9c7f
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/18/2019
ms.locfileid: "67224193"
---
Package Deployer -työkalun PowerShell-tiedostot ovat nyt saatavilla [NuGet-pakettina](https://go.microsoft.com/fwlink/?linkid=859211). Käyttääksesi tiedostoja sinun on ladattava paketti tietokoneellesi ja purettava se **nuget.exe**-ohjelmalla.<br/><br/>

Lataa **nuget.exe** osoitteesta <https://www.nuget.org/downloads> ja tallenna se tietokoneellesi, esimerkiksi sijaintiin **d:\\** . Pura paketin sisältö tietokoneesi kansioon, kuten **PD-PowerShell**, suorittamalla seuraava komento:<br/>

`d:\nuget install Microsoft.CrmSdk.XrmTooling.PackageDeployment.PowerShell -Version [VERSION] -O d:\PD-PowerShell`<br/><br/>
    
Kun olet purkanut Package Deployer -työkalun PowerShell-tiedostot, siirry `[ExtractedLocation]\tools` -kansioon, joka sisältää tarvittavat tiedostot. 
