---
title: Ilmoita dynaamisia muutoksia reaaliaikaisen alueiden kanssa pohjaan perustuvien sovellusten | Microsoft Docs
description: Ilmoita näytönlukuohjelmat dynaaminen muuttuu pohjaan perustuvat sovellukset-live-alueiden avulla
author: tahoon-ms
ms.service: powerapps
ms.topic: article
ms.custom: canvas
ms.date: 10/22/2018
ms.author: tahoon
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 9a886b1c585f4fc07efc29bc1166ce4aca5586b5
ms.sourcegitcommit: 4042388fa5e7ef50bc59f9e35df330613fea29ae
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 04/23/2019
ms.locfileid: "61549946"
---
# <a name="announce-dynamic-changes-with-live-regions-for-canvas-apps"></a>Ilmoita dynaamisia muutoksia pohjaan perustuvat sovellukset live-alueiden kanssa

Dynaamiset muutokset aiheuttaa haasteita visuaalisesti-oletusteemaa paremmin. Käyttäjät, joilla sovelluksen kautta Näytönlukuohjelman valjastetaan sovelluksen yksi osa. Jos muutoksen tapahtuu muualla, kyseiset käyttäjät eivät voi huomioon se.

Voit ratkaista tämän ongelman lisäämällä reaaliaikaisen alueita, jotka näytönlukuohjelmat seuraa. Jos sisältö muuttuu reaaliaikaisen alueella, näytönlukuohjelma ilmoittaa muutokset.

Reaaliaikainen alueiden pohjana mekanismi ovat [aria-live-alueiden](https://www.w3.org/TR/wai-aria-1.1/#dfn-live-region), joten saman ohjeet koskevat sekä.

## <a name="example-uses-of-live-regions"></a>Esimerkissä reaaliaikaisen alueiden

Reaaliaikainen alueiden avulla voit Ilmoita käyttäjille ilmaantuessa, esimerkiksi seuraavat:

* Vahvistusvirhe tapahtuu lomakkeen.
* Painikkeen käynnistämä toiminto onnistuu. Esimerkiksi käyttäjä voi valita painikkeen Lisää kohde kokoelmaan ja reaaliaikaisen alue näyttää viestin ”kohde lisätty”.
* Käyttäjän valita eri välilehdessä.
* Taustan ajastin päivittää uutiset.

## <a name="create-and-configure-a-live-region"></a>Luo ja määritä reaaliaikaisen alue

Voit määrittää vain **[nimen](controls/control-text-box.md)** ohjausobjektin reaaliaikaisen alue. Sen **Live** ominaisuus määrittää, minkä tyyppistä reaaliaikaisen alue on.

* **Käytöstä**: Reaaliaikainen alue. Näytönlukuohjelmat ilmoittavat ei muutoksia.
* **Käyttäjät huomioivaa**: Näytönlukuohjelmat ilmoittavat muutokset jälkeiset puhumalla. Käytä tätä arvoa ei-vakavia ilmoitukset, jotka eivät edellytä välitöntä huomiota.
* **Päättävämmin**: Näytönlukuohjelmat keskeyttää itsensä koskevista muutoksista heti. Käytä tätä kriittinen ilmoitukset, jotka edellyttävät välitöntä huomiota.

Jos reaaliaikainen alue tekstisisältö muuttuu, näytönlukuohjelmat ilmoittavat koko tekstisisältöä, ei vain muutettu osan. Jos arvo **[tekstin](controls/properties-core.md)** ominaisuuden arvo on tyhjä merkkijono **””** , ei näytönlukuohjelma mitään.

Toista viesti Tyhjennä tekstisisältö asetetaan **[tekstin](controls/properties-core.md)** ominaisuus tyhjäksi merkkijonoksi **””** ja määritä arvoksi viestiin uudelleen.

## <a name="best-practices"></a>Parhaat käytännöt

* Aina **[näkyvissä](controls/properties-core.md)** TRUE. Jotkin näytönlukuohjelmat ei tunnista reaaliaikainen alueita, joita poistetaan, ja uudelleen.
* Vältä arvon muuttaminen  **[Live](controls/properties-accessibility.md)** . Jotkin näytön lukijat ei tunnista, kun-live-alue on live ja päinvastoin.
* Aseta reaaliaikaisen alueen looginen sijainti sovelluksessa, vaikka se ei ole näkyvissä. Varmista, että sen sisältö ovat merkitseviä kontekstissa elementtien ennen ja jälkeen se. Käyttäjät voivat käyttää reaaliaikaista alue milloin tahansa kautta säännöllisesti siirtyminen käyttämiseen näytönlukuohjelmalla, ei vain, kun muutoksia tehdään.

## <a name="next-steps"></a>Seuraavat vaiheet

Lue, miten [näyttää sisällön vain näytönlukuohjelmat](accessible-apps-content-visibility.md) Jos reaaliaikaisen alueen olisi piilotettu tarjoaminen käyttäjiltä.