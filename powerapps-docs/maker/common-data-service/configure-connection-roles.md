---
title: Yhteysroolien määrittäminen | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
- Dynamics 365 (online)
- Dynamics 365 Version 9.x
- PowerApps
ms.author: matp
manager: brycho
ms.openlocfilehash: 4faf195f1c751e3796267d52725c1cb753c4889d
ms.sourcegitcommit: aba996b1773ecdf62758e06b34eaf57bede29e08
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/08/2018
ms.locfileid: "39679915"
---
# <a name="configure-connection-roles"></a>Yhteysroolien määrittäminen

Common Data Service for Appsin avulla voit määrittää entiteettitietueiden väliset **yhteydet** ilman, että sinun tarvitsee luoda entiteettisuhdetta. Mallipohjaisten sovellusten käyttäjä voi muodostaa nimetyn linkin tietueiden välille, kun hän haluaa luoda vähemmän virallisen suhteen, joka ei vaadi oikean entiteettisuhteen käyttämistä. Joitakin esimerkkejä tästä ovat *ystävä*, *sisarus*, *puoliso*, *osallistuja* ja *sidosryhmä*. Jotkin yhteydet voivat olla myös vastavuoroisia, kuten *alikohde* ja *pääkohde*, *aviomies* ja *vaimo* tai *lääkäri* ja *potilas*.

Kun käyttäjä muodostaa yhteyden kahden tietueen välille, hän voi myös lisätä kuvauksen sekä muita tietoja, kuten suhteen alkamis- ja päättymispäivämäärän. Lisätietoja: [Yhteyksien luominen tietueiden välisten suhteiden määrittämiseksi ja tarkastelemiseksi](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)

Kaikki käyttäjät, joilla on kirjoitusoikeudet **Yhteysrooli**-entiteettiin, voivat määrittää ne yhteydet, joita muut käyttäjät voivat käyttää.

## <a name="view-connection-roles"></a>Yhteysroolien tarkasteleminen

CDS for Appsiin on määritetty useita vakioyhteysrooleja. Voit tarkastella niitä siirtymällä asetukset-alueeseen. 

### <a name="navigate-to-the-settings-area"></a>Asetukset-alueelle siirtyminen

1. Tarkastellessasi mallipohjaista sovellusta poista URL-osoitteesta kaikki `dynamics.com` -kohdan jälkeen ja päivitä sivu.
1. Siirry kohtaan **Asetukset** > **Liiketoiminta** > **Liiketoiminnan hallinta** ja valitse sitten **yhteysroolit**.

![Liiketoiminnan hallinta -asetusnäkymän yhteysroolit](media/navigate-settings-connection-roles.png)

Tässä näkymässä näet kaikki yhteysroolit, jotka ovat käytettävissä tässä ympäristössä, ja voit myös muokata niitä tässä.

