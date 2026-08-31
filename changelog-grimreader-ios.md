# Changelog — Grim Reader

All notable changes per release. Newest first.
Versions match the `vX.Y` tags and `CFBundleShortVersionString`.

## Nog niet uitgebracht

## 4.35 — 2026-08-31

- Wisselen tussen Start, Alle boeken, Schrijvers, Series, Strips, Luisterboeken en bronoverzichten begint niet meer telkens vanaf een leeg scherm met een grote laadrotator. De app toont de laatst geladen SQLite-resultaten direct en ververst verouderde inhoud op de achtergrond; taalfilters, zoekopdrachten en sorteringen houden daarbij elk hun eigen resultaat.
- Een bezoek aan een bibliotheekscherm start niet langer zelf een WebDAV-bereikbaarheidscontrole of volledige achtergrondverrijking. Dat werk wordt één keer appbreed gecoördineerd, zodat navigeren niet met NAS-verkeer en databasewerk concurreert.

## 4.34 — 2026-08-30

- Het opslagoverzicht telt alleen echte boek- en luisterboekbestanden mee en rekent downloads van een Grimmory-server bij de juiste categorie. Uitgepakte EPUB-caches worden nu meteen verwijderd met het lokale boek; achtergebleven caches uit oudere versies worden bij de eerste start eenmalig opgeruimd. Daardoor kan **Boeken** niet meer ruim een gigabyte blijven melden nadat alle lokale boeken zijn verwijderd.
- Het seriescherm toont bij ieder boek voortaan de reeks en het deelnummer, en houdt de boeken in leesvolgorde: eerst op deelnummer, bij gelijke nummers op titel en boeken zonder nummer achteraan.
- Import, OPDS, WebDAV en Grimmory-downloads bewaren voortaan dezelfde volledige metadataset. Bestandsmetadata en cataloguscorrecties blijven als aparte lagen bewaard; taal, beschrijving, reeks, genres, ISBN, bijdragers, rechten, doelgroep, paginatal en ComicInfo verdwijnen daardoor niet meer door de gekozen downloadroute of een latere armere lijstverversing. Oudere onvolledige Grimmory-sidecars worden aangevuld zodra de server weer bereikbaar is.
- Schrijvers samenvoegen laat nu vooraf zien hoeveel groepen en schrijfwijzen kunnen worden samengevoegd. Iedere volledige naamregel is een ruime tikzone en toont een lege of gevulde kroon, zodat de te behouden schrijfwijze direct en betrouwbaar gekozen kan worden.

## 4.33 — 2026-08-30

- Opstarten en wisselen tussen bibliotheekschermen is lichter: de app decodeert en sorteert bij de opstartcontrole niet meer de volledige lokale bibliotheek, ComicInfo-verrijking gooit geen ongewijzigde taal- en schrijversfacetten meer weg en veroorzaakt niet langer een algemene herlaadronde. Ook een dubbele herlaadactie in Schrijvers is verwijderd.
- De stripeditor toont bij Serie alleen nog het deelnummer. Het verwarrende veld **Totaal** is verdwenen; een bestaande `Count` in `ComicInfo.xml` blijft gewoon behouden en een metadatazoekresultaat kan hem nog steeds bijwerken.
- Een bewust leeggemaakt stripveld wordt nu ook uit `ComicInfo.xml` verwijderd, terwijl een veld dat een online bron niet levert bestaande metadata ongemoeid laat. Dit geldt voor lokale en WebDAV-strips via dezelfde writer.
- Batchverrijking schrijft een gekozen uitgever en verschijningsjaar nu werkelijk naar de WebDAV-catalogus en, wanneer gevraagd, naar het boekbestand. Eerder stonden deze wijzigingen wel in het voorstel maar bereikten ze de schrijfroute niet.

## 4.32 — 2026-08-30

- De Grand Comics Database-zoeker zoekt na de reeks nu gericht naar het exacte stripnummer. Een GCD-kandidaat kan daardoor de echte albumtitel, publicatiejaar, land, uitgever, paginatal, synopsis, genres, makers en cover tonen; hoofdissues gaan vóór herdrukvarianten en de aanvraag blijft tot vijf details begrensd.
- Stripdetails lezen, tonen en bewerken nu rijke ComicInfo 2.0-metadata: uitgavegegevens, makersrollen, verhaalbogen, personages, teams, locaties, technische gegevens en beoordelingen. De informatie blijft bewaard in SQLite en de optionele serverindex en wordt via dezelfde centrale writer veilig naar lokale en WebDAV-CBZ-bestanden geschreven; ontbrekende API-velden laten bestaande waarden ongemoeid.
- Een handmatig gewijzigd deelnummer van een WebDAV-strip blijft nu staan. Eerder werd alleen een gewijzigde reeksnaam als correctie gemarkeerd; daardoor verscheen een nieuw nummer kort in beeld en won bij de volgende catalogusverversing opnieuw de oude waarde.

## 4.31 — 2026-08-29

- De online stripzoeker herkent nu ook het generieke Grimmory-type CBX en CB7, niet alleen CBZ en CBR. Grand Comics Database staat bij een strip vóór Apple Books en wordt ook geraadpleegd als er al een reeks in ComicInfo staat. Een gevonden reeks en deelnummer worden bij een Grimmory-serverboek en bij batchverrijking voortaan werkelijk opgeslagen en direct in het scherm bijgewerkt.

## 4.30 — 2026-08-29

- Een boek dat je vanuit de rechterkolom bewerkt verandert nu direct mee in de middelste boekenlijst. Een bibliotheekmelding die tijdens pagineren binnenkomt wordt daarna alsnog verwerkt, en herladen springt niet meer terug naar het eerste boek.
- Bij een luisterboek heet de voortgang in de rechterkolom en op de detailpagina voortaan **Luistervoortgang** in plaats van **Leesvoortgang**.
- Boeken zonder reeks kunnen via de metadatazoeker nu een reeks en deelnummer uit Wikidata krijgen. De app volgt de taal van het boek, houdt een handmatige correctie altijd intact en gebruikt waar mogelijk de schrijfwijze die al in je bibliotheek staat.
- Schrijvers uit verschillende online bronnen worden betrouwbaarder gekoppeld via hun NTA-, VIAF-, GND-, ISNI-, BnF-, Wikidata- en Open Library-identiteiten. Daardoor is een gelijkende naam veel minder snel genoeg om de gegevens of foto van de verkeerde persoon over te nemen.
- De onderhoudsactie voor schrijvers gebruikt nu dezelfde rijke bronnen als handmatig zoeken, werkt ook zonder WebDAV-server en bewaart de gevonden identiteiten. De aanvragen worden gedoseerd; bij afknijpen of volledige bronuitval stopt de ronde met een zichtbare melding in plaats van stil door te lopen.
- Strips kunnen metadata opzoeken in de Grand Comics Database. Reeks, nummer, totaal aantal delen en uitgever worden als herkenbare GCD-kandidaat aangeboden en kunnen ook naar `ComicInfo.xml` in een lokaal of WebDAV-CBZ-bestand worden geschreven.
- Grote bibliotheken worden sneller in SQLite bijgewerkt doordat terugkerende database-instructies worden hergebruikt. In de releaseproef daalde het schrijven van 100.000 rijke boekrecords van 41,0 naar 25,2 seconden; taal- en schrijversgroepen worden vooraf opgebouwd en daarna hergebruikt.

## 4.29 — 2026-08-29

- Na het bewerken van een boek vanuit een schrijver wordt de boekenlijst van die schrijver meteen opnieuw uit de catalogus geladen. Titel, taal en schrijver blijven daardoor niet meer oud totdat je het scherm of de app opnieuw opent.
- Tijdelijke onbereikbaarheid van een WebDAV-server wordt niet meer aangezien voor ontbrekende verwijderrechten. Verwijderen blijft beschikbaar wanneer schrijfrecht eerder is vastgesteld, terwijl een onbekende of losgekoppelde server een duidelijke melding geeft.
- De Release-build is weer schoon onder de volledige Swift 6-concurrencycontrole. Omslagcache, bestandswrites, tijdelijke bestanden, verwijderrondes en parallelle zoekresultaten hebben nu expliciete, controleerbare isolatie.

- Boekmetadata heeft nu één gelaagde schrijfroute voor losse bewerkingen, bulk, verrijking en auteurs-/seriesamenvoeging. Handmatige waarden winnen per veld van geaccepteerde externe metadata en bestandsmetadata; ontbrekende API-velden wissen niets. Schrijven naar EPUB/PDF/CBZ rapporteert pas succes nadat het bestand veilig is vervangen, en een zelfgekozen omslag blijft buiten de wisbare covercache bewaard.
- Een WebDAV-luisterboek dat van één bestand naar meerdere delen groeit behoudt nu zijn identiteit. Favoriet, collectie, luistervoortgang en omslag blijven gekoppeld; een onbekend of vervangen bestand kan die identiteit niet zomaar erven.
- Grote reeksen bibliotheekmeldingen blijven nu aantoonbaar begrensd: duizenden WebDAV-indexwijzigingen starten geen lokale bestandsscan, terwijl duizenden lokale imports of verwijderingen tot één scanronde worden samengevoegd. De echte productiemeldingen delen voortaan één expliciete, geteste domeingrens; vijfduizend wijzigingen worden ook in de zichtbare boekenlijsten tot precies één schermverversing gebundeld.
- Bij het verplaatsen of hernoemen van een map met dubbele boeken blijft nu aantoonbaar het exemplaar zichtbaar dat je bij het ontdubbelen koos. Ook de winnaar krijgt een padonafhankelijk kenmerk; migratie van oudere catalogi en groepen met drie of meer kopieën kiezen niet langer op toevallige databaserijvolgorde.
- Handmatige boekcorrecties zijn nu volledig verliesvrij bij een herscan, catalogusherbouw en migratie van een bestaande database: ook meerdere auteurs, bewust leeggemaakte velden, genres, ISBN en bijdragers blijven behouden. Een fout bij het vooraf redden van gegevens wordt niet langer ten onrechte als een geslaagd herstel gemeld.
- Vastgelegd welk onderdeel eigenaar is van boekmetadata, gebruikerscorrecties, schrijversgegevens, omslagen, voortgang, favorieten, collecties, scanstatus en tijdelijke bestanden. De contracttest koppelt iedere SQLite-gebruikersoverlay nu aan haar concrete tabel en bewijst via een echte catalogusherbouw dat handmatige boekcorrecties, genegeerde dubbelen en schrijversprofielen behouden blijven.
- Tijdelijke bestanden zijn nu ook racevrij bij gelijktijdige indexuploads en meerdere geopende stripvensters: registratie gebeurt vóór de eerste schrijfactie, gedeelde paden tellen hun gebruikers en een werkmap wordt pas verwijderd wanneer niemand hem meer gebruikt.
- Een meerdelig WebDAV-luisterboek behoudt ook na een gedeeltelijk mislukte verwijdering zijn identiteit wanneer één bekende track overblijft; favorieten, collecties en luistervoortgang blijven daardoor na de volgende scan gekoppeld.
- De zichtbare teller van een hervatte WebDAV-scan wordt nu samen met de mappenwachtrij in het echte checkpoint bewaard en kan bij het afronden niet meer kort teruglopen.

## 4.28 — 2026-08-28

- **Een luisterboek van meerdere bestanden verwijderen haalt nooit meer de hele map leeg.** De map is bij zo'n boek het "adres", en die verwijderen nam alles mee wat er verder in stond — een omslag, aantekeningen, een ander boek. Nu gaan precies de audiobestanden van dat boek weg, en de map alleen als er aantoonbaar niets meer in staat.
- **Lukt het verwijderen maar half, dan klopt je bibliotheek daarna met wat er echt nog staat.** Eerder bleef het boek alle onderdelen vermelden terwijl een deel al van de NAS was.
- **Je eigen correcties overleven het opnieuw opbouwen van de catalogus.** Titel, schrijver, taal, samenvatting, reeks, uitgever en genres die je zelf hebt aangepast zonder ze naar het bestand terug te schrijven, kwamen daarbij niet terug — een scan leest immers het bestand dat je juist corrigeerde. Schrijversprofielen en weggestreepte dubbelen worden net zo behandeld.
- **Weggestreepte dubbele boeken blijven weg**, ook na een synchronisatie, een herstel vanaf de server, of nadat je het bestand hebt verplaatst of hernoemd.
- **Schrijversgegevens werken nu ook zonder NAS-server.** Bio, foto, website en identiteiten zijn bibliotheekbreed en werden zonder server niet geladen; opslaan bouwde dan een leeg profiel over je gegevens heen. Het bewerkscherm wacht nu tot je gegevens ingeladen zijn voordat je kunt opslaan.
- **Bij een online gekozen schrijversfoto wordt bewaard waar hij vandaan komt**, met een verwijzing naar de Wikimedia-bestandspagina waar de maker en de licentie staan. Dat staat onder het portret in het schrijversscherm. Kies je daarna een eigen foto, dan verdwijnt de oude foto én zijn bronvermelding.
- **"Deze map doorzoeken" ruimt niets meer op als de map niet goed te lezen was.** Een share die tijdelijk een lege lijst teruggeeft, wiste eerder de boeken die eronder stonden. Een map die werkelijk leeg is wordt na een tweede scan alsnog opgeruimd.
- **De app blijft vlot bij het importeren of verwijderen van veel boeken.** Elke wijziging startte een volledige scan van je toestelopslag; die worden nu gebundeld tot één ronde.
- **Een hervatte scan telt door** in plaats van opnieuw vanaf nul, zowel op het scherm als in het eindverslag.
- **Tijdelijke bestanden worden alleen nog opgeruimd als ze van Grim Reader zijn** en er niet aan gewerkt wordt. Een lopende import of upload wordt niet meer onder zijn eigen voeten weggehaald, en bestanden van andere apps worden met rust gelaten.
- De catalogus gaat weer mee in de iCloud-backup; daar staan inmiddels gegevens in die een herscan niet terughaalt.
- Bestanden verplaatsen werkt nu ook wanneer de app op het tweede serveradres zit.
- Pseudoniemen van meerdere woorden uit de KB-schrijversbron blijven heel ("Mary Westmacott" werd "Mary" en "Westmacott").

