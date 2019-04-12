---
title: Dynamics 365 -käyttöoikeuksia vaativat rajoitetut entiteetit | Microsoft Docs
description: 'Niiden Common Data Servicen rajoitettujen entiteettien luettelo, jotka vaativat Dynamics 365 -käyttöoikeudet.'
author: lancedMicrosoft
manager: kfile
ms.service: powerapps
ms.component: cds
ms.topic: reference
ms.date: 05/01/2018
ms.author: lanced
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="restricted-entities-requiring-dynamics-365-licenses"></a>Dynamics 365 -käyttöoikeuksia vaativat rajoitetut entiteetit
Sovellusten tekijät voivat käyttää suurinta osaa Common Data Servicen käytettävissä olevista entiteeteistä luodessaan sovelluksia ja työnkulkuja käyttäjille, joilla on vain PowerApps-palvelupaketin 1 käyttöoikeus. Joissakin entiteeteissä on kuitenkin monimutkaista liiketoimintalogiikkaa, joka vaatii käyttäjiltä PowerApps-palvelupaketin 2 tai Microsoft Flow -palvelupaketin 2 käyttöoikeuden (lisätietoja on kohdassa [Entiteetin käyttöoikeusvaatimukset](data-platform-entity-licenses.md)). Jopa pieni Dynamics 365 -tuotteisiin yhdistetty entiteettijoukko edellyttää kaavion ja mallipohjaisen sovelluksen käyttäjiltä Dynamics 365 -tuotteen käyttöoikeuden, jos käyttäjien on luotava, päivitettävä tai poistettava tietueita entiteeteistä. Näitä kutsutaan *rajoitetuiksi* entiteeteiksi.

Seuraavien syiden vuoksi entiteetit voivat vaatia Dynamics 365 -käyttöoikeuden:

* Entiteettiä käytetään sellaisten tuotekohtaisten määritystietojen tallennuksessa ja ylläpidossa, joita ei yleensä käytetä sovelluksen ulkopuolella.
* Entiteettiin liittyy logiikkaa, joka luo ja ylläpitää tietoja erityisellä tavalla Dynamics 365 -tuotteen käyttämisen yhteydessä.

Jos sovellus tai työnkulku lukee tietoja entiteetistä, Dynamics 365 -käyttöoikeus ei ole pakollinen. Tarvitaan vain soveltuva PowerApps- tai Microsoft Flow -käyttöoikeus. 

## <a name="restricted-entities-for-create-update-and-delete-operations"></a>Rajoitetut entiteetit toimintojen luomista, päivittämistä ja poistamista varten
Seuraava taulukko sisältää rajoitetut entiteetit ja liittyvät Dynamics 365 -käyttöoikeusvaatimukset PowerApps- ja Microsoft Flow -sovelluksen käyttäjille, jotka luovat, päivittävät tai poistavat entiteettien tietoja. 

|Entiteetti  |Looginen nimi  |Käyttöoikeus tarvitaan  |
|---------|---------|---------|
Todellinen |msdyn_actual |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Sopimus-liiketoimintaprosessi |msdyn_bpf_baa0a411a239410cb8bded8b5fdd88e3 |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Varauksen kirjauskansio | msdyn_bookingjournal|Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Varauksen asetuksen metatiedot | msdyn_bookingsetupmetadata|Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Varauksen aikaleima | msdyn_bookingtimestamp|Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Palvelupyyntö | tapaus | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Palvelupyynnöstä työtilaukseen -liiketoimintaprosessi |msdyn_bpf_989e9b1857e24af18787d5143b67523b |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Määritys |msdyn_configuration |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Oikeudet | palvelun taso | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Arviorivi|msdyn_estimateline|Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Arvio|msdyn_estimate |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Tieto|msdyn_fact |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Field Service -sovelluksen asetus |msdyn_fieldservicesetting |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Field Service -sovelluksen järjestelmätyö |msdyn_fieldservicesystemjob |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Tavoite | goal | Dynamics 365 for Sales Professional, <br>**tai** Dynamics 365 for Sales, Enterprise edition, <br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Varaston kirjauskansio |msdyn_inventoryjournal |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Laskuprosessi |msdyn_bpf_d8f9dc7f099f44db9d641dd81fbd470d |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Siirtymä | siirtymä | Dynamics 365 for Marketing <br> **tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Tietoartikkeli | knowledgearticle | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Organisaatioyksikkö |msdyn_organizationalunit |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Tuotteen varasto |msdyn_productinventory |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Projektin parametri|msdyn_projectparameter |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Projektin vaiheet| msdyn_bpf_665e73aa18c247d886bfc50499c73b82|Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Projektitehtävän riippuvuus|msdyn_projecttaskdependency |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Projektin tehtävä|msdyn_projecttask |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Projektiryhmän jäsen|msdyn_projecteam |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Ostotilaus-liiketoimintaprosessi | msdyn_bpf_2c5fe86acc8b414b8322ae571000c799|Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Resurssien delegoinnin tiedot (vanhentunut)|msdyn_resourceassignmentdetail |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Resurssien delegointi|msdyn_resourceassignment |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Resurssirajoitus (vanhentunut) |msdyn_workorderresourcerestriction | Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Reitityssääntöjoukko | routingrule | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Aikataulutaulukon asetus |msdyn_scheduleboardsetting |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Aikataulutuksen parametri |msdyn_schedulingparameter |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Palvelutasosopimus (SLA)| sla | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Järjestelmäkäyttäjän aikataulutuksen asetus |msdyn_systemuserschedulersetting|Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Tapahtuman yhteys|msdyn_transactionconnection |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Tapahtuman alkuperä|msdyn_transactionorigin |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Tapahtumatyyppi|msdyn_transactiontype |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Yksilöllinen numero|msdyn_uniquenumber |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Työtilaus-liiketoimintaprosessi |msdyn_bpf_d3d97bac8c294105840e99e37a9d1c39 |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti
Työtilauksen tietojen luontijono (vanhentunut)|msdyn_workorderdetailsgenerationqueue |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement Plan <br> **tai** Dynamics 365 -palvelupaketti

## <a name="licensing"></a>Käyttöoikeuden hankkiminen
Lisätietoja PowerApps- ja Dynamics 365 -käyttöoikeuksista on [Käyttöoikeuksien yleiskatsaus](../../administrator/pricing-billing-skus.md) -sivulla.

