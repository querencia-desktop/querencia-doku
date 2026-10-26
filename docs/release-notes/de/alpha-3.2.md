# Querencia Desktop – Alpha 3.2

**Stand:** 26.10.2026 · **Status:** in der APT-Quelle seit 26. Oktober 2026, 22:11

Alpha 3.2 ist ein Pflegestand zu Alpha 3.1: eine Korrektur der Menüs in
Querencia Dateien und ein neuer Name für das wahlweise installierbare
Programm für WhatsApp Web: Aus Querencia Webhülle wird **Schnatter**. Es sind
24 Debian-Pakete für Ubuntu 26.04 („resolute“) aus derselben signierten
APT-Quelle; 20 davon sind unverändert seit Alpha 3.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren. Querencia Dateien selbst trägt die Stufe „Beta“.

## Neu in Alpha 3.2

- **Querencia Dateien 0.2.2:** Ein offenes Kontextmenü schließt sich nicht
  mehr, wenn der Zeiger auf dem Weg zu einem Eintrag unter einem Menü der
  Menüleiste steht. Bisher klappte dann zum Beispiel auf dem Weg zu
  „Umbenennen …“ oben „Ansicht“ auf. Auch der Pfeil nach rechts im
  Kontextmenü springt nicht mehr in die Menüleiste. Das Fenster „Netzwerk“
  heißt jetzt auch dann so, wenn der Netzdienst des Systems Englisch spricht
  (bisher „Network“). Die Ursache lag in der gemeinsamen Menü-Bibliothek der
  Querencia-Programme; Panel und Arbeitsfläche bekommen die neue Fassung mit
  ihrer nächsten Version.
- **Schnatter 0.3.0** (bisher Querencia Webhülle), wahlweise: WhatsApp Web
  im eigenen Fenster mit der klassischen Menüleiste, im Menü unter
  Anwendungen → Internet → „Schnatter“. Was die Webhülle konnte, kann
  Schnatter auch; neu sind Name und Symbol (eine grüne Sprechblase mit
  Schnabel).
  - **Wer die Webhülle installiert hatte,** bekommt Schnatter mit dem
    Upgrade. Das Paket `querencia-webhuelle` wird zu einem Übergangspaket,
    das Schnatter nachzieht. Beim ersten Start übernimmt Schnatter Anmeldung
    und Einstellungen: Es benennt die drei Ordner der Webhülle um, nichts
    wird kopiert oder gelöscht. Läuft die Webhülle dabei noch, sagt Schnatter
    das und startet erst, wenn sie geschlossen ist.
  - **Wer die Webhülle nicht hatte,** bekommt nichts Neues dazu. Schnatter
    ist nicht im Metapaket und nicht Teil der Standardinstallation.
    Einzeln installieren:

    ```bash
    sudo apt install querencia-schnatter
    ```

  Anrufe gehen weiter nicht (die Web-Engine von Ubuntu kommt ohne WebRTC).
  Schnatter ist kein Produkt von WhatsApp oder Meta und nicht mit ihnen
  verbunden.

Was Alpha 3.1 brachte (Dateien übernimmt die Einstellungen von Querencia
Files auch aus `~/.config/strata`; die Webhülle als neues, wahlweises
Programm), steht in den [Hinweisen zu Alpha 3.1](alpha-3.1.md).

## Versionen