## 4.27 — 2026-08-27

- **De knoppen om gekozen boeken aan te passen of te verwijderen zijn weer zichtbaar.** Ze stonden in de systeembalk onderin, en die gaat schuil achter de tabbalk van de app. Nu staan ze direct onder je selectie.
- **Bij het verwijderen van gekozen boeken kun je kiezen** of je ze van dit toestel haalt of van je NAS, net als bij één boek. Staat er ook iets bij dat op een Grimmory-server leeft, dan verschijnt daar een aparte knop voor.
- Het filter "Zonder taal" toonde in de selectiebalk een kaal streepje in plaats van zijn naam.

## 4.26 — 2026-08-27

- **Kiezen van meerdere boeken wijst zichzelf beter.** Zodra je begint te kiezen staat er boven de lijst hoeveel je hebt gekozen, een knop om alles of niets te kiezen, en een duidelijke knop **Gereed**. Die laatste zat rechtsboven tussen de andere knoppen en was op een iPhone makkelijk te missen.
- **Alles kiezen kan nu ook zonder taalfilter.** Die knop verscheen alleen als je op een taal had gefilterd, terwijl hij het zonder filter net zo goed doet.

## 4.25 — 2026-08-27

- **Een scan ruimt niet meer op als hij verdacht weinig ziet.** Kon een server maar een handjevol boeken tonen — bijvoorbeeld omdat een gedeelde map niet beschikbaar was — dan werd de rest als "verdwenen" beschouwd en uit je bibliotheek gehaald. Voortaan houdt Grim Reader dat tegen en zegt hij wat hij zag en wat er stond, zodat je eerst kunt kijken wat er met de server aan de hand is.
- **Nieuw: "Boekenindex van de servers terugzetten"** in Onderhoud. Zijn er boeken uit je bibliotheek verdwenen, dan haalt deze knop ze terug uit de index die op je server staat. Wat je op dit toestel hebt aangepast blijft daarbij staan.
- **De app bevriest niet meer bij het één voor één verwijderen van boeken.** Bij elke verwijdering werd de hele bibliotheek opnieuw ingelezen, en herlaadden alle lijsten tegelijk. Nu gebeurt dat op de achtergrond en worden opeenvolgende wijzigingen samengevat.
- **De praktijkmeting is uit Onderhoud verdwenen**, en bovenaan die sectie staat nu duidelijk dat deze hulpmiddelen je bibliotheek veranderen en dat sommige acties niet ongedaan te maken zijn.
- Acht meldingen die nog in het Nederlands verschenen — foutteksten over de index en de server — zijn nu ook in het Engels beschikbaar.

## 4.24 — 2026-08-27

- **De taalbalk staat er nu altijd, ook bij één taal — en er is een filter "Zonder taal".** Daarmee vind je in één tik de boeken waar nog geen taal bij staat, wat precies de boeken zijn die je wilt aanvullen. Je kunt het ook combineren: Nederlands én de boeken zonder taal.
- **De gegevens van een schrijver zijn nu te corrigeren.** Geboortejaar, plaatsen, nationaliteit, beroepen, prijzen en website staan als velden in het bewerkscherm. Klopt er iets niet uit de bronnen, dan pas je het aan — en een volgende zoekopdracht overschrijft jouw tekst niet.
- **Schrijversgegevens en -foto's reizen mee naar een tweede apparaat.** De nieuwe velden staan in de `authors.yaml` op je server, en je zelfgekozen foto's komen in een map ernaast te staan.
- **Je eigen schrijversfoto's konden verdwijnen.** Ze stonden in een map die iOS mag legen als de opslag krap wordt, en die niet meegaat in de iCloud-backup. Ze staan nu bij de rest van je gegevens.
- **Je handwerk gaat weer mee in de iCloud-backup.** De catalogus werd overgeslagen omdat hij "opnieuw op te bouwen" was, maar er staan inmiddels ook aangepaste schrijversgegevens in en welke dubbele boeken je hebt opgeruimd. Dat komt met een nieuwe scan niet terug.

## 4.23 — 2026-08-27

- **Schrijversgegevens worden niet meer bij het openen opgehaald.** Grim Reader ging tot nu toe het internet op zodra je een schrijver opende zonder bewaarde gegevens. Dat gebeurt niet meer: alles komt uit je eigen bibliotheek, en ophalen doe je zelf.
- **Daarvoor in de plaats staat er een knop "Gegevens ophalen"** in het schrijversscherm. Die vult alleen lege velden aan — een biografie of foto die je zelf hebt gekozen blijft staan. Vindt hij niets, dan zegt hij dat.

## 4.22 — 2026-08-27

- **Een bewerking is meteen zichtbaar.** Paste je een boek aan, dan bleef het scherm waar je stond de oude titel tonen tot je zelf ververste. Alle boekenlijsten en de rechterkolom bewegen nu mee: Alle boeken, de bibliotheeklijst, schrijvers, series, collecties, favorieten, luisterboeken en het startscherm.
- **Een schrijver krijgt niet langer de biografie en foto van iemand anders.** Grim Reader zocht op Wikipedia in de tekst van artikelen in plaats van op de naam, en nam de eerste treffer over. Bij A.G. Riddle leverde dat de foto en het levensverhaal van Val Kilmer op. Er wordt nu gecontroleerd of het gevonden artikel werkelijk over die schrijver gaat — en zo niet, dan blijft het veld leeg. Dat is beter dan een geloofwaardige onwaarheid.
- **Meer over een schrijver:** geboorte- en sterfplaats, literaire prijzen en een aantikbare link naar zijn eigen website. Die stonden al in Wikidata, maar werden niet opgehaald.

## 4.21 — 2026-08-26

- **Apple Books is erbij gekomen als boekenbron, en wordt als eerste geraadpleegd.** Voor Nederlandse uitgaven is dat verreweg de rijkste gratis bron: een Nederlandstalige beschrijving, genres, het jaar van uitgifte en een omslag. De nationale bibliotheek blijft ernaast staan voor wat Apple niet levert — ISBN, uitgever, omvang en serie — en dezelfde uitgave uit beide bronnen wordt één treffer met het beste van allebei.
- **Er wordt gezocht in de winkel die bij het boek hoort.** Een Nederlands boek in de Nederlandse, een Frans boek in de Franse. Weet de app de taal niet, dan die van jou. Dit was de reden dat er zelden een omslag werd gevonden: er werd altijd in de Amerikaanse winkel gezocht, en die kent de Nederlandse uitgaven grotendeels niet.
- **Omslagen worden ook op ISBN gezocht.** Dat wijst precies jouw editie aan in plaats van de hele familie eromheen.
- **Bij elk zoekresultaat staat nu waar het vandaan komt.**
- **Opgehaalde boekdetails verdwijnen niet meer** als je een ander boek kiest en terugkomt.

## 4.20 — 2026-08-26

- **Een aangepaste zoekterm werkt nu echt.** Vond Grim Reader niets en paste je de zoekterm aan — precies wat het scherm je aanraadt — dan bereikte die aanpassing alleen de algemene bronnen. De Koninklijke Bibliotheek bleef zoeken op de titel zoals die in het bestand staat, en dat is meestal juist de reden dat er niets gevonden werd.
- **Rommel in de titel wordt weggelaten bij het zoeken.** Een titel uit een bestandsnaam sleept van alles mee: het jaartal vooraan, de oorspronkelijke titel tussen haakjes, een formaat- of taalaanduiding. Daar vindt een catalogus niets bij. Grim Reader zoekt nu op de kale titel, en je ziet in het zoekveld waarop gezocht wordt zodat je het kunt bijstellen.
- **Schrijvers worden veel vaker gevonden.** Staat een schrijver in je bibliotheek als "Achternaam, Voornaam" — zoals catalogi en veel e-boeken hem bewaren — dan vonden Wikidata en Wikipedia daar niets bij. De naam wordt nu omgedraaid voor de bronnen die dat nodig hebben.
- **VIAF is als bron vervallen**; die dienst weigert al zijn verzoeken en liet zonder melding een deel van de resultaten wegvallen. De naamvarianten die het leverde komen nu uit de Koninklijke Bibliotheek, inclusief pseudoniemen.
- **Sorteren in het serieoverzicht doet weer wat het zegt.** Op aantal boeken, naam, recent toegevoegd of voortgang — geen van vieren werkte, alleen bij "Naam" viel dat niet op.

## 4.19 — 2026-08-26

- **Nederlandse boeken worden veel vaker gevonden.** Grim Reader vraagt de Koninklijke Bibliotheek nu ook als de taal van een boek nog niet bekend is — en dat is precies de situatie waarin je metadata gaat zoeken. Hij raadt de taal uit de titel; zit die gok ernaast, dan gebeurt er niets bijzonders en zoekt hij verder zoals eerst. Ter illustratie: van "De zeven wijzerplaten" van Agatha Christie kent de KB zeventien uitgaven, terwijl Open Library er geen enkele heeft.
- **Schrijversgegevens uit de Nederlandse Thesaurus van Auteursnamen.** Bij "Ook online zoeken" wordt nu ook de naamsautoriteit van de KB geraadpleegd: een Nederlandstalig levensbericht, geboorte- en sterfjaar en pseudoniemen. Daar hangt vaak een Wikidata-verwijzing aan, en daarmee komt ook de foto binnen. Staat de app in het Nederlands, dan wint een Nederlandse tekst voortaan van een langere Engelse.
- **Voorlezen werkt nu ook bij Nederlandse boeken die niet in UTF-8 zijn opgeslagen.** Bij zulke boeken — vooral oudere uitgaven — kwam er geen tekst uit het bestand, waarna het voorlezen zonder melding niets deed terwijl het boek gewoon te lezen was. Grim Reader herkent de tekencodering nu zelf. En als er werkelijk geen tekst te halen valt, zegt hij dat voortaan in plaats van stil te blijven.
- **Meerdere boeken in één keer verwijderen.** Kies je meerdere boeken, dan staat er naast "Aanpassen" nu een prullenbak. Je kiest of je de kopieën van dit toestel weghaalt — die zijn opnieuw te downloaden — of de bestanden definitief van je NAS. Met een teller en een stopknop, en zonder schrijfrechten is de NAS-optie uitgeschakeld met de reden erbij.

## 4.18 — 2026-08-26

- **Het boekmenu zit nu ook in de schermen waar het nog ontbrak:** bij een schrijver, in de boekenlijst van een bibliotheek, bij zoekresultaten op het startscherm en bij luisterboeken. Houd een boek ingedrukt om het aan een collectie toe te voegen of te verwijderen — van dit toestel, van je NAS of van de server, net wat er bij dat boek kan.

## 4.17 — 2026-08-26

- **Na het opruimen van dubbele boeken wordt je bibliotheek niet opnieuw doorzocht.** Dat gebeurde wel, en bij een grote bibliotheek kostte dat minuten wachten op iets wat de app al wist: van een opgeruimde groep blijft één versie over, dus die groep is geen groep meer. Breek je het opruimen halverwege af, dan blijft de rest van de lijst gewoon staan.

## 4.16 — 2026-08-26

- **Het ontdubbelen bevriest niet meer.** Bij een grote bibliotheek liep de app vast zodra hij dubbele boeken ging zoeken: het wegen van de versies deed per vergelijking een schijfcontrole, en dat liep op de hoofdthread. Het vergelijken gebeurt nu op de achtergrond en elke versie wordt nog maar één keer gewogen.
- **Je ziet nu wat hij doet, en je kunt stoppen.** Het scherm toont de fase — boeken ophalen, vergelijken — met een teller erbij, en er is een stopknop tijdens zowel het zoeken als het opruimen. Tijdens het opruimen zie je hoeveel boeken er al weg zijn.
- **"Alles selecteren" staat nu standaard uit**, zoals bij schrijvers samenvoegen. Een lijst waarin alles al aanstaat nodigt uit tot één tik op opruimen zonder te kijken, en daar verdwijnen bestanden van je NAS mee.

## 4.15 — 2026-08-26

