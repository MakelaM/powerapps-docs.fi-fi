---
title: Dynamics 365 App for Outlookin käyttöönotto | MicrosoftDocs
ms.custom: ''
ms.date: '2017-04-20'
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
---
# <a name="deploy-dynamics-365-app-for-outlook"></a>Dynamics 365 App for Outlookin käyttöönotto
Käyttäjät saavat [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)]-sovelluksen avulla tehokkaan [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]:n käyttöön samalla, kun käytössä on [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] pöytätietokoneessa, verkossa tai tabletissa. Voit esimerkiksi tarkastella sähköposteja tai tapaamisen osallistujia tai linkittää [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]-sähköpostin tai -tapaamisen [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] -tietueeseen, kuten mahdollisuuteen, tiliin tai palvelupyyntöön. Lisätietoja [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] -tarjouksista on kohdassa [Dynamics 365 App for Outlookin käyttöopas](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
> [!IMPORTANT]
>  [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] ei ole sama kuin [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]. [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] -versiosta lähtien [!INCLUDE[pn_ms_dyn_crm_app_for_outlook](../includes/pn-ms-dyn-crm-app-for-outlook.md)] on toiminut [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)] -sovelluksen kanssa. Tämä on suosittelemamme tapa integroida [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)] ja [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]. **Huomaa, että aktiviteettien seuraamista ei tueta, kun sama käyttäjä käyttää yhdessä [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]ia ja [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]ia.** Lisätietoja [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)] apuohjelmasta on [Dynamics 365 for Outlook -käyttöoppaassa](http://go.microsoft.com/fwlink/p/?LinkID=524751).  
>   
>  [Delegoidut käyttäjät](https://support.office.com/article/Allow-someone-else-to-manage-your-mail-and-calendar-9684B670-7588-4EEA-8717-9E5799047540) eivät voi käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]ia sähköpostiviestien seuraamiseen. Delegoitujen käyttäjien kannattaa käyttää [kansiotason seurantaa tai automaattista seurantaa](https://www.microsoft.com/en-us/dynamics/crm-customer-center/overview-of-tracking-records-in-dynamics-365-for-outlook.aspx).  
  
<a name="BKMK_Compare"></a>   
## <a name="comparing-dynamics-365-app-for-outlook-with-dynamics-365-for-outlook"></a>Dynamics 365 App for Outlookin ja Dynamics 365 for Outlookin vertailu  
 Seuraavassa taulukossa vertaillaan [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]in ominaisuuksia [!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]iin (jota kutsutaan myös [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]in asiakasohjelmaksi tai apuohjelmaksi) versiosta [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] alkaen.  
  
||||  
|-|-|-|  
|**Ominaisuus**|**[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]**|**[!INCLUDE[pn_crm_for_outlook_short](../includes/pn-crm-for-outlook-short.md)]**|  
|Sähköpostin seuraaminen ja määrittäminen|Kyllä|Kyllä|  
|Tapaamisten seuraaminen ja määrittäminen|Kyllä|Kyllä|  
|Yhteyshenkilöiden seuraaminen ja määrittäminen|Kyllä|Kyllä|  
|Tehtävien seuraaminen ja määrittäminen|Ei|Kyllä|  
|Yhdellä napsautuksella|Kyllä|Ei|  
|Näyttää vastaanottajien yhteenvedon|Kyllä|Ei|  
|Näyttää liittyvän sähköpostin tai tapaamisen tietueen yhteenvedon|Kyllä|Ei|  
|Toimii yhdessä [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -sovelluksen kanssa|Kyllä|Ei|  
|Yhteensopiva [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]in työpöytäversion kanssa|Kyllä|Kyllä|  
|Yhteensopiva [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]in Mac-version kanssa|Kyllä|Ei|  
|Toimii puhelimissa|Kyllä|Ei|  
|[!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]-tietueen avaaminen ja luominen suoraan|Kyllä|Kyllä|  
|Käytä mukautettuja lomakkeita ja liiketoimintalogiikkaa|Kyllä|Kyllä|  
|Työskentele offline-tilassa|Ei|Kyllä|  
|Sähköpostimallien käyttö|Kyllä|Kyllä|  
|Myyntimateriaalin käyttö|Kyllä|Kyllä|  
|Tietoartikkelien käyttö|Kyllä|Kyllä|  
|Mahdollisuus seurata sähköposteja lähettämisen jälkeen|Kyllä|Ei|  
|Näkymien lajittelu, suodatus, ryhmittely ja luokittelu|Ei|Kyllä|  
|Wordin yhdistämisasiakirjojen luonti|Ei|Kyllä|  
|Hallitse kenttien synkronointia|Ei|Kyllä|  
  
<a name="BKMK_Requirements"></a>   
## <a name="requirements"></a>Vaatimukset  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -sovelluksen edellytykset:  
  
-   [!INCLUDE[pn_crm_online_2016_update](../includes/pn-crm-online-2016-update.md)] tai [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)]  
  
-   Tulevien sähköpostien synkronointi palvelinpään synkronoinnilla. [!INCLUDE[proc_more_information](../includes/proc-more-information.md)][Sähköpostiviestien, tapaamisten, yhteyshenkilöiden ja tehtävien palvelinpään synkronoinnin määrittäminen](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)  
  
-   Tarvittavat käyttöoikeudet seuraavan kohdan mukaisesti  
  
> [!NOTE]
>  [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)]:n toimintojen tuetut kokoonpanot ja vaatimukset kerrotaan tässä dokumentaatiossa. Jos kokoonpano ei sisälly dokumentaatioon, sitä ei tueta.  
  
### <a name="required-privileges"></a>Tarvittavat oikeudet  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] saadaan käyttöön [!INCLUDE[pn_microsoftcrm](../includes/pn-microsoftcrm.md)]:n **Käytä Dynamics 365 App for Outlook -sovellusta** -oikeudella. Jos käyttäjällä ei ole tätä oikeutta, näyttöön tulee seuraava virhe:  
  
> ”Sinulle ei ole annettu valtuuksia käyttää tätä sovellusta. Pyydä järjestelmänvalvojaasi päivittämään asetuksesi.”  
  
 Käyttäjillä on oltava myös seuraavien entiteettien luku- ja kirjoitusoikeudet.  
  
 Yrityksen hallinta -välilehti:  
  
-   **Postilaatikko**  
  
 Mukauttaminen-välilehti:  
  
-   **Entiteetti**  
  
-   **Kenttä**  
  
-   **Suhde**  
  
-   **Järjestelmäsovelluksen metatiedot**  
  
-   **Järjestelmälomake**  
  
-   **Käyttäjäsovelluksen metatiedot**  
  
-   **Näytä**  
  
##### <a name="set-the-privileges-for-a-security-role"></a>Määritä oikeudet käyttöoikeusroolille  
  
1.  [!INCLUDE[proc_settings_security](../includes/proc-settings-security.md)]  
  
2.  Valitse **Käyttöoikeusroolit**.  
  
3.  Valitse käyttöoikeusrooli ja valitse sitten **Yrityksen hallinta** -välilehti.  
  
4.  Tarkista **Entiteetti**-osasta **Postilaatikko**-kohdan lukuoikeuksien asetukset. Käyttöoikeusroolin asetuksen on oltava Käyttäjä tai laajempi.  
  
5.  Tarkista, että **Tietosuojaan liittyvät oikeudet** -osan **Käytä Dynamics 365 App for Outlook -sovellusta** -kohdan arvoksi on määritetty **Organisaatio**. Jos näin ei ole, valitse **Käytä Dynamics 365 App for Outlook -sovellusta**.  
  
### <a name="supported-configurations-with-microsoft-exchange"></a>Microsoft Exchangen kanssa tuetut kokoonpanot  
 Versiosta [!INCLUDE[pn_crm_8_2_0_both](../includes/pn-crm-8-2-0-both.md)] alkaen voit käyttää sovellusta minkä tahansa [!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)] tai [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)] ja [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)] tai [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (paikallinen) yhdistelmän kanssa. Myös hybridikokoonpanot ovat mahdollisia. Niinpä voitkin käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]ia kaikissa seuraavissa kokoonpanoissa:  
  