> [!NOTE]
> Jos haluat jakaa yhteysrooleja ratkaisun yhteydessä, varmista, että ne sisältyvät ratkaisuun, jonka haluat jakaa. Lisätietoja: [Yhteysroolien lisääminen ratkaisuun](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>Yhteysroolien tarkasteleminen ratkaisunhallinnassa.

Koska yhteysroolit ovat *ratkaisun tunnistavia* – mikä tarkoittaa sitä, että ne voidaan sisällyttää ratkaisuun – voit myös lisätä yhteysrooleja jakamasi ratkaisuun.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Useimmat **Asetukset**-alueella näkyvistä yhteysrooleista määritetään *sisäisen* **Oletusratkaisun** sisällä (jota ei tule sekoittaa **Common Data Servicesin oletusratkaisuun**). Tämä sisäinen **Oletusratkaisu** sisältää kaikki järjestelmän mukautukset. Jos haluat tarkastella **Oletusratkaisua**, valitse **Kaikki ratkaisut - sisäinen** -näkymä.

## <a name="add-connection-roles-to-a-solution"></a>Yhteysroolien lisääminen ratkaisuun

Osien muokkaamista sisäisessä **Oletusratkaisussa** ei yleensä suositella. Voit käyttää **Lisää olemassa oleva** -komentoa **Common Data Servicesin oletusratkaisun** tai minkä tahansa luomasi ratkaisun sisällä tuodaksesi minkä tahansa oletusyhteysroolin ratkaisuusi.

![Olemassa olevan yhteysroolin lisääminen](media/add-existing-connection-role.png)

Kun lisäät yhteysroolin ratkaisuusi, voit muokata sitä missä tahansa, missä se on näkyvissä.

## <a name="create-or-edit-connection-roles"></a>Yhteysroolien luominen tai muokkaaminen.

> [!IMPORTANT]
> Jos aiot jakaa ratkaisun, joka sisältää uusia yhteysrooleja tai muutoksia aiemmin luotuihin yhteysrooleihin, sinun on lisättävä ne kyseiseen ratkaisuun. Kun muokkaat tai lisäät uusia yhteysrooleja **Asetukset**-alueessa, nämä yhteysroolit lisätään sisäiseen **Oletusratkaisuun** eikä niitä lisätä jakamaasi ratkaisuun ennen kuin lisäät ne sinne itse. Lisätietoja [Yhteysroolien lisääminen ratkaisuun](#add-connection-roles-to-a-solution)

Valitse **Yhteysroolit**-luettelosta yhteysrooli, jonka sisällä haluat tehdä muokkauksia.
Yhteysroolin määrittämiseen sisältyy kolme vaihetta, jotka näkyvät selvästi lomakkeessa.

![Luo yhteysrooli -lomake](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>Yhteysroolin kuvaileminen

Määritä seuraavat kentät:

|Kenttä|Kuvaus|
|--|--|
|**Nimi**|(Pakollinen) Yhteyttä kuvaava teksti.|
|**Yhteysrooliluokka**|Ryhmä, joka kuvaa yhteyden luokkaa. Lisätietoja: [Yhteysrooliluokan arvot](#connection-role-category-values)|
|**Kuvaus**|Kirjoita roolin määritelmä.|

#### <a name="connection-role-category-values"></a>Yhteysrooliluokan arvot

Oletusarvoiset **Yhteysrooliluokan** arvot ovat:
- Liiketoiminta
- Perheenjäsenet
- Yhteisöpalvelut
- Myynti
- Muu
- Sidosryhmä
- Myyntitiimi
- Palvelu

Voit lisätä uusia luokkia tai muokata olemassa olevia luokkia muokkaamalla **Luokan** yleistä asetusjoukkoa. Lisätietoja: [Yleisten asetusjoukkojen luominen ja muokkaaminen Common Data Service for Appsissa (valintaluettelot)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>Tietuetyyppien valitseminen

Valitse tietuetyypit, joihin voidaan muodostaa yhteys.

> [!NOTE]
> Vaikka oletusarvoinen valinta on **Kaikki**, mieti, mitkä tyypit ovat asianmukaisia yhteysroolille, jota olet lisäämässä.

### <a name="matching-connection-roles"></a>Vastaavat yhteysroolit

Tässä valinnaisessa vaiheessa voit määrittää ne roolit, joita sovelletaan vastavuoroisesti. Tämä ei ole pakollista, mutta yhteydet ovat merkityksellisempiä, jos nämä ovat määritetty.

Voit esimerkiksi määrittää, että Jaakko on Marjan *Ystävä*, mutta tarkoittaako tämä myös sitä, että Marja on Jaakon *Ystävä*? Toivottavasti asia on näin. Mutta jos Jaakko on Marjan *Isä*, tämä ei tarkoita sitä, että Marja olisi myös Jaakon *Isä*. Oikean vastavuoroisuuden määrittäminen edellyttää tätä ylimääräistä vaihetta.

Kun luot yhteysroolin, jolla ei ole vastaavaa yhteysroolia, rooli näytetään vain tarkasteltaessa yhteyttä tietueesta, jossa yhteys on käytössä. Tarkasteltaessa yhdistettyä tietuetta, rooli on tyhjä, ellei vastaavaa roolia ole määritetty.

Kun kyseessä on sellainen roolimääritys kuten *Ystävä*, *Puoliso*, *Työtoveri* tai *Sisarus*, kannattaa vastaava rooli määrittää itselleen. Jos yksi vastaava yhteysrooli on määritetty, otetaan tämä yksi vastaava yhteysrooli käyttöön molempisuuntaisesti.

> [!IMPORTANT]
> Sinun tulee tallentaa uusi yhteysrooli ilman tätä vastaavaa yhteysroolia, ennen kuin voit määrittää vastaavan yhteysroolin itselleen.

Tulet huomaamaan, että joillekin yhteysrooleille on jo määritetty vastaavia yhteysrooleja. *Entinen työntekijä* vastaa roolia *Entinen työnantaja* ja päinvastoin. Tällaiset yksi yhteen -tyyppiset vastaavat yhteysroolit ovat yleisimmin käytettyjä.

Voit määrittää useita vastaavia yhteysrooleja kuvaamaan monimutkaisia suhteita. Jos olet luonut yhteysroolin kuten *Isä*, voit määrittää kaksi lisäroolia kuten *Tytär* ja *Poika* ja sitten määrittää nämä molemmat *Isä*-roolin vastaaviksi yhteysrooleiksi. Sinun tulee samalla myös määrittää, että *Tytär*- ja *Poika*-yhteysroolit vastaavat *Isä*-roolia. Ja muista tietysti myös määrittää samankaltainen *Äiti*-rooli, joka vastaa *Tytär*- ja *Poika*-rooleja.

> [!TIP]
> Ennen kuin luot monimutkaisen yhteysroolien joukon, harkitse, riittäisikö yksinkertaisempi joukko rooleja. Esimerkiksi sen sijaan, että loisit monimutkaisen yhteysroolien joukon kuten *Isä*, *Äiti*, *Poika* ja *Tytär*, voisit harkita, riittäisikö pelkästään *Vanhempi* ja *Lapsi*.

Jos useampi kuin yksi vastaava yhteysrooli on määritetty, kyseiset yhteysroolit edustavat ainoita kelvollisia vastavuoroisia rooleja. Ensimmäinen asetetaan automaattisesti oletusarvoksi. Jos oletusarvo ei ole oikea, käyttäjien tulee muokata yhteyttä manuaalisesti ja valita kelvollisten, asetukseen määritettyjen vaihtoehtojen joukosta.

### <a name="see-also"></a>Katso myös
<!-- This is in the basics guide. It needs to be migrated -->
[Yhteyksien luominen tietueiden välisten suhteiden määrittämiseksi ja tarkastelemiseksi](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[Yleisten asetusjoukkojen luominen ja muokkaaminen Common Data Service for Appsissa (valintaluettelot)](create-edit-global-option-sets.md)<br />
[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)


