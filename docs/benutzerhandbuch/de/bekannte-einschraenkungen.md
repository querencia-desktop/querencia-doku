# Bekannte Einschränkungen

[Zurück zum Inhalt](index.md)

Stand Alpha 2.1 (22.10.2026). Grundlage sind die
[Release-Notes Alpha 2.1](../../release-notes/de/alpha-2.1.md), Abschnitt
„Bekannte Grenzen“.

## Installation und Anmeldung

| Punkt | Was das heißt |
|---|---|
| Nur Ubuntu 26.04 | Die Pakete gibt es nur für Ubuntu 26.04 („resolute“), amd64. |
| Nicht auf echter Hardware getestet | Geprüft wurde in virtuellen Maschinen. Echte Hardware, Drucken auf einem echten Drucker und Windows-Freigaben (SMB) sind noch ungeprüft. |
| Eigener Anmeldebildschirm ungeprüft | Der wahlweise Anmeldebildschirm `querencia-anmeldung` spricht seit Alpha 2.1 die Systemsprache. Die Anmeldung darüber mit dem Paket aus der Paketquelle ist noch ungeprüft. |
| greetd bleibt nach dem Entfernen von `querencia-anmeldung` | War vorher kein Anmeldedienst eingerichtet (Server-Abbild), bleibt greetd mit einer Textanmeldung stehen. Neben GDM kehrt GDM zurück. |
| Neben GNOME: geteilte Einstellungen | Querencia und GNOME lesen dieselben gsettings-Werte; ein in Querencia geändertes Symbolthema gilt auch in GNOME. Neben Ubuntu Desktop zeigt Querencia die Yaru-Symbole, weil Ubuntu das Symbolthema als Benutzerwert setzt. GNOME-Programme erscheinen auch im Querencia-Menü. |
| Netzwerkverbindungen nur mit NetworkManager | Verbinden und Trennen im Netzwerk-Applet geht nur, wenn NetworkManager das Netz verwaltet. Auf dem Server-Abbild zeigt das Applet sonst kein Gerät, und Software kann nichts installieren; siehe [Software](software.md#wenn-software-keine-netzwerkverbindung-meldet). |

## Dunkle Darstellung

| Punkt | Was das heißt |
|---|---|
| Fensterrahmen und Files bleiben hell | labwc zeichnet die Rahmen mit dem eigenen Thema, Querencia Files hat ein eigenes Thema. Sitzungsdialog, Rückfragen und Passwortabfrage sind nur dunkel, wenn die dunkle Darstellung schon beim Anmelden gilt. |
| Fremde GTK-3-Programme folgen nicht | GTK 3 wertet „Dunkle Darstellung bevorzugen“ nicht aus. Die Querencia-Programme sind GTK 4 und folgen der Einstellung (bis auf die Ausnahmen oben). |
| Tastaturfokus nach dem Wechsel | Nach einem Wechsel hell/dunkel im laufenden Programm kann der Tastaturfokus an einer anderen Stelle stehen als beim Start. |
| Geändertes Thema erst nach Neuanmeldung | Panel und Arbeitsfläche übernehmen ein geändertes Thema erst nach einer Neuanmeldung; das Umschalten hell/dunkel wirkt sofort. |
| Firefox als Snap | übernimmt das GTK-Thema nicht. |

## Panel und Arbeitsfläche

| Punkt | Was das heißt |
|---|---|
| Panel-Absturz | In Testläufen stürzte das Panel beim ersten Öffnen des Menüs Anwendungen ab. Seit Alpha 2.1 startet es nach einem Absturz von selbst neu, nach einigen Sekunden und höchstens dreimal in zehn Minuten. Kommt es nicht wieder: Strg+Alt+Entf → Abmelden, dann neu anmelden. Die Ursache des Absturzes wird untersucht. |
| Arbeitsflächenumschalter ohne Fenster-Miniaturen | Die Zellen zeigen keine Fenster. |
| Panel-Elemente nicht zwischen den Panels verschiebbar | Innerhalb eines Panels geht Verschieben; sonst entfernen und im anderen Panel neu hinzufügen. |
| Bereich „Panels“ in den Einstellungen nur Anzeige | Ändern geht direkt im Panel. |
| Bildschirm-Skalierung 1,5 | Zentrierte oder gekachelte Hintergründe erscheinen zu klein. |
| Vollbild von X11-Programmen | Manche X11-Programme liegen im Vollbild unter den Panels. Super+F oder Alt+F11 schaltet das aktive Fenster in echtes Vollbild, dann verdeckt es die Panels. |

## Sprache

| Punkt | Was das heißt |
|---|---|
| Nur deutsch | Panel, Arbeitsfläche, Sperrbildschirm und Tastenkürzel-Übersicht sind vorerst nur deutsch; die Programme sprechen Deutsch und Englisch. |
| Systemdialoge teils englisch | z. B. Meldungen von GVfs beim Einhängen in Files. |
| Vorläufige Programmkennungen | Panel und einige Programme nutzen bis Alpha 3 noch vorläufige Kennungen (`org.example…`). Für die Bedienung spielt das keine Rolle. |

## Programme

| Punkt | Was das heißt |
|---|---|
| Files: Rechner doppelt in der Netzwerkansicht | Zwei Suchdienste melden denselben Rechner. |
| Terminal: Einfügen mit der mittleren Maustaste | Eine Auswahl aus einem anderen Programm kommt nicht immer an. |
| Drucken ungetestet | Auf einen echten Drucker (z. B. aus dem Dokumentenbetrachter) noch nicht geprüft. |
| Blasse Textreste beim Seitenwechsel | Ein Zeichenfehler von GTK 4.22; die Sitzung umgeht ihn, indem GTK-Programme ihre Fenster ganz neu zeichnen. |

## Hardware und virtuelle Maschinen

| Punkt | Was das heißt |
|---|---|
| Alt+Druck in VMs | Das Bildschirmfoto des aktiven Fensters kam in virtuellen Maschinen nicht an; an echter Hardware ungeprüft. |
| Falsche Auflösung nach dem Start einer VM | Die durchgereichte Grafik meldet manchmal keine Bildschirmdaten; den Bildschirm kurz ab- und wieder anstecken hilft. |
| Ton in VMs | Ohne Soundkarte zeigt der Lautstärkeregler nur „Dummy Output“. |
