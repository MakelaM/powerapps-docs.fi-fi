---
title: Dynamics 365 -sovelluksen käyttöönotto Outlookissa | MicrosoftDocs
ms.custom: ''
ms.date: 2017-04-20
ms.reviewer: ''
ms.service: powerapps
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: get-started-article
applies_to:
- Dynamics 365 (online)
ms.assetid: 09736e14-e744-48ca-a755-1b05bb55340e
caps.latest.revision: 39
author: jimholtz
ms.author: jimholtz
manager: brycho
ms.openlocfilehash: d75ec08a1d4d594136ca3339daa819cf89ee910a
ms.sourcegitcommit: 982cab99d84663656a8f73d48c6fae03e7517321
ms.translationtype: MT
ms.contentlocale: fi-FI
ms.lasthandoff: 06/28/2019
ms.locfileid: "67456795"
---
# <a name="deploy-dynamics-365-app-for-outlook"></a>Dynamics 365 -sovelluksen käyttöönotto Outlookissa
[!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] -sovelluksen avulla käyttäjät voivat hyödyntää [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]:n ominaisuuksia käyttäessään [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]ia työpöydällä, verkossa tai tabletissa. Voit esimerkiksi tarkastella sähköpostiviestiin tai tapaamisen vastaanottajiin liittyviä tietoja tai yhdistää [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-sähköpostiviestin tai -tapaamisen [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] -tietueeseen (esimerkiksi mahdollisuus, tili tai tapaus). Jos haluat lisätietoja siitä, mitä mahdollisuuksia [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] sisältää, tutustu ohjeeseen [Dynamics 365 -sovellus Outlookille -käyttöopas](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
> [!IMPORTANT]
>  [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] ei ole sama kuin [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]. [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] alkaen [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] yhdessä [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] kanssa on suositeltavin tapa integroida [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]in kanssa. **Huomaa, että seurantatoimintoja ei tueta, kun sama käyttäjä käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovellusta ja [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]ia yhdessä.** Lisätietoja [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)] -apuohjelmasta löytyy ohjeesta [Dynamics 365 for Outlook -käyttöopas](http://go.microsoft.com/fwlink/p/?LinkID=524751).  
>   
>  [Delegoidut käyttäjät](https://support.office.com/article/Allow-someone-else-to-manage-your-mail-and-calendar-9684B670-7588-4EEA-8717-9E5799047540) eivät voi käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovellusta sähköpostiviestien seuraamiseen. Suosittelemme, että käytät [kansiotason seurantaa tai automaattista seurantaa](https://www.microsoft.com/en-us/dynamics/crm-customer-center/overview-of-tracking-records-in-dynamics-365-for-outlook.aspx), jos olet delegoitu käyttäjä.  
  
<a name="BKMK_Compare"></a>   
## <a name="comparing-dynamics-365-app-for-outlook-with-dynamics-365-for-outlook"></a>Vertailu: Dynamics 365 -sovellus Outlookille ja Dynamics 365 for Outlook  
 Seuraavassa taulukossa verrataan [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovelluksen ominaisuuksia [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]in kanssa (tunnetaan myös nimellä [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-asiakasohjelma tai -apuohjelma) [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] käyttöönotosta alkaen.  
  
||||  
|-|-|-|  
|**Ominaisuus**|**[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]**|**[!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]**|  
|Seuraa ja määritä liittyväksi sähköpostin kanssa|Kyllä|Kyllä|  
|Seuraa ja määritä liittyväksi tapaamisten kanssa|Kyllä|Kyllä|  
|Seuraa ja määritä liittyväksi yhteystietojen kanssa|Kyllä|Kyllä|  
|Seuraa ja määritä liittyväksi tehtävien kanssa|Ei|Kyllä|  
|Yhden napsautuksen aseta liittyy|Kyllä|Ei|  
|Näytä vastaanottajien yhteenveto|Kyllä|Ei|  
|Näyttää liittyvän tietueyhteenvedon sähköpostiviestissä/tapaamisessa|Kyllä|Ei|  
|Toimii [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -sovelluksen kanssa|Kyllä|Ei|  
|Toimii [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-työpöytäsovelluksen kanssa|Kyllä|Kyllä|  
|Toimii [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for Macin kanssa|Kyllä|Ei|  
|Toimii puhelimissa|Kyllä|Ei|  
|Avaa ja luo [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] -tietue suoraan|Kyllä|Kyllä|  
|Käytä mukautettuja lomakkeita ja liiketoimintalogiikkaa|Kyllä|Kyllä|  
|Työskentele offline-tilassa|Ei|Kyllä|  
|Käytä sähköpostimalleja|Kyllä|Kyllä|  
|Käytä myyntimateriaalia|Kyllä|Kyllä|  
|Käytä tietoartikkeleja|Kyllä|Kyllä|  
|Mahdollisuus valvoa sähköpostiviestejä lähettämisen jälkeen|Kyllä|Ei|  
|Lajittele, suodata, muotoile, ryhmittele ja luokittele näkymiä|Ei|Kyllä|  
|Luo Wordin yhdistämistoiminto -tiedostoja|Ei|Kyllä|  
|Hallinnoi kentän synkronointia|Ei|Kyllä|  
  
<a name="BKMK_Requirements"></a>   
## <a name="requirements"></a>Vaatimukset  
 Tarvitset seuraavat ominaisuudet [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovelluksen käyttämiseen:  
  
-   [!INCLUDE[pn_crm_online_2016_update](../includes/pn-crm-online-2016-update.md)] tai [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)]  
  
-   Saapuvien sähköpostiviestien synkronointi palvelinpuolen synkronoinnin avulla. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)][Sähköpostiviestien, tapaamisten, yhteystietojen ja tehtävien palvelinpuolen synkronoinnin määrittäminen](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)  
  
-   Alla kuvatut vaaditut oikeudet  
  
> [!NOTE]
>  [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)] -ominaisuuksien tuetut määritykset ja vaatimukset on lueteltu ohjeistuksessa. Jos et löydä jotain tiettyä määritystä ohjeistuksesta, sitä ei tueta.  
  
### <a name="required-privileges"></a>Tarvittavat oikeudet  
 [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] tarjoaa käyttöoikeuden [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovellukseen **Käytä Dynamics 365 -sovellusta Outlookissa** -oikeuden kautta. Jos käyttäjällä ei ole tätä oikeutta, hänelle näytetään seuraava virheilmoitus:  
  
> ”Sinulla ei ole oikeuksia käyttää tätä sovellusta. Ota yhteyttä järjestelmänvalvojaan ja päivitä asetuksesi.”  
  
 Käyttäjillä on myös oltava luku- ja kirjoitusoikeudet seuraaviin entiteetteihin.  
  
 Liiketoiminnan hallinta -välilehti:  
  
-   **Postilaatikko**  
  
 Mukauttaminen-välilehti:  
  
-   **Entiteetti**  
  
-   **Kenttä**  
  
-   **Suhde**  
  
-   **Järjestelmäsovelluksen metatiedot**  
  
-   **Järjestelmälomake**  
  
-   **Käyttäjän sovelluksen metatiedot**  
  
-   **Näkymä**  
  
##### <a name="set-the-privileges-for-a-security-role"></a>Käyttöoikeusroolin oikeuksien määrittäminen  
  
1.  [!INCLUDE[proc_settings_security](../includes/proc-settings-security.md)]  
  
2.  Napsauta **Avaa käyttöoikeusroolit**.  
  
3.  Valitse käyttöoikeusrooli ja napsauta sitten **Liiketoiminnan hallinta** -välilehteä.  
  
4.  Tarkista **Entiteetti**-osiossa **Postilaatikon** käyttöoikeusasetukset. Käyttöoikeusroolin kohdalla tulisi lukea Käyttäjä tai sitä korkea-arvoisempi asetus.  
  
5.  Varmista **Tietosuojaan liittyvät oikeudet** -osiossa, että **Käytä Dynamics 365 -sovellusta Outlookissa** -kohdan arvoksi on asetettu **Organisaatio**. Jos ei, napsauta **Käytä Dynamics 365 -sovellusta Outlookissa** -kohtaa.  
  
### <a name="supported-configurations-with-microsoft-exchange"></a>Microsoft Exchangessa tuetut kokoonpanot  
 [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] jälkeen voit käyttää sovellusta minkä tahansa yhdistelmän kanssa, johon sisältyy seuraavat: [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] tai [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)] ja [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)] tai [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (paikallinen). Tähän sisältyy myös yhdistelmämääritykset. Tämä tarkoittaa sitä, että [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] toimii kaikilla seuraavilla määrityksillä:  
  
|||  
|-|-|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (paikallinen)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (paikallinen)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
  
> [!NOTE]
>  Jos käytät [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)] -sovellusta, sinun tulee todentaa itsesi Internet-käytön todennuksella alla olevan ohjeen mukaisesti.  
  
### <a name="supported-browsers-for-outlook-on-the-web"></a>Outlook verkossa -palvelun tukemat selaimet  
 Seuraavat selaimet tukevat [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovelluksen käyttämistä [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -palvelun kanssa:  
  
-   [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)] tai [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)]  
  
     Seuraavaa määritystä tuetaan:  
  
    -   Suojattu tila on otettu käyttöön **Internet**-suojausvyöhykkeessä. Suojatun tilan käyttöönotto: siirry Internet Explorer 10:ssä tai 11:ssä kohtaan **Työkalut** > **Internet-asetukset** > **Suojaus-välilehti** > **Internet**.  
  
    -   Suojattu tila on otettu käyttöön **Paikallisen lähiverkon** suojausvyöhykkeessä. Suojatun tilan käyttöönotto: siirry Internet Explorer 10:ssä tai 11:ssä kohtaan **Työkalut** > **Internet-asetukset** > **Suojaus-välilehti** > **Paikallinen Internet**.  
  
    -   [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)] -URL-osoitteesi löytyy **Paikallisen lähiverkon** suojausvyöhykkeen luotettujen sivustojen luettelosta. Siirry Internet Explorer 10:ssä tai 11:ssä kohtaan **Työkalut** > **Internet-asetukset** > **Suojaus-välilehti** > **Paikallinen lähiverkko**  >  **Sivustot** > **Lisäasetukset**.  
  
-   [!INCLUDE[tn_Google_Chrome](../includes/tn-google-chrome.md)] (uusin versio) [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]-käyttöjärjestelmässä  
  
-   [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] (uusin versio) [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]-käyttöjärjestelmässä  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_Safari](../includes/tn-safari.md)] (versiot 9 ja 10) Mac-tietokoneessa tai OSX--käyttöjärjestelmässä  
  
### <a name="supported-operating-systems-for-outlook-on-the-desktop"></a>Outlookin työpöytäsovelluksen tukemat käyttöjärjestelmät  
 Voit käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovellusta seuraavien [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]in työpöytäsovellusversioiden kanssa:  
  
-   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2013 ja [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016.  
  
-   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for Mac*.  
  
     *[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)]in 15.0.847.32-versio tai uudempi vaaditaan.  
  
### <a name="supported-mobile-devices"></a>Tuetut mobiililaitteet  
 Voit käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovellusta [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -palvelun kanssa seuraavien puhelimien ja käyttöjärjestelmien mobiiliselaimissa:  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_iphone](../includes/tn-iphone.md)] -laitteissa, joiden käyttöjärjestelmäversio on iOS 8, 9 tai 10.  
  
