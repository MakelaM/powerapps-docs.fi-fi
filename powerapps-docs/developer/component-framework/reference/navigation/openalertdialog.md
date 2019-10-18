---
title: Openalertindialog | Microsoft Docs
description: ''
keywords: ''
ms.author: nabuthuk
author: Nkrb
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4acd3f17-74c0-4de1-9326-3778ff413f1e
ms.openlocfilehash: f1f5a2a78faf3dd9c6a1d6d197fab61772969084
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72342503"
---
# <a name="openalertdialog"></a>openAlertDialog

[!INCLUDE [openalertdialog-description](includes/openalertdialog-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset

## <a name="syntax"></a>Syntaksi

`context.navigation.openAlertDialog(alertStrings, options)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|Alertsstring|`AlertDialogStrings`|Kyllä|Hälytys valinta ikkunassa käytettävät merkki jonot. Alertddialogstring-määritteillä on seuraavat määritteet:<br/>- **teksti**: `string`. Ilmoitus valinta ikkunassa näytettävä viesti. <br/>- **Confirmbutton-otsikko**: `string`. Vahvista painikkeen nimi. Jos et määritä painikkeen otsikkoa, **OK** (käyttäjän ensisijaisella kielellä) on käytössä painikkeen nimenä.|
|asetukset|`AlertDialogOptions`|Kyllä|Valinta ikkunan asetukset. Alerutdialogoptions-kohteella on seuraavat määritteet:<br/>- **Korkeus**: `number`. Hälytys valinta ikkunan korkeus kuva pisteinä. <br/>- **Leveys**: `number`. Hälytys valinta ikkunan leveys kuva pisteinä|

## <a name="return-value"></a>Palautusarvo

Tyyppi: `Promise`

## <a name="remarks"></a>Huomautuksia

Tarkastele [lupausta](https://developer.mozilla.org/docs/Web/JavaScript/reference/Global_Objects/Promise) ja [tiedostoa](https://developer.mozilla.org/docs/Web/API/File)

## <a name="example"></a>Esimerkki 

```TypeScript
context.navigation.openAlertDialog({text:"This is an alert.", confirmButtonLabel : "Yes",}).then(
        function success()
        {
            document.getElementById("openAlertDialogButton")!.innerHTML = "Alert dialog closed";
        },
        function()
        {
            document.getElementById("openAlertDialogButton")!.innerHTML = "Error in Alert Dialog";
        }
    );
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Siirtyminen](../navigation.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)