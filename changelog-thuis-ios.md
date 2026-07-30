# Changelog — Thuis

All notable changes per release. Newest first.
Versions match the `vX.Y` tags and `CFBundleShortVersionString`.

## 5.05 — 2026-07-30
- **De laadpaal stond op "Beschikbaar" terwijl de auto laadde.** Deze laadpaal houdt zijn echte status bij op de connector, niet op de paal zelf: die blijft "Beschikbaar" melden ook als er 4 kW doorheen gaat. De app las de verkeerde van de twee. Nu is de connector-status leidend, en blijft de correctie uit 4.92 (een achtergebleven vermogenswaarde mag geen laden voorwenden) gewoon staan.

## 5.04 — 2026-07-30
- **De laatste Nederlandse teksten in de Engelse app zijn weg.** Het ging vooral om de kaartjes onder de grafieken ("Verwarmings-gas", "Graaddagen", "Basislijn", "Aandeel verwarming", "Toegevoegd deze sessie", "Piek oplaadsnelheid"), de statusregel bovenaan, de ondertitels van het beste-moment- en ventilatieblok, de laadduur en het tarief, en op het warmtepompscherm de ontwerptemperatuur en de afstand tot de erfgrens.

## 5.03 — 2026-07-30
- **Grafieklegenda's en de laatste subteksten zijn nu ook Engels.** De legenda's kregen hun tekst uit de gegevens zelf (Afname/Teruglevering, Vast/Dynamisch, Net/Zon), en die tekst was tegelijk de sleutel van het kleurenschema — daarom moesten ze samen mee. Verder nog 76 losse teksten: foutmeldingen, de namen in de entiteitkiezer, en de uitlegblokken onder de grafieken.
- Bij de batterij-uitleg en de autofoto-hulptekst stonden zinnen aan elkaar geplakt met `+`. Dat werkt niet in een vertaling, want de woordvolgorde verschilt per taal; die zijn samengevoegd tot één tekst.

## 5.02 — 2026-07-30
- **Nog eens 71 teksten vertaald**, waaronder de periode-keuzes (Week/Maand/Jaar) in alle detailschermen en de titels die daarop meebewegen ("Stroomkosten per week").
- **Datums en getallen volgen nu ook de taal.** De app zette de datumtaal op elf plekken hard op Nederlands, dus in het Engels bleven weekdagen en maanden Nederlands ("Woensdag 30 juli"). En op 22 plekken werd het decimaalteken hard een komma, waardoor er in het Engels "31,0°" stond in plaats van "31.0°". Beide volgen nu de taal die je in de app hebt gekozen.

## 5.01 — 2026-07-29
- **De vertaling was op veel plekken nog Nederlands.** Woorden als "Zon vandaag", "Net vandaag", "Gas vandaag", "Efficiëntie", "Huis", "Binnen" en "Buiten" bleven staan, en in de detailschermen ook regelmatig. Die teksten liepen via gedeelde bouwstenen (de tegels, de rijen, de invoervelden) die ze als gewone tekst doorgaven, waardoor iOS ze niet als vertaalbaar zag. 68 teksten zijn nu wél vertaald.

## 5.00 — 2026-07-29
- **Taalkeuze in Instellingen**, net als in Grim Reader: een knop die je naar de taalinstelling van de app in iOS brengt. Daar kies je Nederlands of Engels, los van de taal van je toestel. Die keuze was er technisch al sinds 4.98, maar iOS liet hem niet zien omdat de app zijn talen nog niet formeel aanmeldde.

## 4.99 — 2026-07-29
- **Kamernamen op het Klimaat-scherm werden op een iPhone letter voor letter afgebroken.** De kolomkoppen uit 4.91 kregen vaste breedtes die samen met het icoon en de potloodknop de hele regel opvulden, waardoor er niets meer overbleef voor de naam — "zolder" kwam er verticaal uit te staan. De kolommen zijn nu per soort waarde op maat, de iconen bij de getallen zijn weg (de kopregel zegt al wat elke kolom is) en de naam krimpt desnoods een fractie in plaats van te wikkelen.

