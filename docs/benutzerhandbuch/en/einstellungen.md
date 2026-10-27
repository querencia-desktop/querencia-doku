# System Settings (Querencia Einstellungen)

[Back to contents](index.md)

**Start:** System → Einstellungen (Preferences) → Systemeinstellungen, or
right-click the desktop → “Hintergrund der Arbeitsfläche ändern …” (change
desktop background).

The settings are German only for now; the area names are given in German with
a translation.

![System Settings, area Erscheinungsbild (appearance)](../bilder/de-einstellungen.png)

The list of areas is on the left, the chosen area on the right. Changes apply
after **Übernehmen** (Apply); “Standard wiederherstellen” restores the
Querencia default. Before changing a configuration file the settings make a
backup.

## The areas

**Erscheinungsbild (appearance)**
- Icon theme (e.g. Querencia, GNOME-Human, MATE) with preview, controls theme
  (Querencia-Klassisch or the built-in GTK theme), “prefer dark appearance”,
  mouse pointer (theme and size 24/32/48).
- Takes effect at once in all GTK programs, the panel and the desktop. The
  dark appearance only changes programs that evaluate it; the Querencia
  programs keep their theme.

**Hintergrundbild (background)**
- Gallery of the included backgrounds with preview; a click selects, Apply
  sets it. The 16:9 or 4:3 version is chosen to match the screen.
- “Hintergrund …” for an own picture, a plain colour and the placement (e.g.
  centred, tiled).

**Symbole der Arbeitsfläche (desktop icons)**
- Show or hide Computer, Home and Trash; icon size.
- Which drives appear: removable drives, optical media, network drives,
  internal drives.

**Fensterdesign (window design)**
- Window theme, corner radius, shadow, order of the title bar buttons, title
  bar font.

**Schriften (fonts)**
- Font for applications, documents and the monospace font; window title font
  (points to “Fensterdesign”).

**Panels**
- Shows the saved panel layout and explains how to change it in the panel
  itself (right-click “Zum Panel hinzufügen …”, moving, “Aus dem Panel
  entfernen”). Nothing can be changed here yet.

**Tastatur (keyboard)**
- Keyboard layout from all layouts and variants (with search), repeat delay,
  repeat rate, Num Lock.
- Several layouts with a switch key are not available yet.

**Maus (mouse)**
- Double-click time, speed, acceleration, left-handed, natural scrolling,
  mouse pointer.

**Bildschirm (display)**
- Per screen resolution, refresh rate, rotation, scale and arrangement.
- After applying, a dialog asks whether to keep the settings. Without
  confirmation within 15 seconds the previous state returns. Saved settings
  also apply at the next login.

**Arbeitsflächen (workspaces)**
- Number (1 to 12), own names, on-screen display when switching and its
  duration.

**Standardanwendungen (default applications)**
- Which program opens web pages, e-mail, text, images, music, video, folders,
  PDF and archives. The terminal is only shown.

**Language and Region**
- **Display Language:** language of menus and texts. Since Alpha 3.3 there
  are German, English, Italian, Spanish and French. Only languages for
  which a locale is installed are offered; the package `locales-all`,
  recommended by Querencia Desktop since Alpha 3.3, brings all of them
  (about 230 MB). Programs without a translation show English.
- **Formats:** date and time, numbers, currency, paper and units, also
  different from the display language.
- Effective from the next login; programs that are already running keep
  their language. Texts of GTK itself (e.g. in the file dialog) come from
  the system's language pack, `language-pack-gnome-<xx>`, for example
  `sudo apt install language-pack-gnome-it`; without it they stay English.

**Informationen über Querencia (about)**
- Versions of the settings, of the system and of labwc.

## When does a change take effect?

Most changes take effect at once. Settings read by the window manager
(keyboard, mouse, window design, title font) are reloaded by labwc on Apply;
layout and key repeat then apply immediately. Only Num Lock takes effect at
the next login or when a keyboard is plugged in.

## Not included yet

Power, startup programs and a writable “Panels” area will follow in later
versions.
