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
| [docs/release-notes/de/alpha-2.md](docs/release-notes/de/alpha-2.md) | Release-Notes Alpha 2, Englisch unter [en/](docs/release-notes/en/alpha-2.md) |
| [docs/release-notes/de/alpha-1.md](docs/release-notes/de/alpha-1.md) | Release-Notes Alpha 1, Englisch unter [en/](docs/release-notes/en/alpha-1.md) |
| [docs/release-notes/de/alpha-1-web.md](docs/release-notes/de/alpha-1-web.md) | Kurztext Alpha 1 für die Webseite, Englisch unter [en/](docs/release-notes/en/alpha-1-web.md) |

## Stand

| | |
|---|---|
| Fassung | Release-Notes Alpha 1 und Alpha 2 auf dem Stand des jeweiligen Paketsatzes, kein Tag |
| Grundlage | Live-Stand der Entwicklungsumgebung, Paketsatz Alpha 1 und Prüfberichte vom 20.10.2026 |
| Offen | signierte APT-Quelle (Bezugsweg der Pakete), Freigabe der Hintergründe (KI-erzeugt, siehe Lizenz); das Handbuch beschreibt noch den Stand vom Nachmittag des 20.10. |

## Bauen und Prüfen

Nichts zu bauen. Vor jeder Änderung: Markdown-Links prüfen, Bildschirmfotos
nur aus abgeschotteten Prüfläufen (eigenes Profil ohne Benutzernamen in
Pfaden) und Herkunft in `docs/benutzerhandbuch/bilder/herkunft.txt`
eintragen. Arbeitsweise: [CONTRIBUTING.md](CONTRIBUTING.md); Änderungen:
[CHANGELOG.md](CHANGELOG.md).

## Lizenz

Texte und Bilder: CC-BY-SA-4.0, siehe [LICENSE](LICENSE); Namensnennung
„Querencia Desktop contributors“. Rechteinhaber in
[COPYRIGHT](COPYRIGHT). Name und Logo „Querencia“ sind keine freien Inhalte
([MARKE.md](MARKE.md)); die Bildschirmfotos zeigen das Logo nur als Teil der
Oberfläche.

## Fehler melden

Fehler, Wünsche und Fragen zu Querencia gehen an die gemeinsame Meldestelle:
<https://github.com/querencia-desktop/querencia/issues/new/choose>.
Sicherheitslücken bitte nicht öffentlich melden, siehe [SECURITY.md](SECURITY.md).
