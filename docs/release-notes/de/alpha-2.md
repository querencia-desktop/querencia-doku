# Querencia Desktop – Alpha 2

**Stand:** 21.10.2026, 22:10, Entwurf zum eingefrorenen Paketsatz · **Status:**
interne Alpha, nicht veröffentlicht · Werte mit „offen“ sind noch nicht belegt oder nicht
entschieden.

Alpha 2 bringt den Stand der Entwicklungsumgebung vom 21. Oktober 2026 in
die Paketquelle: eine **dunkle Darstellung** für den ganzen Desktop, besser
lesbare Farben in der hellen Darstellung, **16 neue Hintergründe**, **Reiter
im Terminal** und eine Dateiverwaltung, die keine Update-Server mehr
anfragt. Es sind 21 Debian-Pakete für Ubuntu 26.04 („resolute“) aus derselben signierten
APT-Quelle.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren.

## Neu in Alpha 2

- **Dunkle Darstellung.** In den Systemeinstellungen unter Erscheinungsbild
  „Dunkle Darstellung bevorzugen“ einschalten: Das Thema
  Querencia-Klassisch 0.2.1 hat jetzt eine dunkle Fassung, und Panel,
  Arbeitsfläche und die Querencia-Programme folgen ihr – bis auf Querencia
  Files, das vorerst sein eigenes helles Thema behält. Ausschalten stellt
  die helle Darstellung wieder her. Laufende Programme wechseln sofort,
  das Panel ebenfalls; die Fensterrahmen von labwc bleiben hell.
- **16 neue Hintergründe** im neuen Datenpaket `querencia-hintergruende`:
  zwölf Motive (Tiefblau, Blaugrün, Blauschein, Glut, Hügel, Küste, Dünen,
  See, Wüste, Berge, Strand, Glas) und vier Fassungen mit dem
  Querencia-Logo, je in 2560×1440 und als eigener 4:3-Ausschnitt.
  **Standardbild ist Tiefblau.** Die Bilder sind mit FLUX1.1 [pro] Ultra
  (Black Forest Labs) über fal.ai erzeugt und vom Projektbesitzer
  ausgewählt; das Logo ist nachträglich per Skript aufgeprägt, nie von der
  KI gemalt. Die Systemeinstellungen 0.1.4 zeigen sie als Galerie, die
  Symbolbeschriftungen der Arbeitsfläche (Desktop 0.2.1) haben eine
  Hinterlegung und bleiben auf jedem Bild lesbar.
- **Kontrast in der hellen Darstellung** nach WCAG AA nachgezogen:
  Tastenkürzel in Menüs, Speichermarke im Rechner, Leerhinweis im
  Bildbetrachter, Text der Benachrichtigungen, Diagrammfarben der
  Systemüberwachung, Kürzel und Auswahl in den Systemeinstellungen.
- **Reiter im Terminal** (Querencia Terminal 0.3.0) wie im GNOME Terminal
  2.x: Strg+Umschalt+T öffnet einen Reiter, Strg+Umschalt+W schließt ihn,
  Strg+Bild auf/ab wechselt, Alt+1 bis Alt+9 springt direkt. Die
  Reiterleiste erscheint ab dem zweiten Reiter. Die Tastenkürzel-Übersicht
  (Super+?) nennt die neuen Kürzel.
- **Files ohne Update-Abfrage.** Querencia Files fragt nicht mehr bei
  GitHub oder im AUR nach neuen Versionen und zeigt keinen Update-Hinweis;
  Updates kommen nur über apt. „Hier entpacken“ läuft über Querencia
  Archiv, der Info-Dialog zeigt das Querencia-Symbol.
- **Symbole 0.7:** eigenes Symbol für den Knopf „Arbeitsfläche anzeigen“
  und Programmsymbole für Archiv, Software, Dateisuche, Rechner und die
  Tastenkürzel-Übersicht im Symbolthema.
- **Nebenfenster mit Titelleiste:** Bildinformationen, Suchen und Ersetzen
  im Editor und die Dialoge im PDF-Betrachter erscheinen auch beim zweiten
  Öffnen mit Titelleiste; ebenso das Auswahlfenster des Bildschirmfotos
  nach einem Abbruch mit Esc.
