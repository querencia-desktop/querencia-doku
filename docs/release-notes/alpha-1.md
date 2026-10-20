# Querencia Desktop – Alpha 1 (Entwurf)

**Stand des Entwurfs:** 20.10.2026 · **Status:** intern, nicht veröffentlicht
· Werte mit „offen“ sind noch nicht belegt oder nicht entschieden.

Querencia Desktop ist eine klassische Desktopumgebung im Stil von GNOME 2
(Ubuntu 10.04) für Wayland: Fensterverwalter labwc 0.9.8, zwei Panels, eine
Arbeitsfläche mit Symbolen und eigene Programme in Rust und GTK 4 ohne
libadwaita. Die Oberfläche ist deutsch, die meisten Programme gibt es auch auf
Englisch. Alpha 1 ist die erste interne Testfassung für Ubuntu 26.04.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie.

## Was drin ist

### Stand der Entwicklungsumgebung (20.10.2026)

Gemessen auf der Entwicklungs-VM; Quelle: Aktivierungsjournal und
Live-Stand des Projekts.

| Bestandteil | Fassung | Was es ist |
|---|---|---|
| labwc | 0.9.8 (eigener Bau) | Fensterverwalter (Wayland-Compositor) |
| Panel | Stand G2-AI (Tag `panel/g2ai-portal`) | zwei Panels, Menüs Anwendungen/Orte/System, Fensterliste, Arbeitsflächenumschalter, Uhr mit Kalender, Lautstärke, Netzwerk, Abmelden/Ausschalten |
| Arbeitsfläche | Stand G2-AI (Tag `desktop/g2ai-portal`) | Hintergrund, Symbole, Datenträger, Kontextmenü |
| Sitzungsstarter | 2.1 | Start und sauberes Beenden der Sitzung |
| Querencia Files | QF-0o-3 | Dateiverwaltung (Fork von Strata) |
| Querencia Terminal | 0.2.0 | Terminal |
| Querencia Editor | 0.2.1 | Texteditor |
| Querencia Bilder | 0.2.1 | Bildbetrachter |
| Querencia Dokumente | 0.1.0 | PDF-Betrachter |
| Querencia Archiv | 0.1.0 | Archivverwaltung |
| Querencia Rechner | 0.1.3 | Taschenrechner |
| Querencia Systemmonitor | 0.1.2 | Systemüberwachung |
| Querencia Dateisuche | 0.1.3 | Nach Dateien suchen |
| Querencia Screenshot | 0.2.8 | Bildschirmfoto mit Editor und Fensterwahl |
| Querencia Einstellungen | 0.0.9 | Systemeinstellungen (zwölf Bereiche) |
| Querencia Software | 0.1.2 | Programme installieren über PackageKit |
| Querencia Benachrichtigungen | 0.1.3 | Benachrichtigungsdienst |
| Querencia Sitzung | 0.1.3 | Sperrbildschirm, Sitzungsdialog, polkit-Agent |
| Tastenkürzel-Übersicht | 0.1.0 | Super+? |
| Thema Querencia-Klassisch | GTK-Thema 0.1 | GTK 4, GTK 3 und Fensterrahmen |
| Symbole | 0.5.2 | Programmsymbole und Symbolthema „Querencia“ |
| Schrift und Zeiger | Erscheinungsbild 0.1 | DejaVu Sans 10, Zeiger DMZ-White |
| Hintergründe | 17 Bilder | Querencia Blau und vier Motive je mit und ohne Logo |

Geprüft und freigegeben, aber noch nicht eingespielt: Symbole 0.6 (eigenes
Symbol für Dokumente), Bilder 0.2.2 (Menü „Grafik“). Freigabe beantragt:
Software 0.1.3 (erklärt Netzwerkprobleme von PackageKit).

### Paketsatz

Der aktuelle Paketsatz (G2-F2) umfasst 18 Debian-Pakete:

| Paket | Fassung |
|---|---|
| querencia-desktop (Metapaket) | 0.1.0~alpha2-2 |
| querencia-shell (Panel, Arbeitsfläche) | 0.1.0~alpha3-1 |
| querencia-session | 0.1.0~alpha3-1 |
| querencia-files | 0.1.0~alpha3-1 |
| querencia-terminal | 0.2.0-1 |
| querencia-editor | 0.2.1-1 |
| querencia-bilder | 0.2.1-1 |
| querencia-dokumente | 0.1.0-1 |
| querencia-rechner | 0.1.3-1 |
| querencia-systemmonitor | 0.1.2-1 |
| querencia-dateisuche | 0.1.3-1 |
| querencia-screenshot | 0.2.8-1 |
| querencia-einstellungen | 0.0.8-1 |
| querencia-software | 0.1.2-1 |
| querencia-benachrichtigungen | 0.1.2-1 |
| querencia-sitzung | 0.1.2-1 |
| querencia-symbole | 0.5.2-1 |
| labwc (Backport) | 0.9.8-0querencia3 |

