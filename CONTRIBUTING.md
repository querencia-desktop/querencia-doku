# Mitmachen bei Querencia Doku

Danke für das Interesse. Querencia ist in einer frühen Alpha-Phase; bitte
rechne mit Rückfragen und langsamen Antworten.

Jede Änderung durchläuft den unten beschriebenen Prüf- und Freigabeweg;
pottrauschen (der „Besitzer“) nimmt sie ab.

## Fehler melden

In der gemeinsamen Meldestelle:
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

**Sicherheitslücken nicht öffentlich melden:** siehe [SECURITY.md](SECURITY.md).

## Arbeitsweise

### 1. Isolierte Prüfung

- Bildschirmfotos nur aus abgeschotteten Prüfläufen der Programm-Repos (eigener
  labwc ohne Bildschirm, eigenes `HOME`, `XDG_RUNTIME_DIR` und
  `XDG_CONFIG_HOME`), nie aus einer echten Sitzung; jedes Bild vorher ansehen
  (keine Benutzernamen, Pfade, Adressen) und in `herkunft.txt` eintragen.
- Aussagen über Programme nur, wenn sie im jeweiligen Repo belegt sind
  (Test, Changelog, Bericht); Unbelegtes steht als „offen“ im Text.
- Deutsch ist maßgeblich; die englische Fassung folgt in derselben Änderung.

### 2. Berichte

Jede abgeschlossene Aufgabe hinterlässt:

- einen **Bericht** (was geändert wurde, was geprüft wurde, Zahlen, was *nicht*
  geprüft wurde, Befunde für andere),
- eine **Übergabe** (Zuständigkeit, Ordner, Prüfwerkzeuge, Integration und
  Rückfall, Offenes, Fallen, Berichte),
- Versionen als Git-Tags (`<programm>/<version>`), Berichte nennen Commits.

Im Pull Request stehen Zusammenfassung und Prüfzahlen; Unfertiges wird als
unfertig gekennzeichnet, in Code, Dokumentation und Changelog.

### 3. Freigaben

- Der Besitzer entscheidet über Merge und Release. Nichts gelangt ohne
  ausdrückliche Freigabe in `main`, in ein Paket oder in eine Sitzung.
- Eine Freigabe zählt nur, wenn sie direkt in dem Pull Request bzw. der Aufgabe
  gegeben wird, die sie ausführt; eine weitergeleitete Freigabe gilt nicht.
- Änderungen an laufenden Systemen (Sitzung, Autostart, `rc.xml`, Pakete)
  brauchen immer einen eigenen, vorab beschriebenen Rückfall.

## Regeln für die Texte

1. Vorab ein Issue, wenn es um mehr als eine kleine Korrektur geht –
   besonders bei Bedienung und Optik. Maßstab ist die Benutzerhilfe von GNOME 2 (Ubuntu 10.04).
2. Zweig von `main`, kleine, thematisch geschlossene Commits
   (Conventional Commits).
3. Programmnamen, Menüs und Tastenkürzel wie in der Oberfläche (deutsch) bzw.
   wie im englischen Katalog des Programms (`po/`).
4. Keine privaten Pfade (`/home/<name>`, `~/projects`, `~/opt`), Rechnernamen
   oder Adressen in Text und Bildern.
5. Fremdmaterial (Texte, Bilder) nur mit passender Lizenz und Vermerk; keine
   Übernahme aus der Dokumentation der Vorbildprogramme.

## Lizenz der Beiträge

Mit einem Beitrag stimmst du zu, dass er unter der Lizenz dieses Repos
(CC-BY-SA-4.0) veröffentlicht wird. Du versicherst, dass du ihn selbst
geschrieben hast oder die Lizenz des Ursprungs es erlaubt.
