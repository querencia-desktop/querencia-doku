# Software (Querencia Software)

[Zurück zum Inhalt](index.md)

**Starten:** System → Systemverwaltung → Software.

![Querencia Software, Detailseite (Prüflauf mit Testkatalog)](../bilder/de-software.png)

Programme suchen, installieren, entfernen und aktualisieren – über
PackageKit, also aus den Paketquellen des Systems (Ubuntu-Archiv).

## Was Software kann

- **Suchen** mit Sofortsuche, **Kategorien**, **Installiert**,
  **Aktualisierungen** und eine **Expertenliste** aller Pakete.
- **Detailseite** mit Beschreibung, Version, Größe, Lizenz und Homepage.
- **Installieren, Entfernen, Aktualisieren:** Vor dem Entfernen zeigt Software,
  welche Pakete mitgehen, und fragt nach. Der Fortschritt läuft im Fenster mit
  „Abbrechen“; man kann weiter blättern.
- Für jede Änderung am System fragt der Passwortdialog der Sitzung nach dem
  eigenen Passwort (Benutzer mit Administratorrechten).
- Klare Meldungen, wenn die Paketverwaltung gerade belegt ist, die
  Berechtigung fehlt oder kein Passwortdialog verfügbar ist.

## Nicht enthalten

Paketquellen verwalten, Bewertungen, Konten, Snap und Flatpak.

## Wenn Software „Keine Netzwerkverbindung“ meldet

Auf einem Ubuntu-Server-System verwaltet oft systemd-networkd das Netz,
NetworkManager aber nicht. PackageKit hält das System dann für offline und
lädt nichts herunter. Abhilfe in der Installationsanleitung: in
`/etc/netplan/*.yaml` unter `network:` die Zeile `renderer: NetworkManager`
ergänzen und `sudo netplan apply` ausführen. Software erkennt diesen Fall
selbst und zeigt einen Hinweis mit dieser Abhilfe.
