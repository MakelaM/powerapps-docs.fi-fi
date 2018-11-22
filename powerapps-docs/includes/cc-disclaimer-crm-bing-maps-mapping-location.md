## <a name="mapping-functions-for-dynamics-365-customer-engagement-plan"></a>Dynamics 365 Customer Engagement Plan -sovelluksen yhdistämistoiminnot 
 Field Service- ja Project Service Automation -sovelluksella on tärkeitä sijaintiin perustuvia toimintoja. Esimerkkejä: palveluasiakkaan sijainti (joka määrittää, missä palvelu tai tehtävä suoritetaan), resurssien (palvelun tai tehtävän suorittavien henkilöiden) aloitus- ja lopetussijainnit.  Jotta järjestelmä voisi näyttää nämä kartalla – tai laskea sijaintien väliset etäisyydet –, on tarpeen käyttää karttapalvelua (tässä tapauksessa Bing Mapsia).  
  
 Seuraavassa on työnkulku Bing Maps -palveluun ja -palvelusta:  
  
|Dynamics 365:stä|Bing Maps palauttaa|Huomautus|  
|-----------------------|-----------------------|----------|  
|Osoite (asiakas tai resurssi)|Osoitteen leveys- ja pituusaste (sijainti)|Tätä kutsutaan osoitteen maantieteelliseksi koodiksi.|  
|Sijaintijoukko (leveys- ja pituusaste)|Sijaintien välinen etäisyys|Tätä voidaan käyttää resurssien optimoitujen reittien tai matka-aikojen laskemiseen.|  
|Sijaintijoukko (leveys- ja pituusaste)|Karttanäkymä, jossa sijainnit on merkitty karttaan|Tätä käytetään asiakkaiden ja resurssien tarkasteluun karttanäkymässä.|  
  
> [!NOTE]
>  Yllä olevien tietojen lisäksi Bing Maps -palveluun ei lähetetä muita tietoja.
