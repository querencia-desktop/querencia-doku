# Querencia Terminal

[Zurück zum Inhalt](index.md)

**Starten:** Anwendungen → Zubehör → Querencia Terminal.

Ein schlichtes Terminal nach dem Vorbild von MATE Terminal und GNOME Terminal
2.x: ein Fenster mit Menüleiste, Reitern und der Shell des Benutzers,
Bildlaufleiste rechts.

## Was das Terminal kann

- Startet die Shell des Benutzers im Persönlichen Ordner, Größe 80×24
  Zeichen, 10 000 Zeilen Rücklauf.
- **Menüleiste** Datei · Bearbeiten · Ansicht · Reiter · Hilfe. F10 und
  Alt+Buchstabe öffnen die Menüleiste nicht, sie bleiben bei der Shell (z. B.
  für Midnight Commander oder die Befehlszeile).
- **Kopieren und Einfügen** wie in GNOME Terminal 2: Strg+Umschalt+C kopiert
  die Markierung, Strg+Umschalt+V oder Umschalt+Einfg fügt ein. Strg+C und
  Strg+V bleiben Steuerzeichen für die Shell.
- Markieren und mittlere Maustaste wie unter Linux üblich (Auswahl einfügen).
- **Kontextmenü** (Rechtsklick, Menü-Taste oder Umschalt+F10): Kopieren,
  Einfügen, Alles auswählen, Neuer Reiter, Reiter schließen.
- Jedes Starten aus dem Menü öffnet ein eigenes Fenster. Endet die Shell
  (`exit`, Strg+D), schließt sich ihr Reiter; der letzte Reiter schließt das
  Fenster.
- Oberfläche Deutsch oder Englisch.

## Reiter

| Kürzel | Wirkung |
|---|---|
| Strg+Umschalt+T | neuer Reiter |
| Strg+Umschalt+W | Reiter schließen |
| Strg+Umschalt+Q | Fenster schließen |
| Strg+Bild↑ / Strg+Bild↓ | vorheriger / nächster Reiter |
| Strg+Umschalt+Bild↑ / Strg+Umschalt+Bild↓ | Reiter nach links / rechts verschieben |
| Alt+1 bis Alt+9 | zu Reiter 1 bis 9 wechseln |

- Die **Reiterleiste** erscheint ab dem zweiten Reiter. Ansicht →
  „Reiterleiste immer anzeigen“ zeigt sie auch mit nur einem Reiter; die
  Wahl bleibt gespeichert.
- Ein **Mittelklick** auf einen Reiter schließt ihn, ein **Doppelklick** auf
  die freie Reiterleiste öffnet einen neuen. Reiter lassen sich mit der Maus
  verschieben.
- Ein neuer Reiter beginnt im Arbeitsverzeichnis des aktuellen. Der Reiter
  trägt den Titel, den die Shell setzt.
- Läuft in einem Reiter außer der Shell noch ein Programm, fragt das
  Schließen von Reiter oder Fenster nach („Dieses Terminal schließen?“ bzw.
  „Dieses Fenster schließen?“).
- Am ersten und letzten Reiter geht es nicht im Kreis weiter. Ist ein Befehl
  gerade nicht möglich (z. B. Strg+Bild↓ mit nur einem Reiter), bekommt die
  Shell die Taste.
- Hilfe → Tastenkürzel zeigt alle Kürzel des Terminals.

## Noch nicht enthalten

Suche, Profile, Schrift- und Farbwahl und der Aufruf als Standardterminal mit
einem Befehl (`-e`/`-x`). Fügt die mittlere Maustaste eine Auswahl ein, die
ein anderes Programm gesetzt hat, klappt das noch nicht immer.
