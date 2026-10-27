# Querencia Doku

Benutzerhandbuch und Release-Notes von Querencia Desktop – einer klassischen
Desktopumgebung im GNOME-2-Stil für Wayland (labwc, Rust, GTK 4). Die Texte
sind Markdown und sollen später als Webseite und im Paket ausgeliefert
werden.

*English summary:* User guide (German and English) and release notes of
Querencia Desktop, a classic GNOME-2-style desktop for Wayland. Alpha; the
German text is the reference.

> **Alpha.** Texte zu Querencia Desktop Alpha 3.3 (Stand 27.10.2026). Was neu
> ist und welche Grenzen gelten, steht in den
> [Release-Notes Alpha 3.3](docs/release-notes/de/alpha-3.3.md); Installation und
> Projektseite: <https://querencialinux.org>.

## Inhalt

| Ort | Was |
|---|---|
| [docs/benutzerhandbuch/de/](docs/benutzerhandbuch/de/index.md) | Benutzerhandbuch Deutsch: Einstieg, Tastenkürzel, je Programm eine Seite, bekannte Einschränkungen, Fragen und Antworten |
| [docs/benutzerhandbuch/en/](docs/benutzerhandbuch/en/index.md) | dieselbe Struktur auf Englisch (Übersetzung) |
| `docs/benutzerhandbuch/bilder/` | Bildschirmfotos aus abgeschotteten Prüfläufen, Herkunft in `herkunft.txt` |
| [docs/release-notes/de/alpha-3.3.md](docs/release-notes/de/alpha-3.3.md) | Release-Notes Alpha 3.3 (fünf Sprachen, Infobereich, Dateien 0.2.4), Englisch unter [en/](docs/release-notes/en/alpha-3.3.md) |
| [docs/release-notes/de/alpha-3.2.md](docs/release-notes/de/alpha-3.2.md) | Release-Notes Alpha 3.2 (Dateien 0.2.2, Schnatter 0.3.0), Englisch unter [en/](docs/release-notes/en/alpha-3.2.md) |
| [docs/release-notes/de/alpha-3.1.md](docs/release-notes/de/alpha-3.1.md) | Release-Notes Alpha 3.1 (Dateien 0.2.1, Webhülle 0.2.0), Englisch unter [en/](docs/release-notes/en/alpha-3.1.md) |
| [docs/release-notes/de/alpha-3.md](docs/release-notes/de/alpha-3.md) | Release-Notes Alpha 3 (Querencia Dateien statt Files), Englisch unter [en/](docs/release-notes/en/alpha-3.md) |
| [docs/release-notes/de/alpha-2.1.md](docs/release-notes/de/alpha-2.1.md) | Release-Notes Alpha 2.1, Englisch unter [en/](docs/release-notes/en/alpha-2.1.md) |
| [docs/release-notes/de/alpha-2.md](docs/release-notes/de/alpha-2.md) | Release-Notes Alpha 2, Englisch unter [en/](docs/release-notes/en/alpha-2.md) |
| [docs/release-notes/de/alpha-1.md](docs/release-notes/de/alpha-1.md) | Release-Notes Alpha 1, Englisch unter [en/](docs/release-notes/en/alpha-1.md) |
| [docs/release-notes/de/alpha-1-web.md](docs/release-notes/de/alpha-1-web.md) | Kurztext Alpha 1 für die Webseite, Englisch unter [en/](docs/release-notes/en/alpha-1-web.md) |

## Stand

| | |
|---|---|
| Fassung | Release-Notes Alpha 1 bis Alpha 3.3 auf dem Stand des jeweiligen Paketsatzes; Benutzerhandbuch mit Querencia Dateien (Beta), der Seite Schnatter (wahlweise), Infobereich im Panel, Sprache und Region (fünf Sprachen), bekannte Einschränkungen auf Alpha 3.3; kein Tag |
| Grundlage | Paketsatz Alpha 3.3 vom 27.10.2026 (in der APT-Quelle seit 27.10.2026), davor Alpha 3.2 vom 26.10.2026, Alpha 3.1 und Alpha 3 vom 24.10.2026, der Quellcode der Programme |
| Offen | Bildschirmfotos für Terminal und Schnatter fehlen; einzelne Bilder zeigen eine frühere Fassung des Programms (Herkunft in `docs/benutzerhandbuch/bilder/herkunft.txt`) |

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
