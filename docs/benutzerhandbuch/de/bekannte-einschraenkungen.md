# Bekannte Einschränkungen

[Zurück zum Inhalt](index.md)

Stand Alpha 1 (20.10.2026). Die Kennungen (QD-…) verweisen auf die Liste der
offenen Punkte des Projekts; P1 ist wichtig, P2 mittel.

## Installation und Anmeldung

| Punkt | Was das heißt |
|---|---|
| Eigener Anmeldebildschirm fehlt im Paket (QD-075, P1) | Angemeldet wird über GDM („Querencia Desktop“ am Zahnrad wählen) oder an der Textkonsole mit `querencia-session`. |
| Neben einem Ubuntu-Desktop noch nicht fertig geprüft (QD-074, P1) | Die Probe auf einem Ubuntu-Desktop-System läuft. |
| Aussehen auf dem GDM-Weg (QD-068, P2) | Schrift-, Symbol- und Zeigervorgaben von Querencia fehlen dort noch; die Sitzung sieht dann anders aus. In Arbeit. |
| Software offline auf Server-Systemen (QD-067, P2) | Siehe [Software](software.md#wenn-software-keine-netzwerkverbindung-meldet). |
| Paketsatz hinter der Entwicklungsumgebung | Einige Pakete sind eine Fassung älter als die hier beschriebenen Programme (siehe Release-Notes). |

## Panel und Arbeitsfläche

| Punkt | Was das heißt |
|---|---|
| Fensterliste zeigt alle Arbeitsflächen (QD-013, P2) | Eine Einstellung „nur aktuelle Arbeitsfläche“ ist in Arbeit. |
| Arbeitsflächenumschalter ohne Fenster-Miniaturen (QD-012, P2) | Die Zellen zeigen keine Fenster. |
| Panel-Elemente nicht zwischen den Panels verschiebbar (QD-044) | Innerhalb eines Panels geht Verschieben. |
| Panel im Paket ruft den alten Abmelden-Dialog (QD-069, P2) | Betrifft die installierten Pakete; in Arbeit. |
| Bereich „Panels“ in den Einstellungen nur Anzeige (QD-046) | Ändern geht direkt im Panel. |
| Bildschirm-Skalierung 1,5 (QD-028, P2) | Zentrierte oder gekachelte Hintergründe erscheinen zu klein. |
| Vollbild von X11-Programmen (QD-065) | Manche X11-Programme liegen im Vollbild unter den Panels. In Arbeit. |

## Programme

| Punkt | Was das heißt |
|---|---|
| Englisch noch nicht überall (QD-055, P1) | Panel, Arbeitsfläche, Einstellungen, Tastenkürzel-Übersicht und der Sperrbildschirm sind nur deutsch. |
| Sprache und Region nicht einstellbar (QD-056, P2) | Texte sind deutsch, Datums- und Zahlenformate folgen noch der englischen Grundeinstellung der Sitzung. |
| Nur eine Tastaturbelegung (QD-057, P1) | Mehrere Belegungen mit Umschalttaste fehlen. |
| Systemdialoge teils englisch (QD-015, P2) | z. B. Meldungen von GVfs beim Einhängen in Files. |
| Files: Rechner doppelt in der Netzwerkansicht (QD-036, P2) | Zwei Suchdienste melden denselben Rechner. |
| Files: Strata-Logo im Info-Dialog (QD-071, P1) | Wird durch das Querencia-Symbol ersetzt. |
| Bildbetrachter: Nebenfenster ohne Titelleiste | Ein zum zweiten Mal geöffneter Dialog erscheint ohne Titelleiste. |
| Terminal: Einfügen mit der mittleren Maustaste | Eine Auswahl aus einem anderen Programm kommt nicht immer an. |
| Dokumentenbetrachter: Drucken | Auf einen echten Drucker noch nicht geprüft. |
| Benachrichtigungen ohne Mitteilungszentrale (QD-073) | In Arbeit; bis dahin „Nicht stören“ über die Kommandozeile. |
| Blasse Textreste beim Seitenwechsel (QD-070, P2) | Ein Zeichenfehler von GTK 4.22; die Sitzung schaltet ihn ab, ein Bericht an GTK steht aus. |

## Hardware und virtuelle Maschinen

| Punkt | Was das heißt |
|---|---|
| Falsche Auflösung nach dem Start einer VM (QD-027, P2) | Die durchgereichte Grafik meldet manchmal keine Bildschirmdaten; den Bildschirm kurz ab- und wieder anstecken hilft. |
| Ton in VMs | Ohne Soundkarte zeigt der Lautstärkeregler nur „Dummy Output“. |
| Alt+Druck in VMs | Kam bei der Probe nicht an; an echter Hardware zu prüfen. |
| Panel und Arbeitsfläche einmal ohne Spur beendet (QD-025, P1) | Am 18.10. einmal beobachtet, Ursache unbekannt. Abhilfe: Strg+Alt+Entf → Abmelden, dann neu anmelden. |
