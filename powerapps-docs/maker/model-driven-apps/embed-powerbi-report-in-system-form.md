---
title: Power BI -raportin upottaminen mallipohjaisessa järjestelmälomakkeessa | MicrosoftDocs
ms.custom: ''
ms.date: 03/05/2019
ms.reviewer: matp
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.assetid: 99c795e0-9165-4112-85b1-6b5e1a4aa5ec
caps.latest.revision: 1
author: prsi-msft
ms.author: prsi
manager: kvivek
tags:
  - Links to topic not migrated
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="embed-a-power-bi-report-in-a-model-driven-system-form"></a>Power BI -raportin upottaminen mallipohjaisessa järjestelmälomakkeessa
Kun Power BI -raportteja käytetään PowerAppsin mallipohjaisissa sovelluksissa, järjestelmälomakkeisiin saadaan monipuoliset raportti- ja analyysitoiminnot, minkä ansiosta käyttäjät saavat tehtyä enemmän. Tällä tavoin tietoja voidaan kerätä eri järjestelmistä ja mukauttaa ne yhden tietueen kontekstitasolle.
 
## <a name="prerequisites"></a>Edellytykset
Power BI -sisällön upottaminen on valinnainen ominaisuus, ja se on poistettu oletusarvoisesti käytöstä kaikissa ympäristöissä. Se on otettava käyttöön, ennen kuin voit upottaa Power BI -sisällön. Lisätietoja: [Power BI -visualisointien ottaminen käyttöön organisaatiossa](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/use-power-bi?#enable--visualizations-in-the-organization).

Tämä ominaisuus edellyttää ratkaisun vientiä, sen muokkaamista xml-koodikatkelman lisäämiseksi ja tuomista takaisin ympäristöön. Varmista, että tuot muutokset kohdeympäristöön käyttämällä ainoastaan hallittua ratkaisua. Lisätietoja päivityksen asentamisesta aiemmin luotuun hallittuun ratkaisuun on kohdassa [Ratkaisujen tuominen. päivittäminen ja vieminen](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/import-update-export-solutions).

## <a name="embed-without-contextual-filtering"></a>Upottaminen ilman tilannekohtaista suodatusta
Voit käyttää Power BI -raportteja ja -ruutuja yksinkertaisesti upottamalla ne, jonka jälkeen saat täsmälleen saman raportin. Tämä ei tarkoita niiden muuttamista nykyisen tilannekohtaisen mallipohjaisen lomakkeen mukaiseksi, joten saat saman raportin tai ruudun entiteetin kaikissa tietueissa. Seuraavassa raportissa näkyy esimerkiksi kaikkien asiakkaiden maantieteellinen sijainti kerralla, ja se kätevä yhteenvetotietojen näyttämiseen.

> [!div class="mx-imgBorder"] 
> ![](media/embed-powerbi/embed-powerbi-report-in-system-form-unfiltered.png "Embed-powerbi-report-in-system-form-unfiltered")

Voit upottaa järjestelmälomakkeisiin osa, joka isännöi Power BI -raportteja ja -ruutuja lisäämällä seuraavan koodikatkelman lomalleen XML-tiedoston `<sections>`-lohkoon. Tuo sitten ratkaisu kohdeympäristössä. 

```xml
<section id="{d411658c-7450-e1e3-bc80-07021a04bcc2}" locklevel="0" showlabel="true" IsUserDefined="0" name="tab_4_section_1" labelwidth="115" columns="1" layout="varwidth" showbar="false">
    <labels>
        <label languagecode="1033" description="Unfiltered Power BI embedding demo"/>
    </labels>
    <rows>
        <row>
            <cell id="{7d18b61c-c588-136c-aee7-03e5e74a09a1}" showlabel="true" rowspan="20" colspan="1" auto="false">
                <labels>
                    <label languagecode="1033" description="Accounts (Parent Account)"/>
                </labels>
                <control id="unfilteredreport" classid="{8C54228C-1B25-4909-A12A-F2B968BB0D62}">
                    <parameters>
                        <PowerBIGroupId>00000000-0000-0000-0000-000000000000</PowerBIGroupId>
                        <PowerBIReportId>544c4162-6773-4944-900c-abfd075f6081</PowerBIReportId>
                        <TileUrl>https://xyz.powerbi.com/reportEmbed?reportId=544c4162-6773-4944-900c-abfd075f6081</TileUrl>
                    </parameters>
                </control>
            </cell>
        </row>
        <row/>
    </rows>
</section>
```
> [!IMPORTANT]
> Varmista, että käytät XML-näytteessä ilmaistua ohjausobjektia `classid="{8C54228C-1B25-4909-A12A-F2B968BB0D62}"`.

 Seuraava taulukko sisältää edellisen esimerkin ominaisuudet.

|                                                 Ominaisuus                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Kuvaus                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         **PowerBIGroupId**                          |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  Power BI -työtilan tunnus. Käyttäjän oletustyötila on aina 00000000-0000-0000-0000-000000000000. Voit tarkistaa minkä tahansa työtilan tunnuksen työtilan URL-osoitteesta. Esimerkki: https://xyz.powerbi.com/groups/0ddbe381-256d-44bc-93de-34e47f3d9ab4/.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|                               **PowerBIReportId**                                |                             Power BI -raportin tunnus. Vaihda tähän raportti, jonka haluat upottaa. Voit tarkistaa minkä tahansa raportin tunnuksen raportin URL-osoitteesta. Esimerkki: https://xyz.powerbi.com/groups/me/reports/544c4162-6773-4944-900c-abfd075f6081.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
|                                       **TileUrl**                                       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        Upotettavan Power BI -raportin tai -ruudun URL-osoite. Varmista, että käytät oikeaa Power BI -esiintymän nimeä (vaihda oma osoite osoitteen msit.powerbi.com tilalle) ja raportin tunnusta (vaihda tunnuksen reportId=544c4162-6773-4944-900c-abfd075f6081 tilalle oma tunnus). Esimerkki: https://xyz.powerbi.com/reportEmbed?reportId=544c4162-6773-4944-900c-abfd075f6081.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |

## <a name="embed-with-contextual-filtering"></a>Upottaminen sisällyttämällä tilannekohtainen suodatus
Voit parantaa Power BI -raporttien ja -ruutujen merkityksellisyyttä käyttämällä nykyisessä mallikohtaisessa lomakkeessa tilannekohtaisia suodattimia, jolloin raportti tai ruutu suodatetaan nykyisen tietueen määritteillä. Esimerkiksi asiakkaan maantieteellinen sijainti näytetään seuraavassa raportissa suodattamalla Power BI -raportti asiakkaan nimen perusteella. Tällä tavoin entiteetin kaikkien tietueiden tilannekohtaiset tiedot voidaan näyttää yhdessä raportissa.

> [!div class="mx-imgBorder"] 
> ![](media/embed-powerbi/embed-powerbi-report-in-system-form-filtered.png "Embed-powerbi-report-in-system-form-filtered")

Suodatus tehdään lisäämällä `<PowerBIFilter>`-elementti `<parameter>`-lohkossa, kuten seuraavassa esimerkissä. Voit luoda suodatinlausekkeen mistä tahansa lomakkeen entiteetin määritteestä. Lisätietoja: Kohdassa [Suodattimien muodostaminen](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Filters#contructingfilters) käsitellään omien suodattamien luomista.
    
```xml
<control id="filteredreport" classid="{8C54228C-1B25-4909-A12A-F2B968BB0D62}">
    <parameters>
        <PowerBIGroupId>00000000-0000-0000-0000-000000000000</PowerBIGroupId>
        <PowerBIReportId>544c4162-6773-4944-900c-abfd075f6081</PowerBIReportId>
        <TileUrl>https://xyz.powerbi.com/reportEmbed?reportId=544c4162-6773-4944-900c-abfd075f6081</TileUrl>
        <PowerBIFilter>{"Filter": "[{\"$schema\":\"basic\",\"target\":{\"table\":\"My Active Accounts\",\"column\":\"Account Name\"},\"operator\":\"In\",\"values\":[$a],\"filterType\":1}]", "Alias": {"$a": "name"</PowerBIFilter>
    </parameters>
</control>
```

Huomaa, että tässä käytetään samaa ohjausobjektia kuin suodattamattoman raportin upottamisessa, joten ohjausobjektin luokkatunnus on sama. 

Seuraava taulukko sisältää ominaisuudet, joita ei käytetty edellisessä esimerkiksi.

|                                                 Ominaisuus                                                  |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      Kuvaus                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
|-----------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                         **PowerBIFilter**                          |        Suodatinlauseke muodostaa tilannekohtaisen Power BI -raportin välittämällä lomakemääritteet parametreina. Luettavuuden parantamiseksi suodatin muodostetaan, kuten seuraavassa kuvassa.    |

    {
            "Filter": "[{
                    \"$schema\":\"basic\",
                    \"target\":{
                            \"table\":\"My Active Accounts\",
                            \"column\":\"Account Name\"
                    },
                    \"operator\":\"In\",
                    \"values\":[$a, $b],
                    \"filterType\":1
            }]",
            "Alias": {
                    "$a": "firstname",
                    "$b":"lastname"
            }
    }

