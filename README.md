# 🕰️ Atzes Zeitkapsel von 2016 — Eine OpenELEC SD-Karte

**Gefunden:** 13. Juni 2026 — in einer Schublade, auf einer 8 GB SD-Karte
**Für:** Atze

---

## Worum geht's hier?

Das ist das Gehirn von Atzes altem Fernseh-Setup aus dem Jahr 2016. Damals hatte er einen **Raspberry Pi 2** (ein winziger Computer für 35 €) am Fernseher hängen. Darauf lief ein kostenloses Mediencenter namens **Kodi**. Damit konnte er:

- Deutsches Fernsehen streamen (ARD, ZDF, Arte)
- Seine Filmsammlung übers Netzwerk abspielen
- YouTube und Twitch gucken
- Das Ganze sah auch noch richtig gut aus

Stell dir das vor wie einen Smart-TV-Stick — nur von vor 10 Jahren, komplett Open-Source, und selbst eingerichtet.

Die SD-Karte lag seit Oktober 2016 in der Schublade. Jetzt hab ich sie analysiert und dokumentiert — bevor sie endgültig den Geist aufgibt.

---

## Was ist da drauf? (Einfach erklärt)

| Was | Erklärung |
|---|---|
| **OpenELEC 6.0.3** | Das Betriebssystem. Wie Windows, aber für den Fernseher — nur winzig und kostenlos. |
| **Kodi 15.2 „Isengard"** | Die Mediencenter-App. Alle Filme, Serien und Streams liefen hier durch. |
| **69 Add-ons** | Zusatz-Apps in Kodi — wie Apps auf dem Handy, nur für den Fernseher. |
| **Deutsche TV-Apps** | ARD, ZDF, Arte, Rocketbeans — das komplette deutsche ÖR-Paket. |
| **YouTube & Twitch** | Ja, das Ding konnte YouTube — zu einer Zeit, als viele Smart-TVs das noch nicht konnten. |
| **Aeon MQ6 Skin** | Ein wunderschönes Design — wie wenn man bei seinem Handy den Look komplett ändert. |
| **Filmsammlung** | Per Netzwerk von einem Rechner namens „CBNPC" gestreamt: „HD Movies I-III". |
| **Detektiv Conan** | Ein ganzer Ordner nur für Conan-Folgen. Logisch. |

---

## Die Technik dahinter (Für Neugierige)

| Komponente | Was auf der Karte ist | Was das bedeutet |
|---|---|---|
| **Hardware** | Raspberry Pi 2 Model B | Ein Minicomputer von 2015, 4 Kerne, 1 GB RAM |
| **Betriebssystem** | OpenELEC 6.0.3 | Die letzte Version vor der Spaltung in LibreELEC |
| **Kodi Version** | 15.2 „Isengard" | Das letzte 32-Bit Kodi — danach alles 64-Bit |
| **Kernel** | Linux 4.1.18 | Der Unterbau, der mit der Hardware redet |
| **SD-Karte** | 7,4 GB | 256 MB für Startdateien + 7,2 GB für alles andere |
| **Erstellt am** | 1. März 2016 | Frisch kompiliert, kurz vor OpenELECs Ende |
| **Zuletzt genutzt** | 22. Oktober 2016 | Der letzte Absturz-Log — dann ab in die Schublade |

---

## Was konnte das Ding alles?

### 📺 Deutsches Fernsehen streamen
- **ARD Mediathek & ZDF Mediathek** — Tatort, Tagesschau, Dokus
- **Arte+7** — Deutsch-französisches Kulturprogramm, Konzerte, Arthouse-Filme
- **Rocketbeans TV** — Gaming und Nerdkultur, live

### 🎬 Filme aus dem Netzwerk abspielen
Statt Filme auf der winzigen SD-Karte zu speichern, hat der Pi sie übers WLAN von einem anderen Rechner geholt. Der hieß **CBNPC** (wahrscheinlich ein Windows-PC oder ein NAS — also eine Festplatte mit Netzwerkanschluss).

```
Gefundene Netzwerk-Freigaben:
  📁 HD Movies      → smb://CBNPC/HD Movies/
  📁 HD Movies II   → smb://CBNPC/HD Movies II/
  📁 HD Movies III  → smb://CBNPC/HD Movies III/
  📁 Detektiv Conan → smb://CBNPC/G/Series/Detektiv Conan/
```

> **SMB** ist einfach das Protokoll, mit dem Windows Ordner im Netzwerk teilt. Der Pi konnte auf die Filmordner vom PC zugreifen, als wären sie auf seiner eigenen Festplatte.

### 🌐 YouTube & Twitch
YouTube lief über ein cleveres Plugin namens **youtube-dl** — das holt den echten Videostream aus der Webseite raus. Das war 2016 ziemlich fortschrittlich. Normale Smart-TVs konnten YouTube damals oft nur mit Einschränkungen.

### 🎨 Sah verdammt gut aus
Der Haupt-Skin war **Aeon MQ6** — ein aufwändiges, funktionsreiches Design. Damit sah Kodi aus wie eine Premium-Streaming-Oberfläche — lange bevor Netflix & Co. so aussahen.

Andere installierte Skins: Conq (leichtgewichtig) und sio2 (minimal).

---

## Die Absturz-Logs — Was lief schief?

Das System hat ein Tagebuch über jeden Absturz geführt. Hier sind die Einträge:

| Datum | Was passiert ist |
|---|---|
| Januar 2016 | Erste Abstürze — vermutlich Einrichtungsprobleme |
| Februar 2016 | Mehrere Abstürze in einer Woche — vielleicht ein kaputtes Add-on? |
| Mai 2016 | Ein Absturz |
| 22. Juni 2016 | **Dicker Absturz** — 1,3 MB Logdatei |
| 7. September 2016 | **Massive Absturz-Schleife** — 64 MB Logdatei! |
| 22. Oktober 2016 | Leeres Absturz-Log — und dann… Stille |

