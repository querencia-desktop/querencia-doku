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

## Stand

| | |
|---|---|
| Fassung | Release-Notes Alpha 1 auf dem Stand des Paketsatzes, kein Tag |
| Grundlage | Live-Stand der Entwicklungsumgebung, Paketsatz Alpha 1 und Prüfberichte vom 20.10.2026 |
| Offen | signierte APT-Quelle (Bezugsweg der Pakete), Freigabe der Hintergründe (KI-erzeugt, siehe Lizenz); das Handbuch beschreibt noch den Stand vom Nachmittag des 20.10. |

## Bauen und Prüfen

Nichts zu bauen; geprüft wird mit `python3 ~/brain/system/scripts/brain_doku_check.py .` und `python3 -I ~/ai-clean/scripts/clean_check.py .`.
Ablauf und Regeln für Änderungen: [CONTRIBUTING.md](CONTRIBUTING.md).

## Lizenz

Texte und Bilder: CC-BY-SA-4.0, siehe [LICENSE](LICENSE); Namensnennung
„Querencia Desktop contributors“. Rechteinhaber in
[COPYRIGHT](COPYRIGHT). Name und Logo „Querencia“ sind keine freien Inhalte
(Markenregel); die Bildschirmfotos zeigen das Logo nur als Teil der
Oberfläche.

