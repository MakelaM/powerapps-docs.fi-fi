---
title: Tietojen integrointi Common Data Service for Appsiin
description: Tietojen integrointi useista lähteistä Common Data Service for Appsiin
author: sabinn-msft
ms.service: powerapps
ms.topic: how-to
ms.component: cds
ms.date: 09/19/2018
ms.author: sabinn
search.audienceType:
- admin
search.app:
- D365CE
- PowerApps
- Powerplatform
ms.openlocfilehash: b8cebc6f9db8a1a7c1a060aad461f4f32fcee05b
ms.sourcegitcommit: 2bcf40aeaa35420dc43f5803f4e57ff0f6afb57b
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 09/19/2018
ms.locfileid: "46469351"
---
# <a name="integrate-data-into-common-data-service-for-apps"></a>Tietojen integrointi Common Data Service for Appsiin

<!--note from editor: the style guide says not to use "the" in front of Common Data Service for Apps, so I'm removing that.-->

Tietojen integrointi (järjestelmänvalvojille) on pisteestä toiseen -integrointipalvelu, jonka avulla tietoja integroidaan Common Data Service for Appsiin. Se tukee tietojen integrointia useista lähteistä – esimerkiksi Dynamics 365 for Finance and Operationsista, Dynamics 365 for Sales and SalesForcesta (esikatselu), SQL:stä (esikatselu) – Common Data Service for Appsiin. Se tukee tietojen integrointia myös Dynamics 365 for Finance and Operationsiin ja Dynamics 365 for Salesiin. Tämä palvelu on ollut yleisesti saatavilla heinäkuusta 2017 lähtien.  

Aloitimme ensimmäisen osapuolen sovelluksista, kuten Dynamics 365 for Finance and Operationsista ja Dynamics 365 for Salesista. Power Query- tai M-pohjaisten liittimien avulla tuemme nyt myös muita lähteitä, kuten SalesForcea (esikatselu) ja SQL:ää (esikatselu). Palvelu laajennetaan yli 20 lähteeseen lähitulevaisuudessa. 

> [!div class="mx-imgBorder"]
> ![Tietolähde kohteeseen](media/data-integrator/DataIntegratorP2P-new.PNG "Tietolähde kohteeseen")

## <a name="how-can-you-use-the-data-integrator-for-your-business"></a>Miten tietojen integrointia voi käyttää yrityksessä?

Tietojen integrointi (järjestelmänvalvojille) tukee myös prosessiin perustuvia integrointiskenaarioita. Tällainen on esimerkiksi Prospect to Cash, joka tarjoaa suoran synkronoinnin Dynamics 365 for Finance and Operationsin ja Dynamics 365 for Salesin välillä. Tietojen integrointiominaisuudessa käytettävissä olevat Prospect to Cash -mallit mahdollistavat tilien, yhteystietojen, tuotteiden, myyntitarjousten, myyntitilausten ja myyntilaskujen tietovuon Finance and Operations- ja Sales-osien välillä. Kun tiedot kulkevat Finance and Operations- ja Sales-osien välillä, voit käyttää myynti- ja markkinointitoimintoja Sales-osassa sekä käsitellä tilausten toteutusta varastonhallinnassa Finance and Operations -osassa. 

> [!div class="mx-imgBorder"]
> ![Prospect to Cash](media/data-integrator/ProspectToCash631.png "Prospect to Cash")

Prospect to Cash -integroinnin avulla myyjät voivat käsitellä ja seurata myyntiprosesseja Dynamics 365 for Salesin vahvuuksilla. Samalla kaikki toteutuksen ja laskutuksen osa-alueet ovat tehokkaasti käytettävissä Finance and Operations -osassa. Microsoft Dynamics 365 Prospect to Cash -integroinnin avulla voit hyödyntää kummankin järjestelmän ominaisuuksia tehokkaasti. 

