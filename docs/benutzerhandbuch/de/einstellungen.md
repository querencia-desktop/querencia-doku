# Systemeinstellungen (Querencia Einstellungen)

[Zurück zum Inhalt](index.md)

**Starten:** System → Einstellungen → Systemeinstellungen, oder auf der
Arbeitsfläche Rechtsklick → „Hintergrund der Arbeitsfläche ändern …“.

![Systemeinstellungen, Bereich Erscheinungsbild](../bilder/de-einstellungen.png)

Links steht die Liste der Bereiche, rechts der gewählte Bereich. Änderungen
gelten nach **Übernehmen**; „Standard wiederherstellen“ setzt den
Querencia-Standard zurück. Vor jeder Änderung an einer Konfigurationsdatei
legen die Einstellungen eine Sicherung an.

## Die Bereiche

**Erscheinungsbild**
- Symbolthema (z. B. Querencia, GNOME-Human, MATE) mit Vorschau,
  Steuerelemente-Thema (Querencia-Klassisch oder GTK-Standard),
  „Dunkle Darstellung bevorzugen“, Mauszeiger (Thema und Größe 24/32/48).
- Wirkt sofort in allen GTK-Programmen, im Panel und auf der Arbeitsfläche.
- **Dunkle Darstellung:** Seit Alpha 2 hat das Thema Querencia-Klassisch
  eine dunkle Fassung. Panel, Arbeitsfläche und die Querencia-Programme
  folgen ihr; laufende Programme und das Panel wechseln sofort, Ausschalten
  stellt die helle Darstellung wieder her. Hell bleiben vorerst die
  Fensterrahmen (labwc), Querencia Files, Bildschirmfoto und einige Dialoge
  (Sitzungsdialog, Tastenkürzel-Übersicht, die Leisten des Terminals). Fremde
  GTK-3-Programme folgen der Einstellung nicht.

**Hintergrundbild**
- Galerie der mitgelieferten Hintergründe mit Vorschau; ein Klick wählt,
  „Übernehmen“ setzt. Passend zum Bildschirm wird die Fassung 16:9 oder 4:3
  genommen.
- „Hintergrund …“ für ein eigenes Bild, eine einfarbige Fläche und die
  Darstellung (z. B. zentriert, gekachelt).

**Symbole der Arbeitsfläche**
- Rechner, Persönlicher Ordner und Papierkorb ein- oder ausblenden,
  Symbolgröße.
- Welche Datenträger erscheinen: Wechseldatenträger, optische Medien,
  Netzlaufwerke, eingebaute Laufwerke.

**Fensterdesign**
- Fensterthema, Eckenradius, Schatten, Anordnung der Titelleistenknöpfe,
  Schrift der Titelleiste.

**Schriften**
- Schrift für Anwendungen, Dokumente und dicktengleiche Schrift; Schrift der
  Fenstertitel (verweist auf „Fensterdesign“).

**Panels**
- Zeigt den gespeicherten Aufbau der Panels und erklärt die Bedienung im
  Panel selbst (Rechtsklick „Zum Panel hinzufügen …“, Verschieben, „Aus dem
  Panel entfernen“). Ändern kann man hier noch nichts.

**Tastatur**
- Tastaturbelegung aus allen Belegungen und Varianten (mit Suche),
  Wiederholverzögerung, Wiederholrate, Num-Taste.
- „Weitere Belegungen und Umschalten“: Mit mehreren Belegungen wechselt die
  Umschalttaste der Reihe nach zur nächsten; nach der Anmeldung gilt die
  erste. Eine Anzeige der aktiven Belegung im Panel gibt es noch nicht.

**Maus**
- Doppelklick-Zeit, Geschwindigkeit, Beschleunigung, Linkshänder,
  natürliches Rollen, Mauszeiger.

**Bildschirm**
- Je Bildschirm Auflösung, Wiederholrate, Drehung, Skalierung und Anordnung.
- Nach dem Anwenden fragt ein Dialog „Bildschirmeinstellungen behalten?“.
  Ohne Bestätigung innerhalb von 15 Sekunden kehrt der vorige Zustand zurück.
  Gespeicherte Einstellungen gelten auch bei der nächsten Anmeldung.

**Arbeitsflächen**
- Anzahl (1 bis 12), eigene Namen, Einblendung beim Wechsel und deren Dauer.

**Standardanwendungen**
- Welches Programm öffnet Webseiten, E-Mail, Text, Bilder, Musik, Video,
  Ordner, PDF und Archive. Das Terminal wird nur angezeigt.

**Sprache und Region**
- Anzeigesprache (Sprache der Menüs und Texte) und Formate (Datum und
  Uhrzeit, Zahlen, Währung, Papier, Maßeinheiten).
- Wirkt ab der nächsten Anmeldung; schon laufende Programme behalten ihre
  Sprache.

**Informationen über Querencia**
- Versionen der Einstellungen, des Systems und von labwc.

## Wann wirkt was?

Die meisten Änderungen wirken sofort. Einstellungen, die der Fensterverwalter
liest (Tastatur, Maus, Fensterdesign, Titelschrift), lädt labwc beim
Übernehmen neu, Belegung und Tastenwiederholung gelten dann sofort. Nur die
Num-Taste wirkt erst ab der nächsten Anmeldung oder beim Anstecken einer
Tastatur.

## Noch nicht enthalten

Energie, Startprogramme und ein schreibender Bereich „Panels“ fehlen noch.
Die Einstellungen selbst gibt es auf Deutsch und Englisch.
