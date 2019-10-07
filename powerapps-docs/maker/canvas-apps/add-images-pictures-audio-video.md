---
title: Upota multimediatiedostoja pohjaan perustuvaan sovellukseen ja lataa niitä | Microsoft Docs
description: Multimediatiedostojen näyttäminen pohjaan perustuvassa sovelluksessa ja niiden lataaminen tietolähteeseen
author: emcoope-msft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: tapanm
ms.date: 07/12/2017
ms.author: emcoope
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: b544b03fbe181265599bab520eddc2a2a646c477
ms.sourcegitcommit: 7dae19a44247ef6aad4c718fdc7c68d298b0a1f3
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 10/07/2019
ms.locfileid: "71994474"
---
# <a name="using-multimedia-files-in-powerapps"></a>Multimediatiedostojen käyttäminen PowerAppsissa

Tässä ohjeaiheessa kerrotaan, miten multimediatiedostoja upotetaan pohjaan perustuvaan sovellukseesi, kynäpiirros ladataan tietolähteeseen ja tietolähteessä olevia kuvia näytetään pohjaan perustuvassa sovelluksessasi. Tässä aiheessa käytetään tietolähteenä Excel-tiedostoa, joka sijaitsee OneDrive for Business -palvelussa.

## <a name="prerequisites"></a>Edellytykset

