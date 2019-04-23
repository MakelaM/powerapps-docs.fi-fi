---
title: 'Kehittäjät: Parhaat käytännöt ja ohjeet laajennusten ja työnkulkujen kehittämiseen Common Data Servicessa | Microsoft Docs'
description: Parhaat käytännöt ja ohjeet laajennusten ja työnkulkujen kehittämiseen kehittäjille PowerAppsin Common Data Servicessa.
services: ''
suite: powerapps
documentationcenter: na
author: jowells
manager: austinj
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: article
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 1/15/2019
ms.author: jowells
search.audienceType:
- developer
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: 60e489ffd35f0e07f9a22f65336b242b7e0e2652
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61528408"
---
# <a name="best-practices-and-guidance-regarding-plug-in-and-workflow-development-for-the-common-data-service"></a>Parhaat käytännöt ja ohjeet laajennusten ja työnkulkujen kehittämiseen Common Data Servicessa

Tässä alla olevassa luettelossa on kaikki ohjeet ja parhaat käytännöt, jotka liittyvät laajennuksen ja työnkulun kehittämiseen Common Data Servicessa.

|Paras käytäntö  |Kuvaus  |
|---------|---------|
|[Vältä eräpyyntötyyppien käyttämistä laajennuksissa ja työnkulun toimissa](avoid-batch-requests-plugin.md)     |Sinun ei kannata käyttää ExecuteMultipleRequest- tai ExecuteTransactionRequest-viestipyyntöluokkia laajennuksen tai työnkulkutoiminnan yhteydessä.         |
|[Kehitä IPlugin-toteutukset tilattomiksi](develop-iplugin-implementations-stateless.md)     |Niiden luokkien jäsenet, jotka toteuttavat IPluginin, altistuvat mahdollisille säikeen turvallisuusongelmille, mikä voi johtaa tietojen epäyhtenäisyyteen tai suorituskykyongelmiin.         |
|[Älä tee kaksoiskappaletta laajennusvaiheen rekisteröinnistä](do-not-duplicate-plugin-step-registration.md)     |Laajennuksen vaiheen rekisteröinnin kaksoiskappale saa laajennuksen käynnistymään useita kertoja samassa viestissä tai tapahtumassa.         |
|[Sisällytä suodatusmääritteet laajennuksen rekisteröintiin](include-filtering-attributes-plugin-registration.md)     |Jos suodatusmääritteitä ei ole määritetty laajennusrekisteröintivaiheessa, laajennus suoritetaan aina, kun tapahtumassa esiintyy päivityssanoma.         |
|[Rajoita laajennusten rekisteröintejä Retrieve- ja RetrieveMultiple-sanomille](limit-registration-plugins-retrieve-retrievemultiple.md)     |Synkronisen laajennuksen logiikan lisääminen Retrieve- ja RetrieveMultiple-viestitapahtumiin voi hidastaa järjestelmää.         |
|[Optimoi mukautetun kokoonpanon kehitys](optimize-assembly-development.md)     |Harkitse erillisten laajennusten tai mukautettujen työnkulkuaktiviteettien yhdistämistä yhdeksi mukautetuksi kokoonpanoksi. Se parantaa suorituskykyä ja ylläpidettävyyttä. Siirrä laajennukset tai mukautetut työnkulkuaktiviteetit useaan mukautettuun kokoonpanoon, jos kokoonpanon koko on lähellä eristyksen kokoonpanon kokorajoitusta.         |
|[Määritä KeepAlive-asetukseksi false, kun käytetään ulkoisia isäntiä laajennuksessa](set-keepalive-false-interacting-external-hosts-plugin.md)     |Jos KeepAlive-ominaisuuden arvoksi on määritetty tosi HTTP-pyyntöotsikossa tai sitä ei ole eksplisiittisesti määritetty epätodeksi, laajennusten suoritusaika voi pidentyä.         |
|[Käytä InvalidPluginExecutionException-kohdetta laajennuksissa ja työnkulkutoimissa](use-invalidpluginexecutionexception-plugin-workflow-activities.md)     |Käytä InvalidPluginExecutionException-määritettä, kun keräät virheitä laajennuksen tai työnkulun toiminnan yhteydessä.         |

# <a name="see-also"></a>Katso myös
[Koodia käyttävän liiketoimintalogiikan käyttäminen](../../apply-business-logic-with-code.md)<br />
[Liiketoimintaprosessien laajentaminen laajennusten avulla](../../plug-ins.md)<br />
[Työnkulun laajennukset](../../workflow/workflow-extensions.md)<br />