## 4.98 — 2026-07-29
- **De app is nu ook in het Engels.** Staat je iPhone of iPad op Engels, dan is de hele app dat voortaan ook: alle schermen, knoppen, uitlegteksten en meldingen. Nederlands blijft de oorspronkelijke taal; je hoeft niets in te stellen, de app volgt gewoon de taal van je toestel.

## 4.97 — 2026-07-29
- **Uurprijzen komen nu uit je eigen Home Assistant als je de EnergyZero-integratie hebt.** De app haalde ze altijd zelf op bij EnergyZero, ook als je Home Assistant dat al deed. Draait die integratie, dan leest de app de prijzen voortaan daaruit — inclusief historie en de prijzen van morgen. Heb je de integratie niet, dan verandert er niets: de app haalt ze zelf op, precies zoals voorheen.

## 4.96 — 2026-07-29
- **"Bekijk de demo" op het welkomstscherm.** De demomodus bestond al, maar was alleen te bereiken door het woord "demo" als adres in te typen — dus onvindbaar. Nu kun je de app meteen met voorbeeldgegevens bekijken voordat je een Home Assistant-token aanmaakt.
- **Grote cijfers schalen mee met je tekstgrootte.** Het energielabel op het dashboard en het efficiëntiescherm, en het berekende vermogen op het warmtepompscherm, hadden een vaste lettergrootte en negeerden daarmee de tekstinstelling van je toestel.

## 4.95 — 2026-07-29
- **De ventilatietip bleef weg terwijl luchten wél zinvol was.** Sinds het dauwpunt meetelt was "buiten droger" een harde eis geworden bóvenop "buiten koeler" — dus bij 25 °C binnen en 20 °C buiten met even vochtige lucht kreeg je niets, terwijl een raam openzetten dan gewoon vijf graden scheelt. Koelen en drogen zijn nu twee losse redenen: elk is op zichzelf genoeg. Vochtige buitenlucht houdt de koeltip nog steeds tegen, maar alleen als die ook echt merkbaar vochtiger is.
- De tip zegt er nu bij wát je wint: koelen, drogen, of allebei.

## 4.94 — 2026-07-28
- **Twee apparaten konden verschillende netvermogens tonen bij dezelfde Home Assistant.** De app zocht de netvermogen-sensor zelf op, maar pakte de eerste treffer uit een lijst zonder vaste volgorde — en de fase-sensoren van een P1-meter passen op datzelfde profiel. Zo kon een iPad naar één fase kijken terwijl de iPhone het totaal las: op een fase zonder verbruik bleef het dashboard dan op 0 W en "Net" staan, terwijl je in werkelijkheid teruglevert. De keuze ligt nu vast, valt nooit meer op een losse fase, en een apparaat dat al verkeerd stond herstelt zichzelf bij de eerstvolgende verbinding.
- In demomodus meldt de statusregel niet langer dat de gegevens verouderd zijn — daar horen ze stil te staan.

## 4.93 — 2026-07-28
- **Het dashboard kon een bevroren stand tonen alsof die live was.** Zette het systeem de app in de achtergrond, dan kon de verbinding met Home Assistant stilvallen zonder dat de app dat merkte: de statusregel bleef "Live" melden terwijl de getallen eronder uren stil konden staan. Een teruglevering van vanochtend zag er dan uit als afname van nu. De app kijkt voortaan of er ook echt gegevens binnenkomen, herstelt de verbinding zodra die opdroogt, en zegt het eerlijk ("Gegevens van 20 min geleden") als dat niet lukt.

## 4.92 — 2026-07-27
- **Laadpaal bleef "Aan het laden" tonen na een sessie.** De app keek naast de status van de paal ook naar het gemeten vermogen, en PlugChoice blijft daar na afloop de laatste waarde teruggeven. Zegt de laadpaal nu "Beschikbaar" of "Gepauzeerd", dan is dat leidend en verdwijnt ook de spookladsnelheid.

