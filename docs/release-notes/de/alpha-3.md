# Querencia Desktop – Alpha 3

**Stand:** `<Datum>` · **Status:** in der APT-Quelle seit `<Datum>`, `<Uhrzeit>`

Mit Alpha 3 bekommt Querencia seinen **eigenen Dateimanager: Querencia
Dateien** 0.2.0, eine Beta. Er folgt Nautilus 2.30 – Menüleiste,
Werkzeugleiste, Knopfpfad, Seitenleiste „Orte“, Statusleiste – und bringt
Reiter, drei Ansichten, Miniaturen, eine Namenssuche und „Mit Server
verbinden …“ mit. Querencia Dateien ist jetzt das Programm für Ordner; das
bisherige Querencia Files (ein Fork von Strata) wird ausgemustert. Es sind
`<Anzahl>` Debian-Pakete für Ubuntu 26.04 („resolute“) aus derselben
signierten APT-Quelle.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren.

## Neu in Alpha 3

- **Querencia Dateien 0.2.0 (Beta).** Anwendungen → Zubehör → „Querencia
  Dateien“ (englisch „Files“), die Orte im Panel und die Ordner- und
  Laufwerkssymbole der Arbeitsfläche öffnen ihn. Er kopiert, verschiebt und
  löscht mit Fortschritt, Abbrechen und Rückfrage bei gleichen Namen, hat
  einen Papierkorb mit Wiederherstellen, Laufwerke mit Einhängen und
  Auswerfen, „Öffnen mit“, einen Eigenschaften-Dialog mit Zugriffsrechten
  und Einstellungen in fünf Reitern, die sofort wirken. Deutsch und
  Englisch, hell und dunkel. Dazu kommen:
  - **Netzwerk:** „Netzwerk“ zeigt die Rechner im lokalen Netz, jeden nur
    einmal. **Datei → Mit Server verbinden …** öffnet SFTP-Server,
    Windows-Freigaben (SMB), FTP und WebDAV, auf Wunsch mit Lesezeichen.
    Das Kennwort wird beim Verbinden abgefragt und nur auf Wunsch im
    Schlüsselbund gemerkt. Bei einem unbekannten SFTP-Server zeigt Dateien
    vor dem Kennwort den Fingerabdruck des Serverschlüssels; „Trotzdem
    verbinden“ muss man ausdrücklich wählen. Fehler erklärt eine Meldung in
    einem Satz.
  - **Miniaturen und Suche:** Bilder zeigen Miniaturen, aus demselben
    Zwischenspeicher wie andere Programme; einstellbar unter Einstellungen
    → Vorschau (Immer, Nur lokale Dateien, Nie; Größengrenze). Fremde
    Vorschauprogramme, etwa für PDF, laufen nur abgeschottet über
    `bubblewrap`. **Strg+F** sucht ab dem gezeigten Ordner nach Namen;
    „Erweiterte Suche …“ übergibt an Nach Dateien suchen.
  - **Reiter und Kompaktansicht:** Strg+T öffnet einen Reiter, die mittlere
    Maustaste öffnet Ordner in einem Reiter dahinter; Reiterleiste und Menü
    „Reiter“ erscheinen ab zwei Reitern. Neben Symbolen und Liste gibt es
    die Kompaktansicht (Strg+3).
- **Querencia Files wird ausgemustert.** Ordner öffnen in Querencia Dateien,
  auch über eine ältere eigene Wahl in `~/.config/mimeapps.list`. Starter
  und Panel-Knöpfe, die noch auf Files zeigen, öffnen Querencia Dateien.
  Das Paket `querencia-files` wird zu einem Übergangspaket: Das Programm
  Files und der Befehl `querencia-files` entfallen mit dem Aktualisieren,
  die beiden versteckten Starter bleiben und öffnen Querencia Dateien. Das
  Übergangspaket kann weg, sobald keine Verknüpfung mehr auf Files zeigt.
  `<laut Packaging-Entwurf vom 24.10., gegen den endgültigen Satz prüfen>`
  Beim ersten Start übernimmt Dateien einmal sechs Einstellungen von Files
  (verborgene Dateien, Ansicht, Sortierung, Ordner zuerst, Einfach- oder
  Doppelklick, Seitenleiste); die Lesezeichen
  (`~/.config/gtk-3.0/bookmarks`) teilen sich beide. Die Einstellungen von
  Files in `~/.config/querencia-files` bleiben unverändert liegen.
