---
title: Microsoft Translator -yhteyden yleiskatsaus | Microsoft Docs
description: Ohjeet Microsoft Translator -yhteyden luomiseen, muutama esimerkki ja kaikki funktiot
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 07/12/2017
ms.author: lanced
ms.openlocfilehash: c375429b7ac2341766c36ca58e1bbf3c78c9a6d1
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803393"
---
# <a name="connect-to-microsoft-translator-from-powerapps"></a>Yhdistä Microsoft Translatoriin PowerAppsista
![Microsoft Translator](./media/connection-microsoft-translator/translatoricon.png)

Näytä käännettyä tekstiä sovelluksesi **Selite**-ohjausobjektissa lisäämällä Microsoft Translator -liitin. Voit esimerkiksi luoda tekstiruudun, joka pyytää käyttäjää kirjoittamaan siihen käännettävää tekstiä. Käännetty teksti voidaan näyttää toisessa selitteessä.

Tässä aiheessa kerrotaan, miten voit muodostaa Microsoft Translator -yhteyden ja käyttää sitä sovelluksessa. Ohje sisältää myös luettelon käytettävissä olevista funktioista.

> [!NOTE]
> Liittimen päivittäinen kutsuraja on 150 kutsua per käyttäjä.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-microsoft-translator"></a>Yhdistä Microsoft Translatoriin
1. Avaa PowerApps, valitse **Uusi** ja luo **Tyhjä sovellus**. Valitse Puhelin- tai Tabletti-asettelu. Tabletti-asettelussa on enemmän työtilaa:  
   
   ![Avaa tyhjä sovellus](./media/connection-microsoft-translator/blank-app.png)
2. Napsauta tai napauta oikealla olevan ruudun **Tiedot**-välilehteä ja valitse **Lisää tietolähde**.
3. Valitse **Uusi yhteys** ja valitse sitten **Microsoft Translator**:  
   
    ![Yhdistä Microsoft Translatoriin](./media/connection-microsoft-translator/addconnection.png)
   
    ![Yhdistä Microsoft Translatoriin](./media/connection-microsoft-translator/add-translator.png)
4. Valitse **Yhdistä**. Yhteytesi näkyy kohdassa **Tietolähteet**:  
   
    ![Yhdistä Microsoft Translatoriin](./media/connection-microsoft-translator/translatordatasource.png)

## <a name="use-the-microsoft-translator-connection-in-your-app"></a>Käytä Microsoft Translator -yhteyttä sovelluksessasi
### <a name="translate-text"></a>Käännä teksti
1. Valitse **Lisää**-valikosta **Teksti** ja valitse sitten **Tekstisyöte**. Nimeä tekstisyöte uudelleen nimellä **Source**:  
   
    ![Nimeä uudelleen](./media/connection-microsoft-translator/renametosource.png)
