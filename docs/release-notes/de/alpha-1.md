# Querencia Desktop – Alpha 1

**Stand:** 20.10.2026, 22:30 · **Status:** interne Alpha, nicht
veröffentlicht · Werte mit „offen“ sind noch nicht belegt oder nicht
entschieden; „in Arbeit“ heißt: gebaut oder im Bau, aber weder in der
Entwicklungsumgebung aktiv noch im Paketsatz.

Querencia Desktop ist eine klassische Desktopumgebung im Stil von GNOME 2
(Ubuntu 10.04) für Wayland: Fensterverwalter labwc 0.9.8, zwei Panels, eine
Arbeitsfläche mit Symbolen und eigene Programme in Rust und GTK 4 ohne
libadwaita. Die Oberfläche ist deutsch, die meisten Programme gibt es auch auf
Englisch. Alpha 1 ist die erste Testfassung für Ubuntu 26.04 („resolute“):
20 Debian-Pakete, die neben einem vorhandenen Ubuntu Desktop installiert
werden können.

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Keine
> Sicherheits- oder Datenverlustgarantie. Erst auf einer virtuellen Maschine
> mit Snapshot ausprobieren.

## Neu in Alpha 1

Gegenüber dem Entwicklungsstand vom 19.10.2026:

- **Mitteilungszentrale** (Benachrichtigungen 0.2.0): Meldungen bleiben in
  einem Verlauf erhalten, auch über eine Neuanmeldung hinweg; Aufruf über
  Anwendungen → Zubehör → Mitteilungszentrale.
- **Systemeinstellungen 0.1.0** auf Deutsch und Englisch, mit dem neuen
  Bereich **Sprache und Region** und **mehreren Tastaturbelegungen**.
- **Panel:** Die Fensterliste zeigt nur die Fenster der aktuellen
  Arbeitsfläche; im Menü System gibt es **Bildschirm sperren** (Strg+Alt+L).
  Abmelden und Ausschalten laufen über den Sitzungsdialog, auch im Paket.
- **Vollbild** für das aktive Fenster mit **Super+F** oder **Alt+F11**.
- **Querencia Archiv 0.1.0**, eine Archivverwaltung (Archive öffnen,
  anzeigen, entpacken, erstellen).
- **Querencia Dokumente 0.1.0**, ein PDF-Betrachter.
- **Symbole 0.6** mit eigenem Symbol für Dokumente. Der Bildbetrachter
  (0.2.2) steht im Menü unter „Grafik“.
- **Anmeldebildschirm als Paket** (`querencia-anmeldung` 0.1.1, optional,
  siehe unten).
- Querencia Software 0.1.3 prüft die Netzwerkverbindung selbst und erklärt,
  warum PackageKit nicht installiert, statt still „offline“ zu melden.
- Neuanmeldung direkt nach dem Abmelden ohne schwarzen Bildschirm; Programme
  aus dem Menü erscheinen auch neben GNOME sofort (Portale korrigiert).

## Versionen

### Im Paketsatz Alpha 1

