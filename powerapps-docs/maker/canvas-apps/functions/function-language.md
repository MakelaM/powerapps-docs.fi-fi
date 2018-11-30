---
title: Kieli-funktio | Microsoft Docs
description: Tietoa PowerAppsin Kieli-funktiosta, mukaan lukien syntaksi ja joitakin esimerkkejä
author: gregli-msft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 10/16/2016
ms.author: gregli
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 45ffd324ff5409a49f1ec8c4c8ea3529c1cf5c5f
ms.sourcegitcommit: 429b83aaa5a91d5868e1fbc169bed1bac0c709ea
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 08/24/2018
ms.locfileid: "42833282"
---
# <a name="language-function-in-powerapps"></a>PowerAppsin Kieli-funktio
Palauttaa nykyisen käyttäjän kielitunnisteen.

## <a name="description"></a>Kuvaus
**Kieli**-funktio palauttaa nykyisen käyttäjän kielen, komentosarjan ja alueen kielitunnisteena.

Kielitietojen avulla voit tehdä sovelluksestasi paikallisen version.  Jos esimerkiksi olet luomassa sovellusta, jota käytetään Italiassa ja Ranskassa, voit määrittää **Kieli**-funktion avulla merkkijonot näkymään automaattisesti kunkin alueen paikallisella kielellä. 

### <a name="language-tags"></a>Kielitunnisteet
*Kielitunnisteen* muotoilussa voidaan käyttää seuraavia kolmea vaihtoehtoa:

| Palautusarvo | Kuvaus |
| --- | --- |
| **"*lg&#8209;RE*"** |*lg* on kielen kaksikirjaiminen lyhenne ja *RE* alueen kaksikirjaiminen lyhenne.  Tämä on yleisin palautustyyppi.  Esimerkiksi Ison-Britannian kielitunnisteena palautetaan ”en-GB”. |
| **"*lg*"** |*lg* on kielen kaksikirjaiminen lyhenne.  Tätä muotoa käytetään, kun PowerApps tietää kielen, mutta ei aluetta. |
| **"*lg&#8209;scrp&#8209;RE*"** |*lg* on kielen kaksikirjaiminen lyhenne, *scrp* komentorivin nelikirjaiminen lyhenne ja *RE* alueen kaksikirjaiminen lyhenne. |

