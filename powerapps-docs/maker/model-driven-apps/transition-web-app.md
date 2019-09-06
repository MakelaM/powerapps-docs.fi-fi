---
title: Pikaopas Dynamics 365 for Customer Engagement -sovellusten WWW-asiakasohjelman siirtämisestä Unified Interfaceen | MicrosoftDocs
description: Lisätietoja vanhan WWW-asiakasohjelman siirtämisestä Unified Interfaceen
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
ms.assetid: 14c4c18c-927c-4ea2-ba66-0531285a99a7
caps.latest.revision: 25
ms.author: matp
manager: kvivek
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="quick-start-for-transitioning-your-dynamics-365-for-customer-engagement-apps-web-client-application-to-unified-interface"></a>Pikaopas Dynamics 365 for Customer Engagement -sovellusten WWW-asiakasohjelman siirtämisestä Unified Interfaceen

Unified Interface -sovelluskehys käyttää responsiivisia verkkosuunnitteluperiaatteita voidakseen antaa optimaalisen katselu- ja vuorovaikutuskokemuksen laitteesta, näytön koosta tai suunnasta riippumatta. Tässä pikaoppaassa kerrotaan, miten Dynamics 365 for Customer Engagement -sovellusten WWW-asiakasohjelma siirretään Unified Interfaceen käyttämällä uutta ympäristöä, joka ei ole tuotantoympäristö. Jos haluat käyttää WWW-asiakasohjelmaa ja siirtää sen olemassa olevaan ympäristöön, joka ei ole tuotantoympäristö, saat lisätietoja kohdasta [Pika-aloitusopas, joka sisältää ohjeita olemassa olevan ympäristön käyttämiseen ja vanhan WWW-asiakasohjelman tarkistamiseen Unified Interfacessa](transition-web-app-existing.md). 


## <a name="prerequisites"></a>Edellytykset
- Dynamics 365 for Customer Engagement -sovellusten vanha WWW-asiakasohjelma. 
- Suosittelemme sovelluksen testaamista muussa kuin tuotantoympäristössä, vaikka tämä ei ole pakollista. Näin varmistetaan, että testaaminen ei vaikuta nykyiseen käyttöönottoon tai käyttöönoton jaksoihin. Lisätietoja: [Sandbox-ympäristöjen hallinta](/dynamics365/customer-engagement/admin/manage-sandbox-instances)

## <a name="prepare-the-environment"></a>Ympäristön valmisteleminen
Valitse ensin muun kuin tuotantoympäristö ja ota käyttöön **Käytä vain Unified Interface -sovellusta** -tila. Tällöin Unified Interfacea käytetään kaikissa ympäristön mallipohjaisissa sovelluksissa. Tämä sisältää myös Dynamics 365 for Customer Engagement -sovelluksen moduulit, jotka on alun perin määritetty vanhalle WWW-asiakasohjelmalle.

1. Kirjaudu [PowerAppsiin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), valitse **Ympäristö** ja valitse sitten Sandbox-ympäristö. 

2. Valitse **Asetukset** > **Toiminta** ja ota sitten käyttöön **Käytä vain Unified Interface -sovellusta** -tila.

   > [!div class="mx-imgBorder"] 
   > ![Käytä vain Unified Interface -sovellusta -asetus](media/use-unified-interface-only-pac.png)

Voit määrittää tämän myös Dynamics 365 for Customer Engagement -sovelluksissa. Siirry kohtaan **Asetukset** > **Hallinta** > **Järjestelmäasetukset**. Määritä sitten **Yleiset**-välilehdessä **Ota käyttöön vain Unified Interface** -kohdan arvoksi **Kyllä**.

> [!div class="mx-imgBorder"] 
> ![Käytä vain uutta Unified Interface -sovellusta](media/use-unified-interface-only.png "Käytä vain uutta Unified Interface -sovellusta")


> [!NOTE]
> Jos haluat siirtää ympäristön takaisin edelliseen tilaan, voit vaihtaa Unified Interface -asetusta ja palauttaa alkuperäisen liittymän. Lisätietoja: [Vain Unified Interfacen käyttöönotto](/dynamics365/customer-engagement/admin/enable-unified-interface-only)

## <a name="run-and-validate-your-application-in-the-unified-interface"></a>Sovelluksen suorittaminen ja tarkistaminen Unified Interfacessa
Suorita sovellukset, jotka olivat alunperin WWW-asiakasohjelmia. Huomaa, että kun otat käyttöön **Käytä vain Unified Interface -sovellusta** -asetuksen, kaikki ympäristön käytettävissä olevat sovellukset käyttävät Unified Interfacea, vaikka sovellus olisi alun perin määritetty WWW-asiakasohjelmaa varten.

