# Querencia Desktop – Alpha 3.4

**Stand:** 27.10.2026 · **Status:** in der APT-Quelle seit 27. Oktober 2026, 20:56

Alpha 3.4 bringt in den Systemeinstellungen eine Seite „Treiber“ für die
Grafikkarte. Querencia Dateien kann jetzt Schritte rückgängig machen, auch
im Dateiinhalt suchen, die Reiter beim nächsten Start wiederherstellen und
Archive „Hier entpacken“. Der Anmeldebildschirm erklärt ein abgelaufenes
Passwort. Sperrbildschirm, Lautstärkeregler und Tastenkürzel-Hilfe gibt es
jetzt in allen fünf Sprachen. Es sind 24 Debian-Pakete für Ubuntu 26.04
(„resolute“) aus derselben signierten APT-Quelle; 6 davon sind neu gebaut.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren. Querencia Dateien selbst trägt die Stufe „Beta“.

## Neu in Alpha 3.4

- **Seite „Treiber“ (Querencia Einstellungen 0.2.0).** Zu finden unter
  System → Systemverwaltung → „Treiber“ oder in den Systemeinstellungen. Die
  Seite zeigt die Grafikkarte, den geladenen Kerneltreiber, den
  OpenGL-Renderer und ob diese Sitzung Software-OpenGL nutzt. Darunter
  stehen die Treiber, die Ubuntu für die Karte kennt, je mit Zustand („in
  Gebrauch“, „installiert, in Gebrauch nach einem Neustart“, „verfügbar“,
  „nicht installiert“).
  - **Vorgabe ist der freie Treiber** („Freier Treiber nouveau
    (Querencia-Vorgabe)“). Der NVIDIA-Treiber ist eine Wahl, etwa
    „NVIDIA-Treiber 615 mit offenen Kernelmodulen“.
  - **Wechseln:** Treiber wählen → „Änderungen anwenden“ → Rückfrage mit
    der Liste der Pakete → Passwort. Die Pakete kommen über PackageKit, wie
    in Querencia Software. Zurück zum freien Treiber entfernt die Seite den
    ganzen NVIDIA-Zweig.
  - **Danach neu starten:** Der neue Treiber gilt erst nach einem Neustart.
    Die Seite sagt das und bietet „Neu starten …“ an; das öffnet die
    Rückfrage der Sitzung.
  - Die Liste kommt vom Programm `ubuntu-drivers` aus dem Paket
    `ubuntu-drivers-common`. Querencia Einstellungen empfiehlt es jetzt; das
    Upgrade installiert es mit. Fehlt es, sagt die Seite das und bietet
    „ubuntu-drivers-common installieren …“ an.
  - Bei einer NVIDIA-Karte erklärt die Seite, warum die Sitzung OpenGL mit
    dem freien Treiber auf Software (llvmpipe) stellt und dass der
    NVIDIA-Treiber das überflüssig macht.
- **Querencia Dateien 0.3.0:**
  - **Rückgängig und Wiederholen** (Strg+Z, Umschalt+Strg+Z; das Menü
    Bearbeiten sagt, was zurückgenommen wird). Das geht für Verschieben,
    Umbenennen, In den Papierkorb, Kopieren, Ordner anlegen und Dokument
    anlegen. Rückgängig nach Kopieren legt die Kopien in den Papierkorb,
    ohne Rückfrage; das Menü sagt „(in den Papierkorb)“. Endgültiges Löschen
    und „Papierkorb leeren“ lassen sich nicht rückgängig machen. Jedes
    Fenster hat eine eigene Liste für alle seine Reiter, bis 50 Schritte.
  - **Suche auch im Dateiinhalt:** In der Suchleiste (Strg+F) gibt es den
    Schalter „Auch Dateiinhalt“ (Vorgabe aus). Dann findet die Suche auch
    Textdateien bis 10 MB, in denen alle Wörter vorkommen. Die Spalte
    „Fundstelle“ zeigt die erste passende Zeile, der Tooltip ihre Nummer.
  - **Reiter beim Start wiederherstellen** (Bearbeiten → Einstellungen →
    Verhalten, Vorgabe an): Ein Start ohne Ordner öffnet die Reiter des
    zuletzt geschlossenen Fensters wieder. Nicht erreichbare Orte werden
    übersprungen.
  - **„Hier entpacken“** im Kontextmenü von Archiven, wenn die
    Archivverwaltung installiert ist (sie ist es mit dem Metapaket). Die
    Archivverwaltung entpackt jedes gewählte Archiv neben sich und zeigt
    Fortschritt und Fragen selbst.
