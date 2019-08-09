---
title: Laskurikentät kohteessa Common Data Service | MicrosoftDocs
description: 'Tietoja automaattisesti numeroitujen kenttien luonnista, hallinnasta ja käytöstä'
keywords: ''
ms.date: 02/26/2019
ms.service: powerapps
ms.custom: null
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: daemelia
ms.assetid: null
ms.author: daemelia
manager: kvivek
ms.reviewer: Mattp123
ms.suite: null
ms.tgt_pltfrm: null
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="autonumber-fields"></a>Automaattisesti numeroidut kentät

Automaattisesti numeroidut kentät ovat kenttiä, jotka muodostavat automaattisesti aakkosnumeerisia merkkijonoja aina, kun niitä luodaan. Tekijät voivat mukauttaa näiden kenttien muodon mieleisekseen ja antaa järjestelmän sitten luoda vastaavat arvot, jotka täyttävät ne automaattisesti suorituksen aikana.

Vaikka automaattisesti numeroitavat kentät ovat muodoltaan tekstikenttiä, joihin on lisätty toimintoja, [PowerApps](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc) yksinkertaistaa niitä näyttämällä **automaattisen numeroinnin** omana tietotyyppinään **Teksti**-luokassa. On tärkeää huomata, että [perinteinen ratkaisunhallinta](use-solution-explorer.md#classic-solution-explorer) ei tue automaattisesti numeroitujen kenttien luontia tai hallintaa.

Luo automaattisesti numeroidut kentät samalla tavoin kuin [kenttä luodaan](create-edit-field-portal.md#create-a-field) ja valitse vain **Automaattinen numerointi** avattavasta **Tietotyyppi**-luetteloruudusta. 

Voit aktivoida automaattisen numerointitoiminnon myös aiemmin luodussa tekstikentässä avaamalla kentän ja valitsemalla **Automaattinen numerointi** avattavasta **Tietotyyppi**-luetteloruudusta. Automaattinen numerointitoimintoa voidaan poistaa vastaavasti käytöstä koska tahansa avaamalla kenttä valitsemalla toinen vaihtoehto avattavasta **Tietotyyppi**-luetteloruudusta.

## <a name="autonumber-types"></a>Automaattiset numerointityypit

Automaattisesti numeroitujen kenttien luontia helpottamassa on muutama valmiiksi määritetty oletusarvoinen automaattinen numerointityyppi, joita voi käyttää useimmissa skenaarioissa. 

### <a name="string-prefixed-number"></a>Numero, jossa on etuliitemerkkijono

Yleisin automaattinen numerointimuoto on yksinkertainen numero, jossa on etuliitemerkkijono. Kun tämä tyyppi valitaan, automaattinen numerointi koostuu automaattisesti kasvavasta numerosta sekä valinnaisesta merkkijonosta, joka vakioetuliite. Esimerkiksi numero, jossa on etuliitemerkkijono, *Contoso*, muodostaisi seuraavat tietueet: *Contoso-1000*, *Contoso-1001*, *Contoso-1002* ja niin edelleen.

### <a name="date-prefixed-number"></a>Numero, jossa on päivämääräetuliite

Toinen yleinen automaattinen numerointimuoto on numero, jossa on päivämääräetuliite. Kun tämä tyyppi valitaan, automaattinen numerointi koostuu automaattisesti kasvavasta numerosta sekä muotoillusta päivämääräetuliitteestä. Tietueen päivämääräosa ilmaiseen sen päivämäärän ja UTC-ajan, jolloin tietue luotiin. Valittavana on erilaisia päivämäärämuotoja.
Numero, jossa on päivämääräetuliite, muodostaa esimerkiksi seuraavanlaisia tietueita: *2019-26-02-1000*, *2019-27-02-1000* ja *2019-28-02-1000*. Etuliitteen muodostuminen määräytyy kuluvan päivän valitun päivämäärämuodon mukaan.

### <a name="custom"></a>Mukautettu

Kehittyneiden käyttäjien erikoiskäyttötapauksia varten on mahdollista mukauttaa automaattisesti numeroidun kentän muoto kokonaisuudessaan. Muoto voi koostua merkkijonovakioista, automaattisesti kasvavista numeroista, muotoilluista päivämääristä tai satunnaisista aakkosnumeerisista sarjoista.
Lisätietoja mukautettujen muotojen määrittämisestä on kohdassa [AutoNumberFormat-asetukset](https://docs.microsoft.com/dynamics365/customer-engagement/developer/create-auto-number-attributes#autonumberformat-options).

## <a name="seed-values"></a>Alkuarvot

Automaattisesti numeroidun kentän alkuarvo on ensimmäinen numero, jota käytetään muodon numero-osassa. Jos esimerkiksi haluat automaattisesti numeroidun kentän muodostavan tietueita, kuten *Contoso-1000*, *Contoso-1001* ja *Contoso-1002*, toivottu alkuarvo on 1000, koska se on arvo, josta numerosarja alkaa. Automaattisesti numeroitujen kenttien oletusalkuarvo on 1000, mutta halutessasi määrittää mukautetun alkuarvon. 


> [!IMPORTANT]
> Alkuarvon määrittäminen muuttaa vain määritetyn määritteen nykyisen numeroarvon nykyisessä ympäristössä. Alkuarvo ei sisälly ratkaisuun, kun se tuodaan toiseen ympäristöön. 

## <a name="create-an-autonumber-field"></a>Automaattisesti numeroiden kentän luominen
  
1.  Kirjaudu [PowerApps-portaaliin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc).
  
2.  Laajenna vasemmassa ruudussa **Tiedot** ja valitse **Entiteetit**.
  
3.  Valitse automaattisesti numeroituun kenttään lisättävä entiteetti ja valitse sitten **Kentät**-välilehti.
  
4.  Valitse työkalurivillä **Lisää**-kenttä.  
  
5.  Anna oikeassa ruudussa **Näytä nimi** ja valitse **tietotyypiksi** **Automaattinen numerointi**.

    > [!div class="mx-imgBorder"] 
    > ![](media/create-autonumber-field.png "Automaattisesti numeroidun kentän luominen")
  
6. Määritä valinnaiset kentät tarvittaessa. Lisätietoja: [Kenttien luominen ja muokkaaminen](create-edit-field-portal.md#create-a-field)

7. Valitse automaattisen numeroinnin tyyppi tai säilytä **Numero, jossa on etuliitemerkkijono** -vaihtoehto.

8. Mukauta lähtöarvoa tai säilytä oletusarvo **1000**.

9. Valitse **Valmis**.

## <a name="see-also"></a>Katso myös
 [Kenttien luominen ja muokkaaminen Common Data Serviceen PowerApps-portaalin avulla](create-edit-field-portal.md)