2. Lisää **Avattava** luettelo (**Lisää**-valikko > **Ohjausobjektit**), nimeä se uudelleen nimellä **TargetLang** ja siirrä se **Source**n alapuolelle.
3. Määritä kohteen **TargetLang**  **[Items](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:  
   
    `MicrosoftTranslator.Languages()`
4. Lisää selite, siirrä se kohteen **TargetLang** alle ja määritä sen **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:  
   
    `MicrosoftTranslator.Translate(Source.Text, TargetLang.Selected.Value)`
5. Kirjoita tekstiä kohtaan **Source** ja valitse kieli kohdasta **TargetLang**. Selite näyttää kirjoittamasi tekstin valitulla kielellä:  
   
    ![Käännä teksti englannista espanjaksi](./media/connection-microsoft-translator/translate-text.png)

### <a name="speak-translated-text"></a>Puhu käännetty teksti
Käännä tekstiä edellisen osan ohjeiden mukaisesti, jos et vielä ole tehnyt niin. Seuraavat vaiheet käyttävät samoja ohjausobjekteja.

1. Määritä avattavan **TargetLang**-luettelon **[Items](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:  
   
    `MicrosoftTranslator.SpeechLanguages()`
2. Nimeä toinen selite (ei **Source**-ruutu) uudelleen nimellä **Target**.
3. Lisää **Audio**-ohjausobjekti (**Lisää**-valikko > **Media**) ja määritä sen **Media**-ominaisuudeksi seuraava kaava:  
   
    `MicrosoftTranslator.TextToSpeech(Target.Text, TargetLang.Selected.Value)`
4. Paina F5-näppäintä tai valitse Esikatselu-painike (![](./media/connection-microsoft-translator/preview.png)). Kirjoita tekstiä **Source**-ruutuun ja valitse kieli kohdasta **TargetLang**. Valitse sitten audio-ohjausobjektin Toista-painike.
   
    Sovellus toistaa kirjoittamasi tekstin ääniversion kielellä, jonka valitsit.
5. Palaa oletustyötilaan painamalla ESC-näppäintä.

### <a name="detect-the-source-language"></a>Tunnista lähdekieli
Seuraavat vaiheet käyttävät samaa **Source**-tekstisyötettä ja **Target**-tekstiohjausobjekteja. Voit luoda halutessasi uusia ohjausobjekteja, kunhan muistat päivittää nimet kaavaan.

1. Valitse **Target**-tekstiohjausobjekti ja määritä **[Text](../controls/properties-core.md)**-ominaisuudeksi seuraava kaava:  
   
    `MicrosoftTranslator.Detect(Source.Text).Name`
2. Kirjoita tekstiä kohtaan **Source**.
   
    Selite näyttää kirjoittamasi tekstin kielen. Selitteessä lukee esimerkiksi **ranska**, jos kirjoitat ruutuun **bonjour**, tai **italia**, jos kirjoitat **ciao**.

## <a name="view-the-available-functions"></a>Selaa käytettävissä olevia funktioita
Tämä yhteys sisältää seuraavat funktiot:

| Funktion nimi | Kuvaus |
| --- | --- |
| [Languages](connection-microsoft-translator.md#languages) |Noutaa kaikki kielet, joita Microsoft Translator tukee |
| [Translate](connection-microsoft-translator.md#translate) |Kääntää tekstin määritetylle kielelle Microsoft Translatorilla |
| [Detect](connection-microsoft-translator.md#detect) |Tunnistaa annetun tekstin lähdekielen |
| [SpeechLanguages](connection-microsoft-translator.md#speechlanguages) |Noutaa puhesynteesille käytettävissä olevat kielet |
| [TextToSpeech](connection-microsoft-translator.md#texttospeech) |Muuntaa annetun tekstin puheeksi äänivirtana WAV-muodossa |

### <a name="languages"></a>Languages
Nouda kielet: noutaa kaikki kielet, joita Microsoft Translator tukee

#### <a name="input-properties"></a>Syöteominaisuudet
Ei mitään.

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koodi |merkkijono |Ei | |
| Nimi |merkkijono |Ei | |

### <a name="translate"></a>Translate
Käännä teksti: kääntää tekstin määritetylle kielelle Microsoft Translatorilla

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| kysely |merkkijono |kyllä |Käännettävä teksti |
| languageTo |merkkijono |kyllä |Kohdekielen kielikoodi (esimerkki: fr) |
| languageFrom |merkkijono |ei |Lähdekieli (jos ei annettu, Microsoft Translator yrittää tunnistaa kielen automaattisesti) (esimerkki: en) |
| luokka |merkkijono |ei |Käännösluokka (oletusarvo: yleinen) |

#### <a name="output-properties"></a>Tulosteominaisuudet
Ei mitään.

### <a name="detect"></a>Detect
Tunnista kieli: tunnistaa annetun tekstin lähdekielen

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| kysely |merkkijono |kyllä |Teksti, jonka kieli tunnistetaan |

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koodi |merkkijono |Ei | |
| Nimi |merkkijono |Ei | |

### <a name="speechlanguages"></a>SpeechLanguages
Nouda puhekielet: noutaa puhesynteesille käytettävissä olevat kielet

#### <a name="input-properties"></a>Syöteominaisuudet
Ei mitään.

#### <a name="output-properties"></a>Tulosteominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koodi |merkkijono |Ei | |
| Nimi |merkkijono |Ei | |

### <a name="texttospeech"></a>TextToSpeech
Teksti puheeksi: muuntaa annetun tekstin puheeksi aaltomuotoisena äänivirtana

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| kysely |merkkijono |kyllä |Muunnettava teksti |
| kieli |merkkijono |kyllä |Puheen muodostamisen kielikoodi (esimerkki: en-us) |

#### <a name="output-properties"></a>Tulosteominaisuudet
Ei mitään.

## <a name="helpful-links"></a>Hyödyllisiä linkkejä
Kaikki [käytettävissä olevat yhteydet](../connections-list.md).  
Lue, miten voit [lisätä yhteyksiä](../add-manage-connections.md) sovelluksiisi.

