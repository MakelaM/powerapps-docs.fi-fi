Sovellusten luominen liiketoiminnan tarpeisiin on hienoa, mutta PowerAppsin todellisena etuna on sovellusten jakaminen muille. Osaat nyt luoda sovelluksen. Tässä aiheessa käsitellään sen jakamista. Voit jakaa sovelluksen tietyille käyttäjille tai ryhmille tai koko organisaatiollesi. Kun jaat sovelluksen jonkun kanssa, hän voi suorittaa sen Dynamics 365:n kautta selaimessa tai PowerApps Mobilen Windows-, iOS- tai Android-versiossa. Jos annat jollekulle Osallistuja-käyttöoikeudet, hän voi myös päivittää sovellusta.

## <a name="prepare-to-share-an-app"></a>Sovelluksen jakamisen valmistelu
Sovellus täytyy ensin tallentaa pilvipalveluun, jotta se voidaan jakaa muille. Anna sovellukselle merkityksellinen nimi ja kuvaus, jotta ihmiset tietävät sovelluksen tarkoituksen ja voivat helposti valita sen luettelosta. Napsauta tai napauta PowerApps Studiossa kohtaa **Tiedosto** ja syötä kuvaus.

![Sovelluksen kuvaus](./media/learning-manage-share-apps/app-description.png)

Ota huomioon, että jaettuun sovellukseen tekemäsi muutokset päivittyvät henkilöille, joille jaoit sovelluksen, heti kun teet muutokset. Tämä voi olla kätevää, jos parannat sovellustasi, mutta se voi myös vaikuttaa käyttäjiin, jos poistat ominaisuuksia tai muutat niitä merkittävästi.

## <a name="share-an-app"></a>Sovelluksen jakaminen
Napsauta sivustossa web.powerapps.com sovelluksen ruudussa kolmea pistettä (. . .) ja napsauta **Jaa**.

![Sovelluksen jakaminen osoitteessa web.powerapps.com](./media/learning-manage-share-apps/share-app.png)

Täällä voit jakaa sovelluksen ja hallita sovelluksen versioita. Niitä käsitellään seuraavassa aiheessa. Määritä käyttäjät tai ryhmät, joille sovellus jaetaan sekä heidän roolinsa – **Käyttäjä** tai **Osallistuja**. Napsauta tai napauta kohtaa **Tallenna**.

![Käyttäjien ja ryhmien valinta](./media/learning-manage-share-apps/select-users.png)

Jos päätät viestiä käyttäjille sähköpostilla, henkilöt, joille jaoit sovelluksen, saavat sähköpostilla linkin Dynamics 365:een. Sovellukselle merkityt osallistujat saavat myös linkin osoitteeseen web.powerapps.com.  Jos joku ei käytä Dynamics 365 -linkkiä, sovellusta ei näytetä hänelle siellä. Sovellus näytetään AppSourcessa, mutta käyttäjän on lisättävä se itse Dynamics 365:een.

![Sovellus Dynamics 365:ssä](./media/learning-manage-share-apps/dynamics-365.png)

## <a name="permissions-and-licensing"></a>Käyttöoikeudet ja lisenssit
Tässä aiheessa ei käsitellä yksityiskohtaisesti käyttöoikeuksia ja lisenssejä, mutta haluamme käydä läpi pari perusasiaa jakamisesta:

* Käyttäjät ja osallistujat tarvitsevat käyttöoikeudet tietoyhteyksiin ja yhdyskäytäviin, joita jaettu sovellus käyttää. Jotkin käyttöoikeudet saadaan sovelluksen mukana, mutta jotkin täytyy nimenomaisesti antaa.
* Jos sovellus käyttää Common Data Service for Apps -entiteettejä, käyttäjät ja osallistujat tarvitsevat pääsyn Common Data Service for Apps -tietokantaan. Osallistujat tarvitsevat myös PowerAppsin "P2"-lisenssin, jos he käsittelevät entiteettejä suoraan.

Sovellusten jakaminen on helppoa ja se on kätevä tapaa antaa hyödyllinen sovellus organisaatiosi jäsenten käytettäväksi. Seuraavassa aiheessa selitetään, miten määritetään jaettavan ja käytettävän sovelluksen aktiivinen versio.

