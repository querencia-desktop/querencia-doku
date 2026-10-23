# Einstieg

[Zurück zum Inhalt](index.md)

![Querencia Desktop mit geöffnetem Menü „Orte“](../bilder/de-einstieg-orte.png)

## Anmelden

Querencia Desktop ist eine eigene Sitzung. Wie man sie startet, hängt davon
ab, wie das System eingerichtet ist:

| System | So meldet man sich an |
|---|---|
| Ubuntu 26.04 Desktop (Anmeldebildschirm GDM) | Nach der Installation **einmal neu starten** (GDM liest neue Sitzungen nur beim Start). Im Anmeldebildschirm den Benutzer wählen, unten rechts auf das Zahnrad klicken, „Querencia Desktop“ wählen, Passwort eingeben. |
| Ubuntu 26.04 Server (ohne Anmeldebildschirm) | An der Textkonsole (tty1) anmelden und `querencia-session` eingeben. |

Ein eigener Querencia-Anmeldebildschirm wird gerade paketiert (siehe
[Bekannte Einschränkungen](bekannte-einschraenkungen.md)).

Nach dem Anmelden erscheinen nacheinander die Arbeitsfläche mit Hintergrund
und Symbolen, dann die beiden Panels.

## Die Panels

Querencia hat wie GNOME 2 zwei Panels.

**Oben** stehen links das Q-Logo mit den Menüs **Anwendungen**, **Orte** und
**System**, rechts die **Uhr**. Ein Klick auf die Uhr öffnet einen
Monatskalender. Lautstärke und Netzwerk lassen sich als Symbole oben rechts
hinzufügen (siehe unten).

**Unten** stehen links die **Fensterliste** (ein Knopf je Fenster) und rechts
der **Arbeitsflächenumschalter** mit vier Arbeitsflächen.

### Menü „Anwendungen“

Die Programme sind wie im GNOME-2-Menü von Ubuntu 10.04 in Gruppen sortiert:
Zubehör, Bildung, Spiele, Grafik, Internet, Büro, Entwicklung,
Unterhaltungsmedien, Systemwerkzeuge, Barrierefreiheit, Sonstige. Leere
Gruppen erscheinen nicht; jedes Programm steht genau einmal. Neu
installierte Programme erscheinen ohne Neustart des Panels.

### Menü „Orte“

Persönlicher Ordner, Arbeitsfläche, Dokumente, Musik, Bilder, Videos und
Downloads (nur die vorhandenen), darunter Computer, Netzwerk und Papierkorb.
Ein Klick öffnet den Ort in [Querencia Dateien](dateien.md).

### Menü „System“

- **Einstellungen** und **Systemverwaltung** mit den passenden Programmen,
  darunter [Systemeinstellungen](einstellungen.md) und
  [Software](software.md).
- **Informationen über Querencia** – Versionen der Bestandteile.
- **Abmelden …** und **Ausschalten …** – mit Rückfrage, siehe
  [Sitzung](sitzung.md).

### Panel anpassen

Rechtsklick auf eine freie Stelle eines Panels öffnet das Panelmenü:

- **Zum Panel hinzufügen …** öffnet eine Liste mit Suchfeld: Anwendungen,
  Orte, System, Fensterliste, Arbeitsflächenumschalter, Uhr,
  Anwendungsstarter …, Lautstärke, Netzwerk. Das neue Element landet in dem
  Bereich (links, Mitte, rechts), in den geklickt wurde.
- Rechtsklick auf ein Element: **Aus dem Panel entfernen**, bei Startern auch
  **Starten**.
- **Verschieben:** Element mit der mittleren Maustaste ziehen oder im
  Kontextmenü „Verschieben“ wählen und mit einem Klick auf das Panel
  abschließen.

Der Aufbau wird gespeichert und gilt bei der nächsten Anmeldung wieder. Ein
Element von einem Panel ins andere zu ziehen geht noch nicht.

## Die Arbeitsfläche

Auf der Arbeitsfläche liegen die Symbole **Rechner**, **Persönlicher
Ordner** und **Papierkorb**, dazu eingehängte Datenträger (USB-Sticks,
CDs, Netzlaufwerke – was angezeigt wird, stellt man in den
[Systemeinstellungen](einstellungen.md) unter „Symbole der Arbeitsfläche“ ein).

- **Doppelklick** öffnet ein Symbol; **F2** oder „Umbenennen …“ ändert die
  Beschriftung.
- **Auswählen:** Klick, Strg+Klick (hinzufügen/entfernen), Umschalt+Klick
  (bis hierher), Strg+A (alle), Esc (keine), oder mit der Maus einen Rahmen
  ziehen.
- Symbole lassen sich frei verschieben; sie rasten in einem unsichtbaren
  Raster ein.
- **Rechtsklick auf die freie Fläche:** Ordner anlegen, Leere Datei oder
  Dokument anlegen, Nach Namen aufräumen, Symbole am Raster ausrichten, Am
  Raster ausrichten (ein/aus), **Hintergrund der Arbeitsfläche ändern …**
- **Rechtsklick auf den Papierkorb:** Papierkorb öffnen, Papierkorb leeren …
  (mit Sicherheitsabfrage).
- **Rechtsklick auf einen Datenträger:** Öffnen, Aushängen bzw. Auswerfen.

Mitgeliefert werden mehrere Hintergründe („Querencia Blau“ und vier weitere
Motive, je mit und ohne Logo); ausgewählt werden sie in den
Systemeinstellungen unter „Hintergrundbild“.

## Arbeitsflächen

Es gibt vier Arbeitsflächen. Der Umschalter unten rechts zeigt sie als
kleine Zellen; ein Klick oder das Mausrad wechselt die Fläche.

| Kürzel | Wirkung |
|---|---|
| Strg+Alt+← / Strg+Alt+→ | zur Arbeitsfläche links / rechts |
| Strg+Alt+Umschalt+← / → | aktives Fenster mitnehmen |

Anzahl und Namen der Arbeitsflächen stellt man in den Systemeinstellungen
unter „Arbeitsflächen“ ein (1 bis 12).

## Fenster

Die Fensterrahmen zeichnet labwc im Thema „Querencia-Klassisch“, mit dem
Programmsymbol in der Titelleiste.

| Kürzel | Wirkung |
|---|---|
| Alt+Tab / Alt+Umschalt+Tab | Fenster wechseln (mit Liste) |
| Alt+F4 | Fenster schließen |
| Super+A | maximieren / zurück |
| Super+←, →, ↑, ↓ | an den Bildschirmrand andocken |
| Alt+Leertaste | Fenstermenü |

In der Fensterliste aktiviert ein Klick das Fenster; ein Klick auf das schon
aktive Fenster minimiert es, ein weiterer holt es zurück.

Alle Kürzel auf einen Blick zeigt **Super+?** (Programm „Tastenkürzel“), siehe
[Tastenkürzel](tastenkuerzel.md).

## Abmelden, Sperren, Ausschalten

- **Bildschirm sperren:** Strg+Alt+L. Nach 10 Minuten ohne Eingabe sperrt
  sich der Bildschirm selbst.
- **Abmelden:** System → Abmelden … oder Strg+Alt+Entf.
- **Ausschalten oder neu starten:** System → Ausschalten … oder Strg+Alt+Entf.

Einzelheiten: [Sitzung](sitzung.md).