Paketsatz vom 20.10.2026 (20 Pakete), gebaut aus dem Stand, der am selben
Abend in der Entwicklungsumgebung aktiv war.

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha2-5 | Metapaket: zieht alle Bestandteile nach |
| labwc | 0.9.8-0querencia4 | Backport des Fensterverwalters (Ubuntu 26.04 liefert 0.9.3) |
| querencia-session | 0.1.0~alpha6-1 | Sitzungsstarter 2.1, labwc-Vorgaben, Portal- und gsettings-Vorgaben |
| querencia-shell | 0.1.0~alpha5-1 | Panel, Arbeitsfläche, Lautstärke, Netzwerk, Tastenkürzel-Übersicht (Super+?), Thema Querencia-Klassisch, Hintergründe |
| querencia-sitzung | 0.1.3-2 | Sitzung 0.1.3: Sperrbildschirm, Sitzungsdialog, polkit-Agent |
| querencia-benachrichtigungen | 0.2.0-1 | Benachrichtigungen 0.2.0 mit Mitteilungszentrale |
| querencia-einstellungen | 0.1.0-1 | Systemeinstellungen 0.1.0 |
| querencia-symbole | 0.6-1 | Programmsymbole und Symbolthema „Querencia“ |
| querencia-files | 0.1.0~alpha4-1 | Querencia Files, Stand QF-0o-3 (Dateiverwaltung, Fork von Strata) |
| querencia-terminal | 0.2.0-1 | Querencia Terminal 0.2.0 |
| querencia-editor | 0.2.1-1 | Texteditor 0.2.1 |
| querencia-bilder | 0.2.2-1 | Bildbetrachter 0.2.2 |
| querencia-dokumente | 0.1.0-2 | PDF-Betrachter 0.1.0 |
| querencia-archiv | 0.1.0-1 | Archivverwaltung 0.1.0 |
| querencia-rechner | 0.1.3-1 | Taschenrechner 0.1.3 |
| querencia-systemmonitor | 0.1.2-1 | Systemüberwachung 0.1.2 |
| querencia-dateisuche | 0.1.3-1 | Nach Dateien suchen 0.1.3 |
| querencia-screenshot | 0.2.8-2 | Bildschirmfoto 0.2.8 mit Editor und Fensterwahl |
| querencia-software | 0.1.3-1 | Programme installieren über PackageKit, 0.1.3 |
| querencia-anmeldung | 0.1.1-1 | Anmeldebildschirm (greetd und ReGreet 0.5.0), optional |

Dazu aus dem Ubuntu-Archiv: Schrift DejaVu Sans und Mauszeiger DMZ-White.

`querencia-anmeldung` **0.1.1-2** mit der Abhängigkeit `accountsservice`
ist **in Arbeit** und ersetzt 0.1.1-1 vor der Freigabe (siehe Installation).

### In Arbeit (nicht in Alpha 1)

| Bestandteil | Fassung | Was sich ändert |
|---|---|---|
| Querencia Terminal | 0.3.0 | Reiter (Strg+Umschalt+T, Reiterleiste, Kontextmenü) |
| Panel | Stand G2-AL | Knopf „Arbeitsfläche anzeigen“ unten im Panel (Super+D), Symbol der Mitteilungszentrale im Panel |
| Thema | 0.2 | dunkle Variante „Querencia-Klassisch-Dunkel“ |
| Querencia Files | Stand QF-0p | Querencia-Symbol statt Strata-Logo im Info-Dialog |
| Bildbetrachter | 0.2.3 | Info-Fenster beim zweiten Öffnen wieder mit Titelleiste |
| Systemeinstellungen | 0.1.1 | eigene Sicherungsdateien mit Begrenzung, Zurückstellen ohne Reste in der labwc-Konfiguration |
| querencia-anmeldung | 0.1.1-2 | Abhängigkeit `accountsservice` |
| Signierte APT-Quelle | – | Bezug der Pakete über `dl.querencialinux.org/apt` |

## Installation

Voraussetzung: Ubuntu 26.04 (Desktop- oder Server-Abbild), ein Benutzer mit
sudo-Rechten, Netzzugang zum Ubuntu-Archiv.

> **Noch nicht verfügbar.** Die Pakete kommen über eine signierte
> APT-Quelle. Sie **folgt mit der APT-Quelle** unter
> `dl.querencialinux.org/apt`; bis dahin funktionieren die Befehle zum
> Einbinden der Quelle nicht, und dieser Abschnitt beschreibt den geplanten
> Weg.

1. **Quelle einbinden:** folgt mit der APT-Quelle (Signierschlüssel
   „Querencia Desktop Archive Signing Key“).

2. **Installieren:**

   ```bash
   sudo apt update
   ```

   ```bash
   sudo apt install querencia-desktop
   ```

   apt installiert dabei auch die empfohlenen Pakete (Recommends): PipeWire
   für den Ton, NetworkManager, Avahi und wsdd für die Netzwerkansicht in
   Files, das GTK-Portal und weitere. Auf einem **Server-Abbild** sind das
   **rund 360 Pakete** aus dem Ubuntu-Archiv, auf einem Ubuntu Desktop nur
   wenige. Mit `--no-install-recommends` bleibt die Installation schlank;
   dann fehlen Ton, das Verbinden über das Netzwerk-Applet, die
   Netzwerkansicht in Files und `notify-send`.