Edellisen lausekkeen kohdeosa määrittää taulukon ja sarakkeen, joissa suodattimia käytetään. Operaattori määrittää logiikan ja arvot, joilla PowerAppsin mallipohjaisesta sovelluksessa välitetyt tiedot määritetään. Yleisessä parametroinnissa arvot muodostetaan määrittämällä tunnus. Edellisessä lausekkeessa asiakkaan **firstname**- ja **lastname**-arvot välitetään ja jompikumpi niistä haetaan Power BI -raportin **Asiakkaan nimi** -sarakkeessa. Huomaa, että **firstname** ja **lastname** ovat asiakasentiteetin määritteiden yksilöiviä nimiä, joiden arvo välitetään tässä. 

Voit luoda monimutkaisia suodatinlausekkeita tutustumalla esimerkkeihin kohdassa [Suodattimien muodostaminen](https://github.com/Microsoft/PowerBI-JavaScript/wiki/Filters#contructingfilters) ja antamalla soveltuvat $schema- ja filterType-arvot. Varmista, että käytät jokaisessa suodatinosan literaalissa ohjausmerkkiä *\"*, jotta JSON muodostetaan oikein.

## <a name="known-issues-and-limitations"></a>Tunnetut ongelmat ja rajoitukset
1. Tämä integraatio on käytettävissä vain tuettujen selainten ja mobiililaitteiden Unified Interface -asiakasohjelmissa.
2. Kun tämä lomake avataan PowerAppsin lomakkeiden suunnitteluohjelmassa, ohjausobjekti ei näy merkityksellä tavalla. Tämä johtuu siitä, että ohjausobjekti on mukautettu lomakkeen suunnitteluohjelman ulkopuolella.
3. Käyttäjät voidaan todentaa Power BI:n automaattisesti PowerAppsin käyttäjänimellä ja salasanalla. Jos tunnistetietoja vastaavaa Power BI -tiliä ei ole, kirjautumiskehote avautuu, kuten seuraavassa kuvassa. 

   > [!div class="mx-imgBorder"] 
   > ![](media/embed-powerbi/embed-powerbi-report-in-system-form-auth-1.png "Embed-powerbi-report-in-system-form-auth-1")

4. Mitään tietoja ei näytetä, jos Power BI:hin kirjautumiseen käytetään väärää tiliä. Voit kirjautua sisään oikeilla tunnistetiedoilla kirjautumalla ensin ulos ja sitten uudelleen sisään.

   > [!div class="mx-imgBorder"] 
   > ![](media/embed-powerbi/embed-powerbi-report-in-system-form-auth-2.png "Embed-powerbi-report-in-system-form-auth-2")

   > [!div class="mx-imgBorder"] 
   > ![](media/embed-powerbi/embed-powerbi-report-in-system-form-auth-3.png "Embed-powerbi-report-in-system-form-auth-3")

5. Raporttitietojen PowerAppsissa näytettävä näkymä on sama kuin Power BI:ssä eivätkä PowerAppsin käyttöoikeusroolit ja oikeudet vaikuta näytettäviin tietoihin. Tiedot ovatkin käytännössä samat, jotka Power BI -tietojoukon tekijä näkisi. Jos haluat käyttää PowerAppsin käyttöoikeusroolien ja ryhmien kaltaisia tietojen käyttöoikeusrajoituksia, käytä [Power BI:n rivitason suojausta](https://docs.microsoft.com/en-us/power-bi/service-admin-rls).
6. Jos lomake ei näytä Power BI -raporttia ratkaisun tuomisen ja mukautusten julkaisemisen jälkeen, avaa se mallipohjaisessa lomake-editorissa ja tallenna se, jolloin lomakkeen JSON luodaan uudelleen.


### <a name="see-also"></a>Katso myös

[Power BI -koontinäytön upottaminen PowerAppsin omaan mallipohjaiseen koontinäyttöön](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/basics/add-edit-power-bi-visualizations-dashboard)

[Power BI:n käyttäminen Dynamics 365 for Customer Engagementin kanssa](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/admin/use-power-bi)

[Ratkaisujen tuominen. päivittäminen ja vieminen](../common-data-service/import-update-export-solutions.md)