- **Dubbele boeken opruimen.** Onder Instellingen > Onderhoud servers zoekt Grim Reader boeken die meer dan één keer in je bibliotheek staan — zelfde titel én schrijver, waarbij hoofdletters, accenten en leestekens niet meetellen — en stelt per groep voor welke versie je houdt. Die keuze kijkt naar hoeveel er is ingevuld, of er een omslag is en welk formaat het is, en staat erbij zodat je ziet waarom. Je kunt per groep een andere versie kiezen of alles in één keer selecteren.
- **Ook zonder schrijfrechten bruikbaar.** Zijn de bestanden op je server niet te verwijderen, dan staat die schakelaar uit met de reden erbij. De niet-gekozen versies verdwijnen dan alleen uit je bibliotheek — en komen bij een volgende scan niet terug, ook al staan de bestanden er nog.
- **Hetzelfde boekmenu in elk scherm.** Toevoegen aan een collectie, van dit toestel verwijderen, van de NAS verwijderen en van de server verwijderen zitten nu overal waar een boek staat. Wat je ziet hangt af van het boek: van de NAS alleen bij een server waar de app op mag schrijven, van de server alleen met beheerdersrechten.
- **"Van dit toestel verwijderen" is nieuw.** Op een server waar je niet mag schrijven was dat het enige wat je kon opruimen, en het kon nergens. Bij een boek dat ook op een server staat gaat alleen de kopie weg; bij een boek dat je zelf hebt geïmporteerd waarschuwt de app dat het echt weg is.

## 4.14 — 2026-08-25

- **Je kunt nu kiezen hoe lang omslagen bewaard blijven.** Bij een grote bibliotheek bewaart de app een omslag voor elk boek, terwijl je er maar een deel van bekijkt. In Instellingen > Opslag kies je tussen alles bewaren (zoals het was) of alleen wat je de laatste 7, 30, 90 of 365 dagen hebt gezien. Onder de keuze staat meteen hoeveel er buiten die termijn valt en wat het oplevert. Kom je zo'n boek weer tegen, dan wordt de omslag opnieuw opgehaald; je boeken en gegevens blijven ongemoeid.
- **De catalogus geeft niet meer op als hij even bezet is.** Er wordt op twee manieren in de database geschreven, en botsten die, dan gaf dat direct een fout in plaats van een korte pauze. Dat kon zich voordoen tijdens een scan terwijl je door je bibliotheek bladerde.

## 4.13 — 2026-08-25

- **Afgebroken downloads laten geen gigabytes meer achter.** Een download zet eerst een bestand in de tijdelijke map; bij een goede afloop verhuist dat naar je bibliotheek, maar bij een mislukking of als je hem afbrak bleef het staan — bij een strip of een luisterboekdeel honderden megabytes per keer, en niets ruimde het ooit op. Elke download ruimt nu zijn eigen bestand op, en bij het starten wordt opgeruimd wat er nog stond.
- **Omslagen en schrijversfoto's worden als HEIC bewaard.** Gemeten op echte omslagen scheelt dat nog eens 39% ten opzichte van JPEG, bij dezelfde kwaliteit. Bestaande omslagen worden omgezet zodra je ze comprimeert en houden ondertussen gewoon hun beeld. Kan een toestel geen HEIC maken, dan blijft het JPEG.
- **Omslagen van gedownloade en geïmporteerde boeken worden nu ook verkleind.** Die gingen buiten de verkleiner om en werden op volle grootte bewaard.
- **Een verwijderde server laat geen halve scanronde meer achter.** Voegde je diezelfde server later opnieuw toe, dan pakte de scan de oude ronde op en ruimde daardoor verdwenen boeken niet op.

## 4.12 — 2026-08-25

- **Het opslagscherm telt nu alles.** Het keek alleen naar de mappen die het zelf kent en sloeg de caches en tijdelijke bestanden over, waardoor het minder meldde dan je toestel. Het totaal komt nu uit de hele map van de app, met de bekende posten eraf getrokken — zo klopt de optelsom altijd.
- **Drie posten erbij, alle drie op te ruimen.** Uitgepakte boeken (elk EPUB dat je opent wordt uitgepakt en blijft staan zodat het de volgende keer meteen opent), overige caches (afbeeldingen van het web en voorleesbestanden) en tijdelijke bestanden (restanten van downloads die niet zijn opgeruimd). Er is een knop om die drie in één keer weg te gooien; ze worden vanzelf opnieuw gemaakt.

## 4.11 — 2026-08-25

- **Omslagen van verdwenen boeken worden opgeruimd.** Verdween een boek van je server, dan wiste de scan wel het boek uit de bibliotheek maar bleef de bewaarde omslag staan — voorgoed. Hetzelfde bij een boek dat verhuist naar een andere map. Bij een grote bibliotheek stapelt dat stil op. De scan ruimt ze nu mee op, en in Instellingen > Opslag verschijnt een knop zodra er omslagen zijn die bij geen enkel boek meer horen, met hoeveel het er zijn en wat het oplevert. Staat er niets in de catalogus, dan gebeurt er niets: dan is niet vastgesteld dát iets verweesd is.

## 4.10 — 2026-08-25

- **Een luisterboek van meerdere bestanden speelt weer af.** Zo'n boek wordt als één boek getoond, maar de tracklijst werd op sommige plekken niet meegelezen. De app dacht dan dat het boek uit één bestand bestond — en dat "bestand" is de map waar de delen in zitten. Afspelen deed niets, er was geen titel en bewerken lukte niet, terwijl de schrijver wél zichtbaar was.
- **Nietszeggende tags maken niet langer de titel kapot.** Bij luisterboeken met per hoofdstuk getagde bestanden werd het meest voorkomende album blind als boektitel genomen; staat daar overal een streepje, dan heette je boek een streepje. Een waarde moet nu door minstens de helft van de delen gedeeld worden en gaat door een zeef die streepjes, losse cijfers en verzamelnamen als "unknown" of "various" weigert. Zegt het album niets, dan blijft de mapnaam de titel. Dat voorkomt ook dat een hoofdstuknaam als schrijver in je bibliotheek belandt.
- **Alles wat opnieuw op te halen is blijft uit je iCloud-backup.** Niet alleen de omslagen en schrijversfoto's, maar ook de serverindexen en de catalogusdatabase. Bij een grote bibliotheek scheelt dat tientallen gigabytes in je backup. Je collecties en de schrijversfoto's die je zelf hebt gekozen blijven er wel in; die zijn niet terug te halen. In Instellingen > Opslag staat nu of het aanstaat.
- **Comprimeren werkt nu ook bij tienduizenden omslagen.** Het liep één bestand tegelijk en stopte zodra je het scherm verliet. Nu vier tegelijk, met een voortgangsbalk en een stopknop, en het gaat door als je wegnavigeert. Afbeeldingen worden iets kleiner bewaard dan eerst, wat bij een grote bibliotheek ruwweg de helft scheelt zonder zichtbaar verschil.

## 4.09 — 2026-08-25

- **Instellingen > Opslag laat zien waar de ruimte op je toestel heen gaat.** Per soort: luisterboeken, boeken, omslagen, schrijversfoto's, de catalogus en de rest, met een streepje voor de verhouding. Zonder dat is er geen antwoord op "de app neemt gigabytes in beslag" — en of dat nu gedownloade audio of omslagen zijn, maakt voor wat je eraan kunt doen alle verschil.
- **Omslagen en schrijversfoto's worden nu verkleind bewaard.** Wat er stond was wat de bron toevallig gaf: de omslag zoals hij in het EPUB zit, bij een strip de eerste pagina op volle scanresolutie, een portret op 800 pixels breed. In beeld komt daar een rastercel van een paar honderd punten van terecht. Nieuwe afbeeldingen worden meteen verkleind, en met één knop haal je ook wat er al staat door de verkleiner — inclusief teller van wat er is vrijgemaakt. Afbeeldingen met doorzichtigheid blijven ongemoeid, en wat al klein genoeg is wordt overgeslagen, zodat een tweede ronde geen kwaliteit kost.
- **Omslagen en foto's kunnen in één keer gewist worden.** Ze worden opnieuw opgehaald zodra je een boek of schrijver bekijkt. Je boeken, leesvoortgang, favorieten en zelf gekozen schrijversfoto's blijven ongemoeid.
- **De cachemappen gaan niet meer mee in je iCloud-backup.** Het zijn gegevens die opnieuw op te halen zijn; die hoeven je backup niet groter te maken. De catalogus blijft er bewust wél in, want daarin staan de nummers waar je favorieten en leesvoortgang aan hangen.

## 4.08 — 2026-08-25

- **Het tweede serveradres voor onderweg werkt nu echt.** In 4.07 werd er alleen naar dat adres uitgeweken als je toevallig de serverlijst in Instellingen had geopend; ging je meteen naar je boeken, dan bleef Grim Reader op het onbereikbare thuisadres proberen. Het uitwijken zit nu in elk verzoek: loopt de verbinding stuk, dan gaat het tweede adres eenmalig op de proef en wordt het bij succes onthouden. Bij het starten van de app wordt bovendien meteen uitgezocht welk van de twee antwoordt, zodat je niet eerst een time-out van tientallen seconden uitzit. Een afgekeurd wachtwoord telt niet als verbindingsprobleem, en werken beide adressen niet, dan krijgt het thuisadres bij de volgende poging weer de voorkeur.

## 4.07 — 2026-08-25

- **Een server kan nu een tweede adres krijgen voor onderweg.** Ben je niet thuis maar via Tailscale of een VPN met je NAS verbonden, dan wijkt Grim Reader uit naar dat tweede adres zodra het eerste niet antwoordt. Je bibliotheek verandert er niet van: er wordt niets opnieuw doorzocht en je leesvoortgang en favorieten blijven staan. Beide adressen moeten wel op dezelfde map wijzen — alleen het IP of de hostnaam mag verschillen.
- **Vanuit de mappenweergave kun je nu één map doorzoeken.** Handig als je één map met boeken hebt toegevoegd: dat scheelt de minuten die een volledige scan van een grote bibliotheek kost. Boeken buiten die map blijven ongemoeid, ook als daar intussen iets is verdwenen.
- **Zoeken in het schrijversscherm doorzoekt eerst je eigen bibliotheek.** Online bronnen zijn een aparte knop geworden, zodat je niet op Open Library, VIAF, Wikidata en Wikipedia hoeft te wachten voor de vraag die er meestal toe doet: staat deze schrijver er al onder een andere schrijfwijze?
- **Een schrijver kiezen neemt nu ook zijn beschrijving en foto over.** Eerder veranderde alleen de naam en bleven de gegevens van de vorige schrijver staan. Heeft de gekozen schrijver geen beschrijving, dan wordt dat veld leeggemaakt in plaats van de oude tekst te laten staan.
- **Meer schrijvers krijgen een foto bij het zoeken.** Treffers uit Open Library tonen nu hun portret, en wie er dan nog geen heeft krijgt er alsnog een uit Wikidata. Schrijvers die al in je bibliotheek staan tonen hun eigen foto in de zoeklijst.

## 4.06 — 2026-08-24

- **Mappen met meerdere audiobestanden verschijnen nu als één luisterboek.** Grim Reader groepeert MP3-, M4A-, M4B-, AAC- en OPUS-delen per diepste map, sorteert op disc-/tracktags met natuurlijke bestandsvolgorde als terugval en bewaart de afspeellijst in SQLite en `books.yaml`. De speler loopt zonder onderbreking door alle delen, bewaart één totale positie, toont de delenlijst en ondersteunt hervatbare downloads van het hele boek voor offline gebruik.
- **Bij schrijvers samenvoegen kun je nu ook ‘Achternaam, Voornaam’ behouden.** Een komma-naam en dezelfde naam in gewone volgorde komen in één groep. Naast het voornaam-eerstvoorstel toont Grim Reader een netjes opgemaakte komma-variant als afzonderlijke doelkeuze.

## 4.05 — 2026-08-24

- **Lokale downloads en imports worden nu crashveilig bewaard.** Grim Reader vervangt boekbestand, metadata en omslag als één transactie met automatisch herstel na een schrijffout of onderbroken app. Een bestaande leesbare kopie blijft behouden en onvolledige boek/metadata-paren verschijnen niet in de bibliotheek.
- **WebDAV-verrijking herstelt nu van tijdelijke leesfouten.** Een mislukte Range-aanvraag of download wordt niet langer als voltooid opgeslagen en verlaagt de openstaande teller niet. Korte storingen krijgen begrensde retries met wachttijd; bewust niet ondersteunde audioformaten blijven wel een geldige eindtoestand.
- **Lees- en luistervoortgang kan niet meer terugspringen door trage netwerkwrites.** EPUB, PDF, strips en audioboeken gebruiken één geordende wachtrij per boek en mediatype. Er loopt maximaal één PUT tegelijk, tussentijdse posities worden samengevoegd tot de nieuwste en een mislukte laatste positie krijgt begrensde retries.
- **Definitief verwijderde boeken verdwijnen nu overal.** Eén centrale cleanup verwijdert na een geslaagde Grimmory-, WebDAV-, import- of OPDS-delete de stabiele boeksleutel uit zowel favorieten als alle collecties. Een mislukte serverdelete of het verwijderen van alleen een offline kopie behoudt die koppelingen juist.
- **Oude zoekantwoorden kunnen actuele lijsten niet meer overschrijven.** Start en het moderne iPad-luisterboekenscherm gebruiken beheerde taken plus een monotone generatie voor zoekterm, taal, sortering en alle pagina's. Zelfs wanneer een backend te laat op annulering reageert, mag alleen de nieuwste aanvraag nog boeken, metadata, foutstatus of selectie wijzigen.
- **Grote bestanden blokkeren “Open met Grim Reader” niet meer.** Kopiëren, fingerprinting, boekgegevens/omslag uitlezen en crash-veilig opslaan draaien buiten de hoofdthread. De import toont de fasen kopiëren, lezen en opslaan, kan vóór het opslaan veilig worden geannuleerd en serialiseert gelijktijdig aangeboden bestanden.
- **Runtime-meldingen volgen nu werkelijk de app-taal.** Fouten, onderhoudsresultaten en automatisch gemaakte hoofdstuk- en deelnamen worden als gelokaliseerde strings opgebouwd in plaats van Nederlandse modeltekst. De vertaaltest bewaakt voortaan ook zichtbare String-state en bekende model-fallbacks, terwijl technische identifiers en logs buiten beschouwing blijven.