|||  
|-|-|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
|[!INCLUDE[pn_crm_online_shortest](../includes/pn-crm-online-shortest.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (paikallinen)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] (paikallinen)|  
|[!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)]|[!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)]|  
  
> [!NOTE]
>  Jos käytössä on [!INCLUDE[pn_crm_op_edition](../includes/pn-crm-op-edition.md)], sinun on käytettävä IFD-todennusta jäljempänä kuvattavalla tavalla.  
  
### <a name="supported-browsers-for-outlook-on-the-web"></a>Outlookin verkkoversion tukemat selaimet  
 Voit käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]- ja [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -sovellusta seuraavissa selaimissa:  
  
-   [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)] tai [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)]  
  
     Seuraavia kokoonpanoja tuetaan:  
  
    -   Suojattu tila otetaan käyttöön **internetin** suojausvyöhykkeessä. Suojatun tilan ottaminen käyttöön: jos käytössä on IE 10 tai 11, siirry kohtaan **Työkalut** > **Internet-asetukset** > **Suojaus-välilehti** > **Internet**.  
  
    -   Suojattu tila otetaan käyttöön **paikallisen intranetin** suojausvyöhykkeessä. Suojatun tilan ottaminen käyttöön: jos käytössä on IE 10 tai 11, siirry kohtaan **Työkalut** > **Internet-asetukset** > **Suojaus-välilehti** > **Paikallinen intranet**.  
  
    -   [!INCLUDE[pn_dyn_365](../includes/pn-dyn-365.md)]:n URL-osoite sisältyy **paikallisen intranetin** suojausvyöhykkeen luotettujen sivustojen luetteloon. Jos käytössä on IE 10 tai 11, siirry kohtaan **Työkalut** > **Internet-asetukset** > **Suojaus-välilehti** > **Paikallinen intranet** > **Sivustot** > **Lisäasetukset**.  
  
