---
title: Tarkista kaaviosovelluksen helppokäyttöisyys | Microsoft Docs
description: Tunnista tapoja, joilla kaaviosovelluksesta voidaan tehdä helppokäyttöisempi käyttäjille, joilla on näkö-, kuulo- tai muita haittoja
author: emcoope-msft
ms.service: powerapps
ms.topic: article
ms.date: 07/05/2018
ms.author: emcoope
ms.openlocfilehash: 33f5f8dfe9f6c6fe31e07c1b626dc627c7cd29b0
ms.sourcegitcommit: dfa0e1a7981814e15e6ca4720e2a5f930e859db1
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 07/13/2018
ms.locfileid: "39023984"
---
# <a name="review-a-canvas-app-for-accessibility-in-powerapps"></a>Tarkista kaaviosovelluksen helppokäyttöisyys PowerAppsissa

Käyttäjät, joilla on näkö-, kuulo- tai muita rajoitteita, voivat käyttää kaaviosovellusta entistä helpommin, jos helppokäyttötoiminnot otetaan huomioon sovelluksen ulkoasun ja toimintojen suunnittelussa. Jos et ole varma, miten voit tehdä sovelluksistasi helppokäyttöisempiä, voit käyttää PowerApps Studion helppokäyttöisyyden tarkistusta. Tämä työkalu löytää mahdolliset helppokäyttöisyysongelmat ja kertoo myös miksi jokainen niistä voi osoittautua mahdolliseksi ongelmaksi käyttäjälle, jolla on tietty vamma, sekä tarjoaa ehdotuksia kunkin ongelman ratkaisemiseksi.
Helppokäyttöisyyden tarkistus havaitsee näytönlukijan ja näppäimistön ongelmat puolestasi. Saat myös tietoa siitä, miten värikontrastiongelmia voi korjata käyttämällä [helppokäyttöisyysvärejä](accessible-apps-color.md).

Helppokäyttöisyyden tarkistus auttaa tunnistamaan asetuksia, joita haluat mahdollisesti muuttaa, mutta ehdotuksia kannattaa aina harkita sovelluksesi käyttökontekstissa. Monet ehdotuksista saattavat olla kannattavia, mutta voit ohittaa kaikki, joista voi olla enemmän haittaa kuin hyötyä.

## <a name="find-accessibility-issues"></a>Löydä helppokäyttötoimintojen ongelmat

1. Valitse PowerApps Studion oikeasta yläkulmasta sovelluksen tarkistus -kuvake.

    ![Sovelluksen tarkistus -kuvake](./media/accessibility-checker/app-checker-icon.png)

2. Valitse ilmestyvästä valikosta **Helppokäyttötoiminnot**.

    ![Sovelluksen tarkistus -ruudun vaihtoehdot](./media/accessibility-checker/app-checker-menu.png)

    Näkyviin tulee luettelo ongelmista, jotka on lajiteltu ensin vakavuusasteen ja sitten näytön mukaan.

    ![Helppokäyttöisyyden tarkistus -ruutu ja kohdeluettelo](./media/accessibility-checker/accessibility-checker-pane.png)

3. Valitse kohteen vieressä oleva nuoli, tarkastellaksesi sen lisätietoja.

    ![Helppokäyttöisyyden tarkistuksen lisätiedot](./media/accessibility-checker/details-pane.png)

4. Palaa kohdeluetteloon valitsemalla taaksepäin osoittava nuoli.

5. Jos päätät korjata ongelman, valitse se, avataksesi kyseisen ominaisuuden.

6. Kun olet muuttanut vähintään yhtä ominaisuutta, valitse **Tarkista uudelleen** päivittääksesi ongelmaluettelon.

    Ratkaistut kohteet katoavat luettelosta ja uusia kohteita saattaa ilmaantua.

## <a name="severity-of-issues"></a>Ongelmien vakavuus

Helppokäyttöisyyden tarkistus luokittelee jokaisen ongelman virheeksi, varoitukseksi tai vihjeeksi, ongelman vakavuuden perusteella.

- **Virheet** ovat ongelmia, jotka tekevät sovelluksen käyttämisestä sekä ymmärtämisestä vammaiskäyttäjälle vaikeaa tai mahdotonta.
- **Varoitukset** ovat ongelmia, jotka tekevät sovelluksen käyttämisestä tai ymmärtämisestä vaikeaa useimmille vammaiskäyttäjille.
- **Vihjeiden** avulla voit parantaa vammaiskäyttäjien käyttökokemusta.

## <a name="types-of-issues"></a>Ongelmatyypit

