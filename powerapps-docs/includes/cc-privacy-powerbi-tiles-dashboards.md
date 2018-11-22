Jos Power BI -ruutujen ja -koontinäyttöjen upotus on otettu käyttöön ja käyttäjä upottaa Power BI -ruudun tai -koontinäytön, kyseisen käyttäjän [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)]:n [!INCLUDE[pn_azure_active_directory](pn-azure-active-directory.md)] -valtuutustunnusta käytetään Power BI -palvelun valtuutustietoina taustalla, jolloin loppukäyttäjän käyttökokemus on saumaton.  
  
 Järjestelmänvalvoja voi ottaa Power BI -ruutujen ja -koontinäyttöjen upottamisen pois käytöstä milloin tahansa, jolloin [!INCLUDE[pn_dynamics_crm](pn-dynamics-crm.md)] -valtuutustunnuksen käyttö Power BI -palvelun valtuutustietoina lopetetaan. Kaikki aiemmin upotetut ruudut ja koontinäytöt lakkaavat toimimasta loppukäyttäjällä.  
  
 [!INCLUDE[pn_azure_shortest](pn-azure-shortest.md)]-komponentti tai -palvelu, joka osallistuu Power BI -ruutujen upottamiseen, kuvataan tarkemmin seuraavassa osiossa.  
  
 [!INCLUDE[cc_privacy_note_azure_trust_center](cc-privacy-note-azure-trust-center.md)]  
  
 [Azure Active Directory](https://azure.microsoft.com/services/active-directory/)  
  
 Tämä palvelu tuottaa valtuutustunnuksen, joka välitetään Power BI -palvelulle ohjelmointirajapinnan ja käyttöliittymän valtuutusta varten.