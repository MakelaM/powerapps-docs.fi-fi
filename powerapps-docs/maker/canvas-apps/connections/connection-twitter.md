---
title: Yleiskuvaus Twitter-yhteydestä | Microsoft Docs
description: Ohjeet Twitter-yhteyden luomiseen, muutama esimerkki ja kaikki funktiot
author: lancedMicrosoft
ms.service: powerapps
ms.topic: reference
ms.component: canvas
ms.date: 07/12/2017
ms.author: lanced
ms.openlocfilehash: bfdd2bc0ed784b9f2302d01f2fc8c176a7d9c4bb
ms.sourcegitcommit: 7354a0c61578fcc0b9965bf557b9d7c553c73e96
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/05/2018
ms.locfileid: "34803554"
---
# <a name="connect-to-twitter-from-powerapps"></a>Twitter-yhteyden luominen PowerAppsista
![Twitter](./media/connection-twitter/twittericon.png)

Kun luot Twitter-tilin, voit julkaista ja lukea twiittejä, saat käyttöösi aikajanan ja voit viestiä ystävien ja seuraajien kanssa.

Voit näyttää nämä tiedot sovelluksesi selitteessä. Voit esimerkiksi lisätä twiittiä varten tekstiruudun, pyytää käyttäjää kirjoittamaan siihen ja sen jälkeen lisätä painikkeen, jolla twiitti julkaistaan. Samalla tavoin voit vastaanottaa tai hakea twiittejä ja näyttää niitä sovelluksesi selitteessä tai galleriassa.

Tässä kohdassa kerrotaan Twitter-yhteyden muodostamisesta, sen käyttämisestä sovelluksissa sekä käytettävissä olevista kaavoista.

[!INCLUDE [connection-requirements](../../../includes/connection-requirements.md)]

## <a name="connect-to-twitter"></a>Yhdistä Twitteriin
1. Avaa PowerApps, valitse **Uusi** ja luo **Tyhjä sovellus**. Valitse Puhelin- tai Tabletti-asettelu. Tabletti-asettelussa on enemmän työtilaa:  
   
   ![Avaa tyhjä sovellus](./media/connection-twitter/blank-app.png)
2. Napsauta tai napauta oikealla olevan ruudun **Tiedot**-välilehteä ja valitse **Lisää tietolähde**.
3. Valitse **Uusi yhteys** ja **Twitter**:  
   
    ![Yhdistä Twitteriin](./media/connection-twitter/addconnection.png)
   
    ![Yhdistä Twitteriin](./media/connection-twitter/add-twitter.png)
4. Valitse **Yhdistä**, kirjoita Twitter-tilisi kirjautumistiedot ja valitse sen jälkeen **Valtuuta sovellus**.
5. Valitse **Lisää tietolähde**. Yhteytesi näkyy kohdassa **Tietolähteet**:  
    ![Sulje Asetukset-ruutu](./media/connection-twitter/twitterdatasource.png)

Twitter-yhteys on luotu ja lisätty sovellukseesi. Se on nyt valmis käytettäväksi.

