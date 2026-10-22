# Querencia Desktop – Alpha 2.1

**Stand:** 22.10.2026 · **Status:** in der APT-Quelle seit 22. Oktober 2026,
11:16

Alpha 2.1 ist ein Pflegestand zwischen Alpha 2 und Alpha 3. Alle Programme
haben jetzt einen **einheitlichen Info-Dialog** und ein **Hilfe-Menü** mit
Online-Hilfe und „Fehler melden“. Dateien lassen sich aus dem **Papierkorb
zurückziehen** und **ins Terminal ziehen**. Die dunkle Darstellung reicht
weiter, das **Panel startet nach einem Absturz von selbst neu**, und der
Anmeldebildschirm spricht Deutsch. Es sind wieder 21 Debian-Pakete für
Ubuntu 26.04 („resolute“) aus derselben signierten APT-Quelle.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren.

## Neu in Alpha 2.1

- **Info-Dialog und Hilfe in allen Programmen.** Jedes Querencia-Programm
  nennt im Info-Dialog den Stand „Alpha – nicht für den Alltag freigegeben“,
  die Website querencialinux.org, Copyright und Lizenz. Das Hilfe-Menü hat
  „Online-Hilfe“ (Dokumentation in der Sprache der Oberfläche) und „Fehler
  melden“; beides öffnet den Browser. „Informationen über Querencia“ im
  Panel und in den Einstellungen zeigt die installierte Ausgabe, also
  „Querencia Desktop Alpha 2.1“.
- **Versionsdatei.** Das Metapaket legt `/usr/share/querencia/version` und
  `/usr/share/querencia/release` an (Format wie `/etc/os-release`). Daraus
  lesen die Info-Dialoge die Ausgabe sowie die Adressen für Hilfe und
  Fehlermeldungen.
- **Papierkorb wiederherstellen durch Ziehen.** Eine Datei aus dem
  Papierkorb in einen Ordner, die Seitenleiste oder auf die Arbeitsfläche
  ziehen stellt sie wieder her; Strg+Z macht das rückgängig (Querencia
  Files).
- **Dateien ins Terminal ziehen.** Aus Files gezogene Dateien landen als
  Pfad in einfachen Anführungszeichen an der Schreibmarke, wie im GNOME
  Terminal. Der Befehl wird nicht sofort ausgeführt (Terminal 0.3.2).
- **Arbeitsfläche:** Kontextmenü wie unter GNOME 2 (Öffnen mit,
  Ausschneiden, Kopieren, Einfügen, Umbenennen, In den Papierkorb,
  Eigenschaften), Strg+X/C/V, Entf und Umschalt+Entf mit Rückfrage; Dateien
  lassen sich zwischen Arbeitsfläche, Files und Papierkorb ziehen. Die
  Symbolbeschriftung steht wieder **ohne dunkle Platte** auf dem
  Hintergrundbild, weiß mit Schatten wie unter GNOME 2.
- **Dunkle Darstellung reicht weiter:** Jetzt folgen ihr auch das
  Bildschirmfoto (Auswahlfenster und Editor), die Tastenkürzel-Übersicht,
  Menü- und Reiterleiste des Terminals sowie der Dialog „Sitzung beenden“,
  die Rückfragen und die Passwortabfrage, wenn die dunkle Darstellung schon
  beim Anmelden gilt.
- **Panel startet nach einem Absturz neu.** Das Panel läuft unter einer
  kleinen Überwachung, die es nach einem Absturz neu startet, höchstens
  dreimal in zehn Minuten. Außerdem liest es das Symbolthema seltener neu
  ein; das behebt einen Absturz nach dem Installieren oder Ändern von
  Programmen.
- **Bildschirmsperre und Videos.** Browser und Videoprogramme können die
  Sperre bei Leerlauf anhalten, solange sie etwas abspielen (Dienst
  `org.freedesktop.ScreenSaver`).
- **Anmeldebildschirm auf Deutsch.** Der wahlweise Anmeldebildschirm
  `querencia-anmeldung` spricht die Systemsprache, die Uhr zeigt Datum und
  Zeit im Format der Sprache, und der Grußtext nennt die installierte
  Ausgabe.