- **Systemeinstellungen 0.1.3:** Zurückstellen lässt keine Standardwerte in
  der labwc-Konfiguration stehen, Sicherungsdateien sind begrenzt.

## Versionen

Paketsatz vom 21.10.2026 (21 Pakete), gebaut aus dem Stand, der am selben
Tag um 18:52 in der Entwicklungsumgebung aktiv war.

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha2-7 | Metapaket: zieht alle Bestandteile nach |
| labwc | 0.9.8-0querencia5 | Backport des Fensterverwalters (unverändert, neue Revision) |
| querencia-session | 0.1.0~alpha7-2 | Sitzungsstarter (unverändert, neue Revision) |
| querencia-shell | 0.1.0~alpha7-1 | Panel 0.2.1, Arbeitsfläche 0.2.2, Tastenkürzel-Übersicht 0.2.0, Thema Querencia-Klassisch 0.2.1 hell und dunkel, die 17 Hintergründe aus Alpha 1 |
| querencia-hintergruende | 0.2-1 | 16 Hintergründe (Standard Tiefblau), neu |
| querencia-sitzung | 0.1.3-3 | Sitzung 0.1.3 (unverändert, neue Revision) |
| querencia-benachrichtigungen | 0.2.2-1 | Benachrichtigungen 0.2.2 |
| querencia-einstellungen | 0.1.4-1 | Systemeinstellungen 0.1.4 mit Hintergrund-Galerie |
| querencia-symbole | 0.7-1 | Programmsymbole und Symbolthema „Querencia“ |
| querencia-files | 0.1.0~alpha6-1 | Querencia Files, Stand QF-0r-1 |
| querencia-terminal | 0.3.0-1 | Querencia Terminal 0.3.0 mit Reitern |
| querencia-editor | 0.2.3-1 | Texteditor 0.2.3 |
| querencia-bilder | 0.2.5-1 | Bildbetrachter 0.2.5 |
| querencia-dokumente | 0.1.3-1 | PDF-Betrachter 0.1.3 (keine weißen Seiten nach Neuschreiben des PDFs) |
| querencia-archiv | 0.1.1-1 | Archivverwaltung 0.1.1 |
| querencia-rechner | 0.1.5-1 | Taschenrechner 0.1.5 |
| querencia-systemmonitor | 0.1.4-1 | Systemüberwachung 0.1.4 |
| querencia-dateisuche | 0.1.4-1 | Nach Dateien suchen 0.1.4 |
| querencia-screenshot | 0.2.9-1 | Bildschirmfoto 0.2.9 |
| querencia-software | 0.1.4-1 | Programme installieren über PackageKit, 0.1.4 |
| querencia-anmeldung | 0.1.1-3 | Anmeldebildschirm, optional (unverändert, neue Revision) |

Prüfsumme der Paketliste (SHA256SUMS): `5cbe6f81fbb58017b50bf340c1bd2c65120b27718e2b7a929986d5de3c3c183d`.

## Aktualisieren von Alpha 1

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

Danach abmelden und neu anmelden, damit Panel und Arbeitsfläche die neue
Fassung starten.

## Neu installieren

