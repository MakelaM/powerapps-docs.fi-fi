---
title: Rajoitetut entiteetit, jotka vaativat Dynamics 365 -käyttöoikeuksia | Microsoft Docs
description: Lista Common Data Service for Appsin sisältämistä rajoitetuista entiteeteistä, jotka vaativat Dynamics 365 -käyttöoikeuksia.
documentationcenter: na
author: clwesene
manager: kfile
editor: ''
tags: ''
ms.service: powerapps
ms.devlang: na
ms.topic: reference
ms.component: cds
ms.date: 05/01/2018
ms.author: clwesene
ms.openlocfilehash: 508f58b48f2dd51bf25f23905cc3513db90ed1ce
ms.sourcegitcommit: 45fac73f04aa03b5796ae6833d777f4757e67945
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 05/03/2018
---
# <a name="restricted-entities-requiring-dynamics-365-licenses"></a>Rajoitetut entiteetit, jotka vaativat Dynamics 365 -käyttöoikeuksia
Sovellusten tekijät voivat käyttää useimpia Common Data Service (CDC) for Appsin sisältämiä entiteettejä sovellusten ja työnkulkujen luomiseen käyttäjille, joilla on pelkästään PowerApps Plan 1 -käyttöoikeus. Jotkin entiteetit sisältävät kuitenkin monitasoista liiketoimintalogiikkaa, joka vaatii sovellusten käyttäjiltä PowerApps Plan 2- tai Microsoft Flow Plan 2 -käyttöoikeudet (katso lisätietoja kohdasta [Entiteettien käyttöoikeusvaatimukset](data-platform-entity-licenses.md)). Vielä pienempi joukko Dynamics 365 -tuotteisiin sidottuja entiteettejä vaatii pohjaan ja malliin perustuvien sovellusten käyttäjiltä vastaavan Dynamics 365 -tuotteen käyttöoikeuden, jos heidän täytyy luoda, päivittää tai poistaa tietueita entiteettien sisältä. Näitä kutsutaan *rajoitetuiksi* entiteeteiksi.

Entiteetit voivat olla Dynamics 365 -käyttöoikeudella rajoitettuja seuraavista syistä:

* Entiteettiä käytetään sellaisten tuotekohtaisten määritystietojen säilyttämiseen, joita ei tavallisesti käytetä sovelluksen ulkopuolella.
* Entiteettiin liittyy edistynyt logiikka, joka luo ja ylläpitää tietoja tietyllä tavalla Dynamics 365 -tuotteen sisällä käytettynä.

Jos sovellus tai työnkulku vain lukee tietoja entiteetistä, Dynamics 365 -käyttöoikeutta ei tarvita ja soveltuva PowerApps- tai Microsoft Flow -käyttöoikeus riittää. 

## <a name="restricted-entities-for-create-update-and-delete-operations"></a>Luo-, päivitä- ja poista-toimintojen rajoitetut entiteetit
Seuraavassa taulukossa on lueteltu rajoitetut entiteetit ja liittyvät Dynamics 365 -käyttöoikeusvaatimukset PowerApps- ja Microsoft Flow -sovellusten käyttäjille, jotka luovat, päivittävät tai poistavat entiteettien sisälle tallennettuja tietoja. 

|Entiteetti  |Looginen nimi  |Käyttöoikeus vaaditaan  |
|---------|---------|---------|
Actual |msdyn_actual |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Agreement Business Process |msdyn_bpf_baa0a411a239410cb8bded8b5fdd88e3 |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Booking journal | msdyn_bookingjournal|Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Booking Setup Metadata | msdyn_bookingsetupmetadata|Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Booking timestamp | msdyn_bookingtimestamp|Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Case to Work Order Business Process |msdyn_bpf_989e9b1857e24af18787d5143b67523b |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Configuration |msdyn_configuration |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Entitlement | entitlement | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Estimate Line|msdyn_estimateline|Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Estimate|msdyn_estimate |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Fact|msdyn_fact |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Field service setting |msdyn_fieldservicesetting |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Field Service System Job |msdyn_fieldservicesystemjob |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Goal | goal | Dynamics 365 for Sales Professional, <br>**tai** Dynamics 365 for Sales, Enterprise edition, <br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Incident | incident | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Inventory Journal |msdyn_inventoryjournal |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Invoice Process |msdyn_bpf_d8f9dc7f099f44db9d641dd81fbd470d |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Journey | journey | Dynamics 365 for Marketing <br> **tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Knowledge article | knowledgearticle | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Organizational Unit |msdyn_organizationalunit |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Product Inventory |msdyn_productinventory |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Project Parameter|msdyn_projectparameter |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Project Stages| msdyn_bpf_665e73aa18c247d886bfc50499c73b82|Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Project Task Dependency|msdyn_projecttaskdependency |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Project Task|msdyn_projecttask |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Project Team Member|msdyn_projecteam |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Purchase Order Business Process | msdyn_bpf_2c5fe86acc8b414b8322ae571000c799|Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Resource Assignment Detail (Deprecated)|msdyn_resourceassignmentdetail |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Resource Assignment|msdyn_resourceassignment |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Resource Restriction (Deprecated) |msdyn_workorderresourcerestriction | Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Routing rule set | routingrule | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Schedule Board Setting |msdyn_scheduleboardsetting |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Scheduling Parameter |msdyn_schedulingparameter |Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
SLA| sla | Dynamics 365 for Customer Service, Enterprise edition <br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
System User Scheduler Setting |msdyn_systemuserschedulersetting|Dynamics 365 for Field Service <br> **tai** Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Transaction Connection|msdyn_transactionconnection |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Transaction Origin|msdyn_transactionorigin |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Transaction Type|msdyn_transactiontype |Dynamics 365 for Project Service Automation<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Unique Number|msdyn_uniquenumber |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Work Order Business Process |msdyn_bpf_d3d97bac8c294105840e99e37a9d1c39 |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus
Work Order Details Generation Queue (Deprecated)|msdyn_workorderdetailsgenerationqueue |Dynamics 365 for Field Service<br>**tai** Dynamics 365 Customer Engagement -sopimus <br> **tai** Dynamics 365 -sopimus

## <a name="licensing"></a>Käyttöoikeudet
Katso lisätietoja PowerAppsin ja Dynamics 365 -käyttöoikeuksista sivulla [Käyttöoikeuksien yleiskuvaus](../../administrator/pricing-billing-skus.md).

