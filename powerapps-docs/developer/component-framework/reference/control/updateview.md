---
title: updateView | MicrosoftDocs
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: reference
applies_to: Dynamics 365 (online)
ms.assetid: 899d6eb3-62b4-4c1f-947c-aed1f8643caa
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: d7ac81ef617aa4e9e3564ade01bc469b0d7f5bc8
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345332"
---
# <a name="updateview"></a>updateView

[!INCLUDE[./includes/updateview-description.md](./includes/updateview-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="syntax"></a>Syntaksi

`updateView(context)`

## <a name="parameters"></a>Parametrit

| Parametrin nimi|Tyyppi|Pakollinen|Kuvaus|
| ------------- |----|--------|-----------|
|kontekstissa|`context`|kyllä|Sisältää arvot, jotka mukauttaja on määrittänyt luettelossa määritettyyn nimeen, sekä apuohjelma funktioihin|

## <a name="example"></a>Esimerkki

```JavaScript
MyNameSpace.JSHelloWorldControl.prototype.updateView = function (context) {
    this._labelElement.innerText = "Hello World! (JS)";
};
```

## <a name="remarks"></a>Huomautuksia

Määrittää kentän osan arvoksi määritetyn kentän raakaarvon


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Ohjausobjekti](../control.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)