-   [!INCLUDE[tn_android](../includes/tn-android.md)]-puhelimissa, joihin on asennettu [!INCLUDE[tn_android](../includes/tn-android.md)] 4.4 (KitKat) tai 5.0 (Lollipop), 6 (Marshmallow) tai 7 (Nougat).  
  
-   [!INCLUDE[pn_windows_phone](../includes/pn-windows-phone.md)] -laitteissa, joihin on asennettu [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)] tai [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)].  
  
### <a name="supported-clients-per-feature"></a>Tuetut ominaisuudet sovellusta kohden  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovelluksen tukemat ominaisuudet riippuvat käytössäsi olevasta sovelluksesta. Seuraavassa taulukossa on lueteltu jokaisen sovelluksen/[!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] ja [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)] -määrityksen tukemat ominaisuudet.  
  
 ![Sovellukset, joita Dynamics 365 -sovellus Outlookille -sovelluksen ominaisuudet tukevat](media/clients-supported-for-each-dynamics-365-app-for-outlook-feature.png "Sovellukset, joita Dynamics 365 -sovellus Outlookille -sovelluksen ominaisuudet tukevat")  
  
 (1) [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] tukee seuraavia: [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)], [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)], [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 9, [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 10, [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] ja [!INCLUDE[tn_chrome](../includes/tn-chrome.md)].  
  
 (2) Mobiilimuotoinen [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -palvelu tukee seuraavia: [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)], [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)], [!INCLUDE[tn_ios](../includes/tn-ios.md)] 8, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 9, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 10, [!INCLUDE[tn_android](../includes/tn-android.md)] KitKat (4.4), [!INCLUDE[tn_android](../includes/tn-android.md)] Lollipop, [!INCLUDE[tn_android](../includes/tn-android.md)] Marshmallow ja [!INCLUDE[tn_android](../includes/tn-android.md)] Nougat.  
  
 (3)  Sähköpostien seuranta laatimistilassa ja tapaamisten seuranta edellyttää seuraavaa: [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2013 CU14 tai [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2016.  
  
 (4) Yhteystietojen seurantaa tuetaan vain seuraavissa: [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)]2016 CU3 ja [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.6741.1000 ja sitä uudemmat.  
  
 (5) Sähköpostimallien, tietämyksenhallinta-artikkelien ja myyntimateriaalin lisäämistä ei tueta mobiilimuotoisessa [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -palvelussa.  
  
 (6) Tuetaan vain [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.7426.1049 -versiossa ja sitä uudemmissa.  
  
 (7) Tuetaan vain 16.0.6741.1000-versiossa ja sitä uudemmissa.  
  
> [!NOTE]
>  Tabletteja ei tueta tällä hetkellä (tulossa sopimusvuoden 2017 aikana).  
  
 [Lue lisätietoja tuetuista asiakkaista tästä blogista: Dynamics 365 -sovellus Outlook-tukimatriisille](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)  
  
### <a name="supported-servers"></a>Tuetut palvelimet  
 [Office-apuohjelmat tarvitsevat jonkin seuraavista palvelimista](https://dev.office.com/docs/add-ins/overview/requirements-for-running-office-add-ins): [!INCLUDE[pn_Exchange_Server_2013_short](../includes/pn-exchange-server-2013-short.md)], [!INCLUDE[pn_exchange_server_2016_short](../includes/pn-exchange-server-2016-short.md)] tai [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)].  
  
### <a name="supported-languages"></a>Tuetut kielet  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] tukee seuraavia kieliä:  
  
||||  
|-|-|-|  
|bulgaria (Bulgaria) - 1026|hindi (Intia) - 1081|portugali (Portugali) - 2070|  
|kiina (Kiinan kansantasavalta) - 2052|unkari - 1038|romania - 1048|  
|kiina (Taiwan) - 1028|indonesia - 1057|venäjä - 1049|  
|kroatia (Kroatia) - 1050|italia - 1040|serbia - 2074|  
|tsekki (Tsekin tasavalta) - 1029|japani -1041|slovakki - 1051|  
|tanska - 1030|kazakki - 1087|sloveeni - 1060|  
|hollanti - 1043|korea - 1042|espanja - 3082|  
|englanti - 1033|latvia - 1062|ruotsi - 1053|  
|viro - 1061|liettua - 1063|thai - 1054|  
|suomi - 1035|malaiji - 1086|turkki - 1055|  
|ranska - 1036|norja - 1044|ukraina - 1058|  
|saksa - 1031|puola - 1045|vietnam - 1066|  
|kreikka - 1032|portugali (Brasilia) - 1046||  
  
<a name="BKMK_Deploy"></a>   
## <a name="deploy-dynamics-365-app-for-outlook"></a>Dynamics 365 -sovelluksen käyttöönotto Outlookissa  
 Kun olet määrittänyt [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] -ominaisuuden ja tarvittavat oikeudet, voit lähettää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -palvelun tietyille tai kaikille käyttäjille tai voit antaa käyttäjien asentaa sen itse aina tarvittaessa.  
  
> [!NOTE]
>  Jos sinulla on [!INCLUDE[pn_dyn_365_op](../includes/pn-dyn-365-op.md)], katso alla oleva osio:  [Dynamics 365:n käyttöönotto paikallisille käyttäjille](#BKMK_DeployOnprem)  
  
#### <a name="to-push-the-app-to-users"></a>Sovelluksen lähettäminen käyttäjille  
  
1.  Siirry kohtaan **Asetukset** >  **Dynamics 365 -sovellus Outlookille**.  
  
2.  Siirry **Dynamics 365 -sovellus Outlookille - käytön aloittaminen** -ruudussa **Lisää oikeutetuille käyttäjille** -kohdan alle (saatat joutua napsauttamaan kohtaa **Asetukset**, jos olet avannut tämän näytön toisen tai sitä seuraavan kerran) ja valitse **Lisää sovellus automaattisesti seuraaville [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]** -valintaruutu, jos haluat, että käyttäjät saavat sovelluksen automaattisesti. Jos käyttäjällä on tarvittavat oikeudet ja hänen sähköpostinsa synkronoidaan [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] -ominaisuuden kautta , sinun ei tarvitse tehdä enempää sovelluksen lähettämisen eteen. Esimerkiksi jos lisäät tarvittavat oikeudet myyjä-roolille ja määrität sitten tämän roolin uudelle käyttäjälle, hän saa sovelluksen automaattisesti.  
  
3.  Tee jokin seuraavista:  
  
    -   Jos haluat lähettää sovelluksen kaikille oikeutetuille käyttäjille, valitse **Lisää sovellus kaikille oikeutetuille käyttäjille**.  
  
    -   Jos haluat lähettää sovelluksen tietyille käyttäjille, valitse kyseiset käyttäjät luettelosta ja napsauta sitten **Lisää sovellus Outlookiin**.  
  
    > [!TIP]
    >  Jos luettelossa näkyy, että käyttäjä on odotustilassa tai häntä ei ole lisätty, voit napsauttaa käyttäjän vieressä olevaa **Lisätietoja**-linkkiä saadaksesi lisää tietoa käyttäjän tilasta.  
  
4.  Kun olet valmis, valitse **Tallenna**.  
  
#### <a name="to-have-users-install-the-app-themselves"></a>Jos haluat, että käyttäjät asentavat sovelluksen itse  
  
1.  Käyttäjän tulee napsauttaa **Asetukset**-painiketta ![Asetukset-painike](media/mp-ua-r16-settings.png "Asetukset-painike") ja sitten kohtaa **Dynamics 365 -sovellukset**.  
  
2.  **Dynamics 365 -sovellukset** -ruudussa, **[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]** -kohdan alla, käyttäjän tulee napsauttaa kohtaa **Lisää sovellus kohteeseen [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]** .  
  
> [!NOTE]
>  Käyttäjät voivat myös itse poistaa apuohjelman tai poistaa apuohjelman käytöstä aina tarvittaessa. Lisätietoja löytyy kohdasta [Dynamics 365 -sovellus Outlookille - käyttöopas](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
<a name="BKMK_DeployOnprem"></a>   
## <a name="to-deploy-to-dynamics-365-on-premises-users"></a>Dynamics 365:n käyttöönotto paikallisille käyttäjille  
 Jos käytät Dynamics 365:tä paikallisesti, toimi seuraavasti.  
  
-   Määritä Dynamics 365 -palvelin Internet-käyttöä varten. Katso [Internet-käytön määrittäminen Microsoft Dynamics 365:lle](https://technet.microsoft.com/library/dn609803.aspx).  
  
-   Jos olet muodostamassa yhteyttä Exchangeen paikallisesti, määritä OAuth-palvelu ja rekisteröi asiakassovellukset. Katso [Windows Server 2012 R2:n määrittäminen Dynamics 365 -sovelluksille, jotka käyttävät OAuth-palvelua](https://technet.microsoft.com/library/hh699726.aspx).  
  
<a name="BKMK_Troubleshoot"></a>   
## <a name="troubleshooting-installation-problems"></a>Asennusongelmien vianmääritys  
 Jos sinulla tai käyttäjälläsi on ongelmia [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovelluksen asentamisen kanssa, syynä voi olla se, että käyttäjän [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postilaatikko liitetty toiseen [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] -organisaation. [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postilaatikko (sähköpostiosoite) voi synkronoida tapaamisia, yhteystietoja ja tehtäviä vain yhden organisaation kanssa, ja käyttäjä, joka kuuluu kyseiseen organisaation, voi synkronoida tapaamisia, yhteystietoja ja tehtäviä vain yhden [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postilaatikon kanssa.  Voit korvata [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]en tallennetut asetukset, jos haluat muuttaa ensisijaisesti synkronoitavan organisaation. Lisätietoja löytyy seuraavasta [KB-artikkelista](https://support.microsoft.com/en-gb/help/3211627/incomingemailrejected-error-when-attempting-to-install-dynamics-365-app-for-outlook).  
  
<a name="BKMK_Explore"></a>   
## <a name="explore-the-users-guide-and-train-your-users"></a>Tutustu käyttöoppaaseen ja kouluta käyttäjäsi  
 Jos haluat oppia käyttämään [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovellusta, [tutustu Dynamics 365 -sovellus Outlookille - käyttöoppaaseen](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
 ![Dynamics 365 -sovellus Outlookille - käyttöopassivu](media/dynamics-365-app-for-outlook-user-s-guide-page.png "Dynamics 365 -sovellus Outlookille - käyttöopassivu")  
  
## <a name="see-also"></a>Katso myös  
 [Dynamics 365 -sovellus Outlookille - käyttöopas](http://go.microsoft.com/fwlink/p/?LinkID=613099)   
 [Lue lisätietoja tuetuista asiakkaista tästä blogista: Dynamics 365 -sovellus Outlook-tukimatriisille](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)   
 [Sähköpostiviestien, tapaamisten, yhteystietojen ja tehtävien palvelinpuolen synkronoinnin määrittäminen](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)   
 [Käyttäjien, käyttöoikeuksien ja käyttöoikeusroolien lisääminen](https://msdn.microsoft.com/23612155-f92d-4871-a109-186419d5c19d)   
 [Yhteentoimivuusominaisuuksien lisääminen Microsoft Dynamics 365 Onlineen](../DocSets/CRMIGv9_Admin/Toc/Add%20interoperation%20features%20to%20Microsoft%20Dynamics%20365%20\(online\).md)