- **Abgelaufenes Passwort verständlich** (`querencia-anmeldung` 0.1.4,
  wahlweise): Der Anmeldebildschirm sagt jetzt in der Systemsprache, dass
  das Passwort abgelaufen ist, und wie man an der Textkonsole ein neues setzt
  (Strg+Alt+F1, zurück mit Strg+Alt+F7). Vorher stand dort
  `Pam_acct_mgmt: NEW_AUTHTOK_REQD`. Im Anmeldebildschirm selbst lässt sich
  das Passwort mit greetd 0.10 nicht ändern.
- **Sprachreste geschlossen:** Der Sperrbildschirm (Querencia Sitzung
  0.1.10), das Fenster des Lautstärkereglers (0.1.2) und die
  Tastenkürzel-Hilfe mit ihrem Starter (0.2.3) gibt es jetzt auch auf
  Italienisch, Spanisch und Französisch. Bisher waren sie fest deutsch.

Was Alpha 3.3 brachte (fünf Sprachen, Infobereich), steht in den
[Hinweisen zu Alpha 3.3](alpha-3.3.md).

## Versionen

Paketsatz vom 27.10.2026 (24 Pakete).

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.4-1 | Metapaket, Versionsdatei „Alpha 3.4“; Abhängigkeiten unverändert |
| querencia-einstellungen | 0.2.0-1 | **geändert:** Seite „Treiber“ mit eigenem Menüeintrag; **neu:** empfiehlt `ubuntu-drivers-common` |
| querencia-dateien | 0.3.0-1 | **geändert:** Rückgängig, Suche im Dateiinhalt, Reiter wiederherstellen, „Hier entpacken“ |
| querencia-shell | 0.1.0~alpha12-1 | **geändert:** Tastenkürzel-Hilfe 0.2.3 und Lautstärkeregler 0.1.2 in fünf Sprachen; Panel 0.4.0 und Arbeitsfläche 0.3.1 unverändert |
| querencia-sitzung | 0.1.10-1 | **geändert:** Sperrbildschirm in fünf Sprachen |
| querencia-anmeldung | 0.1.4-1 | **geändert:** Anmeldebildschirm, klare Meldung bei abgelaufenem Passwort, optional |
| querencia-software | 0.1.7-1 | Software-Center (unverändert seit Alpha 3.3) |
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
| querencia-webhuelle | 0.3.0-1 | Übergangspaket zu Schnatter (unverändert seit Alpha 3.2) |
| querencia-files | 0.2.0-1 | Übergangspaket aus Alpha 3 (unverändert) |
| querencia-session | 0.1.0~alpha10-1 | Sitzungsstarter (unverändert seit Alpha 3) |
| querencia-symbole | 0.8-1 | Programmsymbole und Symbolthema (unverändert seit Alpha 3) |
| querencia-hintergruende | 0.2-1 | 16 Hintergründe (unverändert seit Alpha 2) |
| labwc | 0.9.8-0querencia5 | Backport des Fensterverwalters (unverändert seit Alpha 2) |

Von Software bis labwc sind die Pakete byte-gleich mit Alpha 3.3.

Prüfsumme der Paketliste (SHA256SUMS): `97f55df08e102a5b35e3282e0f7f8c4e38e78dbcdab85b2549bffe4698f9a5aa`.

