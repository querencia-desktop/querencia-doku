# Querencia Desktop – Alpha 3.5

**Stand:** 28.10.2026 · **Status:** in der APT-Quelle seit 28. Oktober 2026, 12:07

Alpha 3.5 ist ein Pflegestand mit zwei Korrekturen. Der Anmeldebildschirm
spricht jetzt auch Italienisch, Spanisch und Französisch. Die Seite
„Treiber“ in den Systemeinstellungen zeigt richtig, ob die Sitzung auf der
Grafikkarte zeichnet oder in Software. Es sind 24 Debian-Pakete für Ubuntu
26.04 („resolute“) aus derselben signierten APT-Quelle; 3 davon
sind neu gebaut.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren. Querencia Dateien selbst trägt die Stufe „Beta“.

## Neu in Alpha 3.5

- **Anmeldebildschirm auf Italienisch, Spanisch und Französisch**
  (`querencia-anmeldung` 0.1.5, wahlweise): Der Anmeldebildschirm zeigt
  Beschriftungen, Knöpfe, Tooltips und Meldungen, auch die bei abgelaufenem
  Passwort, jetzt auch in diesen drei Sprachen; vorher waren sie dort
  englisch. Die Uhr folgt dem Datumsformat der Sprache.
- **Seite „Treiber“ zeigt die Darstellung richtig** (Querencia
  Einstellungen 0.2.1). Die Zeile „Diese Sitzung:“ folgt jetzt dem
  gemessenen Renderer und dem geladenen Kernelmodul. Sie zeigt einen von
  drei Fällen:
  - „OpenGL auf der Grafikkarte mit dem freien Treiber“,
  - „OpenGL auf der Grafikkarte mit dem proprietären NVIDIA-Treiber“,
  - „Software-Darstellung“ mit dem Grund: Die Sitzung hat bei der Anmeldung
    umgeschaltet, weil es mit dieser Karte ein Grafikproblem gibt, oder es
    gibt keine 3D-Beschleunigung, zum Beispiel in einer virtuellen Maschine
    ohne 3D-Grafik.

  Bisher stand in einer virtuellen Maschine mit llvmpipe fälschlich „OpenGL
  auf der Grafikkarte“. „OpenGL-Renderer:“ nennt, was die Programme der
  Sitzung bekommen; hat die Sitzung umgeschaltet, nennt die neue Zeile
  „OpenGL der Karte:“ den Renderer der Grafikkarte. Bei virtueller Grafik
  steht als Kerneltreiber `virtio_gpu` statt `virtio-pci`. Der Hinweis zu
  Software-OpenGL entfällt, wenn der NVIDIA-Treiber zeichnet. Die Seite
  findet den Sitzungsstarter jetzt wie die Sitzung selbst, nicht nur über
  `PATH`; sonst konnte der Renderer „nicht gemessen“ bleiben.

Was Alpha 3.4 brachte (Seite „Treiber“, Rückgängig in Querencia Dateien),
steht in den [Hinweisen zu Alpha 3.4](alpha-3.4.md).

## Versionen

