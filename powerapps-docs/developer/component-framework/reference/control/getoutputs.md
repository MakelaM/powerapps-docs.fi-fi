---
title: Gettuotokset | MicrosoftDocs
manager: kvivek
ms.date: 10/01/2019
ms.service: powerapps
ms.topic: reference
applies_to: ''
ms.assetid: c83c3a09-f04e-4dc6-8ddf-ccd0b4cc080e
ms.author: nabuthuk
author: Nkrb
ms.openlocfilehash: 408633e1fd87c3c9517ec0984251bbbce056cc50
ms.sourcegitcommit: 2a3430bb1b56dbf6c444afe2b8eecd0e499db0c3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/12/2019
ms.locfileid: "72345378"
---
# <a name="getoutputs"></a>getOutputs

[!INCLUDE[./includes/getoutputs-description.md](./includes/getoutputs-description.md)]

## <a name="available-for"></a>Käytettävissä kohteelle 

Mallipohjaiset sovellukset ja pohjaan perustuvat sovellukset (kokeellinen esikatselu)

## <a name="syntax"></a>Syntaksi

`getOutputs()`

## <a name="remarks"></a>Huomautuksia

Tuloste sisältää arvon kullekin ominaisuudelle, joka on merkitty `input-output` tai `bound` luettelossa.
Jos luettelossa on esimerkiksi ominaisuus `value`, joka on `input-output`, ja haluat määrittää sen paikalliselle muuttujalle `myvalue` palautettava:

```javascript
{
    value: myvalue
}
```

## <a name="example"></a>Esimerkki

```javascript
MyControl.prototype.getOutputs = function () {
    var result = {
        value: this._value
    };
    return result;
};
```


### <a name="related-topics"></a>Aiheeseen liittyviä ohjeaiheita

[Ohjausobjekti](../control.md)<br/>
[PowerApps Component Framework-ohjelmointi raja pinnan viite](../../reference/index.md)<br/>
[PowerApps Component Frameworkin yleiskatsaus](../../overview.md)