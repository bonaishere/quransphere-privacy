---
layout: default
title: Privacy Policy — QuranSphere
permalink: /
---

# Privacy Policy — QuranSphere

_Last updated: 9 August 2026_

## Summary (plain language)

QuranSphere is an offline-first Islamic app. **We do not run a server, we have no user accounts, and nothing you create is ever sent to us.** Everything you make — bookmarks, notes, prayer log, hayd and fasting records, tasbih counts, saved locations — stays **on your device**.

We have no analytics, no advertising SDKs, and no crash-reporting backend. There is no "us" on the network to collect anything.

One kind of data does leave your phone: to show prayer times and find nearby mosques, the app sends your **approximate location** straight from your device to independent services. Android is only ever asked for coarse location (never precise GPS), and the coordinates are rounded to about one kilometre before they are sent — enough for prayer times and a mosque search, not enough to place you. It goes to them, not to us, and it is never tied to your name or any identifier. The details are below, and we would rather spell them out than hide behind "we collect nothing".

## What stays on your device (never sent to us)

- Reading state, bookmarks, notes, highlights, collections
- Prayer log, qada counter, hayd tracker, fasting log, khatma progress
- Tasbih counts, achievements, home-dashboard layout, all settings
- Recitation audio you download for offline listening — and, if you turn on auto-save, the ayahs you play
- Your app-lock PIN — never stored, in any form. Only a salted PBKDF2 hash of it is kept, inside the Android Keystore.

Those records are held in an on-device store the app **encrypts at rest**, with a random key kept in the Android Keystore — so lifting the files off the phone does not read them. Downloaded audio and language files are ordinary media and database files in the app's private storage and are not encrypted; they are published content, and say nothing about you.

## Data sent to third parties (only to deliver a feature you use)

The app makes these requests **directly from your device** to the services below. We do not receive, proxy, or log any of it. Each service has its own privacy policy, and their handling of the data is governed by it, not by this policy.

| Feature | Service | What is sent | Why |
|---|---|---|---|
| Prayer times | Aladhan API | your approximate coordinates, rounded to ~1 km | fetch precise times for your location — sent automatically whenever the app knows where you are |
| Nearby mosques | OpenStreetMap Overpass — public mirrors run by unaffiliated operators (`overpass.kumi.systems`, `overpass-api.de`, `overpass.private.coffee`, `overpass.osm.jp`), tried in order until one answers, and sometimes two at once when the first is slow | your approximate coordinates, rounded to ~1 km | find mosques around you — sent only when you open that screen |
| City search | OpenStreetMap Nominatim | the city text you type | turn it into coordinates |
| Place name and auto calc-method | Android system geocoder (Google on most devices) | your approximate coordinates | turn your coordinates into a place name — shown on the home-screen widget so you can see which location its times are for — and look up your country to pick the locally-conventional calculation method. Sent automatically whenever the app knows where you are. The place name is kept on your device and is never sent anywhere. |
| Extra Quran translations | QuranEnc.com — published by the Rowad Translation Center (Saudi Ministry of Islamic Affairs) | the verse requested | fetch a translation you chose to add — sent only when you open it |
| Recitation audio | EveryAyah | the surah/verse requested | stream or download the recitation |
| Azkar audio | hisnmuslim.com | the dhikr requested | stream a recording when you press play, and cache it on the device once it has played through, so replaying it later needs no further request |
| Optional adhan clips | archive.org | the clip requested | download a muezzin you tapped — the clip is fetched from the public archive it already sits on, not from us |
| Language packs — Quran translation and tafsir | QuranEnc.com — published by the Rowad Translation Center (Saudi Ministry of Islamic Affairs) | the file requested | download the translation and the Mukhtasar tafsir for a language you chose — sent only when you tap that language and confirm the download |
| Language packs — hadith | `bonaishere.github.io` (GitHub Pages) | the file requested | download the pre-built hadith text for a language you chose. It is pre-built because HadeethEnc serves one hadith per request, and fetching ~2,776 of them from your device would take about eighteen minutes and place that load on a ministry's donated server |
| Tafsir library | QuranEnc.com (Rowad Translation Center) for each language's Al-Mukhtasar edition; `bonaishere.github.io` (GitHub Pages) for classical Arabic tafsirs we publish | the file requested | download an individual tafsir you chose to add from *More → Settings → Tafsir library* — sent only when you tap it |
| Mushaf editions | `bonaishere.github.io` (GitHub Pages) | the files requested | download a printed mushaf edition you chose in *More → Settings → Mushaf edition* — sent only when you tap it |
| Mushaf frame styles | `bonaishere.github.io` (GitHub Pages) | the two files (the corner ornament and the edge motif) for a frame style you chose | download a decorative page frame you tapped in *More → Settings → Mushaf edition → frame* — sent only when you tap that style |

