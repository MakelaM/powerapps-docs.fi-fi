---
title: Yhteysroolien määrittäminen | MicrosoftDocs
ms.custom: ''
ms.date: 05/27/2018
ms.reviewer: ''
ms.service: crm-online
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
applies_to:
  - Dynamics 365 (online)
  - Dynamics 365 Version 9.x
  - PowerApps
ms.author: matp
manager: brycho
search.audienceType:
  - maker
search.app:
  - PowerApps
  - D365CE
---
# <a name="configure-connection-roles"></a>Yhteysroolien määrittäminen

Common Data Service sovelluksille -ratkaisun avulla voit määrittää **yhteydet** entiteettitietueiden välille ilman entiteettisuhteen luomista. Mallipohjaisissa sovelluksissa tietueiden välille voidaan muodostaa nimetty linkki. Näin muodostetaan vähemmän muodollinen suhde, joka ei anna aihetta todellisen entiteettisuhteen luomiselle. Esimerkkejä ovat *ystävä*, *sisarus*, *puoliso*, *osallistuja* ja *sidosryhmän jäsen*. Jotkin yhteydet voivat olla myös kaksisuuntaisia, kuten *lapsi* ja *vanhempi*, *aviomies* ja *aviovaimo* ja *lääkäri* ja *potilas*.

Kun kahden tietueen välille määritetään yhteys, sille voidaan lisätä myös kuvaus ja lisätietoja, kuten suhteen alku- ja loppupäivämäärät. Lisätietoja: [Yhteyksien luominen tietueiden välisten suhteiden määrittämistä ja tarkastelemista varten](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)

Kuka tahansa, jolla on **Yhteysrooli**-entiteetin kirjoitusoikeus, voi määrittää, mitkä yhteydet ovat henkilöiden käytettävissä.

## <a name="view-connection-roles"></a>Yhteysroolien tarkasteleminen

CDS sovelluksille-ratkaisuun on jo määritetty useita vakioyhteyksiä. Voit tarkastella niitä siirtymällä asetusten alueeseen. 

### <a name="navigate-to-the-settings-area"></a>Asetusten alueeseen siirtyminen

1. Kun tarkastelet mallipohjaista sovellusta, muokkaa URL-osoitetta ja poista kaikki kohdan `dynamics.com` jälkeiset merkit. Päivitä sitten sivu.
1. Siirry kohtaan **Asetukset** > **Yritys** > **Yrityksen hallinta** ja valitse **Yhteysroolit**.

![Yhteysroolit yrityksen hallinnan asetuksissa](media/navigate-settings-connection-roles.png)

Tässä näkymässä ovat kaikki tämän ympäristön käytettävissä olevat yhteysroolit. Voit muokata niitä täällä.

