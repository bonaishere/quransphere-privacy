---
layout: default
title: Privacy Policy — QuranSphere
permalink: /
---

# Privacy Policy — QuranSphere

_Last updated: 14 July 2026_

## Summary (plain language)

QuranSphere is an offline-first Islamic app. **We do not run a server, we have no user accounts, and we do not collect, store, or transmit your personal data to us.** Everything you create — bookmarks, notes, prayer log, hayd and fasting records, tasbih counts, saved locations — stays **on your device**.

We have no analytics, no advertising SDKs, and no crash-reporting backend. There is nothing for us to collect, because there is no "us" on the network: the app has no backend.

## What stays on your device (never sent to us)

- Reading state, bookmarks, notes, highlights, collections
- Prayer log, qada counter, hayd tracker, fasting log, khatma progress
- Tasbih counts, achievements, home-dashboard layout, all settings
- Your app-lock PIN (stored only as a SHA-256 hash, never in plain text)
- Your AI API key, if you add one (stored in the Android Keystore via the OS secure store)

## Data sent to third parties (only to deliver a feature you use)

The app makes requests **directly from your device** to the services below. We do not receive, proxy, or log any of it. Each service has its own privacy policy.

| Feature | Service | What is sent | Why |
|---|---|---|---|
| Prayer times | Aladhan API | your approximate coordinates | refine the times computed on-device |
| Nearby mosques | OpenStreetMap Overpass | your approximate coordinates | find mosques around you |
| City search | OpenStreetMap Nominatim | the city text you type | turn it into coordinates |
| Extra translations / tafsir | Quran.com API | the verse requested | fetch the text you asked for |
| Recitation audio | EveryAyah | the surah/verse requested | stream or download the recitation |
| Zakat nisab | goldprice.org | nothing about you — just the request | fetch the current gold/silver price |
| AI assistant (optional, off by default) | the provider **you** choose, using **your own** API key | your prompt and its verse context | your explicit request |

The AI assistant does nothing unless you enter your own API key. When you do, prompts go to the provider you picked, under your own account and their terms — not through us.

Prayer times, the Qibla, the full Quran, tafsir, translation, hadith and azkar all work with **none** of these services. The app is fully usable with no network at all.

## Location

Location is used only to compute prayer times, the Qibla direction, and nearby mosques. It is requested at the point of use and used in the moment. It is **never stored on any server** and never associated with an identity.

Background location is disabled entirely — the app cannot read your location when it is not open.

You can skip location permission and enter a city by hand instead; every location-based feature works that way.

## Permissions and why each is needed

| Permission | Why |
|---|---|
| Location (fine/coarse) | Prayer times, Qibla, nearby mosques. Optional — a manually entered city works instead. |
| Notifications | The adhan and any reminders you switch on. |
| Exact alarms | The adhan must sound at the exact prayer instant. An inexact alarm would make the call to prayer late, which defeats the feature. |
| Foreground service (media playback) | Plays the full adhan and Quran recitation with the screen off or the app closed. |
| Run at startup | Re-arms the prayer alarms after you restart your phone, so the adhan does not silently stop working. |
| Ignore battery optimisations | Optional, and only prompted. Without it, some manufacturers' battery managers delay or kill the exact prayer alarm. |
| Vibrate | Vibrate-mode prayer alerts, tasbih haptics, and the haptic pulse in the accessible Qibla mode. |

The app does **not** request camera, microphone, contacts, or file-storage access.

## Purchases

QuranSphere is free, and no feature is behind a paywall. The app offers optional tips through Google Play. Payments are handled entirely by Google — we never see your card or billing details, only whether a tip completed.

## Children

The app is suitable for all ages and does not knowingly collect data from anyone, of any age.

## Backup export

You can export your data to a file you control, optionally encrypted with a passphrase you choose. That file is created by you, stored where you choose, and never sent to us. If you lose the passphrase, we cannot recover the file — we do not have it.

## Your rights

Because no data ever reaches us, there is nothing for us to disclose, correct, or delete. Uninstalling the app removes everything it stored. You can also clear the app's data from Android's settings at any time.

## Changes

Material changes will be reflected here with a new "last updated" date.

## Contact

**bonaishere** — [bonaishere@hotmail.com](mailto:bonaishere@hotmail.com)