## 4.91 — 2026-07-27
- Kolomkop boven de klimaatsensoren, zodat duidelijk is welk getal temperatuur, luchtvochtigheid en dauwpunt is — de iconen alleen waren niet zelfverklarend. Het dauwpunt staat nu ook in de VoiceOver-omschrijving van elke rij.

## 4.90 — 2026-07-27
- **Dauwpunt bij elke klimaatsensor**, binnen én buiten. Anders dan de luchtvochtigheid in procenten is het dauwpunt wél vergelijkbaar tussen kamers en met buiten: het zegt hoeveel vocht er absoluut in de lucht zit.
- **De ventilatietip klopt nu ook bij vochtig weer.** Hij keek alleen naar temperatuur, waardoor hij kon adviseren te luchten met buitenlucht die kouder maar vochtiger was — waarmee je het binnen juist klammer maakt. Zijn de dauwpunten bekend, dan moet de buitenlucht ook echt droger zijn, en de tip laat zien hoeveel.
- **Eigen buitenvochtsensor krijgt voorrang op de weersvoorspelling.** De app zoekt zelf de vochtsensor die bij je buitentemperatuur-sensor hoort; vindt hij die niet, dan gebruikt hij zoals voorheen de weer-entiteit. Dat scheelt, want een regionale weerwaarde combineren met een lokaal gemeten temperatuur geeft een dauwpunt dat er flink naast kan zitten.

## 4.89 — 2026-07-25
- Tikken op een warmtepomp opent nu een detailscherm: past deze pomp bij je berekende warmteverlies (inclusief pendelrisico), de volledige specificaties, het geluid met de afstand tot de erfgrens voor zowel de dag- als de nachtnorm, en de jaarkosten doorgerekend met déze pomp. De pomp wordt bij het tikken nog steeds gekozen, dus de simulatie op de achtergrond rekent gewoon mee.

## 4.88 — 2026-07-25
- Warmtepomplijst bijgewerkt naar peildatum juli 2026: Quatt heeft er een volledig elektrische uitvoering bij (en de capaciteiten van de hybride klopten niet), Daikin's Altherma 3 M is vervangen door de Altherma 4 op propaan, en Weheat's Flint, Sparrow en Blackbird staan niet langer vastgepind op één systeemtype — die zijn alle drie zowel hybride als volledig elektrisch leverbaar. Panasonic en LG zijn gecorrigeerd aan de hand van hun eigen documentatie.
- **Geluid toegevoegd bij elke pomp**: het geluidsvermogen van de buitenunit plus de afstand tot de erfgrens waarop de nachtnorm van 40 dB(A) gehaald wordt. Bewust het geluidsvermogen en niet de geluidsdruk uit folders, want die wordt in stille modus op een zelfgekozen afstand gemeten en ligt tot 15 dB lager.

## 4.87 — 2026-07-08
- Auto-afbeeldingen zijn terug, nu optioneel en per model instelbaar.

## 4.86 — 2026-07-08
- Buitentemperatuur valt nu in drie stappen terug: je eigen sensor, anders de weersensor, anders Open-Meteo — zodat de berekeningen ook kloppen als er geen buitensensor gekoppeld is.
- Het warmtepompscherm meldt nu eerlijk wanneer een sensorkoppeling ontbreekt in plaats van stilletjes met een aanname te rekenen.

## 4.85 — 2026-07-08
- Het getekende autosilhouet is vervangen door een systeem-icoon.

## 4.84 — 2026-07-08
- App Store-voorbereiding: automerk-foto's verwijderd, automatische detectie toegevoegd en generieke standaardwaarden gebruikt.

