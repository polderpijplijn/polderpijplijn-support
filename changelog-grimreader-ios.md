# Changelog — Grim Reader

All notable changes per release. Newest first.
Versions match the `vX.Y` tags and `CFBundleShortVersionString`.

## 3.31 — 2026-08-14

- **Strips van je server tonen nu hun eigen titel, serie en tekenaar** in plaats van alleen de bestandsnaam, als die gegevens in het bestand staan. Je ziet het bij strips die na deze versie worden gescand.
- **Bij het zoeken van een schrijver staat er nu een vinkje** bij degene die je gekozen hebt. Kies je iemand zonder beschrijving of foto, dan worden de oude gegevens ook echt gewist in plaats van te blijven staan.
- **Schrijversfoto's zijn na een herstart meteen zichtbaar** in plaats van pas na een tel; ze worden nu bewaard in plaats van elke keer opnieuw opgehaald.
- **De omslag van sommige audioboeken bleef leeg** wanneer er een accent of ander bijzonder teken in de omschrijving van de omslag stond. Die worden nu goed gelezen.
- **De tijdbalk van een audioboek van je server sleepte stroef en belastte je server**: tijdens het slepen werd bij elke beweging opnieuw gezocht. Nu gebeurt dat pas als je loslaat.

## 3.3 — 2026-08-13

- **Delen van de app stonden nog in het Nederlands als je hem in het Engels gebruikte**, waaronder het schrijversscherm, het onderhoudsscherm en de nieuwe knoppen rond strips en audioboeken. Die zijn nu vertaald.
- Op het scherm om een schrijver te bewerken heet "Levensbericht" nu "Beschrijving".

## 3.2 — 2026-08-13

- **Een strip die nog niet op je toestel staat wordt nu automatisch opgehaald** wanneer je hem opent. Voorheen kon je op een melding belanden waar je niet meer uit kwam. De strip wordt bewaard, dus de volgende keer opent hij meteen.
- **Audioboeken van je eigen server spelen nu door op de achtergrond en op het toegangsscherm**, met de omslag en de bedieningsknoppen erbij — net als audioboeken van een Grimmory-server. Sluit je het spelerscherm terwijl het speelt, dan loopt het gewoon door.
- **Het inlogscherm is opgeruimd.** WebDAV, thema en de demo stonden op het Grimmory-inlogscherm terwijl het app-brede instellingen zijn; die vind je nu allemaal onder Instellingen. De demoknop staat daar bovenaan.

## 3.1 — 2026-08-13

- **Een audioboek vanaf het startscherm openen gaf een serverfout.** Het ging langs de speler die bij een Grimmory-server hoort; nu wordt het net als vanuit het serveroverzicht afgespeeld — van je toestel als het er staat, anders rechtstreeks van je server.
- **Strips openden soms met "het archief kon worden geopend maar bleek leeg".** Een interne padcontrole liep mis op de iPhone, waardoor er niets werd uitgepakt. Opgelost.
- **Een boek van je server verwijderen** kan nu, via het menu in het boekdetail. Het bestand wordt van je server gehaald; dit kan niet ongedaan gemaakt worden.
- **Schrijversgegevens aanvullen laat nu eerst zien wat er gevonden is.** Je keurt per schrijver goed, of alles in één keer, en kunt er één aanpassen voordat er iets bewaard wordt. Wijkt de gevonden pagina af van de naam, dan staat daar een waarschuwing bij — dan heeft de bron mogelijk de verkeerde persoon.
- **Bij een schrijver zoeken kies je nu uit meerdere kandidaten**, met aantal boeken en jaartallen erbij, uit Open Library naast Wikipedia. Handig als er automatisch een verkeerde pagina bij is gezocht.
- **Je kunt zelf een foto voor een schrijver kiezen**, uit je fotoalbum of als bestand.
- Schrijversfoto's die in de lijst ontbraken terwijl ze op het scherm van de schrijver wél stonden, verschijnen nu overal, en vullen hun rondje netjes in plaats van er verloren in te zweven.
- Nieuwe strips en audioboeken verschijnen meteen op het startscherm na een scan, in plaats van pas nadat je de app opnieuw opent.

## 3.0 — 2026-08-13

- **Een audioboek rechtstreeks van je server afspelen werkte niet.** De app vertelde de speler wel hoe groot het bestand was, maar stuurde nooit de audio zelf — die vraag werd met het verkeerde antwoord afgedaan.
- **De speler onthield niet waar je gebleven was.** Bij een boek van je eigen server werd de tijdwaarnemer overgeslagen, en juist die houdt je positie bij en bewaart hem. Daardoor stond de schuifbalk ook stil.
- **Strips: "geen pagina's gevonden".** Of een bestand als pagina meetelt wordt nu bepaald door te kijken of het werkelijk een afbeelding is, in plaats van af te gaan op de bestandsnaam. Komt er alsnog niets uit, dan vertelt de app wat er wél in het archief zat.
- **Een schrijver bewerken was niet te openen.** De potloodknop op het schrijversscherm was gekoppeld aan een beheerdersrol op een Grimmory-server; zonder zo'n server bleef hij verborgen. Nu kun je naam, levensbericht en foto aanpassen — handig als er een verkeerde Wikipedia-pagina bij is gezocht.
- **Eigen rijen voor Audioboeken en Strips op het startscherm**, zodat ze niet tussen de rest verdwijnen. Werkt ook met een Grimmory-server.
- **"Recent toegevoegd" toont nu ook boeken van je server.** Die hadden geen datum en belandden daardoor altijd achteraan; de app gebruikt nu de datum van het bestand op de server. Dit geldt voor boeken die na deze versie zijn doorzocht.

## 2.99 — 2026-08-12

- **Strips en audioboeken op je server worden nu gevonden.** De app keek alleen naar EPUB en PDF; al het andere werd bij het doorzoeken overgeslagen. CBZ-strips en audiobestanden (mp3, m4b, m4a, aac) staan nu gewoon in je bibliotheek. CBR blijft buiten beeld: dat is een RAR-archief en daar kan de app niet in kijken — zichtbaar maken wat je niet kunt openen leek ons vervelender dan weglaten.
- **Strips lezen** met bladeren per pagina, knijp-zoomen en dubbeltikken om in te zoomen. De app onthoudt op welke pagina je gebleven was.
- **Audioboeken kun je afspelen zonder ze eerst binnen te halen.** Een audioboek is al gauw honderden megabytes; met "Luisteren" begin je meteen en wordt alleen opgehaald wat er op dat moment nodig is. Wil je hem offline kunnen horen, dan kan downloaden nog steeds.
- **De speler onthoudt waar je gebleven was**, ook zonder Grimmory-server.
- **Omslag, titel en schrijver van een audioboek** worden uit het bestand zelf gehaald — uit alleen de eerste tienduizenden bytes, niet het hele bestand. Werkt voor mp3 en voor m4b/m4a.

## 2.98 — 2026-08-12

- **Een schrijver uit je eigen bibliotheek kun je nu bewerken, met opzoeken erbij.** Via het potlood op het schrijversscherm pas je de naam, het levensbericht en de foto aan; met de zoekknop haal je die gegevens van Wikipedia. **Verander je de naam, dan wordt die in alle boeken van die schrijver meteen meeveranderd** — en bestaat de nieuwe naam al, dan worden de twee samengevoegd.
- **De foto van een schrijver staat nu ook in het rondje in de schrijverslijst**, niet alleen op het scherm van de schrijver zelf. Wat de app nog niet heeft opgehaald blijft leeg; met "Schrijversgegevens aanvullen" in het onderhoudsscherm haal je ze in één keer op.

## 2.97 — 2026-08-12

