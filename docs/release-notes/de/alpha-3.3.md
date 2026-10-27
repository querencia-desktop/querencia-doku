# Querencia Desktop – Alpha 3.3

**Stand:** 27.10.2026 · **Status:** in der APT-Quelle seit [Datum], [Uhrzeit]

Alpha 3.3 spricht fünf Sprachen: Deutsch, Englisch, Italienisch, Spanisch
und Französisch. Neu sind außerdem ein Infobereich im Panel für die Symbole
anderer Programme, zwei Korrekturen in Querencia Dateien und ein
Anmeldebildschirm, der jetzt auch die Namen der Sitzungen übersetzt. Es sind 24
Debian-Pakete für Ubuntu 26.04 („resolute“) aus derselben signierten
APT-Quelle; 18 davon sind neu gebaut oder neu in der Fassung.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren. Querencia Dateien selbst trägt die Stufe „Beta“.

## Neu in Alpha 3.3

- **Fünf Sprachen.** Alle Querencia-Programme, das Panel und die
  Arbeitsfläche gibt es jetzt auch auf Italienisch, Spanisch und
  Französisch: Menüs, Dialoge, Meldungen, die Starter im Anwendungsmenü und
  die Beschreibungen im Software-Center. Welche Sprache gilt, bestimmt die
  Systemsprache (Einstellungen → „Sprache und Region“, wirksam ab der
  nächsten Anmeldung). Noch fest deutsch sind der Sperrbildschirm, das
  Fenster des Lautstärkereglers und die Tastenkürzel-Hilfe (siehe
  [Bekannte Grenzen](#bekannte-grenzen)).
- **Neu empfohlen: `locales-all`.** Das Metapaket empfiehlt jetzt
  `locales-all`. Damit sind Italienisch, Spanisch und Französisch in
  „Sprache und Region“ wählbar; die Seite bietet nur Sprachen an, für die
  eine Locale installiert ist. Das Upgrade installiert das Paket mit; es
  belegt rund 230 MB. Texte von GTK selbst (etwa im Dateidialog) kommen aus
  dem Sprachpaket des Systems, `language-pack-gnome-<xx>`; das Metapaket
  zieht es bewusst nicht nach. Wer Querencia auf ein vorhandenes Ubuntu
  installiert, holt es für seine Sprache selbst, zum Beispiel für
  Italienisch:

  ```bash
  sudo apt install language-pack-gnome-it
  ```
- **Infobereich im Panel (Panel 0.4.0).** Programme, die ein Statussymbol
  anbieten (StatusNotifierItem, auch über libappindicator, etwa Webex,
  Nextcloud oder Discord), zeigen es jetzt oben rechts vor der Glocke:
  - Zeiger auf das Symbol zeigt den Tooltip des Programms.
  - Linksklick öffnet das Programm bzw. holt sein Fenster nach vorn; manche
    Programme zeigen stattdessen ihr Menü.
  - Rechtsklick öffnet das Menü des Programms im Querencia-Stil, mit
    Häkchen und Auswahlpunkten.
  - Mittlere Taste und Mausrad gehen an das Programm.
  - Will ein Programm Aufmerksamkeit (z. B. eine neue Nachricht), wird sein
    Knopf orange hinterlegt.

  Ohne Symbol ist der Infobereich unsichtbar. Im Standard-Panel steht er
  von selbst. **Wer das Panel schon angepasst hat,** fügt ihn über
  Rechtsklick aufs Panel → „Zum Panel hinzufügen …“ → „Infobereich“ hinzu;
  das Panel ändert eine gespeicherte Anordnung nicht von selbst. Entfernen
  und Verschieben gehen über einen Rechtsklick auf den schmalen Rand links
  neben den Symbolen.
- **Querencia Dateien 0.2.4:** Die Kompaktansicht kürzt Namen nicht mehr
  nach der Zoomstufe; die Spalten sind so breit wie der längste Name (bis
  42 Zeichen), längere Namen stehen ganz im Tooltip. Nach dem Schließen der
  Suche zeigt die Statusleiste wieder den Ordner; während der Suche zeigt
  sie die Zahl der Treffer und eine Auswahl in den Treffern. Beides stand
  bisher unter den bekannten Grenzen.
- **Anmeldebildschirm** (`querencia-anmeldung` 0.1.3, wahlweise): Er
  folgt der Systemsprache, Deutsch oder Englisch, bei Knöpfen und Uhr und
  jetzt auch bei den Namen der Sitzungen. Bei anderen Systemsprachen zeigt
  er Englisch.
- **Software:** Thunderbird und Firefox stehen mit Beschreibung im
  Software-Center; installieren lassen sie sich, sobald ihre Paketquelle
  eingerichtet ist, sonst zeigen sie „Nicht verfügbar“. Snap-Hüllen werden
  nicht mehr angeboten.
- **Schnatter 0.3.1** (wahlweise) gibt es ebenfalls auf Italienisch,
  Spanisch und Französisch; sonst unverändert.

Was Alpha 3.2 brachte (Kontextmenüs in Dateien, Schnatter statt
Webhülle), steht in den [Hinweisen zu Alpha 3.2](alpha-3.2.md).

## Versionen

Paketsatz vom 27.10.2026 (24 Pakete).

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.3-1 | Metapaket, Versionsdatei „Alpha 3.3“, **neu:** empfiehlt `locales-all` |
| querencia-shell | 0.1.0~alpha11-1 | **geändert:** Panel 0.4.0 (Infobereich), Arbeitsfläche 0.3.1; Tastenkürzel-Übersicht 0.2.2 und Thema 0.2.2 unverändert |
| querencia-dateien | 0.2.4-1 | **geändert:** Kompaktansicht, Statusleiste nach der Suche |
| querencia-anmeldung | 0.1.3-1 | **geändert:** Anmeldebildschirm, Sitzungsnamen jetzt übersetzt, optional |
| querencia-software | 0.1.7-1 | **geändert:** Thunderbird und Firefox mit Beschreibung |
| querencia-editor | 0.2.5-1 | Texteditor |
| querencia-terminal | 0.3.3-1 | Terminal |
| querencia-sitzung | 0.1.9-1 | Sitzungsdialog, Sperre, Passwortdialog |
| querencia-einstellungen | 0.1.7-1 | Systemeinstellungen |
| querencia-rechner | 0.1.7-1 | Taschenrechner |
| querencia-bilder | 0.2.7-1 | Bildbetrachter |
| querencia-dokumente | 0.1.5-1 | PDF-Betrachter |
| querencia-archiv | 0.1.3-1 | Archivverwaltung |
| querencia-systemmonitor | 0.1.6-1 | Systemüberwachung |
| querencia-dateisuche | 0.1.6-1 | Nach Dateien suchen |
| querencia-screenshot | 0.2.11-1 | Bildschirmfoto |
| querencia-benachrichtigungen | 0.2.3-1 | Benachrichtigungen |
| querencia-schnatter | 0.3.1-1 | Schnatter, WhatsApp Web im eigenen Fenster, wahlweise |
| querencia-webhuelle | 0.3.0-1 | Übergangspaket zu Schnatter (unverändert seit Alpha 3.2) |
| querencia-files | 0.2.0-1 | Übergangspaket aus Alpha 3 (unverändert) |
| querencia-session | 0.1.0~alpha10-1 | Sitzungsstarter (unverändert seit Alpha 3) |
| querencia-symbole | 0.8-1 | Programmsymbole und Symbolthema (unverändert seit Alpha 3) |
| querencia-hintergruende | 0.2-1 | 16 Hintergründe (unverändert seit Alpha 2) |
| labwc | 0.9.8-0querencia5 | Backport des Fensterverwalters (unverändert seit Alpha 2) |

Von Editor bis Schnatter ist die Neuerung jeweils die Übersetzung ins
Italienische, Spanische und Französische.

Prüfsumme der Paketliste (SHA256SUMS): `ad018bf1e7808970d9a98a1a9aaa3b57d2b0b3febf6601e80fc632b09b2f1060`.

## Aktualisieren von Alpha 3.2 oder 3.1

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` genügt ebenfalls. APT aktualisiert alle Pakete mit neuer
Fassung (16 bis 18, je nachdem, ob Schnatter und der Anmeldebildschirm
installiert sind) und installiert `locales-all` neu. Dafür lädt es rund
[Download-Größe] herunter; danach belegt `locales-all` rund 230 MB.
Entfernt wird nichts, und es gibt keine Rückfrage zu Konfigurationsdateien.
In einer virtuellen Maschine dauerte das Upgrade [Upgrade-Dauer]. Danach
abmelden und neu anmelden.

Wer das Panel nie angepasst hat, sieht den Infobereich dann von selbst.
Wer es angepasst hat, fügt ihn hinzu wie [oben](#neu-in-alpha-33)
beschrieben.

Ein Upgrade von Alpha 3 geht genauso; was dabei mit Schnatter und der
Webhülle geschieht, steht in den [Hinweisen zu Alpha 3.2](alpha-3.2.md#aktualisieren-von-alpha-3-oder-31).
Von Alpha 2.1 oder 2.2 siehe [Alpha 3](alpha-3.md#aktualisieren-von-alpha-21).

## Neu installieren

Unverändert: Quelle einbinden, `sudo apt install querencia-desktop`, neu
starten, am Zahnrad „Querencia Desktop“ wählen (siehe
[Alpha 1, Installation](alpha-1.md#installation)). Fingerabdruck des
Signierschlüssels: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
`locales-all` kommt dabei mit, Schnatter nicht. Auf einem frischen
Ubuntu-26.04-Server-Abbild installiert APT [Paketzahl] Pakete.

## Bekannte Grenzen

Weiter gültig aus Alpha 3 bis 3.2 (siehe dort), soweit oben nicht als
behoben genannt. Davon besonders:

- **Noch fest deutsch:** der Sperrbildschirm, das Fenster des
  Lautstärkereglers und die Tastenkürzel-Hilfe (auch ihr Starter). Im
  Italienischen bleibt der Tastenname „Return“ in Menükürzeln englisch
  (z. B. „Alt+Return“ im Bildbetrachter).
- **Texte von GTK selbst** (Dateidialog, einige Knöpfe) folgen dem
  Sprachpaket des Systems. Ohne `language-pack-gnome-<xx>` der gewählten
  Sprache bleiben sie englisch.
- **Der Anmeldebildschirm kennt nur Deutsch und Englisch.** Bei
  Italienisch, Spanisch oder Französisch als Systemsprache zeigt er
  Englisch.
- **Meldung bei abgelaufenem Passwort noch englisch und technisch:** Der
  Anmeldebildschirm zeigt dann `Pam_acct_mgmt: NEW_AUTHTOK_REQD` statt
  einer deutschen Aufforderung.
- **Infobereich:**
  - Kein Infobereich für alte X11-Programme, die ihr Symbol über das ältere
    Verfahren (XEmbed) anbieten; sie zeigen weiter keines.
  - Symbole, die das Programm selbst als „passiv“ meldet, bleiben
    verborgen; einen Knopf zum Aufklappen gibt es nicht. Viele Programme
    haben eine eigene Einstellung, das Symbol immer zu zeigen.
  - Ein Programm, das schon vor dem Panel lief, meldet sich nicht immer an;
    dann das Programm neu starten.
  - Ein offenes Menü zeigt Änderungen erst beim nächsten Öffnen;
    bewegte Symbole werden nicht abgespielt.
  - Mit Webex, Nextcloud oder Discord selbst ist der Infobereich noch nicht
    geprüft, sondern mit Testprogrammen und mit der verbreiteten Bibliothek
    libayatana-appindicator (siehe [Geprüft](#geprüft)).
- **Schnatter** zeigt noch kein Symbol im Infobereich; es meldet neue
  Nachrichten nur, solange sein Fenster offen ist.
- **Querencia Dateien ist eine Beta.** Rückgängig (Strg+Z) gibt es noch
  nicht; eine Spaltenansicht und einen Ordnerbaum in der Seitenleiste gibt
  es nicht. Die Suche findet nur Namen, keinen Dateiinhalt; aus den
  Suchergebnissen lässt sich noch nicht kopieren oder ziehen.
- **Netzwerk teils ungeprüft:** Eine gelungene Verbindung zu einer
  Windows-Freigabe, Zertifikatsfragen bei sicheren Verbindungen und echte
  Netzlaufwerke sind ungeprüft.
- **`locales-all` ist groß:** Es belegt rund 230 MB, auch wenn man nur
  eine Sprache braucht.
- **Software-OpenGL** kostet Rechenzeit und Speicher; Programme, die der
  Fensterverwalter selbst startet (z. B. über Tastenkürzel), bekommen es
  nicht.
- **Nicht auf echter Hardware geprüft**, nur in virtuellen Maschinen und in
  abgeschotteten Kopien des Systems.

## Fehler melden

Wie Alpha 3, im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Geprüft

- Jede Quelle ist ein getaggter Stand, etwa das Panel aus `panel/0.4.0-2`,
  Querencia Dateien aus `dateien/0.2.4`, der Anmeldebildschirm aus
  `anmeldung/0.1.3`.
- **Sprachen:** Kataloge, Starter und Beschreibungen für Italienisch,
  Spanisch und Französisch in allen Paketen 18 von 18; eine
  Probe-Installation mit italienischer Systemsprache in einer abgeschotteten
  Kopie des Systems (98 Prüfungen bestanden, mit Bildschirmfotos).
- **Infobereich (Panel 0.4.0)** in abgeschotteten Läufen: mit Testprogrammen
  63 von 63 in Deutsch und Englisch, zwei Bildschirmgrößen, hell und dunkel;
  mit einem Programm auf Basis von libayatana-appindicator 13 von 13; neben
  einem fremden Dienst für Statussymbole 19 von 19; 309 automatische Tests
  des Panels.
- **Querencia Dateien 0.2.4** in abgeschotteten Läufen: lange Namen in der
  Kompaktansicht bei 50, 100 und 200 % ganz, Statusleiste nach Suche und
  Auswahl in Deutsch und Englisch; 21 Prüfläufe bestanden, 684 automatische
  Tests des Quellbaums.
- **Anmeldebildschirm 0.1.3** in einer abgeschotteten Probe ohne echte
  Anmeldeprüfung: Deutsch ganz deutsch, Englisch ganz englisch, keine
  Mischung; 96 Konfigurationsfälle bestanden.
- Statische Paketprüfung (300 bestanden), Lintian ohne Fehler,
  Probe-Installation in einer abgeschotteten Kopie des Systems (95 Prüfungen
  bestanden), ein Kontrollbau ergab dieselben Pakete.
- **Upgrade** in einer abgeschotteten Kopie des Systems: von Alpha 3.2 mit
  Schnatter (167 Prüfungen bestanden), ohne Schnatter (154), mit Schnatter
  und Webhülle (169) und von Alpha 3.1 mit Webhülle (170): nichts entfernt,
  nichts zurückgehalten, keine Rückfragen; eigene Einstellungen von Dateien
  und Schnatter erhalten.
- **In einer virtuellen Maschine:** [Weg B Lauf 1: Upgrade 3.2 → 3.3 mit
  Anmeldebildschirm, Zahlen]. [Weg B Lauf 2: Neuinstallation, Zahlen].
- Nicht geprüft: der Infobereich mit Webex, Nextcloud oder Discord, Spanisch
  und Französisch in der VM, Schnatter mit echtem Konto, echte
  Windows-Freigaben und Netzlaufwerke, echte USB-Geräte, Anmeldung über GDM,
  echte Hardware.

## Lizenzen und Herkunft

Wie Alpha 3.2. `locales-all` ist ein Paket von Ubuntu. Name und Logo
„Querencia“ sind keine freien Inhalte.

Copyright 2026 Querencia Desktop contributors.
