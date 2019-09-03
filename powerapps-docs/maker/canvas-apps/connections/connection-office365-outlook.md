---
title: Yleiskuvaus yhteydestä Office 365 Outlookiin | Microsoft Docs
description: Viitetiedot ja esimerkkejä Office 365 Outlookin yhteydestä PowerAppsiin
author: lancedMicrosoft
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.date: 10/20/2017
ms.author: lanced
ms.reviewer: anneta
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 5ea7c9fc331d96b50d8623f4ca632859e09be7ab
ms.sourcegitcommit: 25a85b462515cb64f3f2b114864a682abf803f4a
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/03/2019
ms.locfileid: "70213676"
---
# <a name="connect-to-office-365-outlook-from-powerapps"></a>Yhteyden muodostaminen PowerAppsista Office 365 Outlookiin
![Office 365 Outlook](./media/connection-office365-outlook/office365icon.png)

Jos muodostat yhteyden Office 365 Outlookiin, voit näyttää, lähettää ja poistaa sähköpostiviestejä, vastata viesteihin ja suorittaa muita tehtäviä.

Voit lisätä ohjausobjekteja, joilla nämä funktiot suoritetaan sovelluksessasi. Voit lisätä esimerkiksi **Tekstisyöte**-ohjausobjektin, joka kysyy vastaanottajaa, aihetta ja sähköpostiviestin tekstiosaa, tai **Painike**-ohjausobjektin, jolla sähköpostiviesti lähetetään.

Tässä aiheessa näytetään, miten muodostat yhteyden Office 365 Outlookiin, miten lisäät Office 365 Outlookin sovelluksesi tietolähteeksi ja miten käytät kyseisiä tietoja eri ohjausobjekteissa.

> [!IMPORTANT]
> Kalenteri-toiminto ei tue kirjoittamishetkellä toistuvia tapahtumia.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-office-365-outlook"></a>Yhteyden muodostaminen Office 365 Outlookiin
1. [Lisää tietoyhteys](../add-data-connection.md) ja valitse **Office 365 Outlook**:  
   
    ![Yhteyden muodostaminen Office 365:een](./media/connection-office365-outlook/add-office.png)
2. Valitse **Yhdistä**, kirjaudu pyydettäessä sisään ja syötä työtilisi.

Office 365 Outlook -yhteys on luotu ja lisätty sovellukseesi. Se on nyt valmis käytettäväksi.