## 4.83 — 2026-07-02
- Solar forecast fixes from a code review: the dashboard could freeze "expected today" for the whole day based on yesterday's cached weather forecast when the fresh fetch happened to fail at first open — freezing now only happens on a fresh forecast (as the solar screen already did), which also keeps the accuracy graph honest. And the fallback estimate shown just after midnight now includes the remainder of the current hour pro rata, instead of skipping up to a full peak hour.

## 4.82 — 2026-07-01
- Moved the ventilation-tip sensor picker from Settings to the Climate screen, so everything climate-related lives in one place. The picker also now only offers sensors the Climate screen already recognises and shows, instead of every Celsius entity in Home Assistant.

## 4.81 — 2026-07-01
- Fixed a gap in the EV charging graph: while actively charging with the sun out, the current (still in-progress) hour always showed 0% solar, because the grid/solar split relied on Home Assistant's hourly statistics, which only finalize once an hour has fully elapsed. The current hour now falls back to the live self-sufficiency ratio (already updated every second) instead.
- The charge-power slider is back on the EV charging screen — set the OCPP charge limit (in kW, up to the charger's hardware maximum) during an active session. It now also shows the live measured power right next to it, so you can immediately see whether raising the limit actually increases the delivered power, or whether the charger itself has a lower local cap in place that PlugChoice's API can't see or override.

## 4.80 — 2026-07-01
- New "Analyses" tab: the savings analysis, home battery capacity advice and heat pump exploration cards moved off the home screen (which had grown to 12+ tiles) into their own tab, with a disclaimer at the top that these are indicative model-based calculations, not guarantees.

## 4.79 — 2026-07-01
- Fixed the remaining case of the "app jumps to the setup screen" bug from 4.78: that fix covered later iCloud sync notifications, but the very first read on a cold launch could still momentarily treat an empty iCloud value as real and wipe the locally cached host/token. Mostly noticeable on iPhone, since iOS terminates suspended apps there far more aggressively than on iPad, so closing and reopening the app tends to force a real cold launch (and hit this window) sooner.
- "Expected today" on the solar tile and detail screen now stays pinned for the whole day instead of drifting with every new weather forecast — the accuracy graph already used a frozen daily total, but the headline number next to it was still recalculated live on each refresh.
- The efficiency detail screen now opens on the same rolling 12-month window the dashboard tile uses, instead of the calendar year — so the letter grade shown there always matches the tile instead of occasionally disagreeing with it.

## 4.78 — 2026-06-25
- New ventilation tip: pick an indoor and an outdoor temperature sensor in Settings, and the dashboard shows "You can ventilate now" whenever it's warmer than 20°C indoors and more than 1°C cooler outside — the moment to air out without cooling the house down.
- Fixed a bug where the app could suddenly jump to the setup screen (with no "Done" button and a greyed-out "Connect" button); a transient empty iCloud sync read was briefly clearing the stored host/token. The app now only adopts non-empty synced credentials.

## 4.77 — 2026-06-25
- Climate screen now shows only real combined sensors: an entry appears only when a sensor reports both temperature and humidity, and only actual `sensor.*` measurements are considered. This removes the clutter from devices like the SONOFF SNZB-02D, which expose extra configuration/threshold entities (comfort min/max temperature, comfort humidity limits, humidity compensation) and from standalone temperature-only or humidity-only sensors.

## 4.76 — 2026-06-25
- Climate screen: the local weather for your location (the outdoor temperature sensor plus the Home Assistant weather entity — condition, temperature and humidity) now shows in a separate "Location" card at the top, instead of being mixed in with the room sensors. Only your own temperature and humidity sensors remain in the indoor/outdoor room lists.

## 4.75 — 2026-06-25
- New "Climate" tile and detail screen: indoor and outdoor temperature and humidity from any sensors connected to Home Assistant. Detection is brand-independent — sensors are recognised by their Home Assistant device class, so Aqara, Xiaomi, SwitchBot, Shelly, Sonoff, Govee and others all work. Temperature and humidity from the same spot are paired into one room, split into indoor and outdoor, and each room can be given a custom name.

## 4.74 — 2026-06-25
- The dashboard's solar "expected today" tile now matches the figure in the solar detail screen. It previously dropped to just the energy produced so far whenever the live forecast fetch came back empty; it now falls back to the cached forecast like the detail view already did.
- The "Forecast accuracy" line is now solid from the first real (pre-frozen) prediction onward, even when only one real day exists yet — so the day you started getting genuine predictions no longer shows up as a dashed endpoint.

## 4.73 — 2026-06-24
- The "Forecast accuracy" chart is now a line graph: predicted daily total vs. measured generation in kWh. The predicted line is dashed where it's reconstructed from history (an estimate) and solid once real, pre-frozen forecasts kick in — so you can see from when actual predictions count.

## 4.72 — 2026-06-24
- New "Forecast accuracy" chart in the solar panel: predicted daily total vs. measured generation as a percentage correct over the last 28 days. It fills in immediately with estimates reconstructed from logged data; those estimates drop out as real day-ahead predictions accumulate.
- The day's solar forecast is now frozen at a fixed early-morning reference moment via an overnight background refresh, so it no longer depends on when you first open the app (falls back to freezing on first open when background refresh is unavailable).
- About screen: added a note that no rights can be derived from the accuracy of the data, and that a longer HomeWizard history (ideally more than a year, because of the seasons) improves accuracy. Replaced the Forecast.Solar mention with the built-in self-learning forecast.

## 4.71 — 2026-06-23
- Maintenance: version bump with a regenerated Info.plist.

## 4.70 — 2026-06-22
- Solar "Today" detail header now matches the dashboard panel (live figure incl. the current hour).

## 4.69 — 2026-06-20
- Unit-aware solar conversion (kWh based on the sensor's actual Wh/MWh/kWh unit).
- Auto-detection of grid, gas and outdoor-temperature entities.
- Wind speed takes its unit from the weather entity.

## 4.68 — 2026-06-20
- Tappable weather tile with hourly detail: temperature, cloud cover and wind.

## 4.67 — 2026-06-19
- Navigate forward to tomorrow, with the expected solar forecast line.

## 4.66 — 2026-06-19
- Today's expected line is fixed once in the morning instead of being adjusted during the day, so model vs. actual generation stays comparable. KPIs remain live.

## 4.65 — 2026-06-19
- Don't drop hourly solar when Met.no omits the current hour.

## 4.64 — 2026-06-19
- Price cache as a fallback when the EnergyZero fetch fails.

## 4.63 — 2026-06-19
- App-icon marketing slot so App Store Connect shows the icon.

## 4.62 — 2026-06-19
- Forecast cache for an instant solar screen.

## 4.61 — 2026-06-19
- Hourly expected line on the today solar chart (model vs. measured).

## 4.60 — 2026-06-19
- Dashboard "expected" tile now comes from the self-learning model instead of the old Forecast.Solar sensor.

## 4.59 — 2026-06-19
- Anchor the cloud-transmission curve at clear = 1.0 so the forecast isn't structurally ~17% too low on clear days.

## 4.58 — 2026-06-19
- Bootstrap the cloud-transmission curve from Home Assistant's own cloud-coverage history (~10 days) so the forecast avoids a 1–2 week cold start.

## 4.57 — 2026-06-18
- Fix "expected today" on the solar screen: add actual generation so far to the model's prediction for the remaining hours.

## 4.56 — 2026-06-18
- Replaced Forecast.Solar with an own self-learning solar forecast (Met.no cloud cover × a learned clear-sky envelope and cloud-transmission curve).

## 4.55 — 2026-06-18
- Home-battery screen: "My battery" settings card placed under the battery-advice widget.

## 4.54 — 2026-06-18
- Split the EV "finished" notification: a slim banner at the top, session figures as their own card lower down.

## 4.53 — 2026-06-18
- Reordered the EV charge screen: pinned "finished" banner at the top, status and charged-today as separate cards.

## 4.52 — 2026-06-18
- Configurable battery size + return on the home-battery screen; EV status card under the trend chart.

## 4.51 — 2026-06-18
- EV charge screen solar/grid fix: proportional solar model + restored "today" section.

## 4.50 — 2026-06-18
- Fix EV charge detail showing 100% solar: hourly surplus model instead of daily netting.

## 4.49 — 2026-06-18
- Solar coverage with a home battery + financial return in the battery detail.

## 4.48 — 2026-06-18
- Home-battery analysis (base load, net grid, capacity advice) as a new submenu.

## 4.47 — 2026-06-17
- Renamed "markup" to "purchase fee" (electricity + gas) with defaults; the best-moment view applies the fee.

## 4.46 — 2026-06-17
- Savings analysis now recalculates when tariff settings change (markup etc.).

## 4.45 — 2026-06-17
- Cost chart shows only buckets with actual consumption (no more empty months).

## 4.44 — 2026-06-17
- Cost chart (grouped bars, fixed vs. dynamic) + 12-month view.

## 4.43 — 2026-06-17
- Dynamic average price per kWh + cost of feed-in at negative prices.

## 4.42 — 2026-06-17
- Fixed-tariff comparison without netting, including feed-in compensation.

## 4.41 — 2026-06-17
- Fresh installs no longer stuck at 0 W + learned profiles synced via iCloud.

## 4.40 — 2026-06-17
- Maintenance: version bump to 4.40.

## 4.39 — 2026-06-17
- Freeze home consumption on a stale solar reading (slow Enphase refresh).

## 4.38 — 2026-06-17
- Traffic-light learns solar shape and forecast bias from your own history.

## 4.37 — 2026-06-17
- Traffic-light scores on learned solar surplus instead of raw solar output.

## 4.36 — 2026-06-17
- Cache day-ahead prices for the traffic-light.

## 4.35 — 2026-06-17
- Energy tax in the dynamic price view + 2026 rates.

## 4.34 — 2026-06-16
- Reliable charging status after stop (power-usage is leading).

## 4.32 — 2026-06-16
- More realistic solar share for charging + removed the charge-limit slider.

## 4.31 — 2026-06-16
- Lazy section loading + heat pump in the savings panel (fixed vs. dynamic).

## 4.30 — 2026-06-16
- Week-chart fix, 3-phase home consumption, gloss on charts.

## 4.29 — 2026-06-15
- "Best time to use electricity" traffic-light.

## 4.28 — 2026-06-15
- In-app "car finished charging" notification + shared session KPIs.

## 4.27 — 2026-06-15
- Tap bars for grid/solar detail, session-curve screen, real charge time + a split trend widget.

## 4.26 — 2026-06-15
- EV charge split on actual charging hours + on-disk curve cache.

## 4.25 — 2026-06-15
- Maintenance: sync the Info.plist version string.

## 4.24 — 2026-06-14
- Home consumption no longer wrongly reads 0 with a slow solar sensor.

## 4.23 — 2026-06-14
- Solar-panel choice moved to the main settings + charge-limit error message.

## 4.22 — 2026-06-14
- Store the charge limit locally as a fallback for the slider.

## 4.21 — 2026-06-14
- Automatic solar-system detection in the entity settings.

## 4.20 — 2026-06-14
- Solar/costs on the charger screen + 422 fix for the charge limit.

## 4.19 — 2026-06-14
- Charging charts split into grid power and solar power.

## 4.18 — 2026-06-14
- Improved charging-history screen.

## 4.17 — 2026-06-14
- Charging-history screen + cleaned-up "today" tile.

## 4.16 — 2026-06-13
- Fix preview caching for your own car, new ID.Buzz photo, text without PNG.

## 4.15 — 2026-06-13
- Own car, "charged yesterday", read the charge limit + updated VW catalogue.

## 4.14 — 2026-06-13
- Read phases/max current from the separate charger endpoint.

## 4.13 — 2026-06-12
- Charge control via PlugChoice: start/stop + charge-limit slider.

## 4.12 — 2026-06-12
- Documented recommended Home Assistant integrations + logo on the info screen.

## 4.11 — 2026-06-12
- No error flash on failover.

## 4.10 — 2026-06-12
- Maintenance: version bump (lockstep with Android).

## 4.9 — 2026-06-12
- Suppress the error flash during failover.

## 4.8 — 2026-06-12
- Fix a false 'cancelled' error via a generation guard.

## 4.7 — 2026-06-12
- Robust failover: don't drop a healthy local connection.

## 4.6 — 2026-06-12
- Stable Nabu Casa connection: keep-alive instead of stream timeout.

## 4.5 — 2026-06-12
- Save button in the connection-settings screen.

## 4.4 — 2026-06-12
- Phase 3 connection robustness + dashboard jitter fix.

## 4.3 — 2026-06-12
- Pick entities from the live Home Assistant list instead of typing them.

## 4.2 — 2026-06-12
- Formula fixes, shared calculation tests, heat pump v2 and configurable entities.

## 4.1 — 2026-06-11
- Connection settings in a separate submenu under Settings.

## 4.0 — 2026-06-11
- Remote connection (Nabu Casa) with automatic failover.

## 3.8 — 2026-06-11
- Info page with a Polderpijplijn section and a link to the website.

## 3.7 — 2026-06-11
- Charge detail screen: trend chart + charging history.

## 3.6 — 2026-06-10
- Derived charging power on the charger tile and detail.

## 3.5 — 2026-06-10
- Decimals for indoor temperature in settings.

## 3.4 — 2026-06-09
- Privacy manifest, info page, new icon.

## 3.3 — 2026-06-09
- Heat pumps: show modulation + split the advice on short-cycling risk.

## 3.2 — 2026-06-09
- Heat-pump exploration: capacity, costs and suitable pumps.

## 3.1 — 2026-06-09
- Electricity prices + costs, grid widget; removed Cloudflare.

## 3.0 — 2026-06-09
- Show the efficiency rating on the dashboard once there's ≥1 winter of data.

## 2.9 — 2026-06-09
- Efficiency rating on the dashboard widget.

## 2.8 — 2026-06-09
- Rolling 12-month window + efficiency docs update.

## 2.7 — 2026-06-09
- Moved the housing-type picker out of the efficiency screen.

## 2.6 — 2026-06-09
- Two-layer efficiency architecture + year-chart fix.

## 2.5 — 2026-06-09
- Efficiency winter mode, dashboard layout and various fixes.

## 2.4 — 2026-06-09
- New "Home Energy Efficiency" screen.

## 2.3 — 2026-06-06
- Keep the chart tooltip on screen.

## 2.2 — 2026-06-06
- Simplified KPIs: removed peak figures, added "expected tomorrow".

## 2.1 — 2026-06-06
- Stronger glow reflecting generation and consumption.

## 2.0 — 2026-06-06
- Soft glow instead of a large weather symbol on the Solar/Outside tiles.

## 1.9 — 2026-06-06
- Ten extra cars in the catalogue.

## 1.8 — 2026-06-06
- Charging status no longer stuck on "Charging" after a pause.

## 1.7 — 2026-06-06
- Removed auto colour selection (it didn't work).

## 1.6 — 2026-06-06
- Charging screen tuned to real PlugChoice data + auto colour selection.

## 1.5 — 2026-06-06
- Derive charging status from live power + ongoing session.

## 1.4 — 2026-06-06
- Charger detail screen + car auto-selection, period selection and SF backgrounds.

## 1.3 — 2026-06-06
- Maintenance: version bump (detail-screens release).

## 1.2 — 2026-06-05
- Maintenance: version bump (charger release).

## 1.1 — 2026-06-05
- Gas usage today + chart detail screens.

## 1.0 — 2026-06-05
- First TestFlight release.