Paketsatz vom 27.10.2026 (24 Pakete).

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.5-1 | Metapaket, Versionsdatei „Alpha 3.5“; Abhängigkeiten unverändert |
| querencia-einstellungen | 0.2.1-1 | **geändert:** Zeile „Diese Sitzung“ der Seite „Treiber“ nach gemessenem Renderer |
| querencia-anmeldung | 0.1.5-1 | **geändert:** Anmeldebildschirm auf Deutsch, Englisch, Italienisch, Spanisch, Französisch; optional |
| querencia-dateien | 0.3.0-1 | Dateimanager (unverändert seit Alpha 3.4) |
| querencia-shell | 0.1.0~alpha12-1 | Panel, Arbeitsfläche, Tastenkürzel-Hilfe, Lautstärkeregler (unverändert seit Alpha 3.4) |
| querencia-sitzung | 0.1.10-1 | Sitzungsdialog, Sperrbildschirm (unverändert seit Alpha 3.4) |
| querencia-software | 0.1.7-1 | Software-Center |
| querencia-editor | 0.2.5-1 | Texteditor |
| querencia-terminal | 0.3.3-1 | Terminal |
| querencia-rechner | 0.1.7-1 | Taschenrechner |
| querencia-bilder | 0.2.7-1 | Bildbetrachter |
| querencia-dokumente | 0.1.5-1 | PDF-Betrachter |
| querencia-archiv | 0.1.3-1 | Archivverwaltung |
| querencia-systemmonitor | 0.1.6-1 | Systemüberwachung |
| querencia-dateisuche | 0.1.6-1 | Nach Dateien suchen |
| querencia-screenshot | 0.2.11-1 | Bildschirmfoto |
| querencia-benachrichtigungen | 0.2.3-1 | Benachrichtigungen |
| querencia-schnatter | 0.3.1-1 | Schnatter, WhatsApp Web im eigenen Fenster, wahlweise |
| querencia-webhuelle | 0.3.0-1 | Übergangspaket zu Schnatter |
| querencia-files | 0.2.0-1 | Übergangspaket aus Alpha 3 |
| querencia-session | 0.1.0~alpha10-1 | Sitzungsstarter |
| querencia-symbole | 0.8-1 | Programmsymbole und Symbolthema |
| querencia-hintergruende | 0.2-1 | 16 Hintergründe |
| labwc | 0.9.8-0querencia5 | Backport des Fensterverwalters |

Von Dateien bis labwc sind die Pakete byte-gleich mit Alpha 3.4.

Prüfsumme der Paketliste (SHA256SUMS): `e19e14215b5d86f8174b7ef06b68e9d8de7f528221304327dd81172c99d6f509`.

