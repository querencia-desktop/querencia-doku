# Querencia Desktop – Alpha 2

**As of:** 21 October 2026, 22:10, draft for the frozen package set ·
**Status:** internal alpha, not published · Values marked “open” are not yet confirmed or not yet decided.

Alpha 2 brings the state of the development environment of 21 October 2026
into the package repository: a **dark appearance** for the whole desktop,
more readable colours in the light appearance, **16 new backgrounds**,
**tabs in the terminal** and a file manager that no longer contacts update
servers. It consists of 21 Debian packages for Ubuntu 26.04 (“resolute”) from the same
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
- **16 new backgrounds** in the new data package `querencia-hintergruende`:
  twelve motifs (deep blue, blue-green, blue glow, ember, hills, coast,
  dunes, lake, desert, mountains, beach, glass) and four variants with the
  Querencia logo, each in 2560×1440 and as a separate 4:3 crop. **The
  default background is deep blue (“Tiefblau”).** The pictures were
  generated with FLUX1.1 [pro] Ultra (Black Forest Labs) through fal.ai and
  selected by the project owner; the logo was added afterwards by a
  script, never painted by the AI. System Settings 0.1.4 show them as a
  gallery, and the icon labels on the desktop (desktop 0.2.1) have a
  backing so they stay readable on every picture.
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
- **System Settings 0.1.4:** background gallery; resetting no longer leaves default values in
  the labwc configuration, backup files are limited.

## Versions

Package set of 21 October 2026 (21 packages), built from the state that was
active in the development environment at 21:43 that day.

| Package | Version | Contents |
|---|---|---|
| querencia-desktop | 0.1.0~alpha2-7 | metapackage: pulls in all parts |
| labwc | 0.9.8-0querencia5 | backport of the window manager (unchanged, new revision) |
| querencia-session | 0.1.0~alpha7-2 | session starter (unchanged, new revision) |
| querencia-shell | 0.1.0~alpha7-1 | panel 0.2.1, desktop 0.2.2, shortcut overview 0.2.0, Querencia-Klassisch theme 0.2.1 light and dark, the 17 backgrounds of Alpha 1 |
| querencia-hintergruende | 0.2-1 | 16 backgrounds (default deep blue), new |
| querencia-sitzung | 0.1.3-3 | session tools 0.1.3 (unchanged, new revision) |
| querencia-benachrichtigungen | 0.2.2-1 | notifications 0.2.2 |
| querencia-einstellungen | 0.1.4-1 | System Settings 0.1.4 with background gallery |
| querencia-symbole | 0.7-1 | program icons and the “Querencia” icon theme |
| querencia-files | 0.1.0~alpha6-1 | Querencia Files, state QF-0r-1 |
| querencia-terminal | 0.3.0-1 | Querencia Terminal 0.3.0 with tabs |
| querencia-editor | 0.2.3-1 | text editor 0.2.3 |
| querencia-bilder | 0.2.5-1 | image viewer 0.2.5 |
| querencia-dokumente | 0.1.3-1 | PDF viewer 0.1.3 (no blank pages after the PDF is rewritten) |
| querencia-archiv | 0.1.1-1 | archive manager 0.1.1 |
| querencia-rechner | 0.1.5-1 | calculator 0.1.5 |
| querencia-systemmonitor | 0.1.4-1 | system monitor 0.1.4 |
| querencia-dateisuche | 0.1.4-1 | search for files 0.1.4 |
| querencia-screenshot | 0.2.9-1 | screenshot 0.2.9 |
| querencia-software | 0.1.4-1 | install programs through PackageKit, 0.1.4 |
| querencia-anmeldung | 0.1.1-3 | login screen, optional (unchanged, new revision) |

Checksum of the package list (SHA256SUMS): `5cbe6f81fbb58017b50bf340c1bd2c65120b27718e2b7a929986d5de3c3c183d`.

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
- **Third-party GTK 3 programs do not follow the dark appearance:** GTK 3
  ignores the “Prefer dark appearance” setting; all Querencia programs use
  GTK 4 and follow it.
- After switching between light and dark in a running program, the
  keyboard focus may sit somewhere else than after a start.
- **Panel crash in a test run:** in one test run the panel crashed the
  first time the Applications menu was opened and did not restart by
  itself; logging out and back in restores it. The cause is being
  investigated.
- Fixed since Alpha 1: terminal without tabs, no dark appearance, secondary
  windows without title bar, Strata logo in the About dialog of Files,
  default values in `rc.xml` after resetting.

## Reporting bugs

In the project's bug tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>,
in English or German. Please include:

- output of `dpkg -l 'querencia-*' labwc` and `lsb_release -ds`
- what you did, what you expected, what happened
- about 50 lines from the matching log in `~/.local/state/querencia/`
  (session start: `sitzung-start.log`)

Please redact home paths, host names and IP addresses in the log first.
Do not report security vulnerabilities publicly, but via
<https://github.com/querencia-desktop/querencia/security/advisories/new>.

## Tested

- Every source is a tagged state; for every program it is shown that the
  program running in the development environment was built from exactly
  this state (panel and shortcut overview rebuilt byte-identical).
- Static package check 242 passed, Lintian without errors, signed test
  repository, trial installation in an isolated copy of the system 87
  passed (including the dark variant for GTK 4 and GTK 3).
- **Mandatory test on a fresh Ubuntu 26.04**, passed on 21 October 2026:
  - login on the **text console (tty1)** and through **GDM** on Ubuntu
    Desktop: installation, session, check script inside the session
    (28/28), new login after logging out in about 6 s;
  - dark appearance switched on and off (panel and programs change at
    once), terminal with three tabs, Files without update notice and
    without network connection, notification, shortcut overview, PDF viewer
    after the file was rewritten;
  - measurements: settings portal answers in 7–12 ms, panel and desktop
    1.1–1.3 s after the window manager.
  - Not tested: login through querencia-anmeldung (unchanged since Alpha
    1), real hardware, SMB shares, copy and paste in the terminal.

## Licences and origin

As in Alpha 1. New:

- **Backgrounds 0.2:** CC-BY-SA-4.0 with an AI caveat (pictures generated
  purely by AI may not be protected by copyright in every jurisdiction;
  the licence statement is then a notice). For the four logo variants only
  the base picture is free; the name and logo “Querencia” fall under the
  project's trademark rule. The origin of every picture is described in
  `/usr/share/doc/querencia-hintergruende/herkunft.md`.
- The five program icons in the icon theme (Archiv, Software, Dateisuche,
  Rechner, shortcut overview) are licensed like their programs under
  GPL-3.0-or-later; the rest of the icon theme under CC-BY-SA-4.0.

The name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