3. **Neu starten.** GDM liest neue Sitzungen nur beim Start: Erst nach einem
   Neustart steht „Querencia Desktop“ im Zahnrad unten rechts im
   Anmeldebildschirm.

4. **Anmelden:**
   - mit **GDM** (Ubuntu Desktop): Benutzer wählen, am Zahnrad „Querencia
     Desktop“ wählen, anmelden;
   - **ohne grafischen Anmeldebildschirm** (Server-Abbild): an der Textkonsole
     anmelden und `querencia-session` eingeben.

### Server-Abbild: Netz über NetworkManager

Auf einem Ubuntu Server verwaltet netplan das Netz über systemd-networkd.
NetworkManager ist dann zwar installiert, verwaltet aber nichts. Folgen:
Das Netzwerk-Applet zeigt nur den Zustand („Kein Netzwerkgerät“), und
PackageKit hält das System für offline. **Querencia Software kann dann nichts
installieren** und zeigt einen klaren Hinweis mit Abhilfe.

Abhilfe: NetworkManager als netplan-Renderer einrichten (`renderer:
NetworkManager` unter `network:` in `/etc/netplan/`). Auf Cloud- und
VM-Abbildern mit cloud-init und dracut reicht diese eine Zeile allein nicht:
Dort hat das Projekt ein geprüftes Umstellskript (`nm-umstellen.sh`, mit
`pruefen`, `umstellen` und `zurueck`), das die Adresse behält. **Bezugsweg
des Skripts: offen.**

### Neben GNOME (Ubuntu Desktop)

Querencia **ersetzt GNOME nicht**, es steht daneben. Geprüft auf Ubuntu 26.04
Desktop:

- Die Installation entfernt nichts von Ubuntu Desktop. **GDM bleibt der
  Anmeldebildschirm** und bietet nach dem Neustart „Ubuntu“ und „Querencia
  Desktop“ an. Wechsel in beide Richtungen über Abmelden und Anmelden
  funktionieren.
- In der Querencia-Sitzung laufen keine GNOME-Sitzungsdienste.
- Die **Sitzungswerkzeuge** (Bildschirmfoto, Einstellungen, Tastenkürzel,
  Lautstärke, Sitzungsdialog, Mitteilungszentrale) erscheinen **nur in
  Querencia**. Die übrigen Querencia-Programme sind auch in GNOME sichtbar.
- **Fünf Dateitypen**, für die Ubuntu keinen Standard festlegt (Markdown,
  JSON, XML, Python, Shell-Skripte), öffnet GNOME danach mit Querencia Editor.
  Ändern lässt sich das in GNOME unter Einstellungen → Apps →
  Standard-Apps oder über „Öffnen mit“.
- **Einstellungen werden geteilt:** Querencia und GNOME lesen dieselben
  gsettings-Werte. Ändert man in Querencia das Symbolthema, gilt es auch in
  GNOME; umgekehrt zeigt Querencia auf Ubuntu Desktop die Yaru-Symbole, weil
  Ubuntu sie als Benutzerwert setzt. Getrennte Einstellungen für die
  Querencia-Sitzung sind ein Folgepunkt.

### Eigener Anmeldebildschirm (optional)

`querencia-anmeldung` ist ein Anmeldebildschirm im Querencia-Aussehen
(greetd mit ReGreet). Das Metapaket schlägt ihn nur vor (Suggests); er wird
nicht automatisch installiert. **Empfohlen bleibt GDM.**

- Installieren: `sudo apt install querencia-anmeldung`. Neben GDM bleibt GDM
  Standard, bis man umschaltet:

  ```bash
  sudo dpkg-reconfigure querencia-anmeldung
  ```

  Die Umschaltung wirkt nach dem nächsten Neustart; dieselbe Frage schaltet
  zurück.
- Er zeigt standardmäßig **nur die Querencia-Sitzung**. Andere Sitzungen
  lassen sich in `/etc/querencia/greetd/sitzungen.conf` freigeben. **GNOME
  läuft unter diesem Anmeldebildschirm ohne Bildschirmsperre:** gnome-shell
  koppelt die Sperre an GDM. Das gilt für jeden fremden Anmeldebildschirm und
  ist kein Querencia-Fehler.
