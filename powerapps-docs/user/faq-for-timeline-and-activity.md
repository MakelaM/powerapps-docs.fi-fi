---
title: Usein kysyttyjä kysymyksiä toiminnoista ja aikajanaseinästä | MicrosoftDocs
ms.custom: ''
author: mduelae
manager: kvivek
ms.service: powerapps
ms.component: pa-user
ms.topic: conceptual
ms.date: 01/29/2019
ms.author: mduelae
ms.reviewer: ''
ms.assetid: ''
search.audienceType:
- enduser
search.app:
- PowerApps
- D365CE
ms.openlocfilehash: e79412c79a3b2a6d5c7f7f51c8cfcad8e4f5cc78
ms.sourcegitcommit: 826bde1eab3dd32d7bf9fa3f43ea069694845597
ms.translationtype: HT
ms.contentlocale: fi-FI
ms.lasthandoff: 01/30/2019
ms.locfileid: "55290948"
---
# <a name="frequently-asked-questions-about-activities-and-the-timeline-wall"></a>Usein kysyttyjä kysymyksiä toiminnoista ja aikajanaseinästä  

## <a name="is-a-title-required-when-adding-a-new-note"></a>Täytyykö uudelle muistiinpanolle antaa otsikko?

Ei. Otsikkokenttä on määritetty pakolliseksi kentäksi toiminnon muistiinpanon luomisessa, mutta se ei kuitenkaan oikeasti ole pakollinen. Tämä on vanhasta verkkosovelluksesta peräisin oleva tunnettu ongelma.

## <a name="for-an-appointment-when-i-choose-the-option-to-save-as-draft-it-doesnt-show-that-the-appointment-has-been-saved-as-a-draft"></a>Kun valitsen tapaamisen kohdalta *Tallenna luonnoksena*, tapaaminen ei näytä luonnokselta.

Kun tallennat tapaamisen luonnoksena vanhassa verkkosovelluksessa, otsikossa ei lue **[LUONNOS]** merkkinä luonnoksena tallentamisesta.

## <a name="can-i-add-activities-to-read-only-records"></a>Voiko vain luku -muotoisiin tietueisiin lisätä toimintoja?

Kyllä. Voit lisätä vain luku -muotoisiin entiteetteihin toimintoja, kuten muistiinpanoja, puheluja tai tehtäviä. 

## <a name="are-html-tags-supported-in-notes"></a>Tukevatko **muistiinpanot** HTML-tunnisteita?

Ei. Tunnisteille tai entiteeteille luotavat muistiinpanot eivät tue HTML-tunnisteita. Jos esimerkiksi lisäät muistiinpanokenttään <TAG> </TAG>, se näkyy muodossa <TAG_XXX="XX"> </TAG>.

## <a name="how-can-i-improve-performance-on-timeline-wall"></a>Miten voin parantaa aikajanaseinän suorituskykyä?

Aikajanaseinän suorituskykyä voi parantaa optimoimalla tietyn entiteettitietueen palauttamien tietojen määrää. 

1.  Voit määrittää entiteettilomakkeet näyttämään vain käytössä olevat toiminnot.  Tämä voidaan tehdä lomaketasolla niin, että vain hyödylliset toiminnot näytetään.  Jos et esimerkiksi käytä tapauksissa tehtäviä, voit määrittää aikajanaseinän tapauksen lomakkeen kautta niin, ettei tehtäviä näytetä.
2.  Pienennä aikajanaseinän oletusarvoisesti näyttämien tietueiden lukumäärää.  Seinä on oletusarvoisesti määritetty näyttämään 10 tietuetta. Yli 10 tietueen näyttäminen saattaa aiheuttaa suorituskykyongelmia.  Oletusarvon ylittämistä ei suositella. 

## <a name="activity-wall-is-not-supported-in-print-preview"></a>Tulostuksen esikatselu ei tue toimintoseinää.

Kun valitset Dynamics 365:stä **Tulostuksen esikatselu**, **Aikatauluseinä**-vaihtoehtoa ei näy käytettävissä olevien vaihtoehtojen luettelossa. **Muistiinpanot** näkyvät, mutta tehtävät ja sähköpostit eivät.