-   [!INCLUDE[tn_Google_Chrome](../includes/tn-google-chrome.md)] (uusin versio) [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]ille  
  
-   [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] (uusin versio) [!INCLUDE[pn_ms_Windows_short](../includes/pn-ms-windows-short.md)]ille  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_Safari](../includes/tn-safari.md)] (versiot 9 tai 10) Mac- tai OSX-käyttöjärjestelmässä  
  
### <a name="supported-operating-systems-for-outlook-on-the-desktop"></a>Outlookin työpöytäversion tukemat käyttöjärjestelmät  
 Voit käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]ia seuraavissa [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]in työpöytäversiossa:  
  
-   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2013 ja [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016.  
  
-   [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] for Mac*.  
  
     *[!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] -versio 15.0.847.32 tai uudempi vaaditaan.  
  
### <a name="supported-mobile-devices"></a>Tuetut mobiililaitteet  
 Voit käyttää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -ympäristön [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -sovellusta mobiiliselainta jollakin seuraavista puhelimista ja käyttöjärjestelmistä:  
  
-   [!INCLUDE[tn_apple](../includes/tn-apple.md)] [!INCLUDE[tn_iphone](../includes/tn-iphone.md)] -laitteet, joissa on iOS-versio 8, 9 tai 10.  
  
-   [!INCLUDE[tn_android](../includes/tn-android.md)]-puhelimet, joissa on [!INCLUDE[tn_android](../includes/tn-android.md)] 4.4 (KitKat), 5.0 (Lollipop), 6 (Marshmallow) tai 7 (Nougat).  
  
-   [!INCLUDE[pn_windows_phone](../includes/pn-windows-phone.md)] -laitteet, joissa on [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)] tai [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)].  
  
