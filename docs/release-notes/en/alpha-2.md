# Querencia Desktop – Alpha 2

**As of:** 21 October 2026, draft · **Status:** internal alpha, not
published · Values marked “open” are not yet confirmed or not yet decided.

Alpha 2 brings the state of the development environment of 21 October 2026
into the package repository: a **dark appearance** for the whole desktop,
more readable colours in the light appearance, **tabs in the terminal** and
a file manager that no longer contacts update servers. Like Alpha 1 it
consists of 20 Debian packages for Ubuntu 26.04 (“resolute”) from the same
signed APT repository.

> **Alpha.** Meant for test systems, not for everyday use. No guarantee
> regarding security or data loss. Try it on a virtual machine with a
> snapshot first.

## New in Alpha 2

- **Dark appearance.** In System Settings → Appearance, switch on “Prefer
  dark appearance”: the Querencia-Klassisch theme 0.2.1 now has a dark
  variant, and the panel, the desktop and the Querencia programs follow it –
  except Querencia Files, which keeps its own light theme for now. Switching
  it off restores the light appearance. Running programs change at once,
  so does the panel; the labwc window frames stay light.
- **Contrast in the light appearance** raised to WCAG AA: keyboard
  shortcuts in menus, the memory mark in the calculator, the empty-state
  hint in the image viewer, notification text, the chart colours of the
  system monitor, shortcuts and selection in System Settings.
- **Tabs in the terminal** (Querencia Terminal 0.3.0) as in GNOME Terminal
  2.x: Ctrl+Shift+T opens a tab, Ctrl+Shift+W closes it, Ctrl+Page Up/Down
  switches, Alt+1 to Alt+9 jumps directly. The tab bar appears from the
  second tab on. The keyboard shortcut overview (Super+?) lists the new
  shortcuts.
- **Files without update checks.** Querencia Files no longer asks GitHub or
  the AUR for new versions and shows no update notice; updates come only
  through apt. “Extract here” uses Querencia Archiv, the About dialog shows
  the Querencia icon.
- **Icons 0.7:** an icon of its own for the “Show desktop” button and
  program icons for Archiv, Software, Dateisuche (file search), Rechner
  (calculator) and the shortcut overview in the icon theme.
- **Secondary windows keep their title bar:** image information, Find and
  Replace in the editor and the dialogs of the PDF viewer also have a title
  bar when opened a second time; so does the selection window of the
  screenshot tool after cancelling with Esc.
- **System Settings 0.1.3:** resetting no longer leaves default values in
  the labwc configuration, backup files are limited.

## Versions

Package set of 21 October 2026 (20 packages), built from the state that was
active in the development environment at 18:52 that day.

| Package | Version | Contents |
|---|---|---|
| querencia-desktop | 0.1.0~alpha2-7 | metapackage: pulls in all parts |
| labwc | 0.9.8-0querencia5 | backport of the window manager (unchanged, new revision) |
| querencia-session | 0.1.0~alpha7-2 | session starter (unchanged, new revision) |
| querencia-shell | 0.1.0~alpha7-1 | panel 0.2.1, desktop 0.2.0, shortcut overview 0.2.0, Querencia-Klassisch theme 0.2.1 light and dark |
| querencia-sitzung | 0.1.3-3 | session tools 0.1.3 (unchanged, new revision) |
| querencia-benachrichtigungen | 0.2.2-1 | notifications 0.2.2 |
| querencia-einstellungen | 0.1.3-1 | System Settings 0.1.3 |
| querencia-symbole | 0.7-1 | program icons and the “Querencia” icon theme |
| querencia-files | 0.1.0~alpha5-1 | Querencia Files, state QF-0q-1 |
| querencia-terminal | 0.3.0-1 | Querencia Terminal 0.3.0 with tabs |
| querencia-editor | 0.2.3-1 | text editor 0.2.3 |
| querencia-bilder | 0.2.5-1 | image viewer 0.2.5 |
| querencia-dokumente | 0.1.2-1 | PDF viewer 0.1.2 |
| querencia-archiv | 0.1.1-1 | archive manager 0.1.1 |
| querencia-rechner | 0.1.5-1 | calculator 0.1.5 |
| querencia-systemmonitor | 0.1.4-1 | system monitor 0.1.4 |
| querencia-dateisuche | 0.1.4-1 | search for files 0.1.4 |
| querencia-screenshot | 0.2.9-1 | screenshot 0.2.9 |
| querencia-software | 0.1.4-1 | install programs through PackageKit, 0.1.4 |
| querencia-anmeldung | 0.1.1-2 | login screen, optional (unchanged from Alpha 1) |

Not in Alpha 2: the new backgrounds (licence review open).

## Upgrading from Alpha 1

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

Then log out and log in again so that the panel and the desktop start the
new version.

## New installation

Unchanged from Alpha 1: add the repository, `sudo apt install
querencia-desktop`, reboot, choose “Querencia Desktop” from the gear menu
(see [Alpha 1, Installation](alpha-1.md#installation), also for servers,
GNOME and removal). Fingerprint of the signing key: `63F6 C499 246E 3699
CA04 726D 342F 12D2 0CE7 1CBD`.

## Known limitations

Still valid from Alpha 1: login screen in English, Alt+Print in VMs, the
network applet needs NetworkManager, Firefox as a snap ignores the GTK
theme, gsettings values are shared with GNOME, greetd stays after removing
`querencia-anmeldung`. New or changed:

- **Window frames and Files stay light:** labwc draws the frames with its
  own theme, Querencia Files has a theme of its own; dark variants for both
  are follow-up items.
- After switching between light and dark in a running program, the
  keyboard focus may sit somewhere else than after a start.
- Fixed since Alpha 1: terminal without tabs, no dark appearance, secondary
  windows without title bar, Strata logo in the About dialog of Files,
  default values in `rc.xml` after resetting.

## Tested

- Every source is a tagged state; for every program it is shown that the
  program running in the development environment was built from exactly
  this state.
- Static package check, Lintian without errors, trial installation in an
  isolated copy of the system: **open** (results follow).
- **Mandatory test on a fresh Ubuntu 26.04** (text console and GDM, plus
  dark appearance, terminal tabs, Files without update notice, light
  contrast): **open**.

## Licences and origin

As in Alpha 1. New: the five program icons in the icon theme (Archiv,
Software, Dateisuche, Rechner, shortcut overview) are licensed like their
programs under GPL-3.0-or-later; the rest of the icon theme under
CC-BY-SA-4.0. The name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.