- **Het schrijversscherm toont nu ook de foto en het levensbericht van schrijvers uit je eigen bibliotheek.** Die gegevens werden al opgehaald en naast je boeken bewaard, maar je zag ze alleen bij een boek — het schrijversscherm zelf bleef leeg.
- **Onderhoud voor je eigen servers**, in Instellingen. Drie hulpmiddelen die eerder alleen met een Grimmory-server bestonden:
  - **Schrijvers samenvoegen** — "P.G. Wodehouse", "P. G. Wodehouse" en "p g wodehouse" worden als één schrijver herkend; jij kiest welke schrijfwijze blijft.
  - **Schrijversgegevens aanvullen** — haalt van al je schrijvers in één keer de foto en het levensbericht op, in plaats van pas wanneer je toevallig een boek van ze opent.
  - **Taalcodes standaardiseren** — brengt "nl", "nl-NL" en "Dutch" onder één noemer, zodat filteren op taal klopt.
- Deze hulpmiddelen werken op de gegevens die de app naast je boeken bewaart; je boekbestanden worden er niet door aangepast.

## 2.96 — 2026-08-12

- **"Ook in het boekbestand zelf opslaan" werkte alleen als je het boek via je server opende.** Bewerkte je hetzelfde boek vanuit Schrijvers of Start, dan werd de instelling genegeerd en bleef het bestand ongemoeid. Beide wegen doen nu hetzelfde.

## 2.95 — 2026-08-12

- **Je kunt de gegevens nu ook in het boekbestand zelf laten opslaan.** Tot nu toe werden je wijzigingen naast het boek bewaard, zodat andere programma's de oude titel bleven tonen. Zet je in het bewerkscherm "Ook in het boekbestand zelf opslaan" aan, dan worden titel, schrijver, taal en samenvatting in het EPUB geschreven. Het boek wordt daarvoor opgehaald, aangepast en teruggezet op je server. Alleen voor EPUB; de instelling blijft onthouden en staat standaard uit.
- Bij het aanpassen van een boekbestand blijft het origineel op je server staan tot de nieuwe versie volledig is geüpload. Valt de verbinding weg, dan is je boek ongemoeid en ligt er hooguit een tijdelijk bestand naast. Alles in het boek behalve de metadata wordt ongewijzigd overgenomen — er wordt niets opnieuw ingepakt.

## 2.94 — 2026-08-12

- **Het aantal boeken achter een schrijver liep niet mee.** De schrijverslijst werd één keer opgebouwd en daarna niet meer; kwamen er boeken bij, dan bleven de getallen op de oude stand staan terwijl het openen van die schrijver wél alles liet zien. De lijst werkt nu bij zodra er boeken bijkomen, en je kunt hem omlaagtrekken om te vernieuwen.
- **Achter elke server in het zijpaneel staat nu hoeveel boeken de app van die server kent**, net als bij de bibliotheken.

## 2.93 — 2026-08-12

- **Een boek bewerken zonder Grimmory-server gaf "Serverfout (401)".** Het opslaan van de gegevens ging goed, maar de omslag werd daarna alsnog naar een Grimmory-server gestuurd die je niet hebt. Datzelfde gold voor het wijzigen van de taal en de schrijver. Die gaan nu allemaal naar je eigen opslag of naar je WebDAV-server, net als de rest van de bewerking.

## 2.92 — 2026-08-12

- **Een boek bewerken kan nu ook zonder Grimmory-server.** De potloodknop was gekoppeld aan een beheerdersrol op die server, en verscheen dus nooit als je alleen je eigen bestanden of een WebDAV-server gebruikt. Vanuit Schrijvers, Start of waar dan ook kun je nu titel, schrijver, taal en samenvatting aanpassen. Voor een geïmporteerd bestand blijft dat op je toestel; voor een boek van je WebDAV-server gaat het naar die server, zodat je andere toestellen het ook zien.
- **Je bewerking wordt nu meteen naar je server geschreven.** Dat gebeurde pas twintig seconden nadat het stil werd, wat bedoeld is voor het massaal aanvullen van omslagen — sloot je de app in die tijd, dan was je wijziging weg.
- **Een boek bewerken dat je via de mappenbrowser had gevonden ging verloren.** Stond het boek niet in een doorzochte index, dan werd alleen de omslag bewaard en verdwenen titel en schrijver zonder melding. Het boek wordt nu alsnog aan de index toegevoegd.
- **Alles downloaden in één keer**, bij een schrijver en in een servermap. Boven de twintig boeken wordt eerst gevraagd of je het zeker weet, en tijdens het downloaden zie je de voortgang met een stopknop. In een map worden alleen de boeken in die map gepakt, niet die in de submappen.
- **Het aantal boeken naast een schrijver klopte niet.** Schrijvers werden voor die telling op hun exacte schrijfwijze gegroepeerd, terwijl het openen van een schrijver hoofdletters juist negeert. "Stephen King" en "STEPHEN KING" stonden daardoor als twee regels met elk een deel van de boeken, terwijl je bij het openen van één van beide het volledige aantal kreeg. Ze worden nu als één schrijver geteld.
- **Bij het bladeren door de mappen van je server kun je kiezen tussen een lijst en een raster met omslagen.** De keuze blijft bewaard.
- **Open je een boek vanuit de mappenbrowser, dan zie je nu meteen de omslag, de titel en de schrijver.** Die waren al opgehaald voor het overzicht, maar werden niet doorgegeven aan het detailscherm — dat begon daardoor blanco.

## 2.90 — 2026-08-12

- **Je boeken op een WebDAV-server tellen nu overal mee.** Start, Schrijvers en Collecties lieten alleen zien wat je zelf had geïmporteerd of al had gedownload — de duizenden boeken die de app op je server had gevonden zaten er niet bij, en waren dus alleen via het serveroverzicht te vinden. Nu maakt het niet meer uit waar een boek vandaan komt: het staat gewoon onder zijn schrijver. Tik je zo'n boek aan, dan wordt het op dat moment van je server gehaald.
- Een boek dat je al hebt binnengehaald verschijnt niet meer dubbel naast zijn versie op de server.
- De schrijversnaam van een serverboek komt uit het boekbestand zelf; zolang de app dat nog niet heeft opgehaald staat het boek onder "Onbekende schrijver" en schuift het vanzelf op zijn plek zodra dat gebeurd is.

## 2.89 — 2026-08-12

- **Door de mappen van je server bladeren, zonder te wachten op het doorzoeken.** Rechtsboven in het boekenoverzicht van een server staat nu een mapknop. Daarmee loop je je server door zoals je dat op je computer zou doen: elke map wordt opgehaald op het moment dat je hem opent, dus je kunt meteen een boek zoeken en lezen. Van de boeken in de map die je openslaat worden de omslag, de titel en de schrijver erbij gehaald terwijl je kijkt. Bij een bibliotheek van duizenden mappen is dat het verschil tussen direct beginnen en minutenlang wachten. Het doorzoeken van de hele bibliotheek blijft bestaan en blijft nodig voor zoeken, de schrijverslijst en het Start-scherm.
- **Een nieuwe server wordt niet meer ongevraagd helemaal doorzocht.** Voorheen begon dat vanzelf zodra je zijn boeken opende, wat bij een grote bibliotheek minuten stil wachten betekende zonder dat je erom had gevraagd. Nu krijg je de keuze: doorzoeken, of meteen door de mappen bladeren. Bewaarde de app al eerder een boekenindex op de server zelf, dan wordt die nog steeds vanzelf geladen — dat is één bestand en zo gebeurd.

## 2.88 — 2026-08-12

