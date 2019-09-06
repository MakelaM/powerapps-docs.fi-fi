---
title: 'Pika-aloitusopas, joka sisältää ohjeita olemassa olevan ympäristön käyttämiseen ja vanhan WWW-asiakasohjelman tarkistamiseen Unified Interfacessa | MicrosoftDocs'
description: Lisätietoja siirron suunnittelemisesta ja suorittamisesta vanhasta WWW-asiakasohjelmasta Unified Interfaceen
ms.custom: ''
ms.date: 07/24/2019
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - powerapps
author: Mattp123
ms.assetid: null
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---


<!--editor comment: I notice two mentions of Dynamics 365 Home page and both are followed by the URL but the text isn't linked. Just want to point that out in case it wasn't intentional. -->


# <a name="quick-start-for-using-an-existing-environment-to-validate-your-legacy-web-client-app-with-the-unified-interface"></a>Pika-aloitusopas, joka sisältää ohjeita olemassa olevan ympäristön käyttämiseen ja vanhan WWW-asiakasohjelman tarkistamiseen Unified Interfacessa

Tässä pikaoppaan aiheessa näytetään, miten olemassa olevaa ympäristöä käytetään Unified Interface -sovelluksen luomisessa nykyisen määrityksen tai oletusratkaisun perusteella. Näin on mahdollista tutkia ja testata Unified Interfacea samalla, kun olemassa olevia vanhoja WWW-asiakasohjelmia suoritetaan rinnakkain. Käyttäjä voi tämän jälkeen vaihtaa ympäristöjä rinnakkaisessa näkymässä. Lisätietoja samanlaisista ohjeista, joissa kerrotaan uuden Sandbox-ympäristön luomisesta, testaamisen eristämisestä ja vain Unified Interface -kokemuksen tarkastelemisesta, on kohdassa [Pikaopas Dynamics 365 for Customer Engagement -sovellusten vanhan WWW-asiakasohjelman siirtämisestä Unified Interfaceen](transition-web-app.md).

