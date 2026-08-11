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

## 📖 Über HWTOOL9 64bit

HWTOOL9 liest die Hardware- und Systemdaten eines 64bit Windows-PCs aus und zeigt sie
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

##  Was wird ausgelesen

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

##  Zwei Betriebsmodi

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

##  Datenschutz

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

##  Haftungsausschluss

Die Nutzung erfolgt **auf eigene Gefahr**. Es wird keine Gewähr für die
Vollständigkeit oder Richtigkeit der angezeigten Daten übernommen.

Die Werte stammen aus dem, was Windows und die Firmware des Geräts melden —
diese Angaben sind je nach Hersteller unvollständig oder schlicht falsch. Als
„geschätzt" gekennzeichnete Werte sind ausdrücklich Näherungen. Eine Haftung für
Schäden aus Nutzung oder Nichtnutzung ist ausgeschlossen, soweit gesetzlich
zulässig.

---

<div align="center">

Kostenlos nutzbar · Benutzung auf eigene Gefahr

</div>