Jos haluat suorittaa sovelluksen, kirjaudu [PowerAppsiin](https://web.powerapps.com/?utm_source=padocs&utm_medium=linkinadoc&utm_campaign=referralsfromdoc), valitse **Sovellukset** ja valitse sitten suoritettava sovellus. Vaihtoehtoisesti voit siirtyä Dynamics 365 for Customer Engagement -sovelluksissa suoraan **Omat sovellukset** -sivulle, esimerkiksi sivulle *https://contoso.crm.dynamics.com/apps/*.

### <a name="validate-your-app-processes-and-customizations"></a>Sovelluksen, prosessien ja mukautusten tarkistaminen 
Suosittelemme kaikkien käyttötapausten testaamista. Voit aloittaa tärkeimmistä tapauksista tai ryhmitellä tapaukset loogisiksi rakennemalleiksi. Koska Unified Interface perustuu vuorovaikutteiseen rakenteeseen, testit kannattaa tehdä eri laitteissa ja erilaisilla näyttöresoluutioilla. Sovelluksen testaamisen yhteydessä voi tarkistaa, että mukautukset ovat yhteensopivia Unified Interfacen kanssa. Samalla on mahdollista tarkistaa mahdolliset muokattavat tai puuttuvat toiminnot. Luo suunnitelma näiden elementtien tarkistamista varten ja lähetä kysymykset ja palaute yhteisön keskustelupalstalle. <!-- Link tbd -->

> [!IMPORTANT]
> Common Data Service- ja Dynamics 365 for Customer Engagement -sovellusten nykyinen versio sisältää yhä useita vanhentuneita toimintoja. Tarkista, onko sovelluksessa vanhentuneita toimintoja, ja korjaa ne tarvittaessa uusilla ominaisuuksilla. Lisätietoja: [Tärkeitä Dynamics 365 Customer Engagementin tulevia muutoksia (vanhentumisia)](/dynamics365/get-started/whats-new/customer-engagement/important-changes-coming)

### <a name="dynamics-365-for-customer-engagement-apps"></a>Dynamics 365 for Customer Engagement -sovellukset
Jos käytössä on Dynamics 365 for Field Service- tai Dynamics 365 for Project Service Automation -sovellus ja haluat testata Unified Interfacen, sinun on määritettävä uusi Sandbox-ympäristö ja kopioitava tuotantoympäristö uusimman Field Service -sovelluksen version 8 ja Project Service Automation -sovelluksen version 3 päivittämistä varten, ennen kuin nämä sovellukset tarkistetaan Unified Interfacessa. Voit tehdä tämän seuraavasti:

1. Luo uusi Sandbox-ympäristö [Power Platform -hallintakeskuksessa](https://admin.powerplatform.microsoft.com/environments) tai [Dynamics 365 -hallintakeskuksessa](https://port.crm.dynamics.com/). Lisätietoja: [Ilmentymän lisääminen tilaukseen](/dynamics365/customer-engagement/admin/add-instance-subscription)

2. Kopioi uuteen Sandbox-ympäristöön se tuotantoympäristö, jossa on Dynamics 365 for Field Service- tai Dynamics 365 for Project Service Automation -sovellus. Voit tehdä tämän avaamalla tuotantoympäristön Power Platform -hallintakeskuksessa ja valitsemalla sitten **Kopioi**.

    > [!div class="mx-imgBorder"] 
    > ![Kopioi ympäristö](media/ppac-copy-environment.png "Kopioi ympäristö")

3. Valitse **Kopioi ympäristö** -sivulla **Kaikki** ja valitse sitten uusi Sandbox-ympäristö **Valitse korvattava ympäristö** -luettelosta. Valitse lopuksi **Kopioi**. 

    > [!div class="mx-imgBorder"] 
    > ![Korvaa ympäristö](media/ppac-copy-overwrite.png "Korvaa ympäristö")

4. Esille tulee **Korvaa ympäristö** -valintaikkuna. Varmista, että olet valinnut oikean ympäristön ja että oikeat asetukset. Valitse sitten **Vahvista**. 

5. Kun kopiointi onnistuu, näkyviin tulee vahvistusilmoitus. 

6. Valitse valikkoriviltä **Hallitse ratkaisuja**, jos haluat avata **Ratkaisut**-alueen. 

    > [!div class="mx-imgBorder"] 
    > ![Hallitse ratkaisuja](media/ppac-manage-solutions.png "Hallitse ratkaisuja")

    > [!IMPORTANT]
    > Jos **järjestelmänvalvojan tila** on käytössä, se on poistettava käytöstä, jotta **Ratkaisut**-alue näkyy. Lisätietoja: [Järjestelmänvalvojan tila](/power-platform/admin/sandbox-environments#administration-mode)

7. Etsi Field Service- tai Project Service Automation -ratkaisu ja avaa se. **Päivitä**-vaihtoehdon tulisi olla käytettävissä. Valitse vaihtoehto, jos haluat päivittää ratkaisun. 

    > [!div class="mx-imgBorder"] 
    > ![Päivitä ratkaisu](media/ppac-upgrade-solution.png "Päivitä ratkaisu")
    
> [!NOTE]
> Unified Interfacen Field Service- ja Project Service Automation -sovellusten uusimmat versiot ovat oletusarvoisesti käytettävissä uusissa instansseissa. Jos haluat päivittää olemassa olevan ympäristön aiemmista versioista versioista, sinun on pyydettävä päivitysversiota [Microsoftin asiakastuelta](https://go.microsoft.com/fwlink/?LinkId=853505). 

Lisätietoja: [Dynamics 365 for Field Service -sovelluksen uusimmat versiot](/dynamics365/customer-engagement/field-service/version-history#latest-versions) ja [Dynamics 365 for Project Service Automation -sovelluksen päivitysversion aloitussivu](/dynamics365/customer-engagement/project-service/upgrade-psa-home-page)

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

