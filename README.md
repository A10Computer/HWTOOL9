<div align="center">

# 🖥️ HWTOOL9

**Hardware-Informationen für Windows — lokal, schnell und übersichtlich**

[![Version](https://img.shields.io/badge/Version-10.0-0F6CBD?style=for-the-badge)](https://alpha10.de/tools/Alpha10-HWTOOL9.php)
[![Plattform](https://img.shields.io/badge/Windows-10%20%7C%2011-0078D6?style=for-the-badge&logo=windows&logoColor=white)](https://alpha10.de/tools/Alpha10-HWTOOL9.php)
[![Preis](https://img.shields.io/badge/Preis-kostenlos-2E7D32?style=for-the-badge)](https://alpha10.de/tools/Alpha10-HWTOOL9.php)
[![Installation](https://img.shields.io/badge/Installation-nicht%20nötig-2E7D32?style=for-the-badge)](#-download)

[![Python](https://img.shields.io/badge/Python-3.12%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![PySide6](https://img.shields.io/badge/GUI-PySide6-41CD52?style=flat-square&logo=qt&logoColor=white)](https://doc.qt.io/qtforpython/)
[![Sprachen](https://img.shields.io/badge/Sprachen-DE%20%7C%20EN-blue?style=flat-square)](#-oberfläche)
[![Datenschutz](https://img.shields.io/badge/Daten-bleiben%20lokal-success?style=flat-square&logo=shieldsdotio&logoColor=white)](#-datenschutz)

</div>

---

## 📖 Über HWTOOL9

HWTOOL9 liest die Hardware- und Systemdaten eines Windows-PCs aus und zeigt sie
in 22 Kategorien an. Es braucht keine Installation, keine Internetverbindung und
keine Administratorrechte — mit Rechten liefert es allerdings mehr.

Gedacht ist es für die PC-Diagnose, den Support-Alltag, den An- und Verkauf
gebrauchter Hardware und für alle, die wissen wollen, was eigentlich in ihrem
Rechner steckt.

> **Version 10.0 ist eine vollständige Neuentwicklung.** Die Vorgängerversionen
> waren ein PowerShell-Skript mit WPF-Oberfläche; 10.0 ist in Python mit Qt neu
> geschrieben, liest deutlich mehr aus und lädt in etwa der halben Zeit.

---

## ⬇️ Download

**[HWTOOL9 kostenlos herunterladen →](https://alpha10.de/tools/Alpha10-HWTOOL9.php)**

Eine einzelne `HWTOOL9.exe`, rund 49 MB. Herunterladen, doppelklicken, fertig.
Kein Installer, keine Laufzeitumgebung, keine Registry-Einträge.

---

## ✨ Was wird ausgelesen

<table>
<tr><td width="50%" valign="top">

**System & Rechenkern**
- Übersicht (OS, Build, Laufzeit, Aktivierung)
- CPU (Kerne, Cache je Ebene, Sockel, Befehlssätze)
- Arbeitsspeicher (Teilenummer, Takt, Rang, XMP-Erkennung)
- Grafikkarte (echter VRAM, Treiber)
- Chipsatz
- Mainboard & BIOS (inkl. PCIe-/M.2-Steckplätze)
- Gehäuse

</td><td width="50%" valign="top">

**Geräte & Peripherie**
- Speicher (SSD-Verschleiß, TBW, SMART)
- Netzwerk (IP, WLAN, Firewall, VPN)
- USB (inkl. Verlauf aller je verbundenen Geräte)
- Bluetooth (Adapter, gekoppelte Geräte, Profile)
- Monitore (native Auflösung, HDR, Farbprofil)
- Audio, Eingabegeräte, Drucker
- Akku (Gesundheit, Zyklen)

</td></tr>
<tr><td width="50%" valign="top">

**Zustand & Sicherheit**
- Sensoren (Spannungen, Temperaturen, Lüfter, Netzteil)
- Sicherheit (TPM, Secure Boot, BitLocker, Defender, VBS)

</td><td width="50%" valign="top">

**Software & Start**
- Autostart & Dienste
- Windows-Funktionen
- Updates
- Weitere Geräte

</td></tr>
</table>

### 🔍 Ein paar Werte, die andere Tools weglassen

| Wert | Warum interessant |
|---|---|
| **TBW** — insgesamt geschriebene Datenmenge | Der ehrlichste Verschleißmaßstab einer SSD. Die Herstellergarantie ist genau darauf bezogen. HWTOOL9 rechnet zusätzlich die Schreiblast pro Betriebstag aus. |
| **Konfigurierte vs. nominale RAM-Taktrate** | Zeigt, ob XMP/EXPO wirklich aktiv ist — eine der häufigsten Fragen bei selbstgebauten PCs. |
| **Maximale Bildwiederholrate** | Kommt aus dem CTA-Erweiterungsblock der Monitor-EDID. Ohne den meldet ein 165-Hz-Monitor fälschlich 60 Hz. |
| **Erweiterungssteckplätze** | Welcher PCIe- und M.2-Steckplatz belegt ist und mit welcher Anbindung — direkt aus der Firmware-Tabelle. |
| **Verzögert startende Dienste** | Getrennt ausgewiesen, denn kurz nach dem Hochfahren sind die völlig normal gestoppt und wären sonst ein Fehlalarm. |
| **Fehlgeschlagene Updates** | Mit Fehlercode und Zeitpunkt aus dem Ereignisprotokoll — die Information, die man bei „warum installiert der nichts mehr?" tatsächlich braucht. |

---

## 🎛️ Oberfläche

- **22 Kategorien**, jede wird erst beim Anklicken geladen → sofortiger Start
- **Suche** filtert alle angezeigten Werte
- **Deutsch und Englisch**, umschaltbar ohne Neuladen
- **Heller und dunkler Modus**, folgt beim Start der Windows-Einstellung
- **Export** als PDF, CSV, HTML oder JSON
- **Kopieren** der aktuellen Kategorie in die Zwischenablage
- Direktknöpfe zu Geräte-Manager, Datenträgerverwaltung, Autostart-Liste,
  Diensten, Sound-Einstellungen und Windows Update

---

## 🔐 Zwei Betriebsmodi

|  | Normalmodus | Admin-Modus |
|---|---|---|
| Voraussetzung | keine | als Administrator gestartet |
| Grundfunktion | vollständig | vollständig |
| SSD-Verschleiß (NVMe) | ✅ | ✅ |
| TPM-Details, BitLocker, SATA-SMART | Hinweis statt Wert | ✅ |
| Quellen je Wert | Primärquellen | zusätzliche Gegenprüfungen |

Rechtepflichtige Abfragen werden im Normalmodus **gar nicht erst versucht** —
`Win32_Tpm` und `Win32_EncryptableVolume` brauchen ohne Rechte jeweils rund fünf
Sekunden bis zum „Zugriff verweigert". Das allein hat die Sicherheitskategorie
von 11,1 s auf 0,3 s gebracht.

---

## ⚡ Geschwindigkeit

Alle 22 Kategorien zusammen: **rund 7 Sekunden** (Admin-Modus: 11 s). Keine
einzelne Kategorie braucht im Normalmodus länger als 1,5 Sekunden.

| Abfrage | Vorher | Jetzt | Wie |
|---|---:|---:|---|
| Treiberdaten aller Geräte | 3,36 s | **0,02 s** | Registry statt `Win32_PnPSignedDriver` |
| CPU-Auslastung | 1,09 s | **0,12 s** | `GetSystemTimes` statt `LoadPercentage` |
| Windows-Aktivierung | 1,55 s | **0,60 s** | Filter über die Anwendungs-ID |
| VPN-Verbindungen | 0,50 s | **~0 s** | RAS-Telefonbuch statt `Get-VpnConnection` |
| Ausstehende Updates | 16,1 s | **entfällt** | Die Online-Suche macht Windows Update selbst — dafür zeigt HWTOOL9 jetzt fehlgeschlagene Updates und die letzte Update-Aktivität aus dem Ereignisprotokoll (3 ms) |

Die alten Abfragen bleiben jeweils als **zweite Prüfung** erhalten, falls der
schnelle Weg auf einem System nichts liefert.

---

## 🛡️ Qualitätssicherung

Ein Werkzeug, das auf fremden Rechnern läuft, muss auch dann funktionieren, wenn
dort etwas anders oder kaputt ist. Dafür gibt es einen Belastungstest, der die
Datenquellen gezielt sabotiert und alle 22 Kategorien in beiden Sprachen
durchrechnet:

| Szenario | Ergebnis |
|---|:---:|
| Referenzlauf | ✅ |
| WMI liefert nichts (beschädigtes Repository) | ✅ |
| WMI-Provider wirft bei jeder Abfrage | ✅ |
| WMI liefert Unsinn statt Zahlen | ✅ |
| Keine SMBIOS-Tabelle (typisch in VMs) | ✅ |
| PowerShell fehlt oder ist gesperrt | ✅ |
| Keine der nativen Schnittstellen verfügbar | ✅ |
| Alles gleichzeitig kaputt | ✅ |

**352 Prüfungen, 0 harte Fehler.** Zusätzlich geprüft: Oberfläche und Export auf
einem System ganz ohne Datenquellen.

Weitere Vorkehrungen für fremde Systeme:

- **Keine Abhängigkeit von Anzeigesprachen.** WLAN-Daten kommen über die
  Native-Wifi-API statt über `netsh`, dessen Ausgabe übersetzt ist.
- **Eine fehlende Spalte kippt keine Abfrage.** Schlägt eine WQL-Abfrage fehl,
  wird sie automatisch mit `SELECT *` wiederholt.
- **Jede native Schnittstelle ist optional.** Fehlt eine DLL oder eine erst ab
  Windows 10 1709 vorhandene Funktion, kommt eine leere Liste statt einer
  Ausnahme.

---

## 🔒 Datenschutz

HWTOOL9 arbeitet vollständig lokal:

- ❌ Keine Übertragung an den Hersteller oder an Dritte
- ❌ Keine Telemetrie, kein Konto, keine Registrierung
- ❌ **Überhaupt keine Netzwerkverbindung** — HWTOOL9 fragt auch bei Microsoft
  nichts ab; für die Suche nach neuen Updates öffnest du Windows Update selbst
- ❌ Keine Installation, keine Änderungen am System

> ⚠️ **Hinweis:** Ein erstellter Bericht kann personenbezogene Daten enthalten
> (Computername, Benutzername, Seriennummern, IP- und MAC-Adressen). Prüfe ihn,
> bevor du ihn weitergibst.

---

## ⚖️ Haftungsausschluss

Die Nutzung erfolgt **auf eigene Gefahr**. Es wird keine Gewähr für die
Vollständigkeit oder Richtigkeit der angezeigten Daten übernommen.

Die Werte stammen aus dem, was Windows und die Firmware des Geräts melden —
diese Angaben sind je nach Hersteller unvollständig oder schlicht falsch. Als
„geschätzt" gekennzeichnete Werte sind ausdrücklich Näherungen. Eine Haftung für
Schäden aus Nutzung oder Nichtnutzung ist ausgeschlossen, soweit gesetzlich
zulässig.

---

## 🧰 Für Entwickler

<details>
<summary><b>Selbst bauen</b></summary>

```bash
python -m pip install PySide6 pywin32 pyinstaller
python make_icon.py
pyinstaller hwtool9.spec --noconfirm
```

Ergebnis: `dist/HWTOOL9.exe` — eine Datei, ohne Konsolenfenster, mit Symbol und
Versionsinformationen.

Direkt aus dem Quelltext starten:

```bash
python run_hwtool9.py
```

Kategorien auf der Konsole ausgeben (ohne Oberfläche):

```bash
python dump.py CPU Speicher --lang EN
```

Belastungstest ausführen:

```bash
python robustness_test.py
```

</details>

<details>
<summary><b>Aufbau</b></summary>

```
hwtool9/
  context.py        Betriebsmodus, Caches, Quellenketten
  wmi.py            WMI über COM, Namespace-Cache, SELECT-*-Rückfallebene
  psbridge.py       ein dauerhaft laufender PowerShell-Prozess
  model.py          Builder / Gruppen / Zeilen
  i18n.py           DE/EN, aufgelöst erst bei der Anzeige
  export.py         HTML, PDF (über Qt), CSV, JSON
  native/           SMBIOS, EDID, NVMe, Bluetooth, WLAN, DisplayConfig …
  collectors/       die 22 Kategorien
  gui/              PySide6-Oberfläche
```

Datenquellen in der Reihenfolge ihrer Verwendung: SMBIOS-Rohtabelle →
Registry → Win32-APIs → WMI/CIM → PowerShell-Cmdlets. Werte werden
sprachneutral abgelegt und erst beim Zeichnen übersetzt — dadurch ist der
Sprachwechsel verzögerungsfrei.

</details>

---

<div align="center">

**© 2026 Bjoern Scherf · [alpha10.de](https://alpha10.de) · [GitHub](https://github.com/A10Computer/)**

Kostenlos nutzbar · Benutzung auf eigene Gefahr

</div>