## <a name="use-the-twitter-connection-in-your-app"></a>Twitter-yhteyden käyttö sovelluksessasi
### <a name="show-a-timeline"></a>Näytä aikajana
1. Valitse **Lisää**-valikosta **Valikoima** ja lisää jokin **tekstiä käyttävistä** valikoimista.
2. Seuraavassa esitellään aikajanoja:  
   
   * Kun haluat hakea näyttöön nykyisen käyttäjän aikajanan, määritä valikoiman **[Kohteet](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:
     
       `Twitter.HomeTimeline().TweetText`  
       `Twitter.HomeTimeline({maxResults:3}).TweetText`  
   * Kun haluat hakea näyttöön jonkun toisen käyttäjän aikajanan, määritä valikoiman **[Kohteet](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:  
     
       `Twitter.UserTimeline( *TwitterHandle* ).TweetText`
     
       Anna Twitter-tunnus lainausmerkkien sisällä tai käytä jotain muuta vastaavaa arvoa. Voit esimerkiksi syöttää kaavan lausekkeeseen suoraan arvon `"satyanadella"` tai `"powerapps"`.
   * Lisää tekstisyöte, jonka nimi on **Tweep**, ja aseta sen oletusarvoksi `Tweep.Text`. Kirjoita Tweep-tekstiruutuun Twitter-tunnus, kuten `satyanadella` (ilman lainausmerkkejä ja @-merkkiä).
     
       Määritä valikoiman ohjausobjektin Kohteet-ominaisuus seuraavalla kaavalla:  
     
       `Twitter.UserTimeline(Tweep.Text, {maxResults:5}).TweetText`
     
       Valikoiman ohjausobjektiin ilmaantuvat automaattisesti ne twiitit, joiden julkaisijan tunnuksen kirjoitit tekstiruutuun.
     
     > [!TIP]
> Jotkin näistä kaavoista käyttävät **maxResults**-argumenttia näyttämään uusimpien twiittien *x*-lukumäärän aikajanalla.
3. Määritä valikoiman **Kohteet**-ominaisuuden asetukseksi `Twitter.HomeTimeline()`.
   
    Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
4. Valitse ensimmäisestä luettelosta **TweetText**, toisesta luettelosta **TweetedBy** ja kolmannesta luettelosta **CreatedAt**.
   
    Valikoimassa näkyvät nyt valitsemasi ominaisuuksien arvot.

### <a name="show-followers"></a>Näytä seuraajat
1. Nyt haemme näyttöön joitakin seuraajia käyttämällä **tekstiä käyttäviä**  vaihtoehtoja:  
   
   * Jos haluat nähdä nykyisen käyttäjän seuraajat, määritä valikoiman **[Kohteet](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:  
     
       `Twitter.MyFollowers()`  
       `Twitter.MyFollowers({maxResults:3})`
   * Jos haluat nähdä jonkun toisen käyttäjän seuraajat, määritä valikoiman **[Kohteet](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:  
     
       `Twitter.Followers( *TwitterHandle* )`
     
       Anna Twitter-tunnus lainausmerkkien sisällä tai käytä jotain muuta vastaavaa arvoa. Voit esimerkiksi syöttää kaavan lausekkeeseen suoraan arvon `"satyanadella"` tai `"powerapps"`.
   * Lisää tekstisyöte, jonka nimi on **Tweep**, ja aseta sen oletusarvoksi `Tweep.Text`. Kirjoita Tweep-tekstiruutuun Twitter-tunnus, kuten `satyanadella` (ilman lainausmerkkejä ja @-merkkiä).
     
       Määritä valikoiman ohjausobjektin Kohteet-ominaisuus seuraavalla kaavalla:  
     
       `Twitter.Followers(Tweep.Text, {maxResults:5})`
     
       Valikoiman ohjausobjektiin ilmaantuvat automaattisesti sen Twitter-tunnuksen seuraajat, jonka kirjoitit tekstiruutuun.
     
     > [!TIP]
> Jotkin näistä kaavoista käyttävät **maxResults**-argumenttia näyttämään uusimpien twiittien *x*-lukumäärän aikajanalla.
2. Määritä valikoiman **Kohteet**-ominaisuuden asetukseksi `Twitter.MyFollowers()`.
   
    Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
3. Valitse **käyttäjänimi** toisesta luettelosta ja **koko nimi** kolmannesta luettelosta.
   
    Valikoimassa näkyvät nyt valitsemasi ominaisuuksien arvot.

### <a name="show-followed-users"></a>Näytä seuratut käyttäjät
1. Seuraavaksi haemme seurattuja käyttäjiä **tekstiä käyttävän** valikoiman avulla:  
   
   * Jos haluat nähdä, keitä nykyinen käyttäjä seuraa, määritä valikoiman **[Kohteet](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:  
     
       `Twitter.MyFollowing()`  
       `Twitter.MyFollowing({maxResults:3})`
   * Jos haluat nähdä, keitä joku toinen käyttäjä seuraa, määritä valikoiman **[Kohteet](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:
     
       `Twitter.Following( *TwitterHandle* )`
     
       Anna Twitter-tunnus lainausmerkkien sisällä tai käytä jotain muuta vastaavaa arvoa. Voit esimerkiksi syöttää kaavan lausekkeeseen suoraan arvon `"satyanadella"` tai `"powerapps"`.
   * Lisää tekstisyöte, jonka nimi on **Tweep**, ja aseta sen oletusarvoksi `Tweep.Text`. Kirjoita Tweep-tekstiruutuun Twitter-tunnus, kuten `satyanadella` (ilman lainausmerkkejä ja @-merkkiä).
     
       Määritä valikoiman ohjausobjektin Kohteet-ominaisuus seuraavalla kaavalla:  
     
       `Twitter.Following(Tweep.Text, {maxResults:5})`
     
       Valikoiman ohjausobjekti näyttää automaattisesti muut Twitter-tunnukset, joita seuraat.
     
     Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
2. Valitse **Leipäteksti1**-luettelosta kohta**Kuvaus**, **Otsikko1**-luettelosta **Käyttäjänimi** ja **Alaotsikko1**-luettelosta **Koko nimi**.
   
    Valikoimassa näkyvät nyt valitsemasi ominaisuuksien arvot.

### <a name="show-information-about-a-user"></a>Hae tietoa käyttäjästä
Lisää selite ja lisää sen jälkeen selitteen **[Teksti](../controls/properties-core.md)**-ominaisuus käyttämällä jotain näistä kaavoista:  

* `twitter.User( *TwitterHandle* ).Description`
* `twitter.User( *TwitterHandle* ).FullName`
* `twitter.User( *TwitterHandle* ).Location`
* `twitter.User( *TwitterHandle* ).UserName`
* `twitter.User( *TwitterHandle* ).FollowersCount`
* `twitter.User( *TwitterHandle* ).FriendsCount`
* `twitter.User( *TwitterHandle* ).Id`
* `twitter.User( *TwitterHandle* ).StatusesCount`

Anna Twitter-tunnus lainausmerkkien sisällä tai käytä jotain muuta vastaavaa arvoa. Voit esimerkiksi syöttää kaavan lausekkeeseen suoraan arvon `"satyanadella"` tai `"powerapps"`.

Vaihtoehtoisesti voit käyttää syötetekstin ohjausobjektia ja kirjoittaa Twitter-tunnuksen samalla tavoin kuin olemme tehneet aiemminkin tämän opastusjakson aikana.

### <a name="search-tweets"></a>Hae twiittejä
1. Käytä **tekstillä varustettuja** vaihtoehtoja ja määritä valikoiman **[Kohteet](../controls/properties-core.md)**-ominaisuus seuraavalla kaavalla:  
   
    `Twitter.SearchTweet( *SearchTerm* ).TweetText`
   
    Tee haku antamalla lainausmerkeillä varustettu *hakutermi* tai viittaamalla vastaavaan arvoon. Voit esimerkiksi syöttää kaavaan suoraan arvon `"PowerApps"` tai `"microsoft"`.
   
    Vaihtoehtoisesti voit käyttää **syötetekstin** ohjausobjektia ja määrittää hakusanan samalla tavoin kuin olemme tehneet aiemminkin tämän opastusjakson aikana.
   
    > [!TIP]
> Näytä viisi ensimmäistä tulosta käyttämällä maxResults-ominaisuutta:  
   
    `Twitter.SearchTweet(SearchTerm.Text, {maxResults:5}).TweetText`
2. Määritä valikoiman **Kohteet**-ominaisuuden arvoksi `Twitter.SearchTweet(SearchTerm.Text, {maxResults:5})`.
   
    Valittuna olevan valikoiman käytettävissä olevat vaihtoehdot näkyvät oikeanpuoleisessa ruudussa.
3. Valitse ensimmäisestä luettelosta **TweetText**, toisesta luettelosta **TweetedBy** ja kolmannesta luettelosta **CreatedAt**.
   
    Valikoimassa näkyvät nyt valitsemasi ominaisuuksien arvot.

### <a name="send-a-tweet"></a>Lähetä twiitti
1. Lisää tekstisyötteen ohjausobjekti ja muuta sen nimeksi **MyTweet**.
2. Lisää painike ja määritä sen **[OnSelect](../controls/properties-core.md)** (Valittaessa) -ominaisuus tällä kaavalla:  
    `Twitter.Tweet({tweetText: MyTweet.Text})`
3. Paina F5-näppäintä tai valitse Esikatselu-painike (![](./media/connection-twitter/preview.png)). Kirjoita tekstiä **MyTweet**-ohjausobjektiin ja julkaise twiitti valitsemalla painike.
4. Palaa oletustyötilaan painamalla Esc-näppäintä.

## <a name="view-the-available-functions"></a>Selaa käytettävissä olevia funktioita
Tämä yhteys sisältää seuraavat funktiot:

| Funktion nimi | Kuvaus |
| --- | --- |
| [UserTimeline](connection-twitter.md#usertimeline) |Hakee määritetyn käyttäjän uusimmat twiitit |
| [HomeTimeline](connection-twitter.md#hometimeline) |Hakee uusimmat twiitit ja uudelleentwiittaukset, jotka on kirjattu minulle ja seuraajilleni |
| [SearchTweet](connection-twitter.md#searchtweet) |Hakee hakuehtojen mukaiset twiitit |
| [Seuraajat](connection-twitter.md#followers) |Hakee määritetyn käyttäjän seuraajat |
| [MyFollowers](connection-twitter.md#myfollowers) |Hakee minua seuraavat käyttäjät |
| [Seuraajat](connection-twitter.md#following) |Hakee käyttäjät, joita määritetty käyttäjä seuraa |
| [MyFollowing](connection-twitter.md#myfollowing) |Hakee käyttäjät, joita itse seuraan |
| [Käyttäjä](connection-twitter.md#user) |Hakee tietoja määritetystä käyttäjästä (esimerkiksi käyttäjänimi, kuvaus, seuraajien määrä jne.) |
| [Twiitti](connection-twitter.md#tweet) |Twiitti |
| [OnNewTweet](connection-twitter.md#onnewtweet) |Käynnistää työnkulun, kun Twitterissä julkaistaan uusi twiitti, joka vastaa hakuehtojasi |

### <a name="usertimeline"></a>UserTimeline
Hae käyttäjän aikajana: hakee määritetyn käyttäjän uusimmat twiitit

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Käyttäjätunnus |merkkijono |kyllä |Twitter-tunnus |
| maxResults |kokonaisluku |ei |Haettavien twiittien enimmäismäärä, esimerkiksi {maxResults:5} |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Twiitin teksti |merkkijono |Kyllä | |
| TweetId |merkkijono |Ei | |
| CreatedAt |merkkijono |Ei | |
| RetweetCount |kokonaisluku |Kyllä | |
| TweetedBy |merkkijono |Kyllä | |
| MediaUrls |matriisi |Ei | |

### <a name="hometimeline"></a>HomeTimeline
Hae kotiaikajana: hakee uusimmat twiitit ja uudelleentwiittaukset, jotka on julkaistu minulle ja seuraajilleni

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| maxResults |kokonaisluku |ei |Haettavien twiittien enimmäismäärä, esimerkiksi {maxResults:5} |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Twiitin teksti |merkkijono |Kyllä | |
| TweetId |merkkijono |Ei | |
| CreatedAt |merkkijono |Ei | |
| RetweetCount |kokonaisluku |Kyllä | |
| TweetedBy |merkkijono |Kyllä | |
| MediaUrls |matriisi |Ei | |

### <a name="searchtweet"></a>SearchTweet
Hae twiittiä: hakee määritettyä kyselyä vastaavat twiitit

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| searchQuery |merkkijono |kyllä |Kyselyn teksti (voit käyttää Twitterin tukemia kyselyoperaattoreita: http://www.twitter.com/search) |
| maxResults |kokonaisluku |ei |Haettavien twiittien enimmäismäärä, esimerkiksi {maxResults:5} |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Twiitin teksti |merkkijono |Kyllä | |
| TweetId |merkkijono |Ei | |
| CreatedAt |merkkijono |Ei | |
| RetweetCount |kokonaisluku |Kyllä | |
| TweetedBy |merkkijono |Kyllä | |
| MediaUrls |matriisi |Ei | |

### <a name="followers"></a>Seuraajat
Hae seuraajat: hakee määritetyn käyttäjän seuraajat

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Käyttäjätunnus |merkkijono |kyllä |Käyttäjän Twitter-tunnus |
| maxResults |kokonaisluku |ei |Enimmäismäärä, jonka käyttäjä voi hakea, esimerkiksi {maxResults:5} |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koko nimi |merkkijono |Kyllä | |
| Sijainti |merkkijono |Kyllä | |
| Tunnus |kokonaisluku |Ei | |
| Käyttäjänimi |merkkijono |Kyllä | |
| FollowersCount |kokonaisluku |Ei | |
| Kuvaus |merkkijono |Kyllä | |
| StatusesCount |kokonaisluku |Ei | |
| FriendsCount |kokonaisluku |Ei | |

### <a name="myfollowers"></a>MyFollowers
Hae omat seuraajat: hakee omat seuraajani

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| maxResults |kokonaisluku |ei |Enimmäismäärä, jonka käyttäjä voi hakea, esimerkiksi {maxResults:5} |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koko nimi |merkkijono |Kyllä | |
| Sijainti |merkkijono |Kyllä | |
| Tunnus |kokonaisluku |Ei | |
| Käyttäjänimi |merkkijono |Kyllä | |
| FollowersCount |kokonaisluku |Ei | |
| Kuvaus |merkkijono |Kyllä | |
| StatusesCount |kokonaisluku |Ei | |
| FriendsCount |kokonaisluku |Ei | |

### <a name="following"></a>Seurattavat
Hae seurattavat: hakee käyttäjät, joita määritetty käyttäjä seuraa

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Käyttäjätunnus |merkkijono |kyllä |Käyttäjän Twitter-tunnus |
| maxResults |kokonaisluku |ei |Enimmäismäärä, jonka käyttäjä voi hakea, esimerkiksi {maxResults:5} |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koko nimi |merkkijono |Kyllä | |
| Sijainti |merkkijono |Kyllä | |
| Tunnus |kokonaisluku |Ei | |
| Käyttäjänimi |merkkijono |Kyllä | |
| FollowersCount |kokonaisluku |Ei | |
| Kuvaus |merkkijono |Kyllä | |
| StatusesCount |kokonaisluku |Ei | |
| FriendsCount |kokonaisluku |Ei | |

### <a name="myfollowing"></a>MyFollowing
Hae omat seurattavat: hakee käyttäjät, joita itse seuraan

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| maxResults |kokonaisluku |ei |Enimmäismäärä, jonka käyttäjä voi hakea, esimerkiksi {maxResults:5} |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koko nimi |merkkijono |Kyllä | |
| Sijainti |merkkijono |Kyllä | |
| Tunnus |kokonaisluku |Ei | |
| Käyttäjänimi |merkkijono |Kyllä | |
| FollowersCount |kokonaisluku |Ei | |
| Kuvaus |merkkijono |Kyllä | |
| StatusesCount |kokonaisluku |Ei | |
| FriendsCount |kokonaisluku |Ei | |

### <a name="user"></a>Käyttäjä
Hae käyttäjä: hakee tietoa määritetystä käyttäjästä (esimerkiksi käyttäjänimi, kuvaus, seuraajien määrä jne.)

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Käyttäjätunnus |merkkijono |kyllä |Käyttäjän Twitter-tunnus |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| Koko nimi |merkkijono |Kyllä | |
| Sijainti |merkkijono |Kyllä | |
| Tunnus |kokonaisluku |Ei | |
| Käyttäjänimi |merkkijono |Kyllä | |
| FollowersCount |kokonaisluku |Ei | |
| Kuvaus |merkkijono |Kyllä | |
| StatusesCount |kokonaisluku |Ei | |
| FriendsCount |kokonaisluku |Ei | |

### <a name="tweet"></a>Twiitti
Julkaise uusi twiitti: twiittaa

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| tweetText |merkkijono |ei |Julkaistava teksti, esimerkiksi {tweetText: ”hello”} |
| leipäteksti |merkkijono |ei |Julkaistava mediasisältö |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| TweetId |merkkijono |Kyllä | |

### <a name="onnewtweet"></a>OnNewTweet
Kun uusi twiitti tulee näkyviin: käynnistää työnkulun, kun julkaistaan uusi hakukyselyä vastaava twiitti

#### <a name="input-properties"></a>Syöteominaisuudet
| Nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| searchQuery |merkkijono |kyllä |Kyselyn teksti (voit käyttää Twitterin tukemia kyselyoperaattoreita: http://www.twitter.com/search) |

#### <a name="output-properties"></a>Output-ominaisuudet
| Ominaisuuden nimi | Tietotyyppi | Pakollinen | Kuvaus |
| --- | --- | --- | --- |
| arvo |matriisi |Ei | |

## <a name="helpful-links"></a>Hyödyllisiä linkkejä
Kaikki [käytettävissä olevat yhteydet](../connections-list.md).  
Lue, miten voit [lisätä yhteyksiä](../add-manage-connections.md) sovelluksiisi.

