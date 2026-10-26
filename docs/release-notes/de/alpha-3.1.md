# Querencia Desktop – Alpha 3.1

**Stand:** 24.10.2026 · **Status:** in der APT-Quelle seit 24. Oktober 2026, 14:48

Alpha 3.1 ist ein Pflegestand zu Alpha 3: eine Korrektur in Querencia
Dateien und ein neues, wahlweise installierbares Programm. Es sind 23
Debian-Pakete für Ubuntu 26.04 („resolute“) aus derselben signierten
APT-Quelle. Nachfolger ist [Alpha 3.2](alpha-3.2.md).

> **Alpha.** Für Testsysteme gedacht, nicht für den Alltag. Erst auf einer
> virtuellen Maschine mit Snapshot ausprobieren.

## Neu in Alpha 3.1

- **Querencia Dateien 0.2.1:** Wer von Alpha 2.1 aktualisiert, bekommt beim
  ersten Start von Dateien jetzt auch die Einstellungen von Querencia Files
  übernommen (Ansicht, verborgene Dateien, Sortierung, Ordner zuerst,
  Einfach- oder Doppelklick, Seitenleiste). Files speicherte sie bis
  Alpha 2.1 unter `~/.config/strata`; Dateien 0.2.0 las nur den späteren Ort.
- **Querencia Webhülle 0.2.0** (neu, wahlweise): zeigt WhatsApp Web in einem
  eigenen Fenster mit der klassischen Menüleiste, meldet neue Nachrichten
  über die Benachrichtigungen und behält die Anmeldung. Nicht Teil der
  Standardinstallation:

  ```bash
  sudo apt install querencia-webhuelle
  ```

  Anrufe gehen nicht (die Web-Engine von Ubuntu kommt ohne WebRTC). Die
  Webhülle ist kein Produkt von WhatsApp oder Meta und nicht mit ihnen
  verbunden. Seit Alpha 3.2 heißt sie **Schnatter** (siehe
  [Alpha 3.2](alpha-3.2.md)).

## Versionen

Gegenüber Alpha 3 geändert; alle anderen Pakete sind unverändert.

| Paket | Fassung | Inhalt |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.1-1 | Metapaket, Versionsdatei „Alpha 3.1“ |
| querencia-dateien | 0.2.1-1 | übernimmt Files-Einstellungen auch aus `~/.config/strata` |
| querencia-webhuelle | 0.2.0-1 | **neu, wahlweise:** WhatsApp Web im eigenen Fenster |

Prüfsumme der Paketliste (SHA256SUMS): `f87a4a5ff48c4e20d515716e1f7a44e03065eb9dfba40ccca3acfd69aea4a112`.

## Aktualisieren

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` genügt ebenfalls. Aktualisiert werden Dateien und das
Metapaket; entfernt wird nichts. Die Webhülle kommt nur auf ausdrücklichen
Wunsch dazu (siehe oben). Ein Upgrade von Alpha 2.1 oder 2.2 direkt auf 3.1
geht wie in den [Hinweisen zu Alpha 3](alpha-3.md) beschrieben.

## Bekannte Grenzen

- **Übernahme nur beim ersten Start.** Dateien übernimmt die Einstellungen
  von Files nur, solange es noch keine eigenen hat
  (`~/.config/querencia/dateien.ini`). Wer nach dem Upgrade auf Alpha 3
  Dateien schon gestartet hat, behält dessen Einstellungen; die Werte von
  Files unter `~/.config/strata` bleiben dann unberücksichtigt. Nachholen:
  Dateien schließen, `~/.config/querencia/dateien.ini` löschen (die eigenen
  Einstellungen von Dateien gehen dabei verloren) und Dateien neu starten.
- Sonst wie Alpha 3.

## Geprüft

- Statische Paketprüfung, Lintian ohne Fehler, Tests der Quelle beim Bau
  (Dateien: 228 bestanden, Webhülle: 39).
- Upgrade von Alpha 3, 2.2 und 2.1 auf 3.1 in einer abgeschotteten Kopie des
  Systems: nichts entfernt, nichts zurückgehalten; ein Benutzer mit
  Files-Einstellungen unter `~/.config/strata` bekommt sie beim ersten Start
  von Dateien (Liste, nach Datum, verborgene Dateien).
- Webhülle einzeln: installiert ohne das Metapaket; ohne Empfehlungen nur
  das eine Paket.
- Nicht geprüft: Webhülle mit echtem Konto in der Test-VM.

Copyright 2026 Querencia Desktop contributors.