That table is the complete list. The app contacts no other service.

Two things sit outside it because the app does not make the request itself. On the mosques screen, **Directions**, **Call** and **Website** hand off to another app — your maps app, your dialer, your browser — carrying the *mosque's* coordinates, phone number or address, never yours; what that app then does is governed by its own policy, not this one. The About screen's rows (email, the Play listing) open your mail or store app the same way.

None of these requests carries an identifier of any kind — no account, no device id, no advertising id, nothing that ties one request to another or to you. They are ordinary file and API requests, and each service sees only what any web request shows it (an IP address and the file asked for).

There is no AI assistant. Earlier builds had an optional one that used an API key you supplied; it has been removed, and any key you had stored is deleted when you update.

The zakat calculator no longer fetches gold or silver prices from any service. It used to call goldprice.org; that request is gone, you enter the nisab value yourself, and the calculator now works entirely offline.

Prayer times, the Qibla, the full Quran, the bundled translations, the hadith collections and the azkar text all work with **none** of these services — they are inside the app and never need the network. Azkar **audio** is the exception: every recording streams from hisnmuslim.com the first time you play it (see the table above), and is cached on the device once it has played through — a recording you pause, navigate away from, or that the app backgrounding interrupts is not cached, and streams again next time. Caching is automatic, with no toggle to turn it off. These recordings go to the app's OS-managed cache directory, not the storage described below — there is no in-app screen to browse or delete them individually; Android may clear this cache under storage pressure on its own, and uninstalling the app (or clearing its data in Android settings) removes it entirely.

## Downloaded languages

The app ships with Arabic and English inside it. Every other language is downloaded when you pick it — from the globe on the home screen, or in *More → Settings → Appearance* — as three database files: the Quran translation, the Mukhtasar tafsir, and the hadith text, totalling roughly 5–8 MB. Each row tells you the size before you tap it, and nothing downloads until you do.

They are stored in the app's own private storage on your device, and nothing about them is sent anywhere. A download that fails or is interrupted deletes whatever landed rather than leaving a partial language behind. There is no in-app screen for removing a language once it has landed; clearing the app's data in Android settings, or uninstalling the app, removes them all.

The interface text for those languages is **not** downloaded — it ships inside the app, so switching language works before and without any download.

## Tafsir library

Two Arabic tafsirs ship inside the app. *More → Settings → Tafsir library* lets you add more, one at a time: an Al-Mukhtasar edition in your own language (from QuranEnc.com, the same publisher as the language packs above) and classical Arabic tafsirs we publish ourselves (fetched from `bonaishere.github.io`, GitHub Pages). Each row shows its size before you tap it, nothing downloads until you do, and a tafsir you add is also selected for the aya sheet — you can deselect it there without removing the file.

They land in the same private, on-device storage as everything else described here. Unlike a language pack, a downloaded tafsir **can** be removed individually from the same screen; deleting it also deselects it. A download that fails or is interrupted deletes whatever landed rather than leaving a partial file behind.