Katso video: [Prospect to Cash -integrointi](https://www.youtube.com/watch?v=AVV9x5x-XCg)

Lisätietoja Prospect to Cash -integroinnista on [Prospect to Cash -ratkaisun](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/prospect-to-cash) ohjeissa.

Tuemme myös [Field Service -integrointia](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order) ja [PSA (Project Service Automation) -integrointia](https://docs.microsoft.com/dynamics365/unified-operations/financials/project-management/psa-integration?toc=/fin-and-ops/toc.json) Dynamics 365 for Finance and Operationsiin.

## <a name="data-integrator-platform"></a>Tietojen integroinnin ympäristö

Tietojen integrointi (järjestelmänvalvojille) koostuu tietojen integroinnin ympäristöstä, sovellusryhmien tarjoamista valmiista malleista (esimerkiksi Dynamics 365 for Finance and Operations ja Dynamics 365 for Sales) sekä asiakkaiden ja kumppaneiden luomista mukautetuista malleista. Olemme luoneet sovellusagnostisen ympäristön, jonka voi skaalata eri lähteisiin. Sen ytimessä luodaan yhteydet (integroinnin päätepisteisiin), luodaan mukautettu malli valmiilla yhdistämismäärityksillä (joita voi mukauttaa lisää) sekä luodaan ja suoritetaan tietojen integrointiprojekti.  

Integrointimallit toimivat suunnitelmana, ja ne sisältävät valmiit entiteetit ja kenttien yhdistämismääritykset, joiden avulla tiedot kulkevat lähteestä kohteeseen. Se tarjoaa myös mahdollisuuden muuntaa tietoja ennen niiden tuomista. Usein rakenne lähde- ja kohdesovellusten välillä voi olla hyvinkin erilainen. Valmiiksi määritetyt entiteetit ja yhdistämismääritykset sisältävä malli on hyvä lähtökohta integrointiprojektissa.  

> [!div class="mx-imgBorder"]
> ![Tietojen integroinnin ympäristö](media/data-integrator/DIPlatform.PNG "Tietojen integroinnin ympäristö")

## <a name="how-to-set-up-a-data-integration-project"></a>Tietojen integrointiprojektin määrittäminen

Ensisijaisia vaiheita on kolme:

1. Luo yhteys (anna tunnistetiedot yhteyden tietolähteisiin).

2. Luo yhteysjoukko (yksilöi ympäristöt yhteyksille, jotka loit edellisessä vaiheessa).

3. Luo mallista tietojen integrointiprojekti (luo yhdistämismääritykset vähintään yhdelle entiteetille tai käytä valmiita yhdistämismäärityksiä).

Kun olet luonut integrointiprojektin, voit suorittaa projektin manuaalisesti ja määrittää myös aikataulupohjaisen päivityksen jatkoa varten. Tämän artikkelin loppuosassa näitä kolmea vaihetta käsitellään tarkemmin.

### <a name="how-to-create-a-connection"></a>Yhteyden luominen

Ennen tietojen integrointiprojektin luomista sinun on valmisteltava yhteys jokaiseen järjestelmään, jota aiot käyttää Microsoft PowerApps -portaalissa. Nämä yhteydet on eräänlaisia integraatiopisteitä.

**Yhteyden luominen**

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Valitse Tiedot-kohdasta **Yhteydet** ja valitse sitten **Uusi yhteys**.

3. Voit valita yhteyden yhteysluettelosta yhteyttä tai hakea yhteyttä.

    > [!div class="mx-imgBorder"] 
    > ![Luo yhteys](media/data-integrator/CreateConnection780.png "Luo yhteys")

4. Kun olet valinnut yhteyden, valitse **Luo**. Sen jälkeen sinulta pyydetään tunnistetiedot.

5. Kun olet antanut tunnistetietosi, yhteys luetellaan omissa yhteyksissäsi.

    > [!div class="mx-imgBorder"] 
    > ![Yhteysluettelo](media/data-integrator/CreateConnection1780.png "Yhteysluettelo")

### <a name="how-to-create-a-connection-set"></a>Yhteysjoukon luominen

Yhteysjoukko on kokoelma, jossa on kaksi yhteyttä, yhteyksien ympäristöt, organisaation yhdistämismääritysten tiedot ja integrointiavaimet, joita kaikkia voidaan käyttää uudelleen projekteissa. Voit aloittaa yhteysjoukon käyttämisen kehittämisessä ja siirtyä toiseen tuotannossa. Yhteysjoukkoon tallennettu keskeinen tieto on organisaatioyksikön yhdistämismääritys – esimerkiksi yhdistämismääritykset juridisen Finance and Operations -yksikön (tai yrityksen) ja Dynamics 365 for Sales -organisaation tai -liiketoimintayksiköiden välillä. Voit tallentaa yhteysjoukkoon useita organisaation yhdistämismäärityksiä.

**Yhteysjoukon luominen**

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Valitse **Tietojen integroinnin** -välilehti vasemmassa siirtymisruudussa.

3. Valitse **Yhteysjoukot**-välilehti ja valitse **Uusi yhteysjoukko**.

4. Anna yhteysjoukollesi nimi.
  
    > [!div class="mx-imgBorder"] 
    > ![Luo yhteysjoukko](media/data-integrator/CreateConnectionSet1780.png "Luo yhteysjoukko")
  
5. Valitse aiemmin luomasi yhteydet ja valitse haluamasi ympäristö.

6. Toista vaiheet valitsemalla seuraava yhteytesi (nämä ovat ikään kuin lähde ja kohde ilman määritettyä järjestystä).

7. Määritä yhdistämismääritykset organisaation ja liiketoimintayksikön välillä (jos olet integroimassa tietoja Finance and Operations- ja Sales-järjestelmien välillä).
  
    > [!NOTE]
    > Voit määrittää kullekin yhteysjoukolle useita yhdistämismäärityksiä.
  
8. Kun olet täyttänyt kaikki kentät, valitse **Luo**.

9. Näet luomasi uuden yhteysjoukon Yhteysjoukot-luettelosivulla.
    
    > [!div class="mx-imgBorder"] 
    > ![Yhteysjoukkoluettelo](media/data-integrator/CreateConnectionSet2780.png "Yhteysjoukkoluettelo")

Yhteysjoukkosi on valmis käytettäväksi integrointiprojekteissa.

### <a name="how-to-create-a-data-integration-project"></a>Tietojen integrointiprojektin luominen

Projektit mahdollistavat tietovuon järjestelmien välillä. Projektin sisältää vähintään yhden entiteetin yhdistämismääritykset. Yhdistämismääritykset ilmaisevat, mikä kenttä vastaa mitäkin.

**Tietojen integrointiprojektin luominen**

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Valitse **Tietojen integroinnin** -välilehti vasemmassa siirtymisruudussa.

3. Valitse **Projektit**-välilehden oikeassa yläkulmassa **Uusi projekti**.

    > [!div class="mx-imgBorder"] 
    > ![Luo projekti](media/data-integrator/CreateNewProject780.png "Luo projekti")

4. Anna integrointiprojektille nimi.

5. Valitse jokin käytettävissä olevista malleista (tai [luo oma malli](#how-to-customize-or-create-your-own-template)). Tässä tapauksessa Tuotteet-entiteetti siirretään Finance and Operations -osasta Sales-osaan.

    > [!div class="mx-imgBorder"] 
    > ![Luo uusi projekti valitsemalla malli](media/data-integrator/CreateNewProjectSelectTemplate780.png "Luo uusi projekti valitsemalla malli")

6. Valitse **seuraava** ja valitse aiemmin luomasi yhteysjoukko (tai [luo uusi yhteysjoukko](#how-to-create-a-connection-set)).

7. Varmista yhteyden ja ympäristön nimistä, että olet valinnut oikean vaihtoehdon.

    > [!div class="mx-imgBorder"] 
    > ![Luo uusi yhteysjoukko](media/data-integrator/CreateNewProjectSelectConnectionSet780.png "Luo uusi yhteysjoukko")

8. Valitse **Seuraava** ja valitse sitten juridinen entiteetti liiketoimintayksikön yhdistämismäärityksiä varten.

    > [!div class="mx-imgBorder"] 
    > ![Luo uusi juridisen entiteetin yhdistämismääritys](media/data-integrator/CreateNewProjectLegalEntityMapping780.png "Luo uusi juridisen entiteetin yhdistämismääritys")

9. Tarkista ja hyväksy tietosuojahuomautus ja suostuminen seuraavassa näytössä.

10. Jatka projektin luomista ja suorita sitten projekti, mikä puolestaan suorittaa projektin työnkulun.

    > [!div class="mx-imgBorder"] 
    > ![Suorita projekti](media/data-integrator/RunProject780.png "Suorita projekti")

    Tässä näytössä on useita välilehtiä – **Aikataulutus** ja **Suoritushistoria** – sekä painikkeita – **Lisää tehtävä**, **Päivitä entiteetit** ja **Kyselyn lisäasetukset**. Niitä käsitellään tarkemmin jäljempänä tässä artikkelissa.

### <a name="execution-history"></a>Suoritushistoria

<!--note from editor: Do you think most people reading this will know what "upsert" means?-->

Suoritushistoriassa näkyvät kaikki projektisuoritukset projektin nimellä, projektin suorituksen aikaleima ja suorituksen tila sekä päivityslisäysten ja/tai virheiden määrä.

-   Esimerkki projektin suoritushistoriasta

    > [!div class="mx-imgBorder"] 
    > ![Projektin suoritushistoria](media/data-integrator/ExecutionHistorySuccessFailures4780.png "projektin suoritushistoria")

-   Esimerkki onnistuneesta suorituksesta, jossa tilana on valmis ja päivityslisäyksiä on \# (Päivityslisäys on logiikka, jossa tietue päivitetään, jos se on jo olemassa, tai uusi tietue lisätään.)

    > [!div class="mx-imgBorder"] 
    > ![Suorituksen onnistuminen](media/data-integrator/ExecutionHistorySuccess2780.png "Suorituksen onnistuminen")

-   Suorittamisvirheissä voit porautua alaspäin, jotta näet virheen pääsyyn.

    Tässä on esimerkki virheestä, jossa projektissa on vahvistusvirheitä. Tässä tapauksessa projektin vahvistusvirhe johtuu entiteetin yhdistämismäärityksissä puuttuvista lähdekentistä.

    > [!div class="mx-imgBorder"] 
    > ![Suoritushistorian virhe](media/data-integrator/ExecutionHistoryFailures3780.png "Suoritushistorian virhe")

-   Jos projektin suoritus on VIRHE-tilassa, suoritusta yritetään uudelleen seuraavana ajoitettuna suorituskertana.

-   Jos projektin suoritus on VAROITUS-tilassa, ongelmat on korjattava lähteessä. Suoritusta yritetään uudelleen seuraavana ajoitettuna suorituskertana.

    Kummassakin tapauksessa voit myös suorittaa projektin suorittamisen uudelleen manuaalisesti.

### <a name="how-to-set-up-a-schedule-based-refresh"></a>Aikatauluun perustuvan päivityksen määrittäminen

Tuemme nykyisin kahta suoritusten/kirjoitusten tyyppiä:

-   Manuaaliset kirjoitukset (projektin suoritus ja päivitys manuaalisesti)

-   Aikatauluun perustuvat kirjoitukset (automaattinen päivitys)

Kun olet luonut integrointiprojektin, voit suorittaa sen manuaalisesti tai määrittää aikatauluun perustuvat kirjoitukset, jonka avulla voit määrittää projekteillesi automaattisen päivityksen.

**Aikatauluun perustuvien kirjoitusten määrittäminen**

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Voit ajoittaa projekteja kahdella eri tavalla.<br>

    Valitse projekti ja **Aikataulutus**-välilehti tai käynnistä aikataulutustoiminto projektiluettelosivulta napsauttamalla kolmea pistettä projektin nimen vieressä.

    > [!div class="mx-imgBorder"] 
    > ![Aikatauluun perustuvat kirjoitukset](media/data-integrator/Schedulebasedwrites780.png "Aikatauluun perustuvat kirjoitukset")

3. Valitse **Toistuu joka**. Kun olet täyttänyt kaikki kentät, valitse **Tallenna aikataulu**.

    > [!div class="mx-imgBorder"] 
    > ![Aikatauluun perustuvat kirjoitukset](media/data-integrator/Schedulebasedwrites1780.png "Aikatauluun perustuvat kirjoitukset")

Voit määrittää tiheydeksi lyhimmillään 1 minuuttiin. Voit määrittää kirjoituksen toistumaan tietyn tunti-, päivä-, viikko- tai kuukausimäärän välein. Huomaa, että seuraava päivitys ei käynnisty, ennen kuin edellisen projektitehtävän suorittaminen on valmis.

Huomaa myös, että Ilmoitukset-kohdassa voit halutessasi asettaa sähköpostipohjaiset ilmoitukset. Niissä ilmoitetaan työn suorituksista valmiina varoitusten kera ja/tai epäonnistuneina virheiden takia. Voit antaa useita vastaanottajia, myös ryhmiä pilkuilla eroteltuina.

> [!div class="mx-imgBorder"] 
> ![Sähköposti-ilmoitus](media/data-integrator/EmailNotification780.png "Sähköposti-ilmoitus")

## <a name="customizing-projects-templates-and-mappings"></a>Projektien, mallien ja yhdistämismääritysten mukauttaminen 

Käytä mallia tietojen integrointiprojektin luomiseen. Mallissa määritetään tietojen kulku, joten yrityskäyttäjän tai järjestelmänvalvojan on helpompi integroida tiedot lähteestä kohteeseen ja pienentää kokonaisvaivaa ja kustannuksia. Yrityskäyttäjä tai järjestelmänvalvoja voi aloittaa Microsoftin tai sen kumppaneiden julkaisemasta valmiista mallista ja mukauttaa sitä ennen projektin luomista. Sen jälkeen projektin voi tallentaa mallina ja jakaa organisaatiolle ja/tai luoda uutena projektina. 

Malli sisältää lähteen, kohteen ja tietovuon suunnan. Tämä on pidettävä mielessä omaa mallia mukautettaessa ja/tai luotaessa.  

Voit mukauttaa projekteja ja malleja seuraavilla tavoilla:

-   Mukauta kenttien yhdistämismäärityksiä.

-   Mukauta mallia lisäämällä haluamasi entiteetti.

### <a name="how-to-customize-field-mappings"></a>Kenttien yhdistämismääritysten mukauttaminen

**Yhteysjoukon luominen**

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Valitse projekti, jonka kenttien yhdistämismäärityksiä haluat mukauttaa. Valitse sitten lähde- ja kohdekenttien välinen nuoli.

    > [!div class="mx-imgBorder"] 
    > ![Kentän yhdistämismääritys](media/data-integrator/FieldMapping780.png "Kentän yhdistämismääritys")

3. Tästä pääset yhdistämismääritysnäyttöön, jossa voit lisätä uuden yhdistämismäärityksen valitsemalla **Lisää yhdistämismääritys** oikeassa yläkulmassa tai **Mukauttaa aiemmin luotuja yhdistämismäärityksiä** avattavasta luettelosta.

    > [!div class="mx-imgBorder"] 
    > ![Kentän yhdistämismääritysten mukauttaminen](media/data-integrator/FieldMappingCustomize780.png "Kentän yhdistämismääritysten mukauttaminen")

4. Kun olet mukauttanut kenttien yhdistämismäärityksiä, valitse **Tallenna**.

### <a name="how-to-customize-or-create-your-own-template"></a>Oman mallin mukauttaminen tai luominen 

**Oman mallin luominen**

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Määritä uudelle mallille lähde ja kohde sekä tietovuon suunta.

3. Luo projekti valitsemalla aiemmin luotu malli, joka vastaa valitsemaasi lähdettä ja kohdetta sekä tietovuon suuntaa.

<!--note from editor: Didn't we create the project in step 3? Step 4 tells us to create the project.-->

4. Luo projekti, kun olet valinnut sopivan yhteyden.

5. Ennen kuin tallennat ja/tai suoritat projektin, valitse oikeassa yläkulmassa **Lisää tehtävä**.

    > [!div class="mx-imgBorder"] 
    > ![Mukauta mallia](media/data-integrator/CustomizeTemplate780.png "Mukauta mallia")

    Tämä tuo näkyviin **Lisää tehtävä** -valintaikkunan.

6. Anna tehtävälle merkityksellinen nimi ja lisää haluamasi lähde- ja kohde-entiteetit.

    > [!div class="mx-imgBorder"] 
    > ![Mukauta mallia lisäämällä tehtävä](media/data-integrator/CustomizeTemplateAddtask75.png "Mukauta mallia lisäämällä tehtävä")

7. Avattavassa luettelossa näytetään kaikki lähde- ja kohde-entiteetit.

    > [!div class="mx-imgBorder"] 
    > ![Mukauta mallia lisäämällä tehtävä](media/data-integrator/CustomizeTemplateAddtask175.png "Mukauta mallia lisäämällä tehtävä")

    Tässä tapauksessa uusi tehtävä luotiin Käyttäjä-entiteetin synkronoimiseksi SalesForcesta Common Data Service for Appsin Käyttäjät-entiteettiin.

    > [!div class="mx-imgBorder"] 
    > ![Mukauta mallia lisäämällä tehtävä](media/data-integrator/CustomizeTemplateAddtask275.png "Mukauta mallia lisäämällä tehtävä")

8. Kun tehtävä on luotu, näet uuden tehtävän luettelossa ja voit poistaa alkuperäisen tehtävän.

    > [!div class="mx-imgBorder"] 
    > ![Mukauta mallia lisäämällä tehtävä](media/data-integrator/CustomizeTemplateAddtask3780.png "Mukauta mallia lisäämällä tehtävä")

9. Loit juuri uuden mallin – tässä tapauksessa mallin, joka vie Käyttäjä-entiteetin tiedot SalesForcesta Common Data Serviceen. Tallenna mukautuksesi valitsemalla **Tallenna**.

10. Voit mukauttaa kenttien yhdistämismäärityksiä uudessa mallissa noudattamalla ohjeita. Voi suorittaa tämän projektin ja/tai tallentaa projektin mallina **Projektiluettelo**-sivulla.

    > [!div class="mx-imgBorder"] 
    > ![Mukauta mallia tallentamalla nimellä malliksi](media/data-integrator/CustomizeTemplateSaveAsTemplate780.png "Mukauta mallia tallentamalla nimellä malliksi")

11. Anna nimi ja kuvaus ja/tai jaa muiden kanssa organisaatiossasi.

    > [!div class="mx-imgBorder"] 
    > ![Mukauta mallia tallentamalla nimellä malliksi](media/data-integrator/CustomizeTemplateSaveAsTemplate175.png "Mukauta mallia tallentamalla nimellä malliksi")

## <a name="advanced-data-transformation-and-filtering"></a>Kehittynyt tietojen muuntaminen ja suodattaminen 

Power Query -tuen ansiosta tarjoamme nyt lähdetietojen lisäsuodatuksen ja tietojen muuntamisen. Power Queryn avulla käyttäjät voivat muotoilla tiedot omien tarpeidensa mukaisiksi yksinkertaisen, innostavan ja koodittoman käyttökokemuksen myötä. Voit ottaa tämän käyttöön projektikohtaisesti. 

### <a name="how-to-enable-advanced-query-and-filtering"></a>Kehittyneen kyselyn ja suodatuksen ottaminen käyttöön

**Lisäsuodatuksen ja tietojen muuntamisen määrittäminen**

1. Siirry [PowerApps-hallintakeskukseen](https://admin.powerapps.com).

2. Valitse projektin, jossa haluat ottaa kehittyneen kyselyn käyttöön. Valitse sitten **Kehittynyt kysely**.

    > [!div class="mx-imgBorder"] 
    > ![Valitse kehittynyt kysely](media/data-integrator/EnablePQ1780.png "Valitse kehittynyt kysely")

3. Näkyviin tulee varoitus siitä, että kehittynyt kysely on yksisuuntainen toiminto, eikä sitä voi kumota. Jatka valitsemalla **OK**. Valitse sitten lähteen ja kohteen yhdistämismääritysnuoli.

    > [!div class="mx-imgBorder"] 
    > ![Varoitus](media/data-integrator/EnablePQ275.png "Varoitus")

4. Sinulle esitetään nyt tuttu entiteetin yhdistämismäärityksen sivu, jossa on linkki kehittyneen kyselyn ja suodatuksen käynnistämiseen.

    > [!div class="mx-imgBorder"] 
    > ![Kehittynyt kysely ja suodatus](media/data-integrator/EnablePQ3780.png "Kehittynyt kysely ja suodatus")

5. Valitse **linkki** kehittyneen kyselyn ja suodatuksen käyttöliittymän käynnistämiseksi. Sen kautta näet lähdekenttätiedot Microsoft Excel -tyyppisinä sarakkeissa.

    > [!div class="mx-imgBorder"] 
    > ![Kehittynyt kysely ja suodatus](media/data-integrator/EnablePQ4780.png "Kehittynyt kysely ja suodatus")

6. Yläreunan valikossa on useita vaihtoehtoja tietojen muuntamiseen, kuten **Lisää ehdollinen sarake**, **Tee sarakkeesta kaksoiskappale** ja **Pura**.

    > [!div class="mx-imgBorder"] 
    > ![Lisää sarake](media/data-integrator/EnablePQAddColumn75.png "Lisää sarake")

7. Voit myös napsauttaa mitä tahansa saraketta hiiren kakkospainikkeella, jotta saat näkyviin lisää vaihtoehtoja, kuten **Poista sarakkeet**, **Poista kaksoiskappaleet** ja **Jaa sarake osiin**.

    > [!div class="mx-imgBorder"] 
    > ![Napsauta saraketta hiiren kakkospainikkeella](media/data-integrator/EnablePQAddColumn180.png "Napsauta saraketta hiiren kakkospainikkeella")

8. Voit myös suodattaa napsauttamalla saraketta. Käytä sen jälkeen Excel-tyyppisiä suodattimia.

    > [!div class="mx-imgBorder"] 
    > ![Ota suodatus käyttöön](media/data-integrator/EnablePQFiltering80.png "Ota suodatus käyttöön")

<!--note from editor: I don't see an "otherwise" in the screenshot. I see "else".-->

9. Oletusarvon muunnokset voidaan tehdä käyttämällä ehdollista saraketta. Voit tehdä tämän valitsemalla avattavasta **Lisää sarake** -luettelosta **Lisää ehdollinen sarake**. Anna sitten uudelle sarakkeelle nimi. Täytä sekä **Sitten**- että **Muuten**-kohtiin haluamasi oletusarvo minkä tahansa kentän ja **Jos**- ja **Yhtä suuri kuin** -arvojen avulla.

    > [!div class="mx-imgBorder"] 
    > ![Lisää ehdollinen sarake](media/data-integrator/EnablePQDefaultValueTransforms2780.png "Lisää ehdollinen sarake")

10. Huomioi **jokainen** lauseke *fx* editorin yläosassa.

    > [!div class="mx-imgBorder"] 
    > ![fx editori](media/data-integrator/EnablePQDefaultValueTransforms2780.png "fx editori")

11. Korjaa **jokainen** lauseke *fx* editorissa ja valitse **OK**.

    > [!div class="mx-imgBorder"] 
    > ![Korjaa jokainen lauseke](media/data-integrator/EnablePQDefaultValueTransforms5780.png "Korjaa jokainen lauseke")

<!--note from editor: The sentence that starts with "Additionally" is confusing - not sure where the "same steps" fit in.-->

12. Aina, kun teet muutoksen, suoritat vaiheen. Näet käytetyt vaiheet oikeanpuoleisessa ruudussa (vieritä luettelon loppuun nähdäksesi uusimman vaiheen). Voit kumota vaiheen, jos sitä on muokattava. Voit vaihtoehtoisesti siirtyä laajennettuun editorin napsauttamalla **QrySourceData**-kohtaa hiiren kakkospainikkeella vasemmassa ruudussa yläreunassa, jotta saat taustalla suoritettavan M-kielen ja samat vaiheet näkyviin.

    > [!div class="mx-imgBorder"] 
    > ![Laajennettu editori](media/data-integrator/EnablePQDefaultValueTransforms4780.png "Laajennettu editori")

13. Sulje kehittyneen kyselyn ja suodatuksen käyttöliittymä valitsemalla **OK**. Valitse sitten yhdistämismäärityksen tehtäväsivulla uusi luotu sarake lähteeksi, jotta yhdistämismääritys luodaan vastaavasti.

    > [!div class="mx-imgBorder"] 
    > ![Valitse uusi sarake](media/data-integrator/EnablePQDefaultValueTransforms6780.png "Valitse uusi sarake")

Lisätietoja Power Querystä on [Power Queryn ohjeissa](https://docs.microsoft.com/power-query/).
