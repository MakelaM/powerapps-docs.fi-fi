Kurssin tässä osiossa luodaan sovellus SharePoint-luettelosta "Flooring Estimates." Sovellusta voi esimerkiksi käyttää arvioija asiakkaan tiloissa luettelon tarkistamiseksi ja päivittämiseksi. Aloittaminen-osiossa näytettiin, kuinka sovellus voidaan luoda samasta luettelosta – miksi siis katsomme sitä taas? Ensinnäkin emme aloita PowerApps Studiolla vaan näytämme, kuinka PowerApps on integroitu SharePoint Onlineen. Toiseksi tarkastelemme lähemmin sovelluksen rakennetta ja näytämme, kuinka sitä voi mukauttaa. Saat tästä osiosta varmasti uusia tietoja, joten aloitetaanpa!

## <a name="generate-the-app"></a>Sovelluksen luominen
Seuraavassa kuvassa näytetään SharePoint-luettelo "Flooring Estimates", joka sisältää perustietoja, kuten nimen ja hinnan sekä kuvan eri lattiatyypeille. Tässä voit nähdä, kuinka PowerApps ja Microsoft Flow on integroitu SharePoint Onlineen, jotta voit rakentaa helposti sovelluksia ja työnkulkuja luetteloistasi.

![Flooring Estimates -luettelo](./media/learning-spo-app-generate/flooring-estimates-list.png)

Rakenna sovellus napsauttamalla **PowerApps** ja sitten **Luo sovellus**. Syötä oikeanpuoleiseen ruutuun sovelluksen nimi ja napsauta **Luo**. Kun olet napsauttanut **Luo**, PowerApps alkaa luomaan sovellusta. PowerApps tekee erinäisiä tietoihin liittyviä päätelmiä, jotta se luo aloituspisteeksi hyödyllisen sovelluksen.

![Sovelluksen luominen luettelosta](./media/learning-spo-app-generate/generate-app.png)

## <a name="view-the-app-in-powerapps-studio"></a>Sovelluksen näyttäminen PowerApps Studiossa
Uusi kolmen näytön sovelluksesi avautuu PowerApps Studiossa. Kaikilla tiedoista luoduilla sovelluksilla on samat näytöt:

* **Selaa**-näyttö: tässä voit selata, lajitella, suodattaa ja päivittää luettelosta noudettuja tietoja sekä lisätä kohteita napsauttamalla (+)-kuvaketta.
* **Tiedot**-näyttö: tässä voit tarkastella kohteen tietoja sekä poistaa kohteen tai muokata sitä.
* **Muokkaa/luo**-näyttö: tässä muokataan olemassa olevaa kohdetta tai luodaan uusi.

Voit vaihtaa pikkukuvanäkymään napsauttamalla tai napauttamalla vasemman navigointipalkin oikeassa yläkulmassa olevaa kuvaketta.

![Näkymien vaihtaminen](./media/learning-spo-app-generate/toggle-view.png)

Napsauta tai napauta pikkukuvaa, niin näet kyseisen näytön ohjausobjektit.

![Luotu sovellus](./media/learning-spo-app-generate/generate-finished-app.png)

## <a name="run-the-app-in-preview-mode"></a>Sovelluksen suorittaminen esikatselutilassa
Napsauta tai napauta ![sovelluksen esikatselunuolta](./media/learning-spo-app-generate/f5-arrow-sm.png) oikeassa yläkulmassa, niin sovellus käynnistyy. Sovellusta selaamalla näet, että se sisältää kaikki luettelon tiedot ja tarjoaa hyvän oletuskokemuksen.

![Sovelluksen suorittaminen esikatselutilassa](./media/learning-spo-app-generate/generate-run-app.png)

Seuraavaksi tutkimme sovellusta yksityiskohtaisemmin ja myöhemmin mukautamme sovellusta, jotta se sopii paremmin tarpeisiin.