## 4.04 — 2026-08-24

- **Oude schrijvers verdwijnen nu betrouwbaar na hernoemen of samenvoegen.** Ook wijzigingen van alleen hoofdletters en alle schrijfwijzen die alleen in hoofdletters verschillen worden meegenomen. De auteurslijst, het open schrijversdetail, foto's en verrijkte profielen verversen direct en verhuizen naar de nieuwe naam.
- **Meerdere echte schrijvers blijven afzonderlijk bewaard.** SQLite, `books.yaml`, downloads en de EPUB-writer gebruiken voortaan een auteurslijst in plaats van tekst op komma's te splitsen. Daardoor blijft `Achternaam, Voornaam` één schrijver, terwijl alle afzonderlijke `dc:creator`-elementen wel behouden en gericht herschreven worden. Ook series toont namen met komma's correct.
- **De upgrade van bestaande schrijversindexen is veiliger.** De v9→v10-migratie herstelt fout gesplitste WebDAV-namen zonder echte auteursrelaties van lokale boeken te wissen. Onderhoud werkt op de fysieke NAS-regel, ook als hetzelfde boek al is gedownload, en een SQLite-schrijffout kan een bulkbewerking niet meer eindeloos laten herhalen.

## 4.03 — 2026-08-24

- **De schrijverslijst toont direct de nieuwe naam na hernoemen of samenvoegen.** Het overzicht krijgt na een voltooide auteurswijziging een gericht ververssignaal en wacht bij lokale boeken tot SQLite werkelijk is bijgewerkt, ook wanneer het totale boekaantal gelijk blijft.

## 4.02 — 2026-08-24

- **De actie ‘Samenvoegen’ blijft altijd zichtbaar.** In het schrijversscherm staat de knop voortaan in een vaste onderbalk, samen met de actuele voortgang en resultaatmelding, zodat je bij een lange lijst niet meer naar beneden hoeft te scrollen.
- **Samengevoegde schrijvers blijven ook na een herstart samengevoegd.** De nieuwe auteursnaam wordt voortaan als een bewuste metadatawijziging beschermd tegen oude gegevens uit `books.yaml` of een ongewijzigd boekbestand. Het scherm wacht bovendien tot lokale en gedownloade boeken daadwerkelijk in SQLite zijn bijgewerkt, zodat verwerkte schrijfwijzen ook direct verdwijnen.

## 4.01 — 2026-08-24

- **De recent toegevoegde schermen zijn nu volledig in het Engels vertaald.** Dit omvat het zoeken naar bestaande schrijvers, schrijvers samenvoegen, voortgang van bulkbewerkingen, EPUB-reparatie en selectie onder een taalfilter.

## 4.00 — 2026-08-24

- **Het boekaantal op een schrijverspagina volgt nu het gekozen taalfilter.** Zowel de kop als ‘Boeken van …’ tonen het aantal boeken in de geselecteerde taal in plaats van het totale aantal van de schrijver.
- **Een schrijver zoeken controleert voortaan eerst je eigen bibliotheek.** In het bewerkscherm verschijnen bestaande schrijvers uit de lokale SQLite-catalogus direct bovenaan, inclusief hun boekaantal en een duidelijke melding dat kiezen de namen samenvoegt. Resultaten van Wikipedia en andere online bronnen volgen daaronder.
- **Schrijvers samenvoegen volgt nu een vaste naamstijl en vereist een bewuste selectie.** De optie om boekbestanden bij te werken staat bovenaan, iedere schrijversgroep staat standaard uit en met één schakelaar kun je alles selecteren. De voorgestelde naam gebruikt hoofdletters voor voor- en achternamen, kleine Nederlandse tussenvoegsels, punten na initialen zonder tussenliggende spaties en nooit losse interpunctie aan het einde van de naam.

## 3.99 — 2026-08-24

- **Schrijvers samenvoegen toont nu iedere verwerkingsstap.** Na het herschrijven van de boekbestanden zie je afzonderlijk de voortgang van de catalogusupdate en daarna de afronding van lokale gegevens, schrijversfoto's en de vernieuwde schrijverslijst. Daardoor lijkt een grote bewerking niet meer stil te staan wanneer de eerste teller klaar is.
- **Bulkbewerkingen tonen voortaan ook de voortgang ná het schrijven van de bestanden.** Bij onder meer het wijzigen van de taal zie je afzonderlijk het voorbereiden, herschrijven van boekbestanden, bijwerken van de SQLite-bibliotheek en vernieuwen van de boekenlijsten.
- **Metadataresultaten zijn beter te vergelijken.** Iedere kandidaat vermeldt hoeveel en welke details de bron levert. ‘Over dit boek’ krijgt een eigen bronvermelding en, wanneer direct beschikbaar, een korte voorvertoning.

## 3.98 — 2026-08-24

- **EPUB-reparatie kan voortaan optioneel ondubbelzinnige technische metadatafouten opruimen.** De nieuwe instelling staat standaard uit. Zet je hem aan, dan verdwijnen lege en dubbele identifiers, krijgen geldige ISBN's het juiste schema, krijgen makerrollen geldige OPF-prefixen en worden herkenbare datum/tijdwaarden een gewone ISO-datum. Met de instelling uit wordt alleen een daadwerkelijk gewijzigd veld gerepareerd; een gekozen taal wordt bijvoorbeeld één consequente standaardcode. Taalmarkeringen van echte anderstalige passages blijven behouden.
- **Alle boeken onder een actief taalfilter zijn in één keer te selecteren.** De actie neemt ook resultaten mee die nog niet in beeld of geladen zijn en werkt in algemene boekenlijsten, schrijverdetails en afzonderlijke WebDAV-bronnen.
- **Ook de testcode is vrij van waarschuwingen die onder Swift 6 compileerfouten worden.**
- **Dubbele WebDAV-schrijvers kunnen optioneel ook in de boekbestanden worden samengevoegd.** De nieuwe schakelaar staat standaard uit. Met de optie aan worden EPUB-, CBZ- en PDF-bestanden veilig één voor één herschreven; een mislukt bestand blijft met zijn oude schrijver in de catalogus staan en wordt in het resultaat genoemd.

## 3.97 — 2026-08-24

- **EPUB-metadata wordt bij het bewaren automatisch opgeschoond.** Grim Reader bewaart voortaan precies één canonieke taalcode en maakt bestaande taalmarkeringen in het boek en de inhoudsopgave consequent. Ontbreekt de technische omslagverwijzing terwijl er een duidelijke coverafbeelding aanwezig is, dan wordt die veilig hersteld.
- **Alle lokale en WebDAV-bewerkingsroutes gebruiken dezelfde EPUB-writer.** Ook oudere bewerkingsschermen geven de volledige bestaande metadata mee, zodat een wijziging van alleen titel, schrijver of omslag niet ongemerkt taal, serie of genres verliest. De Grimmory-serverroute is niet gewijzigd.

## 3.96 — 2026-08-23

- **Taalfilters tonen na iedere appstart dezelfde complete selectie.** Verschillende schrijfwijzen voor dezelfde taal, zoals `nl`, `nld` en `Dutch`, blijven één Nederlandse chip maar worden bij het zoeken allemaal meegenomen. Daardoor verdwijnen of verschijnen niet langer willekeurig boeken wanneer je Grim Reader opnieuw opent.

## 3.95 — 2026-08-23

- **YAML-indexen worden alleen nog op jouw verzoek naar de NAS geschreven.** Scannen, bewerken, verwijderen, schrijvers verrijken en omslagen ophalen werken voortaan uitsluitend de lokale SQLite-catalogus bij. Onder Instellingen → Onderhoud servers staat de nieuwe actie ‘Schrijver- en boekenindexen naar servers schrijven’. Die schrijft `books.yaml` en `authors.yaml` bewust naar alle ingestelde WebDAV-servers en toont de voortgang en eventuele fouten per server.

## 3.94 — 2026-08-23

- **Taalfilters zijn nu beschikbaar in meer bibliotheekschermen.** Je kunt ook bij schrijvers, favorieten, strips en afzonderlijke bronnen op taal filteren. De aantallen en resultaten komen rechtstreeks uit de catalogus en lege talen worden niet getoond.
- **Schrijverspagina's verschijnen merkbaar sneller.** De kop en reeds bekende schrijversinformatie worden direct getoond; de beschrijving en boekenlijst laden daarna onafhankelijk van elkaar, zodat het scherm niet op het langzaamste onderdeel hoeft te wachten.
- **Verrijkte schrijversgegevens staan voortaan in de lokale database.** Biografie, foto-URL, levensdata en externe identifiers zijn offline beschikbaar zonder eerst een serverbestand te lezen. Een schrijver heeft één bibliotheekbreed profiel, ook als diens boeken op meerdere bronnen staan. Bestaande caches worden automatisch overgezet en `authors.yaml` blijft gebruikt voor synchronisatie tussen toestellen.

## 3.93 — 2026-08-23

- **Het gekozen audioboek blijft in de rechterkolom staan.** Afspelen vanaf Start selecteert het audioboek en na pauzeren springt de inspector niet meer terug naar het eerder gelezen EPUB-boek. De actuele luistervoortgang blijft wel meelopen.
- **Meerdere boeken aanpassen rondt netjes af.** Na een geslaagde bulkbewerking sluit het aanpasscherm automatisch. Alleen bij een gedeeltelijke bestandsfout blijft het open om de fout te tonen.
- **Coverdownloads schrijven de gedeelde boekenindex niet meer onnodig weg.** Het ophalen van toestel-eigen omslagen verandert `books.yaml` op de NAS niet meer. Alleen werkelijk gewijzigde gedeelde metadata wordt gebundeld gepubliceerd.
- **Lege taalfilters verdwijnen direct.** Na het verplaatsen van boeken naar een andere taal worden de taaltellingen opnieuw opgebouwd, oude cachewaarden verwijderd en talen met nul boeken niet meer getoond.

## 3.92 — 2026-08-23

- **Audioboeken spelen direct af vanaf Start en de rechterkolom.** De afspeelknop opent niet langer eerst het detailscherm en verandert tijdens het afspelen meteen in Pauzeren. Open je na een gewoon boek een audioboek, dan blijft bovendien het gekozen audioboek actief in plaats van terug te springen.
- **Boeken die je bekijkt krijgen voorrang.** Zichtbare boeken op Start en in de bibliotheek halen hun omslag en aanvullende gegevens als eerste op; achtergrondwerk hoeft daar niet meer op te worden afgewacht.
- **Bulkbewerkingen van taal blijven bewaard.** Na het wijzigen van meerdere boeken worden de filters direct ververst, lege taalfilters verdwijnen en de oude taal keert na een herstart niet terug.
- **WebDAV-bronnen laden volledig en tonen eerlijk waar een scan mee bezig is.** De bronlijst stopt niet meer na de eerste pagina en aan het einde zie je aparte fasen voor verwerken, indexeren en afronden in plaats van een schijnbaar vastgelopen laatste map.
- **Het hervatten van ontbrekende boekgegevens is duidelijker.** De app legt beter uit welke achtergrondtaak wordt voortgezet en wat al voltooid is.

## 3.91 — 2026-08-23

- **Grote WebDAV-bibliotheken gebruiken nog minder geheugen.** De laatste volledige boekenkopie is uit het geheugen verwijderd; boeken, schrijvers en series komen nu rechtstreeks en in pagina's uit SQLite. Ook het gedeelde `books.yaml` wordt in stukken opgebouwd.
- **Scans zijn veiliger en hervatbaar.** Pauzeren en doorgaan begint niet opnieuw, een onleesbare map wist geen geldige bibliotheek en de app laat zien hoeveel boeken nieuw, gewijzigd of verwijderd zijn.
- **Book Details toont beschikbare gegevens onafhankelijk van de bron.** ISBN-10, ISBN-13 en EAN krijgen het juiste label. Een gedownload boek vult ontbrekende beschrijving, taal, genres, uitgever, serie, medewerkers en rechten aan uit het lokale bestand, ook zonder NAS-verbinding.
- **De laatst bekende bibliotheek blijft offline beschikbaar.** Alle boeken, schrijvers en series blijven zichtbaar wanneer de NAS onderweg niet bereikbaar is; alleen een niet-gedownload bestand zelf kan dan niet worden geopend.
- **Praktijkmeting voor grote bibliotheken.** Onder Instellingen → Onderhoud servers staat een meetpaneel voor boekenaantal, SQLite-querytijden, geheugen, scans en offline herstart. Het rapport kan rechtstreeks worden gedeeld.
- **Betrouwbaardere tests.** Testcatalogi zijn geïsoleerd en asynchrone catalogusupdates lopen niet meer door naar een volgende test.