> [!NOTE]
> Jos haluat jakaa yhteysroolit ratkaisun kanssa, varmista, että ne sisältyvät jaettavaan ratkaisuun. Lisätietoja [Yhteysroolien lisääminen ratkaisuun](#add-connection-roles-to-a-solution)

## <a name="view-connection-roles-in-the-solution-explorer"></a>Tarkastele yhteysrooleja ratkaisunhallinnassa.

Koska yhteysroolit ovat *ratkaisukohtaisia*, eli ne voidaan sisällyttää ratkaisuun, voit lisätä yhteysrooleja myös jaettavaan ratkaisuun.

[!INCLUDE [cc_navigate-solution-from-powerapps-portal](../../includes/cc_navigate-solution-from-powerapps-portal.md)]

Suurin osa **Asetukset**-alueessa nähtävistä yhteysrooleista määritetään *sisäisiksi* **oletusratkaisuiksi** (joita ei pidä sekoittaa **Common Data Services -oletusratkaisuun**). Tämä sisäinen **oletusratkaisu** sisältää järjestelmän kaikki mukautukset. Voit tarkastella **oletusratkaisua** valitsemalla **Kaikki ratkaisut - sisäinen** -näkymän.

## <a name="add-connection-roles-to-a-solution"></a>Yhteysroolien lisääminen ratkaisuun

Yleensä sisäisen **oletusratkaisun** osien muokkausta ei suositella. Voit käyttää **Common Data Services -oletusratkaisussa** tai luomassasi ratkaisussa **Lisää aiemmin luotu** -komentoa, kun haluat tuoda oletusyhteysrooleja ratkaisuusi.

![Olemassa olevan yhteysroolin lisääminen](media/add-existing-connection-role.png)

Kun olet lisännyt ratkaisuun yhteysroolin, voit muokata sitä aina yhteysroolin ollessa näkyvillä.

## <a name="create-or-edit-connection-roles"></a>Luo tai muokkaa yhteysrooleja.

> [!IMPORTANT]
> Jos haluat jakaa ratkaisun, joka sisältää uusia yhteysrooleja, tai muutettuja olemassa olevia yhteysrooleja, lisää ne jaettavaan ratkaisuun. Uusien yhteysroolien muokkaaminen tai lisääminen **Asetukset**-alueella lisää yhteysroolit sisäiseen **oletusratkaisuun**. Ne sisällytetään jaettavaan ratkaisuun vasta, kun olet lisännyt ne ratkaisuun. Lisätietoja: [Yhteysroolien lisääminen ratkaisuun](#add-connection-roles-to-a-solution)

Valitse **Yhteysroolit**-luettelossa muokattava yhteysrooli.
Yhteysroolin määrittäminen sisältää kolme lomakkeessa selvästi erottuvaa vaihetta.

![Yhteysroolilomakkeen luominen](media/create-connection-role-form.png)

### <a name="describe-the-connection-role"></a>Yhteysroolin määrittäminen

Määritä seuraavat kentät:

|Kenttä|Kuvaus|
|--|--|
|**Nimi**|(Pakollinen) Yhteyttä kuvaileva teksti.|
|**Yhteysrooliluokka**|Yhteyden luokkaa kuvaileva ryhmä. Lisätietoja: [Yhteysroolin luokan arvot](#connection-role-category-values)|
|**Kuvaus**|Anna roolille määritys.|

#### <a name="connection-role-category-values"></a>Yhteysroolin luokan arvot

**Yhteysroolin luokan** oletusarvot ovat seuraavat:
- Yritys
- Perhe
- Yhteisöpalvelu
- Sales
- Muu
- Sidosryhmän jäsen
- MYYNTIRYHMÄ
- Palvelu

Voit lisätä uusia luokkia tai muokata olemassa olevia luokkia muokkaamalla **luokan** yleistä asetusjoukkoa. Lisätietoja: [Common Data Service sovelluksille -ratkaisun yleisten asetusjoukkojen luominen ja muokkaaminen (valintaluettelot)](create-edit-global-option-sets.md)

### <a name="select-record-types"></a>Tietuetyyppien valitseminen

Määritä, mitkä tietuetyypit ovat käytettävissä yhteyttä varten.

> [!NOTE]
> Vaikka **Kaikki** on valittuna oletusarvoisesti, varmista, että pohdit lisättävälle yhteysroolille sopivia tyyppejä.

### <a name="matching-connection-roles"></a>Toisiaan vastaavat yhteysroolit

Tässä valinnaisessa vaiheessa voit määrittää mitkä tahansa kaksisuuntaisesti kohdistettavat roolit. Tämä ei ole pakollinen vaihe. Yhteydet ovat kuitenkin merkityksellisempiä, jos vastavuoroiset yhteydet määritetään.

Käyttäjä voi esimerkiksi määrittää, että Glen on Maryn *ystävä*. Mutta tarkoittaako tämä sitä, että Mary on Glenin *ystävä*? Toivomme, että tarkoittaa. Mutta jos Glen on Maryn *isä*, se ei tarkoita sitä, että Mary olisi Glenin *isä*. Kaksisuuntaisuuden määrittäminen oikein vaatii tämän ylimääräisen vaiheen.

Kun käyttäjä määrittää yhteysroolin, jolla ei ole vastaavaa yhteysroolia, rooli näytetään vain kun yhteyttä tarkastellaan tietueessa, jossa yhteyttä käytetään. Kun roolia tarkastellaan yhteystietueessa, se on tyhjä, ellei vastaavaa roolia määritetä.

Määrityksille, kuten *ystävä*, *puoliso*, *työtoveri* tai *sisarus*, kannattaa delegoida vastaava rooli itselleen. Jos yhden vastaavuuden yhteysrooli on määritetty, yhden vastaavuuden yhteysroolia käytetään molemmissa suunnissa.

> [!IMPORTANT]
> Tallenna uusi yhteysrooli ilman tätä vastaavaa yhteysroolia, ennen kuin määrität vastaavan yhteysroolin itseensä.

Osa yhteysrooleista on jo määritetty niin, että niillä on vastaavat yhteysroolit. Määritetään *entisen työntekijän* vastaavuus *entiseen työnantajaan* ja päinvastoin. Tällainen yksi yhteen -vastaavuuden yhteysrooli on yleisin.

Voit määrittää useita vastaavia yhteysrooleja monimutkaisia suhteita kuvaamaan. Jos luot yhteysroolin, joka on esimerkiksi *Isä*, voit määrittää kaksi lisäroolia, esimerkiksi *Tytär* ja *Poika*, ja käyttää niitä molempia *Isä*-roolin vastaavina yhteysrooleina. Vastaavasti *Tytär*- ja *Poika*-yhteysroolit tulee määrittää vastaamaan *Isä*-roolia. Samoin myös *Äiti*-roolille tulee määrittää vastaavuudet *Tytär*- ja *Poika*-rooleille.

> [!TIP]
> Ennen kuin luot monimutkaisia yhteysroolijoukkoja, kannattaa varmistaa, ovat yksinkertaisemmat roolijoukot riittäviä. Esimerkiksi monimutkaisten yhteysroolien, kuten *Isä*, *Äiti*, *Poika* ja *Tytär*, sijaan voit käyttää yksinkertaisesti *Vanhempi*- ja *Lapsi*-rooleja.

Jos vastaavia yhteysrooleja on määritetty useita, yhteysroolit edustavat vain sallittuja kaksisuuntaisia rooleja. Ensimmäistä käytetään automaattisesti oletusarvona. Jos oletusarvo ei ole oikea, yhteyttä täytyy muokata manuaalisesti. Tällöin valitaan määritykselle sallittuja asetuksia.

### <a name="see-also"></a>Katso myös
<!-- This is in the basics guide. It needs to be migrated -->
[Tietueiden välisten suhteiden määrittäminen ja näyttäminen yhteyksiä luomalla](/dynamics365/customer-engagement/basics/create-connections-view-relationships-between-records)<br />
[Common Data Service sovelluksille -ratkaisun yleisten asetusjoukkojen luominen ja muokkaaminen (valintaluettelot)](create-edit-global-option-sets.md)<br />
[Entiteettien välisten suhteiden luominen ja muokkaaminen](create-edit-entity-relationships.md)