- Voraussetzung ist `accountsservice`. Ab **0.1.1-2** ist es eine
  Abhängigkeit des Pakets; mit 0.1.1-1 bleibt der Bildschirm auf einem
  Server-Abbild ohne `accountsservice` schwarz.
- Die Oberfläche des Anmeldebildschirms ist englisch, die Uhr ebenfalls.

### Entfernen

```bash
sudo apt purge 'querencia-*' labwc
```

```bash
sudo apt autoremove --purge
```

Erst `autoremove --purge` entfernt auch die mitinstallierten Pakete. Sonst
bleibt unter anderem **wsdd-server als Netzwerkdienst aktiv**. Auf Ubuntu
Desktop ist das System danach im Paketbestand wieder wie vor der
Installation (geprüft). Ubuntus eigenes labwc 0.9.3 lässt sich bei Bedarf
wieder installieren.

Bekannte Reste:

- Benutzerdaten bleiben, wie unter Debian üblich: `~/.config/querencia/`,
  `~/.local/state/querencia/`, `~/.local/share/strata/`.
- War `querencia-anmeldung` installiert, bleibt nach dem Entfernen **greetd
  mit einer Textanmeldung** als Anmeldedienst stehen, wenn vorher keiner
  eingerichtet war (Server-Abbild). Neben GDM kehrt GDM zurück. Die
  Bereinigung kommt mit `querencia-anmeldung` 0.1.2.

## Bekannte Grenzen

Die vollständige Liste steht im Benutzerhandbuch unter
[Bekannte Einschränkungen](../../benutzerhandbuch/de/bekannte-einschraenkungen.md).
Die wichtigsten in Alpha 1:

- **Anmeldebildschirm englisch:** ReGreet zeigt Knöpfe und Uhr auf Englisch.
- **Alt+Druck in VMs:** Das Bildschirmfoto des aktiven Fensters kam in
  virtuellen Maschinen nicht an; an echter Hardware ungeprüft.
- **Nebenfenster ohne Titelleiste:** Ein Fenster, das ein Programm beim
  Schließen nur versteckt, erscheint beim zweiten Öffnen ohne Titelleiste
  (z. B. die Bildinformationen im Bildbetrachter). Ursache liegt im
  Zusammenspiel von GTK 4.22 und labwc; die Behebung in Bilder 0.2.3 läuft.
- **Terminal ohne Reiter** bis Querencia Terminal 0.3.0.
- **Einstellungen und rc.xml:** Ändern und Zurückstellen in den Bereichen
  Tastatur, Maus, Fensterdesign und Arbeitsflächen lässt die Standardwerte
  ausdrücklich in `~/.config/querencia/labwc/rc.xml` stehen, und jedes
  Übernehmen legt eine Sicherungsdatei `rc.xml.vorher-…` an. Die Wirkung ist
  richtig; die Bereinigung kommt mit Einstellungen 0.1.1.
- **Netzwerk:** Verbinden und Trennen im Netzwerk-Applet geht nur, wenn
  NetworkManager das Netz verwaltet; sonst zeigt es nur den Zustand (siehe
  Server-Abbild).
- **Firefox als Snap** übernimmt das GTK-Thema nicht.
- **Keine dunkle Darstellung:** Sie kommt mit dem Thema 0.2.
- **Neben GNOME:** geteilte gsettings-Werte und Querencia Editor für fünf
  Dateitypen in GNOME (siehe oben); im Querencia-Menü stehen auf Ubuntu
  Desktop auch die GNOME-Programme, teils mit gleichem Namen.
- **Files:** Info-Dialog zeigt noch das Strata-Logo (Behebung in Arbeit);
  Rechner können in der Netzwerkansicht doppelt erscheinen.
- Panel und Arbeitsfläche sind einmal (18.10.) ohne erkennbare Ursache
  beendet worden. Abhilfe: Strg+Alt+Entf → Abmelden, neu anmelden.

## Geprüft