| Ongelman otsikko                            | Vakavuus | Ongelman kuvaus  | Korjaaminen | Korjauksen hyödyt|
| ------------------------------         |:---------| -----| ------|------ |
| **Helppokäyttöisyysotsikko puuttuu**           | Virhe    | Kun vuorovaikutteisen ohjausobjektin helppokäyttöisyysotsikon ominaisuus ei sisällä tekstiä. Vuorovaikutteinen ohjausobjekti voi olla luontaisesti vuorovaikutteinen, kuten painike, tai sillä voi olla vuorovaikutteisia ominaisuuksia. Saatat esimerkiksi määrittää kuvan **OnSelect**-ominaisuuden tai asettaa sen **TabIndex**-ominaisuuden arvoksi 0 tai enemmän.  | Kuvaile kohde muokkaamalla helppokäyttöisyysotsikon ominaisuutta. | Jos helppokäyttöisyysotsikon ominaisuus ei sisällä tekstiä, näkövammainen henkilö ei ymmärrä mitä kuvat ja ohjausobjektit sisältävät. |
| **Kohdistus ei ole näkyvissä**                | Virhe    | Kun **FocusBorderThickness** ohjausobjektin arvoksi asetetaan 0. On hyvä varmistaa asianmukainen värikontrasti kohdistusreunan ja ohjausobjektin välille, jotta se näkyy selvästi. | Muuta **FocusedBorderThickness**-ominaisuuden arvoksi suurempi kuin 0.  | Jos kohdistus ei ole näkyvissä, ihmiset, jotka eivät käytä hiirtä, eivät pysty näkemään sitä käyttäessään sovellusta.   |
| **Tekstitys puuttuu**                   | Varoitus  | Kun **äänen** tai **videon** ohjausobjektin **ClosedCaptionsURL**-ominaisuus on tyhjä. | Aseta**ClosedCaptionsURL**-ominaisuus URL-osoitteeseen tekstityksen aktivoimiseksi. | Ilman tekstitystä, vammaiskäyttäjät eivät välttämättä saa mitään tietoja video- tai äänisegmentistä. |
| **Hyödylliset ohjausobjektin asetukset puuttuvat**   | Varoitus  | Kun useat asetukset (kuten otsikoiden näyttäminen, kaavioiden merkinnät ja **äänen**, **videon** ja **kynäsyötteen** ohjausobjektien oletusarvoiset ohjaukset) ovat poissa käytöstä. | Valitse varoitus ja aseta ominaisuuden arvoksi **tosi**. | Tämän ominaisuusasetuksen muuttaminen antaa käyttäjälle entistä parempia tietoja sovelluksesi ohjausobjektien toiminnasta. |
| **HTML ei ole käytettävissä**           | Varoitus  | Muu ohjausobjekti kuin HTML-teksti-ohjausobjekti sisältää HTML-koodia. Tässä tapauksessa PowerApps ei tuen mukautettujen HTML-elementtien helppokäyttöisyyttä. | Käytä muuta kuin HTML:ä tai poista HTML tästä elementistä. | Sovelluksesi ei toimi oikein eikä sitä voi käyttää, jos lisäät vuorovaikutteisen HTML-elementtejä. |
| **Poista automaattinen käynnistys käytöstä**                 | Varoitus  | Kun **äänen** tai **video** ohjausobjektin **automaattinen käynnistys** -ominaisuuden arvoksi on asetettu **tosi**. | Määritä ohjausobjektin **automaattinen käynnistys** -ominaisuuden arvoksi **epätosi**. | Automaattisesti käynnistyvät video- ja äänitiedostot voivat häiritä käyttäjiä. Anne heidän valita, haluavatko he toistaa tiedoston. |
| **Muokkaa näyttönimeä**                 | Vihje      | Näytöllä on oletusnimi, jonka näytönlukija lukee, kun käyttäjät siirtyy sovellukseen. | Anna näytölle nimi, joka kuvaa sitä, mitä näytössä on tai mihin sitä käytetään.| Sokeat tai heikkonäköiset, tai lukivaikeuksista kärsivät, ovat navigoidessaan riippuvaisia näytönlukijan lukemista näyttönimistä. |
| **Lisää teksti tilan ilmaisemisen**          | Vihje      |  Ohjausobjektilla on tila, kuten vaihtopainike, mutta arvo-otsikot ovat poissa käytöstä. | Määritä **ShowValue**-ominaisuuden ohjausobjektin arvoksi **tosi**, jotta sen tämänhetkinen tila näkyy. | Käyttäjät eivät saa vahvistusta toiminnoistaan, jos ohjausobjektin tila ei tule näkyviin. |
| **Tarkista näytön kohteiden järjestys**| Vihje      | **TabIndex**-ominaisuus on suurempi kuin 1. Sovelluksen luoja voi määrittää mukautetun välilehden tilaukset asettamalla **TabIndex** -ominaisuuden arvoksi numeerisen arvon, esimerkiksi 1, 2, 3 ja 4. Tämä vinkki muistuttaa sinua tarkistamaan näytön vuorovaikutteisen järjestyksen. Paras käytäntö on noudattaa rakennetta, jossa **TabIndex**-ominaisuuden arvo on 0.  | Varmista, että näyttösi elementit vastaavat järjestystä, jossa haluat käydä niitä läpi sarkainta käytettäessä. | Kun näytönlukija lukee sovelluksen osia, niiden pitäisi näkyä siinä järjestyksessä, jossa käyttäjä näkee ne, vähemmän intuitiivisen järjestyksen sijaan.  |
| **Lisää toinen syöttötapa**           | Vihje      | Sovellus sisältää **kynä**-ohjausobjektin. Tämä vinkki muistuttaa sisällyttämään erillisen syöttömenetelmän. | Lisää **tekstisyöte**-ohjausobjekti **kynä**-ohjausobjektin lisäksi taataksesi helppokäyttöisen kokemuksen. | Kaikki käyttäjät eivät voi käyttää kynää ja tarvitsevat toisen tavan tietojen syöttämiseksi (kuten esimerkiksi allekirjoituksen näppäily). |

## <a name="next-steps"></a>Seuraavat vaiheet

- [Helppokäyttöisten sovellusten luominen](accessible-apps.md)
- [Helppokäyttöisyysvärit](accessible-apps-color.md)
- [Helppokäyttöisyysasetukset](controls/properties-accessibility.md)
