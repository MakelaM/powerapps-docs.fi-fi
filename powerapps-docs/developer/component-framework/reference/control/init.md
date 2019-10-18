---
title: init | MicrosoftDocs
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: reference
applies_to: ''
ms.assetid: 4485b7d4-c68f-4298-8676-1820eb33c1ad
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: 57a5ce0d4e930184bf42502f1dc16b6a648f1292
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345493"
---
# <a name="init"></a>init

[!INCLUDE[./includes/init-description.md](./includes/init-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="syntax"></a>Syntaksi

`init(context,notifyOutputChanged,state,container)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|kontekstissa|[Context](../context.md)|kyllä|Parametrit, komponentin metatiedot ja liittymä funktiot sisältävät *syöte ominaisuudet* .|
|notifyOutputChanged|`function`|ei|Menetelmä, joka ilmoittaa kehykselle, että sillä on uudet tuotokset|
|tila|`Dictionary`|ei|*Setcontrolstate* -kohteesta edellisessä istunnossa tallennettu komponentin tila|
|säilön|[HTMLDivElement](https://developer.mozilla.org/docs/Web/API/HTMLDivElement)|ei|Hahmontamisen div-elementit|

## <a name="example"></a>Esimerkki

```JavaScript
MyNameSpace.JSHelloWorldControl.prototype.init = function (context, notifyOutputChanged, state, container) {
    this._labelElement = document.createElement("label");
    this._labelElement.setAttribute("class", "JS_HelloWorldColor");
    container.appendChild(this._labelElement);
};
```

### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Ohjausobjekti](../control.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)
