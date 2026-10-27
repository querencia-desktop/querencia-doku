# Bekannte Einschränkungen

[Zurück zum Inhalt](index.md)

Stand Alpha 1 (20.10.2026); Infobereich und Schnatter Stand Alpha 3.3,
Querencia Dateien Stand Alpha 3.4, Sprachen, Anmeldebildschirm und Treiber
Stand Alpha 3.5 ([Datum]).
Die Kennungen (QD-…) verweisen auf die Liste der offenen Punkte des
Projekts; P1 ist wichtig, P2 mittel.

## Installation und Anmeldung

| Punkt | Was das heißt |
|---|---|
| Eigener Anmeldebildschirm: Passwort und GTK-Texte | Der wahlweise Anmeldebildschirm (`querencia-anmeldung`) folgt seit Alpha 3.5 der Systemsprache in allen fünf Sprachen; einige Texte von GTK selbst (etwa der Tooltip am Auge) bleiben ohne `language-pack-gnome-<xx>-base` englisch. Ein abgelaufenes Passwort meldet er seit Alpha 3.4 verständlich, ändern lässt es sich aber nur an der Textkonsole (siehe [Einstieg](einstieg.md#anmelden)). Ohne ihn wird über GDM („Querencia Desktop“ am Zahnrad wählen) oder an der Textkonsole mit `querencia-session` angemeldet. |
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
| Infobereich: kein XEmbed | Alte X11-Programme, die ihr Symbol über das ältere Verfahren XEmbed anbieten, zeigen keines. Angezeigt werden Programme mit StatusNotifierItem (auch libappindicator). |
| Infobereich: passive Symbole verborgen | Symbole, die ein Programm als „passiv“ meldet, bleiben verborgen; einen Knopf zum Aufklappen gibt es nicht. Viele Programme können ihr Symbol selbst immer zeigen. |
| Infobereich: Programm schon vor dem Panel gestartet | Es meldet sich nicht immer an; dann das Programm neu starten. |
| Infobereich mit echten Programmen | Geprüft mit Testprogrammen und der Bibliothek libayatana-appindicator, noch nicht mit Webex, Nextcloud oder Discord selbst. |

## Programme

| Punkt | Was das heißt |
|---|---|
| Kleine Sprachreste | Seit Alpha 3.4 gibt es alle Programme, Panel, Arbeitsfläche, Sperrbildschirm, Lautstärkeregler und Tastenkürzel-Übersicht auf Deutsch, Englisch, Italienisch, Spanisch und Französisch. Im Italienischen bleibt der Tastenname „Return“ in Menükürzeln englisch. |
| Sprache und Region: nur Sprachen mit Locale | Die Seite bietet nur Sprachen an, für die eine Locale installiert ist. Das empfohlene Paket `locales-all` (rund 230 MB) bringt alle mit. Eine Änderung wirkt ab der nächsten Anmeldung. |
| Nur eine Tastaturbelegung (QD-057, P1) | Mehrere Belegungen mit Umschalttaste fehlen. |
| Systemdialoge teils englisch (QD-015, P2) | z. B. die „Meldung des Systems“ beim Verbinden mit einem Server in Querencia Dateien. |
| Querencia Dateien: Rückgängig mit Grenzen | Rückgängig gilt nur im eigenen Fenster und bis Querencia Dateien geschlossen wird. Endgültiges Löschen und „Papierkorb leeren“ lassen sich nicht zurücknehmen; Ersetztes kommt nicht zurück; „Hier entpacken“ steht nicht in der Liste. Siehe [Rückgängig und Wiederholen](dateien.md#rückgängig-und-wiederholen). |
| Querencia Dateien: Einstellungen von Files nur beim ersten Start | Seit Alpha 3.1 übernimmt Dateien die Einstellungen von Files beim ersten Start. Wer Dateien unter Alpha 3 schon gestartet hat, behält dessen Einstellungen; nachholen: Dateien schließen, `~/.config/querencia/dateien.ini` löschen (die eigenen Einstellungen von Dateien gehen verloren), Dateien neu starten. Lesezeichen bleiben. |
| Querencia Dateien: keine Spaltenansicht | Die Spaltenansicht von Querencia Files entfällt; Strg+1, Strg+2 und Strg+3 sind Symbole, Liste und Kompakt. |
| Querencia Dateien: kein Ordnerbaum | Die Seitenleiste zeigt nur „Orte“; die Ansicht wird nicht je Ordner gemerkt. |
| Querencia Dateien: Suche im Inhalt ohne Index | „Auch Dateiinhalt“ liest nur Textdateien bis 10 MB, keine Netzwerkorte und keine Dokumente wie odt oder pdf; große Ordner dauern. Die Treffer aktualisieren sich nicht, Kopieren und Ziehen aus den Suchergebnissen geht noch nicht. |
| Querencia Dateien: Reiter nur mit Ordner | Wiederhergestellte Reiter merken nur den Ordner, nicht Ansicht, Zoom oder Verlauf. |
| Querencia Dateien: Miniaturen für PDF | Erscheinen nur mit einem installierten Vorschauprogramm für PDF und `bubblewrap`; sonst bleibt das Symbol. |
| Querencia Dateien: Server teils ungeprüft | Geprüft mit Testservern für SFTP, WebDAV und FTP. Eine gelungene Verbindung zu einer Windows-Freigabe (SMB) und Zertifikatsfragen bei Sicherem WebDAV sind ungeprüft. |
| Querencia Dateien: „Kennwort merken“ im zweiten Versuch | Nach einem falschen Kennwort bietet ein WebDAV-Server das Merken nicht mehr an. |
| Querencia Dateien: echte Geräte ungeprüft | Laufwerke und Netzlaufwerke sind nur mit Abbildern und Testservern geprüft, nicht mit echten USB-Geräten. |
| Schnatter: keine Anrufe | Die Web-Engine von Ubuntu ist ohne WebRTC gebaut. |
| Schnatter: Meldungen nur bei offenem Fenster | Schließen beendet Schnatter; ein Symbol im Infobereich zeigt Schnatter noch nicht. |
| Schnatter: mit echtem Konto ungeprüft | Geprüft sind Umzug, Anmeldeseite und Fenster, nicht die Arbeit mit einem echten Konto. |
| Bildbetrachter: Nebenfenster ohne Titelleiste | Ein zum zweiten Mal geöffneter Dialog erscheint ohne Titelleiste. |
| Terminal: Einfügen mit der mittleren Maustaste | Eine Auswahl aus einem anderen Programm kommt nicht immer an. |
| Dokumentenbetrachter: Drucken | Auf einen echten Drucker noch nicht geprüft. |
| Benachrichtigungen ohne Mitteilungszentrale (QD-073) | In Arbeit; bis dahin „Nicht stören“ über die Kommandozeile. |
| Blasse Textreste beim Seitenwechsel (QD-070, P2) | Ein Zeichenfehler von GTK 4.22; die Sitzung schaltet ihn ab, ein Bericht an GTK steht aus. |

## Hardware und virtuelle Maschinen

| Punkt | Was das heißt |
|---|---|
| Treiberwechsel ungeprüft | Die Seite „Treiber“ ist nur mit nachgebildeten Karten geprüft. Ein echter Wechsel auf den NVIDIA-Treiber, Rechner mit zwei Grafikkarten und Secure Boot sind ungeprüft. Ein Wechsel braucht `ubuntu-drivers-common`, Netz und Passwort und wirkt erst nach einem Neustart. Vorher einen Snapshot anlegen. |
| Falsche Auflösung nach dem Start einer VM (QD-027, P2) | Die durchgereichte Grafik meldet manchmal keine Bildschirmdaten; den Bildschirm kurz ab- und wieder anstecken hilft. |
| Ton in VMs | Ohne Soundkarte zeigt der Lautstärkeregler nur „Dummy Output“. |
| Alt+Druck in VMs | Kam bei der Probe nicht an; an echter Hardware zu prüfen. |
| Panel und Arbeitsfläche einmal ohne Spur beendet (QD-025, P1) | Am 18.10. einmal beobachtet, Ursache unbekannt. Abhilfe: Strg+Alt+Entf → Abmelden, dann neu anmelden. |