Der Paketsatz bildet den Stand der Entwicklungsumgebung vom 20.10.2026,
13:00 ab: Einstellungen, Benachrichtigungen und Sitzung sind darin eine
Fassung älter; die Archivverwaltung und die Sitzungsänderungen vom
Nachmittag (sauberes Abmelden, Sitzungsstarter 2.1) fehlen noch. Ein neuer Paketsatz (G2-F3) ist in
Arbeit. **Endgültiger Paketsatz für Alpha 1: offen.**

### Prüfung

- **Pflichtprobe** auf einer frischen Ubuntu-26.04-VM (Paketsatz vom
  20.10.2026, 03:45): bestanden am 20.10.2026 – Installation, Sitzung, 13
  Programme, Entfernen und Rückfall; 17 Prüfpunkte PASS, 6 PASS mit Befund,
  kein Programmfehler. Die Befunde sind in Arbeit oder erledigt. Wiederholung
  mit dem neuen Paketsatz: offen.
- Jedes Programm ist mit Unit-Tests und in abgeschotteten GUI-Läufen (eigener
  Compositor, eigenes Profil, Deutsch und Englisch, 1024×768 und 1920×1080)
  geprüft. Ein Gesamt-Prüflauf aller seit dem 19.10. eingespielten Stände
  (QREL-06) läuft; **Ergebnis: offen.**

## Installation

Voraussetzung: Ubuntu 26.04 (Desktop- oder Server-Abbild), Benutzer mit
sudo-Rechten, Netzzugang zum Ubuntu-Archiv. Erst auf einer Test-VM mit
Snapshot ausprobieren.

1. Paketordner auf den Rechner kopieren und prüfen:

   ```bash
   cd ~/querencia-debs && sha256sum -c SHA256SUMS
   ```

2. Installieren (apt holt die Abhängigkeiten aus dem Ubuntu-Archiv; der
   labwc-Backport 0.9.8 ist dabei, weil Ubuntu nur 0.9.3 liefert):

   ```bash
   cd ~/querencia-debs && sudo apt install ./*.deb
   ```

3. **Server-Abbild:** Damit Querencia Software installieren kann, in
   `/etc/netplan/*.yaml` unter `network:` die Zeile
   `renderer: NetworkManager` ergänzen und `sudo netplan apply` ausführen.

4. Anmelden:
   - **Desktop-Abbild:** neu starten, im Anmeldebildschirm am Zahnrad
     „Querencia Desktop“ wählen.
   - **Server-Abbild:** an tty1 anmelden und `querencia-session` eingeben.

5. Entfernen:

   ```bash
   sudo apt remove 'querencia-*'
   ```

   Benutzerdaten in `~/.config/querencia` und `~/.local/state/querencia`
   bleiben. Zurück auf Ubuntus labwc:

   ```bash
   sudo apt install --allow-downgrades labwc/resolute
   ```

Eine signierte APT-Quelle gibt es noch nicht; **Bezugsweg der Pakete für
Tester: offen.**

## Was fehlt

- Eigener Anmeldebildschirm als Paket (in Arbeit) und geprüfte Installation
  neben einem vorhandenen Ubuntu-Desktop (in Arbeit).
- Mitteilungszentrale und Panel-Symbol für Benachrichtigungen (in Arbeit).
- Einstellungsbereiche „Sprache und Region“, Energie, Startprogramme; mehrere
  Tastaturbelegungen mit Umschalttaste; schreibender Bereich „Panels“.
- Englisch für Panel, Arbeitsfläche, Einstellungen und Sperrbildschirm.
- Menüleiste, Reiter und Profile im Terminal.
- Signierte APT-Quelle, Veröffentlichung auf GitHub (Veröffentlichungsklone
  vorbereitet), Webseite.
- Boot-Splash (zurückgestellt), zweite Distribution (geplant).

## Bekannte Fehler

Die vollständige Liste steht im Benutzerhandbuch unter
[Bekannte Einschränkungen](../benutzerhandbuch/de/bekannte-einschraenkungen.md).
Die wichtigsten:

- Die Fensterliste zeigt Fenster aller Arbeitsflächen.
- Im installierten Paket ruft das Panel beim Abmelden noch den alten
  Zwei-Knopf-Dialog auf.
- Auf dem GDM-Weg fehlen die Querencia-Vorgaben für Schrift, Symbole und
  Zeiger.
- Auf Server-Systemen meldet Software ohne NetworkManager „offline“.
- Files zeigt im Info-Dialog noch das Strata-Logo; Rechner können in der
  Netzwerkansicht doppelt erscheinen.
- Panel und Arbeitsfläche sind einmal ohne erkennbare Ursache beendet worden.

## Lizenzen

- Programme: GPL-3.0-or-later.
- Querencia Files: MIT wie der Ursprung Strata; die PDF-Vorschau linkt gegen
  Poppler (GPL).
- Bibliotheken von Querencia Software: MIT oder Apache-2.0.
- Dokumentation, Symbole und Symbolthema: CC-BY-SA-4.0.
- Hintergründe: **Lizenz offen** (KI-erzeugte Motive; Prüfung der
  Nutzungsbedingungen vor der Veröffentlichung).
- Name und Logo „Querencia“ sind keine freien Inhalte (Markenregel).

Copyright 2026 Querencia Desktop contributors.

