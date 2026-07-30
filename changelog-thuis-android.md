# Changelog — Thuis (Android)

All notable changes per release. Newest first.
Versions match the `vX.Y` tags and `versionName`.

## 4.88 — 2026-07-30
- **De laadpaal stond op "Beschikbaar" terwijl de auto laadde.** Deze laadpaal houdt zijn echte status bij op de connector, niet op de paal zelf: die blijft "Beschikbaar" melden ook als er 4 kW doorheen gaat. De app las de verkeerde van de twee. Nu is de connector-status leidend, en blijft de correctie uit 4.80 gewoon staan.

## 4.87 — 2026-07-30
- **De app is nu ook in het Engels.** Staat je telefoon of tablet op Engels, dan is de hele app dat voortaan ook: alle schermen, knoppen, grafieklegenda's en uitlegteksten. Nederlands blijft de oorspronkelijke taal; je hoeft niets in te stellen, de app volgt de taal van je toestel. Je kunt de taal ook per app kiezen via Instellingen → Apps → Thuis → Taal.
- **Datums volgen nu ook de taal.** Weekdagen en maanden stonden op achttien plekken vast op Nederlands, dus die bleven staan als je de app op Engels zette.

## 4.86 — 2026-07-29
- **Uurprijzen komen nu uit je eigen Home Assistant als je de EnergyZero-integratie hebt.** De app haalde ze altijd zelf op bij EnergyZero, ook als je Home Assistant dat al deed. Draait die integratie, dan leest de app de prijzen voortaan daaruit — inclusief historie en de prijzen van morgen. Heb je de integratie niet, dan verandert er niets.

## 4.85 — 2026-07-29
- **"Bekijk de demo" op het welkomstscherm.** De demomodus bestond al, maar was alleen te bereiken door het woord "demo" als adres in te typen — dus onvindbaar. Nu kun je de app meteen met voorbeeldgegevens bekijken voordat je een Home Assistant-token aanmaakt.

## 4.84 — 2026-07-29
- **De ventilatietip bleef weg terwijl luchten wél zinvol was.** Sinds het dauwpunt meetelt was "buiten droger" een harde eis geworden bóvenop "buiten koeler" — dus bij 25 °C binnen en 20 °C buiten met even vochtige lucht kreeg je niets, terwijl een raam openzetten dan gewoon vijf graden scheelt. Koelen en drogen zijn nu twee losse redenen: elk is op zichzelf genoeg. Vochtige buitenlucht houdt de koeltip nog steeds tegen, maar alleen als die ook echt merkbaar vochtiger is.
- De tip zegt er nu bij wát je wint: koelen, drogen, of allebei.

## 4.83 — 2026-07-28
- **De automatische sensorherkenning kon het netvermogen op één fase leggen.** De fase-sensoren van een P1-meter passen op hetzelfde profiel als het totaal, en de keuze hing af van de volgorde waarin de sensoren binnenkwamen. Op een fase zonder verbruik bleef het dashboard dan op 0 W en "Net" staan terwijl je in werkelijkheid teruglevert. De keuze ligt nu vast en valt nooit meer op een losse fase.
- In demomodus meldt de statusregel niet langer dat de gegevens verouderd zijn — daar horen ze stil te staan.

## 4.82 — 2026-07-28
- **Stooklabel, graaddagen, gasgrafiek en warmtepompverkenning werken nu ook zonder eigen buitensensor.** Waar de app eerst niets liet zien als er geen gekoppelde buitentemperatuursensor met historie was, zoekt hij nu zelf een weersensor van je weer-integratie, en anders haalt hij de historische buitentemperatuur bij Open-Meteo op basis van de locatie die Home Assistant zelf rapporteert. De iOS-app deed dit al.
- **Het dashboard flikkert niet meer als een sensor kortstondig wegvalt.** Meldde een sensor even "unavailable", dan werd de laatst bekende goede waarde overschreven — waardoor bijvoorbeeld de zon op 0 sprong en de teruglevering te groot leek. Zulke tussenwaarden worden nu genegeerd.
- **De laadpaal valt weer netjes terug bij een haperend netwerk.** Een time-out bij het ophalen van het laadvermogen kon het hele laadpaalpaneel laten mislukken in plaats van terug te vallen op de berekende waarde.

