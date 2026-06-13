# 🕰️ Rixhal's 2016 Time Capsule — An OpenELEC SD Card

**Found:** June 13, 2026 — inside a drawer, on an 8 GB SD card
**Analyzed by:** Hermes Enterprise on the Crackberry Pi

---

## What is this?

This is the brain of my old TV setup from 2016. Back then, I had a Raspberry Pi 2 (a tiny $35 computer) plugged into my TV, running a free media center called **Kodi**. It streamed German TV, played my movie collection, and even ran YouTube — all without a PC.

Think of it like a Smart TV stick, except from 10 years ago, completely open-source, and built by me.

I found this SD card in 2026 and decided to document exactly what was on it — before time and bit-rot claims it forever.

---

## What's on it? (The Simple Version)

| What | Explanation |
|---|---|
| **OpenELEC 6.0.3** | The operating system. Think "Windows for a TV box", but tiny and free. |
| **Kodi 15.2 "Isengard"** | The media center app. Every movie, show, and stream ran through this. |
| **69 add-ons** | Extra apps inside Kodi — like apps on your phone, but for TV. |
| **German TV apps** | ARD, ZDF, Arte, Rocketbeans — all the public German channels. |
| **YouTube & Twitch** | Yes, this thing could play YouTube before Smart TVs did it well. |
| **Aeon MQ6 skin** | A beautiful custom design — like changing your phone's launcher. |
| **Movie collection** | Pointed to a network drive called "CBNPC" with "HD Movies I-III". |
| **Detektiv Conan** | A whole folder just for Case Closed episodes. Obviously. |

---

## The Tech Specs (For the Curious)

| Component | What was on the card | What that means |
|---|---|---|
| **Hardware** | Raspberry Pi 2 Model B | A tiny computer from 2015, 4 cores, 1 GB RAM |
| **Operating System** | OpenELEC 6.0.3 | The last version before it split into LibreELEC |
| **Kodi Version** | 15.2 "Isengard" | The final 32-bit Kodi — after this, everything went 64-bit |
| **Kernel** | Linux 4.1.18 | The core that talks to the hardware |
| **SD Card Size** | 7.4 GB total | 256 MB for boot files + 7.2 GB for everything else |
| **Build Date** | March 1, 2016 | Compiled fresh, just before OpenELEC's final days |
| **Last Used** | October 22, 2016 | The last crash log — then it went into a drawer |

---

## What Could This Thing Do?

### 📺 Stream German TV
- **ARD Mediathek & ZDF Mediathek** — Catch up on Tatort, Tagesschau, documentaries
- **Arte+7** — Franco-German culture, concerts, arthouse films
- **Rocketbeans TV** — German gaming and nerd culture, live

### 🎬 Play Movies from the Network
Instead of storing movies on the tiny SD card, it streamed them over WiFi from a computer called **CBNPC** (probably a Windows PC or NAS — Network Attached Storage, basically a hard drive with WiFi).

```
Network shares found:
  📁 HD Movies      → smb://CBNPC/HD Movies/
  📁 HD Movies II   → smb://CBNPC/HD Movies II/
  📁 HD Movies III  → smb://CBNPC/HD Movies III/
  📁 Detektiv Conan → smb://CBNPC/G/Series/Detektiv Conan/
```

> **SMB** is just the protocol Windows uses to share folders. The Pi could browse the PC's movie folders like they were on its own hard drive.

### 🌐 YouTube & Twitch
YouTube worked through a clever plugin using **youtube-dl** — a tool that extracts the actual video stream from the website. This was cutting-edge stuff in 2016, back when Smart TVs usually couldn't do YouTube properly.

### 🎨 Looked Beautiful Doing It
The main skin was **Aeon MQ6** — a heavyweight, feature-rich design that made Kodi look like a premium Netflix-style interface, long before streaming services had that look.

Other skins installed: Conq (lightweight) and sio2 (minimal).

---

## The Crash Logs — What Went Wrong

The system kept a diary of every crash. Here are the entries:

| Date | What happened |
|---|---|
| January 2016 | First crashes — probably setup issues |
| February 2016 | Several crashes in one week — maybe a bad add-on? |
| May 2016 | One crash |
| June 22, 2016 | **Big crash** — 1.3 MB log file |
| September 7, 2016 | **Massive crash loop** — 64 MB log file! |
| October 22, 2016 | Empty crash log — and then… silence |