- **Netzwerkeinstellungen.** Die Einstellungen haben eine Seite „Netzwerk“,
  und der Eintrag „Netzwerkeinstellungen …“ im Netzwerksymbol des Panels
  öffnet sie.
- **Schriften für asiatische Zeichen.** Das Metapaket empfiehlt
  `fonts-noto-core` und `fonts-noto-cjk`, damit Fenstertitel mit
  chinesischen, japanischen oder koreanischen Zeichen keine Kästchen zeigen.
  Mit `--no-install-recommends` entfallen sie.

## Versionen

Paketsatz vom 22.10.2026 (21 Pakete).

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha2.1-1 | Metapaket: zieht alle Bestandteile nach, Versionsdatei, empfiehlt Noto-Schriften |
| labwc | 0.9.8-0querencia5 | Backport des Fensterverwalters (unverändert seit Alpha 2) |
| querencia-session | 0.1.0~alpha7-3 | Sitzungsstarter; Panel unter Überwachung |
| querencia-shell | 0.1.0~alpha8-1 | Panel 0.2.3, Arbeitsfläche 0.2.4, Tastenkürzel-Übersicht 0.2.1, Thema Querencia-Klassisch 0.2.1 |
| querencia-hintergruende | 0.2-1 | 16 Hintergründe (unverändert seit Alpha 2) |
| querencia-sitzung | 0.1.4-1 | Sitzungsdialog, Sperre, Passwortabfrage, Bildschirmschoner-Dienst |
| querencia-benachrichtigungen | 0.2.2-1 | Benachrichtigungen (unverändert seit Alpha 2) |
| querencia-einstellungen | 0.1.5-1 | Systemeinstellungen mit Seite „Netzwerk“ und Info über die Ausgabe |
| querencia-symbole | 0.7-1 | Programmsymbole und Symbolthema (unverändert seit Alpha 2) |
| querencia-files | 0.1.0~alpha7-1 | Querencia Files: Papierkorb-Ziehen, Info mit Paketversion |
| querencia-terminal | 0.3.2-1 | Terminal: Dateien hineinziehen, dunkle Leisten |
| querencia-editor | 0.2.4-1 | Texteditor |
| querencia-bilder | 0.2.6-1 | Bildbetrachter |
| querencia-dokumente | 0.1.4-1 | PDF-Betrachter |
| querencia-archiv | 0.1.2-1 | Archivverwaltung |
| querencia-rechner | 0.1.6-1 | Taschenrechner |
| querencia-systemmonitor | 0.1.5-1 | Systemüberwachung |
| querencia-dateisuche | 0.1.5-1 | Nach Dateien suchen |
| querencia-screenshot | 0.2.10-1 | Bildschirmfoto, dunkel |
| querencia-software | 0.1.5-1 | Programme installieren über PackageKit |
| querencia-anmeldung | 0.1.2-1 | Anmeldebildschirm auf Deutsch, optional |

Prüfsumme der Paketliste (SHA256SUMS): `d990d65f791e50d20acd56a8210a91de50d4cbdb13f20cd4541029e43ab7ed50`.

## Aktualisieren von Alpha 2

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

Danach abmelden und neu anmelden: Erst dann starten Panel und Arbeitsfläche
in der neuen Fassung, und das Panel läuft unter seiner Überwachung. Eine
Rückfrage zu Konfigurationsdateien gibt es nicht, solange Sie
`/etc/querencia/labwc/` nicht selbst geändert haben. Mit Recommends lädt APT
die beiden Noto-Schriftpakete mit, laut Ubuntu-Index etwa 75 MB.

## Neu installieren