## 3.90 — 2026-08-22

Onder de motorkap. Deze versie bereidt de app voor op hele grote bibliotheken — tienduizenden tot honderdduizend boeken op een NAS. Je ziet er weinig van, behalve dat het sneller en rustiger hoort te zijn.

- **Je bibliotheek staat nu in een database op je toestel.** Tot nu toe werd de hele boekenlijst als één bestand ingelezen en weer weggeschreven. Bij een grote bibliotheek kostte dat bij elke start seconden en veel geheugen. Nu wordt alleen opgehaald wat nodig is. Je bestaande lijst wordt bij de eerste start automatisch overgezet; er gaat niets verloren.
- **De app haalt niet meer elk boek op voor gegevens die hij al heeft.** Na het inlezen van de gedeelde index werd alsnog elk boek van de server gedownload om titel en omslag uit het bestand te halen — bij tienduizenden boeken eindeloos. Wat de index al weet wordt nu overgeslagen, en omslagen worden alleen opgehaald voor de boeken die je in beeld hebt. Wegnavigeren stopt dat werk ook echt.
- **Zoeken en filteren op een serverlijst gaan door de database.** Bij een lange lijst wordt er per keer een stuk geladen in plaats van alles tegelijk, en filteren gebeurt niet meer door de hele lijst na te lopen. Typ je snel achter elkaar, dan verschijnt niet meer kort het resultaat van je vorige zoekterm.
- **Je scrollpositie blijft staan tijdens het doorzoeken van een server.** De lijst sprong terug naar boven zodra er boeken bijkwamen.
- **Een boek houdt zijn plek na een herstart.** Boeken kregen intern bij elke start een nieuw nummer; dat is nu vast.

## 3.89 — 2026-08-22

- **Een boek dat je op je iPad aanpast verschijnt nu ook op je iPhone.** Je toestellen delen een index op de NAS, maar die werd alleen gelezen als een toestel nog helemaal geen bibliotheek had. Daardoor bleef je tweede toestel op oude gegevens staan, ook al klopte alles op de NAS allang. Nu kijkt elk toestel bij verbinding of er een nieuwere versie klaarstaat en neemt die over — één klein bestand, geen volledige doorzoeking. Een boek dat je op dat moment open hebt staan wordt meteen bijgewerkt.
- **Wat je zelf hebt ingevuld blijft van jou, op al je toestellen.** Paste je op de iPad een titel of beschrijving aan, dan was die op de iPhone niet beschermd en kon een herinlezing van het bestand hem alsnog overschrijven. Dat gaat nu mee.
- **Twee toestellen overschrijven elkaar niet meer.** Werken je iPhone en iPad kort na elkaar bij, dan wordt dat opgemerkt en samengevoegd in plaats van dat de laatste het wint.
- **Is de NAS onbereikbaar, dan blijft je bibliotheek gewoon staan.** Ook bij een time-out, een aanmeldfout of een beschadigd indexbestand: er wordt niets gewist en je boeken, talen, series en omslagen blijven zichtbaar.

## 3.88 — 2026-08-22

- **Boekgegevens komen nu van de nationale bibliotheek van je boek.** Zoek je gegevens bij een Nederlands boek, dan wordt eerst de Koninklijke Bibliotheek geraadpleegd; bij een Duits boek de Deutsche Nationalbibliothek en bij een Frans boek de Bibliothèque nationale de France. Die weten van vertaalde uitgaven veel meer dan de algemene diensten: de juiste uitgever, het jaar, de vertaler, de reeks, het aantal pagina's en de oorspronkelijke titel. Levert de nationale bibliotheek niets op, dan wordt alsnog bij Open Library en Google Books gekeken. In het zoekscherm kun je de bron ook zelf kiezen.
- **Het zoekscherm laat zien wat voor uitgave je voor je hebt.** Een verzamelband of een stripbewerking van een roman is als zodanig gemarkeerd, en de vertaler, de reeks en het paginatal staan erbij. Bij een strip komen stripbewerkingen juist bovenaan, bij een gewoon boek juist niet.
- **Alle zichtbare boeken in één keer verrijken.** Nieuw in de werkbalk van je boekenlijsten en bij een NAS-server. Het gaat over de boeken die op dat moment in de lijst staan, dus filteren op schrijver of taal bepaalt wat er meegaat. Je ziet eerst per boek en per veld wat er zou veranderen en wat er nu staat, en vinkt zelf af wat je toepast. Boeken waarover twijfel bestaat staan uit tot je er zelf naar kijkt, en een veld waarover de bibliotheek niets weet blijft staan zoals het was. Je kiest of alleen Grim Reader wordt bijgewerkt of ook de boekbestanden zelf.
- **Een boek dat je buiten de app hebt aangepast wordt nu helemaal opnieuw ingelezen.** Veranderde je op de NAS de serie of haalde je de taal of de beschrijving eruit, dan bleef de oude waarde staan. Nu volgt alles het bestand — behalve wat je zelf in de app hebt ingevuld, dat blijft van jou.
- **Het bewerkscherm toont de omschrijving die je al had staan.** Die bleef leeg, waardoor je hem per ongeluk kon wissen door gewoon te bewaren.
- **Een wijziging is meteen te zien.** Na Bewaar toonde het boekdetailscherm soms nog even de oude titel of omschrijving.

## 3.87 — 2026-08-22

- **Een boek dat je buiten de app hebt aangepast wordt bij het doorzoeken opnieuw ingelezen.** Bleef het pad hetzelfde, dan hield de app de oude gegevens vast — ook als je het bestand intussen had bijgewerkt. Nu wordt aan de grootte en de wijzigingsdatum gezien dat er iets veranderd is.
- **De taal van een WebDAV-boek komt nu uit het bestand zelf.** Die werd alleen ingevuld als je hem met de hand had ingesteld.
- **Bij het zoeken zie je de serie ook als je op een boektitel zoekt.** Zoek je op de naam van een deel, dan staat de serie waar het bij hoort nu boven de losse boeken.
- **De schrijverskaart in de zoekresultaten toont de foto.** Die keek alleen naar de foto van een Grimmory-server; heb je je schrijvers via WebDAV verrijkt, dan zag je een silhouet.

## 3.86 — 2026-08-22

- **Zoeken vindt nu ook series en schrijvers.** Tik je een serienaam of een schrijver in, dan staan die bovenaan als aparte kaart — een serie van tien delen is zo één resultaat in plaats van tien. Tik op een schrijver en je gaat naar zijn pagina. De losse boeken staan er daaronder.
- **De omschrijving van een boek heet overal hetzelfde.** In het bewerkscherm stond "Samenvatting" en in het boekdetail "Over dit boek", terwijl het om hetzelfde veld gaat. Dat heet nu overal "Over dit boek", en op de iPhone staat die kop er nu ook boven.

## 3.85 — 2026-08-22

- **Het boekdetailscherm toont veel meer van wat er in je bestanden staat.** Bij een strip komen nu de samenvatting, taal, verschijningsjaar, leeftijdscategorie, het aantal pagina's en de tekenaars erbij — inkt, kleuren, letters, omslag en redactie, elk met wat diegene gedaan heeft. Bij een PDF zie je het aantal pagina's en de datum, en bij een boek met meerdere schrijvers staan ze er nu allemaal in plaats van alleen de eerste.
- **Genres en de uitgeverij werken nu ook bij strips.** ComicInfo bevat die gegevens al lang; de app keek er alleen niet naar. Je kunt er dus ook op filteren.
- **De genres staan bovenaan bij het boek**, direct onder de titel en de schrijver, in plaats van halverwege de pagina.
- **Bij een luisterboek wordt de voorlezer niet langer als schrijver getoond.** Die stond in een veld dat de app als auteur las. Ook album, uitgever, genre, jaar en de beschrijving worden nu uit luisterboeken gehaald.

## 3.84 — 2026-08-22

- **Genres uit je boeken, en filteren daarop.** De app leest nu de genres uit een EPUB en toont ze bij het boek. Onder Alle boeken kun je er via het filter op zoeken, en je kunt ze zelf aanpassen — je wijziging gaat het boekbestand in.
- **Meer gegevens in het boekdetailscherm.** ISBN, leeftijdscategorie, medewerkers zoals de vertaler of illustrator, en de rechten. Die stonden vaak wel in het bestand maar werden nooit uitgelezen; voor ISBN en genres lag de weergave er zelfs al klaar.
- **Doorzoeken van een WebDAV-server haalt nu alles op.** Voorheen moest je een boek eerst downloaden om die gegevens te zien. Ze worden ook meegeschreven naar je server, zodat een tweede toestel ze meteen heeft. Bestaande bibliotheken vullen zich bij de volgende scan.
- **Informatie over de uitgeverij bij een boek.** Oprichtingsjaar, land, moederbedrijf en een link naar de website, met het logo als dat te vinden is. Eenmaal opgehaald blijft het op je toestel staan, dus het werkt ook zonder verbinding.

## 3.83 — 2026-08-21

- **De samenvatting en de taal worden nu echt in een EPUB opgeslagen.** Zet je "ook in het boekbestand zelf opslaan" aan, dan bleef je samenvatting soms weg zonder foutmelding — namelijk als het boek daar nog geen veld voor had, wat bij veel EPUB's zo is. Datzelfde gold voor de taal.
- **Ook de serie gaat mee bij je eigen boeken.** Bij een boek van een WebDAV-server werd de serie al in het bestand geschreven, bij een zelf geïmporteerd of gedownload boek niet. En je kon de serie daar niet eens invullen: het bewerkscherm heeft nu velden voor serienaam en deel, net als bij een WebDAV-boek.
- **Een net toegevoegde server geeft niet langer meteen "geen verbinding".** Bij de eerste keer vraagt iOS toestemming voor je lokale netwerk, en de scan die op dat moment al liep strandde daarop. De app probeert het nu vanzelf nog een keer, en er staat een knop "Opnieuw proberen" bij de foutmelding als het langer duurt.

## 3.82 — 2026-08-21

- **Een net toegevoegde server wordt meteen doorzocht.** Voorheen moest je daarna zelf het serverscherm opzoeken en op een knop tikken; deed je dat niet, dan bleef je bibliotheek leeg.
- **Het startscherm meldt geen verbindingsfout meer als er simpelweg nog niets is.** Na het toevoegen van een server stond er "Kan niet laden — geen verbinding met de server" terwijl de verbinding er prima was; de server was alleen nog niet doorzocht. Nu zie je waar je aan toe bent: dat er doorzocht wordt, dat er nog geen boeken zijn, of — als er écht iets mis is — wat de server terugmeldde.
- **Verbinden met een andere Grimmory-server ruimt nu op.** Twee servers geven hun boeken dezelfde nummers, waardoor een boek van de oude server kon doorschuiven naar de nieuwe en de app stil het verkeerde bestand opende. De app waarschuwt nu vooraf en verwijdert daarna de downloads, favorieten en collecties van de vorige server. Je eigen geïmporteerde boeken en alles van een WebDAV-server blijven staan.
- **De instelling voor serielengte begint bij 2 in plaats van bij een lege waarde.** Op een nieuwe installatie stond daar geen getal maar "Toon alle series", wat leest als een leeg veld. Eén boek met een serienaam is ook geen serie.
- **Losse Nederlandse teksten in de Engelse app zijn weg.** Vooral foutmeldingen, maar ook een bevestigingsvraag, een lege-staat en wat VoiceOver voorlas bleven Nederlands. Vijftig teksten toegevoegd aan de vertalingen.

## 3.81 — 2026-08-21

- **Een verse installatie legt nu uit hoe je begint.** Bij de eerste start stond er alleen dat je een boek kon downloaden of een bestand openen — terwijl de app juist om je eigen bibliotheek draait, en die werd nergens genoemd. Er staat nu een welkomstscherm met allebei de manieren: een WebDAV-server, OPDS-catalogus of Grimmory-server verbinden, of een bestand van je toestel openen. Met een knop voor elk, een knop naar de demo, en een link naar polderpijplijn.nl. Je ziet dit alleen zolang je nog nergens een bron hebt ingesteld.
- **De Grimmory-serverinstellingen werken zoals die van WebDAV en OPDS.** Er stond rechtsboven "Overslaan" — een overblijfsel van toen dit nog het inlogscherm bij de eerste start was — en annuleren kon niet. Nu staat "Annuleren" links en "Inloggen" rechts, en sluit het scherm zichzelf zodra het gelukt is. Voorheen bleef het ingevulde formulier gewoon staan en was niet te zien of het had gewerkt.
- **Twee teksten stonden in het Nederlands terwijl de app op Engels stond.** De uitleg onder "Ook in het boekbestand zelf opslaan" bleef bij een EPUB Nederlands, en het land van een schrijver werd altijd in het Nederlands opgehaald — "Verenigd Koninkrijk" in plaats van "United Kingdom". Schrijversgegevens en biografieën volgen nu de taal waarin je de app gebruikt.

