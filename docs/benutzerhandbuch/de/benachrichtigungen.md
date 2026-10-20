# Benachrichtigungen (Querencia Benachrichtigungen)

[Zurück zum Inhalt](index.md)

Der Dienst startet mit der Sitzung und zeigt Meldungen von Programmen an
(Standard `org.freedesktop.Notifications`, z. B. `notify-send`).

![Benachrichtigung mit Dringlichkeit „kritisch“](../bilder/de-benachrichtigungen.png)

## So sehen Meldungen aus

- Sie erscheinen **oben rechts** unter dem oberen Panel und stapeln sich nach
  unten; höchstens fünf sind gleichzeitig zu sehen, weitere warten.
- **Anzeigedauer** nach Dringlichkeit: niedrig 3 s, normal 5 s; **kritische**
  Meldungen haben einen orangen Rand und bleiben, bis man sie schließt.
- Liegt der Mauszeiger auf einer Meldung, läuft ihre Zeit nicht ab.
- Ein Klick löst die Hauptaktion des Programms aus; Aktionsknöpfe erscheinen,
  wenn das Programm welche anbietet. Der Knopf „Schließen“ entfernt die
  Meldung.
- Bilder in Meldungen werden auf höchstens 48 Pixel verkleinert.

## Nicht stören und Verlauf

Bis es dafür ein Panel-Symbol gibt, geht beides im Terminal:

```bash
querencia-benachrichtigungen --nicht-stoeren an
```

```bash
querencia-benachrichtigungen --nicht-stoeren aus
```

```bash
querencia-benachrichtigungen --verlauf
```

Eine **Mitteilungszentrale** mit gespeichertem Verlauf und ein Panel-Symbol
sind in Arbeit.