## Aktualisieren von Alpha 3.3

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` genügt ebenfalls. APT aktualisiert 5 Pakete, mit dem
Anmeldebildschirm 6, und installiert `ubuntu-drivers-common` (mit
`python3-xkit`) neu. Dafür lädt es rund 29 MB herunter (mit
Anmeldebildschirm). Entfernt wird nichts, und es gibt keine Rückfrage zu
Konfigurationsdateien. In einer virtuellen Maschine dauerte das Upgrade rund
8 Sekunden, ohne die Zeit zum Herunterladen. Danach
abmelden und neu anmelden.

Ein Upgrade von Alpha 3.2 geht genauso; was dabei sonst geschieht, steht
in den [Hinweisen zu Alpha 3.3](alpha-3.3.md#aktualisieren-von-alpha-32-oder-31).
Für ältere Stände siehe dort.

## Neu installieren

Unverändert: Quelle einbinden, `sudo apt install querencia-desktop`, neu
starten, am Zahnrad „Querencia Desktop“ wählen (siehe
[Alpha 1, Installation](alpha-1.md#installation)). Fingerabdruck des
Signierschlüssels: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
`ubuntu-drivers-common` kommt dabei mit, Schnatter nicht. Auf einem
frischen Ubuntu-26.04-Server-Abbild installiert APT 392 Pakete.

## Bekannte Grenzen

Weiter gültig aus Alpha 3 bis 3.3 (siehe dort), soweit oben nicht als
behoben genannt. Davon besonders:

- **Seite „Treiber“:**
  - Ein Wechsel braucht `ubuntu-drivers-common`, eine Netzverbindung und
    das Passwort, und er wirkt erst nach einem Neustart.
  - In einer virtuellen Maschine mit Software-Rendering (llvmpipe) zeigt
    die Seite bei „Diese Sitzung:“ fälschlich „OpenGL auf der Grafikkarte“.
    Der Renderer darüber nennt richtig llvmpipe. Das berichtigt eine spätere
    Fassung der Einstellungen.
  - Die Seite zeigt nur, was `ubuntu-drivers` nennt. Mit einer echten
    NVIDIA-Karte ist der Wechsel noch nicht geprüft, ebenso wenig Rechner
    mit zwei Grafikkarten (etwa Notebooks mit Intel und NVIDIA) und Secure
    Boot. Für Secure Boot installiert die Seite das von Canonical signierte
    Modulpaket mit; eine Abfrage für einen eigenen MOK-Schlüssel gibt es
    nicht.
  - Kommt nach dem Wechsel kein Bild, an der Textkonsole (Strg+Alt+F3)
    anmelden und die NVIDIA-Pakete wieder entfernen. Deshalb vorher einen
    Snapshot der virtuellen Maschine anlegen.
- **Querencia Dateien ist eine Beta.**
  - Rückgängig gilt nur für Vorgänge dieses Fensters und nur, bis Querencia
    Dateien geschlossen wird. Endgültiges Löschen und „Papierkorb leeren“
    lassen sich nicht zurücknehmen; was beim Einfügen ersetzt wurde, kommt
    nicht zurück. „Hier entpacken“ steht nicht in der Liste zum
    Rückgängigmachen.
  - Die Suche im Dateiinhalt hat keinen Index (große Ordner dauern), liest
    keine Netzwerkorte und keine Dokumente wie odt oder pdf.
  - Wiederhergestellte Reiter merken nur den Ordner, nicht Ansicht, Zoom
    oder Verlauf.
  - Eine Spaltenansicht und einen Ordnerbaum in der Seitenleiste gibt es
    nicht; aus den Suchergebnissen lässt sich noch nicht kopieren oder
    ziehen.
- **Anmeldebildschirm:** Ein abgelaufenes Passwort lässt sich nur an der
  Textkonsole ändern, nicht im Anmeldebildschirm. Er kennt weiter nur
  Deutsch und Englisch; bei Italienisch, Spanisch oder Französisch als
  Systemsprache zeigt er Englisch.
- **Sprachen:** Im Italienischen bleibt der Tastenname „Return“ in
  Menükürzeln englisch (z. B. „Alt+Return“ im Bildbetrachter). Texte von GTK
  selbst (Dateidialog, einige Knöpfe) folgen dem Sprachpaket des Systems,
  `language-pack-gnome-<xx>`.
- **Infobereich:** wie in Alpha 3.3 (kein XEmbed, passive Symbole
  verborgen, mit Webex, Nextcloud oder Discord selbst noch nicht geprüft).
- **Schnatter** zeigt noch kein Symbol im Infobereich.
- **Netzwerk teils ungeprüft:** Windows-Freigaben, Zertifikatsfragen bei
  sicheren Verbindungen und echte Netzlaufwerke sind ungeprüft.
- **Software-OpenGL** mit dem freien Treiber kostet Rechenzeit und
  Speicher; Programme, die der Fensterverwalter selbst startet (z. B. über
  Tastenkürzel), bekommen es nicht.
- **Nicht auf echter Hardware geprüft**, nur in virtuellen Maschinen und in
  abgeschotteten Kopien des Systems.

## Fehler melden

Wie Alpha 3, im Fehlertracker des Projekts,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Geprüft

- Jede Quelle ist ein getaggter Stand: die Einstellungen aus
  `einstellungen/0.2.0`, Querencia Dateien aus `dateien/0.3.0`, der
  Anmeldebildschirm aus `anmeldung/0.1.4`, die Sitzung aus `sitzung/0.1.10`.
- **Seite „Treiber“** in abgeschotteten Läufen mit nachgebildeten
  Grafikkarten (NVIDIA mit freiem und mit NVIDIA-Treiber, AMD, Intel, keine
  Karte, ohne `ubuntu-drivers`) und einer Attrappe von PackageKit: 256
  Prüfungen bestanden, in Deutsch und Englisch, zwei Bildschirmgrößen, hell
  und dunkel; Wechsel hin und zurück, abgelehntes Passwort und gesperrte
  Paketverwaltung; die 14 übrigen Seiten wie vorher; 155 automatische
  Tests.
- **Querencia Dateien 0.3.0** in abgeschotteten Läufen: Rückgängig je Art,
  Inhaltssuche, Reiter und „Hier entpacken“ in eigenen Szenarien, alle
  bestanden; 701 automatische Tests des Quellbaums.
- **Anmeldebildschirm 0.1.4** in einer abgeschotteten Probe mit echtem
  greetd und echter Passwortprüfung: abgelaufenes Passwort in Deutsch und
  Englisch mit der neuen Meldung, falsches und gültiges Passwort wie
  vorher; 96 Konfigurationsfälle bestanden.
- **Sprachen:** Sperrbildschirm, Lautstärkeregler und Tastenkürzel-Hilfe
  in abgeschotteten Läufen in fünf Sprachen mit Bildschirmfotos;
  Kataloge, Starter und Beschreibungen in allen Paketen 18 von 18.
- Statische Paketprüfung (304 bestanden), Lintian ohne Fehler,
  Probe-Installation in einer abgeschotteten Kopie des Systems (96
  Prüfungen bestanden, mit italienischer Systemsprache 103, mit
  Bildschirmfotos), ein Kontrollbau ergab dieselben Pakete.
- **Upgrade** in einer abgeschotteten Kopie des Systems: von Alpha 3.3 mit
  Schnatter (168 Prüfungen bestanden), ohne Schnatter (155) und von Alpha
  3.2 mit Schnatter (169): nichts entfernt, nichts zurückgehalten, keine
  Rückfragen; `ubuntu-drivers-common` neu.
- **In einer virtuellen Maschine:** Alpha 3.3 mit Schnatter und
  Anmeldebildschirm aus der veröffentlichten Quelle, dann das Upgrade auf
  3.4: 6 Querencia-Pakete aktualisiert, `ubuntu-drivers-common` neu, nichts
  entfernt, keine Rückfragen, eigene Einstellungen erhalten; Sitzung 28 von
  28, Anmeldebildschirm 3 von 3, Prüfskript 107 bestanden (die drei übrigen
  Meldungen betreffen nicht das Upgrade: zwei verglichen mit einem Stand vor
  der Installation des Anmeldebildschirms, eine ist das Protokoll des
  laufenden Panels). Sichtproben: Seite „Treiber“, Rückgängig,
  Inhaltssuche, Reiter und „Hier entpacken“ in Dateien, abgelaufenes
  Passwort in Deutsch und Englisch samt Wechsel an der Textkonsole und
  Anmeldung mit dem neuen Passwort, Sperrbildschirm, Lautstärkeregler und
  Tastenkürzel-Hilfe auf Italienisch. Neuinstallation (392 Pakete mit
  `locales-all` und `ubuntu-drivers-common`, kein Schnatter): Prüfskript
  108 von 108, Sitzung 28 von 28.
- Nicht geprüft: ein echter Treiberwechsel mit Neustart, echte NVIDIA-,
  AMD- oder Intel-Karten, Secure Boot, der Infobereich mit Webex, Nextcloud oder Discord, Schnatter mit
  echtem Konto, echte Windows-Freigaben und Netzlaufwerke, Anmeldung über
  GDM, echte Hardware.

## Lizenzen und Herkunft

Wie Alpha 3.3. `ubuntu-drivers-common` und die NVIDIA-Treiber sind Pakete
von Ubuntu; der NVIDIA-Treiber ist proprietär und wird nur auf Wunsch
installiert. Name und Logo „Querencia“ sind keine freien Inhalte.

Copyright 2026 Querencia Desktop contributors.