## 3.80 — 2026-08-21

- **Een boek toont niet langer even de omslag van een ander boek.** Bij het scrollen kon een cel kort de afbeelding van zijn vorige bewoner laten zien — een strip van Jan Jans met de cover van iets anders, of een schrijversportret bij de verkeerde naam. Het boek zelf was gewoon goed; alleen het plaatje liep achter. Openen en teruggaan herstelde het, nu gebeurt het niet meer.
- **Een boek kan niet meer onder de verkeerde schrijver belanden.** Boeken en schrijvers kregen op je toestel nummers uit dezelfde reeks, waardoor die elkaar bij genoeg boeken konden inhalen — een boek van Asimov verscheen dan onder Pratchett tot je de app opnieuw opende. De twee reeksen staan nu zo ver uit elkaar dat ze elkaar niet kunnen raken.
- **De app blijft leesbaar bij de grootste tekstinstellingen van iOS.** Zet je de systeemtekst op een toegankelijkheidsgrootte, dan werden boektitels afgekapt tot "De Mist…" en schrijvers tot "Lena…", waardoor delen van dezelfde serie niet uit elkaar te houden waren. Het boekenraster gaat nu naar één brede kolom en gunt titel en schrijver meer regels; de "Lees verder"-kaart zet omslag en tekst onder elkaar; en het serveradres in Instellingen loopt door in plaats van af te kappen.

## 3.79 — 2026-08-20

- **Nieuwe optie "Vernieuwen en gegevens opnieuw inlezen" bij een WebDAV-server.** Gewoon vernieuwen kijkt alleen of er boeken bij zijn gekomen; boeken die de app al kent blijven staan zoals ze zijn. Wil je titel, schrijver, serie en omslag opnieuw uit de bestanden laten halen — bijvoorbeeld om striptitels op te halen die er eerder niet goed uit kwamen — dan kan dat nu met deze extra optie. De app vraagt eerst om bevestiging: het haalt elk boek op, en gegevens die je zelf hebt aangepast worden overschreven door wat er in het bestand staat.

## 3.78 — 2026-08-20

- **Bij een strip zie je weer de titel van het album in plaats van de serienaam.** Een strip met serie "Storm", deel 2 en titel "De Laatste Vechter" heette in de app "Storm 2"; die titel raakte je kwijt. Serie en titel staan nu netjes apart. Strips die je al in je bibliotheek had houden hun huidige naam tot je die opnieuw laat doorzoeken — doe dat op elk toestel, anders verschilt het per apparaat.
- **De titel van een strip aanpassen overschrijft niet langer de serienaam.** Wijzigde je de titel van een album dat bij een serie hoorde, dan belandde die tekst in het serieveld — waarmee de hele reeks werd hernoemd.

## 3.77 — 2026-08-20

- **Bij een strip kun je nu kiezen of de nieuwe omslag de eerste pagina vervangt.** Standaard komt hij er als extra pagina vóór, zodat er niets verloren gaat. Begint de strip al met een covertekening, dan zag je die daardoor dubbel — zet de nieuwe schakelaar aan en de bestaande eerste pagina wordt overschreven. Die keuze maak je per strip, want overschrijven kan niet ongedaan worden gemaakt.
- **De getoonde omslag van een strip klopt nu altijd met de eerste pagina in de lezer.** Bij archieven met meerdere submappen, of met paginanamen zonder bestandsextensie, kon de omslag een andere plaat zijn dan de pagina waarmee de strip opent.

## 3.76 — 2026-08-20

- **Een gewijzigde omslag wordt nu ook in het boekbestand zelf opgeslagen.** Tot nu toe bleef die alleen in de app: je zag je nieuwe cover hier wel, maar in elke andere lezer de oude. Bij een EPUB gaat dat zonder aan de inhoud te komen. Een strip heeft geen apart omslagveld — daar wordt de nieuwe omslag als extra eerste pagina toegevoegd, zodat er niets van je bestand verloren gaat; dat staat ook in het bewerkscherm vermeld. Strips waarvan je de omslag al eerder had aangepast moet je één keer opnieuw opslaan.
- **Sommige PDF's konden niet worden bijgewerkt.** Bij een deel van de bestanden — vooral ingescande strips — meldde de app dat bijwerken niet lukte. Die weigering was terecht bedoeld als vangrail (er is nooit een beschadigd bestand weggeschreven), maar de oorzaak was een fout in de app zelf. Dit type PDF werkt nu gewoon.

## 3.75 — 2026-08-20

- **Metadata bijwerken in een PDF laat de rest van het bestand nu met rust.** De app bouwde een PDF bij het opslaan opnieuw op, en daarbij verdwenen dingen die er wél in stonden: de taal en de structuur waar schermlezers op leunen. Bladwijzers bleven gelukkig behouden. Voortaan blijft je originele bestand onaangeroerd en wordt de wijziging er netjes achter gezet, zoals het PDF-formaat daar zelf voor bedoeld is.
- **De taal van een boek wordt nu ook echt in een PDF opgeslagen** — en weer teruggelezen als je hem opnieuw inleest. PDF heeft daar een eigen veld voor dat we tot nu toe niet gebruikten.
- **"Meerdere aanpassen" werkte niet voor PDF's.** Selecteerde je een stapel PDF's en paste je de schrijver of serie aan met "ook in de boekbestanden bijwerken", dan gebeurde er in de bestanden niets — zonder melding. Ook een taalwijziging kwam nooit in het bestand terecht.
- **Bronnen opent hetzelfde boekscherm als de rest van de app.** Via Bronnen → je server → een boek kreeg je een ander, eenvoudiger scherm dan bij "Alle boeken".
- **Bij Bibliotheek staat nu de naam die je je bron zelf hebt gegeven** in plaats van "Op de server" — handig zodra je er meer dan één hebt.
- **Een gedownloade strip toont zijn omslag in "Mijn boeken".** Die bleef leeg, terwijl dezelfde strip één tik verderop wél een omslag had.
- **Spreek je geen Nederlands of Engels, dan is de app nu Engels in plaats van Nederlands.** Wie iOS op bijvoorbeeld Duits of Frans heeft staan kreeg tot nu toe een Nederlandse interface.

## 3.74 — 2026-08-19

- **Metadata bijwerken op een lokaal EPUB, CBZ of PDF schrijft nu ook echt in het bestand zelf.** Deze functie bestond al voor WebDAV; via "Ook in het boekbestand zelf opslaan" in het bewerkscherm werkt hij nu ook voor geïmporteerde bestanden zonder server. Bij een strip staat dit altijd aan, omdat ComicInfo.xml daar de primaire metadata is.
- **Je ziet nu een balkje wanneer een boekbestand wordt bijgewerkt**, met een duidelijke melding als het lukt of mislukt. Deze terugkoppeling bestond al in de mappenbrowser, maar niet op de plek waar je 'm waarschijnlijk het vaakst tegenkomt: de "Bewerk"-knop op het boekdetailscherm. Een mislukte poging bleef daar tot nu toe helemaal onopgemerkt.
- **PDF's met alleen een eigenaarswachtwoord (rechten beperken, vrij leesbaar) kunnen weer bijgewerkt worden.** Kwam vaak voor bij e-books en werd tot nu toe onterecht geweigerd, alsof het bestand écht vergrendeld was.
- **Eerste opstart vraagt niet meer om een Grimmory-login.** Je komt meteen in de app terecht, met lege secties tot je zelf iets toevoegt. Inloggen bij Grimmory kan nog gewoon later via Instellingen.

## 3.73 — 2026-08-19

- **Een handmatig aangepaste titel of auteur van een WebDAV-boek springt niet meer terug naar de oude waarde.** Opslaan leek te lukken, maar de wijziging kwam later — bijvoorbeeld na het bezoeken van Series — stilletjes weer terug op wat er nog in het bestand stond. Gold ook voor "Meerdere aanpassen" (bv. onder een schrijver) en het hernoemen van een schrijver.
- **De tekst bij "Ook in de boekbestanden bijwerken" (bulkbewerking) noemt nu ook PDF.** Dat werkte al net zo goed als bij EPUB en CBZ, maar de tekst zei nog "alleen EPUB en CBZ" en beloofde dus minder dan de app deed.

## 3.72 — 2026-08-19

- **Boekdetails zien er nu overal hetzelfde uit, ook in "Mijn boeken".** Een geïmporteerd of gedownload boek opende voorheen een ander, eenvoudiger scherm dan bijvoorbeeld "Alle boeken" — zonder leesvoortgang, series of categorieën. Nu krijg je overal hetzelfde volledige boekdetailscherm te zien. Bijvangst: "Download verwijderen" op zo'n boek deed voorheen niets; dat werkt nu wel.
- **Een PDF op je eigen server kun je nu ook echt bijwerken.** Titel, auteur, samenvatting en trefwoorden aanpassen ging al, maar de wijziging kwam nooit in het PDF-bestand zelf terecht. Via "Ook in het boekbestand zelf opslaan" gebeurt dat nu wél, met dezelfde veilige route als bij EPUB en strips: eerst een tijdelijke kopie, pas na een geslaagde controle het origineel vervangen. Een beveiligd of digitaal ondertekend PDF-bestand wordt geweigerd. Serie en deelnummer kun je er ook aan toevoegen; PDF heeft daar geen standaardveld voor, dus Grim Reader bewaart dat als een herkenbaar trefwoord.
- **Een audioboek zonder Grimmory-server toont nu zijn omslag** — in de speler en op het lockscreen tijdens afspelen op de achtergrond. Die ontbrak, wat er op sommige toestellen uitzag als een verschil tussen iPhone en iPad, maar in werkelijkheid gold voor alle geïmporteerde, WebDAV- en OPDS-audioboeken ongeacht toestel.
- **Foutmeldingen bij het bewerken van een EPUB of strip zijn nu leesbaar.** Ging er iets mis, dan stond er een kale technische melding in plaats van uitleg — en juist dan wil je weten dat je bestand ongewijzigd is gebleven.

## 3.71 — 2026-08-19

- **"Toon één versie per boek" werkt nu ook bij een bibliotheek met tienduizenden boeken.** De optie uit 3.70 maakte de app traag en kon hem laten vastlopen zodra je hem aanzette op een grote bibliotheek. De app controleerde per boek de omslag door het hele afbeeldingsbestand in te lezen, vergeleek ook boeken die helemaal geen dubbele hebben, en bouwde de boekenlijst bij elk schermonderdeel opnieuw op. Dat gebeurt nu allemaal veel zuiniger.

## 3.70 — 2026-08-19

- **Staat hetzelfde boek meerdere keren in je bibliotheek, dan kun je er nu één laten tonen.** Via Instellingen → Dubbele boeken zet je "Toon één versie per boek" aan. De app groepeert alleen boeken waarvan zowel de titel als de schrijver overeenkomen, en kiest het exemplaar waarin je al aan het lezen bent — en anders het prettigst leesbare bestand. Er wordt niets verwijderd: de andere exemplaren blijven gewoon op de server staan. Standaard staat de optie uit.

## 3.69 — 2026-08-19

- **De app blijft vlot reageren tijdens het doorzoeken van een grote bibliotheek.** Tijdens een scan werd het scherm bij élke doorzochte map opnieuw opgebouwd en de hele boekenlijst opnieuw gesorteerd. Dat gebeurt nu rustiger en op de achtergrond, waardoor het doorzoeken zelf ook sneller gaat.
- **Omslagen worden niet meer telkens opnieuw van schijf gelezen.** Bij het scrollen door een grote bibliotheek werd voor elk boekje in beeld steeds opnieuw het omslagbestand geopend; ze worden nu onthouden.
- **Een serienaam met een aanhalingsteken beschadigt het boekbestand niet meer.** Bewerkte je de serie van een EPUB en stond er een `"` in de naam, dan werden de gegevens ín het boek onleesbaar voor andere leesprogramma's. Bovendien controleert de app een bijgewerkt boek nu voordat het het origineel vervangt: klopt er iets niet, dan blijft het originele bestand staan.
- **Je bibliotheek en collecties raken niet meer beschadigd als de app onverwacht stopt.** Alle lijsten die de app zelf bijhoudt worden nu in één keer weggeschreven in plaats van gaandeweg, zodat er nooit een half bestand achterblijft.
- **Een collectie met veel boeken opent sneller.**

## 3.68 — 2026-08-19

- **Een WebDAV-server met tienduizenden boeken toevoegen laat de app niet meer vastlopen.** Na het inlezen van de boekenlijst van de server bleef de app hangen en werd hij door iOS afgesloten; bij de volgende start meldde die dat de app was gecrasht. Het inlezen van die lijst en het klaarzetten van de omslagen gebeuren nu op de achtergrond en veel efficiënter, zodat de app bedienbaar blijft.

## 3.67 — 2026-08-19

- **Op iPhone staat je WebDAV-bibliotheek er meteen weer na het opstarten.** Na het starten van de app — het duidelijkst na het installeren van een nieuwe versie — toonden Start, Bladeren en Schrijvers alleen de lokale boeken; je WebDAV-boeken verschenen pas zodra je zelf de server opende. Er ging niets verloren: de bewaarde lijst werd alleen niet ingelezen. Op iPad speelde dit niet.

## 3.66 — 2026-08-18

