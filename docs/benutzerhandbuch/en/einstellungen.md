# System Settings (Querencia Einstellungen)

[Back to contents](index.md)

**Start:** System → Einstellungen (Preferences) → Systemeinstellungen, or
right-click the desktop → “Hintergrund der Arbeitsfläche ändern …” (change
desktop background).

The settings are available in German and English; the area names are given
in English with the German name in brackets.

![System Settings, area Appearance (German interface)](../bilder/de-einstellungen.png)

The list of areas is on the left, the chosen area on the right. Changes apply
after **Apply** (Übernehmen); “Restore Defaults” restores the
Querencia default. Before changing a configuration file the settings make a
backup.

## The areas

**Appearance (Erscheinungsbild)**
- Icon theme (e.g. Querencia, GNOME-Human, MATE) with preview, controls theme
  (Querencia-Klassisch or the built-in GTK theme), “Prefer dark appearance”,
  mouse pointer (theme and size 24/32/48).
- Takes effect at once in all GTK programs, the panel and the desktop.
- **Dark appearance:** since Alpha 2 the Querencia-Klassisch theme has a dark
  variant. The panel, the desktop and the Querencia programs follow it;
  running programs and the panel change at once, switching it off restores
  the light appearance. For now the window frames (labwc), Querencia Files,
  Screenshot and a few dialogs (session dialog, shortcut overview, the
  terminal's bars) stay light. Third-party GTK 3 programs do not follow the
  setting.

**Background Image (Hintergrundbild)**
- Gallery of the included backgrounds with preview; a click selects, Apply
  sets it. The 16:9 or 4:3 version is chosen to match the screen.
- “Background …” for an own picture, a plain colour and the placement (e.g.
  centred, tiled).

**Desktop Icons (Symbole der Arbeitsfläche)**
- Show or hide Computer, Home and Trash; icon size.
- Which drives appear: removable drives, optical media, network drives,
  internal drives.

**Window Design (Fensterdesign)**
- Window theme, corner radius, shadow, order of the title bar buttons, title
  bar font.

**Fonts (Schriften)**
- Font for applications, documents and the monospace font; window title font
  (points to “Window Design”).

**Panels**
- Shows the saved panel layout and explains how to change it in the panel
  itself (right-click “Zum Panel hinzufügen …” (Add to Panel), moving, “Aus
  dem Panel entfernen” (Remove from Panel)). Nothing can be changed here
  yet.

**Keyboard (Tastatur)**
- Keyboard layout from all layouts and variants (with search), repeat delay,
  repeat rate, Num Lock.
- “Additional Layouts and Switching”: with several layouts the switch key
  changes to the next one in turn; after login the first one applies. The
  panel does not show the active layout yet.

**Mouse (Maus)**
- Double-click time, speed, acceleration, left-handed, natural scrolling,
  mouse pointer.

**Screen (Bildschirm)**
- Per screen resolution, refresh rate, rotation, scale and arrangement.
- After applying, a dialog asks “Keep Screen Settings?”. Without
  confirmation within 15 seconds the previous state returns. Saved settings
  also apply at the next login.

**Workspaces (Arbeitsflächen)**
- Number (1 to 12), own names, on-screen display when switching and its
  duration.

**Default Applications (Standardanwendungen)**
- Which program opens web pages, e-mail, text, images, music, video, folders,
  PDF and archives. The terminal is only shown.

**Language and Region (Sprache und Region)**
- Display language (language of menus and texts) and formats (date and time,
  numbers, currency, paper, units).
- Takes effect from the next login; programs that are already running keep
  their language.

**About Querencia (Informationen über Querencia)**
- Versions of the settings, of the system and of labwc.

## When does a change take effect?

Most changes take effect at once. Settings read by the window manager
(keyboard, mouse, window design, title font) are reloaded by labwc on Apply;
layout and key repeat then apply immediately. Only Num Lock takes effect at
the next login or when a keyboard is plugged in.

## Not included yet

Power, startup programs and a writable “Panels” area are still missing. The
settings themselves are available in German and English.
