# Changelog — Thuis (Android)

All notable changes per release. Newest first.
Versions match the `vX.Y` tags and `versionName`.

## 4.74 — 2026-07-04
- New Climate screen: all indoor/outdoor temperature and humidity sensors, grouped by room and renameable, plus a dashboard tip that appears when it's a good moment to ventilate (indoors warm, outdoors cooler).
- Gas chart now overlays outdoor temperature (its own right-hand axis) and the 7-day average as a background band, on the day view.
- New "Analyses" tab: Savings, Home battery and Heat pump moved here from the bottom of the dashboard, grouped with a disclaimer that these are model-based estimates, not live readings.

## 4.73 — 2026-06-24
- New "Forecast accuracy" chart in the solar panel: predicted daily total vs. measured generation in kWh, shown as a line graph. The predicted line is dashed where it's reconstructed from history (an estimate) and solid once real, pre-frozen forecasts kick in — so you can see from when actual predictions count.
- The day's solar forecast is now frozen at a fixed early-morning moment (~3 AM) via a background refresh (WorkManager), so it no longer depends on when you first open the app (falls back to freezing on first open when the background task hasn't run).
- About screen: replaced the Forecast.Solar mention with the built-in self-learning forecast, and added a note that no rights can be derived from the accuracy of the data and that a longer HomeWizard history (ideally more than a year, because of the seasons) improves accuracy.