- **Op iPhone opent een boek weer wanneer je het aantikt na "Bekijk alles" op de startpagina.** Via Ontdek, Strips of Luisterboeken naar het volledige overzicht gaan en daar een boek aantikken deed niets; alle andere routes naar een boek werkten wel. Op iPad viel het niet op, omdat een tik daar de kolom ernaast vult.
- **De navigatie werkt nu overal op dezelfde manier.** De schermen achter de tab "Meer" — Favorieten, Bibliotheken, Zoeken en Instellingen — volgen dezelfde opzet als de rest van de app.
- **De app start vlot en zonder vastlopen bij een zeer grote WebDAV-bibliotheek.** De bewaarde boekenlijst wordt nu op de achtergrond ingelezen; bij tienduizenden boeken kon het inlezen de app bij het opstarten laten crashen. Ook het bewaren gebeurt voortaan op de achtergrond.

## 3.65 — 2026-08-18

- **Grote WebDAV-bibliotheken (tienduizenden boeken) scannen nu vlot en zonder vastlopen.** Bij zeer veel boeken werd tijdens het scannen en aanvullen telkens de complete lijst opnieuw gesorteerd en weggeschreven, waardoor het scannen eindeloos duurde en de app na verloop van tijd kon crashen. De app werkt de lijst nu gebundeld bij, zodat het doorzoeken van de mappen niet langer op zichzelf hoeft te wachten.

## 3.64 — 2026-08-18

- **Het boekdetailscherm toont geen leesstatusknop meer, maar je leesvoortgang.** Was je al in een boek bezig, dan staat er nu een balk die laat zien hoever je was — met "Pagina x van y" wanneer dat bekend is, anders het percentage. Nog niet begonnen boeken tonen niets.
- **Boeken op een WebDAV-server tonen nu ook uitgever, verschijningsdatum en beschrijving uit het EPUB-bestand zelf.** Deze gegevens werden al uit het bestand gelezen maar niet bewaard; bestaande bibliotheken lezen ze eenmalig alsnog in.
- **Twee Nederlandse teksten op het detailscherm die in de Engelse app bleven staan zijn vertaald** ("Onbekend" en "Op de server").
- **De rechterkolom van een boek toont geen losse scheidingslijntjes meer** wanneer een boek geen extra details heeft, en lokale boeken zonder schrijver krijgen een duidelijk "Schrijver onbekend"-blok met de hint dat je er zelf een kunt invullen.

## 3.63 — 2026-08-18

- **Een Details-knop in de rechterkolom opent het volledige boekscherm.** Op een brede iPad zet een tik op een omslag de selectie in de kolom ernaast; het uitgebreide scherm met alle gegevens, leesstatus en waardering was daardoor vanuit Start, Alle boeken, Favorieten en Lokale boeken niet meer te bereiken.

## 3.62 — 2026-08-18

- **Het boekdetailscherm gebruikt op een brede iPad de ruimte.** Links het boek met de bediening — omslag, titel, schrijver, serie, de hoofdknop, download verwijderen, leesstatus en de waardering — en rechts "Over dit boek" met daaronder de details als scanbare rijen met pictogram. Op iPhone en in een smal venster blijft de vertrouwde indeling.
- **Boekgegevens aanpassen kan nu ook vanuit de rechterkolom**, op Start en in de bibliotheekoverzichten. Dezelfde knop werkt voor je Grimmory-server, je eigen geïmporteerde boeken en boeken op je WebDAV-server, inclusief online zoeken naar gegevens en omslagen.
- **Een storing bij een naslagbron laat het zoeken niet meer vastlopen.** Toen openlibrary.org uit de lucht was, bleef een scan hangen omdat er een minuut op antwoord werd gewacht. Een bron die niet reageert wordt nu snel overgeslagen; de overige bronnen leveren gewoon hun resultaat.
- **"Pagina x van y" telt bij ieder boek weer het hele boek.** Bij sommige boeken kwam de teller niet verder dan ongeveer het aantal hoofdstukken.

## 3.61 — 2026-08-16

- **Favoriete boeken, strips en luisterboeken hebben op iPad ieder hun eigen correcte detailkolom.** De rechterkolom volgt nu altijd de actieve mediacategorie: bij Boeken kan geen luisterboek meer blijven staan, en onder Luisterboeken kun je een favoriet selecteren en direct in het detailpaneel bekijken.

## 3.60 — 2026-08-16

- **Boeken die je aan een collectie toevoegt zijn nu werkelijk in die collectie zichtbaar.** Collecties vinden lokale, gedownloade, WebDAV- en Grimmory-serverboeken terug; vanuit Alle boeken en andere boekrasters kun je via het contextmenu direct aan een collectie toevoegen.
- **WebDAV-series laden alleen opnieuw wanneer hun inhoud echt verandert.** Het openen of bewerken van één boek vraagt niet langer ongewijzigde series opnieuw op.
- **Serienaam en deelnummer zijn bewerkbaar bij WebDAV-boeken.** Bij EPUB kunnen deze gegevens ook in het boekbestand zelf worden opgeslagen als EPUB 3- en Calibre-metadata.
- **De rechterkolom van Series toont nu ook de schrijver bij ieder boek.** Dit sluit aan bij Alle boeken en de overige bibliotheekoverzichten.
- **WebDAV-boeken kunnen vanuit Series en de algemene boeklijsten definitief van de NAS worden verwijderd**, wanneer de server schrijfrechten bevestigt. Een aparte waarschuwing voorkomt onbedoeld verwijderen; index, omslag en eventuele lokale kopie worden pas na een geslaagde serveractie opgeruimd.

## 3.59 — 2026-08-16

- **WebDAV-series worden nu rechtstreeks uit de volledige serverbibliotheek opgebouwd.** Series combineert lokale en servergegevens, valt bij een onbereikbare Grimmory-server terug op WebDAV en herlaadt zodra de WebDAV-index beschikbaar komt.
- **Oudere WebDAV-indexen worden eenmalig opnieuw op seriegegevens gecontroleerd.** De analyse start vanuit het Series-scherm zelf; gevonden series verschijnen tijdens het proces en blijven lokaal en in de server-sidecar bewaard.
- **Collecties staat nu ook in de iPad-zijbalk**, met dezelfde collectie-interface en boeknavigatie als op iPhone.

## 3.58 — 2026-08-16

- **WebDAV-series bevatten nu de volledige bibliotheek.** Boeken uit de serverindex tellen mee en gedownloade exemplaren behouden hun serienaam en deelnummer.
- **Offline toont Grim Reader alleen boeken die werkelijk op het apparaat staan.** Niet-gedownloade WebDAV-boeken verdwijnen zodra de verbinding wegvalt en komen bij herstel automatisch terug.
- **Schrijversfoto's blijven offline zichtbaar.** Eenmaal opgehaalde Wikipedia- en Grimmory-portretten worden duurzaam lokaal bewaard.
- **Taalfilters zijn voortaan per scherm.** Een taalkeuze in ‘Alle boeken’ beïnvloedt Series, Schrijvers, Strips en Luisterboeken niet meer.
- **Lokale audioboeken met voortgang staan onder ‘Luister verder’** in plaats van onder ‘Lees verder’.
- **Gedownloade WebDAV-boeken verschijnen niet meer dubbel onder schrijvers**, ook niet wanneer hun serverpad percent-encoding bevat.
- **Rechtstreeks hervatten en sluiten verloopt zonder tussenliggende boekdetailflits.**

## 3.57 — 2026-08-16

- **Boeken hervatten zonder storende paginaflits.** EPUB en PDF worden pas zichtbaar nadat de opgeslagen leespositie is hersteld. Sluit je een boek dat je rechtstreeks via ‘Lees verder’ opende, dan keer je terug naar het scherm waar je vandaan kwam.
- **WebDAV scant nu ook diep geneste bibliotheken volledig.** De vaste limiet van acht mapniveaus is verwijderd, terwijl dubbele en cyclische mapbezoeken veilig worden voorkomen.
- **Opgeslagen schrijversfoto's verschijnen direct in het schrijversoverzicht**, zonder dat je een schrijver eerst afzonderlijk hoeft te openen.
- **De app is voorbereid op de strengere Swift 6-concurrencycontrole.** Alle waarschuwingen uit de strikte Release-build zijn opgelost in de reader, vertaling, audio, WebDAV-streaming en menutellers.
- **Het infoscherm beschrijft Grim Reader nu als zelfstandige bibliotheekapp** voor boeken, strips en luisterboeken uit bestanden, WebDAV en OPDS, zonder advertenties of tracking.

## 3.56 — 2026-08-15

- **Luisterboeken spelen nu rechtstreeks vanuit het Luisterboeken-scherm.** De afspeelknop verandert live in pauze, de voortgang volgt de echte luisterpositie en in het detailpaneel kun je terug- en vooruitspoelen of de tijdlijn verslepen. Lokale en WebDAV-audioboeken tonen hun omslag ook op het toegangsscherm.
- **Een auteursprofiel opent altijd met alle talen.** Een taalfilter uit een ander bibliotheekscherm kon de boeken van een schrijver ongemerkt verbergen terwijl de teller wel boeken aangaf.
- **Het Series-scherm blijft op iPhone niet meer blanco** wanneer de apparaatinstelling voor de minimale serielengte alle reeksen wegfiltert. Het scherm legt nu uit wat er gebeurt en biedt direct aan om alle series te tonen.

## 3.55 — 2026-08-15

- **Zoeken naar boekgegevens levert nauwkeurigere resultaten op.** Resultaten uit meerdere bronnen worden slimmer samengevoegd en gerangschikt op ISBN, titel en schrijver, terwijl een tijdelijke storing bij één bron de andere resultaten niet meer tegenhoudt.
- **Schrijvers worden betrouwbaarder herkend en samengevoegd** met blijvende VIAF- en Wikidata-identiteiten, alternatieve namen en aanvullende gegevens. Gelijknamige schrijvers blijven afzonderlijk als hun identiteit niet overeenkomt.
- **Het Series-scherm is volledig vernieuwd voor iPhone en iPad.** Series tonen hun omslagen, voortgang en het eerstvolgende ongelezen deel; op iPad staat de geselecteerde serie in een ruim detailpaneel volgens de mockup.
- **Luisterboeken hebben op iPad een eigen moderne bibliotheekweergave** met zoeken, taalfilter, sortering, luistervoortgang en directe bediening. Het detailpaneel toont de belangrijkste boek- en schrijversinformatie; op iPhone blijft het compacte raster behouden.

## 3.54 — 2026-08-15

- **‘Alle boeken’ opent weer betrouwbaar op iPhone.** De dubbele navigatiestack blokkeerde dit scherm en maakte daarna ook de andere opties onder Bladeren onbruikbaar.
- **Het auteursprofiel heeft op iPad een nieuwe ruime indeling** met een grotere foto, prominente naam, echt boekaantal en een beter leesbare, inklapbare biografie.
- **Boeken van een auteur staan in een herkenbare collectie-sectie** en kunnen worden gesorteerd op titel of publicatiejaar. Op iPhone blijft het profiel compact.

## 3.53 — 2026-08-15

- **Open EPUB-, PDF-, CBZ- en audiobestanden rechtstreeks in Grim Reader** vanuit Bestanden, Mail en andere apps.
- **De navigatie op iPhone en iPad gebruikt nu dezelfde bestemmingen.** Op iPhone blijven de onderste tabs compact via Bladeren en Meer.
- **"Lees verder" opent een aanwezige lokale kopie direct** op de opgeslagen positie en downloadt alleen als het bestand echt ontbreekt.
- **Favoriete strips en luisterboeken staan weer in hun eigen categorie**, ook voor WebDAV en lokale imports.
- **WebDAV-CBZ-metadata wordt veilig in ComicInfo.xml bewaard.** Eerst wordt een tijdelijke kopie geüpload; pas na succesvolle vervanging worden index en caches bijgewerkt.

## 3.52 — 2026-08-15

- **Een schrijver die je bij meerdere strips tegelijk invulde werd stilletjes teruggedraaid.** De app zag zo'n boek nog als "nog te bekijken" en haalde de oude gegevens later opnieuw uit het bestand. Wat je zelf invult wint nu.
- **Het filterscherm gaf een serverfout** als je geen Grimmory-server gebruikt. De filterkeuzes komen nu uit je eigen bibliotheek.
- **Een taal bleef in de balk staan nadat je hem bij het laatste boek had weggehaald.** En bij een serie stonden talen die geen enkel boek in die serie heeft.
- **Is een lijst leeg door een taalfilter, dan staat dat er nu bij** — met een knop om alle talen weer te tonen. Boeken zonder bekende taal vallen namelijk ook buiten zo'n filter.
- De opslaan-knop heette in het Engels "Keep"; dat is nu "Save". Kies je een schrijver bij het zoeken, dan wordt zijn naam meteen ingevuld.
- De naam van de app staat op iPad weer boven de boekenlijst, want in de zijbalk liep hij over twee regels.
- Enkele teksten die in het Engels Nederlands bleven, waaronder de favorietknop en een aantal labels die alleen VoiceOver voorleest.
- Gedimde regels in de keuzemodus waren te licht voor de toegankelijkheidsnorm; die zijn nu beter leesbaar.

## 3.51 — 2026-08-15

