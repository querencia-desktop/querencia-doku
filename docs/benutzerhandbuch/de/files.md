# Querencia Files – Dateiverwaltung

[Zurück zum Inhalt](index.md)

**Starten:** Menü Orte (z. B. „Persönlicher Ordner“), Doppelklick auf ein
Ordnersymbol der Arbeitsfläche oder Anwendungen → Zubehör → Querencia Files.

Querencia Files ist die Dateiverwaltung von Querencia, ein Fork des
Dateimanagers Strata mit Bedienung und Aussehen nach Nautilus 2.30: Menüleiste,
Werkzeugleiste, Ortszeile, Seitenleiste mit Orten und Geräten.

## Was Files kann

- **Ansichten:** Symbole, Liste (sortierbar) und Spalten; umschalten im Menü
  „Ansicht“.
- **Dateien bearbeiten:** Ordner anlegen, umbenennen (F2), ausschneiden,
  kopieren, einfügen, duplizieren, in den Papierkorb verschieben, endgültig
  löschen (Umschalt+Entf, mit Rückfrage), rückgängig machen; versteckte
  Dateien ein- und ausblenden; Reiter und mehrere Fenster.
- **Suchen:** Strg+K sucht nach Namen im Persönlichen Ordner und auf allen
  eingehängten Laufwerken.
- **Vorschau und Eigenschaften:** Vorschau für Text, Quelltext, Bilder, PDF,
  Ton und Video; Alt+Eingabe zeigt die Eigenschaften.
- **Datenträger:** USB-Sticks, CDs und weitere Laufwerke erscheinen unter
  „Geräte“ mit eigenem Symbol, auch wenn sie nicht eingehängt sind. Solange
  Files läuft, werden neu angesteckte Datenträger eingehängt (abschaltbar in
  den Einstellungen von Files). Ist ein Laufwerk beim Aushängen noch belegt,
  fragt Files nach.
- **Netzwerk:** „Netzwerk“ in der Seitenleiste zeigt gefundene Rechner;
  „Mit Server verbinden …“ öffnet Freigaben über SMB (Windows-Freigaben) oder
  SFTP. Bei einem unbekannten SFTP-Server zeigt Files den Schlüsseltyp und den
  SHA256-Fingerabdruck, damit man ihn vor dem Verbinden prüfen kann.
  Verbundene SMB-Freigaben lassen sich über einen Trennen-Knopf lösen.
- **Öffnen mit:** Doppelklick öffnet eine Datei mit dem Standardprogramm,
  z. B. Textdateien im Texteditor, PNG im Bildbetrachter, PDF im
  Dokumentenbetrachter, Archive in der Archivverwaltung. „Hier entpacken“
  läuft über Querencia Archiv.
- **Updates** kommen nur über apt; Files fragt nicht bei GitHub oder im AUR
  nach neuen Versionen und zeigt keinen Update-Hinweis.

## Tastenkürzel

Siehe [Tastenkürzel](tastenkuerzel.md#programme) oder Super+?.

## Gut zu wissen

- Die Oberfläche ist deutsch; einige Systemdialoge (aus GVfs, z. B. beim
  Einhängen) können englisch erscheinen.
- In der Netzwerkansicht kann derselbe Rechner zweimal auftauchen, weil zwei
  Suchdienste ihn melden.
- In der dunklen Darstellung bleibt Files vorerst hell; es hat ein eigenes
  Thema.

Siehe auch [Bekannte Einschränkungen](bekannte-einschraenkungen.md).
