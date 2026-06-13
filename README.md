# OpenELEC 6.0.3 SD Card — Rixhal's Legacy System

**Fund:** 2026-06-13 on a 8 GB SD card
**Analyzed by:** Hermes Enterprise on Crackberry Pi

---

## System Overview

| Component | Details |
|---|---|
| **OS** | OpenELEC 6.0.3 (official) |
| **Kodi** | 15.2 Isengard (Git: 02e7013) |
| **Architecture** | ARM 32-bit (ARMv7), 4 cores, Neon |
| **Hardware** | Raspberry Pi 2 Model B |
| **Kernel** | Linux 4.1.18 |
| **Compiler** | GCC 4.9.3 |
| **FFmpeg** | 2.6.4 (unsupported per Kodi warning) |
| **Hostname** | OpenELEC |
| **Build date** | March 1, 2016 |
| **Last activity** | October 22, 2016 |
| **SD Card** | 7.4 GB (256 MB boot + 7.2 GB root) |

## Filesystem Layout

```
SD CARD (/dev/mmcblk0)
├── p1 (256M FAT) — BOOT
│   ├── kernel.img          Linux kernel (zImage ARM)
│   ├── SYSTEM              SquashFS root (107 MB, LZO, 7934 inodes)
│   ├── config.txt           Pi boot configuration
│   ├── cmdline.txt          boot=/dev/mmcblk0p1 disk=/dev/mmcblk0p2 quiet
│   ├── start.elf            GPU firmware
│   ├── bootcode.bin         Bootloader
│   ├── fixup.dat            GPU fixup
│   └── overlays/            Device tree overlays
│       ├── bcm2709-rpi-2-b.dtb
│       └── bcm2710-rpi-3-b.dtb
│
└── p2 (7.2G ext4) — ROOT (/storage)
    ├── .kodi/               Kodi userdata
    │   ├── addons/          69 addons
    │   ├── userdata/        Settings, DBs, thumbnails
    │   └── temp/            Crash logs (2016)
    ├── music/
    ├── pictures/
    ├── screenshots/
    ├── tvshows/
    ├── videos/
    └── .ssh/                Empty — no SSH keys
```

## Installed Skins

| Skin | Type |
|---|---|
| **Aeon MQ6** | Heavyweight media center skin |
| Conq | Lightweight skin |
| sio2 | Minimal skin |
| Skin Shortcuts | Widget helper |
| Skin Widgets | Service |

## Installed Addons (69 total)

### Streaming & Video

| Addon | Notes |
|---|---|
| ARD Mediathek | German public TV |
| ZDF Mediathek | German public TV |
| Arte+7 / Arte TV | Franco-German culture |
| Rocketbeans TV Live | German gaming/nerd TV |
| YouTube | With youtube.dl module |
| Twitch | Game streaming |
| South Park (unofficial) | Comedy Central |
| iTunes Podcasts | |

### Metadata Scrapers

- TheMovieDB (movies + TV)
- TheTVDB
- TheAudioDB
- MusicBrainz
- IMDb
- OFDb (German movie DB)
- Universal Album/Artist scrapers

### Repositories

| Repo | Notes |
|---|---|
| Kodi Official (xbmc.org) | |
| Unofficial Addon Pro | Third-party German addon repo |

## Network Sources

| Name | Path |
|---|---|
| HD Movies | `smb://CBNPC/HD Movies/` |
| HD Movies II | `smb://CBNPC/HD Movies II/` |
| HD Movies III | `smb://CBNPC/HD Movies III/` |
| Detektiv Conan | `smb://CBNPC/G/Series/Detektiv Conan/` |

> **CBNPC** was likely a Windows PC or NAS on Rixhal's home network in 2016.

## Crash History

The system has 10 crash logs spanning January–October 2016:

| Date | Size |
|---|---|
| 2016-01-17 | Crashlog |
| 2016-02-13 | Crashlog |
| 2016-02-15 | Crashlog |
| 2016-02-20 | Crashlog |
| 2016-05-19 | Crashlog |
| 2016-06-22 | 1.3 MB crashlog |
| 2016-09-07 | 64 MB crashlog (massive!) |
| 2016-10-22 | 0 bytes (empty) |

The **64 MB crashlog** from September 2016 suggests a severe recurring crash loop.

## Historical Significance

- **OpenELEC** was the predecessor to LibreELEC. The fork happened in March 2016 — this SD card was from the final OpenELEC 6.0 era.
- **Isengard (15.2)** was the last 32-bit ARM Kodi release before Jarvis (16.x).
- This system represents Rixhal's home theater setup from ~2015-2016, complete with German TV addons and SMB network shares.
- The SD card survived ~10 years before being rediscovered in 2026 on the Crackberry Pi.

---

*Analysis by Hermes Enterprise, June 13, 2026*
