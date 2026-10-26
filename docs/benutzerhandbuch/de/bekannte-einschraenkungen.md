# Bekannte Einschränkungen

[Zurück zum Inhalt](index.md)

Stand Alpha 1 (20.10.2026), Querencia Dateien und Schnatter Stand Alpha 3.2
(26.10.2026).
Die Kennungen (QD-…) verweisen auf die Liste der offenen Punkte des
Projekts; P1 ist wichtig, P2 mittel.

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
| Englisch noch nicht überall (QD-055, P1) | Panel, Arbeitsfläche, Einstellungen, Tastenkürzel-Übersicht und der Sperrbildschirm sind nur deutsch. |
| Sprache und Region nicht einstellbar (QD-056, P2) | Texte sind deutsch, Datums- und Zahlenformate folgen noch der englischen Grundeinstellung der Sitzung. |
| Nur eine Tastaturbelegung (QD-057, P1) | Mehrere Belegungen mit Umschalttaste fehlen. |
| Systemdialoge teils englisch (QD-015, P2) | z. B. die „Meldung des Systems“ beim Verbinden mit einem Server in Querencia Dateien. |
| Querencia Dateien: kein Rückgängig | Strg+Z und Umschalt+Strg+Z gibt es noch nicht. Gelöschtes lässt sich aus dem Papierkorb wiederherstellen. |
| Querencia Dateien: Einstellungen von Files nur beim ersten Start | Seit Alpha 3.1 übernimmt Dateien die Einstellungen von Files beim ersten Start. Wer Dateien unter Alpha 3 schon gestartet hat, behält dessen Einstellungen; nachholen: Dateien schließen, `~/.config/querencia/dateien.ini` löschen (die eigenen Einstellungen von Dateien gehen verloren), Dateien neu starten. Lesezeichen bleiben. |
| Querencia Dateien: keine Spaltenansicht | Die Spaltenansicht von Querencia Files entfällt; Strg+1, Strg+2 und Strg+3 sind Symbole, Liste und Kompakt. |
| Querencia Dateien: kein Ordnerbaum | Die Seitenleiste zeigt nur „Orte“; die Ansicht wird nicht je Ordner gemerkt. |
| Querencia Dateien: Suche nur nach Namen | Keine Suche im Dateiinhalt (dafür [Nach Dateien suchen](dateisuche.md)); die Treffer aktualisieren sich nicht, Kopieren und Ziehen aus den Suchergebnissen geht noch nicht. |
| Querencia Dateien: Miniaturen für PDF | Erscheinen nur mit einem installierten Vorschauprogramm für PDF und `bubblewrap`; sonst bleibt das Symbol. |
| Querencia Dateien: Server teils ungeprüft | Geprüft mit Testservern für SFTP, WebDAV und FTP. Eine gelungene Verbindung zu einer Windows-Freigabe (SMB) und Zertifikatsfragen bei Sicherem WebDAV sind ungeprüft. |
| Querencia Dateien: „Kennwort merken“ im zweiten Versuch | Nach einem falschen Kennwort bietet ein WebDAV-Server das Merken nicht mehr an. |
| Querencia Dateien: echte Geräte ungeprüft | Laufwerke und Netzlaufwerke sind nur mit Abbildern und Testservern geprüft, nicht mit echten USB-Geräten. |
| Querencia Dateien: Kompaktansicht kürzt Namen | Lange Namen werden in der Kompaktansicht gekürzt. |
| Querencia Dateien: Statusleiste nach der Suche leer | Nach einer Suche zeigt die Statusleiste nichts an. |
| Kein Infobereich im Panel | Programme, die ein Symbol im Panel anzeigen wollen („Tray“), zeigen keines. |
| Schnatter: keine Anrufe | Die Web-Engine von Ubuntu ist ohne WebRTC gebaut. |
| Schnatter: Meldungen nur bei offenem Fenster | Schließen beendet Schnatter; ein Symbol im Panel gibt es nicht (kein Infobereich). |
| Schnatter: mit echtem Konto ungeprüft | Geprüft sind Umzug, Anmeldeseite und Fenster, nicht die Arbeit mit einem echten Konto. |
| Bildbetrachter: Nebenfenster ohne Titelleiste | Ein zum zweiten Mal geöffneter Dialog erscheint ohne Titelleiste. |
| Terminal: Einfügen mit der mittleren Maustaste | Eine Auswahl aus einem anderen Programm kommt nicht immer an. |
| Drucken ungetestet | Auf einen echten Drucker (z. B. aus dem Dokumentenbetrachter) noch nicht geprüft. |
| Blasse Textreste beim Seitenwechsel | Ein Zeichenfehler von GTK 4.22; die Sitzung umgeht ihn, indem GTK-Programme ihre Fenster ganz neu zeichnen. |

## Hardware und virtuelle Maschinen

| Punkt | Was das heißt |
|---|---|
| Alt+Druck in VMs | Das Bildschirmfoto des aktiven Fensters kam in virtuellen Maschinen nicht an; an echter Hardware ungeprüft. |
| Falsche Auflösung nach dem Start einer VM | Die durchgereichte Grafik meldet manchmal keine Bildschirmdaten; den Bildschirm kurz ab- und wieder anstecken hilft. |
| Ton in VMs | Ohne Soundkarte zeigt der Lautstärkeregler nur „Dummy Output“. |
