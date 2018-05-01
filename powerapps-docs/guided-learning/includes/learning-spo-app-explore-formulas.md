Yksi PowerAppsin tärkeimmistä eduista on se, että sinun ei tarvitse kirjoittaa perinteistä koodia. Sinun ei tarvitse olla ohjelmankehittäjä laatiaksesi sovelluksia! Tarvitset kuitenkin tavan ilmaista sovelluksen logiikkaa, jotta voit hallita sovelluksen siirtymiä, suodatusta, lajittelua ja muita toimintoja. Tässä vaiheessa kaavat tulevat mukaan kuvaan. Jos olet käyttänyt Excel-kaavoja, PowerAppsin lähestymistapa tuntuu sinusta varmasti tutulta. Tässä ohjeaiheessa esittelemme muutamia peruskaavoja tekstin muotoiluun ja käymme sitten läpi kolme kaavaa, joita PowerApps käyttää luodussa sovelluksessa. Saat esimakua siitä, mihin kaavat pystyvät. Tämän jälkeen voit käyttää jonkin verran aikaa luodussa sovelluksessa olevien muiden kaavojen tarkasteluun ja omiesi kirjoittamiseen.

## <a name="understanding-formulas-and-properties"></a>Kaavojen ja ominaisuuksien ymmärtäminen
Edellisessä ohjeaiheessa otimme mukaan Hinta-kentän selaa näyttöjä -valikoimassa, mutta se näkyi pelkkänä numerona ilman valuuttasymbolia. Oletetaan, että haluamme lisätä dollarimerkin ja muuttaa myös tekstin värin sen mukaan, kuinka paljon kohde maksaa (esimerkiksi punainen, jos hinta on yli 5 $, muussa tapauksessa vihreä). Idea näkyy seuraavassa kuvassa.

![Tekstin muotoilu väriä ja valuuttaa varten](./media/learning-spo-app-explore-formulas/text-formatting.png)

Aloitetaan valuuttamuotoilulla. Oletusarvoisesti PowerApps hakee vain kunkin kohteen hinta-arvon, joka on määritetty **Text**-*ominaisuutena* selitteelle, joka näyttää hinnan.

![Hinnan oletusmuotoilu](./media/learning-spo-app-explore-formulas/price-default.png)

Voit lisätä Yhdysvaltain valuuttasymbolin napsauttamalla tai napauttamalla selitteen ohjausobjektia ja määrittämällä kaavarivillä **Text**-ominaisuuden tälle kaavalle.

![Hinnan valuuttamuotoilu](./media/learning-spo-app-explore-formulas/price-formatted.png)

Kaavassa `Text(Price, "[$-en-US]$ ##.00"` käytetään **Text***-funktiota* sen määrittämiseen, miten luku muotoillaan. Kaava on kuin Excel-kaava, mutta PowerAppsin kaavat viittaavat ohjausobjekteihin ja muihin sovelluksen elementteihin laskentataulukon solujen sijaan. Jos napsautat tai napautat ohjausobjektia ja sen jälkeen ominaisuuksien avattavaa luetteloa, näet luettelon niistä ominaisuuksista, jotka liittyvät ohjausobjektiin. Esimerkiksi tässä on osittainen luettelo selitteen ominaisuuksista. Jotkin ominaisuudet ovat olennaisia laajalle valikoimalle ohjausobjekteja ja muut vain tietylle ohjausobjektille.

![Ominaisuuksien määrittäminen](./media/learning-spo-app-explore-formulas/properties.png)

Voit muotoilla värin ehdollisesti hinnan perusteella käyttämällä seuraavanlaista kaavaa selitteen **Color**-ominaisuudelle: `If(Price > 5, Color.Red, Color.Green)`.

![Hinnan värimuotoilu](./media/learning-spo-app-explore-formulas/color-formatted.png)

## <a name="formulas-included-in-the-generated-app"></a>Luotuun sovellukseen sisältyvät kaavat
Nyt kun osaat käyttää kaavoja ominaisuuksien yhteydessä, tutustumme kolmeen esimerkkiin kaavoista, joita PowerApps käyttää luodussa sovelluksessa. Kaikki esimerkit ovat selausnäytöstä ja toimivat OnSelect-ominaisuuden avulla, joka määrittää mitä tapahtuu, kun käyttäjä napsauttaa tai napauttaa sovelluksen ohjausobjektia.

* Ensimmäinen kaava liittyy **IconNewItem1**-ohjausobjektin: ![Uusi kohde -kuvake](./media/learning-spo-app-explore-formulas/icon-add-item.png). Napsauta tai napauta tätä ohjausobjektia siirtyäksesi muokkaa-/luo-näyttöön ja luo kohde. 
  
  * Kaava on `NewForm(EditForm1);Navigate(EditScreen1, ScreenTransition.None)`
  * Kaava *muodostaa* uuden muokkauslomakkeen ja siirtyy sitten muokkaa-/luo-näyttöön, jotta voit luoda uuden kohteen. Arvo `ScreenTransition.None` tarkoittaa, että näyttöjen välillä ei ole siirtymää (kuten häivytystä).
* Toinen kaava liittyy **IconSortUpDown1**-ohjausobjektiin: ![Lajittele valikoima -kuvake](./media/learning-spo-app-explore-formulas/icon-sort.png). Lajittele kohdeluettelo selausnäytön valikoimassa napsauttamalla tai napauttamalla tätä ohjausobjektia.
  
  * Kaava on `UpdateContext({SortDescending1: !SortDescending1})`
  * Kaavassa `UpdateContext` päivittää *muuttujan*, jonka nimi on `SortDescending1`. Muuttujan arvo muuttuu edestakaisin, kun napsautat ohjausobjektia. Tämä kertoo tässä näytössä olevalle valikoimalle, miten kohteita lajitellaan (saat lisätietoja katsomalla videon). 
* Kolmas kaava liittyy **NextArrow1**-ohjausobjektiin: ![Siirry tietoihin -nuolikuvake](./media/learning-spo-app-explore-formulas/icon-arrow.png). Siirry selausnäytöstä tiedot-näyttöön napsauttamalla tai napauttamalla tätä ohjausobjektia.
  
  * Kaava on `Navigate(DetailScreen1, ScreenTransition.None)`
  * Kaava aiheuttaa siirtymisen tiedot-näyttöön, tässäkin ilman siirtymää.

Sovelluksessa on monia muita kaavoja, joten käytä vähän aikaa ohjausobjektien napsauttamiseen ja sen katsomiseen, mitä kaavoja eri ominaisuuksille on määritetty.

## <a name="wrapping-it-all-up"></a>Yhteenveto tästä kaikesta
Tähän päättyy luodun sovelluksen tutkiskelu ja sovelluksen ominaisuudet aikaan saavien näyttönäkymien, ohjausobjektien, ominaisuuksien ja kaavojen kulissien taakse kurkistaminen. Jos olet seurannut mukana, sinun pitäisi nyt ymmärtää luodun sovelluksen toimintaa paremmin. Nyt voit hyödyntää tätä ymmärrystä laatiessasi omia sovelluksiasi. 

Ennen kuin siirryt seuraavaan osaan, haluamme palata SharePointiin ja näyttää, miten sovellus on nyt integroitu luettelokokemuksen kanssa. Kuten näet, **LattiaSovellus** toimii nyt *näkymänä* luetteloon ja käynnistät sovelluksen napsauttamalla **Avaa**. Tämä on yksinkertainen tapa hallita luetteloita niin, että käyttökokemus on helppo ja mukautettu.

![Sovellus näkymänä Sharepoint-luetteloon](./media/learning-spo-app-explore-formulas/list-view.png)