## Mushaf editions

The app's page reader draws the Quran with a font that ships inside it, so it works offline from the first launch and nothing here is needed to read.

*More → Settings → Mushaf edition* offers other printed editions — the page fonts published by the King Fahd Glorious Quran Printing Complex — that reproduce a particular print exactly. These are **large**: 95 to 208 MB each, because an edition is one font per page for all 604 pages, and they cannot be made smaller (the publisher permits redistribution but not modification). Every row shows its size before you tap it, and nothing downloads until you do.

The files come from `bonaishere.github.io` (GitHub Pages) and land in the app's own private storage. Only the file being fetched is sent; nothing about which edition you chose is reported anywhere. Leaving the screen cancels a download in progress, and what already arrived stays so tapping again resumes rather than starting over — a download that fails deletes the whole partial edition rather than leaving a broken mushaf behind. A downloaded edition can be removed from the same screen at any time, and the reader falls straight back to the built-in one.

## Mushaf frame styles

The page reader's default border ships inside the app and needs no network. *More → Settings → Mushaf edition → frame* offers ten further decorative styles — original QuranSphere artwork, not a printed edition — each under 4 KB. Tapping one downloads exactly two SVG files, the corner ornament and the repeating edge motif, from `bonaishere.github.io` (GitHub Pages), and only then: nothing downloads until you tap a style. The files land in the app's own private storage, and nothing about you or which style you picked is sent or reported anywhere — the request carries only the two file names. A downloaded style can be removed from the same screen, and the reader falls back to the style it was drawing before.

## Downloaded recitation audio

You can save recitations for offline listening — a single surah from the reader, or a
reciter's whole recitation from **More → Reciter**. The audio files are fetched from
EveryAyah and written to the app's **own private storage** on your device. This needs no
storage permission, the app cannot see or touch anything else on your phone, and nothing
about what you downloaded is reported anywhere.

**Auto-saving what you play (optional).** You can also let the app save each ayah as
you listen, so it replays offline later without fetching it again. The first time you
play a recitation the app asks whether to turn this on, and you can change it any time in
*More → Settings → Audio* — it is **off until you choose**. When on, each ayah you play
**through to the end** is written to the same private storage as above (fetched from
EveryAyah — the same request the app already makes to play it), with no extra permission
and nothing reported anywhere; an ayah you skip past or stop part-way through is not
saved. The same screen chooses whether those saves may use mobile data — **Wi-Fi only by
default**.
Ayahs saved this way are exempt from the storage cap, so what you have listened to stays
available offline; you can remove them any time from *More → Downloads*.

A full recitation is roughly 1 GB, so the app tells you the size before it starts and
refuses to begin if the device is short on space. You control the rest:

- **Storage limit.** *More → Downloads* sets a cap. It is **unlimited by default**; pick a
  size there if you want one.
  When individually downloaded surahs go over it, the app deletes the ones you played
  least recently to stay inside the limit you chose.
- **Reciters you keep offline, and ayahs auto-saved as you play, are exempt.** They are
  never deleted automatically and do not count toward the cap — you asked for them, so
  only you remove them.
- **Delete any time.** *More → Downloads* deletes a single surah or everything at once.
  Uninstalling the app, or clearing its data in Android settings, removes all of it.

## Optional adhan clips

Two adhans are built into the app — a full one and a Fajr one — and work with no network at
all, as do the built-in iqama and pre-adhan cue. You can also choose a different clip for each
individual prayer; that choice is a setting stored on your device and is sent nowhere. The
remaining clips are marked **Tap to download**: tapping one downloads that single clip (under
1 MB) from archive.org into the app's own private storage, and it then plays offline like the
built-in ones. Nothing is downloaded until you tap, and the request goes from your device
straight to archive.org — we do not host these files, proxy the request, or learn which
muezzin you chose.

## Wear OS watch and home-screen widgets

