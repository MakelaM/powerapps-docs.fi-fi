Jos olet käynyt läpi kurssin vaiheet tähän asti, olet viettänyt jonkin verran aikaa web.powerapps.comissa. Ehkä et tiedä, että olet työskennellyt erityisessä *ympäristössä* koko tämän ajan. Ympäristö on yksinkertaisesti ryhmä sovelluksia ja muita resursseja (kerromme tästä hetken kuluttua lisää). Katso web.powerapps.com-näytön oikeaa yläkulmaa. Siellä on avattava valikko, joka näyttää nykyisen ympäristön.

![Ympäristön valitsin](./media/learning-manage-environments/environment-picker.png)

Jos olet uusi PowerApps-käyttäjä, käytät tässä vaiheessa ehkä vasta oletusympäristöä. Tarkista, onko muita ympäristöjä käytettävissä napsauttamalla tai napauttamalla valikkoa.

## <a name="why-use-environments"></a>Miksi ympäristöjä käytetään?
Ympäristö on säilö sovelluksille ja muille resursseille, kuten Microsoft Flow’n tietoyhteyksille ja työnkuluille. Sen avulla ryhmitetään asioita liiketoimintavaatimusten perusteella. Lisäympäristöjä oletusympäristön lisäksi voidaan luoda useista eri syistä:

* **Erittele sovelluskehitys osaston mukaan**: suuressa organisaatiossa kukin osasto voi työskennellä eri ympäristössä.
* **Tue sovelluksen elinkaaren hallintaa (ALM)**: pidä ympäristöt erillisinä kehitettäville sovelluksille ja jo valmiille ja jaetuille sovelluksille.
* **Hallitse tietojen käyttöä**: kullakin ympäristöllä voi olla oma Common Data Service for Apps -tietokanta muiden tietoyhteyksien ollessa ympäristökohtaisia (eli ei jaettuja ympäristöjen kesken).

Kannattaa pitää mielessä, että ympäristöt ovat relevantteja vain sovellusten luojille ja PowerApps-järjestelmänvalvojille. Kun jaat sovelluksen käyttäjälle, kyseinen käyttäjä vain suorittaa sovellusta, niin kauan kuin hänellä on asianmukaiset käyttöoikeudet. Hänen ei tarvitse välittää siitä, mistä ympäristöstä se on peräisin.

## <a name="create-an-environment"></a>Ympäristön luominen
Tähän mennessä tällä kurssilla olemme keskittyneet sovellusten luojiin, mutta ympäristöjä luovat ja ylläpitävät järjestelmänvalvojat. Jos et ole järjestelmänvalvoja, nämä tiedot saattavat silti olla hyödyllisiä, kun keskustelet järjestelmänvalvojan kanssa ympäristöjen määrittämisestä. Napsauta tai napauta PowerApps-hallintakeskuksessa **Ympäristöt** ja sitten**Uusi ympäristö**. Anna ympäristölle nimi **Uusi ympäristö** -näytössä, valitse alue, määritä, luodaanko Common Data Service for Apps -tietokanta ympäristölle, ja napsauta tai napauta sitten **Luo ympäristö**.

![Ympäristön luominen](./media/learning-manage-environments/create-environment.png)

Siinä kaikki: olet luonut uuden ympäristön, jossa voit työskennellä. Jos siirryt takaisin osoitteeseen web.powerapps.com, näet sen ympäristöjen avattavassa valikossa.

## <a name="manage-access-to-an-environment"></a>Ympäristön käyttöoikeuksien hallinta
Sinulla on ympäristön käyttöoikeus, jos olet:

* **Ympäristön järjestelmänvalvoja**: sinulla on täydet ympäristön käyttöoikeudet.
* **Ympäristön tekijä**: näet kaikki sovellukset, voit luoda sovelluksia ja työskennellä Common Data Service for Appsin parissa (muut käyttöoikeudet ovat voimassa).

Järjestelmänvalvojana myönnät käyttöoikeuksia ympäristölle **Ympäristöt**-välilehdestä. Napsauta tai napauta ensin ympäristöä. Jos haluat lisätä jonkun (tässä esimerkissä **ympäristön tekijän**), napsauta tai napauta **Ympäristöroolit** ja sitten **Ympäristön tekijä**. Nyt voit lisätä käyttäjiä tai ryhmiä rooliin. Napsauta sitten **Tallenna**.

![Ympäristön käyttöoikeuksien hallinta](./media/learning-manage-environments/environment-access.png)

Olemme tutustuneet ympäristöjen etuihin, niiden luomiseen ja käyttöoikeuksien myöntämiseen. Vaikka et ole järjestelmänvalvojaroolissa, on hyödyllistä tietää, miten se toimii. 

Olemme päässeet sovellusten hallintaosion loppuun ja samalla tämän ohjatun oppimisen kurssin loppuun. Toivottavasti sinulla on ollut hauskaa ja olet oppinut paljon. Kerro meille, jos haluat antaa palautetta, ja käy täällä jatkossakin – aiomme lisätä sisältöä ajan myötä. Saat perusteellisempaa tietoa heti tutustumalla [PowerApps-dokumentaatioon](https://docs.microsoft.com/powerapps/). 