- **Andere Tastenkürzel als in Files.** In Querencia Dateien gilt:

  | Wirkung | Querencia Files | Querencia Dateien |
  |---|---|---|
  | Symbolansicht | Strg+2 | **Strg+1** |
  | Listenansicht | Strg+3 | **Strg+2** |
  | Kompaktansicht | – | **Strg+3** |
  | Spaltenansicht | Strg+1 | entfällt (wird zur Liste) |
  | Lesezeichen hinzufügen | – | **Strg+D** (in Files: Duplizieren) |
  | Seitenleiste ein/aus | Strg+B | **F9** |
  | Suchen | Strg+K | **Strg+F** |
  | Aktualisieren | Strg+R | Strg+R oder **F5** |
  | Einstellungen | Strg+, | ohne Kürzel, Bearbeiten → Einstellungen |
  | Rückgängig, Wiederholen | Strg+Z, Strg+Umschalt+Z | noch nicht vorhanden |
  | Endgültig löschen | Umschalt+Entf | Umschalt+Entf, heißt „Löschen …“, mit Nachfrage |

  Was in Files „Tab“ hieß, heißt in Dateien **„Reiter“**. Weiter gilt unter
  anderem: Strg+T neuer Reiter, Strg+W schließt den Reiter (der letzte das
  Fenster), Strg+N neues Fenster, Strg+L Ort eingeben, Strg+H verborgene
  Dateien, Alt+↑ übergeordneter Ordner. Alle Kürzel zeigt Super+?.
- **Panel 0.3.2:** Das Menü „Orte“ öffnet Ordner mit dem Ordnerprogramm der
  Sitzung und kennt Querencia Dateien auch ohne gesetzte Vorgabe.
- **Tastenkürzel-Übersicht 0.2.2:** Super+? zeigt den Block „Querencia
  Dateien“ mit allen Kürzeln statt des Blocks von Files.
- `<nur wenn querencia-sitzung 0.1.8 im Satz ist; Stand 24.10.: 0.1.7>`
  **Sitzung 0.1.8:** Nach einem Neustart von polkitd, etwa
  durch ein Update, meldet sich der Passwortdialog für Verwaltungsaufgaben
  von selbst beim neuen polkitd an; bisher scheiterten solche Anfragen dann
  ohne Dialog.
- `<nur wenn das Paket querencia-session die Grafikprüfung des Sitzungsstarters enthält; Stand 24.10.: nur im Entwicklungsstand>`
  **Software-OpenGL bei zink auf nouveau:** Läuft OpenGL auf einer
  NVIDIA-Karte mit dem freien Treiber nouveau über zink, gibt der
  Sitzungsstarter den Programmen der Sitzung Software-OpenGL (llvmpipe). In
  der Prüfung stürzte sonst der Webinhalt von Querencia Nachrichten ab und
  Firefox fror ein; mit Software-OpenGL laufen beide, dafür rechnet der
  Prozessor. Der Fensterverwalter selbst bleibt unverändert. Steuerbar in
  `~/.config/querencia/grafik.ini` (`[Grafik] Software-OpenGL =
  automatisch|an|aus`), Protokoll in
  `~/.local/state/querencia/sitzung-start.log`.
- `<nur wenn querencia-nachrichten im Satz ist:>` **Querencia Nachrichten
  0.1.1:** derselbe Grafik-Rückfall (Einstellung „Software-Grafik“, ab dem
  nächsten Start); Links mit anderen Schemata als http, https und mailto
  öffnen erst nach Rückfrage. Anrufe gehen weiterhin nicht.
- **Arbeitsfläche 0.3.0:** Kopieren, Verschieben und Löschen auf der
  Arbeitsfläche mit Fortschritt, Abbrechen und derselben Rückfrage bei
  gleichen Namen wie in Querencia Dateien; neu angesteckte USB-Sticks und
  eingelegte CDs werden eingehängt, ohne dass sich ein Fenster öffnet;
  Rechner, Papierkorb und Laufwerke öffnen in Dateien.
- `<nur wenn Alpha 2.2 nicht vorher veröffentlicht wird:>` **Aus dem Stand
  Alpha 2.2:** Die Ursache der Panel-Abstürze beim Öffnen von „Anwendungen“
  ist behoben; die dunkle Darstellung schaltet auch Fensterrahmen und
  GTK-3-Programme um; in der Sperre geht der Bildschirm nach zwei Minuten
  aus; „Ausschalten …“ bietet „Neu starten“ an; Panel und Arbeitsfläche
  sprechen auch Englisch; Bildschirm-Einstellungen je Monitor.
- **Symbole 0.8:** eigenes Programmsymbol für Querencia Dateien.

## Versionen

Paketsatz vom `<Datum>` (`<Anzahl>` Pakete).

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | `<0.1.0~alpha3-n>` | Metapaket: zieht Querencia Dateien statt Files nach, Versionsdatei „Alpha 3“ |
| querencia-dateien | `<0.2.0-n>` | **neu:** Dateimanager Querencia Dateien 0.2.0 (Beta) |
| querencia-files | `<0.2.0-1>` | Übergangspaket: Files entfällt, die versteckten Starter öffnen Querencia Dateien |
| querencia-shell | `<0.1.0~alpha10-n>` | Panel 0.3.2, Arbeitsfläche 0.3.0, Tastenkürzel-Übersicht 0.2.2, Thema `<Fassung>` |
| querencia-session | `<0.1.0~alpha9-n>` | Sitzungsstarter: Ordner öffnen mit Querencia Dateien |
| querencia-sitzung | `<0.1.7-1 oder 0.1.8-1>` | Sitzungsdialog, Sperre, Passwortdialog |
| querencia-symbole | `<0.8-1>` | Programmsymbole und Symbolthema, neu das Symbol von Dateien |
| querencia-dateisuche | `<0.1.5-2>` | Nach Dateien suchen; empfiehlt Querencia Dateien statt Files |
| `<übrige Pakete>` | `<Fassung>` | `<unverändert seit Vorgänger, Liste laut endgültigem Satz>` |

