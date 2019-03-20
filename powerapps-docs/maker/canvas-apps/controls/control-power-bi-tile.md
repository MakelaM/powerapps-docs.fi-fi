---
title: 'Power BI -ruudun ohjausobjekti: viitetietoja | Microsoft Docs'
description: Tietoja Power BI -ruudun ohjausobjektista, kuten ominaisuudet ja esimerkkejä
author: fikaradz
manager: kvivek
ms.service: powerapps
ms.topic: reference
ms.custom: canvas
ms.reviewer: anneta
ms.date: 07/07/2016
ms.author: fikaradz
search.audienceType:
- maker
search.app:
- PowerApps
ms.openlocfilehash: 82a7089ec14753a70d52d09024d1df527dbeb866
ms.sourcegitcommit: a06e3137e3cb36414f0d61825bbc687487ea6f8c
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 03/06/2019
ms.locfileid: "57804259"
---
# <a name="power-bi-tile-control-in-powerapps"></a>Power BI -ruudun ohjausobjekti PowerAppsissa

Ohjausobjekti, joka näyttää [Power BI](https://powerbi.microsoft.com) -ruudun sovelluksessa.

Eikö sinulla ole Power BI? [Rekisteröidy](https://docs.microsoft.com/power-bi/service-self-service-signup-for-power-bi).

## <a name="description"></a>Kuvaus

Hyödynnä olemassa olevaa tietojen analysointia ja raportointia näyttämällä **[Power BI -ruutuja](https://docs.microsoft.com/power-bi/service-dashboard-tiles)** sovelluksissasi. Määritä näytettävä ruutu asettamalla sen **Työtila**-, **Koontinäyttö**- ja **Ruutu**-ominaisuudet asetuspaneelin **Tiedot**-välilehdessä.

## <a name="sharing-and-security"></a>Jakaminen ja suojaus

Kun jaat sovelluksen, jossa on Power BI -sisältöä, sinun on jaettava sovelluksen itsensä lisäksi myös [koontinäyttö](https://docs.microsoft.com/power-bi/service-how-to-collaborate-distribute-dashboards-reports), josta ruutu saadaan. Muutoin Power BI -sisältö ei tule näkyviin niillekään käyttäjille, jotka avaavat sovelluksen. Sovellukset, joissa on Power BI -sisältöä, noudattavat kyseisen sisällön käyttöoikeuksia.

## <a name="performance"></a>Suorituskyky

Yli kolmen Power BI -ruudun lataamista sovellukseen yhtä aikaa ei suositella. Voit hallita ruutujen lataamista ja poistamista muistista määrittämällä **LoadPowerBIContent**-ominaisuuden.

## <a name="pass-a-parameter"></a>Välittää parametri

Välittämällä yksittäinen parametri sovelluksesta, voit suodattaa tulokset, jotka näkyvät Power BI-ruudun. Vain merkkijonoarvoja ja equals-operaattoria, ja suodattimen eivät ehkä toimi taulukon tai sarakkeen nimessä on välilyöntejä.

Voit välittää yhden suodattimen arvon muokkaamalla arvo **TileURL** ominaisuutta, joka noudattaa seuraavaa syntaksia:

```"https://app.powerbi.com/embed?dashboardId=<DashboardID>&tileId=<TileID>&config=<SomeHash>" ```

Arvoon Liitä seuraavaa syntaksia:

```&$filter=<TableName>/<ColumnName> eq "<Value>" ```

Parametrin suodattaa raportin tietojoukon arvo Jos ruutu on peräisin.

## <a name="key-properties"></a>Tärkeimmät ominaisuudet

**Työtila** – Power BI -työtila, josta ruutu on peräisin.

**Koontinäyttö** – Power BI -koontinäyttö, josta ruutu on peräisin.

**Ruutu** – Näytettävän Power BI -ruudun nimi.

**LoadPowerBIContent** – Kun asetuksena on tosi, Power BI -sisältö ladataan ja näytetään. Kun arvo on epätosi, Power BI -sisältö poistetaan, mikä vapauttaa muistia ja optimoi suorituskyvyn.

## <a name="additional-properties"></a>Lisäominaisuudet

**[BorderColor](properties-color-border.md)** – Ohjausobjektin reunan väri.

**[BorderStyle](properties-color-border.md)** – Onko ohjausobjektin reuna **yhtenäinen**, **katkoviiva**, **pisteviiva** vai **ei mitään**.

**[BorderThickness](properties-color-border.md)** – Ohjausobjektin reunan paksuus.

**[DisplayMode](properties-core.md)** – Onko käyttäjällä oikeus muokata (**Muokkaa**) vai vain tarkastella tietoja (**Näytä**), vai onko ominaisuus poistettu käytöstä (**Ei käytössä**).

**[Height](properties-size-location.md)** – Ohjausobjektin ylä- ja alareunan välinen etäisyys.

**[OnSelect](properties-core.md)** – Miten sovellus reagoi, kun käyttäjä napauttaa tai napsauttaa ohjausobjektia. Ruutuun liittyvä Power BI -raportti avautuu oletusarvoisesti.

**TileUrl** – URL-osoite, jota käyttämällä ruutu pyydetään Power BI -palvelusta. Voit välittää yksittäisen parametrin Power BI -ruutuun liittämällä parametrin URL-osoitteeseen (Esimerkki: & "&$filter=Town/Province eq '" & ListBox1.Selected.Abbr & "'"). Voit käyttää vain parametrissa vain yhtä suuri kuin -operaattoria.

**[Visible](properties-core.md)** – Ilmaisee, onko ohjausobjekti näkyvissä vai piilossa.

**[Leveys](properties-size-location.md)** – Ohjausobjektin vasemman ja oikean reunan välinen etäisyys.

**[X](properties-size-location.md)** – Ohjausobjektin vasemman reunan ja pääsäilön (näytön, jos pääsäilöä ei ole) vasemman reunan välinen etäisyys.

**[Y](properties-size-location.md)** – Ohjausobjektin yläreunan ja pääsäilön yläreunan välinen etäisyys (tai näytön, jos pääsäilöä ei ole).

## <a name="example"></a>Esimerkki

1. Avaa **Lisää**-välilehdessä **Ohjausobjektit**-valikko ja lisää sitten **Power BI -ruutu** -ohjausobjekti.

    Etkö tiedä, miten [ohjausobjekti lisätään ja määritetään](../add-configure-controls.md)?

2. Valitse **Tiedot**-välilehden asetuspaneelissa **Työtila**-asetukseksi **Oma työtila**.

3. Valitse jokin koontinäyttö koontinäyttöjen luettelossa ja valitse sitten ruutu ruutujen luettelossa.

    Ohjausobjekti muodostaa Power BI -ruudun.

## <a name="accessibility-guidelines"></a>Helppokäyttötoimintojen ohjeet

**Power BI-ruutu** on vain säilö Power BI -sisällölle. Opi luomaan helppokäyttöistä sisältöä näiden [Power BI -helppokäyttötoimintojen vinkkien](https://docs.microsoft.com/power-bi/desktop-accessibility) avulla.

Jos Power BI -sisällössä ei ole otsikkoa, voit lisätä otsikon **[Selite](control-text-box.md)**-ohjausobjektin avulla näytönlukuohjelmien tukea varten. Otsikko voidaan sijoittaa välittömästi ennen Power BI -ruutua.