If you install the QuranSphere companion app on a paired Wear OS watch, the phone shares your prayer times, Qibla direction and tasbih count with it so the watch can show them offline. This moves between your phone and your watch over Android's Wear Data Layer — part of Google Play Services on both devices — so it stays **on your devices**, never reaches a server we operate (we operate none), and the watch app makes no network requests of its own. The home-screen widgets (next-prayer countdown and tasbih) read that same on-device data and send nothing anywhere.

## Location

Location is used only to compute prayer times, the Qibla direction, and nearby mosques.

**Approximate only, and rounded again before it is sent.** The app asks Android for coarse location and never for precise GPS, then rounds the coordinates to two decimal places (about one kilometre) before any request leaves the device. On Android 12 and newer it cannot access precise location at all. On older versions the permission is coarser-grained, but the app still only ever reads an approximate fix.

Your coordinates are sent to the services named above so those features work. They are **never stored on any server we operate** — we operate none — and are never associated with an identity. We cannot tell you who requested what, because we never see it.

**Letting the widget follow you when you travel is on by default, does nothing unless you have given the app location permission, and is used for exactly one thing.** The home-screen prayer widget computes prayer times on your device, so it stays correct for years without the app ever being opened — but the coordinates it uses are frozen at the last time the app ran, so if you move to another city it would go on showing the times of the city you left, with nothing on the card to say so. **"Keep the widget right when I travel"** in Locations is what prevents that, and you can switch it off there.

**The app never asks for "Allow all the time".** It holds only the ordinary "While using the app" location permission — the same one prayer times and Qibla already need. When the widget needs to know where you are, it briefly runs a foreground service, which posts a notification saying the widget is updating its location and stops itself within seconds. You can see it happen; nothing reads your location silently in the background.

Even switched on, it is narrow by design:

- It uses **the last location your phone has already recorded** for some other app or system service, whenever that reading is recent enough to still mean anything.
- When it is not — which is exactly what arriving somewhere new looks like — it takes **one network location** (worked out from cell towers and Wi-Fi). It never turns on GPS, and it does this at most twice a day — or, in the few minutes after your phone tells us its timezone changed, as soon as it can. If it cannot get one then (location switched off, no signal), it waits longer before each further attempt — 15 minutes, then half an hour, then an hour, up to eight — rather than asking again and again.
- It does both **only for the widget**, and only if you are on "Current location" — a city you saved by hand is never overridden.
- If it cannot work out where you are, the widget **stops showing times** and asks you to open the app, rather than showing you another city's prayer times as though they were yours.
- The coordinates are used **on your device only**, to recompute prayer times. Turning this on sends nothing new anywhere. The one reading the widget is currently working from is kept on your device so it can draw without asking again; nothing older is retained.
- It changes nothing until you have actually moved about 25 km.

You can switch it off in the app at any time, or revoke the permission in Android's settings — the widget re-checks the permission every time it draws, and simply goes back to the last coordinates the app saw.

You can skip location permission entirely and enter a city by hand instead; every location-based feature works that way, and the travel option is then neither needed nor offered.

**Prayer alerts do the same thing with the location already on your device, and take no new reading of any kind.** So that the adhan does not stop on a phone you have not opened in a while, the app keeps a queue of upcoming prayer alerts and extends it — when a prayer alert fires, when your phone restarts, and when Android wakes the app for a moment (see *Background processing* below). Extending it recomputes prayer times **on your device** from the coordinates already saved and the settings you chose. Nothing is sent, nothing is fetched, and unlike the widget option above this never asks your phone where it is: it only reads what is already stored.

Because those coordinates are frozen at the last time you opened the app, the same travelling problem applies — so the app applies the same rule. If your phone's timezone no longer matches the one those coordinates were saved in, and you have not pinned a city by hand, the app **stops extending the queue** rather than go on announcing the prayer times of the city you left. Alerts already scheduled still sound; opening the app puts it right.

## Permissions and why each is needed