Dieses **64 MB Absturz-Log** von September 2016 ist ein Monster. Kodi ist wahrscheinlich in einer Schleife steckengeblieben: abstürzen, neustarten, abstürzen, neustarten — hunderte Male. Irgendwas hat sich in dem Monat richtig zerschossen. Im Oktober hat es dann endgültig aufgegeben. Die SD-Karte wanderte für 10 Jahre in die Schublade.

---

## Warum ist das interessant?

### OpenELEC → LibreELEC: Die große Spaltung
Im März 2016 — nur wenige Wochen nachdem diese SD-Karte erstellt wurde — hat sich das OpenELEC-Team zerstritten. Die Entwickler, die ein offeneres Projekt wollten, sind gegangen und haben **LibreELEC** gegründet. Diese SD-Karte stammt aus den *letzten Tagen* des ursprünglichen OpenELEC, bevor es von LibreELEC abgelöst wurde.

### 32-Bit's letzter Auftritt
Kodi 15.2 „Isengard" war die letzte Version für 32-Bit-Prozessoren. Jedes Kodi danach (16 „Jarvis" aufwärts) lief nur noch auf 64-Bit. Diese Karte ist eine Momentaufnahme vom Ende der 32-Bit-Ära.

### Eine persönliche Zeitkapsel
Das ist nicht nur alte Software. Es ist ein eingefrorener Moment von Atzes Wohnzimmer im Jahr 2016:
- Der Netzwerkrechner „CBNPC" (was auch immer das genau war)
- Die deutschen TV-Add-ons, die er geguckt hat
- Die Detektiv-Conan-Sammlung
- Die liebevoll sortierten „HD Movies I-III"-Ordner

Wie wenn man seinen alten iPod findet und genau sieht, was man in der zehnten Klasse gehört hat — nur dass es das komplette TV-Setup ist.

---

## Wie wurde das analysiert?

Im Juni 2026 hab ich die SD-Karte in den **Crackberry Pi** gesteckt und analysiert. Die Karte wurde nur-lesend eingebunden — jede Datei gelesen, nichts verändert. Die ganze Geschichte ist aus den Logdateien und Einstellungen rekonstruiert.

**Es wurde keine einzige Datei verändert.** Die Karte ist exakt so, wie sie 2016 war.

---

## Was ist wo auf der Karte? (Technische Karte)

```
SD-KARTE (8 GB)
├── 📀 START-Partition (256 MB, FAT-Format)
│   ├── kernel.img           Der Linux-Kernel (der Motor)
│   ├── SYSTEM               Das Betriebssystem (107 MB, komprimiert, nur-lesbar)
│   ├── config.txt            Raspberry Pi Hardware-Einstellungen
│   ├── cmdline.txt           Start-Anweisungen
│   ├── start.elf             GPU-Firmware (für die Grafik)
│   └── Gerätebaum-Dateien    Hardware-Beschreibungen für Pi 2 und Pi 3
│
└── 💾 HAUPT-Partition (7,2 GB, ext4-Format = Linux-Festplatte)
    ├── .kodi/                Alles rund um Kodi
    │   ├── addons/           69 installierte Add-ons (Apps)
    │   ├── userdata/         Einstellungen, Datenbanken, Vorschaubilder
    │   │   ├── sources.xml        „Wo sind meine Filme?" → CBNPC
    │   │   ├── guisettings.xml    Skin, Sprache, Einstellungen
    │   │   └── Database/          „Was hab ich schon geguckt?"
    │   └── temp/             Absturz-Logs (10 Stück)
    ├── music/                (leer)
    ├── pictures/             (leer)
    ├── tvshows/              (leer)
    ├── videos/               (leer)
    └── .ssh/                 SSH-Fernzugriff (leer — keine Schlüssel)
```

> Alles wurde übers Netzwerk gestreamt. Die SD-Karte enthielt nur das Betriebssystem und Kodi-Einstellungen. Keine Filme oder Serien waren lokal gespeichert.

---

## Alle 69 Add-ons

### 📺 Deutsches Fernsehen
- ARD Mediathek
- ZDF Mediathek (Lite)
- Arte+7 / Arte TV
- Rocketbeans TV Live
- Media-CCC-De (Chaos Computer Club Vorträge)

### 🌍 Internationales Streaming
- YouTube (mit youtube-dl-Engine)
- Twitch
- South Park (inoffiziell)
- iTunes Podcasts

### 🎬 Film- & Serien-Infos (Metadata-Scraper)
*Wenn man einen Film zu Kodi hinzufügt, holen diese Add-ons automatisch Poster, Beschreibung, Besetzung, Bewertungen usw.*
- TheMovieDB (Filme + Serien)
- TheTVDB (Serien)
- TheAudioDB (Musik)
- MusicBrainz (Musik)
- IMDb
- OFDb (deutsche Filmdatenbank)
- Fanart.TV (Hintergrundbilder)
- Universal Scraper (Alben, Künstler)

### 🎨 Aussehen
- **Aeon MQ6** — Premium Mediencenter-Design
- Conq — Leichtgewichtige Alternative
- sio2 — Minimalistisches Design
- Skin Shortcuts — Eigene Schnellzugriffe
- Skin Widgets — Widget-Dienst

### 📦 Add-on-Quellen (Repositories)
- Kodi offizielles Repository (xbmc.org)
- Unofficial Addon Pro (deutsches Drittanbieter-Repo)

---

*Analysiert auf dem Crackberry Pi — 13. Juni 2026*
*Die Karte lag seit Oktober 2016 unberührt*
