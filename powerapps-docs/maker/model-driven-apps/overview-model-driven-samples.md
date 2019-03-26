---
title: Mallipohjaiset esimerkkisovellukset
description: 'Tietoja mallipohjaisten esimerkkisovellusten hakemisesta, mukauttamisesta ja poistamisesta.'
documentationcenter: na
author: mr-dang-msft
manager: kvivek
ms.service: powerapps
ms.devlang: na
ms.topic: conceptual
ms.component: model
ms.date: 03/08/2018
ms.author: brdang
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---

# <a name="model-driven-sample-apps"></a>Mallipohjaiset esimerkkisovellukset

Käytä sivustossa [powerapps.com](https://powerapps.com) esimerkkisovellusta, kun haluat tutkia suunnittelumahdollisuuksia ja etsiä käsitteitä, jotka haluat ottaa käyttöön omien sovellusten kehittämisessä. Jokaisessa esimerkkisovelluksessa käytetään kuvitteellisia tietoja, joiden avulla esitetään tosielämän skenaario. 

Varmista, että tarkistat lisätiedot jokaisen esimerkkisovelluksen dokumentaatiosta. 

![Rahankeräyksen esimerkkisovellus](media/overview-model-driven-samples/fundraiser-app1.png)


## <a name="get-sample-apps"></a>Esimerkkisovellusten hakeminen

Mallipohjaiset esimerkkisovellukset on ensin valmisteltava Common Data Service -tietokannassa, ennen kuin niitä voidaan toistaa tai muokata. Luo ensin kokeiluympäristö ja -tietokanta ja varmista, että **Sisällytä esimerkkisovellukset ja -tiedot** on valittuna.

![Tietokannan luominen](media/overview-model-driven-samples/create-database1.png)


> [!IMPORTANT]
> Tämä vaihtoehto asentaa tietokantaan kaikki käytettävissä olevat esimerkkisovellukset. Esimerkkisovelluksia käytetään koulutuksessa ja esittelyssä. Niiden asentamista tuotantotietokantoihin ei suositella. 

## <a name="customize-a-sample-app"></a>Esimerkkisovelluksen mukauttaminen

1. [Powerapps.comiin](https://powerapps.com) kirjautuminen  

    

2. Siirrä osoitin **Luo**-sivulla näytesovelluksen päälle ja valitse **Luo tämä sovellus**.

![Näytemallisovellus](media/overview-model-driven-samples/model-driven-create-page-sample.png)

3. Näyttöön avautuu sovellusten suunnitteluohjelma, jossa on useita vaihtoehtoja sovelluksen mukauttamista varten. 
4. Saat lisätietoja mukauttamisasetuksista, kun valitset portaalin vasemmalla olevassa siirtymistoiminnossa **Lisäasetukset**.

## <a name="remove-sample-apps-and-data"></a>Esimerkkisovellusten ja -tietojen poistaminen 
- Esimerkkisovelluksen poistaminen edellyttää, että vastaava [isännöity ratkaisu](https://docs.microsoft.com/dynamics365/customer-engagement/developer/uninstall-delete-solution) poistetaan. 
- Jos ratkaisu poistetaan, myös sovelluksen mukautettuja entiteettejä koskevat esimerkkitiedot poistetaan.
- Jos esimerkkisovellukseen on tehty mukautuksia, sillä voi olla [riippuvuuksia](https://docs.microsoft.com/dynamics365/customer-engagement/developer/dependency-tracking-solution-components). Ne on poistettava ennen sovelluksen poistamista.

### <a name="steps"></a>Osavaiheet.
1. Kirjaudu sisään [PowerAppsin hallintaportaaliin](https://admin.powerapps.com).

2. Valitse ympäristö.

3. Valitse **Dynamics 365 Administration Center** 

    ![Dynamics 365:n hallintakeskus](media/overview-model-driven-samples/admin-center.png)

4. Valitse tietokanta luettelosta ja valitse sitten **AVAA**.

    ![Tietokannan valitseminen](media/overview-model-driven-samples/select-database.png)

5. Siirry kohtaan **Asetukset/Ratkaisut**.

6. Valitse ratkaisu poistettavalle sovellukselle ja valitse sitten **Poista**.

    ![Ratkaisun poistaminen](media/overview-model-driven-samples/delete-solution.png)

*Vaihtoehtoisesti voit siirtyä ratkaisuluetteloon valitsemalla tekijän portaalissa **Lisäasetukset** ja poistamalla URL-osoitteesta kohdan .dynamics.com/ jälkeiset merkit*

> [!IMPORTANT]
> Älä poista muita järjestelmäratkaisuja, ellet ole varma poiston vaikutuksesta.

## <a name="install-or-uninstall-sample-data"></a>Esimerkkitietojen asentaminen tai asennuksen poistaminen
1. Noudata yllä mainittuja vaiheita 1–4.
2. Siirry kohtaan **Aseukset / Tietojen hallinta / Esimerkkitiedot**.
3. Jos esimerkkitiedot on asennettu, poistovalinta on käytettävissä. Muussa tapauksessa käytettävissä on asennusvalinta. 

    ![esimerkkitietojen poistaminen](media/overview-model-driven-samples/remove-sample-data.png)