## 4.81 — 2026-07-28
- **Het dashboard kon een bevroren stand tonen alsof die live was.** Zette het systeem de app in de achtergrond, dan kon de verbinding met Home Assistant stilvallen zonder dat de app dat merkte: de statusregel bleef "Live" melden terwijl de getallen eronder uren stil konden staan. Een teruglevering van vanochtend zag er dan uit als afname van nu. De app kijkt voortaan of er ook echt gegevens binnenkomen, herstelt de verbinding zodra die opdroogt, en zegt het eerlijk ("Gegevens van 20 min geleden") als dat niet lukt.

## 4.80 — 2026-07-27
- **Laadpaal bleef "Aan het laden" tonen na een sessie.** De app keek naast de status van de paal ook naar het gemeten vermogen, en PlugChoice blijft daar na afloop de laatste waarde teruggeven. Zegt de laadpaal nu "Beschikbaar" of "Gepauzeerd", dan is dat leidend en verdwijnt ook de spookladsnelheid.

## 4.79 — 2026-07-27
- Kolomkop boven de klimaatsensoren, zodat duidelijk is welk getal temperatuur, luchtvochtigheid en dauwpunt is — de iconen alleen waren niet zelfverklarend.

## 4.78 — 2026-07-27
- **Dauwpunt bij elke klimaatsensor**, binnen én buiten. Anders dan de luchtvochtigheid in procenten is het dauwpunt wél vergelijkbaar tussen kamers en met buiten: het zegt hoeveel vocht er absoluut in de lucht zit.
- **De ventilatietip klopt nu ook bij vochtig weer.** Hij keek alleen naar temperatuur, waardoor hij kon adviseren te luchten met buitenlucht die kouder maar vochtiger was — waarmee je het binnen juist klammer maakt. Zijn de dauwpunten bekend, dan moet de buitenlucht ook echt droger zijn, en de tip laat zien hoeveel.
- **Eigen buitenvochtsensor krijgt voorrang op de weersvoorspelling.** De app zoekt zelf de vochtsensor die bij je buitentemperatuur-sensor hoort; vindt hij die niet, dan gebruikt hij zoals voorheen de weer-entiteit.

## 4.77 — 2026-07-25
- Tikken op een warmtepomp opent nu een detailscherm: past deze pomp bij je berekende warmteverlies (inclusief pendelrisico), de volledige specificaties, het geluid met de afstand tot de erfgrens voor zowel de dag- als de nachtnorm, en de jaarkosten doorgerekend met déze pomp. Gelijk aan de iOS-versie.

## 4.76 — 2026-07-25
- Warmtepomplijst gelijkgetrokken met iOS (peildatum juli 2026): Quatt All-Electric toegevoegd en de hybride capaciteiten gecorrigeerd, Daikin Altherma 3 M vervangen door de Altherma 4 op propaan, en Weheat's Flint, Sparrow en Blackbird zijn nu alle drie zowel hybride als volledig elektrisch leverbaar. Panasonic en LG bijgesteld aan de hand van hun eigen documentatie.
- **Geluid toegevoegd bij elke pomp**: het geluidsvermogen van de buitenunit plus de afstand tot de erfgrens waarop de nachtnorm van 40 dB(A) gehaald wordt.

## 4.75 — 2026-07-22
- De app target nu Android 16 (API 36), zoals Google Play vereist.

## 4.74 — 2026-07-04
- New Climate screen: all indoor/outdoor temperature and humidity sensors, grouped by room and renameable, plus a dashboard tip that appears when it's a good moment to ventilate (indoors warm, outdoors cooler).
- Gas chart now overlays outdoor temperature (its own right-hand axis) and the 7-day average as a background band, on the day view.
- New "Analyses" tab: Savings, Home battery and Heat pump moved here from the bottom of the dashboard, grouped with a disclaimer that these are model-based estimates, not live readings.

## 4.73 — 2026-06-24
- New "Forecast accuracy" chart in the solar panel: predicted daily total vs. measured generation in kWh, shown as a line graph. The predicted line is dashed where it's reconstructed from history (an estimate) and solid once real, pre-frozen forecasts kick in — so you can see from when actual predictions count.
- The day's solar forecast is now frozen at a fixed early-morning moment (~3 AM) via a background refresh (WorkManager), so it no longer depends on when you first open the app (falls back to freezing on first open when the background task hasn't run).
- About screen: replaced the Forecast.Solar mention with the built-in self-learning forecast, and added a note that no rights can be derived from the accuracy of the data and that a longer HomeWizard history (ideally more than a year, because of the seasons) improves accuracy.
