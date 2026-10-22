# Sitzung: Abmelden, Sperren, Ausschalten (Querencia Sitzung)

[Zurück zum Inhalt](index.md)

![Sitzungsdialog nach Strg+Alt+Entf](../bilder/de-sitzung-dialog.png)

## Bildschirm sperren

- **Strg+Alt+L** oder **System → Bildschirm sperren** sperrt sofort.
- Nach **10 Minuten** ohne Eingabe sperrt sich der Bildschirm selbst.
  Browser und Videoprogramme können das anhalten, solange sie etwas
  abspielen.
- Der Sperrbildschirm zeigt Uhr und Passwortfeld auf jedem Bildschirm;
  entsperrt wird mit dem eigenen Passwort.

## Sitzungsdialog

**Strg+Alt+Entf** öffnet einen Dialog mit **Abmelden**, **Bildschirm
sperren**, **Neu starten** und **Herunterfahren**. Esc oder „Abbrechen“
schließt ihn; Pfeiltasten und Eingabe funktionieren.

## Abmelden und Ausschalten über das Menü

- **System → Abmelden …** fragt „Möchten Sie sich jetzt abmelden?“.
- **System → Ausschalten …** fragt „Möchten Sie den Rechner jetzt herunterfahren?“.

Die Rückfragen warten, bis man wählt; sie zählen nicht von selbst herunter.
Wer einen Countdown möchte, trägt ihn in `~/.config/querencia/sitzung.ini`
ein:

```ini
[Dialog]
Countdown=an
```

Beim Abmelden beendet Querencia zuerst die Programme der Sitzung und dann
die Sitzungsdienste; danach kann man sich sofort wieder anmelden.

## Passwortdialog

Verlangt ein Programm Administratorrechte (z. B. Software beim Installieren,
Neu starten), erscheint der Passwortdialog der Sitzung („Legitimierung erforderlich“) und
fragt nach dem eigenen Passwort.

## Gut zu wissen

Der Sperrbildschirm und seine Meldungen sind nur deutsch. Sitzungsdialog,
Rückfragen und Passwortdialog erscheinen dunkel, wenn die dunkle Darstellung
schon beim Anmelden eingeschaltet ist.