Paketsatz vom 26.10.2026 (24 Pakete).

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.2-1 | Metapaket, Versionsdatei „Alpha 3.2“ |
| querencia-dateien | 0.2.2-1 | **geändert:** Kontextmenüs bleiben offen, Titel „Netzwerk“ |
| querencia-schnatter | 0.3.0-1 | **neu, wahlweise:** Schnatter, WhatsApp Web im eigenen Fenster (bisher Webhülle) |
| querencia-webhuelle | 0.3.0-1 | **Übergangspaket:** zieht Schnatter nach, ein versteckter Starter öffnet Schnatter |
| querencia-files | 0.2.0-1 | Übergangspaket aus Alpha 3 (unverändert) |
| querencia-shell | 0.1.0~alpha10-1 | Panel 0.3.2, Arbeitsfläche 0.3.0, Tastenkürzel-Übersicht 0.2.2, Thema 0.2.2 (unverändert seit Alpha 3) |
| querencia-session | 0.1.0~alpha10-1 | Sitzungsstarter (unverändert seit Alpha 3) |
| querencia-sitzung | 0.1.8-1 | Sitzungsdialog, Sperre, Passwortdialog (unverändert seit Alpha 3) |
| querencia-symbole | 0.8-1 | Programmsymbole und Symbolthema (unverändert seit Alpha 3) |
| querencia-dateisuche | 0.1.5-2 | Nach Dateien suchen (unverändert seit Alpha 3) |
| querencia-einstellungen | 0.1.6-1 | Systemeinstellungen (unverändert seit Alpha 3) |
| querencia-benachrichtigungen | 0.2.2-1 | Benachrichtigungen (unverändert seit Alpha 2) |
| querencia-hintergruende | 0.2-1 | 16 Hintergründe (unverändert seit Alpha 2) |
| labwc | 0.9.8-0querencia5 | Backport des Fensterverwalters (unverändert seit Alpha 2) |
| querencia-terminal | 0.3.2-1 | Terminal (unverändert seit Alpha 2.1) |
| querencia-editor | 0.2.4-1 | Texteditor (unverändert seit Alpha 2.1) |
| querencia-bilder | 0.2.6-1 | Bildbetrachter (unverändert seit Alpha 2.1) |
| querencia-dokumente | 0.1.4-1 | PDF-Betrachter (unverändert seit Alpha 2.1) |
| querencia-archiv | 0.1.2-1 | Archivverwaltung (unverändert seit Alpha 2.1) |
| querencia-rechner | 0.1.6-1 | Taschenrechner (unverändert seit Alpha 2.1) |
| querencia-systemmonitor | 0.1.5-1 | Systemüberwachung (unverändert seit Alpha 2.1) |
| querencia-screenshot | 0.2.10-1 | Bildschirmfoto (unverändert seit Alpha 2.1) |
| querencia-software | 0.1.5-1 | Programme installieren über PackageKit (unverändert seit Alpha 2.1) |
| querencia-anmeldung | 0.1.2-1 | Anmeldebildschirm auf Deutsch, optional (unverändert seit Alpha 2.1) |

Prüfsumme der Paketliste (SHA256SUMS): `fbf26227628c91d94d37faf2f222aaa397b4e475a4dbf24da029b157afed3c7f`.

