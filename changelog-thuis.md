# Wijzigingslog — Thuis

Alle noemenswaardige wijzigingen per release. Nieuwste bovenaan.
Versies komen overeen met de `vX.Y`-tags en `CFBundleShortVersionString`.

## 4.71 — 2026-06-23

- Onderhoud: versiebump met geregenereerde Info.plist.

## 4.70 — 2026-06-22

- Zon-detail "Vandaag" toont in de header nu hetzelfde live-getal als het
  dashboard-paneel (inclusief het lopende uur).

## 4.69 — 2026-06-20

- Zon-opbrengst wordt naar kWh omgerekend op basis van de werkelijke eenheid
  (Wh/MWh/kWh) van de sensor, in plaats van een vaste factor.
- Nieuwe knop "Detecteer automatisch" herkent net-, gas- en
  buitentemperatuur-entiteiten via Home Assistant.
- Windsnelheid neemt de eenheid over uit de weer-entiteit.

## 4.68 — 2026-06-20

- Tikbare weertegel met uur-detail: temperatuur, bewolking en wind.

## 4.67 — 2026-06-19

- Vooruit navigeren naar morgen, met de verwachte zon-prognoselijn.

## 4.66 — 2026-06-19

- De verwacht-lijn van vandaag wordt 's ochtends één keer vastgezet in plaats
  van gedurende de dag bijgesteld, zodat model en werkelijke opbrengst zuiver
  te vergelijken zijn. KPI's blijven live.