PowerApps käyttää kielitunnisteen muotoa [IETF BCP-47 ](https://tools.ietf.org/html/bcp47).  

Voit tarkastella tuettujen kielitunnisteiden luetteloa kirjoittamalla kaavariville tai lisänäkymään **Value( "1", )** ja selaamalla toiselle argumentille ehdotettuja kielialueita.  

Myös **[Teksti](function-text.md)**- ja **[Arvo](function-value.md)**-funktiot käyttävät kielen tunnisteita.  Näiden funktioiden avulla voit kääntää merkkijonoja globaalisti toimivalla tavalla.  Kun välität näihin funktioihin kielitunnisteen, mutta alueella ei ole merkitystä, voit käyttää tunnisteen pelkkää kieliosaa.

## <a name="syntax"></a>Syntaksi
**Language**()

## <a name="examples"></a>Esimerkkejä
### <a name="users-locale"></a>Käyttäjän aluekohtaiset asetukset
Oletuksena on, että isäntäkäyttöjärjestelmä tai -selain käyttävät sijaintipaikan oletuskieltä.

| Kaava | Sijainti | Palautusarvo |
| --- | --- | --- |
| **Language()** |Lissabon, Portugali |"pt-PT" |
| **Language()** |Rio de Janeiro, Brasilia |"pt-PT" |
| **Language()** |Atlanta, USA |"en-US" |
| **Language()** |Manchester, Iso-Britannia |"en-GB" |
| **Language()** |Pariisi, Ranska |"fr-FR" |
| **Language()** |Roseau, Dominica |"en" |
| **Language()** |Belgrad, Serbia |”sr-cyrl – RS” tai ”sr-latn – RS”, käyttäjän järjestelmän asetusten mukaan |

### <a name="localization-table"></a>Lokalisointitaulukko
Yksinkertainen lokalisointimenetelmä on luoda Excel-taulukko, joka yhdistetään tekijän määrittämällä tunnuksella (**TextID**) käyttäjän kielelle käännettyyn tekstiin.  Taulukon pohjana voi käyttää
kokoelmaa tai mitä tahansa muuta tietolähdettä, mutta valitsimme Excelin, koska kääntäjien on helppo muokata ja hallita sitä sovelluksen ulkopuolella.

1. Luo Excelissä seuraava taulukko: 
   
    ![](media/function-language/loc-table.png)
   
    Jos jollakin kielellä ei ole olemassa tiettyä tekstimerkkijonoa, sen tilalla käytetään **Kieli**-sarakkeessa olevaa *tyhjää* merkintää. Tämän merkinnän täytyy esiintyä kaikkien muiden tietylle tekstitunnukselle (**TextID**) varattujen merkintöjen perässä.
   
    Näitä tarkoituksia varten tarvitsemme vain kielen, emme aluetta.  Jos alueelliset seikat olisivat tärkeitä, olisimme voineet lisätä yllä olevaan taulukkoon koko kielitunnisteen. 
2. Käytä **Lisää**-valintanauhan **Taulukko**-komentoa, jotta tästä muodostuu asianmukainen Excel-taulukko.  Oletusarvoinen nimi on **Taulukko1**, mutta voit muuttaa nimen käyttämällä **Taulukkotyökalut/Rakenne**- valintanauhaa ja kaukana vasemmassa reunassa olevaa **Taulukkonimi**-tekstiruutua.
3. Tallenna Excel-tiedosto paikalliseen tiedostojärjestelmään.   
4. Napsauta tai napauta PowerAppsin oikeanpuoleisessa ruudussa olevaa **Tietolähteet**-välilehteä ja napsauta tai napauta sitten **Lisää tietolähde**.
5. Napsauta tai napauta **Lisää sovellukseen staattisia tietoja** (Add static data to your app). Napsauta tai napauta tallentamaasi Excel-tiedostoa ja sitten **Avaa**.
6. Valitse luomasi taulukko ja napsauta tai napauta **Yhdistä**.

Siirry siihen sovelluksen kohtaan, jossa olisit aiemmin käyttänyt tekstiä **"Hello"**, ja käytä sen sijaan tätä kaavaa:

* **LookUp( Table1, TextID = "Hello" && (LanguageTag = Left( Language(), 2 ) || IsBlank( LanguageTag ))).LocalizedText**  

Tämä kaava hakee sopivan **LocalizedText**-arvon, joka on käännetty käyttäjän kielelle. Jos lokalisoitua arvoa ei löydy, kaava ottaa käyttöön oletusmuotoisen *tyhjän* version. 

Huomaa, että käännetyt merkkijonot voivat olla muissa kielissä huomattavasti pidempiä kuin omassa kielessäsi.  Monissa tapauksissa käyttöliittymäsi merkkijonot näyttävien selitteiden ja muiden elementtien täytyy olla suurempia.

### <a name="translation-service"></a>Käännöspalvelu
Voit kääntää tekstiä tarpeen mukaan käyttämällä käännöspalvelua, kuten Microsoft Translatoria:  

1. Napsauta tai napauta PowerAppsin oikeanpuoleisessa ruudussa olevaa **Tietolähteet**-välilehteä ja napsauta tai napauta sitten **Lisää tietolähde**.
2. Napsauta tai napauta **Microsoft Translator**.

Siirry siihen sovelluksen kohtaan, jossa olisit aiemmin käyttänyt tekstiä **”Hello”**, ja käytä sen sijaan tätä kaavaa:

* **MicrosoftTranslator.Translate( "Hello", Language() )**

Microsoft Translator-palvelu käyttää samoja kielitunnisteita, jotka **Kieli**-funktio palauttaa.

Tähän menetelmään liittyy joitakin haittapuolia verrattuna edelliseen esimerkkiin, jossa käytettiin valmista käännöstaulukkoa:

* Kääntämiseen kuluu aikaa, sillä palvelu on kutsuttava verkon yli.  Tämä aiheuttaa viiveen ennen kuin käännetty teksti näkyy sovelluksessasi. 
* Käännöksestä tulee mekaaninen, ja se ei välttämättä täytä odotuksiasi tai ole paras mahdollinen ratkaisu sovelluksen senhetkiseen käyttötarkoitukseen.