- **Omslagen en schrijversnamen ophalen kost nu een kwart van het dataverkeer.** De app haalde per boek het hele bestand van je server op om er een plaatje en een naam uit te vissen en gooide de rest weg; bij een grote bibliotheek liep dat in de gigabytes. Nu wordt alleen het stukje opgehaald dat er werkelijk toe doet. Op een verzameling van bijna tienduizend boeken scheelt dat ruwweg vijf gigabyte. Servers die dit niet ondersteunen werken gewoon zoals voorheen.
- **Het aanvullen van omslagen wacht nu tot het doorzoeken klaar is.** Beide gebeurden tegelijk en gebruikten dezelfde verbinding met je server, waarbij de zware boekdownloads de lichte mapopvragingen in de weg zaten — waardoor juist het doorzoeken, dat je als eerste wilt zien, langzaam ging.

## 2.87 — 2026-08-12

- **Het doorzoeken van een WebDAV-server gaat ongeveer vier keer zo snel.** De app vroeg de mappen één voor één op en wachtte telkens op het antwoord voor hij verder ging; nu vraagt hij er acht tegelijk op. Op een bibliotheek van zo'n vierduizend mappen scheelt dat ruwweg vier en een halve minuut wachten tegenover iets meer dan één. Servers die de hele mappenboom in één keer kunnen leveren gebruikten die snelle weg al — maar veel servers, waaronder Synology, staan dat niet toe en waren dus altijd op de trage manier aangewezen.
- **Het ophalen van omslagen en schrijversnamen gaat eveneens sneller**, om dezelfde reden: acht boeken tegelijk in plaats van drie.

## 2.86 — 2026-08-11

- **Favorieten op je eigen geïmporteerde boeken wezen na een herstart een ander boek aan.** Die boeken krijgen bij elke start een nieuw intern nummer toegekend, in de volgorde waarin ze op schijf gevonden worden — en juist dat nummer werd als favoriet opgeschreven. Startte je de app opnieuw, dan hoorde het bij een ander boek. Favorieten worden nu bewaard op iets dat niet verandert: het bestand zelf, net zoals collecties dat al deden. Favorieten op boeken van je server werkten wel goed en blijven behouden; die op geïmporteerde boeken zijn niet te herstellen en beginnen opnieuw.
- **Favorieten beloofden synchronisatie tussen je apparaten, maar deden dat nooit.** De app schreef ze naar iCloud zonder daar toestemming voor te hebben aangevraagd, waardoor iOS het stilzwijgend negeerde. Je favorieten werkten al die tijd op de lokale kopie — dat verandert dus niets — maar de app belooft nu niets meer wat hij niet waarmaakt.
- **Vijf teksten stonden nog in het Nederlands als je de app in het Engels gebruikte**, waaronder drie voorleeslabels voor VoiceOver.

## 2.85 — 2026-08-11

- **Je server werd onterecht als "alleen-lezen" aangemerkt** (het slotje in Instellingen). De app testte zijn schrijfrechten met een bestandje dat met een punt begon, en veel servers — waaronder QNAP met Apache — weigeren zulke verborgen bestanden standaard. De boekenindex zelf heeft geen punt en werd wél geaccepteerd, dus de test mat iets anders dan wat de app werkelijk doet. Het testbestand heet nu `write-test.tmp`.
- **Mislukt het bijwerken van de index op je server, dan zegt de app dat nu ook.** Die fout werd volledig weggeslikt; je kon het alleen ontdekken door op je NAS naar de datum van het bestand te kijken. De reden staat nu in de regel bovenaan het serverscherm.

## 2.83 — 2026-08-11

- **Je WebDAV-server wordt niet meer bij elke start opnieuw doorzocht.** De bewaarde lijst werd genegeerd doordat een scan die niet helemaal afmaakte — bij een grote bibliotheek bijna altijd — als "nooit gescand" gold. De app toont nu wat hij van je server kent en jij bepaalt zelf wanneer je ververst. Stond er nog helemaal niets, dan zoekt hij wel vanzelf.
- **Boeken verdwenen tijdens het opnieuw zoeken.** Een herscan begon met een lege lijst en vulde die gaandeweg, waardoor nog niet teruggevonden boeken tijdelijk uit beeld waren — en blijvend als de scan afbrak. Inclusief hun al opgehaalde omslag en schrijver. De scan begint nu bij wat er al is.
- **Aantal boeken naast de servernaam**, in Instellingen en in het serveroverzicht.
- **Omslagen en schrijvers worden nu voor je hele bibliotheek opgehaald**, niet alleen voor de boeken die je toevallig in beeld hebt gehad. Dat gebeurt rustig op de achtergrond en blijft bewaard, dus het is eenmalig werk per boek. De regel bovenaan laat zien hoeveel er nog te gaan zijn.
- **De app schrijft veel minder naar je server.** Grim Reader houdt op je WebDAV-server een boekenindex bij (`.grimreader/books.yaml`) zodat een tweede toestel niet opnieuw hoeft te zoeken. Die werd bij élk aangevuld boek opnieuw geüpload; bij een grote bibliotheek werden dat duizenden uploads van een steeds groter bestand. Nu wordt dat gebundeld tot één keer.
- Op de iPad stonden je OPDS-catalogi dubbel: als eigen onderdeel én bij de servers. Nu alleen nog bij de servers, net als op de iPhone.

## 2.82 — 2026-08-11

- **Zoeken in een OPDS-catalogus gaf "Kan niet laden … requires the use of a secure connection".** Catalogi geven hun zoekadres vaak nog als `http://` op, ook als ze zelf allang via `https://` draaien (Project Gutenberg doet dat), en iOS blokkeert zo'n onbeveiligde aanroep. De app zet dat adres nu om naar `https` wanneer de catalogus zelf ook beveiligd is. Een server op je eigen netwerk die bewust over `http` draait blijft ongemoeid.

## 2.81 — 2026-08-11

- **Je eigen OPDS-catalogi staan nu bij je WebDAV-servers onder "Servers"**, in plaats van in een aparte tab "Mijn catalogi". Het zijn allebei bronnen die je zelf toevoegt, dus die horen bij elkaar — en het scheelt een tab in de onderbalk.
- **Zoeken in een OPDS-catalogus werkt nu vanzelf.** Voorheen moest je bij het toevoegen met de hand een zoek-URL invullen; deed je dat niet, dan was er simpelweg geen zoekbalk en zag je niet waarom. De app vraagt de catalogus nu zelf om zijn zoekadres (via de zoeklink in de feed, en zo nodig de OpenSearch-beschrijving daarachter). Het handmatige veld blijft bestaan voor het geval een catalogus dat niet netjes publiceert.

## 2.80 — 2026-08-11