| Permission | Why |
|---|---|
| Location (approximate) | Prayer times, Qibla, nearby mosques. Optional — a manually entered city works instead. Precise location is not used; on Android 11 and older the system grants a broader location permission, but the app only ever reads an approximate fix. |
| Foreground service (location) | **On by default with "Keep the widget right when I travel", which you can switch off in Locations; it does nothing at all unless you have granted location permission.** Only so the home-screen prayer widget can notice you have moved to another city and recompute, with the app never opened. It runs for a few seconds, shows a notification while it does, and stops itself. It uses the last fix your phone already recorded, and takes one network location (never GPS) when that fix is too old to trust. The coordinates never leave the device. The app does **not** request "Allow all the time". See Location above. |
| Notifications | The adhan and any reminders you switch on, and an ongoing status-bar notification showing the current prayer and a live countdown to the next — **on by default**. It is silent, shows nothing beyond what the home-screen widget already displays, and is computed entirely on your device from the location and settings data already described above; nothing new is sent anywhere for it. Turn it off any time in Settings → Notifications, or dismiss it directly with its own Hide button in the notification itself. |
| Exact alarms | The adhan must sound at the exact prayer instant. An inexact alarm would make the call to prayer late, which defeats the feature. Android grants this to alarm-clock apps automatically and it cannot be revoked; it lets the app set alarms and nothing else — it reads no data and reaches no network. |
| Foreground service (media playback) | Plays the full adhan and Quran recitation with the screen off or the app closed. |
| Run at startup | Re-arms the prayer alarms after you restart your phone **or after the app updates** — both wipe every alarm the app had set, so without this the adhan would silently stop until you next opened it. |
| Background processing | Lets Android wake the app roughly twice a day, for a moment, to extend the queue of upcoming prayer alerts. Nothing is sent or fetched: it reads the settings and the last location already on your device, recomputes prayer times on the device, and re-sets the alarms. Without it the queue eventually runs out and the adhan stops on a phone that has not been opened for a while. |
| Ignore battery optimisations | Optional, and only prompted. Without it, some manufacturers' battery managers delay or kill the exact prayer alarm. |
| Vibrate | Vibrate-mode prayer alerts, tasbih haptics, and the haptic pulse in the accessible Qibla mode. |

The app does **not** request camera, microphone, contacts, or file-storage access.

## Importing your own adhan

You can use your own recording as the call to prayer. Tapping **import** opens your device's own file picker, you choose a single audio file, and the app copies that one file into its private storage so it can play at prayer time. The app receives nothing except the file you pick — it cannot browse your storage, it never reads a second file, and the imported audio is **never uploaded anywhere**. It stays on your device and is deleted when you remove it in the app or uninstall.

## Purchases

QuranSphere is free, and no feature is behind a paywall. There are no in-app purchases, no subscriptions, no Google Play Billing, and no donation link — the app takes no money at all, so it never sees a payment, a card, or a billing detail.

## Children

The app is suitable for all ages. It has no accounts, no chat, no user-generated content and no advertising, and it asks no one their age or identity. The only data that leaves the device is the approximate location described above, which is treated the same way for every user and is never profiled or linked to a person.

## Backup export

You can export your data to a file you control, optionally encrypted with a passphrase you choose. That file is created by you, stored where you choose, and never sent to us. If you lose the passphrase, we cannot recover the file — we do not have it.

## Your rights

We hold no data about you, so there is nothing for us to disclose, correct, or delete — there is no account to close and no server to erase you from. Uninstalling the app removes everything it stored. You can also clear the app's data from Android's settings at any time. For the approximate coordinates sent to Aladhan or OpenStreetMap, their own privacy policies govern retention; you can avoid sending them at all by declining the location permission and entering a city by hand.

## Changes

Material changes will be reflected here with a new "last updated" date.

## Contact

**bonaishere** — [bonaishere@hotmail.com](mailto:bonaishere@hotmail.com)