Unverändert: Quelle einbinden, `sudo apt install querencia-desktop`, neu
starten, am Zahnrad „Querencia Desktop“ wählen (siehe
[Alpha 1, Installation](alpha-1.md#installation)). Fingerabdruck des
Signierschlüssels: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`. Auf
einem Server-Abbild installiert APT etwa 389 Pakete.

## Bekannte Grenzen

Weiter gültig aus Alpha 2: Netzwerk-Applet nur mit NetworkManager, Firefox
als Snap ohne GTK-Thema, geteilte gsettings-Werte neben GNOME, greetd bleibt
nach dem Entfernen von `querencia-anmeldung`, vorläufige Kennungen
(`org.example…`) bei Panel und einigen Programmen. Neu bzw. geändert:

- **Files bleibt hell**, ebenso die Fensterrahmen von labwc. Fremde
  GTK-3-Programme folgen der dunklen Darstellung nicht.
- **Panel, Arbeitsfläche und Sperrbildschirm nur deutsch.** Die Programme
  sprechen Deutsch und Englisch.
- **Neustart des Panels dauert einige Sekunden.** Ubuntu schreibt bei jedem
  Absturz einen Fehlerbericht nach `/var/crash` (beim Panel etwa 17 MB); erst
  danach startet die Überwachung das Panel neu, in der Probe nach etwa
  sechs Sekunden. Die Ursache des Absturzes beim ersten Öffnen von
  „Anwendungen“ wird weiter untersucht.
- **Nicht auf echter Hardware geprüft**, nur in virtuellen Maschinen.
  Ebenfalls ungeprüft: Drucken auf einem echten Drucker, Windows-Freigaben
  (SMB), Anmeldung über den wahlweisen Anmeldebildschirm in der Paketquelle.
- Behoben gegenüber Alpha 2: Anmeldebildschirm nur englisch, Bildschirmfoto,
  Tastenkürzel-Übersicht und Terminal-Leisten hell, Panel startete nach
  einem Absturz nicht neu, „Netzwerkeinstellungen“ ohne Ziel.

## Fehler melden

Im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>, Deutsch
oder Englisch; „Fehler melden“ im Hilfe-Menü jedes Programms führt dorthin.
Bitte angeben:

- Ausgabe von `dpkg -l 'querencia-*' labwc`, `lsb_release -ds` und
  `cat /usr/share/querencia/version`
- was Sie getan haben, was Sie erwartet haben, was passiert ist
- etwa 50 Zeilen aus dem passenden Protokoll in `~/.local/state/querencia/`
  (Panel: `panel.log`, Sitzungsstart: `sitzung-start.log`)

Heimpfade, Rechnernamen und IP-Adressen im Protokoll bitte vorher
schwärzen. Sicherheitslücken nicht öffentlich melden, sondern über
<https://github.com/querencia-desktop/querencia/security/advisories/new>.

## Geprüft

- Jede Quelle ist ein getaggter Stand.
- Statische Paketprüfung 242 bestanden, Lintian ohne Fehler, signierte
  Testquelle, Probe-Installation in einer abgeschotteten Kopie des Systems
  88 bestanden; dabei wurde das Panel gezielt zum Absturz gebracht und kam
  von selbst wieder.
- **Frisches Ubuntu 26.04** (virtuelle Maschine, 22.10.2026, Textkonsole):
  Installation in etwa 64 s, Sitzung nach etwa 3 s, Prüfskript in der Sitzung 28/28. Geprüft wurden
  Info-Dialoge mit „Alpha 2.1“, Dateien ins Terminal ziehen, Papierkorb
  zurückziehen, dunkle Darstellung und der Neustart des Panels nach einem
  erzwungenen Absturz.
- **Upgrade von Alpha 2** (virtuelle Maschine): Alpha 2 aus der
  Paketquelle installiert, dann `apt full-upgrade` auf Alpha 2.1 in etwa
  19 s, ohne Rückfragen; nach der Neuanmeldung (knapp 5 s) läuft die neue
  Fassung mit Panel-Überwachung.
- Nicht geprüft: Anmeldung über GDM auf Ubuntu Desktop mit Alpha 2.1,
  Bildschirmsperre und Entsperren, echte Hardware.

## Lizenzen und Herkunft

Wie Alpha 2. Name und Logo „Querencia“ sind keine freien Inhalte.

Copyright 2026 Querencia Desktop contributors.
