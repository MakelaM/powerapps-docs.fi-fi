---
ms.openlocfilehash: 787ff9592604f9a9bce1929e4d429a39da5ec48a
ms.sourcegitcommit: 982cab99d84663656a8f73d48c6fae03e7517321
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/28/2019
ms.locfileid: "67456836"
---
Kun otat käyttöön Dynamics 365 Mobile Offlinen, Dynamics 365 Online -tiedot ladataan SQL Azure -tietokantaan Azure-pilvipalvelun avulla sen perusteella, mille entiteeteille otat offline-käytön käyttöön. Kun käyttäjä muodostaa yhteyden Azure-pilvipalveluun mobiilisovelluksella, joka tukee offline-käyttöä, tiedot ladataan Azure SQL -tietokannasta mobiililaitteen paikalliseen tietokantaan. Tiedonsiirto SQL Azure -tietokannan ja Azure-pilvipalvelun sekä offline-käyttöä tukevan Dynamics 365 -mobiilisovelluksen välillä tehdään suojatulla SSL-yhteydellä. Asiakastiedot tallennetaan lopulta SQL Azure -tietokantaan ja mobiililaitteeseen.  
  
 Järjestelmänvalvoja määrittää käyttöoikeusrooleilla ja Dynamics 365 Mobile -profiilia mukauttamalla, onko organisaation käyttäjillä oikeus käyttää tietoja offline-tilassa Microsoft Dynamics 365 Mobile Offline -sovelluksella. Dynamics 365 -järjestelmänvalvojat voivat määrittää, mitkä entiteetit ladataan offline-synkronoinnissa. Tämä on mahdollista asetusten valintaikkunan Mobile Offline -asetuksella.  
  
 Ota huomioon, että käyttäjän laitteeseen tallennettuja tietoja hallitsee asiakas, ei Microsoft. Järjestelmänvalvoja voi hallita käyttöoikeusrooli- ja entiteettitasolla täysin sitä, mitä tietoja voidaan hakea. Kun tiedot on haettu järjestelmästä, ne eivät kuitenkaan enää ole Dynamics 365 Onlinen suojauksen piirissä.  
  
 Mobile Offline -toimintoon liittyvät Azure-komponentit ja palvelut on lueteltu alla.  
  
 **Huomautus:** Jos haluat lisätietoja muista Azure-palveluista, siirry [Microsoft Azuren luottamuskeskukseen](https://azure.microsoft.com/support/trust-center/).  
  
 **Pilvipalvelut (verkkorooli)**  
  
 Mobile Offline hyödyntää kahta pilvipalvelua: yhtä valmisteluun ja toista tietojen synkronointiin.  
  
 Valmistelupalvelulla on yksi verkkorooli, joka lukee palveluväylän jonosta Dynamics 365:stä tulevien tapahtumien viestit (esimerkiksi valmistelu ja valmistelun purkaminen). Sitten se käsittelee nämä viestit luomalla ja poistamalla organisaatiotietokantoja sekä lähettämällä toistuvat työkohteet (viestit) tietojen synkronoinnin palveluväylän jonoon. Tässä yhteydessä se lukee ja kirjoittaa määritystiedostoja CSCFG-tiedoston tai Dynamics 365 -ohjelmiston ohjelmointirajapinnan avulla.  
  
 Tietojen synkronointipalvelulla on kaksi verkkoroolia. Toinen pitää väliaikaisen tietokannan rakenteen ja tiedot synkronoituna Dynamics 365:n organisaation metatietojen ja tietojen kanssa, kun taas toinen verkkorooli huolehtii synkronointipalvelimen suorittamisesta ja asiakasohjelmien synkronointipyyntöjen käsittelystä. Ensimmäinen verkkorooli käsittelee eri organisaatioiden viestit tietojen synkronoinnin palveluväylän jonosta ja ottaa sitten yhteyttä Dynamics 365:een hakeakseen metatietojen ja tietojen muutokset ennen niiden vahvistamista väliaikaiseen tietokantaan. Se myös määrittää synkronointipalvelimeen järjestelmästä tulevat ja järjestelmään lähetettävät organisaatiot sekä niiden asiakasmallit. Toinen verkkorooli suorittaa synkronointipalvelinta (hallitsematon koodi) hallinnan ja synkronoinnin päätepisteiden isännöimiseksi. Toinen verkkorooli lähettää hallinnan päätepisteen avulla määritystiedot. Ulkoiset asiakkaat (Dynamics 365 -mobiilisovellus) synkronoivat tietoja synkronoinnin päätepisteen avulla. Aivan kuten valmistelupalvelussa, molemmat roolit lukevat ja kirjoittavat määritystiedostoja CSCFG-tiedoston tai Dynamics 365 -ohjelmiston ohjelmointirajapinnan avulla.  
  
 **Jono**  
  
 Mobile Offline käyttää Azure-jonoja viestinsiirrossa Dynamics 365:n ja Azuren välillä. Sitä käytetään pilvipalveluiden käsittelemien työkohteiden ylläpitoon. Jokaiseen viestiin tallennetaan tietoja (esimerkiksi organisaatiotunnus, sen entiteetin nimi, johon tiedot synkronoidaan, ja organisaation OData-päätepisteen yhteysmerkkijono).  
  
 **SQL-tietokanta**  
  
 Mobile Offline tallentaa Azure SQL -tallennuksen avulla  
  
-   Dynamics 365 -organisaatioista replikoidut tiedot ja asiakkaiden synkronointipyyntöjen toteuttamisen tiedot  
  
-   määritystiedot, esimerkiksi organisaatioiden tietokantojen yhteysmerkkijonot.  
  
 **Tallennus**  
  
 Mobile Offline tallentaa Azure Blob -säilön avulla pilvipalvelun luomat lokit ja jäljitystiedot.  
  
 **Active Directory -palvelu**  
  
 Mobile Offline todentautuu muihin palveluihin (esimerkiksi Dynamics 365, ohjelmiston ohjelmointirajapinta tai Azure-hallintaohjelmointirajapinnat) Azure Active Directory -palvelun avulla.  
  
 **Azure DNS**  
  
 Mobile Offline uudelleenohjaa asiakaspyynnöt organisaatioiden nimien perusteella oikeisiin pilvipalvelun päätepisteisiin Azure DNS:n avulla.  
  
 **Azure-näennäisverkko**  
  
 Azure-näennäisverkko (VNet) edustaa omaa verkkoasi pilvessä. Dynamics 365 -tuotetiimi voi hallita Azure-verkkosi asetuksia ja määrittää DHCP-osoitealueet, DNS-asetukset, suojauskäytännöt ja reitityksen.  
  
 **Azuren kuormituksentasain**  
  
 Azuren kuormituksentasain tarjoaa suuren käytettävyyden ja verkon erinomaisen suorituskyvyn sovelluksillesi. Se on Layer-4 (TCP, UDP) -tyyppinen kuormituksentasain, joka jakaa saapuva liikenteen pilvipalveluiden hyvässä toimintakunnossa oleviin palveluesiintymiin tai virtuaalikoneisiin, jotka on määritetty kuormituksentasainjoukossa. Tasapainotamme käyttöönoton päätepisteitä sen avulla.