- **Eigen collecties.** Onder Bladeren → Collecties maak je zelf groepen ("Sciencefiction", "Nog lezen") om je boeken te ordenen. Toevoegen doe je vanuit Mijn boeken: houd een boek ingedrukt en kies "Toevoegen aan collectie". Een boek kan in meerdere collecties zitten, en er wordt niets verplaatst of hernoemd op schijf. Werkt voor zowel geïmporteerde bestanden als van je server gedownloade boeken.
- **Je eigen OPDS-catalogus kan weer.** Onder Instellingen → Servers voeg je het adres van je eigen bron toe, bijvoorbeeld een Calibre-Web-server — net zoals je dat met WebDAV en Grimmory doet. De app levert zelf geen catalogi mee; de tab "Mijn catalogi" verschijnt pas zodra je er een hebt toegevoegd.
- **Een scan van een WebDAV-server stopt niet meer als je van tab wisselt, en toont gevonden boeken meteen.** De scan hing aan het scherm en werd door het systeem afgebroken zodra je wegklikte, waarna al het werk verloren was en hij bij terugkomst weer bij nul begon. De scan loopt nu los van het scherm door, en boeken verschijnen in de bibliotheek zodra ze gevonden zijn in plaats van pas aan het eind.
- **Van je server gedownloade boeken staan nu ook onder Start en Schrijvers als je offline bent.** Ze zaten in een andere opslag dan geïmporteerde bestanden, en alleen die laatste werd gebruikt om die schermen te vullen — een gedownload boek was daardoor onderweg alleen via Mijn boeken te vinden. Wie uitsluitend downloadt zag die schermen zelfs helemaal leeg.
- **Boeken zonder schrijver in hun metadata (vaak PDF's) verdwenen uit de schrijverslijst.** Die staan nu onder "Onbekende schrijver".
- Het sorteermenu bij Schrijvers (naam, aantal boeken, recent toegevoegd) deed niets zolang je zonder server werkte. Dat werkt nu.

## 2.79 — 2026-08-11

- **"Overslaan"-knop op het inlogscherm.** Bij een verse installatie oogde het inlogscherm als een verplichte instellingenpagina: twee secties met (lege) inlogvelden vóór je "WebDAV-server toevoegen" of "Offline demo" tegenkwam. Rechtsboven staat nu direct een "Overslaan"-knop die naar een leeg hoofdscherm gaat — geen voorbeeldboeken zoals de demo, gewoon een lege "Mijn boeken" voor wie eigen bestanden importeert of een WebDAV-server toevoegt.
- **De app valt nu terug op lokale boeken als de server niet bereikbaar is, ook al heeft het toestel internet.** Weg van huis met mobiel internet aan dacht de app eerder dat hij bij de Grimmory-server kon (het toestel heeft immers internet), en elk scherm probeerde de server alsnog te bereiken — tot 20 seconden per verzoek, zonder nette terugval. Er is nu een aparte, snelle proef (5s) die de server zelf test in plaats van alleen de internetverbinding van het toestel; is de server onbereikbaar, dan schakelt de app meteen om naar lokaal geïmporteerde/gedownloade boeken. Werkt ook beter in vliegtuigmodus.

## 2.78 — 2026-07-18

- **Tikken op een plaatje in een EPUB speelt nu het bijbehorende geluid én opent het plaatje schermvullend** (met knijp-zoom). Twee bugs hielden het geluid daarvoor stil: het pad naar het audiobestand werd relatief doorgegeven in plaats van als volledige URL, en de vergelijking op tagnaam ging mis omdat XHTML als XML wordt gelezen (kleine letters in plaats van hoofdletters).

## 2.77 — 2026-07-18

- Een tik op een plaatje bereikte de leesweergave helemaal niet: er ligt een onzichtbare laag overheen die veegbewegingen opvangt om te kunnen bladeren, en die slokte de tik op. De app vraagt nu bij een tik aan de pagina of daar een plaatje met geluid zit — zonder het bladeren te breken.

## 2.76 — 2026-07-18

- Geluid dat in een EPUB aan een plaatje hangt (`epub:trigger`) wordt nu door de app zelf afgespeeld. Rechtstreeks afspelen vanuit de pagina werkt niet betrouwbaar op iOS.

## 2.75 — 2026-07-08

- Internetboeken (OPDS/Gutenberg) verwijderd uit de App Store-build.

## 2.74 — 2026-07-02

- **Tekst en bediening vallen op de iPhone niet meer weg aan de zijkanten tijdens het voorlezen.** De bedieningsrij was met zes knoppen breder dan het scherm en rekte daardoor de hele leesweergave op; de weergave-knop (AA) wijkt nu zolang het voorlezen speelt.
- Het parkeren van de leesweergave bij achtergrond-voorlezen (2.73) is teruggedraaid: het loste het iPad-beginscherm-geval niet op en veroorzaakte alleen een onnodige pagina-heropbouw bij terugkeer. Eindstand: audioboeken spelen overal door op iPhone en iPad; voorlezen speelt op de iPhone overal door en op de iPad in de app en met het scherm op slot.

## 2.73 — 2026-07-02

- **Voorlezen speelt nu ook op de iPad door na het wegvegen naar het beginscherm.** De leesweergave (webweergave) wordt tijdens achtergrond-voorlezen tijdelijk geparkeerd, zodat iPadOS de audio niet meer meetrekt bij het slapend maken van die weergave — op de iPhone werkte dit al. Bij terugkeer bouwt de pagina zich opnieuw op.
- **Engelse vertaling gerepareerd:** ruim honderd teksten (waaronder de voorleesknop, vertalen, catalogi en zoeken) toonden in de Engelse interface nog Nederlands.
- **Voorlezen toont boektitel, auteur en omslag op het toegangsscherm**, net als de audioboekspeler.
- **De voorleesknop rekt niet meer uit** zodra het voorlezen speelt: tijdens het afspelen toont hij alleen het stop-icoon.

## 2.72 — 2026-07-02

- **Diagnoseregel uit het voorleespaneel verwijderd** — het achtergrond-onderzoek is afgerond. Eindstand: voorlezen speelt door met het scherm op slot, met bediening op het toegangsscherm; alleen naar het beginscherm navigeren stopt het nog, door een bekende WebKit-beperking waarvoor geen nette oplossing bestaat. Audioboeken spelen overal door, ook op het beginscherm.

## 2.71 — 2026-07-02

- **De leesweergave geeft de audiobesturing niet meer uit handen.** De ingebouwde webweergave kreeg altijd rechten om media automatisch af te spelen (voor video's in EPUB's), en claimde daarmee het audiosessiebeheer van de app — met als gevolg dat iOS de audio bij het verlaten van de app uitschakelde. Die rechten gelden nu alleen nog voor boeken die daadwerkelijk video of audio bevatten.
- **Voorlezen heeft nu bediening op het toegangsscherm**: afspelen/pauzeren en zin vooruit/terug, net als de audioboekspeler.

## 2.70 — 2026-07-01

- **Voorlezen fundamenteel herbouwd voor betrouwbaar doorspelen op de achtergrond.** Zes pogingen om de live spraakmotor op de achtergrond aan de praat te houden strandden op hetzelfde iOS-gedrag: de volgende zin start simpelweg niet meer, hoe correct de audio-instellingen ook staan. Het voorlezen rendert de zinnen nu vooraf als kleine audiofragmenten en speelt die naadloos af via dezelfde afspeeltechniek als audioboeken — die aantoonbaar wél feilloos doorspelen. Bediening, zin-oplichting, hoofdstukdoorloop en snelheid werken zoals voorheen.

## 2.69 — 2026-07-01

- **Voorlezen op de achtergrond, volgende poging:** de spraakstem gebruikt nu een eigen, door iOS beheerde audiosessie (de bekende oplossing van de Apple-ontwikkelaarsforums voor "leest één zin en valt dan stil"). De diagnose uit 2.68 bewees dat de app-sessie zelf al die tijd correct stond, dus het probleem zit in de spraakmotor zelf.
- Diagnoseregel uitgebreid: toont bij terugkeer in de app nu ook of de spraakmotor nog leefde en bij welke zin hij stond.

## 2.68 — 2026-07-01

- **Voorlezen op de achtergrond: de echte oorzaak gevonden en verholpen.** De diagnose uit 2.67 wees uit dat de audiosessie al die tijd correct stond — het probleem is dat de spraakstem tussen twee zinnen een fractie van een seconde stil is, en iOS de app precies in dat gaatje als "speelt niets" aanmerkt, waarna de volgende zin nooit meer start. Een onhoorbare achtergrondloop houdt de audio nu continu, zodat het voorlezen ook op de achtergrond gewoon doorleest.

## 2.67 — 2026-07-01

- **Voorlezen op de achtergrond: terug naar de bewezen werkende aanpak.** De slimmere sessie-afhandeling uit 2.66 bleek de verse start juist te breken; het voorlezen herstelt de audiosessie nu altijd expliciet vóór het starten, exact zoals in de versie waar dit aantoonbaar werkte.
- **Tijdelijke diagnoseregel in het voorleespaneel** die laat zien wat de audiosessie werkelijk deed — ook van de vorige app-sessie, mocht de app op de achtergrond zijn beëindigd. Wordt weer verwijderd zodra het achtergrond-voorlezen op alle paden bevestigd werkt.

## 2.66 — 2026-07-01

- **Voorlezen bij een verse start speelt weer door op de achtergrond.** De leesweergave zelf (de webweergave die de boekpagina toont) claimt bij het laden de audiosessie, waardoor het voorlezen in 2.65 op de achtergrond stilviel en de app zelfs afgesloten kon worden. Het voorlezen en de ingesproken-audiospeler zetten de sessie nu eerst expliciet terug — behalve wanneer die net door de audioboekspeler is overgedragen, want dat pad werkte juist al.

## 2.65 — 2026-07-01

- **Voorlezen na een audioboek werkt weer op de achtergrond.** In 2.64 stopte het voorlezen op de achtergrond (na de lopende zin, en de app kon zelfs afgesloten worden) als er eerder in dezelfde sessie een audioboek had gespeeld — de audiosessie-wissel tussen de twee kon stilletjes mislukken. De overdracht houdt de sessie nu actief.
- **De EPUB-lezer sluiten stopt een op de achtergrond spelend audioboek niet meer**: opruim-stops laten de audiosessie voortaan met rust als ze zelf niets afspeelden.

## 2.64 — 2026-07-01

- **Audioboeken spelen door als je de speler sluit.** Het spelerscherm sluiten stopt het afspelen niet meer: je kunt verder bladeren door je bibliotheek terwijl het boek doorloopt, met bediening op het toegangsscherm. Het boek opnieuw openen koppelt weer aan de lopende weergave, op de juiste positie.
- **Ingesproken boeken (zoals van Grim Books) spelen betrouwbaarder door met het scherm op slot**, en pauzeren nu netjes bij een telefoontje of Siri — met automatisch hervatten na afloop. Voorheen bleef de voorlezing na zo'n onderbreking stil hangen.
- **Veiligheid en stabiliteit:** een kwaadaardig EPUB-bestand kan niet langer bestanden buiten zijn eigen cache-map schrijven; twee verschillende boeken met dezelfde bestandsnaam tonen niet langer elkaars inhoud; en de app declareert nu een privacy-manifest (geen tracking, geen dataverzameling).

## 2.63 — 2026-07-01

- **Voorlezen speelt weer betrouwbaar door op de achtergrond.** De lockscreen-bediening uit 2.62 bleek de achtergrond-audio te verstoren (het voorlezen stopte zodra je naar het beginscherm ging); die toevoeging is teruggedraaid. Het voorlezen loopt nu weer ononderbroken door op de achtergrond en met het scherm op slot, zoals in 2.61.

## 2.62 — 2026-07-01

- **Voorlezen heeft nu bediening op het toegangsscherm en in Bedieningspaneel.** Titel, auteur en omslag van het boek verschijnen in het "speelt nu"-paneel, met knoppen voor afspelen/pauzeren en de vorige/volgende zin — ook met het scherm op slot. Voorheen had alleen de audioboek-speler dit.

## 2.61 — 2026-07-01

- **Voorlezen speelt nu door op de achtergrond en met het scherm op slot.** Voorheen las de voorleesstem één zin, stopte en wachtte — waardoor iOS de app op de achtergrond schorste en het geluid na de eerste zin stilviel. De resterende zinnen van een hoofdstuk worden nu in één keer klaargezet, zodat het voorlezen ononderbroken doorloopt.
- **Lees-sjablonen** staan in Instellingen nu als een navigeerbare lijst in plaats van een keuzemenu.

## 2.60 — 2026-07-01

- **De app is niet meer kaal zonder Grimmory-server:** Start (Lees verder/Recent toegevoegd) en Schrijvers vullen zich nu met je eigen lokaal geïmporteerde of via WebDAV gedownloade boeken, ook zonder serververbinding. Series blijft voorlopig leeg — dat vraagt nog nieuwe metadata die nog niet uit boeken gelezen wordt.
- **Boeken toevoegen via bestandskiezer:** een "+"-knop in "Mijn boeken" opent de Bestanden-app als alternatief voor "Open met…".

## 2.59 — 2026-07-01

- **Bug uit 2.58 hersteld: bladeren via swipe deed het niet meer.** De vorige release liet tikken op knoppen/video-bediening in de pagina doorvallen naar de webweergave, maar die wijziging blokkeerde per ongeluk ook de swipe-gesture zelf. Bladeren werkt weer; knoppen/video-bediening in de pagina zijn (net als vóór 2.58) bereikbaar na het openen van de bedieningsbalk.
- **Taal, leeftijdscategorie, uitgever, datum en beschrijving** uit het boek zelf worden nu gelezen en getoond bij geïmporteerde/WebDAV-boeken, inclusief boeken die de nieuwere `dcterms:`-metadatavorm gebruiken in plaats van de klassieke `dc:*`-elementen.

## 2.58 — 2026-07-01

- **Knoppen/links in de paginatekst weer aantikbaar:** de vorige swipe-only-wijziging blokkeerde per ongeluk óók gewone knoppen, video-bediening en links in de pagina zelf, niet alleen het bladeren. Tikken vallen nu door naar de webweergave; swipen blijft gewoon werken om te bladeren.
- **`<epub:trigger>` ondersteund:** boeken die knoppen declaratief koppelen aan acties (afspelen/pauzeren/dempen van video of audio, zonder eigen script) deden voorheen niets — geen enkele browser-engine interpreteert dit uit zichzelf. Grim Reader bekabelt dit nu zelf (play/resume/pause/stop/mute/unmute/show/hide).

## 2.57 — 2026-06-30

- **Bladeren alleen via swipe:** een tik ergens op de pagina liet altijd óf direct naar de vorige/volgende pagina springen, óf (op video-pagina's) de bedieningsbalk opspringen — allebei voelde onvoorspelbaar, vooral als je een verkennende tik deed op een pagina met video. Tikken doet nu niets meer behalve de onderste strook die de balk opent; bladeren gaat voortaan uitsluitend via swipe.

## 2.56 — 2026-06-30

- **`navigator.epubReadingSystem` toegevoegd:** boeken met eigen scripts (EPUB3 "scripted content") kunnen nu detecteren wat de lezer ondersteunt, zoals de spec voorschrijft. Gemeld als geen muis-events (een touch-toestel heeft er geen), zodat scripts die daarop letten netjes terugvallen op native bediening.
- **`linear="no"`-pagina's overgeslagen:** een omslagpagina die in de spine buiten de normale leesvolgorde staat (zoals bij het EPUB3-voorbeeldbestand "A Shared Culture") verscheen voorheen ten onrechte als gewone eerste pagina, dubbel op met het al aparte omslagscherm van de app. Wordt nu overgeslagen, zoals de spec voorschrijft.

## 2.55 — 2026-06-30

- **Video in EPUB's speelt nu af:** `autoplay`-video startte nooit vanzelf (WKWebView blokkeert dat standaard zonder gebruikersactie), en de onzichtbare bladerlaag onderschepte ook elke tik bedoeld voor de eigen afspeelknop van de video. Beide zijn gefixt: autoplay-video start nu vanzelf, en op pagina's met video maakt de bladerlaag plaats na de eerste tik zodat de video-bediening bereikbaar wordt.

## 2.54 — 2026-06-30

- **EPUB3 Media Overlays (voorlezing met echte audio):** boeken die per pagina een ingesproken audiospoor + SMIL-synchronisatie bevatten (zoals Grim-books die genereert) tonen nu een "Voorlezing afspelen"-knop met de eigen audio van het boek, in plaats van alleen de robotstem-voorleesfunctie. Speelt automatisch door naar de volgende pagina als die ook audio heeft, met pauzeren en vorig/volgend fragment.

## 2.53 — 2026-06-30

- **Elegantere offline-weergave:** zonder internetverbinding verbergt de app nu tabs en secties die een server nodig hebben (Start, Alle boeken, Series, Schrijvers, Favorieten, Zoeken, Servers en Internet boeken) in plaats van overal losse "Kan niet laden"-foutmeldingen te tonen. "Mijn boeken" en Instellingen blijven gewoon werken; zodra de verbinding terugkomt, verschijnen de andere tabs vanzelf weer.
- **Achtergrondafbeelding ook bij geïmporteerde boeken:** de template-instelling `image_book_card_bg` werkte al op de detailpagina van serverboeken, maar niet bij boeken die je zelf importeert of download. Dat is nu gelijkgetrokken.

## 2.52 — 2026-06-30

- **Cover bij geïmporteerde boeken:** EPUB's die je via "Open met…" of AirDrop importeert tonen nu hun ingebedde omslag (plus titel en auteur uit het bestand) in de bibliotheek, net als bij WebDAV. Voorheen bleef de cover leeg.

## 2.51 — 2026-06-28

- **Achtergrondafbeelding op de boekdetailpagina:** `image_book_card_bg` in het template vult nu de bovenste kaart (omslag + titel + auteur) op de detailpagina. Aanbevolen afmeting: ≥ 1290 × 900 px.

## 2.5 — 2026-06-27

- **Commentaar in template-JSON:** je kunt nu `//` en `/* */` commentaar in `template.json` zetten; de app negeert dit netjes bij het inlezen.
- **Template verwijderen schakelt direct terug naar Standaard:** als je het actieve template verwijdert, springt de app meteen naar het Standaard-template.

## 2.4 — 2026-06-27

- **Transparantie van boekenkaarten instelbaar:** voeg `"card_opacity"` (0.0–1.0) toe aan je template om de secties "Lees verder", "Recent toegevoegd" enz. doorzichtig te maken zodat een achtergrondafbeelding doorschijnt.
- **Templates verwijderen:** in Instellingen verschijnt een verwijderknop zodra je een zelfgemaakt template selecteert. Ingebouwde templates kunnen niet verwijderd worden.
- **Kerst-template verwijderd:** het ingebouwde kerstthema is uit de app gehaald.

## 2.3 — 2026-06-27

- **Achtergrondafbeelding van geïmporteerde templates werkt nu correct:** na het importeren toonde de achtergrondafbeelding soms niet. Dit is verholpen.
- **Vorig gekozen template wordt onthouden:** de app herinnert na herstarten welk template je had geselecteerd.

## 2.2 — 2026-06-27

- **Templates importeren via .grimtemplate-bestanden:** deel een `.grimtemplate`-bestand via AirDrop, Mail of de Bestanden-app, of gebruik de importknop in Instellingen → Weergave. Het bestand is een gewone zip met een `template.json` en optionele afbeeldingen.
- **OpenDyslexic-ondersteuning:** stel `"font_body": "opendyslexic"` in om het ingebouwde OpenDyslexic-lettertype in te schakelen — de EPUB-lezer schakelt automatisch mee.
- **Meerdere templates:** je kunt meerdere templates installeren en via de picker in Instellingen wisselen.

## 2.1 — 2026-06-27

- **Achtergrondafbeelding in templates:** voeg `"image_background"` toe aan je template voor een eigen foto of illustratie als achtergrond van het startscherm. Aanbevolen afmeting: ≥ 1290 × 2800 px.

## 2.0 — 2026-06-27

- **Templates passen nu de volledige app-stijl aan:** kleuren, lettertypen, hoekradius en slagschaduw uit het template worden toegepast in het startscherm en de boekdetailpagina. Het Standaard-template blijft het systeem-uiterlijk volgen (inclusief donkere modus).

## 1.98 — 2026-06-26 *(eerste App Store-release)*

- **Onderhoud opgeschoond:** de opties "Boeken zonder auteur aanvullen" en "Boeken
  zonder cover aanvullen" zijn verwijderd (werkten nog niet betrouwbaar).
- **Onder de motorkap:** compiler-waarschuwingen weggewerkt (actor-isolatie in de
  audioboekspeler en wat ongebruikte code), zodat de build schoon is en Swift 6-klaar.

## 1.97 — 2026-06-26

- **Diagnose-weergave verwijderd:** nu de eerste tik op Vertalen betrouwbaar de
  juiste paginatekst pakt, is de tijdelijke "Diagnose (tijdelijk)"-sectie en de
  bijbehorende interne meet-code weggehaald.

## 1.96 — 2026-06-26

- **Eerste tik op Vertalen pakt nu meteen de juiste paginatekst:** het
  vertaalscherm werd geopend via een aparte aan/uit-schakelaar terwijl de tekst in
  losse toestand stond, waardoor de sheet die tekst soms nog leeg inlas (de "0
  tekens / geen debug"-meldingen). De paginatekst reist nu mee als het item dat het
  scherm opent, dus het scherm krijgt gegarandeerd precies de uitgelezen pagina.

## 1.95 — 2026-06-26

- **Vertalen leest de pagina nu zonder reflow-race uit:** de uitlezing zette vlak
  vóór het meten de pagina-transform tijdelijk uit en mat soms op de oude posities,
  waardoor de eerste tikken leeg terugkwamen en hij op het hele hoofdstuk terugviel.
  De transform wordt nu niet meer aangeraakt; de paginapositie wordt rechtstreeks
  uit de live-transform berekend, robuust voor 1 én 2 kolommen. (Diagnose staat nog
  één build aan om dit te bevestigen.)

## 1.94 — 2026-06-26

- **Tijdelijke diagnose terug in de vertaalweergave:** toont de interne
  leestoestand (o.a. scroll-modus, pagina, kolommen, lengte) om te achterhalen
  waarom het vertalen nog het hele hoofdstuk pakt. Wordt na de fix weer verwijderd.

## 1.93 — 2026-06-26

- **Vertalen pakt nu correct de huidige pagina, ook met twee kolommen:** de
  paginatekst werd bepaald door af te ronden op één staprondte, waardoor de tweede
  kolom (en soms de hele pagina) buiten beeld viel en hij terugviel op het hele
  hoofdstuk (traag). De zichtbare tekst wordt nu bepaald op de x-band van de pagina,
  met een terugval op wat letterlijk in beeld staat. De korte herpoging is ingekort.

## 1.92 — 2026-06-26

- **Vertalen pakt nu betrouwbaar de huidige pagina, ook bij de eerste tik:** de
  oorzaak was een timing-race — bij de eerste tik was de pagina-uitlezing nog niet
  gereed, waardoor hij leeg terugkwam en op het hele hoofdstuk terugviel (traag). De
  app probeert de zichtbare paginatekst nu kort opnieuw tot die beschikbaar is.
- **Tijdelijke diagnose verwijderd** nu de oorzaak gevonden is.

## 1.91 — 2026-06-26

- **Diagnose aangescherpt:** de tijdelijke diagnose-info wordt nu synchroon vastgelegd
  vóór het ophalen van de paginatekst, zodat zichtbaar wordt of de uitlees-koppeling
  tussen de lezer en de vertaalweergave wel aankomt. Helpt om te bepalen waarom de
  paginatekst leeg bleef. Wordt na de fix weer verwijderd.

## 1.90 — 2026-06-26

- **Tijdelijke diagnose in de vertaalweergave:** toont onder "Diagnose (tijdelijk)"
  hoeveel paginatekst wordt opgehaald, om te achterhalen waarom het vertalen het hele
  hoofdstuk pakte in plaats van de huidige pagina. Wordt in een volgende versie weer
  verwijderd.

## 1.89 — 2026-06-26

- **Vertalen pakt nu daadwerkelijk alleen de huidige pagina:** de vorige poging las
  de zichtbare tekst nog niet goed uit en viel terug op het hele hoofdstuk (traag).
  De paginatekst wordt nu betrouwbaar bepaald, zodat alleen wat op het scherm staat
  vertaald wordt.

## 1.88 — 2026-06-26

- **Vertalen pakt nu echt alleen de huidige pagina:** in 1.87 viel hij soms terug
  op het hele hoofdstuk (en was daardoor traag). De app leest nu betrouwbaar alleen
  de tekst die op het scherm staat, ongeacht de paginaopmaak.

## 1.87 — 2026-06-26

- **Vertalen vertaalt nu alleen de huidige pagina:** voorheen ging de hele
  hoofdstuktekst eronderdoor, wat lang duurde. De app pakt nu precies de tekst die
  je op het scherm ziet.
- **Voortgangsbalk in plaats van een tollend wieltje:** je ziet nu hoe ver het
  vertalen is (met percentage), en bij de eerste keer dat een taalpakket nog
  gedownload moet worden de melding "Taalpakket voorbereiden…".

## 1.86 — 2026-06-26

- **OPDS-catalogi met inloggen:** vereist je eigen OPDS-bron een gebruikersnaam en
  wachtwoord, dan kun je die nu invullen bij de catalogus (Instellingen → Servers). De
  app stuurt ze mee bij bladeren en downloaden; het wachtwoord staat veilig in de
  Keychain. Vraagt een bron om inloggen en heb je niets ingevuld, dan zie je een
  duidelijke melding in plaats van een onbekende fout. https blijft vereist.
- **Vertalen (proef) robuuster:** de brontaal wordt nu netjes uit de boekgegevens of de
  tekst afgeleid (ook als de metadata een afwijkende taalcode bevat), en bij een niet-
  ondersteunde talencombinatie krijg je een melding in plaats van een eindeloos
  draaiend wieltje.

## 1.85 — 2026-06-26

- **Downloaden van eigen OPDS-catalogi werkt nu:** boeken van een zelf-gehoste OPDS-bron
  (bijvoorbeeld Calibre-Web) die over http draait, gaven een beveiligingsfout. De app
  staat nu verbindingen met je eigen opgegeven servers toe, net als bij je NAS.
- **OPDS-catalogi bij je servers:** je eigen OPDS-bronnen voeg je nu toe onder Instellingen
  → Servers, samen met je Grimmory- en WebDAV-servers, via één "Server toevoegen"-knop.
- **"Ontdek" heet nu "Internet boeken":** duidelijker waar je gratis boeken van het
  internet vindt.

## 1.84 — 2026-06-26

- **Je blijft langer ingelogd op je Grimmory-server:** een tijdelijke serverhapering
  (bijvoorbeeld als de NAS net even herstart) meldt je niet meer onnodig af. Pas als je
  aanmelding echt is verlopen, kom je terug op het inlogscherm.
- **Vertalen (proef) werkt nu echt:** koos je een taal die je nog niet had, dan bleef het
  bij een tollend wieltje. iOS vraagt nu netjes om het taalpakket te downloaden, en de
  brontaal wordt uit de boekgegevens gehaald (of anders automatisch herkend).

## 1.83 — 2026-06-26

- **Eigen OPDS-catalogi:** voeg in Instellingen je eigen OPDS-bron toe (bijvoorbeeld een
  Calibre-Web-server of een andere OPDS-feed). Die verschijnen onder Ontdek naast de
  ingebouwde bronnen, met bladeren, zoeken en downloaden.
- **VoiceOver houdt je leespositie beter vast:** schakel je VoiceOver in tijdens het lezen,
  dan blijft de lezer nu staan waar je was in plaats van naar het begin van het hoofdstuk te
  springen.
- **Vertalen (proef):** op iOS 18 en nieuwer kun je een hoofdstuk on-device laten vertalen
  via een nieuwe knop in de leesbalk. Dit is een eerste experiment — de tekst wordt zonder
  opmaak getoond.

## 1.82 — 2026-06-26

- **Swipen om te bladeren:** veeg in de EPUB-lezer naar links voor de volgende pagina en
  naar rechts voor de vorige — naast het bestaande tikken links/rechts. De veegbeweging
  werkte voorheen niet doordat de tekstweergave hem opslokte; dat is nu verholpen.

## 1.81 — 2026-06-25

- **VoiceOver houdt je leespositie vast:** zet je VoiceOver aan (of weer uit) terwijl je
  een EPUB leest, dan blijft de lezer nu staan waar je was, in plaats van terug te springen
  naar het begin van het hoofdstuk. De positie wordt bij het wisselen tussen kolom- en
  doorlopende voorleesweergave bewaard.

## 1.80 — 2026-06-25

- **Uitloggen houdt je in de app:** log je uit van je Grimmory-server, dan kom je nu
  netjes terug in het hoofdmenu (met Mijn boeken, Ontdek en je WebDAV-servers) in plaats
  van vast te lopen op het accountscherm. En na een herstart word je niet meer naar het
  Grimmory-inlogscherm gedwongen zodra je de app eenmaal hebt gebruikt — opnieuw inloggen
  kan altijd via Instellingen.

## 1.79 — 2026-06-25

- **De app werkt nu ook zonder Grimmory-server:** wil je alleen boeken van een
  WebDAV-server (NAS, Nextcloud e.d.) lezen, dan kun je vanaf het inlogscherm meteen
  een WebDAV-server toevoegen zonder eerst op een Grimmory-server in te loggen. De
  Grimmory-specifieke onderdelen (Start, Series, Schrijvers, Bibliotheken, Zoeken,
  Onderhoud …) blijven dan netjes verborgen; je ziet enkel je servers, Mijn boeken en
  Ontdek. Log je later alsnog in op een Grimmory-server, dan verschijnt alles vanzelf.
- **Onderhoud opgeruimd in Instellingen:** de beheerdersfuncties voor je Grimmory-
  bibliotheek (duplicaten, samenvoegen, metadata aanvullen …) staan nu samen onder één
  "Onderhoud"-knop in plaats van los onder elkaar.
- **Geen storende balk meer:** de rode "geen verbinding"-strook onderaan is verdwenen;
  schermen die niet kunnen laden tonen zelf al een melding.

## 1.78 — 2026-06-25

- **Boeken van een WebDAV-server bewerken:** open je een boek van een WebDAV-server,
  dan kun je nu via het potlood titel, auteur, taal en omschrijving aanpassen — net
  als bij je eigen boeken in "Mijn boeken". Je kunt ook de cover vervangen via een
  online zoekopdracht, een foto of een bestand. De wijzigingen worden bewaard in de
  `books.yaml` op de server zelf, zodat ze op al je toestellen verschijnen; heb je het
  boek gedownload, dan worden de gegevens daar meteen mee bijgewerkt.
- **Rustiger overzicht:** het mapicoon ("Bladeren per map") is uit het serverboeken-
  raster gehaald; het scherm toont nu enkel je boeken.

## 1.77 — 2026-06-25

- **Voortgang tijdens het scannen van een WebDAV-server:** loopt de app map voor
  map door de server, dan zie je nu live "X mappen doorzocht · Y boeken" onder de
  spinner, en een balkje bovenaan als je een al gevulde lijst vernieuwt — zodat je
  ziet dat hij nog bezig is in plaats van enkel een tollend wieltje.
- **Bibliotheek laadt direct op een tweede toestel:** na een scan bewaart de app de
  hele boekenstructuur als `books.yaml` op de server zelf (naast `authors.yaml`).
  Open je dezelfde server op een ander toestel, dan verschijnt de bibliotheek meteen
  uit die index in plaats van opnieuw de hele mappenboom te scannen; covers vullen
  daarna vanzelf aan. Op een alleen-lezen share blijft het bij de gewone scan.

## 1.76 — 2026-06-25

- **Schrijversinfo bij WebDAV-boeken:** open je een boek van een WebDAV-server, dan
  zoekt de app de schrijver op (Wikipedia) en toont een portret met een korte bio.
  Die gegevens worden bewaard in een eigen `authors.yaml` op de server zelf, zodat ze
  bij je bibliotheek horen en op al je toestellen beschikbaar zijn — en offline in een
  lokale cache. Op een alleen-lezen share blijft het bij de lokale cache.
- **Overal hetzelfde openen:** tik nu op de cover van een boek om het te openen — bij
  je eigen boeken en WebDAV-boeken net zoals bij de Grimmory-bibliotheek.
- **Sneller scannen van grote WebDAV-bibliotheken:** de app probeert de hele mappenboom
  in één keer op te halen. Staat je server dat niet toe, dan valt hij automatisch terug
  op de vertrouwde map-voor-map-scan.

## 1.75 — 2026-06-25

- **Alle boeken van een server in één overzicht:** elke WebDAV-server toont nu een
  raster met álle boeken uit de hele mappenboom, mét cover en titel/auteur. De lijst
  wordt op je toestel onthouden zodat hij niet elke keer opnieuw hoeft te scannen;
  met "Vernieuwen" zoek je opnieuw, en "Bladeren per map" blijft beschikbaar.
- **Eén plek voor al je servers:** in Instellingen staan je Grimmory-bibliotheek en
  WebDAV-servers nu samen onder "Servers". Naast elke server zie je of hij bereikbaar
  is; bij een WebDAV-server geeft een potlood aan dat de app er een eigen mapje voor
  metadata mag bijhouden. Toevoegen gaat via één knop met de keuze Grimmory of WebDAV.

## 1.74 — 2026-06-25

- **Lees boeken van een WebDAV-server:** voeg in Instellingen één of meer WebDAV-
  servers toe (NAS, Nextcloud e.d.) met gebruikersnaam en wachtwoord, blader door de
  mappen en download EPUB- en PDF-boeken. Het wachtwoord staat veilig in de Keychain,
  en met "Verbinding testen" controleer je de server meteen.
- **Covers uit de bestanden zelf:** voor WebDAV-downloads haalt de app de cover uit
  het EPUB of toont de eerste PDF-pagina. De boeken verschijnen bij "Mijn boeken" en
  blijven offline beschikbaar, net als catalogus-downloads.

## 1.73 — 2026-06-25

- **De tekst springt niet meer als je het paneel opent:** tik je tijdens het lezen
  onderaan om de bediening te tonen, dan blijft de pagina nu staan. Eerder schoof de
  statusbalk mee waardoor het boek opnieuw werd ingedeeld en de tekst versprong.
- **Gewijzigde schrijversfoto verandert direct overal:** pas je een auteur aan
  (foto, naam of een online match), dan ververst de portretfoto meteen op elk scherm,
  ook in de lijst "Schrijvers" — net zoals boekkaften dat al deden. Voorheen zag je
  de nieuwe foto pas na het herstarten van de app.

## 1.72 — 2026-06-25

- **You're back where you stopped reading:** when you leave a book and come back,
  it now reliably reopens on the exact page you left off. Before, it could land a
  page or two earlier — for PDFs the very last page turn wasn't always saved before
  closing, and for EPUBs the restored page could get nudged back while the page was
  still re-laying out.
- **Tap the cover to open a book:** on a book's page you can now tap the cover image
  itself to start reading (or listening, or to download it first) — the same as the
  button below it.

## 1.71 — 2026-06-24

- **A new cover stays put when you go back:** after you change the cover of a book
  from your Grimmory server, the new image now shows immediately on every screen,
  including the library grid one step back. Previously the cover could briefly go
  blank there and only fill in later, because the app re-fetched it from the server
  before the server had finished saving it. It now reuses the image you just picked.

## 1.70 — 2026-06-24

- **A search bar on every book screen:** every screen with books now has a search
  bar pinned at the top that searches within that screen — All books, each
  library, shelf and smart shelf, a series, an author's books, and My books.
- **Search everything from the home screen:** a search field right under the
  Grim Reader logo searches your whole library.
- **Search bar pinned on the Authors screen** so it's always in reach.
- **Faster edit screen:** opening the edit screen from a book's details no longer
  stalls while it re-formats the description.
- **Covers no longer disappear after you change them:** the new cover is uploaded
  directly instead of asking the server to fetch it, which could fail and wipe the
  existing cover. Missing covers in a library grid also retry instead of staying
  blank.

## 1.69 — 2026-06-24

- **Covers from your Grimmory server refresh straight away:** after you replace
  the cover of a server book, the library updates immediately instead of only
  after restarting the app.
- **More cover choices when searching:** the online cover search now also looks
  on Apple Books, alongside Open Library and Google Books — handy for modern
  titles the others don't have.

## 1.68 — 2026-06-24

- **Author and series pages now show their books:** when an author or series had
  stray spaces in its stored name, the page showed a book count but no books.
  It now falls back to searching, so the books appear just like they do when you
  search for them.
- **Covers refresh straight away:** after you edit a book and change its cover,
  "My books" now updates immediately instead of only after restarting the app.

## 1.67 — 2026-06-24

- **Pick the language from a list:** when editing a book you now choose the
  language from a searchable list of languages instead of typing free text, so
  it's always stored consistently.
- **Edit Grimmory books too:** administrators can now edit the title, author,
  language and description of books from your Grimmory server — including the
  online "search the whole book" auto-fill and online cover search — just like
  for your own local books.
- **Read-aloud now scrolls and highlights:** starting read-aloud switches the
  reader to scroll mode and highlights the sentence being spoken; the highlight
  is now visible in every theme.

## 1.66 — 2026-06-24

- **Edit metadata for your own books:** for books that don't come from your
  Grimmory server you can now edit the title, author, language and description
  from a pencil button on the book screen.
- **Auto-fill book details online:** search Open Library and Google Books for the
  whole book and fill in the title, author, language, description and cover in one
  go — you can still tweak everything by hand afterwards.
- **Change the cover three ways:** an online cover search, a photo from your
  library, or an image file.

## 1.65 — 2026-06-24

- **"Open with …" for EPUB/PDF:** open an EPUB or PDF file from Files or the
  share sheet straight into Grim Reader. The file is saved to your local
  library and opened right away — even when you're not signed in to the server.
- **"Downloaded" becomes "My books":** server downloads and locally added or
  catalogue-downloaded books now sit together in a single grid. Books from your
  own Grimmory server carry a NAS badge on the cover.
- The Discover tab now shows only the catalogues; the downloads section moved
  to "My books".

## 1.64 — 2026-06-23

- **New Discover tab with DRM-free catalogues (Project Gutenberg):** browse
  over 70,000 free public-domain books, download them and read them offline in
  the app. Works independently of your Grimmory server.

## 1.62 — 2026-06-23

- The iPad sidebar no longer jumps back to Favourites: the selected shelf or
  library now stays put.
- The connection check no longer refreshes the view unnecessarily.

## 1.61 — 2026-06-23

- Improvements to the offline demo.

## 1.60 — 2026-06-23

- Renamed the demo button to "Offline demo".
- Polished, code-drawn covers for the demo books.
