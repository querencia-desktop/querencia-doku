# Querencia Desktop – Alpha 3.6

**Stand:** 28.10.2026 · **Status:** in der APT-Quelle seit [Datum], [Uhrzeit]

Alpha 3.6 ist ein Pflegestand mit zwei Korrekturen. Panel, Arbeitsfläche
und Querencia Dateien zeigen in einer frischen Installation die
Querencia-Symbole statt der Symbole von GNOME-Human. Querencia Software
zeigt Programme nicht mehr doppelt. Es sind 24 Debian-Pakete für Ubuntu
26.04 („resolute“) aus derselben signierten APT-Quelle; 4 davon sind neu
gebaut.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren. Querencia Dateien selbst trägt die Stufe „Beta“.

## Neu in Alpha 3.6

- **Querencia-Symbole in frischen Installationen** (`querencia-shell`
  0.1.0~alpha13 mit Panel 0.4.1 und Arbeitsfläche 0.3.2, Querencia
  Dateien 0.3.1): Ohne eigene Wahl eines Symbolthemas zeigten Panel,
  Arbeitsfläche und Querencia Dateien bisher die Symbole von GNOME-Human,
  etwa einen glänzenden Rechner und einen Papierkorb aus Metall, während
  die Systemeinstellungen „Querencia“ anzeigten. Jetzt gilt ohne eigene Wahl
  die Vorgabe der Querencia-Sitzung, also „Querencia“, mit flachen
  Symbolen. Wer unter „Erscheinungsbild“ selbst ein Symbolthema gewählt
  hat, sieht keinen Unterschied. Außerhalb der Querencia-Sitzung bleibt es
  bei GNOME-Human.
- **Keine doppelten Programme in Querencia Software** (`querencia-software`
  0.1.8): Programme wie Remmina, die Ubuntu in zwei Paketquellen unter
  leicht verschiedener Kennung führt (einmal mit, einmal ohne die Endung
  `.desktop`), stehen nur noch einmal in Suche und Kategorien. Dabei
  behoben: GIMP verschwand aus Software, sobald es installiert war.

Was Alpha 3.5 brachte (Anmeldebildschirm in fünf Sprachen, Zeile „Diese
Sitzung“ der Seite „Treiber“), steht in den
[Hinweisen zu Alpha 3.5](alpha-3.5.md).

## Versionen

Paketsatz vom 28.10.2026 (24 Pakete).

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.6-1 | Metapaket, Versionsdatei „Alpha 3.6“; verlangt mindestens die neuen Fassungen von Shell, Dateien und Software |
| querencia-shell | 0.1.0~alpha13-1 | **geändert:** Panel 0.4.1, Arbeitsfläche 0.3.2 mit der Symbolvorgabe der Sitzung; dazu Tastenkürzel-Hilfe, Lautstärkeregler |
| querencia-dateien | 0.3.1-1 | **geändert:** Dateimanager mit der Symbolvorgabe der Sitzung |
| querencia-software | 0.1.8-1 | **geändert:** Software-Center mit Katalog 0.1.1, keine doppelten Programme |
| querencia-einstellungen | 0.2.1-1 | Systemeinstellungen (unverändert seit Alpha 3.5) |
| querencia-anmeldung | 0.1.5-1 | Anmeldebildschirm in fünf Sprachen, optional (unverändert seit Alpha 3.5) |
| querencia-sitzung | 0.1.10-1 | Sitzungsdialog, Sperrbildschirm |
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
| querencia-session | 0.1.0~alpha10-1 | Sitzungsstarter; setzt „Querencia“ als Vorgabe für das Symbolthema |
| querencia-symbole | 0.8-1 | Programmsymbole und Symbolthema |
| querencia-hintergruende | 0.2-1 | 16 Hintergründe |
| labwc | 0.9.8-0querencia5 | Backport des Fensterverwalters |

Von den Einstellungen bis labwc sind die Pakete byte-gleich mit Alpha 3.5.

Prüfsumme der Paketliste (SHA256SUMS): `19dfc9355bbcb45b0d4832dc240c913b7be59444d28affa58bb03676859942fc`.

