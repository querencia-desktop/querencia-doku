# Querencia Desktop – User Guide

**Status:** Alpha 2.1, 22 October 2026 · [Deutsche Fassung](../de/index.md)

Querencia Desktop is a classic desktop environment in the style of GNOME 2
(Ubuntu 10.04) for Wayland. It consists of the window manager labwc, two
panels, a desktop with icons and a set of its own programs (Rust and GTK 4).
Since Alpha 3.3 the interface is available in German, English, Italian,
Spanish and French (see [System Settings](einstellungen.md), “Language and
Region”); this guide is available in German and English. Parts that are
still German only are named on each page.

> **Alpha.** Querencia is under development. This guide describes the
> Alpha 2.1 package set of 22 October 2026 (see the
> [Alpha 2.1 release notes](../../release-notes/en/alpha-2.1.md)). There is no
> security or data-loss guarantee. Known gaps are listed under
> [Known limitations](bekannte-einschraenkungen.md).

## Contents

**Getting started**

- [Getting started](einstieg.md) – login, panels, menus, desktop, workspaces,
  windows, logging out
- [Keyboard shortcuts](tastenkuerzel.md) – all fixed shortcuts of the session
  and the programs

**Programs**

| Program | Menu | Page |
|---|---|---|
| Querencia Dateien (file manager, menu entry “Files”) | Orte (Places), Anwendungen → Zubehör (Applications → Accessories) | [dateien.md](dateien.md) |
| Querencia Terminal | Applications → Accessories | [terminal.md](terminal.md) |
| Text Editor | Applications → Accessories | [editor.md](editor.md) |
| Image Viewer | Applications → Grafik (Graphics) | [bilder.md](bilder.md) |
| Document Viewer (PDF) | Applications → Büro (Office) | [dokumente.md](dokumente.md) |
| Archive Manager | Applications → Accessories | [archiv.md](archiv.md) |
| Calculator | Applications → Accessories | [rechner.md](rechner.md) |
| System Monitor | Applications → Systemwerkzeuge (System Tools) | [systemmonitor.md](systemmonitor.md) |
| Search for Files… | Applications → Accessories | [dateisuche.md](dateisuche.md) |
| Take Screenshot | Print key, Applications → Accessories | [screenshot.md](screenshot.md) |
| System Settings | System → Einstellungen (Preferences) | [einstellungen.md](einstellungen.md) |
| Drivers (in the System Settings) | System → Systemverwaltung (Administration) | [einstellungen.md](einstellungen.md) |
| Software | System → Systemverwaltung (Administration) | [software.md](software.md) |
| Schnatter (WhatsApp Web, optional) | Applications → Internet | [schnatter.md](schnatter.md) |
| Notifications | runs in the background | [benachrichtigungen.md](benachrichtigungen.md) |
| Session: log out, lock, shut down | System, Ctrl+Alt+Del, Ctrl+Alt+L | [sitzung.md](sitzung.md) |

**Help**

- [Known limitations](bekannte-einschraenkungen.md)
- [Questions and answers](fragen-und-antworten.md)

## About this guide

The screenshots come from isolated test runs (own compositor without a
screen, throw-away user profile), never from a real user session; most are
1024×768. Some show an earlier version of the same program (for example light
instead of dark text on orange); the source of each picture is listed in
`../bilder/herkunft.txt`. Where a program has no English interface yet, the
German picture is shown. Texts: CC-BY-SA-4.0, see [LICENSE](../../../LICENSE).
The German version is the reference.