## <a name="show-messages"></a>Viestien näyttäminen
1. Valitse **Lisää**-valikosta **Valikoima** ja valitse jokin **Tekstivalikoima**-ohjausobjekti.
2. Määritä sen **[Items](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:  
   
    `Office365.GetEmails({fetchOnlyUnread:false})`
   
    Kun olet muuttanut asetuksia, muuta **asetteluksi** **otsikko, alaotsikko, leipä teksti**.
    
    Valikoima-ohjausobjekti täytetään automaattisesti sähköpostiviesteilläsi.
    
3. Määritä valikoiman ensimmäisen selitteen **Text**-ominaisuudeksi `ThisItem.From`. Määritä toiseksi selitteeksi `ThisItem.Subject`. Määritä kolmanneksi selitteeksi `ThisItem.BodyPreview`. Voit myös muuttaa selitteiden kokoa.
   
    Valikoima-ohjausobjekti täytetään automaattisesti uusilla ominaisuuksilla.
4. Funktion käytettävissä on useita valinnaisia parametreja. Määritä valikoiman **Items**-ominaisuudeksi jokin seuraavista kaavoista:
   
    `Office365.GetEmails({fetchOnlyUnread:false})`  
    `Office365.GetEmails({fetchOnlyUnread:false, top:2})`  
    `Office365.GetEmails({folderPath:"Sent Items", fetchOnlyUnread:false, top:2})`  
    `Office365.GetEmails({folderPath:"Sent Items", fetchOnlyUnread:false, top:2, searchQuery:"powerapps"})`  
    `Office365.GetEmails({folderPath:"Deleted Items", fetchOnlyUnread:false, top:2, skip:3})`

## <a name="send-a-message"></a>Viestin lähettäminen
1. Valitse **Lisää**-valikosta **Teksti** ja valitse sitten **Tekstisyöte**.
2. Toista edelliset vaiheet kahdesti, minkä jälkeen ruutuja on kolme. Järjestä ne sitten sarakkeeseen:  
   
    ![Kolme ruutua sarakkeessa](./media/connection-office365-outlook/threetextinput.png)
3. Nimeä ohjausobjektit uudelleen:  
   
   * **inputTo**
   * **inputSubject**
   * **inputBody**
4. Valitse **Lisää**-valikosta **Ohjausobjektit** ja valitse **Painike**. Määritä sen **[OnSelect](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:  
   
    `Office365.SendEmail(inputTo.Text, inputSubject.Text, inputBody.Text)`
5. Siirrä painiketta niin, että se näkyy kaikkien muiden ohjausobjektien alapuolella, ja määritä sen **[Text](../controls/properties-core.md)** -ominaisuudeksi **"Send email"** .
6. Paina F5 tai valitse Esikatselu-painike (![Esikatselu-painike](./media/connection-office365-outlook/preview.png)). Kirjoita kelvollinen sähköpostiosoite kohtaan **inputTo** ja haluamasi teksti toisiin **Tekstisyöte**-ohjausobjekteihin.
7. Lähetä viesti valitsemalla **Lähetä sähköposti**. Palaa oletustyötilaan painamalla ESC-näppäintä.

## <a name="send-a-message-with-an-attachment"></a>Viestin lähettäminen liitteen kanssa
Voit luoda sovelluksen, jossa käyttäjä ottaa kuvia laitteen kameralla ja lähettää ne liitteinä. Käyttäjät voivat liittää sähköpostisovellukseen myös monia muita tiedostotyyppejä.

Lisää viestiin liite seuraamalla edellisen osan ohjeita, mutta lisää parametri määrittämään liitettä (kun määrität painikkeen **OnSelect**-ominaisuuden). Tämä parametri on rakenteeltaan taulukko, jossa voit määrittää enintään kolme ominaisuutta jokaiselle liitteelle:

* Nimi
* ContentBytes
* @odata.type

> [!NOTE]
> Voit määrittää @odata.type-ominaisuuden vain yhdelle liitteistä, ja voit määrittää sen tyhjäksi merkkijonoksi.

Tässä esimerkissä lähetetään valokuva nimellä **file1.jpg**:

`Office365.SendEmail(inputTo.Text, inputSubject.Text, inputBody.Text, {Attachments:Table({Name:"file1.jpg", ContentBytes:Camera1.Photo, '@odata.type':""})})`

Tässä esimerkissä lähetetään kuvan lisäksi äänitiedosto:

`Office365.SendEmail(inputTo.Text, inputSubject.Text, inputBody.Text, {Attachments:Table({Name:"file1.jpg", ContentBytes:Camera1.Photo, '@odata.type':""}, {Name:"AudioFile", ContentBytes:microphone1.audio })})`

## <a name="delete-a-message"></a>Viestin poistaminen
1. Valitse **Lisää**-valikosta **Valikoima** ja valitse jokin **Tekstivalikoima**-ohjausobjekti.
2. Määritä sen **[Items](../controls/properties-core.md)** -ominaisuudeksi seuraava kaava:  
   
    `Office365.GetEmails({fetchOnlyUnread:false})`
   
    Valikoima-ohjausobjekti täytetään automaattisesti sähköpostiviesteilläsi.
3. Määritä valikoiman ensimmäisen selitteen **Text**-ominaisuudeksi `ThisItem.Id`. Määritä toiseksi selitteeksi `ThisItem.Subject`. Määritä kolmanneksi selitteeksi `ThisItem.Body`.
4. Valitse valikoiman ensimmäinen selite ja nimeä se uudelleen nimellä **EmailID**:
   
    ![Nimeä ensimmäinen selite uudelleen](./media/connection-office365-outlook/renameheading.png)
5. Valitse valikoiman kolmas selite ja lisää **Painike** (**Lisää**-valikko). Määritä painikkeen **OnSelect**-ominaisuudeksi seuraava kaava:  
   
    `Office365.DeleteEmail(EmailID.Text)`
6. Paina F5 tai valitse Esikatselu-painike (![Esikatselu-painike](./media/connection-office365-outlook/preview.png)). Valitse yksi valikoimasi sähköposteista ja napsauta painiketta. 
    
    > [!NOTE]
    > Tämä poistaa sähköpostin Saapuneet-kansiosta. Valitse siis tarkkaan.
7. Palaa oletustyötilaan painamalla ESC-näppäintä.

## <a name="mark-a-message-as-read"></a>Merkitse viesti luetuksi
Tässä osassa käytetään samoja ohjausobjekteja kuin kohdassa [Viestin poistaminen](connection-office365-outlook.md#delete-a-message).

1. Määritä painikkeen **OnSelect**-ominaisuudeksi seuraava kaava:  
   
    `Office365.MarkAsRead(EmailID.Text)`
2. Paina F5 tai valitse Esikatselu-painike (![Esikatselu-painike](./media/connection-office365-outlook/preview.png)). Valitse jokin lukematon sähköposti ja valitse painike.
3. Palaa oletustyötilaan painamalla ESC-näppäintä.

## <a name="helpful-links"></a>Hyödyllisiä linkkejä
* Katso luettelo funktioista ja niiden parametreista kohdasta [Office 365 Outlook -viittaus](https://docs.microsoft.com/connectors/office365connector/).
* Kaikki [käytettävissä olevat yhteydet](../connections-list.md).  
* Lue, miten [yhteyksiä hallitaan](../add-manage-connections.md).