- **Pflichtprobe auf frischem Ubuntu 26.04** mit dem Paketsatz Alpha 1,
  bestanden am 20.10.2026 um 22:18: Installation, Sitzung, alle Programme,
  Abmelden mit sofortiger Neuanmeldung, Sperren, polkit, Portale und Sprache.
  - Anmeldung an der **Textkonsole (tty1)**: bestanden;
  - Anmeldung über **GDM**: bestanden;
  - Anmeldung über **querencia-anmeldung**: bestanden mit
    nachinstalliertem `accountsservice`; ohne ihn schwarzer Bildschirm
    (daher 0.1.1-2). Nach dem Entfernen bleibt greetd stehen (siehe oben).
  - Messwerte: Einstellungs-Portal antwortet in 9–11 ms, Terminal aus dem
    Menü in höchstens 2,2 s, Neuanmeldung nach dem Abmelden in unter 10 s.
  - Nicht geprüft: Alt+Druck, Kopieren und Einfügen im Terminal, Kopieren in
    Files, Speichern im Editor, echte Hardware, SMB-Freigaben.
- **Neben Ubuntu Desktop** (Ubuntu 26.04.1 mit GNOME 50): bestanden.
  Installation entfernt nichts, GDM startet beide Sitzungen, Wechsel je
  zweimal in beide Richtungen, nach dem Entfernen ist der Paketbestand wieder
  wie vorher. Die Befunde (geteilte gsettings, Editor für fünf Dateitypen,
  GNOME-Programme im Querencia-Menü, wsdd-server nach dem Entfernen) sind
  oben beschrieben und in Arbeit.
- **Prüflauf QREL-06, Teil A** (Werkstatt, alle Programme in der laufenden
  Entwicklungssitzung): **63 PASS, 3 FAIL, 8 NOT TESTED**. Die drei FAIL:
  - Bildbetrachter 0.2.1: Bildinformationen beim zweiten Öffnen ohne
    Titelleiste (siehe Bekannte Grenzen; Behebung in Bilder 0.2.3);
  - Terminal 0.2.0: keine Reiter – eine fehlende Funktion, keine Regression
    (Terminal 0.3.0);
  - Einstellungen 0.0.9: Zurückstellen lässt die labwc-Konfiguration nicht
    byte-gleich zurück und legt Sicherungsdateien an (Einstellungen 0.1.1).

  Sechs der acht NOT TESTED betreffen Programme, die während des Laufs durch
  neuere Fassungen ersetzt wurden (Panel, Bildbetrachter, Software,
  Benachrichtigungen, Symbole); sie gehen in Teil B. Zwei Schritte ließ der
  Prüfer aus Vorsicht oder wegen eines Fehlklicks aus. **Teil B: offen.**
- Jedes Programm hat Unit-Tests und abgeschottete GUI-Läufe (eigener
  Compositor, eigenes Profil, Deutsch und Englisch, mehrere Auflösungen).
  Der Paketsatz besteht die statische Paketprüfung und Lintian ohne Fehler.

## Lizenzen und Herkunft

- **Programme:** GPL-3.0-or-later, auch Querencia Screenshot.
- **Querencia Files:** MIT wie der Ursprung Strata; die PDF-Vorschau linkt
  gegen Poppler (GPL).
- **Bibliotheken von Querencia Software:** MIT oder Apache-2.0.
- **Dokumentation, Symbole und Symbolthema:** CC-BY-SA-4.0; die Werkzeuge
  des Symbol-Repos GPL-3.0-or-later.
- **Anmeldebildschirm:** ReGreet 0.5.0 aus der Upstream-Quelle, GPL-3.0.
- **Hintergründe:** eigene Bilder ohne Logo unter CC-BY-SA-4.0. Die vier
  Motive sind KI-erzeugt; sie werden erst veröffentlicht, wenn die
  Nutzungsbedingungen des Erzeugers die Weitergabe unter CC-BY-SA erlauben.
  Rein KI-erzeugte Bilder sind in manchen Rechtsordnungen womöglich nicht
  urheberrechtlich geschützt; die Lizenzangabe ist dann ein Hinweis.
- **Name und Logo „Querencia“** sind keine freien Inhalte; es gilt die
  Markenregel des Projekts, auch für den Logo-Teil der Hintergründe.
- **Signierschlüssel der Paketquelle:** „Querencia Desktop Archive Signing
  Key <archive@querencialinux.org>“.

Copyright 2026 Querencia Desktop contributors.

