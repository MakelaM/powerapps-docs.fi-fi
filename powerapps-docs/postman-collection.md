---
title: Mukautetun liittimen kuvaileminen Postman-kokoelmalla | Microsoft Docs
description: Luo Postman-kokoelma mukautettujen liittimien rekisteröimiseksi
services: ''
suite: powerapps
documentationcenter: ''
author: archnair
manager: anneta
editor: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 04/28/2017
ms.author: archanan
ms.openlocfilehash: fd060ff873ee376b7ca886f721d360372c1d13ed
ms.sourcegitcommit: 68eee592c351688e5d0bd458f33a70be507fa53f
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2018
ms.locfileid: "30987625"
---
# <a name="describe-a-custom-connector-with-postman"></a>Mukautetun liittimen kuvaileminen Postman-kokoelmalla
[Postman](https://www.getpostman.com/) on työkalu, jonka avulla API-kehitystyö on nopeampaa ja helpompaa. Tässä opetusohjelmassa näytetään, miten voit luoda Postman-kokoelman, jota voit käyttää luodaksesi [mukautettuja liittimiä ](register-custom-api.md) helposti PowerAppsissa.

## <a name="prerequisites"></a>Edellytykset
* Asenna [Postman-sovellus](https://www.getpostman.com/apps)

## <a name="create-a-postman-collection"></a>Luo Postman-kokoelma
Luomme Postman-kokoelman Azuren kognitiivisten palvelujen [tekstianalyysin ohjelmointirajapinnalle](https://www.microsoft.com/cognitive-services/en-us/text-analytics-api). Tämä ohjelmointirajapinta tunnistaa kielen, asenteen ja tärkeimmät sanaryhmät tekstissä, jonka välität sille.

1. Postman-kokoelman luonnin ensimmäisessä vaiheessa luodaan pyyntö. Kun luot pyyntöä, voit asettaa HTTP-verbin, pyynnön URL-osoitteen, kyselyn tai polun parametrit, otsikot ja leipätekstin. Lue lisätietoja Postman-dokumentaation kohdasta [Pyyntöjen lähettäminen](https://www.getpostman.com/docs/requests). Aseta Detect Language API -päätepisteelle seuraavat arvot:
   
    ![Postman-pyyntö](./media/postman-collection/request.png)
   
    Käytettyjen parametrien ja arvojen tiedot:
   
   | Parametri | Arvo |
   | --- | --- |
   | Verbi |POST |
   | Pyynnön URL-osoite |https://westus.api.cognitive.microsoft.com/text/analytics/v2.0/languages |
   | Params |numberOfLanguagesToDetect |
   | Käyttöoikeuksien myöntäminen |"No Auth" |
   | Otsikot |Ocp-Apim-Subscription-Key = <your subscription key> <br/>Content-Type = application/json |
   | Leipäteksti |<code>{<br/>&nbsp;&nbsp;&nbsp;"documents": [<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"id": "1",<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"text": "Hello World"<br/>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}<br/>&nbsp;&nbsp;]<br/>}<code> |
2. Napsauta **Lähetä** tehdäksesi pyynnön ja saadaksesi vastauksen.
3. Tallenna pyyntö Postman-kokoelmaan napsauttamalla **Tallenna**.
   
    ![Postman-vastaus](./media/postman-collection/request-response-save.png)
4. Anna **Pyynnön nimi** ja **Pyynnön kuvaus** **Tallenna pyyntö** -valintaikkunassa. Käytät näitä arvoja mukautetussa liittimessäsi.
   
    ![Postman-kokoelman tallentaminen](./media/postman-collection/save-request-note.png)
   
    Voit tallentaa myös vastauksen pyyntöön. Mukautetut liittimet tukevat tällä hetkellä vain yhtä vastausta pyyntöä kohti. Jos tallennat useita vastauksia pyyntöä kohti, vain ensimmäistä käytetään.
   
    ![Postman-vastauksen tallentaminen](./media/postman-collection/save-response.png)
5. Jatka Postman-kokoelmasi luontia luomalla ja tallentamalla muita pyyntöjä ja vastauksia.
6. Kun olet suorittanut loppuun Postman-kokoelman luomisen kaikille pyynnöille ja vastauksille, vie kokoelma.
   
    ![Postman-kokoelman vienti](./media/postman-collection/export.png)
7. Valitse vientimuodoksi **Collection v1**.
   
    ![Postman-kokoelman vienti](./media/postman-collection/export2.png)

Voit nyt käyttää tätä Postman-kokoelmaa mukautetun liittimen luomiseen PowerAppsissa. Lue lisätietoja artikkelista [Mukautettujen liittimien rekisteröinti ja käyttö PowerAppsissa](register-custom-api.md). 