Unverändert gegenüber Alpha 1: Quelle einbinden, `sudo apt install
querencia-desktop`, neu starten, am Zahnrad „Querencia Desktop“ wählen
(siehe [Alpha 1, Installation](alpha-1.md#installation), auch für Server,
GNOME und Entfernen). Fingerabdruck des Signierschlüssels: `63F6 C499 246E
3699 CA04 726D 342F 12D2 0CE7 1CBD`.

## Bekannte Grenzen

Weiter gültig aus Alpha 1: Anmeldebildschirm englisch, Alt+Druck in VMs,
Netzwerk-Applet nur mit NetworkManager, Firefox als Snap ohne GTK-Thema,
geteilte gsettings-Werte neben GNOME, greetd bleibt nach dem Entfernen von
`querencia-anmeldung`. Neu bzw. geändert:

- **Fensterrahmen und Files bleiben hell:** labwc zeichnet die Rahmen mit
  dem eigenen Thema, Querencia Files hat ein eigenes Thema; dunkle
  Fassungen dafür sind Folgepunkte.
- **Fremde GTK-3-Programme folgen dem Dunkelmodus nicht:** GTK 3 wertet
  die Einstellung „Dunkle Darstellung bevorzugen“ nicht aus; alle
  Querencia-Programme sind GTK 4 und folgen ihr.
- Nach einem Wechsel hell/dunkel im laufenden Programm kann der
  Tastaturfokus an einer anderen Stelle stehen als beim Start.
- **Panel und Arbeitsfläche** übernehmen ein geändertes Thema erst nach
  einer Neuanmeldung; das Umschalten hell/dunkel wirkt sofort.
- **Files:** Die Seite „Updates“ in den Einstellungen nennt nur noch die
  Paketquelle; einige übersetzte Texte verweisen noch auf Strata.
- Behoben gegenüber Alpha 1: Terminal ohne Reiter, keine dunkle
  Darstellung, Nebenfenster ohne Titelleiste, Strata-Logo im Info-Dialog,
  Standardwerte in `rc.xml` nach dem Zurückstellen.

## Fehler melden

Im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>,
Deutsch oder Englisch. Bitte angeben:

- Ausgabe von `dpkg -l 'querencia-*' labwc` und `lsb_release -ds`
- was Sie getan haben, was Sie erwartet haben, was passiert ist
- etwa 50 Zeilen aus dem passenden Protokoll in `~/.local/state/querencia/`
  (Sitzungsstart: `sitzung-start.log`)

Heimpfade, Rechnernamen und IP-Adressen im Protokoll bitte vorher
schwärzen. Sicherheitslücken nicht öffentlich melden, sondern über
<https://github.com/querencia-desktop/querencia/security/advisories/new>.

## Geprüft

- Jede Quelle ist ein getaggter Stand; für jedes Programm ist belegt, dass
  das in der Entwicklungsumgebung laufende Programm aus genau diesem Stand
  gebaut wurde (Panel und Tastenkürzel-Übersicht byte-gleich nachgebaut).
- Statische Paketprüfung 242 bestanden, Lintian ohne Fehler, signierte
  Testquelle, Probe-Installation in einer abgeschotteten Kopie des Systems
  87 bestanden (darunter die dunkle Fassung für GTK 4 und GTK 3).
- **Pflichtprobe auf frischem Ubuntu 26.04**, bestanden am 21.10.2026:
  - Anmeldung an der **Textkonsole (tty1)** und über **GDM** auf Ubuntu
    Desktop: Installation, Sitzung, Prüfskript in der Sitzung (28/28),
    Neuanmeldung nach dem Abmelden in etwa 6 s;
  - dunkle Darstellung ein- und ausgeschaltet (Panel und Programme wechseln
    sofort), Terminal mit drei Reitern, Files ohne Update-Hinweis und ohne
    Netzverbindung, Benachrichtigung, Tastenkürzel-Übersicht,
    PDF-Betrachter nach Neuschreiben der Datei;
  - Messwerte: Einstellungs-Portal antwortet in 7–12 ms, Panel und
    Arbeitsfläche 1,1–1,3 s nach dem Fensterverwalter.
  - Nicht geprüft: Anmeldung über querencia-anmeldung (unverändert seit
    Alpha 1), echte Hardware, SMB-Freigaben, Kopieren und Einfügen im
    Terminal.

## Lizenzen und Herkunft

Wie Alpha 1. Neu:

- **Hintergründe 0.2:** CC-BY-SA-4.0 mit KI-Vorbehalt (rein KI-erzeugte
  Bilder sind in manchen Rechtsordnungen womöglich nicht
  urheberrechtlich geschützt; die Lizenzangabe ist dann ein Hinweis). Bei
  den vier Logo-Fassungen ist nur das Grundbild frei; Name und Logo
  „Querencia“ unterliegen der Markenregel. Herkunft je Bild steht in
  `/usr/share/doc/querencia-hintergruende/herkunft.md`.
- Die fünf Programmsymbole im Symbolthema (Archiv, Software, Dateisuche,
  Rechner, Tastenkürzel-Übersicht) stehen wie ihre Programme unter
  GPL-3.0-or-later; das übrige Symbolthema unter CC-BY-SA-4.0.

Name und Logo „Querencia“ sind keine freien Inhalte.

Copyright 2026 Querencia Desktop contributors.

