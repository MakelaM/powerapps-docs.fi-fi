---
title: ShowError-toiminto | Microsoft Docs
description: ShowError-toiminnon viitetietoja PowerAppsissa mukaan lukien syntaksi ja esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 06/05/2018
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5e18b64910bbc7efca8c460100163e1a0716a089
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71992147"
---
# <a name="notify-function-in-powerapps"></a>PowerAppsin Ilmoita-funktio
Näyttää ilmoitussanoman käyttäjälle.

## <a name="description"></a>Kuvaus
**Notify**-funktio näyttää käyttäjälle ilmoitussanoman näytön yläreunassa parhaillaan näytettävän sisällön päällä.  

Sopivaa väriä ja kuvaketta käytetään sanoman tyypin mukaan.   Funktion toinen argumentti määrittää tyypin:

| NotificationType-argumentti | Kuvaus |
| --- | --- |
| **NotificationType.Error** | Näyttää sanoman virheenä. |
| **NotificationType.Information** (oletus) | Näyttää sanoman tietona.  |
| **NotificationType.Success** | Näyttää sanoman onnistumisena. |
| **NotificationType.Warning** | Näyttää sanoman varoituksena. |

Sanomat näkyvät, kun kehität sovellustasi ja kun käyttäjät käyttävät sovellustasi.

**Notify**-funktiota voidaan käyttää vain [toimintokaavoissa](../working-with-formulas-in-depth.md).

**Notify** voidaan yhdistää [**IfError**](function-iferror.md)-funktion kanssa havaitsemaan virheitä ja ilmoittamaan niistä mukautetulla virhesanomalla.

PowerApps voi lähettää myös palveluilmoituksia käyttämällä täysin **Notify**-funktiosta poikkeavaa tapaa.  Lisätietoja on artikkelissa [Ilmoituksen lähettäminen PowerAppsissa](../add-notifications.md).

**Notify** palauttaa aina arvon *true*.

Huomautus Tämä on aiemmin nimetty **showerror** -funktiolla, kun se saattoi näyttää vain virhe sanomia.

## <a name="syntax"></a>Syntaksi
**Notify**( *Message*, [ *NotificationType* ] )

* *Message* – Pakollinen.  Sanoma, joka näytetään käyttäjälle.
* *NotificationType* – Valinnainen.  Näytettävän sanoman tyyppi edellä olevasta taulukosta.  Oletus on **NotificationType.Information**.  

## <a name="examples"></a>Esimerkkejä

### <a name="step-by-step"></a>Vaihe vaiheelta

1. Lisää **painike**-ohjausobjekti näyttöön.

2. Määritä **painikkeen** **OnSelect**-ominaisuudeksi:

    **Notify( ”Hei maailma” )**

3. Napsauta tai paina painiketta.  

    Aina kun painiketta napsautetaan, käyttäjä näkee sanoman **Hei maailma** tietona.

    ![Kehitysympäristö, jossa painike näkyvillä.OnSelect kutsuu Notify-funktiota ja tuo näyttöön tuloksena saatavan Hei maailma -sanoman sinisenä ilmoitussanomana käyttäjälle](media/function-showerror/hello-world.png)

4. Muuta sanoman tyyppi ilmoittamaan virheestä.  Lisää toinen argumentti kaavaan:

    **Notify( ”Hei maailma”, NotificationType.Error )**

5. Napsauta tai paina painiketta.

    Aina kun painiketta napsautetaan, käyttäjä näkee nyt sanoman **Hei maailma** virheenä.

    ![Kehitysympäristö, jossa painike näkyvillä.OnSelect kutsuu Notify-funktiota ja tuo näyttöön tuloksena saatavan Hei maailma -sanoman punaisena ilmoitussanomana käyttäjälle](media/function-showerror/hello-world-error.png)

4. Muuta sanoman tyyppi antamaan varoituksen.  Muuta toista argumenttia kaavassa:

    **Notify( ”Hei maailma”, NotificationType.Warning )**

5. Napsauta tai paina painiketta.

    Aina kun painiketta napsautetaan, käyttäjä näkee nyt sanoman **Hei maailma** varoituksena.

    ![Kehitysympäristö, jossa painike näkyvillä.OnSelect kutsuu Notify-funktiota ja tuo näyttöön tuloksena saatavan Hei maailma -sanoman oranssina ilmoitussanomana käyttäjälle](media/function-showerror/hello-world-warning.png)

4. Muuta sanoman tyyppi ilmoittamaan onnistumisesta.  Muuta toista argumenttia kaavassa:

    **Notify( ”Hei maailma”, NotificationType.Success )**

5. Napsauta tai paina painiketta.

    Aina kun painiketta napsautetaan, käyttäjä näkee nyt sanoman **Hei maailma** onnistumisena.

    ![Kehitysympäristö, jossa painike näkyvillä.OnSelect kutsuu Notify-funktiota ja tuo näyttöön tuloksena saatavan Hei maailma -sanoman vihreänä ilmoitussanomana käyttäjälle](media/function-showerror/hello-world-success.png)