### <a name="supported-clients-per-feature"></a>Tuetut asiakkaat toimintoa kohden.  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] Tuetut ominaisuudet riippuvat käyttämästäsi asiakasohjelmasta. Seuraavassa taulukossa on yhteenveto kunkin asiakasohjelman tai kokoonpanon tukemista ominaisuuksista [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)] ja [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)].  
  
 ![Kunkin Dynamics 365 App for Outlook -ominaisuuden tukemat asiakkaat](media/clients-supported-for-each-dynamics-365-app-for-outlook-feature.png "Kunkin Dynamics 365 App for Outlook -ominaisuuden tukemat asiakkaat")  
  
 (1) [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] tukee seuraavia: [!INCLUDE[pn_IE_10](../includes/pn-ie-10.md)], [!INCLUDE[pn_ie_11](../includes/pn-ie-11.md)], [!INCLUDE[pn_microsoft_edge](../includes/pn-microsoft-edge.md)], [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 9, [!INCLUDE[tn_Safari](../includes/tn-safari.md)] 10, [!INCLUDE[tn_Firefox](../includes/tn-firefox.md)] ja [!INCLUDE[tn_chrome](../includes/tn-chrome.md)].  
  
 (2) Mobile [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] tukee seuraavia: [!INCLUDE[pn_windows_8_1](../includes/pn-windows-8-1.md)], [!INCLUDE[pn_windows_10](../includes/pn-windows-10.md)], [!INCLUDE[tn_ios](../includes/tn-ios.md)] 8, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 9, [!INCLUDE[tn_ios](../includes/tn-ios.md)] 10, [!INCLUDE[tn_android](../includes/tn-android.md)] KitKat (4.4), [!INCLUDE[tn_android](../includes/tn-android.md)] Lollipop, [!INCLUDE[tn_android](../includes/tn-android.md)] Marshmallow ja [!INCLUDE[tn_android](../includes/tn-android.md)] Nougat.  
  
 (3) Sähköpostien seuranta kirjoitustilassa ja tapaamisten seuraaminen edellyttää [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2013 CU14- tai [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)] 2016 -versiota.  
  
 (4) Vain [!INCLUDE[pn_Exchange_Server_short](../includes/pn-exchange-server-short.md)]2016 CU3 ja [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.6741.1000 ja sitä uudemmat versiot tukevat yhteyshenkilöiden seurantaa.  
  
 (5) Sähköpostimallien lisäämistä, Tietämyksenhallinta-artikkeleita ja myyntimateriaalia ei tueta Mobile [!INCLUDE[pn_outlook_web_app](../includes/pn-outlook-web-app.md)] -versiossa.  
  
 (6) Tuetaan vain [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)] 2016 16.0.7426.1049 ja sitä uudemmissa versioissa.  
  
 (7) Tuetaan vain 16.0.6741.1000 ja sitä uudemmissa versioissa.  
  
> [!NOTE]
>  Tabletteja ei tueta tällä hetkellä (tulossa 2017).  
  
 [Lue tarkempia tietoja tuetuista asiakasohjelmista tästä blogista: Dynamics 365 App for Outlook Support Matrix](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)  
  
### <a name="supported-servers"></a>Tuetut palvelimet  
 [Office-lisäosien käytön vaatimukset palvelimelle](https://dev.office.com/docs/add-ins/overview/requirements-for-running-office-add-ins) ovat [!INCLUDE[pn_Exchange_Server_2013_short](../includes/pn-exchange-server-2013-short.md)], [!INCLUDE[pn_exchange_server_2016_short](../includes/pn-exchange-server-2016-short.md)] tai [!INCLUDE[pn_Exchange_Online](../includes/pn-exchange-online.md)].  
  
### <a name="supported-languages"></a>Tuetut kielet  
 [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] tukee seuraavia kieliä:  
  
||||  
|-|-|-|  
|Bulgaria (Bulgaria) - 1026|Hindi (Intia) - 1081|Portugali (Portugali) - 2070|  
|Kiina (Kiinan kansantasavalta) - 2052|Unkari - 1038|Romania - 1048|  
|Kiina (Taiwan) - 1028|Indonesia - 1057|Venäjä - 1049|  
|Kroatia (Kroatia) - 1050|Italia - 1040|Serbia - 2074|  
|Tšekki (Tšekin tasavalta) - 1029|Japani - 1041|Slovakki - 1051|  
|Tanska - 1030|Kazakki - 1087|Sloveeni - 1060|  
|Hollanti - 1043|Korea - 1042|Espanja - 3082|  
|Englanti - 1033|Latvia - 1062|Ruotsi - 1053|  
|Viro - 1061|Liettua - 1063|Thai - 1054|  
|Suomi - 1035|Malesia - 1086|Turkki - 1055|  
|Ranska - 1036|Norja - 1044|Ukraina - 1058|  
|Saksa - 1031|Puola - 1045|Vietnam - 1066|  
|Kreikka - 1032|Portugali (Brasilia) - 1046||  
  
<a name="BKMK_Deploy"></a>   
## <a name="deploy-dynamics-365-app-for-outlook"></a>Dynamics 365 App for Outlookin käyttöönotto  
 Kun olet määrittänyt [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)]toiminnon ja tarvittavat oikeudet, voit siirtää [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]in käyttäjille. Tarvittaessa käyttäjät voivat asentaa ohjelman itse.  
  
> [!NOTE]
>  Jos käytössäsi on [!INCLUDE[pn_dyn_365_op](../includes/pn-dyn-365-op.md)], katso alla olevia osio: [Dynamics 365:n käyttöönotto paikallisille käyttäjille](#BKMK_DeployOnprem)  
  
#### <a name="to-push-the-app-to-users"></a>Sovelluksen siirtäminen käyttäjille  
  
1.  Siirry kohtaan **Asetukset** >  **Dynamics 365 App for Outlook**.  
  
2.  Jos haluat lähettää sovelluksen automaattisesti käyttäjille, valitse **Dynamics 365 CRM for Outlookin käytön aloittaminen** -näytön **Lisää mahdollisille käyttäjille** -kohdassa (saatat joutua valitsemaan **Asetukset**, jos olet avannut näytön aiemmin) **Lisää sovellus automaattisesti [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]iin** -valintaruutu. Jos käyttäjällä on tarvittavat oikeudet ja sähköposti synkronoidaan [!INCLUDE[cc_server_side_synch](../includes/cc-server-side-synch.md)]toiminnolla, et tarvitse erikseen siirtää ohjelmaa käyttäjälle. Jos esimerkiksi lisäät tarvittavat oikeudet myyjän rooliin ja delegoit roolin uudelle käyttäjälle, hän saa sovelluksen automaattisesti käyttöönsä.  
  
3.  Valitse jokin seuraavista:  
  
    -   Voit siirtää sovelluksen kaikille käyttäjille valitsemalla **Lisää sovellus kaikille soveltuville käyttäjille**.  
  
    -   Voit siirtää sovelluksen tietyille käyttäjille valitsemalla heidät luettelosta ja valitsemalla **Lisää sovellus Outlookiin**.  
  
    > [!TIP]
    >  Jos käyttäjä odottaa tai häntä ei ole lisätty luetteloon, saat lisätietoja tilasta valitsemalla käyttäjän vieressä olevaa **Lue lisää** -linkkiä.  
  
4.  Kun olet valmis, valitse **Tallenna**.  
  
#### <a name="to-have-users-install-the-app-themselves"></a>Käyttäjät asentavat sovelluksen itse  
  
1.  Napsauta **Asetukset**-painiketta ![Asetukset-painike](media/mp-ua-r16-settings.png "Asetukset-painike") ja valitse sitten **Dynamics 365:n sovellukset**.  
  
2.  **Dynamics 365:n sovellukset** -näytön kohdassa **[!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]** käyttäjä valitsee **Lisää sovellus [!INCLUDE[pn_Outlook_short](../includes/pn-outlook-short.md)]iin**.  
  
> [!NOTE]
>  Käyttäjät voivat myös tarvittaessa itse poistaa apuohjelman tai poistaa sen kokonaan. Lisätietoja on [Dynamics 365 App for Outlookin käyttöoppaassa](http://go.microsoft.com/fwlink/p/?LinkID=613099).  
  
<a name="BKMK_DeployOnprem"></a>   
## <a name="to-deploy-to-dynamics-365-on-premises-users"></a>Dynamics 365:n käyttöönotto paikallisille käyttäjille  
 Toimi seuraavasti, jos käytät paikallista Dynamics 365 -versiota.  
  
-   Määritä Dynamics 365 Server Internet-käyttöön. Katso [Microsoft Dynamics 365:n IDF-asetusten määrittäminen](https://technet.microsoft.com/library/dn609803.aspx).  
  
-   Määritä OAuth-palveluntarjoaja ja rekisteröi asiakassovellukset, jos muodostat yhteyden paikalliseen Exchange-palvelimeen. Lisätietoja on kohdassa [Windows Server 2012 R2 määrittäminen Dynamics 365-sovelluksille, jotka käyttävät OAuth-tunnistusta](https://technet.microsoft.com/library/hh699726.aspx).  
  
<a name="BKMK_Troubleshoot"></a>   
## <a name="troubleshooting-installation-problems"></a>Asennusongelmien vianmääritys  
 Jos sinulla tai käyttäjillä on [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)]in asennukseen liittyvä ongelmia, on mahdollista, että käyttäjien [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postilaatikko on linkitetty tällä hetkellä toiseen [!INCLUDE[pn_crm_shortest](../includes/pn-crm-shortest.md)]-organisaatioon. [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postilaatikko (sähköpostiosoite) voi synkronoida tapaamiset, yhteystiedot ja tehtävät vain yhden organisaation kanssa, ja käyttäjä, joka kuuluu kyseisen organisaatioon, voi synkronoida tapaamiset, yhteystiedot ja tehtävät vain yhden [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]-postilaatikon kanssa.  Voit korvata [!INCLUDE[pn_Exchange](../includes/pn-exchange.md)]en tallennetun asetuksen, jos haluat muuttaa ensisijaisen synkronointiorganisaation. Lisätietoja on [tässä Knowledge Base -artikkelissa](https://support.microsoft.com/en-gb/help/3211627/incomingemailrejected-error-when-attempting-to-install-dynamics-365-app-for-outlook).  
  
<a name="BKMK_Explore"></a>   
## <a name="explore-the-users-guide-and-train-your-users"></a>Käyttöoppaaseen tutustuminen ja käyttäjien kouluttaminen  
 Voit opetella käyttämään [!INCLUDE[pn_crm_app_for_outlook_short](../includes/pn-crm-app-for-outlook-short.md)] -järjestelmää [Dynamics 365 App for Outlookin käyttöoppaan](http://go.microsoft.com/fwlink/p/?LinkID=613099) avulla.  
  
 ![Dynamics 365 App for Outlookin käyttöoppaan sivu](media/dynamics-365-app-for-outlook-user-s-guide-page.png "Dynamics 365 App for Outlookin käyttöoppaan sivu")  
  
## <a name="see-also"></a>Katso myös  
 [Dynamics 365 App for Outlookin käyttöopas](http://go.microsoft.com/fwlink/p/?LinkID=613099)   
 [Lue tarkempia tietoja tuetuista asiakasohjelmista tästä blogista: Dynamics 365 App for Outlook Support Matrix](https://blogs.msdn.microsoft.com/crm/2016/12/13/dynamics-365-app-for-outlook-support-matrix/)   
 [Sähköpostiviestien, tapaamisten, yhteyshenkilöiden ja tehtävien palvelinpään synkronoinnin määrittäminen](../Topic/Set%20up%20server-side%20synchronization%20of%20email,%20appointments,%20contacts,%20and%20tasks.md)   
 [Lisää käyttäjiä, käyttöoikeuksia ja käyttöoikeusrooleja](http://msdn.microsoft.com/en-us/23612155-f92d-4871-a109-186419d5c19d)   
 [Toimintojen välisten ominaisuuksien lisääminen Microsoft Dynamics 365:een (online)](../DocSets/CRMIGv9_Admin/Toc/Add%20interoperation%20features%20to%20Microsoft%20Dynamics%20365%20\(online\).md)