## <a name="delegation"></a>Delegointi
Jos mahdollista, PowerApps delegoi suodatus- ja lajittelutoiminnot tietolähteeseen ja näyttää tulokset tarvittaessa sivu kerrallaan. Kun esimerkiksi käynnistät sovelluksen, jossa on **[Galleria](../maker/canvas-apps/controls/control-gallery.md)**-ohjausobjekti tietoineen, laitteeseen tuodaan aluksi vain ensimmäinen tietuejoukko. Käyttäjän vierittäessä alaspäin tietolähteestä tuodaan lisää tietoja. Näin sovellus käynnistyy nopeammin ja se voi käyttää suuria tietojoukkoja.

Delegointi ei kuitenkaan aina ole mahdollista. Tietolähteiden tukemat delegointitoiminnot ja -operaattorit vaihtelevat. Jos kaavan täysi delegointi ei ole mahdollista, muokkausympäristö merkitsee varoituksella osan, jota ei voi delegoida. Jos mahdollista, muuta kaavaa siten, että se välttää toimintoja ja operaattoreita, joita ei voi delegoida.  [Delegointiluettelossa](../maker/canvas-apps/delegation-list.md) on mainittu tietolähteet ja toiminnot, jotka voidaan delegoida.

Jos delegointi ei ole mahdollista, PowerApps noutaa vain pienen joukon tietueita paikallista käsittelyä varten. Suodatus- ja lajittelutoiminnot käsittelevät tietueiden rajattua joukkoa. Jos **[Galleriassa](../maker/canvas-apps/controls/control-gallery.md)** ei ole kaikkia tietueita, käyttäjät voivat hämmentyä. 

Katso lisätietoja [delegoinnin yleiskatsauksesta](../maker/canvas-apps/delegation-overview.md).

