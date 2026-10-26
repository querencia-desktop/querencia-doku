# Schnatter (WhatsApp Web im eigenen Fenster)

[Zurück zum Inhalt](index.md)

**Starten:** Anwendungen → Internet → Schnatter.

Schnatter zeigt WhatsApp Web in einem eigenen Fenster mit der klassischen
Menüleiste, für alle, die am Rechner schreiben wollen, ohne einen
Browser-Reiter offen zu halten. Bis Alpha 3.1 hieß das Programm „Querencia
Webhülle“, davor „Querencia Nachrichten“.

Schnatter ist **kein Produkt von WhatsApp oder Meta** und nicht mit ihnen
verbunden. WhatsApp ist eine Marke ihres Inhabers.

## Installieren

Schnatter gehört nicht zur Standardinstallation und kommt nicht mit
`querencia-desktop`. Einzeln installieren:

```bash
sudo apt install querencia-schnatter
```

Wer die Querencia Webhülle installiert hatte, bekommt Schnatter mit dem
nächsten Upgrade (siehe [Release Notes Alpha 3.2](../../release-notes/de/alpha-3.2.md)).

## Anmelden

Beim ersten Start zeigt das Fenster die Anmeldeseite von WhatsApp Web. Die
Anmeldung bleibt erhalten, auch wenn das Fenster geschlossen wird.
**Datei → Abmelden und Daten löschen …** meldet ab und leert nach einer
Rückfrage Sitzung und Zwischenspeicher.

## Was Schnatter kann

- **Meldungen** neuer Nachrichten über die
  [Benachrichtigungen](benachrichtigungen.md); ein Klick holt das Fenster nach
  vorn. Ungelesene Nachrichten zählt der Fenstertitel mit („(3) Schnatter“).
- **Downloads** landen ohne Rückfrage im Download-Ordner, nie über einer
  vorhandenen Datei; danach kommt eine Meldung mit „Öffnen“ und „Ordner
  öffnen“.
- **Mikrofon** (Sprachnachrichten), **Kamera** und **Lesen der
  Zwischenablage:** Schnatter fragt je Art einmal und merkt sich die Antwort.
- **Fremde Links** öffnet der Standardbrowser bzw. das Mailprogramm; das
  Fenster bleibt bei WhatsApp Web.
- **Rechtschreibprüfung** in der Sprache der Oberfläche und Englisch, soweit
  die Wörterbücher installiert sind.
- **Zoom und Fenstergröße** werden gemerkt.
- Stürzt die Webseite ab, lädt das Fenster neu und sagt es.

## Menüs

| Menü | Einträge |
|---|---|
| Datei | Neu laden, Abmelden und Daten löschen …, Beenden |
| Bearbeiten | Ausschneiden, Kopieren, Einfügen, Alles auswählen, Einstellungen |
| Ansicht | Vergrößern, Verkleinern, Normale Größe, Vollbild |
| Hilfe | Hilfe, Info |

## Einstellungen

**Bearbeiten → Einstellungen:**

- **Browserkennung:** „Standard der Web-Engine (WhatsApp sieht Safari auf
  einem Mac)“ oder „Linux-Kennung ohne Seitenausnahmen“.
- **Ton:** „Töne und Sprachnachrichten abspielen“.
- **Software-Grafik:** Automatisch (nur, wo der Grafiktreiber bekanntermaßen
  versagt), An oder Aus.
- **Gespeicherte Rechte:** „Antworten vergessen“ für Mikrofon, Kamera und
  Zwischenablage.

## Tasten

| Taste | Wirkung |
|---|---|
| Strg+R, F5 | Neu laden |
| Strg+Q | Beenden |
| Strg+X, Strg+C, Strg+V, Strg+A | Ausschneiden, Kopieren, Einfügen, Alles auswählen |
| Strg+Plus, Strg+Minus, Strg+0 | Vergrößern, Verkleinern, normale Größe |
| F11 | Vollbild ein/aus |
| F1 | Hilfe |

## Umzug von der Webhülle

Beim ersten Start übernimmt Schnatter Anmeldung und Einstellungen der
Querencia Webhülle (oder, wer die Webhülle übersprungen hat, von Querencia
Nachrichten): Es benennt deren drei Ordner in `querencia-schnatter` um.
Nichts wird kopiert oder gelöscht. Läuft das alte Programm noch, sagt
Schnatter das und startet erst nach dem Schließen. Gibt es schon Ordner von
Schnatter, bleiben die alten unangetastet liegen.

Die Daten liegen danach unter `~/.local/share/querencia-schnatter`,
`~/.cache/querencia-schnatter` und `~/.config/querencia-schnatter`.

## Gut zu wissen

- **Keine Anrufe.** Die Web-Engine von Ubuntu ist ohne WebRTC gebaut.
- **Meldungen nur bei offenem Fenster.** Schließen beendet Schnatter; ein
  Symbol im Panel gibt es nicht, weil das Panel noch keinen Infobereich hat.
- Nur ein Konto je Benutzer.
- Mit echtem Konto ist Schnatter in der Test-VM nicht geprüft (siehe
  [Bekannte Einschränkungen](bekannte-einschraenkungen.md)).
