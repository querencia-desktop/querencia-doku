# Alpha 1 – Kurztext für die Webseite

Vorlage für den Alpha-Abschnitt von querencialinux.org (Stand 20.10.2026).
Ausführlich: [Release-Notes Alpha 1](alpha-1.md).

---

## Alpha 1: zum Ausprobieren auf Ubuntu 26.04

Querencia Desktop Alpha 1 ist die erste Testfassung: 20 Debian-Pakete für
Ubuntu 26.04, als Desktop- oder Server-Installation. Querencia ersetzt GNOME
nicht, es steht daneben. GDM bleibt der Anmeldebildschirm und bietet nach
einem Neustart „Querencia Desktop“ im Zahnrad an.

**Neu in Alpha 1:** eine Mitteilungszentrale mit Verlauf und Glocke im Panel,
Systemeinstellungen auf Deutsch und Englisch mit Sprache und Region und
mehreren Tastaturbelegungen, eine Fensterliste je Arbeitsfläche, Bildschirm
sperren im Panel, ein Knopf „Arbeitsfläche anzeigen“ (Super+D), Vollbild mit
Super+F, eine Archivverwaltung und ein PDF-Betrachter. Ein eigener
Anmeldebildschirm liegt als optionales Paket bei.

**Geprüft:** Die Pakete bestehen die Pflichtprobe auf einem frischen Ubuntu
26.04, mit Anmeldung an der Textkonsole und über GDM. Neben Ubuntu Desktop
lassen sie sich installieren und wieder entfernen; danach sind die
installierten Pakete wie vorher.

**Installation:** folgt mit der APT-Quelle unter `dl.querencialinux.org/apt`.
Bis dahin gibt es keinen Download.

**Bekannte Grenzen:** Auf Ubuntu Server braucht Querencia Software
NetworkManager als netplan-Renderer, sonst kann es nichts installieren. Der
Anmeldebildschirm ist englisch. Das Terminal hat noch keine Reiter, und eine
dunkle Darstellung fehlt; beides ist in Arbeit.

> **Alpha:** nur für Testsysteme, am besten eine virtuelle Maschine mit
> Snapshot. Keine Garantie für Sicherheit oder Daten.
