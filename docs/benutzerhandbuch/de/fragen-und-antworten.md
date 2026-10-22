# Fragen und Antworten

[Zurück zum Inhalt](index.md)

**Wie sehe ich alle Tastenkürzel?**
Super+? (Windows-Taste, Umschalt und ß bzw. die Taste mit dem Fragezeichen).
Siehe [Tastenkürzel](tastenkuerzel.md).

**Wie bekomme ich Lautstärke und Netzwerk ins Panel?**
Rechtsklick auf eine freie Stelle im oberen Panel → „Zum Panel hinzufügen …“
→ „Lautstärke“ bzw. „Netzwerk“. Auf einem frischen Benutzerprofil sind beide
noch nicht da.

**Wie schalte ich auf die dunkle Darstellung um?**
System → Einstellungen → Systemeinstellungen → Erscheinungsbild, „Dunkle
Darstellung bevorzugen“ einschalten und „Übernehmen“. Panel, Arbeitsfläche
und die Querencia-Programme wechseln sofort; Fensterrahmen und Querencia
Files bleiben vorerst hell.

**Wo sind die Einstellungen?**
System → Einstellungen → Systemeinstellungen. Den Hintergrund erreicht man
auch über Rechtsklick auf die Arbeitsfläche.

**Wie installiere ich Programme?**
System → Systemverwaltung → Software. Zum Installieren fragt der
Passwortdialog nach dem eigenen Passwort. Siehe [Software](software.md).

**Ich habe mich abgemeldet – kann ich mich sofort wieder anmelden?**
Ja. Querencia beendet beim Abmelden die Programme und Dienste der Sitzung, so
dass eine neue Anmeldung sauber startet.

**Der Bildschirm wird dunkel und gesperrt, obwohl ich nichts getan habe.**
Nach 10 Minuten ohne Eingabe sperrt Querencia den Bildschirm. Mit dem eigenen
Passwort entsperren. Browser und Videoprogramme können die Sperre anhalten,
solange sie etwas abspielen.

**Der Abmelden-Dialog wartet einfach – ist das richtig?**
Ja. Rückfragen zählen nicht von selbst herunter. Einen Countdown kann man in
`~/.config/querencia/sitzung.ini` einschalten, siehe [Sitzung](sitzung.md).

**Warum sind einige Dialoge englisch?**
Die Querencia-Programme, auch die Systemeinstellungen, sind deutsch und
englisch; manche Dialoge kommen aus Systembibliotheken (z. B. GVfs,
GTK-Dateidialog) und folgen deren Übersetzungen. Panel, Arbeitsfläche und
Sperrbildschirm sind bisher nur deutsch.

**Wie stelle ich das Programm auf Englisch um?**
Die Programme folgen der Spracheinstellung (`LANGUAGE`/`LANG`). Einstellen
lässt sie sich in den Systemeinstellungen unter „Sprache und Region“; sie
gilt ab der nächsten Anmeldung. Zum Ausprobieren kann man ein einzelnes
Programm auch so starten:

```bash
LANGUAGE=en querencia-rechner
```

**Wohin speichert das Bildschirmfoto?**
In den Ordner `Screenshots` im Bilder-Ordner; vorhandene Dateien werden nie
überschrieben.

**Ein Programm hängt oder reagiert nicht.**
Anwendungen → Systemwerkzeuge → Systemüberwachung, Prozess auswählen,
„Beenden“ (Entf) bzw. „Abwürgen“ (Strg+K).

**Wo finde ich Protokolle für eine Fehlermeldung?**
Unter `~/.local/state/querencia/` (je Programm eine `.log`-Datei, der
Sitzungsstart in `sitzung-start.log`).

**Panel oder Arbeitsfläche sind verschwunden.**
Das Panel startet nach einem Absturz nach einigen Sekunden von selbst neu.
Kommt es nicht wieder oder fehlt die Arbeitsfläche: Strg+Alt+Entf → Abmelden
und neu anmelden. Hängt die ganze Sitzung, an einer
Textkonsole (Strg+Alt+F3) anmelden und `querencia-session --exit` eingeben.

**Wie entferne ich Querencia wieder?**
`sudo apt remove 'querencia-*'`. Eigene Einstellungen in `~/.config/querencia`
und Protokolle in `~/.local/state/querencia` bleiben erhalten. Im
Anmeldebildschirm wieder die gewohnte Sitzung wählen.