Prüfsumme der Paketliste (SHA256SUMS): `<SHA256SUMS>`.

## Aktualisieren von `<Alpha 2.1 oder 2.2>`

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`<Was APT dabei installiert, aktualisiert und entfernt, laut Upgrade-Probe des endgültigen Satzes>`
Danach abmelden und neu anmelden. Ordner öffnen dann in Querencia Dateien;
„Querencia Files“ steht nicht mehr im Menü.

`<Rückfallhinweis laut endgültigem Satz, z. B. ob und wie sich Files noch installieren lässt>`

## Neu installieren

Unverändert: Quelle einbinden, `sudo apt install querencia-desktop`, neu
starten, am Zahnrad „Querencia Desktop“ wählen (siehe
[Alpha 1, Installation](alpha-1.md#installation)). Fingerabdruck des
Signierschlüssels: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
Querencia Files wird nicht mehr installiert.
`<Neuinstallation: Paketzahl und Dauer>`

## Bekannte Grenzen

Weiter gültig aus Alpha 2 (siehe dort). Neu bzw. geändert:

- **Querencia Dateien ist eine Beta.** Rückgängig (Strg+Z) gibt es noch
  nicht; eine Spaltenansicht und einen Ordnerbaum in der Seitenleiste gibt
  es nicht. Die Suche findet nur Namen, keinen Dateiinhalt; aus den
  Suchergebnissen lässt sich noch nicht kopieren oder ziehen. Die Ansicht
  wird nicht je Ordner gemerkt, offene Reiter nicht beim nächsten Start.
- **Netzwerk teils ungeprüft:** Geprüft wurde mit Testservern für SFTP,
  WebDAV und FTP in einer abgeschotteten Umgebung. Eine gelungene Verbindung
  zu einer Windows-Freigabe, Zertifikatsfragen bei sicheren Verbindungen und
  echte Netzlaufwerke sind ungeprüft.
- **Miniaturen für PDF** erscheinen nur, wenn ein Vorschauprogramm für PDF
  und `bubblewrap` installiert sind.
- **Was Files konnte und Dateien nicht:** die Vorschau im Fenster, die
  Spaltenansicht und das Entpacken im Programm. Archive öffnet die
  Archivverwaltung per Doppelklick; ein Eintrag „Hier entpacken“ im
  Kontextmenü von Dateien fehlt noch.
- `<nur wenn Software-OpenGL im Satz ist:>` **Software-OpenGL** kostet Rechenzeit und Speicher; Programme, die der
  Fensterverwalter selbst startet (z. B. über Tastenkürzel), bekommen es
  nicht.
- `<nur wenn querencia-nachrichten im Satz ist:>` **Querencia Nachrichten:**
  keine Anrufe.
- **Nicht auf echter Hardware geprüft**, nur in virtuellen Maschinen und in
  abgeschotteten Kopien des Systems.

## Fehler melden

Wie Alpha 2, im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>. Für
Querencia Dateien bitte zusätzlich die Ausgabe aus dem Terminal angeben
(`querencia-dateien` im Terminal starten, die Zeilen mit
„querencia-dateien:“).

## Geprüft

- Jede Quelle ist ein getaggter Stand; Querencia Dateien aus `dateien/0.2.0`.
- Querencia Dateien in abgeschotteten Läufen (eigener Fensterverwalter ohne
  Bildschirm, eigenes Profil mit Testdateien, Netz nur im eigenen
  Namensraum), in 1024×768 und 1920×1080, hell und dunkel, alle bestanden:
  Reiter 20 Fälle,
  Kompaktansicht 14, Suche in Reitern 5, Übernahme der Files-Einstellungen
  je 3, Netzwerk 53, Miniaturen und Suche 26, Ansichten 80, Dateioperationen
  35; dazu 656 automatische Tests des Quellbaums.
- `<Paketprüfung, Lintian, Probe-Installation und Upgrade-Probe des endgültigen Satzes>`
- Nicht geprüft: echte Windows-Freigaben und Netzlaufwerke, echte
  USB-Geräte, Anmeldung über GDM.

## Lizenzen und Herkunft

Querencia Dateien steht unter der GPL-3.0-or-later; einige aus Querencia
Files übernommene Teile behalten die MIT-Lizenz von Strata (der Info-Dialog
nennt das). Sonst wie Alpha 2. Name und Logo „Querencia“ sind keine freien
Inhalte.

Copyright 2026 Querencia Desktop contributors.