> [!IMPORTANT]
>  Jos käytössä on Dynamics 365 for Field Service- tai Dynamics 365 for Project Service Automation -sovellus, saat lisätietoja kohdasta [Dynamics 365 for Customer Engagement -sovellukset](transition-web-app.md#dynamics-365-for-customer-engagement-apps).

## <a name="prerequisites"></a>Edellytykset 
- Olemassa olevan Dynamics 365 for Sales- tai Service-sovelluksen vanha WWW-asiakasohjelma. 
- Sovelluksen testauksessa suositellaan käytettäväksi muuta kuin tuotantoympäristöä. Tämä ei kuitenkaan ole pakollista. Lisätietoja: [Sandbox-ympäristöjen hallinta](/dynamics365/customer-engagement/admin/manage-sandbox-instances) 

## <a name="overview"></a>Yleiskatsaus 
Tässä aiheessa on ohjeita olemassa oleville vanhoja WWW-asiakasohjelmia käyttäville asiakkaille, joiden on suunniteltava ja suoritettava siirtyminen Unified Interfaceen. Jos haluat määrittää rinnakkaisen ympäristön, luo uusi sovellus oletusratkaisun tämänhetkisen tilan perusteella. Tämän voi tehdä nykyisessä Sandbox-kehitysympäristössä niin, että käynnissä olevaa työtä ei muuteta.

Kun tässä artikkelissa mainitut vaiheet on suoritettu, soveltuvat roolit omaavat käyttäjät näkevät uuden sovelluksen sovellusluettelossa sekä Dynamics 365 for Customer Engagement -sovelluksen avattavassa sovellusluettelossa että Dynamics 365:n aloitussivulla (http://home.dynamics.com).

![Sovellusluettelo](media/app-list.png)

Kun olet suorittanut tämän aiheen tehtävät kehitysympäristössä ratkaisun avulla, voit tuoda ratkaisun testausympäristöön. Näin suurempi ryhmä yrityksen käyttäjiä voi testata sovelluksia ja vertailla niitä tutussa ympäristössä. 

Noudata sovelluksen elinkaaren hallintapalveluita ja kehitystoimintojen prosesseja. Suosittelemme kaikkien näiden vaiheiden suorittamista ratkaisun kontekstissa. Kun sovellus on testattu ja tarkistettu kehitysympäristössä, sitä voi testata lisää käynnistämällä sovellus pilottiohjelmana useammille käyttäjille esimerkiksi tuotantoympäristössä. Kun käytössä on mallipohjainen sovellus ja ratkaisun sisäinen sivustokartta, sovellus voidaan viedä luontiympäristöstä ympäristön putken olemassa olevien prosessien mukaan. 

## <a name="process-for-validating-your-legacy-web-client-app-in-an-existing-environment"></a>Vanhan WWW-asiakasohjelman tarkistusprosessi olemassa olevassa ympäristössä
 
Vanhan WWW-asiakasohjelman tarkistusprosessi olemassa olevassa ympäristössä sisältää seuraavat kolme vaihetta:  

1.  Oletusratkaisuun perustuvan uuden ratkaisun luominen
2.  Uuden mallipohjaisen sovelluksen luominen 
3.  Sovelluksen ominaisuuksien määrittäminen  

Jos olet vaihtanut kehitysympäristössä lähiaikoina **Käytä vain Unified Interface -sovellusta** -tilaksi **Päällä**, kuten [Pikaopas Dynamics 365 for Customer Engagement -sovellusten vanhan WWW-asiakasohjelman siirtämisestä Unified Interfaceen](transition-web-app.md) -aiheessa ehdotettiin, vaihda asetuksen tilaksi **Pois päältä**. Tällöin voit suorittaa olemassa olevia vanhoja WWW-asiakasohjelmia.

### <a name="create-a-new-solution-thats-based-on-the-default-solution"></a>Oletusratkaisuun perustuvan uuden ratkaisun luominen
1. Kirjaudu [PowerApps Maker -portaaliin](https://make.powerapps.com).   
2. Valitse ympäristöluettelosta haluamasi ympäristö.  
3. Valitse vasemmassa siirtymisruudussa **Ratkaisut**. 
4. Valitse valikkoriviltä **Uusi ratkaisu**. 
5. Anna **Uusi ratkaisu** -ruutuun seuraavat ominaisuudet: 
   - **Nimi**. Kirjoita ratkaisun nimi. Esimerkiksi *Unified Interface -sovellus*. 
   - **Julkaisija**. Valitse julkaisija, jota organisaatiossa käytetään. Varmista, että olemassa olevissa mukautuksissa noudatetaan mukautusten hallintaa. Näin varmistetaan, että mallipohjaisen sovelluksen ja sen sivustokartan rakennenimet ovat yhdenmukaisia olemassa olevien standardien kanssa. 
   - **Versio**. Tämä on määritettävä olemassa olevien standardien ja ratkaisujen hallinnan mukaan. 
6. Valitse **Luo**.  
7. Uusi ratkaisu luodaan ratkaisuluetteloon. Avaa ratkaisu valitsemalla se. Siirry sitten seuraavaan osaan. 

### <a name="create-a-new-model-driven-app-in-the-new-solution"></a>Uuden mallipohjaisen sovelluksen luominen uudessa ratkaisussa
Tässä vaiheessa luodaan uusi sovellus, joka hyödyntää olemassa olevia mukautuksia. Nyt voit käyttää niitä Unified Interfacessa. Sovellus luodaan edellisessä osassa luodun uuden ratkaisun säilössä.  

1. Valitse valikkoriviltä **Uusi**, osoita **Sovellus**-kohtaa ja valitse sitten **Mallipohjainen sovellus**.
2. Syötä **Luo uusi sovellus** -sivulla seuraavat ominaisuudet: 
   - **Nimi**. Anna sovellukselle haluamasi nimi. Esimerkiksi *Sovelluksen nimi* + *Uusi* tai *Unified Interface -testi*. 
   - **Yksilöllinen nimi**. Tämä alkaa ratkaisun etuliitteellä ja määrittämäsi sovelluksen nimen yksinkertaisella versiolla. Voit tehdä muutoksia tai jättää nimen tällaiseksi.  
   - **Kuvaus** Lisää sovelluksen kuvaus, kuten *Ratkaisumme uuden Unified Interfacen testaamista varten*.  
3. Valitse **Käytä olemassa olevaa ratkaisua sovelluksen luomiseksi** ja valitse sitten **Seuraava**. 
4. Valitse **Valitse ratkaisu** -luettelossa **Oletusluettelo**. Valitse sitten **Valitse sivustokartta** -luettelossa **Sivustokartta** ja valitse lopuksi **Valmis**.  

   > [!div class="mx-imgBorder"] 
   > ![Valitse olemassa oleva ratkaisu](media/select-existing-solution.png "Valitse olemassa oleva ratkaisu")

5. Avautuvassa sovellusten suunnitteluohjelmassa näkyvät kaikki oletusratkaisun sovelluksen osat. Valitse **Julkaise**.  
6. Kun julkaisuprosessi on valmis, valitse **Toista**.  

Selaimeen avautuu uusi ikkuna, joka sisältää uuden mallipohjaisen sovelluksen ja kaikki Dynamics 365 for Customer Engagement -oletussovelluksen entiteetit, sivustokartan ja sivustokartan mukautukset.  

> [!div class="mx-imgBorder"] 
> ![Uusi Unified Interface -sovellus](media/new-unified-interface-app.png "Uusi Unified Interface -sovellus")

Huomaa, että kun siirryt takaisin PowerApps Maker -portaalin **Ratkaisut**-alueen selaimen välilehteen, uusi mallipohjainen sovellus ja samalla tavalla nimetty sivustokartan työasemaohjelman laajennus ovat luodun ratkaisun osia.  

> [!div class="mx-imgBorder"] 
> ![Ratkaisun resurssit](media/solution-assets.png "Ratkaisun resurssit")

Tässä vaiheessa luotiin uusi mallipohjainen sovellus ratkaisun sisälle. Sen voi tuoda testaus- tai arviointiympäristöihin. Uutta sovellusta voi nyt käyttää. Ennen käyttöönottoa määritetään kuitenkin seuraavassa vaiheessa joitakin uuden sovelluksen asetuksia. Näin sovellus on mahdollista jakaa muiden käyttäjien kanssa.

### <a name="configure-app-properties"></a>Sovelluksen ominaisuuksien määrittäminen
Mallipohjaisen sovelluksen ominaisuuksien määrittämisessä vaadittavat tehtävät ovat seuraavat: 

- Uuden sovelluksen käyttäjäroolien delegoiminen, jotta muut kuin järjestelmänvalvojat voivat käyttää sovellusta.  
- Käyttäjäystävällisen URL-osoitteen muokkaaminen niin, että uuden sovelluksen linkin jakaminen, kirjanmerkiksi lisääminen ja muistaminen on helppoa. 


1. Siirry kohtaan *ympäristön URL-osoite*/**sovellukset**. URL-osoite näyttää tältä: https://*OmaYmpäristö*.crm.dynamics.com/sovellukset. Nyt näyttöön avautuu luettelo kaikista ympäristön sovelluksista. 
2. Etsi luotu mallipohjainen sovellus.  
3. Valitse sovellusruudussa kolme pistettä ja valitse sitten **Roolien hallinta**.   

   > [!div class="mx-imgBorder"] 
   > ![Roolien hallinta](media/select-app-ellipsis.png "Roolien hallinta")

4. Käytettävissä olevien roolien alue näkyy oikeanpuoleisessa ruudussa. Valitse tarvittavat roolit, jotta muut kuin järjestelmänvalvojakäyttäjät voivat käyttää sovellusta. 

    > [!IMPORTANT]
    > Varmista, että kaikille käyttäjille myönnetään vähintään yksi käyttöoikeusrooli, joka sisältää **mallipohjaisen sovellus** -oikeuden **lukuoikeuden**. Tämä oikeus löytyy käyttöoikeusroolin Mukautus-välilehdestä. Jos käyttäjällä ei ole tätä oikeutta, hänelle näytetään virhesanoma mallipohjaisen sovelluksen avaamisen yhteydessä.  Huomaa, että järjestelmänvalvojan ja järjestelmän mukauttajan käyttöoikeusrooleilla on jo tämä oikeus. 
 
   > [!div class="mx-imgBorder"] 
   > ![Mallipohjaisen sovelluksen oikeus](media/model-driven-app-privilege.png "Mallipohjaisen sovelluksen oikeus")

5. Vaihtoehtoisesti voit laajentaa **Roolien hallinta** -ruudussa **Sovelluksen URL-osoitteen jälkiliite** -kohdan, jos haluat mukauttaa mallipohjaisen sovelluksen käyttäjäystävällistä URL-osoitetta. Huomaa, että voit määrittää nimeksi lähes mitä tahansa. Voit esimerkiksi kirjoittaa *new* (uusi), jolloin esikatselussa näkyy URL-osoite *https://YourEnvironment.crm.dynamics.com/apps/new*.   

   > [!div class="mx-imgBorder"] 
   > ![Sovelluksen URL-osoitteen jälkiliite](media/app-url-suffix.png "Sovelluksen URL-osoitteen jälkiliite")

   Tästä tulee käyttäjäystävällinen URL-osoite, jota käytetään ja joka jaetaan niin, että käyttäjät voivat käynnistää Unified Interfacen suoraan. Käyttäjät voivat merkitä tämän linkin kirjanmerkkeihin. 

6. Valitse **Tallenna**. 

Nyt soveltuvat roolit omaavat käyttäjät näkevät uuden sovelluksen sovellusluettelossa sekä Dynamics 365 for Customer Engagement -sovelluksen avattavassa sovellusluettelossa että Dynamics 365:n aloitussivulla (http://home.dynamics.com). 
  
   ![Sovellusluettelo](media/app-list.png "Sovellusluettelo")

Koska **Käytä vain Unified Interface -sovellusta** -tilan arvoksi on määritetty **Pois päältä** käyttäjien siirtyessä ympäristön juuren URL-osoitteeseen, heidän on yhä siirryttävä **Dynamics 365 – Custom** -oletussovellukseen kuten aiemminkin. Tämä on odotettava toiminta, jos haluat jatkaa olemassa olevien vanhojen WWW-asiakasohjelmien tukemista Unified Interface -sovellusten testaamisen ja niiden käyttämisen yhteydessä.  

## <a name="compare-your-new-app-to-the-default-dynamics-365-app"></a>Uuden sovelluksen ja Dynamics 365 -oletussovelluksen vertaileminen  
Nyt olet valmis käynnistämään sovelluksen. Voit vertailla uutta Unified Interface -sovellusta Dynamics 365:n mukautettuun sovellukseen käyttämällä esimerkiksi samoja tietoja, käyttäjärooleja, liiketoimintasääntöjä, työnkulkuja ja laajennuksia, koska ne ovat samassa ympäristössä. Näin voit osoittaa organisaatiolle, että kaikki perustoiminnot ovat yhä käytettävissä, ja samalla antaa mahdollisuuden uusien Unified Interface -sovelluksen parannusten tutkimiseen.  

> [!TIP]
> Jos haluat, että sovellukset näkyvät rinnakkain yhdessä näytössä, voit painaa Windows-näppäintä ja vasenta (tai oikeaa) nuolinäppäintä yhtaikaa. Tällöin selainikkunat jaetaan samassa näytössä. 

> [!NOTE]
> Jos jatkat mukautusten tekemistä oletussivustokartassa (esimerkiksi painikkeiden ja toimintojen siirtymisen tai valintanauhan syvempien mukautusten muutosten tekemistä), sinun on toistettava prosessi luomalla toinen mallipohjainen sovellus tai suoritettava samat mukautukset mallipohjaiseen sovellukseen liittyvässä uudessa sivustokartassa.  

## <a name="validate-your-new-app"></a>Uuden sovelluksen tarkistaminen  
Koska Unified Interface esitellään sovelluksessa, voit aloittaa sovelluksen, prosessien ja mukautusten tarkistuksen ja määrittää, miltä siirtäminen näyttää. Suosittelemme kaikkien käyttötapausten testaamista. Voit aloittaa tärkeimmistä tapauksista tai ryhmitellä tapaukset loogisiksi rakennemalleiksi. Koska Unified Interface perustuu vuorovaikutteiseen rakenteeseen, testit kannattaa aina tehdä eri laitteissa ja erilaisilla näyttöresoluutioilla. Sovelluksen testaamisen yhteydessä voi tarkistaa, että mukautukset ovat yhteensopivia Unified Interfacen kanssa. Samalla on mahdollista tarkistaa mahdolliset muokattavat tai puuttuvat toiminnot.  

> [!IMPORTANT]
> Common Data Service- ja Dynamics 365 for Customer Engagement -sovellusten nykyinen versio sisältää yhä useita vanhentuneita toimintoja. Tarkista, onko sovelluksessa vanhentuneita toimintoja, ja korjaa ne tarvittaessa uusilla ominaisuuksilla. Lisätietoja: [Tärkeitä Dynamics 365 Customer Engagementin tulevia muutoksia (vanhentumisia)](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming)

> [!TIP]
> The PowerApps -tarkistustyökalu auttaa ratkaisun osien laadun tarkistamisessa.  Lisätietoja: [Mallipohjaisten sovellusten tarkistaminen PowerAppsissa ratkaisun tarkistustoiminnolla](../common-data-service/use-powerapps-checker.md)

## <a name="next-steps"></a>Seuraavat vaiheet
Havaintojesi perusteella käyttöönottoryhmä tai kumppani voi arvioida työmäärän, joka tarvitaan sovelluksen siirtämiseksi Unified Interfaceen, sekä määrittää mahdolliset käytettävyyteen tehtävät parannukset. Unified Interface sisältää useita uusia toimintoja ja ominaisuuksia. Tämän ansiosta ratkaisusta on aiempaa enemmän hyötyä sovelluksen käyttäjille. 

Unified Interfaceen siirtyminen mahdollistaa nykyaikaisen käyttöliittymän tekemisen sekä olemassa olevien prosessien käyttämisen. Näin voit varmistaa niiden toimivuuden ja mahdolliset parannustarpeet. Nyt kannattaa myös miettiä sitä, vastaako sovellus liiketoiminnan vaatimuksia ja tulisiko olemassa oleva sovellus jakaa eri ryhmien ja roolien sovelluksille.
Lisätietoja: [Mallipohjaisten sovellusten suunnitteleminen sovellusten suunnitteluohjelman avulla](design-custom-business-apps-using-app-designer.md) 

### <a name="see-also"></a>Katso myös
<!-- Unified Interface transition community (link tbd) <br />  -->
[Unified Interface -käsikirja](unified-interface-playbook.md) <br />
[Siirtyminen kohti käyttökokemusta ja Unified Interface -siirtymää](approaching-unified-interface.md) <br />
[Tietoja Unified Interfacesta](/dynamics365/customer-engagement/admin/about-unified-interface) <br />
[Mitä PowerAppsin mallipohjaiset sovellukset ovat?](model-driven-app-overview.md) <br />
[Sovellusten päivittäminen Unified Interfaceen](/dynamics365/customer-engagement/admin/update-apps-to-unified-interface) <br />
[Mallipohjaisen sovelluksen vuorovaikutteisen kokemuksen koontinäyttöjen määrittäminen](configure-interactive-experience-dashboards.md) <br />
[Mallipohjaisen sovelluksen tietojen visualisointien mukautettujen ohjausobjektien käyttäminen](use-custom-controls-data-visualizations.md) <br />
[PowerApps component framework -yleiskatsaus](/powerapps/developer/component-framework/overview) <br />
[Unified Interface jokaiselle](/power-platform-release-plan/2019wave2/microsoft-powerapps/unified-interface-app-everybody)
