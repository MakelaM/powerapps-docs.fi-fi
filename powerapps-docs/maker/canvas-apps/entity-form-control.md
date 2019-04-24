---
title: Käytä entiteettilomake-ohjausobjektia | Microsoft Docs
description: Luo sovelluksia nopeammin käyttämällä Entiteettilomake-ohjausobjektia monipuolisten lomakkeiden lisäämiseksi Common Data Service -entiteetille.
author: aneesmsft
manager: kvivek
ms.service: powerapps
ms.topic: conceptual
ms.custom: canvas
ms.reviewer: anneta
ms.date: 03/11/2017
ms.author: aneesa
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: ee8573cb9ae4df5ac42deefad4ac67aede3a3502
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61547641"
---
# <a name="use-the-entity-form-control"></a>Entiteettilomake-ohjausobjektin käyttäminen
Luo sovelluksia nopeammin käyttämällä **Entiteettilomake**-ohjausobjektia monipuolisten lomakkeiden lisäämiseksi Common Data Service -entiteetille.

Johdanto **entiteettilomake** ohjausobjekti, tästä blogikirjoituksesta: [Uusi entiteettilomakkeen ohjausobjekti (kokeellinen ominaisuus) Common Data Service-](https://powerapps.microsoft.com/blog/new-entity-form-control-experimental-feature-for-common-data-service/).

> [!IMPORTANT]
> Ota huomioon blogikirjoituksessa mainittu **Entiteettilomake**-ohjausobjektin kokeellisuus ja ole varovainen, jos käytät **entiteettilomake**-ohjausobjektia käyttöä tuotantosovelluksissa ainakin toistaiseksi.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet
Tässä ovat **Entiteettilomake**-ohjausobjektin tärkeimmät ominaisuudet.

**DataSource** – Tätä käytetään määrittämään tietolähde, joka sisältää tietueet, jotka haluat näyttää.   
> [!NOTE]
> Tällä hetkellä vain Common Data Service -entiteettejä tuetaan tietolähteinä **Entiteettilomake**-ohjausobjektille.  

**Pattern** – Määrittää tyylin lomakkeelle, jonka haluat näyttää **Entiteettilomake**-ohjausobjektissa. Määritä tämä ominaisuus käyttämällä **FormPattern**-luettelointia.

* **FormPattern.List** – Näyttää taulukkomuotoisen luettelon tietueista.
* **FormPattern.CardList** – Näyttää korttiluettelon tietueista.
* **FormPattern.Details** – Näyttää lomakkeen, jolla voidaan tarkastella tai muokata yksittäisen tietueen tietoja.
* **FormPattern.None** – Tyyliä ei ole määritetty eksplisiittisesti. Oletusarvo on **List** tablettisovelluksille ja **CardList** puhelinsovelluksille.

**Item** – Määrittää tietolähteen tietueen, jonka **Entiteettilomake**-ohjausobjektin tulisi näyttää. Tätä ominaisuutta käytetään vain, kun **Pattern**in arvoksi on määritetty **FormPattern.Details**.

**Selected** – Hakee tällä hetkellä valittuna olevan tietueen.  
Esimerkki: Jos **entiteettilomake** ohjausobjekti näyttää myyntitilaustietueiden, luettelo **valittu** ominaisuus antaa tällä hetkellä valitun tietueen. Voit myös käyttää tietueen kenttää. (Määritä esimerkiksi valitun tietueen **Account**-kentän arvoksi **Selected.Account**.)

**SelectableFields** – Määrittää, mitkä kentät tulee näyttää linkkeinä. Aseta tämän ominaisuuden arvo tällä syntaksilla:  
**{Field1Name : true, Field2Name : true}**  
Esimerkki: Jos haluat **SalesOrderId** ja **tilin** kentät näkyvät linkkeinä lomakkeessa, aseta **SelectableFields** ominaisuuden kyseisen lomakkeen tämä arvo:  
**{SalesOrderId : true, Account : true}**

**SelectedField** – Määrittää, mitä kenttää on napsautettu tai napautettu. Tämä pätee vain kenttiin, joille on määritetty **SelectableFields**-ominaisuus.  
Esimerkki: Jos määrität **SelectableFields** ominaisuudeksi **{SalesOrderId: true, Account: true}** ja käyttäjä napsauttaa tai napauttaa **tilin** kentän  **SelectedField.Account** asetetaan tosi.

**OnFieldSelect** – Kuinka sovellus reagoi, kun käyttäjä napsauttaa tai napauttaa kenttää. Tämä pätee vain kenttiin, joille on määritetty **SelectableFields**-ominaisuus.

**Mode** – Määrittää lomakkeen tilan. Voit muuttaa tilaa käyttämällä funktiota **ViewForm**, **EditForm** tai **NewForm**. Nämä funktiot toimivat vain, kun **Pattern**-ominaisuudeksi on asetettu **FormPattern.Details**. Määritä **Mode**-ominaisuuden arvoksi **FormMode**-luetteloinnin arvo.

* **FormMode.View** – Käyttäjät voivat tarkastella, mutta eivät muokata tai lisätä tietuetta.
* **FormMode.Edit** – Käyttäjät voivat muokata tietuetta.
* **FormMode.New** – Käyttäjät voivat lisätä tietueen.

**OnSuccess** – Kuinka sovellus vastaa, kun tietotoiminto onnistuu.

**OnFailure** - kuinka sovellus vastaa, kun tietotoiminto epäonnistuu.

**Unsaved** – Määrittää, onko käyttäjän muokkaamassa tietueessa tallentamattomia muutoksia.

## <a name="related-functions"></a>Liittyvät funktiot
Voit käyttää näitä jaettuja funktioita joko **Entiteettilomake**-ohjausobjektin tai [Muokkaa lomaketta -ohjausobjektin](functions/function-form.md) kanssa. Nämä funktiot toimivat **Entiteettilomake**-ohjausobjektin kanssa vain, kun sen **Pattern**-ominaisuudeksi on asetettu **FormPattern.Details**.

**ViewForm** – Asettaa **Entiteettilomake**-ohjausobjektin **Mode**-ominaisuudeksi **FormMode.View**.

**EditForm** – Asettaa **Entiteettilomake**-ohjausobjektin **Mode**-ominaisuudeksi **FormMode.Edit**.

**NewForm** – Asettaa **Entiteettilomake**-ohjausobjektin **Mode**-ominaisuudeksi **FormMode.New**.

**SubmitForm** – Tallentaa muutokset, kun käyttäjä muokkaa **Entiteettilomake**-ohjausobjektin sisäistä tietuetta.

**ResetForm** – Hylkää käyttäjän tekemät tallentamattomat muutokset **Entiteettilomake**-ohjausobjektin tietueeseen.

Nyt kun olet saanut yleiskatsauksen eri ominaisuuksiin ja funktioihin, katsotaan, miten ne toimivat.

> [!NOTE]
> Jo sinulla ei ole käytettävissäsi Common Data Service -tietokantaa, luo sellainen ennen seuraavia vaiheita.

## <a name="display-a-list-of-records"></a>Tietueluettelon näyttäminen
Seuraavassa viidessä kohdassa suoritetaan alusta loppuun yksi **Entiteettilomake**-ohjausobjektien käyttöesimerkki. Tässä toimenpiteessä lisätään lomake, jossa näytetään luettelo myyntitilauksista.  

1. Luo tyhjä tablettisovellus.
   
    ![](media/entity-form-control/entityform-tutorial-01-01.png)
2. Anna ensimmäiselle näytölle nimi **SalesOrderListScreen**.
   
    ![](media/entity-form-control/entityform-tutorial-01-02.png)
3. Napsauta tai napauta **Lisää**-välilehdellä kohtaa **Lomakkeet** ja napsauta tai napauta kohtaa **Entiteettilomake (kokeellinen)**.  
   
    Näyttöön lisätään **Entiteettilomake**-ohjausobjekti.  
   
    ![](media/entity-form-control/entityform-tutorial-01-03.png)
4. Anna **Entiteettilomake**-ohjausobjektille uusi nimi **SalesOrderListForm** ja muuta sen kokoa niin, että se kattaa koko näytön.
5. Napsauta tai napauta oikeanpuoleisen ruudun tietokantakuvaketta, joka on tekstin **Tietolähdettä ei ole valittu** vieressä, ja napsauta tai napauta kohtaa **Lisää tietolähde**.  
   
    ![](media/entity-form-control/entityform-tutorial-01-04.png)
6. Napsauta tai napauta yhteysluettelosta tietokantasi yhteyttä.  
   
    ![](media/entity-form-control/entityform-tutorial-01-05.png)
7. Napsauta tai napauta entiteettiluettelosta **Myyntitilaus** ja napsauta tai napauta **Yhdistä**.  
   
    **Myyntitilaus**-entiteetin tietolähde luodaan ja **SalesOrderListForm**-kohteen **DataSource**-ominaisuudeksi asetetaan kyseinen tietolähde.
   
    ![](media/entity-form-control/entityform-tutorial-01-06.png)  
   
    **Entiteettilomake**-ohjausobjekti näyttää luettelon myyntitilauksista. Käyttämällä **Entiteettilomake**-ohjausobjektia voit tehdä nopeasti luettelolomakkeen ilman, että sitä tarvitsee rakentaa manuaalisesti.
   
    ![](media/entity-form-control/entityform-tutorial-01-07.png)  
   
    Et asettanut esimerkissä **Entiteettilomake**-ohjausobjektin **Pattern**-ominaisuutta, joten sille käytetään oletusarvoa **List**. Lisäksi **Myyntitilaus**-entiteetin **DefaultList**-kenttäryhmää käytetään luettelolomakkeen näyttämiseksi. Lomake on lisäksi dynaaminen ja kenttäryhmän muutokset näkyvät siinä automaattisesti.


## <a name="display-the-details-of-a-record"></a>Tietueen tietojen näyttäminen
Lisätään toinen **Entiteettilomake**-ohjausobjekti, joka näyttää aikaisemmin luodussa luettelossa valitun myyntitilauksen tiedot.  

1. Muuta kohteen **SalesOrderListForm** kokoa niin, että se kattaa puolet näytöstä, ja lisää toinen **Entiteettilomake**-ohjausobjekti, joka kattaa näytön toisen puoliskon.  
   <br>![](media/entity-form-control/entityform-tutorial-01-09.png)
2. Anna toiselle **Entiteettilomake**-ohjausobjektille nimi **SalesOrderDetailsForm** ja yhdistä se **Myyntitilaus**-tietolähteeseen, jonka loit aiemmin.  
   <br>![](media/entity-form-control/entityform-tutorial-01-10.png)
3. Määritä **SalesOrderDetailsForm**-kohteen **Pattern**-ominaisuudeksi **FormPattern.Details**.  
   
    **SalesOrderDetailsForm** käyttää **Myyntitilaus**-entiteetin **DefaultDetails**-kenttäryhmää lomakkeen näyttämiseen. Kuten **SalesOrderListForm**-lomakkeen tapauksessa, voit nopeasti näyttää tietueen tiedot ilman lomakkeen manuaalista rakentamista.  
   
    ![](media/entity-form-control/entityform-tutorial-01-11.png)
4. Määritä **SalesOrderDetailsForm**-kohteen **Item**-ominaisuudeksi **SalesOrderListForm.Selected**.
   
    **SalesOrderDetailsForm** näyttää tiedot tietueelle, jota käyttäjä napsauttaa tai napauttaa **SalesOrderListForm**-kohteessa.
   
    ![](media/entity-form-control/entityform-tutorial-01-12.png)
5. Esikatsele sovellusta painamalla F5-näppäintä ja napsauttamalla tai napauttamalla myyntitilausta vasemmalla olevasta luettelosta.  
   
    Valitsemasi tilauksen tiedot näytetään oikealla.  
   
    ![](media/entity-form-control/entityform-tutorial-01-13.png)  

## <a name="configure-a-field-to-navigate-to-another-screen"></a>Kentän määrittäminen toiseen näyttöön siirtymiseksi
Lisätään sovellukseemme seuraavaksi lisää näyttöjä ja määritetään **Entiteettilomake**-ohjausobjektin kentät siirtämään näkymä sovelluksen toiseen näyttöön, kun käyttäjä napsauttaa tai napauttaa kenttää.  

1. Lisää sovellukseen toinen näyttö ja anna sille nimeksi **SalesOrderDetailsScreen**.
2. Leikkaa **SalesOrderDetailsForm**, liitä se **SalesOrderDetailsScreen**-näyttöön ja muuta lomakkeen kokoa niin, että se täyttää suurimman osan näytöstä niin, että ylös jää kuitenkin tilaa kuvakkeelle.
3. Lisää **SalesOrderDetailsScreen**-näytön vasemman yläkulman lähelle takaisin-nuolikuvake.
4. Määritä takaisin-nuolikuvakkeen **OnSelect**-ominaisuudeksi [**Back**](functions/function-navigate.md)-toiminto.  
   
    ![](media/entity-form-control/entityform-tutorial-01-14.png)
5. Muuta **SalesOrderListScreen**-näytössä **SalesOrderListForm**-kohteen kokoa niin, että se kattaa koko näytön.
6. Valitse **SalesOrderListForm** napsauttamalla sitä.
7. Aseta oikealla olevassa ruudussa **Kentät**-kohdan alla **SalesOrderId** siirtymään **SalesOrderDetailsScreen**-näyttöön.  
   
    ![](media/entity-form-control/entityform-tutorial-01-15.png)
   
    **Entiteettilomake**-ohjausobjekti näyttää **SalesOrderId**-kentän arvot (luettelon ensimmäinen sarake) linkkeinä.
   
    ![](media/entity-form-control/entityform-tutorial-01-16.png)  
8. Esikatsele sovellusta painamalla F5-näppäintä ja napsauttamalla tai napauttamalla linkkiä myyntitilausluettelosta.
   
    ![](media/entity-form-control/entityform-tutorial-01-17.png)  
   
    Toinen näyttö avautuu ja näyttää määrittämäsi myyntitilauksen tiedot.
   
    ![](media/entity-form-control/entityform-tutorial-01-18.png)  
   
    Voit näyttää eri myyntitilauksen tiedot siirtymällä takaisin luetteloon napsauttamalla tai napauttamalla takaisin-nuolta ja napsauttamalla tai napauttamalla sitten haluamasi tilauksen linkkiä.

## <a name="navigate-with-a-context-variable"></a>Siirtyminen kontekstimuuttujan avulla
**SalesOrderDetailsForm**-kohteen **Item**-ominaisuudeksi asetetaan **SalesOrderListForm.Selected**, jotta **SalesOrderDetailsForm** näyttää tietoja tietueesta, jonka käyttäjä valitsee **SalesOrderListForm**-lomakkeessa. Voit myös saada valitun tietueen kontekstin käyttämällä **NavigationContext**-kontekstimuuttujaa, joka luodaan automaattisesti, kun käytät lomakkeen mukautusruutua siirtymisen kohdekentän valitsemiseksi.  

1. Aseta **SalesOrderDetailsForm**-lomakkeen **Item**-ominaisuudeksi **NavigationContext**.
   
    ![](media/entity-form-control/entityform-tutorial-01-19.png)
2. Esikatsele sovellusta painamalla F5-näppäintä ja napsauttamalla tai napauttamalla linkkiä myyntitilausluettelosta.
   
    Sovellus avaa **SalesOrderDetailsScreen**-näytön ja näyttää määrittämäsi myyntitilauksen tiedot.

Katsotaanpa, kuinka lomakkeen mukautusruutu lisää siirtymisen ja kontekstin.  

**SalesOrderListForm**-lomakkeen **SelectableFields**-ominaisuus määrittää **SalesOrderId:n** valittavaksi kentäksi.

![](media/entity-form-control/entityform-tutorial-01-20.png)  

Tämä määritettiin automaattisesti, kun määritimme lomakkeen mukautusruudulla **SalesOrderId**-kentän siirtämään näkymän **SalesOrderDetailsScreen**-näyttöön. Näin ollen **SalesOrderId**-kentän arvot näytetään linkkeinä.

**OnFieldSelect** -ominaisuuden **SalesOrderListForm** asetetaan [ **Jos** ](functions/function-if.md) funktio, joka määrittää, onko käyttäjä napsauttaa tai napauttaa **salesorderid** kenttä: **SalesOrderListForm.SelectedField.SalesOrderId = true**.  

Jos funktion tulos on tosi, **SalesOrderDetailsScreen** avautuu aiemmin käyttämämme **NavigationContext**-kontekstimuuttujan kanssa.  

Kaikki tämä määritettiin myös automaattisesti, kun määritimme lomakkeen mukautusruudulla **SalesOrderId**-kentän siirtämään näkymän **SalesOrderDetailsScreen**-näyttöön.  

Näin ollen, kun käyttäjä napsauttaa tai napauttaa SalesOrderId-kenttää, [**If**](functions/function-if.md)-funktio saa arvon tosi, [**Navigate**](functions/function-navigate.md)-funktio kutsutaan vastaavalla kontekstilla ja tietonäyttö näytetään.  

![](media/entity-form-control/entityform-tutorial-01-21.png)  

> [!NOTE]
> Kun käytät lomakkeen mukautusruutua, **NavigationContext** määritetään sinua varten älykkäästi. Kun käyttäjä napsauttaa tai napauttaa **SalesOrderId**-kenttää, **NavigationContext**-arvoksi asetetaan **SalesOrderListForm.Selected**, kuten aiemmassa kaavassa näkyi. Jos olisimme tämän sijaan määrittäneet **Account**-kentän siirtymistä varten, **NavigationContext**-arvoksi olisi asetettu **SalesOrderListForm.Selected.Account** sen varmistamiseksi, että oikea sisältö siirretään. Tämän sisällön kuluttamiseksi tarvitaan kuitenkin **Entiteettilomake**-ohjausobjekti, joka on liitetty Common Data Servicen **Account**-entiteettiin.

## <a name="edit-and-save-a-record"></a>Tietueen muokkaus ja tallennus
Katsotaan lopuksi, kuinka **Entiteettilomake**-ohjausobjektin tietuetta voidaan muokata ja tallentaa.  

1. Lisää **SalesOrderDetailsScreen**-näytössä muokkauskuvake ja aseta sen **OnSelect**-ominaisuudeksi tämä kaava:  
   **EditForm(SalesOrderDetailsForm)**
   
    ![](media/entity-form-control/entityform-tutorial-01-22.png)
2. Lisää muokkauskuvakkeen viereen valintamerkkikuvake ja aseta sen **OnSelect**-ominaisuudeksi tämä kaava:  
   **SubmitForm(SalesOrderDetailsForm)**  
   
    ![](media/entity-form-control/entityform-tutorial-01-23.png)
3. Esikatsele sovellusta painamalla F5-näppäintä, napsauttamalla tai napauttamalla **SalesOrderId**-linkkiä myyntitilauksen tietojen näyttämiseksi ja sitten napsauttamalla tai napauttamalla muokkauskuvaketta.  
   
    **Entiteettilomake**-ohjausobjektin **Mode**-ominaisuudeksi asetetaan **FormMode.Edit**, jotta voit muokata tietuetta.
4. Päivitä **Tilauksen tilaksi** **Lasku**.  
   
    ![](media/entity-form-control/entityform-tutorial-01-24.png)
5. Päivitä **Myyjäksi** **WRK014**.
   
    **Myyjän** valinnan avuksi **Entiteettilomake**-ohjausobjekti näyttää automaattisesti yksityiskohtaisen näkymän. Näkymän luomiseksi ja näyttämiseksi ohjausobjekti käyttää Common Data Servicen **Työntekijä**-entiteetin **DefaultLookup**-kenttäryhmää. **Työntekijä**-entiteettiä käytetään, koska **Myyjä**-kentän tyyppi on **Työntekijä**.
   
    ![](media/entity-form-control/entityform-tutorial-01-25.png)
6. Tallenna muutokset napsauttamalla tai napauttamalla valintamerkin kuvaketta.

**Entiteettilomake**-ohjausobjektin käyttöohjeartikkeli sovelluksia varten päättyy tähän vaiheeseen. Toivomme, että artikkelin tiedot auttavat sinua **Entiteettilomake**-ohjausobjektin käytössä. Kuuntelemme mielellämme ajatuksiasi **Entiteettilomake**-ohjausobjektista ja tavoitteestamme auttaa käyttäjiä luomaan nopeasti monipuolisia lomakkeita sovelluksiin.