## Aktualisieren von Alpha 3.5

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` genügt ebenfalls. APT aktualisiert 4 Pakete
(`querencia-shell`, `querencia-dateien`, `querencia-software`,
`querencia-desktop`) und lädt dafür rund 26 MB herunter. Neu installiert
wird nichts, entfernt wird nichts, und es gibt keine Rückfrage zu
Konfigurationsdateien. Schnatter und der Anmeldebildschirm bleiben, wie sie
sind. Danach abmelden und neu anmelden; erst dann zeigen Panel,
Arbeitsfläche und Querencia Dateien die Querencia-Symbole.

Von Alpha 3.4 geht es genauso; dann kommen die Pakete aus Alpha 3.5 dazu
(die Einstellungen, mit dem Anmeldebildschirm auch er), siehe
[Hinweise zu Alpha 3.5](alpha-3.5.md#aktualisieren-von-alpha-34).

## Neu installieren

Unverändert: Quelle einbinden, `sudo apt install querencia-desktop`, neu
starten, am Zahnrad „Querencia Desktop“ wählen (siehe
[Alpha 1, Installation](alpha-1.md#installation)). Fingerabdruck des
Signierschlüssels: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
Auf einem frischen Ubuntu-26.04-Server-Abbild installiert APT
392 Pakete.

## Bekannte Grenzen

Weiter gültig aus Alpha 3.5 (siehe dort). Die Symbole von GNOME-Human in
frischen Installationen und doppelte Programme in Software sind behoben.
Davon besonders:

- **Symbolthema:** Die Vorgabe „Querencia“ gilt nur in der
  Querencia-Sitzung. Neben Ubuntu Desktop zeigt Querencia weiter die
  Yaru-Symbole, weil Ubuntu das Symbolthema als eigenen Wert setzt. Ein
  gewähltes Symbolthema, das nicht installiert ist, führt zu GNOME-Human.
- **Seite „Treiber“:** Ein Wechsel braucht `ubuntu-drivers-common`, eine
  Netzverbindung und das Passwort, und er wirkt erst nach einem Neustart.
  Mit einer echten NVIDIA-, AMD- oder Intel-Karte ist die Seite noch nicht
  geprüft, ebenso wenig Rechner mit zwei Grafikkarten und Secure Boot. Vor
  einem Wechsel einen Snapshot anlegen.
- **Anmeldebildschirm:** Ein abgelaufenes Passwort lässt sich nur an der
  Textkonsole ändern. Texte von GTK selbst bleiben ohne das Sprachpaket
  `language-pack-gnome-<xx>-base` englisch.
- **Querencia Dateien ist eine Beta**, mit den Grenzen aus Alpha 3.4.
- **Nicht auf echter Hardware geprüft**, nur in virtuellen Maschinen und in
  abgeschotteten Kopien des Systems.

## Fehler melden

Wie Alpha 3, im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Geprüft

- Jede Quelle ist ein getaggter Stand: Panel, Arbeitsfläche und Dateien aus
  `panel/0.4.1`, `desktop/0.3.2` und `dateien/0.3.1`, Software aus
  `software/0.1.8` mit dem Katalog `katalog/0.1.1`.
- **Symbolthema** in abgeschotteten Sitzungen mit leerer Konfiguration:
  Mit der Vorgabe der Querencia-Sitzung zeigen Panel, Arbeitsfläche und
  Dateien „Querencia“, ohne die Vorgabe GNOME-Human; eine eigene Wahl geht
  vor; fehlt das Thema „Querencia“, bleibt es bei GNOME-Human; wird die
  eigene Wahl zur Laufzeit zurückgesetzt, wechseln sie zu „Querencia“. Dazu
  394 automatische Tests.
- **Software** gegen die echten Kataloge eines Ubuntu 26.04: vorher
  2649 Komponenten mit Remmina doppelt, nachher 2647 ohne Doppel; die Suche
  „remmina“ findet einen Treffer, GIMP steht wieder in der Liste. Der
  Katalog hat 50 automatische Tests, Software 63; die Oberfläche wurde in
  abgeschotteten Läufen geprüft.
- Statische Paketprüfung (304 bestanden), Lintian ohne Fehler,
  Probe-Installation in einer abgeschotteten Kopie des Systems (96
  Prüfungen bestanden, mit italienischer Systemsprache 103), Italienisch,
  Spanisch und Französisch in allen 18 Paketen mit Texten vollständig, ein
  Kontrollbau ergab dieselben Pakete.
- **Upgrade** in einer abgeschotteten Kopie des Systems: von Alpha 3.5 mit
  Schnatter (167 Prüfungen bestanden), ohne Schnatter (154) und von Alpha
  3.4 mit Schnatter (167): nichts entfernt, nichts zurückgehalten, keine
  Rückfragen.
- **In einer virtuellen Maschine:** Alpha 3.5 mit Schnatter und
  Anmeldebildschirm aus der veröffentlichten Quelle; vorher zeigten Panel,
  Arbeitsfläche und Dateien GNOME-Human, und Software fand Remmina zweimal.
  Dann das Upgrade auf 3.6: 4 Querencia-Pakete aktualisiert, keins neu,
  nichts entfernt, keine Rückfragen; Prüfskript 114 bestanden (die übrige
  Meldung ist das Protokoll des laufenden Panels), Anmeldebildschirm 4 von
  4. Nach dem Ab- und Anmelden zeigen Panel, Arbeitsfläche und Dateien die
  flachen Querencia-Symbole und melden „Symbolthema Querencia (Vorgabe
  „Querencia“)“; Software findet Remmina einmal. Prüfung in der Sitzung 28
  von 29; der übrige Punkt war ein Fehler im Prüfskript selbst, berichtigt
  bestanden. Neuinstallation (392 Pakete mit `locales-all` und
  `ubuntu-drivers-common`, kein Schnatter): Prüfskript 113 von 113, Sitzung
  wie oben, Dateien mit Querencia-Symbolen, Remmina einmal.
- Nicht geprüft, wie bei Alpha 3.5: ein echter
  Treiberwechsel mit Neustart, echte NVIDIA-, AMD- oder Intel-Karten,
  Rechner mit zwei Grafikkarten, Secure Boot, der Anmeldebildschirm auf
  Spanisch und Französisch in der virtuellen Maschine, echte Hardware.

## Lizenzen und Herkunft

Wie Alpha 3.5. Name und Logo „Querencia“ sind keine freien Inhalte.

Copyright 2026 Querencia Desktop contributors.