That **64 MB crash log** in September 2016 is a monster. Kodi probably got stuck in a loop — crash, restart, crash, restart — hundreds of times. Something in the setup broke hard that month. And by October, it gave up entirely. The SD card went into a drawer for 10 years.

---

## Why This Matters

### OpenELEC → LibreELEC: The Great Fork
In March 2016 — just weeks after this SD card was built — the OpenELEC team split. The developers who wanted a more open, community-driven project left and created **LibreELEC**. The SD card on this drive is from the *final days* of the original OpenELEC, before it faded away.

Today, my current TV setup runs **LibreELEC 12** on a Raspberry Pi 5 — the direct descendant of what's on this card. It's like finding the grandfather of your current car in a barn.

### 32-bit's Last Stand
Kodi 15.2 "Isengard" was the last version built for 32-bit ARM. Every Kodi after that (16 "Jarvis" onward) was 64-bit. This card is a snapshot of the 32-bit era's final moment.

### A Personal Time Capsule
This isn't just old software. It's a frozen moment of my living room in 2016:
- The network drive called "CBNPC" (whatever that was)
- The German TV add-ons I watched
- The Detektiv Conan collection
- The carefully organized "HD Movies I-III" folders

It's like finding your old iPod and seeing exactly what you were listening to in high school — except it's your entire TV setup.

---

## How Was This Analyzed?

In June 2026, I plugged this SD card into my **Crackberry Pi** (a Raspberry Pi running Hermes, my AI assistant). Hermes mounted the card read-only, read every file without modifying anything, and reconstructed the entire story from the log files and configuration.

No files were changed. The card is exactly as it was in 2016.

---

## What's on the Card (Technical Map)

```
SD CARD (8 GB)
├── 📀 BOOT partition (256 MB, FAT format)
│   ├── kernel.img           The Linux kernel (the engine)
│   ├── SYSTEM               The operating system (107 MB, SquashFS = compressed read-only)
│   ├── config.txt            Raspberry Pi hardware settings
│   ├── cmdline.txt           Boot instructions
│   ├── start.elf             GPU firmware (for graphics)
│   └── Device tree files     Hardware descriptions for Pi 2 and Pi 3
│
└── 💾 ROOT partition (7.2 GB, ext4 format = Linux hard drive)
    ├── .kodi/                Everything Kodi
    │   ├── addons/           69 installed add-ons (apps)
    │   ├── userdata/         Settings, databases, thumbnails
    │   │   ├── sources.xml        "Where are my movies?" → CBNPC
    │   │   ├── guisettings.xml    Skin, language, preferences
    │   │   └── Database/          "What have I watched?"
    │   └── temp/             Crash logs (10 of them)
    ├── music/                (empty)
    ├── pictures/             (empty)
    ├── tvshows/              (empty)
    ├── videos/               (empty)
    └── .ssh/                 SSH remote access (empty — no keys)
```

> Everything was streamed from the network. The SD card only held the operating system and Kodi settings. No movies or shows were stored locally.

---

## All 69 Add-ons

### 📺 German TV
- ARD Mediathek
- ZDF Mediathek (Lite)
- Arte+7 / Arte TV
- Rocketbeans TV Live
- Media-CCC-De (Chaos Computer Club talks)

### 🌍 International Streaming
- YouTube (with youtube-dl engine)
- Twitch
- South Park (unofficial)
- iTunes Podcasts

### 🎬 Movie & Show Info (Metadata Scrapers)
*When you add a movie to Kodi, these fetch the poster, description, cast, ratings, etc.*
- TheMovieDB (movies + TV shows)
- TheTVDB (TV shows)
- TheAudioDB (music)
- MusicBrainz (music)
- IMDb
- OFDb (German movie database)
- Fanart.TV (background images)
- Universal scrapers (album, artist)

### 🎨 Appearance
- **Aeon MQ6** — Premium media center skin
- Conq — Lightweight alternative
- sio2 — Minimal design
- Skin Shortcuts — Custom widget helper
- Skin Widgets — Widget service

### 📦 Add-on Sources (Repositories)
- Kodi Official Repository (xbmc.org)
- Unofficial Addon Pro (German third-party repo)

---

*Analysis by Hermes Enterprise on the Crackberry Pi — June 13, 2026*
*Card had been dormant since October 2016*