## Aktualisieren von Alpha 3.4

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` genügt ebenfalls. APT aktualisiert 2 Pakete, mit dem
Anmeldebildschirm 3; neu installiert wird nichts. Dafür lädt es rund 1,6 MB
herunter (mit Anmeldebildschirm 3,6 MB). Entfernt wird nichts, und es gibt
keine Rückfrage zu Konfigurationsdateien. Wer zugleich Updates von Ubuntu bekommt (in der Prüfung ein neuer Kernel),
lädt entsprechend mehr und wartet länger; die Zeit für Querencia allein ist
nicht getrennt gemessen.
Danach abmelden und neu anmelden.

Von Alpha 3.3 geht es genauso; was dabei sonst geschieht
(`ubuntu-drivers-common` kommt neu dazu), steht in den
[Hinweisen zu Alpha 3.4](alpha-3.4.md#aktualisieren-von-alpha-33).

## Neu installieren

Unverändert: Quelle einbinden, `sudo apt install querencia-desktop`, neu
starten, am Zahnrad „Querencia Desktop“ wählen (siehe
[Alpha 1, Installation](alpha-1.md#installation)). Fingerabdruck des
Signierschlüssels: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
Auf einem frischen Ubuntu-26.04-Server-Abbild installiert APT
392 Pakete.

## Bekannte Grenzen

Weiter gültig aus Alpha 3.4 (siehe dort). Die falsche Zeile „Diese
Sitzung:“ in virtuellen Maschinen ist behoben. Davon besonders:

- **Seite „Treiber“:** Ein Wechsel braucht `ubuntu-drivers-common`, eine
  Netzverbindung und das Passwort, und er wirkt erst nach einem Neustart.
  Mit einer echten NVIDIA-, AMD- oder Intel-Karte ist die Seite noch nicht
  geprüft, ebenso wenig Rechner mit zwei Grafikkarten und Secure Boot. Vor
  einem Wechsel einen Snapshot anlegen; kommt danach kein Bild, an der
  Textkonsole (Strg+Alt+F3) anmelden und die NVIDIA-Pakete wieder
  entfernen.
- **Anmeldebildschirm:** Ein abgelaufenes Passwort lässt sich nur an der
  Textkonsole ändern. Texte von GTK selbst, etwa der Tooltip am Auge im
  Passwortfeld, bleiben ohne das Sprachpaket
  `language-pack-gnome-<xx>-base` englisch.
- **Querencia Dateien ist eine Beta**, mit den Grenzen aus Alpha 3.4.
- **Nicht auf echter Hardware geprüft**, nur in virtuellen Maschinen und in
  abgeschotteten Kopien des Systems.

## Fehler melden

Wie Alpha 3, im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Geprüft

- Jede Quelle ist ein getaggter Stand: die Einstellungen aus
  `einstellungen/0.2.1-2`, der Anmeldebildschirm aus `anmeldung/0.1.5`.
- **Seite „Treiber“** in abgeschotteten Läufen mit sieben nachgebildeten
  Fällen (virtuelle Maschine mit llvmpipe, NVIDIA mit freiem Treiber mit und
  ohne Umschalten, NVIDIA mit NVIDIA-Treiber, AMD, Intel, keine Karte), in
  Deutsch und Englisch: 162 Prüfungen bestanden; die 14 übrigen Seiten
  pixelgleich mit 0.2.0; 159 automatische Tests; die Kataloge aller fünf
  Sprachen 532 Prüfungen.
- **Anmeldebildschirm 0.1.5** in abgeschotteten Proben in Italienisch,
  Spanisch, Französisch, Deutsch und Englisch: alle eigenen Texte in der
  Sprache, Uhr nach der Sprache, abgelaufenes Passwort mit der Meldung,
  gültiges Passwort startet die Sitzung; 102 Konfigurationsfälle bestanden.
- Statische Paketprüfung (304 bestanden), Lintian ohne Fehler,
  Probe-Installation in einer abgeschotteten Kopie des Systems (96
  Prüfungen bestanden, mit italienischer Systemsprache 103), ein
  Kontrollbau ergab dieselben Pakete.
- **Upgrade** in einer abgeschotteten Kopie des Systems: von Alpha 3.4 mit
  Schnatter (167 Prüfungen bestanden), ohne Schnatter (154) und von Alpha
  3.3 mit Schnatter (168): nichts entfernt, nichts zurückgehalten, keine
  Rückfragen.
- **In einer virtuellen Maschine:** Alpha 3.4 mit Schnatter und
  Anmeldebildschirm aus der veröffentlichten Quelle, dann das Upgrade auf
  3.5: 3 Querencia-Pakete aktualisiert, nichts neu, nichts entfernt, keine
  Rückfragen; Prüfskript 110 bestanden (die übrige Meldung ist das
  Protokoll des laufenden Panels), Anmeldebildschirm 4 von 4, Sitzung 28
  von 28. Sichtproben: Seite „Treiber“ mit „Software-Darstellung: keine
  3D-Beschleunigung …“ und `virtio_gpu`; Anmeldebildschirm auf Italienisch
  samt falschem und abgelaufenem Passwort, Gegenprobe auf Deutsch.
  Neuinstallation (392 Pakete mit `locales-all` und `ubuntu-drivers-common`,
  kein Schnatter): Prüfskript 109 von 109, Sitzung 28 von 28.
- Nicht geprüft: ein echter Treiberwechsel mit Neustart, echte NVIDIA-,
  AMD- oder Intel-Karten, Rechner mit zwei Grafikkarten, Secure Boot, die
  Treiberseite in Italienisch, Spanisch und Französisch mit
  Bildschirmfotos, Texte von GTK und Linux-PAM im Anmeldebildschirm auf
  Italienisch, Spanisch und Französisch, der Anmeldebildschirm auf Spanisch
  und Französisch in der virtuellen Maschine, echte Hardware.

## Lizenzen und Herkunft

Wie Alpha 3.4. Name und Logo „Querencia“ sind keine freien Inhalte.

Copyright 2026 Querencia Desktop contributors.
