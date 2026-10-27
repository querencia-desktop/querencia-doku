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
Die Querencia-Programme, das Panel und die Arbeitsfläche gibt es seit
Alpha 3.3 auf Deutsch, Englisch, Italienisch, Spanisch und Französisch.
Manche Dialoge kommen aus Systembibliotheken (z. B. GVfs, GTK-Dateidialog)
und folgen deren Übersetzungen; für GTK braucht es das Sprachpaket
`language-pack-gnome-<xx>` der gewählten Sprache. Fest deutsch sind noch
der Sperrbildschirm, das Fenster des Lautstärkereglers und die
Tastenkürzel-Übersicht.

**Wie stelle ich eine andere Sprache ein?**
In den Einstellungen unter „Sprache und Region“, wirksam ab der nächsten
Anmeldung (siehe [Systemeinstellungen](einstellungen.md)). Fehlt dort eine
Sprache, ist ihre Locale nicht installiert; das Paket `locales-all` bringt
alle mit. Ein einzelnes Programm kann man zum Ausprobieren so starten:

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
