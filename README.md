# Querencia Doku

Benutzerhandbuch und Release-Notes von Querencia Desktop – einer klassischen
Desktopumgebung im GNOME-2-Stil für Wayland (labwc, Rust, GTK 4). Die Texte
sind Markdown und sollen später als Webseite und im Paket ausgeliefert
werden.

*English summary:* User guide (German and English) and release notes of
Querencia Desktop, a classic GNOME-2-style desktop for Wayland. Alpha; the
German text is the reference.

> **Alpha.** Texte zur ersten internen Alpha (Stand 20.10.2026, abends). Was
> nicht belegt ist, steht als „offen“ im Text.

## Inhalt

| Ort | Was |
|---|---|
| [docs/benutzerhandbuch/de/](docs/benutzerhandbuch/de/index.md) | Benutzerhandbuch Deutsch: Einstieg, Tastenkürzel, je Programm eine Seite, bekannte Einschränkungen, Fragen und Antworten |
| [docs/benutzerhandbuch/en/](docs/benutzerhandbuch/en/index.md) | dieselbe Struktur auf Englisch (Übersetzung) |
| `docs/benutzerhandbuch/bilder/` | Bildschirmfotos aus abgeschotteten Prüfläufen, Herkunft in `herkunft.txt` |
| [docs/release-notes/de/alpha-1.md](docs/release-notes/de/alpha-1.md) | Release-Notes Alpha 1, Englisch unter [en/](docs/release-notes/en/alpha-1.md) |
| [docs/release-notes/de/alpha-1-web.md](docs/release-notes/de/alpha-1-web.md) | Kurztext Alpha 1 für die Webseite, Englisch unter [en/](docs/release-notes/en/alpha-1-web.md) |
| [docs/release-notes/de/alpha-2.md](docs/release-notes/de/alpha-2.md) | Release-Notes Alpha 2, Englisch unter [en/](docs/release-notes/en/alpha-2.md) |
| [docs/release-notes/de/alpha-3.md](docs/release-notes/de/alpha-3.md) | Release-Notes Alpha 3 (Querencia Dateien statt Files), Englisch unter [en/](docs/release-notes/en/alpha-3.md) |
| [docs/release-notes/de/alpha-3.1.md](docs/release-notes/de/alpha-3.1.md) | Release-Notes Alpha 3.1 (Dateien 0.2.1, Webhülle 0.2.0), Englisch unter [en/](docs/release-notes/en/alpha-3.1.md) |
| [docs/release-notes/de/alpha-3.2.md](docs/release-notes/de/alpha-3.2.md) | Release-Notes Alpha 3.2 (Dateien 0.2.2, Schnatter 0.3.0), Englisch unter [en/](docs/release-notes/en/alpha-3.2.md) |
| [docs/release-notes/de/alpha-3.3.md](docs/release-notes/de/alpha-3.3.md) | Release-Notes Alpha 3.3 (fünf Sprachen, Infobereich, Dateien 0.2.4), Englisch unter [en/](docs/release-notes/en/alpha-3.3.md) |
| [docs/release-notes/de/alpha-3.4.md](docs/release-notes/de/alpha-3.4.md) | Release-Notes Alpha 3.4 (Seite Treiber, Dateien 0.3.0, Anmeldung 0.1.4), Englisch unter [en/](docs/release-notes/en/alpha-3.4.md) |
| [docs/release-notes/de/alpha-3.5.md](docs/release-notes/de/alpha-3.5.md) | Release-Notes Alpha 3.5 (Anmeldung 0.1.5 in fünf Sprachen, Einstellungen 0.2.1 Seite Treiber), Englisch unter [en/](docs/release-notes/en/alpha-3.5.md) |

## Stand

| | |
|---|---|
| Fassung | Release-Notes Alpha 1 auf dem Stand des Paketsatzes, kein Tag |
| Grundlage | Live-Stand der Entwicklungsumgebung, Paketsatz Alpha 1 und Prüfberichte vom 20.10.2026 |
| Offen | signierte APT-Quelle (Bezugsweg der Pakete), Freigabe der Hintergründe (KI-erzeugt, siehe Lizenz); das Handbuch beschreibt noch den Stand vom Nachmittag des 20.10. |
| Nachtrag 24.10.2026 | Handbuch: Querencia Dateien (Beta 0.2.0) statt Querencia Files; Release-Notes Alpha 3 als Entwurf |
| Nachtrag 26.10.2026 | Release-Notes Alpha 3.1 und 3.2; Handbuch: Seite Schnatter, bekannte Einschränkungen auf Alpha 3.2 |
| Nachtrag 27.10.2026 | Release-Notes Alpha 3.3; Handbuch: Infobereich im Panel, Sprache und Region, fünf Sprachen, Dateien 0.2.4, bekannte Einschränkungen auf Alpha 3.3 |
| Nachtrag 27.10.2026, abends | Release-Notes Alpha 3.4; Handbuch: Seite Treiber, Dateien 0.3.0 (Rückgängig, Inhaltssuche, Reiter, Hier entpacken), Anmeldebildschirm und abgelaufenes Passwort, Sperrbildschirm und Tastenkürzel in fünf Sprachen, bekannte Einschränkungen auf Alpha 3.4 |
| Nachtrag 27./28.10.2026, nachts | Release-Notes Alpha 3.5; Handbuch: Zeile „Diese Sitzung“ der Seite Treiber (drei Fälle), Anmeldebildschirm in fünf Sprachen, bekannte Einschränkungen auf Alpha 3.5 |

## Bauen und Prüfen

Nichts zu bauen; geprüft wird mit `python3 ~/brain/system/scripts/brain_doku_check.py .` und `python3 -I ~/ai-clean/scripts/clean_check.py .`.
Ablauf und Regeln für Änderungen: [CONTRIBUTING.md](CONTRIBUTING.md).

## Lizenz

Texte und Bilder: CC-BY-SA-4.0, siehe [LICENSE](LICENSE); Namensnennung
„Querencia Desktop contributors“. Rechteinhaber in
[COPYRIGHT](COPYRIGHT). Name und Logo „Querencia“ sind keine freien Inhalte
(Markenregel); die Bildschirmfotos zeigen das Logo nur als Teil der
Oberfläche.