- **Bij een EPUB van je server werd je leespositie niet bewaard.** De app zocht het bestand op de plek waar alleen boeken van een Grimmory-server staan, en bood daardoor niets aan om te lezen. Nu werkt het en verschijnt de voortgangsbalk onder "Lees verder".
- **Twee boeken met dezelfde bestandsnaam overschreven elkaar** bij het toevoegen. Ze staan nu naast elkaar; hetzelfde boek nogmaals toevoegen vervangt het zoals voorheen.
- **Verbindingen met een Grimmory-server gaan standaard beveiligd.** Tik je een adres zonder "https://" ervoor, dan wordt dat nu een beveiligde verbinding. Kies je bewust voor een onbeveiligde verbinding, dan krijg je daar een waarschuwing bij.
- Je toegangssleutel staat niet langer in het adres van een audiostream, waar hij in logboeken van servers terecht kan komen.
- De app biedt zichzelf niet meer aan voor CBR-bestanden, die hij niet kan openen.
- Na het downloaden van een boek schakelt de app meteen goed over als de serververbinding wegvalt.

## 3.50 — 2026-08-14

- **Schrijversfoto's verschijnen nu meteen** in plaats van langzaam in te druppelen; ze werden bij elke beweging opnieuw van schijf gelezen. Ook in Favorieten staan ze er nu bij.
- **Luisterboeken hebben een eigen tabblad onder Favorieten**, los van je boeken.
- **Meerdere boeken kiezen kan nu ook op het scherm van een schrijver.**
- **Een wijziging aan een strip leek niet bewaard** wanneer je hem vanuit de mappenbrouwer aanpaste: de map toonde nog de oude titel. Nu zie je je wijziging meteen.
- **Boeken delen vanuit een andere app werkt nu ook voor strips en audioboeken.** Bij een gedeelde strip worden de omslag en gegevens uit het bestand gehaald, net als bij boeken van je server.
- Op iPad staan de naam en het logo van de app bovenaan de zijbalk in plaats van boven de boekenlijst.
- Nog een reeks teksten die in het Engels Nederlands bleven, waaronder de koppen van Strips en Luisterboeken en "Verder lezen" in het detailpaneel.

## 3.49 — 2026-08-14

- **Modern is nu de standaardweergave.** Had je eerder bewust Klassiek gekozen, dan blijft dat zo; je wisselt via Instellingen.
- **Je leespositie werd bij de meeste boeken niet bewaard.** Bij een EPUB of PDF zonder Grimmory-server ging er helemaal niets naar je toestel, en bij strips en luisterboeken werd hij weggeschreven op een plek waar de app zelf niet zocht. Daardoor bleef "Lees verder" op hetzelfde boek staan. Posities van vóór deze versie zijn helaas niet terug te halen.
- **Favorieten bleven leeg als je geen Grimmory-server gebruikt.** Je hartjes waren wel bewaard, maar de lijst kon er niet bij. Ze staan er nu allemaal weer in.
- **Delen van de app bleven Nederlands als je hem op Engels zet**, waaronder de zijbalk, "Bekijk alles" en het hele detailpaneel rechts. Die zijn nu vertaald.

## 3.48 — 2026-08-14

- **De leesvoortgang was nergens te zien bij je eigen boeken.** De app bewaarde hem wel, maar gaf hem niet door aan het scherm — de balk op de "Lees verder"-kaart bleef daardoor altijd weg. Nu staat het percentage er weer bij, samen met wanneer je het boek het laatst open had.
- **Favorieten waren niet te bereiken zonder Grimmory-server.** Je kon een boek wel als favoriet markeren, maar de lijst nergens openen. Die verschijnt nu vanzelf zodra je je eerste favoriet hebt.
- **"Mijn boeken" heet voortaan "Lokale boeken".**
- De kleuren van de Modern-interface zijn aangepast zodat alle tekst en knoppen ook in donkere modus goed leesbaar zijn.
- De "Lees verder"-kaart heeft rustiger verhoudingen: kleinere omslag en compacte knoppen in plaats van knoppen over de volle breedte.

## 3.47 — 2026-08-14

- **"Lees verder" begint nu bij het boek dat je het laatst open had.** Die rij stond in een willekeurige volgorde, omdat de app wel bijhield dát je ergens gebleven was maar niet wanneer. Dat wordt nu vastgelegd zodra je een boek sluit. Boeken die je vóór deze versie las hebben nog geen tijdstip en staan erachter.

## 3.46 — 2026-08-14

- **Het Modern-startscherm en het detailpaneel zijn verder bijgewerkt** naar het beoogde ontwerp, met een eigen kleuraccent voor knoppen.
- **"Bekijk alles" werkt nu overal**: elke sectie op het startscherm brengt je naar de bijbehorende volledige lijst.
- Bij Mijn boeken staat het zoekveld nu boven de boekenlijst in plaats van over het hele scherm, zodat het detailpaneel ernaast blijft staan.
- De leesvoortgang in het paneel klopt weer.
- Instellingen staat op de iPad onderaan de zijbalk, los van de bibliotheekonderdelen.

## 3.45 — 2026-08-14

- **Het detailpaneel van Modern zit nu ook bij Alle boeken, Favorieten en Mijn boeken**, niet alleen op het startscherm. Overal waar je een boekenraster ziet, staat naast je selectie dezelfde context.
- **Nieuw in het paneel: informatie over de schrijver**, opgehaald uit de bronnen die de app al gebruikt en in je eigen taal. Die wordt per boek opnieuw geladen, dus wisselen blijft snel.
- De omslag wisselt nu netjes mee wanneer je een ander boek aantikt.
- In de zijbalk staat Series nu ook bij een WebDAV-server, en een losse pijl is verdwenen.

## 3.44 — 2026-08-14

- **Modern op iPad is verder afgemaakt.** De detailkolom is nu in te klappen, de indeling volgt de werkelijke breedte (dus ook bij draaien of een gesplitst scherm), en je opent een boek rechtstreeks vanuit het paneel.
- Leesvoortgang wordt duidelijker weergegeven, en "Verder lezen" loopt weer gelijk met wat er in het paneel staat.
- De zijbalk is opgeruimd en houdt rekening met je WebDAV-servers.

## 3.43 — 2026-08-14

- **Modern op iPad gebruikt de breedte nu echt.** Naast je bibliotheek staat een vast paneel met het boek dat je hebt aangetikt: omslag, schrijver, serie, taal, leesvoortgang en de omschrijving, met knoppen om te lezen of het boek te bewaren. Op iPhone blijft het rustige startscherm zoals het was.

## 3.42 — 2026-08-14

- **Nieuwe, optionele interface: Modern.** Een rustiger, contentgericht startscherm voor iPhone en iPad. De vertrouwde weergave blijft de standaard en heet nu Klassiek; je wisselt ertussen via Instellingen.
- **Meerdere boeken kiezen kan nu ook tijdens het bladeren door mappen**, en vanuit het scherm van een schrijver of een serie. Voorheen kon dat alleen in het serveroverzicht, terwijl een map met strips juist de plek is waar je een hele reeks in één keer wilt bijwerken. Submappen blijven gewoon te openen terwijl je kiest; alleen boeken zijn aan te vinken.
- Boeken die je via de mappenbrowser aanpast worden meteen aan je bibliotheek toegevoegd, ook als je de server nog nooit hebt doorzocht.
- **Het openen van boekbestanden is grondig beveiligd.** Een geprepareerd boek kon de app dwingen enorme hoeveelheden geheugen te reserveren; er gelden nu grenzen aan de grootte, het aantal bestanden en de compressieverhouding. Een beschadigd bestand meldt zich als beschadigd in plaats van half of leeg te openen, en een schrijffout op je toestel — bijvoorbeeld een volle schijf — blijft niet langer onopgemerkt.
- Boeken die met een wachtwoord beveiligd zijn, of een archief- of compressievorm gebruiken die de app niet kent, worden nu herkend en geweigerd met uitleg.
- Verwijzingen binnen een boek — inclusief de audiobestanden bij voorlezen — kunnen niet meer buiten het boek wijzen. Dezelfde controles gelden bij het rechtstreeks van je server lezen, waarbij verdachte bestanden worden geweigerd vóórdat er iets wordt opgehaald.
- **Wachtwoorden en toegangssleutels blijven op je toestel** en gaan niet meer via iCloud naar je andere Apple-apparaten. Je serveradres en gebruikersnaam nog wel — die typ je liever niet opnieuw. Bestaande gegevens worden bij het opstarten automatisch teruggehaald.
- Bij een serveradres dat met `http://` begint verschijnt nu een waarschuwing dat je gegevens onbeschermd over het netwerk gaan.

## 3.38 — 2026-08-14

- **Bij het bewerken van een boek kies je de schrijver nu uit een lijst** van wie je al in je bibliotheek hebt, met het aantal boeken erbij. Een nieuwe naam intik je gewoon in hetzelfde zoekveld. Zo houd je dezelfde schrijfwijze aan en levert een tikfout geen tweede schrijver meer op.
- **Meerdere boeken tegelijk aanpassen.** Kies in het serveroverzicht *Meerdere aanpassen*, vink de boeken aan en zet in één keer de schrijver en/of de taal. Ook hier kun je kiezen om de schrijver meteen in de boekbestanden zelf te schrijven.
- **Series worden nu uit je boeken gelezen** en verschijnen in het Series-scherm, net als bij een Grimmory-server. Voor EPUB leest de app zowel de officiële EPUB 3-manier als de velden die Calibre schrijft; voor strips de Series- en Number-velden uit ComicInfo.xml.
- **Series instellen kan in het scherm voor meerdere boeken.** Je kiest een serie die je al hebt of tikt een nieuwe naam, en kunt de gekozen boeken in één keer doornummeren vanaf een startgetal.
- De serie wordt desgewenst ook in de bestanden zelf geschreven — bij een EPUB in beide vormen tegelijk, zodat zowel Calibre als andere e-readers hem zien.
- Een PDF kent geen serieveld; daar blijft de serie in de app bewaard.

## 3.36 — 2026-08-14

- **Een verkeerd wachtwoord zag eruit als een lege bibliotheek.** Ging het doorzoeken van je server mis, dan werd de fout stilzwijgend ingeslikt en bleef er niets over om naar te kijken. Nu staat er wat er misging, met een knop om het opnieuw te proberen. Stond er al een lijst van een eerdere keer, dan zie je erboven dat de laatste poging mislukte.
- **Na een afgekeurd wachtwoord probeerde de app alsnog omslagen op te halen** — acht tegelijk, allemaal kansloos. Dat gebeurt nu niet meer.
- **Een boek openen voelde traag als je veel boeken op je toestel hebt staan.** De app las bij elke handeling opnieuw de hele map van schijf; dat gebeurt nu één keer en daarna alleen nog als er echt iets verandert.
- **De titel van een boek aanpassen kon in zeldzame gevallen het boekbestand beschadigen.** Bij een EPUB met een leeg titelveld werd niet dat veld maar alles wat erop volgde overschreven. Nu wordt zo'n leeg veld overgeslagen.
- **Een audioboek dat rechtstreeks van je server speelt kon blijven hangen** als je het spelerscherm sloot terwijl er nog een stuk werd opgehaald. Ook konden twee gelijktijdige aanvragen elkaar in de weg zitten.
- Mislukte downloads lieten geen tijdelijke bestanden meer achter op je toestel.
- **Sommige audioboeken misten hun titel of hadden een afgekapte schrijversnaam.** De app las de lengtevelden in het metadatablok op één manier, terwijl een deel van de programma's die zo'n bestand maakt ze anders wegschrijft. Beide manieren worden nu herkend, en één beschadigd veld kost niet langer alles wat erachter staat.
- **Een server verwijderen terwijl hij nog aan het inlezen was, liet de app doorwerken** aan een bibliotheek die niet meer bestond. Dat stopt nu meteen.
- Knoppen op het toegangsscherm melden niet langer dat ze iets deden als de speler al was afgesloten.
- Door mappen bladeren is soepeler bij mappen met veel boeken.
- **Een schrijver hernoemen paste alleen de boeken op je server aan.** Boeken die je zelf had toegevoegd of gedownload bleven onder de oude naam staan, zodat je die schrijver daarna twee keer in de lijst had. Nu gaan al je boeken mee, ook bij het samenvoegen van schrijvers in het onderhoudsscherm.
- Een zelfgekozen schrijversfoto verhuist mee bij het hernoemen. Voeg je twee schrijvers samen, dan blijft de foto van degene die je behoudt staan.
- Het aantal boeken dat bij het hernoemen wordt genoemd klopt nu; dat telde eerder alleen je serverboeken.
- Een schrijver hernoemen werkt nu ook zonder server ingesteld te hebben.
- **Bij het hernoemen van een schrijver kun je nu kiezen om de naam ook in de boekbestanden zelf te schrijven**, zodat andere programma's hem ook zien. Staat uit tenzij je hem aanzet; je ziet vooraf om hoeveel boeken het gaat en tijdens het bijwerken hoe ver het is.
- **Strips in CBZ kunnen nu ook worden bijgewerkt.** Titel en schrijver gaan naar het ComicInfo.xml in het bestand, dat wordt aangemaakt als het er nog niet was. Voorheen kon alleen een EPUB worden aangepast.

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