[Rekisteröidy](../signup-for-powerapps.md) PowerAppsiin ja [kirjaudu sitten sisään](https://web.powerapps.com?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) samoilla tunnistetiedoilla, joita käytit rekisteröityessäsi.

## <a name="add-media-from-a-file-or-the-cloud"></a>Lisää media tiedostosta tai pilvipalvelusta

Voit valita lisättävän mediatiedoston tyypin (esimerkiksi kuvat, video tai ääni).

1. Valitse **Sisältö**-välilehdessä **Media**.

2. Valitse **Media**-kohdassa **Kuvat**, **Videot** tai **Ääni** ja valitse **Selaa**:

    ![Selaa mediaa][1]

3. Valitse lisättävä tiedosto ja valitse **Avaa**.

    Tietokoneesi **Kuvat**-kansio avautuu, ja voit valita kuvan sieltä tai siirtyä toiseen kansioon.

4. Kun olet lisännyt haluamasi tiedostot, palaa oletustyötilaan painamalla ESC-näppäintä.

5. Valitse **Lisää**-välilehdessä **Media** ja valitse sitten **Kuva**, **Video** tai **Ääni**:

    ![Valitse mediatyyppi][8]

6. Jos olet lisännyt kuvan ohjausobjektin, aseta sen **[Image](controls/properties-visual.md)** -ominaisuus lisäämääsi tiedostoon:  

    ![Määritä kuvan ominaisuus](./media/add-images-pictures-audio-video/imageproperty.png)

    > [!NOTE]
   > Määritä vain tiedoston nimi, ilman tiedostopäätettä ja puolilainausmerkeissä.

7. Jos olet lisännyt video- tai ääniohjausobjektin, aseta sen **Media**-ominaisuus lisäämääsi tiedostoon:  

    ![Määritä mediaominaisuus](./media/add-images-pictures-audio-video/mediaproperty.png)

    > [!NOTE]
   > Toista YouTube-video asettamalla video-ohjausobjektin **Media**-ominaisuus oikeaan URL-osoitteeseen lainausmerkkien sisään.

## <a name="add-media-from-azure-media-services"></a>Median lisääminen Microsoft Azure -mediapalveluista
1. Lataa ja julkaise videoresurssisi Azure-mediapalveluiden tililtäsi kohteesta **AMS > Asetukset > Resurssit**.

2. Kun video on julkaistu, kopioi sen URL-osoite.

3. Kun toimit PowerAppsista käsin, lisää **Video**-ohjausobjekti kohdasta **Lisää > Media**.

4. Aseta **Media**-ominaisuus kopioimaasi URL-osoitteeseen.

    Kuten tässä kaaviossa näkyy, voit valita minkä tahansa suoratoisto-URL-osoitteen, jota Microsoft Azure -mediapalvelut tukee:

    ![Määritä mediaominaisuus](./media/add-images-pictures-audio-video/ams-with-powerapps.png)

## <a name="add-images-from-the-cloud-to-your-app"></a>Kuvien lisääminen pilvipalvelusta sovellukseen
Tässä skenaariossa voit tallentaa kuvia OneDrive for Business -pilvitallennuspalvelun tililtä. Voit käyttää Excel-taulukkoa, joka sisältää kuvien polut, ja voit näyttää kuvat sovelluksesi valikoima-ohjausobjektissa.

Tämä skenaario käyttää [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip)-pakettia, joka sisältää joitakin .jpeg-tiedostoja.

> [!NOTE]
> Excel-tiedostossa näiden kuvien polussa on käytettävä vinoviivaa. Kun PowerApps tallentaa kuvan polut Excel-taulukkoon, polussa käytetään kenoviivoja. Jos käytät kuvan polkuja tällaisessa taulukossa, muuta polut Excel-taulukossa käyttämään vinoviivaa kenoviivojen asemasta. Muussa tapauksessa kuvat eivät näy.  

1. Lataa [CreateFirstApp.zip](http://pwrappssamples.blob.core.windows.net/samples/CreateFirstApp.zip) ja pura **Assets**-kansio pilvipalvelun tallennustilan tiliisi.

2. Vaihda **Assets**-kansion nimeksi **Assets_images**.

3. Luo yksisarakkeinen taulukko Excel-laskentataulukossa ja täytä siihen seuraavat tiedot:

    ![Jackets-taulukko](./media/add-images-pictures-audio-video/jackets.png)

4. Anna taulukolle nimi **Jackets** ja Excel-tiedostolle nimi **Assets.xlsx**.

5. Lataa **Jackets**-taulukko tietolähteeksi sovellukseesi.  

6. Lisää **Vain kuva** -ohjausobjekti (**Lisää**-välilehti > **Valikoima**) ja aseta sen **Items**-ominaisuudeksi `Jackets`:  

    ![Items-ominaisuus](./media/add-images-pictures-audio-video/items-jackets.png)

    Valikoimaan päivitetään automaattisesti kuvat:  

    ![Takkien kuvat](./media/add-images-pictures-audio-video/images.png)

    Kun määrität **Items**-ominaisuuden, sarake, jonka nimi on **PowerAppsId**, lisätään automaattisesti Excel-taulukkoon.

    Excel-taulukon kuvan polku voi olla myös kuvan URL-osoite. Esimerkkinä on [Flooring Estimates](http://pwrappssamples.blob.core.windows.net/samples/FlooringEstimates.xlsx) -mallitiedosto. Voit ladata sen pilvipalvelun tallennustiliisi, lisätä `FlooringEstimates`-taulukon tietolähteeksi sovelluksellesi ja määrittää sitten valikoiman ohjausobjektiksi `FlooringEstimates`. Kuvat päivitetään automaattisesti valikoimaan.

## <a name="upload-pen-drawings-to-the-cloud"></a>Lataa kynäpiirustukset pilveen
Tässä skenaariossa opit lataamaan kynäpiirustukset tietolähteeseen, OneDrive for Business -palveluun, ja näet, miten piirustukset tallennetaan sinne.

1. Lisää Excelissä **Image [image]** soluun A1.

2. Luo taulukko suorittamalla seuraavat vaiheet:    

   1. Valitse solu A1.

   2. Valitse **Lisää**-valintanauhasta **Taulukko**.

   3. Valitse valintaikkunassa **Taulukossa on otsikot** ja valitse sitten **OK**.

       ![Luo taulukko](./media/add-images-pictures-audio-video/create-table.png)

       Excel-tiedostosi on nyt taulukkomuodossa. Katso kohdasta [Muotoile tiedot taulukoksi](https://support.office.com/article/Format-an-Excel-table-6789619F-C889-495C-99C2-2F971C0E2370) lisätietoja taulukon muotoilusta Excelissä.

   4. Anna taulukolle nimi **Drawings**:

       ![Anna taulukon uudeksi nimeksi Drawings](./media/add-images-pictures-audio-video/name-media-table.png)

3. Tallenna Excel-tiedosto OneDrive for Business -palveluun nimellä **SavePen.xlsx**.

4. Luo [tyhjä sovellus](get-started-create-from-blank.md) PowerAppsissa.

5. Lisää OneDrive for Business -tilisi [tietolähteeksi](add-data-connection.md) sovelluksessasi:

   1. Napauta tai napsauta **Näkymä**-välilehteä ja napsauta tai napauta sitten kohtaa **Tietolähteet**.

       ![](./media/add-images-pictures-audio-video/choose-data-sources.png)

   2. Napsauta tai napauta kohtaa **Lisää tietolähde** ja napsauta tai napauta kohtaa **OneDrive for Business**.

       ![](./media/add-images-pictures-audio-video/select-source.png)

   3. Napsauta tai napauta tiedostoa **SavePen.xlsx**.

   4. Valitse **Drawings**-taulukko ja napsauta tai napauta sitten kohtaa **Yhdistä**.

       ![Yhdistä](./media/add-images-pictures-audio-video/savepen.png)  

       Nyt Drawings-taulukko luetteloidaan tietolähteeksi.

6. Valitse **Lisää**-välilehdestä **Teksti** ja valitse sitten **Kynäsyöte**.

7. Nimeä uusi ohjausobjekti uudelleen nimellä **MyPen**:  

    ![Nimeä uudelleen](./media/add-images-pictures-audio-video/rename-mypen.png)

8. Lisää **Lisää**-välilehdessä **Button**-ohjausobjekti ja määritä sen **OnSelect**-ominaisuudeksi tämä kaava:

    **Patch(Drawings, Defaults(Drawings), {Image:MyPen.Image})**

9. Lisää **Kuvavalikoima**-ohjausobjekti (**Lisää**-välilehti > **Valikoima**) ja aseta sen **Items**-ominaisuudeksi `Drawings`. Valikoima-ohjausobjektin **Image**-ominaisuudeksi asetetaan automaattisesti `ThisItem.Image`.

    Järjestä ohjausobjektit niin, että näyttösi näyttää tältä:  

    ![Mallinäyttö](./media/add-images-pictures-audio-video/screen.png)

10. Paina F5-näppäintä tai valitse Esikatsele ( ![Esikatselu-painike](./media/add-images-pictures-audio-video/preview.png) ).

11. Piirrä jotain MyPen-kuvaan ja valitse sitten painike.

    Piirroksesi näkyy valikoima-ohjausobjektin ensimmäisessä kuvassa.

12. Lisää jotain muuta piirrokseesi ja valitse painike.

    Piirroksesi näkyy valikoima-ohjausobjektin toisessa kuvassa.

13. Sulje esikatseluikkuna painamalla ESC-näppäintä.

    Pilvitallennuspalvelun tilillesi on luotu automaattisesti **SavePen_images**-kansio. Tämä kansio sisältää tallennetut kuvasi ja niiden tiedostonimien tunnukset. Jotta saat kansion näkyviin, sinun on ehkä päivitettävä selainikkuna esimerkiksi painamalla F5-näppäintä.

    Tiedoston **SavePen.xlsx** **Image**-sarake määrittää uusien kuvien polun.

### <a name="known-limitations"></a>Tunnetut rajoitukset
[Tutustu näihin rajoituksiin](connections/cloud-storage-blob-connections.md#known-limitations) saadaksesi lisätietoja siitä, miten voit jakaa Excel-tietoja organisaatiossasi.

## <a name="for-more-information"></a>Lisätietoja
Muista testata sovelluksesi eri ympäristöissä, kuten [selainikkunassa](https://home.dynamics.com/) ja puhelimessa.

Lisätietoja kehittyneemmistä skenaarioista, joihin liittyy multamediatiedostojen lataaminen suoraan toiseen tietolähteeseen, on kohdissa [Ammattilaistason vihjeitä kuvakaappauksia varten](https://powerapps.microsoft.com/blog/image-capture-pro-tips/) ja [Mukautetut liittimet kuvan palvelimeen lataamista varten](https://powerapps.microsoft.com/blog/custom-api-for-image-upload/).

Toinen tapa ladata tiedostoja tietolähteeseen on käyttää [Patch](functions/function-patch.md)-funktiota.

[1]: ./media/add-images-pictures-audio-video/add-image-video-audio-file.png
[3]: ./media/add-images-pictures-audio-video/add-intro-sound.png
[4]: ./media/add-images-pictures-audio-video/add-picture.png
[5]: ./media/add-images-pictures-audio-video/camera-gallery.png
[6]: ./media/add-images-pictures-audio-video/audio-gallery.png
[7]: ./media/add-images-pictures-audio-video/pen-gallery.png
[8]: ./media/add-images-pictures-audio-video/mediaoptions.png
[9]: ./media/add-images-pictures-audio-video/imageproperty.png
[10]: ./media/add-images-pictures-audio-video/mediaproperty.png
[11]: ./media/add-images-pictures-audio-video/renamecamera.png
