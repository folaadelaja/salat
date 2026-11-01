# Adhan · Prayer, Qibla & Quran

A mobile-friendly, installable web app with prayer times, Qibla direction, Quran recitation, and a daily authentic hadith reminder.

## Run locally

No build step or dependencies are required:

```sh
python3 -m http.server 8080 --directory dist
```

Open http://localhost:8080. Production hosting needs HTTPS for location, compass sensors, and service workers.

## Features

- Automatic location detection, with city and US ZIP code search
- Prayer calculation methods and Asr school settings
- Current time in the selected location's time zone
- Qibla bearing and supported phone compass sensors (iPhone requires a permission tap)
- Dark mode by default and a saved light/dark preference
- Quran audio: 154 reciters, 114 surahs, continuous playback, and saved selections
- Daily hadith: seven verified references from Sahih al-Bukhari and Sahih Muslim, rotating by the selected location's calendar date (device date before a location is selected)
- Home Screen installation and offline access to cached app assets and the last loaded prayer schedule; Quran audio requires a connection

## Quran reader

Browse all 114 surahs and 30 juz. Search by English/Arabic surah names or numbers, or juz number and starting surah. Uthmani Arabic is bold with adjustable text size. Last section and size are remembered; the last three opened sections are cached locally. New sections need internet access. Arabic text is fetched without modification from [Al Quran Cloud](https://alquran.cloud/api).

## Sources

Prayer data: [AlAdhan](https://aladhan.com/prayer-times-api).
Quran audio/catalog: [MP3Quran](https://www.mp3quran.net/eng/api).
Hadith references: [Sunnah.com](https://sunnah.com). Each reminder is labeled as a short English rendering of meaning or excerpt, with narrator, collection, number, and a full-source link. No AI-generated hadith text or unverified random-hadith feed is used.

The hadith selection is in `dist/hadith.js`. Existing browser storage retains the original `sakinah-` keys to preserve user settings after the rename.

## iPhone installation

Open the hosted app in Safari, then Share → Add to Home Screen. Tap Play to start recitation. Grant location and motion/orientation permissions when prompted.

## Privacy and hosting

Preferences and saved schedules are stored locally in the browser. Selected addresses or coordinates are sent to AlAdhan; audio streams from MP3Quran. This repository contains only application source and public assets, without saved user locations, credentials, or hosting-account configuration. Serve `dist/` on any HTTPS static host. Hosted site deployment is managed separately through Sites.
