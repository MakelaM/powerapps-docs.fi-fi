Kun **Seuraa**-asetuksella merkitty sähköpostiviesti lähetetään [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:stä ja sähköpostin seuranta on otettu käyttöön, upotettu älykäs toiminto kerää tietoja vastaanottajien sähköpostivuorovaikutuksista. Tiedot kerätään ja tallennetaan [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]en vastaanottajan toiminnan tunnuslukujen ja seurattujen sähköpostiviestitapahtumien laskentaa varten.  
  
 Järjestelmänvalvoja ottaa sähköpostin seurannan käyttöön valmistelemalla toiminnon upotetun älykkään toiminnon **Sähköpostin seuranta** -välilehdessä. Järjestelmänvalvojat voivat poistaa sähköpostin seurannan käytöstä organisaatiossa **Älykkään toiminnon määritykset** -solmussa **Asetukset**-kohdassa.  
  
 Kun toiminto on poistettu käytöstä, [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:stä lähetettyjä sähköpostiviestejä ei voi seurata käyttöliittymästä eikä ohjelmallisesti. Myöskään vastaanottajan yhteydenottotietoja ei enää kerätä lähetetyistä sähköposteista, jotka on merkitty **Seuraa**-asetuksella. Kaikki aiemmin kerätyt tiedot säilyvät [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]ssa. Ne ovat käytettävissä, jos toiminto otetaan uudelleen käyttöön organisaatiossa. Tiedot säilytetään 90 päivän ajan sen jälkeen, kun asiakas on päättänyt Microsoft-tilauksensa. [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -käyttäjät voivat poistaa käytöstä myös upotetun älykkään sähköpostin seuranta -toiminnon yhteyshenkilön tai liidin perusteella muuttamalla **Seuraa sähköpostia** -asetusta **Yhteyshenkilöasetukset**-kohdassa.  
  
 Seuraavassa esitellään [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentit ja -palvelut, jotka liittyvät Sähköpostin seuranta -toimintoon.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 **[!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)]**  
  
 Sähköpostin seuranta -toiminto tallentaa sähköpostiviestitapahtumien blob-objektit väliaikaisesti [!INCLUDE[pn_azure_storage_account](pn-azure-storage-account.md)] -sovelluksen avulla.