## Aktualisieren von Alpha 3 oder 3.1

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` genügt ebenfalls. APT aktualisiert Querencia Dateien und
das Metapaket. Wer die Webhülle installiert hat, bekommt dazu Schnatter neu
und die Webhülle als Übergangspaket. Entfernt wird nichts, und es gibt keine
Rückfrage zu Konfigurationsdateien. In einer virtuellen Maschine dauerte das
Upgrade wenige Sekunden, ohne die Zeit zum Herunterladen. Danach abmelden und
neu anmelden (oder wenigstens Dateien schließen und neu öffnen). Die
Webhülle steht dann nicht mehr im Menü, Schnatter steht unter Internet; ein
Starter der Webhülle im Panel öffnet Schnatter.

Nach dem Upgrade meldet APT `querencia-webhuelle` als „nicht mehr benötigt“.
Das ist gewollt: Das Übergangspaket darf gehen, sobald keine Verknüpfung mehr
auf die Webhülle zeigt. APT überträgt dabei die Markierung „manuell
installiert“ auf Schnatter, sodass `sudo apt autoremove` nur das
Übergangspaket entfernt. Wer sichergehen will, markiert Schnatter vorher
selbst:

```bash
sudo apt install querencia-schnatter
```

Ein Upgrade von Alpha 2.1 oder 2.2 direkt auf 3.2 geht wie in den
[Hinweisen zu Alpha 3](alpha-3.md#aktualisieren-von-alpha-21) beschrieben.

## Neu installieren

Unverändert: Quelle einbinden, `sudo apt install querencia-desktop`, neu
starten, am Zahnrad „Querencia Desktop“ wählen (siehe
[Alpha 1, Installation](alpha-1.md#installation)). Fingerabdruck des
Signierschlüssels: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
Schnatter wird dabei nicht installiert. Auf einem frischen
Ubuntu-26.04-Server-Abbild installiert APT 389 Pakete; aus der
veröffentlichten Quelle dauert das etwa 1,5 bis 2 Minuten (je nach
Ubuntu-Archiv).

## Bekannte Grenzen

Weiter gültig aus Alpha 3 und 3.1 (siehe dort), soweit oben nicht als
behoben genannt. Davon besonders:

- **Querencia Dateien ist eine Beta.** Rückgängig (Strg+Z) gibt es noch
  nicht; eine Spaltenansicht und einen Ordnerbaum in der Seitenleiste gibt
  es nicht. Die Suche findet nur Namen, keinen Dateiinhalt; aus den
  Suchergebnissen lässt sich noch nicht kopieren oder ziehen. Die Ansicht
  wird nicht je Ordner gemerkt, offene Reiter nicht beim nächsten Start.
- **Kleinigkeiten in Dateien, noch offen:** Die Kompaktansicht kürzt lange
  Namen; die Statusleiste ist nach einer Suche leer.
- **Netzwerk teils ungeprüft:** Eine gelungene Verbindung zu einer
  Windows-Freigabe, Zertifikatsfragen bei sicheren Verbindungen und echte
  Netzlaufwerke sind ungeprüft.
- **Übernahme der Files-Einstellungen nur beim ersten Start** von Dateien
  (siehe [Alpha 3.1](alpha-3.1.md#bekannte-grenzen)).
- **Kein Infobereich im Panel.** Programme, die ein Symbol im Panel anzeigen
  wollen (Infobereich, „Tray“), zeigen keines. Schnatter meldet neue
  Nachrichten nur, solange sein Fenster offen ist; Schließen beendet es.
- **Schnatter mit echtem Konto** ist nicht in der Test-VM geprüft; geprüft
  sind Umzug, Anmeldeseite und Fenster.
- **Software-OpenGL** kostet Rechenzeit und Speicher; Programme, die der
  Fensterverwalter selbst startet (z. B. über Tastenkürzel), bekommen es
  nicht.
- **Nicht auf echter Hardware geprüft**, nur in virtuellen Maschinen und in
  abgeschotteten Kopien des Systems.

## Fehler melden

Wie Alpha 3, im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Geprüft

- Jede Quelle ist ein getaggter Stand; Querencia Dateien aus `dateien/0.2.2`,
  Schnatter aus `schnatter/0.3.0`.
- **Querencia Dateien 0.2.2** in abgeschotteten Läufen: Kontextmenü und
  Menüleiste 12 Fälle, hell und dunkel bestanden (mit 0.2.1 scheiterten 7
  davon); Fenstertitel „Netzwerk“ mit englisch sprechendem Netzdienst 2 von
  2; Wiederholung der Prüfungen von 0.2.1 (Reiter, Kompaktansicht, Suche,
  Übernahme der Files-Einstellungen) bestanden; 659 automatische Tests des
  Quellbaums.
- **Schnatter 0.3.0** in abgeschotteten Läufen: Umzug von der Webhülle und
  von älteren Fassungen mit Test-Ordnern (ohne echtes Konto), je 58 von 58 in
  acht Kombinationen; Prüfseite 74 von 74.
- Statische Paketprüfung (290 bestanden), Lintian ohne Fehler, Probe-Installation
  in einer abgeschotteten Kopie des Systems (95 Prüfungen bestanden), ein
  Kontrollbau ergab dieselben Pakete.
- **Upgrade** in einer abgeschotteten Kopie des Systems: von Alpha 3.1 mit
  Webhülle (168 Prüfungen bestanden) und ohne (149), von Alpha 3 (149) und
  von Alpha 2.1 (148): nichts entfernt, nichts zurückgehalten, keine
  Rückfragen.
- **In einer virtuellen Maschine:** Alpha 3.1 mit Webhülle aus der
  veröffentlichten Quelle, Webhülle einmal gestartet, dann das Upgrade auf
  3.2: drei Pakete aktualisiert, Schnatter neu, nichts entfernt, keine
  Rückfragen; Prüfskript 78 von 78, Sitzung 28 von 28. Schnatter übernahm
  beim ersten Start alle Dateien der Webhülle (139 von 139). Sichtprobe:
  Kontextmenü bleibt offen, Fenstertitel „Netzwerk“. Neuinstallation
  (389 Pakete, kein Schnatter): Prüfskript 76 von 76, Sitzung 28 von 28.
- Nicht geprüft: Schnatter mit echtem Konto, echte Windows-Freigaben und
  Netzlaufwerke, echte USB-Geräte, Anmeldung über GDM, echte Hardware.

## Lizenzen und Herkunft

Schnatter steht wie die anderen Querencia-Programme unter der
GPL-3.0-or-later. WhatsApp ist eine Marke ihres Inhabers und steht nur
beschreibend da, nie im Programmnamen oder im Symbol. Sonst wie Alpha 3.
Name und Logo „Querencia“ sind keine freien Inhalte.

Copyright 2026 Querencia Desktop contributors.
