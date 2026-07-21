---
layout: default
title: Privacy Policy — QuranSphere
permalink: /
---

# Privacy Policy — QuranSphere

_Last updated: 22 July 2026_

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

## Data sent to third parties (only to deliver a feature you use)

The app makes these requests **directly from your device** to the services below. We do not receive, proxy, or log any of it. Each service has its own privacy policy, and their handling of the data is governed by it, not by this policy.

| Feature | Service | What is sent | Why |
|---|---|---|---|
| Prayer times | Aladhan API | your approximate coordinates, rounded to ~1 km | fetch precise times for your location — sent automatically whenever the app knows where you are |
| Nearby mosques | OpenStreetMap Overpass — public mirrors run by unaffiliated operators (`overpass.kumi.systems`, `overpass-api.de`, `overpass.private.coffee`, `overpass.osm.jp`), tried in order until one answers, and sometimes two at once when the first is slow | your approximate coordinates, rounded to ~1 km | find mosques around you — sent only when you open that screen |
| City search | OpenStreetMap Nominatim | the city text you type | turn it into coordinates |
| Auto calc-method | Android system geocoder (Google on most devices) | your approximate coordinates | look up your country to pick the locally-conventional calculation method — sent automatically unless you choose a method by hand |
| Extra Quran translations | QuranEnc.com — published by the Rowad Translation Center (Saudi Ministry of Islamic Affairs) | the verse requested | fetch a translation you chose to add — sent only when you open it |
| Recitation audio | EveryAyah | the surah/verse requested | stream or download the recitation |
| Optional adhan clips | archive.org | the clip requested | download a muezzin you tapped — the clip is fetched from the public archive it already sits on, not from us |

That table is the complete list. The app contacts no other service.

There is no AI assistant. Earlier builds had an optional one that used an API key you supplied; it has been removed, and any key you had stored is deleted when you update.

The zakat calculator no longer fetches gold or silver prices from any service. It used to call goldprice.org; that request is gone, you enter the nisab value yourself, and the calculator now works entirely offline.

Prayer times, the Qibla, the full Quran, the bundled translations, the hadith collections and the azkar all work with **none** of these services — they are inside the app and never need the network.

## Downloaded recitation audio

You can save recitations for offline listening — a single surah from the reader, or a
reciter's whole recitation from **More → Reciter**. The audio files are fetched from
EveryAyah and written to the app's **own private storage** on your device. This needs no
storage permission, the app cannot see or touch anything else on your phone, and nothing
about what you downloaded is reported anywhere.

**Auto-saving what you play (optional).** You can also let the app save each ayah as
you listen, so it replays offline later without fetching it again. The first time you
play a recitation the app asks whether to turn this on, and you can change it any time in
*Settings → Audio* — it is **off until you choose**. When on, each ayah you play is
written to the same private storage as above (fetched from EveryAyah — the same request
the app already makes to play it), with no extra permission and nothing reported anywhere.
Ayahs saved this way are exempt from the storage cap, so what you have listened to stays
available offline; you can remove them any time from *More → Downloads*.

A full recitation is roughly 1 GB, so the app tells you the size before it starts and
refuses to begin if the device is short on space. You control the rest:

- **Storage limit.** *More → Downloads* sets a cap (500 MB by default, or unlimited).
  When individually downloaded surahs go over it, the app deletes the ones you played
  least recently to stay inside the limit you chose.
- **Reciters you keep offline, and ayahs auto-saved as you play, are exempt.** They are
  never deleted automatically and do not count toward the cap — you asked for them, so
  only you remove them.
- **Delete any time.** *More → Downloads* deletes a single surah or everything at once.
  Uninstalling the app, or clearing its data in Android settings, removes all of it.

## Optional adhan clips

One adhan is built into the app and works with no network at all. The others are marked
**Tap to download**: tapping one downloads that single clip (under 1 MB) from archive.org
into the app's own private storage, and it then plays offline like the built-in one. Nothing
is downloaded until you tap, and the request goes from your device straight to archive.org —
we do not host these files, proxy the request, or learn which muezzin you chose.

## Location

Location is used only to compute prayer times, the Qibla direction, and nearby mosques.

**Approximate only, and rounded again before it is sent.** The app asks Android for coarse location and never for precise GPS, then rounds the coordinates to two decimal places (about one kilometre) before any request leaves the device. On Android 12 and newer it cannot access precise location at all. On older versions the permission is coarser-grained, but the app still only ever reads an approximate fix.

Your coordinates are sent to the services named above so those features work. They are **never stored on any server we operate** — we operate none — and are never associated with an identity. We cannot tell you who requested what, because we never see it.

Background location is disabled entirely — the app cannot read your location when it is not open.

You can skip location permission and enter a city by hand instead; every location-based feature works that way.

## Permissions and why each is needed

| Permission | Why |
|---|---|
| Location (approximate) | Prayer times, Qibla, nearby mosques. Optional — a manually entered city works instead. Precise location is not used; on Android 11 and older the system grants a broader location permission, but the app only ever reads an approximate fix. |
| Notifications | The adhan and any reminders you switch on. |
| Exact alarms | The adhan must sound at the exact prayer instant. An inexact alarm would make the call to prayer late, which defeats the feature. |
| Foreground service (media playback) | Plays the full adhan and Quran recitation with the screen off or the app closed. |
| Run at startup | Re-arms the prayer alarms after you restart your phone, so the adhan does not silently stop working. |
| Ignore battery optimisations | Optional, and only prompted. Without it, some manufacturers' battery managers delay or kill the exact prayer alarm. |
| Vibrate | Vibrate-mode prayer alerts, tasbih haptics, and the haptic pulse in the accessible Qibla mode. |

The app does **not** request camera, microphone, contacts, or file-storage access.

## Importing your own adhan

You can use your own recording as the call to prayer. Tapping **import** opens your device's own file picker, you choose a single audio file, and the app copies that one file into its private storage so it can play at prayer time. The app receives nothing except the file you pick — it cannot browse your storage, it never reads a second file, and the imported audio is **never uploaded anywhere**. It stays on your device and is deleted when you remove it in the app or uninstall.

## Purchases

QuranSphere is free, and no feature is behind a paywall. Donations are entirely optional, give you nothing in return, and are handled **outside** the app by PayPal or Vodafone Cash — we never see your card or billing details. There are no in-app purchases and no Google Play Billing.

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
