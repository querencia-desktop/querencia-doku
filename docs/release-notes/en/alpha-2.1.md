# Querencia Desktop – Alpha 2.1

**As of:** 22 October 2026 ·
**Status:** in the APT repository since 22 October 2026, 11:16

Alpha 2.1 is a maintenance release between Alpha 2 and Alpha 3. Every
program now has a **common About dialog** and a **Help menu** with online
help and "Report a problem". Files can be **dragged out of the trash** to
restore them and **dragged into the terminal**. The dark style reaches
further, the **panel restarts itself after a crash**, and the login screen
speaks German. Again 21 Debian packages for Ubuntu 26.04 ("resolute") from
the same signed APT repository.

> **Alpha.** Meant for test systems, not for daily use. No guarantee
> against security problems or data loss. Try it in a virtual machine with
> a snapshot first.

## New in Alpha 2.1

- **About dialog and Help in every program.** Each Querencia program shows
  "Alpha – not ready for daily use", the website querencialinux.org,
  copyright and licence. The Help menu has "Online help" (documentation in
  the language of the interface) and "Report a problem"; both open the
  browser. "About Querencia" in the panel and in Settings shows the
  installed release, "Querencia Desktop Alpha 2.1".
- **Release file.** The metapackage installs `/usr/share/querencia/version`
  and `/usr/share/querencia/release` (same format as `/etc/os-release`). The
  About dialogs read the release name and the help and bug report addresses
  from it.
- **Restore from the trash by dragging.** Dragging a file from the trash into
  a folder, the sidebar or onto the desktop restores it; Ctrl+Z undoes it
  (Querencia Files).
- **Drag files into the terminal.** Files dragged from Files are inserted at
  the cursor as single-quoted paths, as in GNOME Terminal; nothing runs
  until you press Enter (Terminal 0.3.2).
- **Desktop:** context menu as in GNOME 2 (Open with, Cut, Copy, Paste,
  Rename, Move to trash, Properties), Ctrl+X/C/V, Delete and Shift+Delete
  with confirmation; files can be dragged between desktop, Files and the
  trash. Icon labels sit **without the dark plate** on the wallpaper again,
  white with a shadow as in GNOME 2.
- **Dark style goes further:** the screenshot tool (selection window and
  editor), the keyboard shortcut overview, the terminal's menu and tab bars,
  and the "End session" dialog, confirmations and password prompt when the
  dark style is already on at login.
- **The panel restarts after a crash.** It runs under a small watchdog that
  restarts it after a crash, at most three times in ten minutes. It also
  reloads the icon theme less often, which fixes a crash after installing or
  changing programs.
- **Screen lock and videos.** Browsers and video players can hold off the
  idle lock while they play (`org.freedesktop.ScreenSaver` service).
- **Login screen in German.** The optional login screen `querencia-anmeldung`
  uses the system language, shows date and time in the format of that
  language, and its greeting names the installed release.
- **Network settings.** Settings has a "Network" page, and "Network
  settings …" in the panel's network icon opens it.
- **Fonts for Asian characters.** The metapackage recommends
  `fonts-noto-core` and `fonts-noto-cjk`, so window titles with Chinese,
  Japanese or Korean characters no longer show boxes. With
  `--no-install-recommends` they are left out.

## Versions

Package set of 22 October 2026 (21 packages).

| Package | Version | Contents |
|---|---|---|
| querencia-desktop | 0.1.0~alpha2.1-1 | Metapackage: pulls in everything, release file, recommends Noto fonts |
| labwc | 0.9.8-0querencia5 | Backport of the window manager (unchanged since Alpha 2) |
| querencia-session | 0.1.0~alpha7-3 | Session starter; panel under its watchdog |
| querencia-shell | 0.1.0~alpha8-1 | Panel 0.2.3, desktop 0.2.4, shortcut overview 0.2.1, theme Querencia-Klassisch 0.2.1 |
| querencia-hintergruende | 0.2-1 | 16 wallpapers (unchanged since Alpha 2) |
| querencia-sitzung | 0.1.4-1 | Session dialog, lock, password prompt, screensaver service |
| querencia-benachrichtigungen | 0.2.2-1 | Notifications (unchanged since Alpha 2) |
| querencia-einstellungen | 0.1.5-1 | Settings with a "Network" page and release information |
| querencia-symbole | 0.7-1 | Program icons and icon theme (unchanged since Alpha 2) |
| querencia-files | 0.1.0~alpha7-1 | Querencia Files: drag from the trash, About with package version |
| querencia-terminal | 0.3.2-1 | Terminal: drop files in, dark bars |
| querencia-editor | 0.2.4-1 | Text editor |
| querencia-bilder | 0.2.6-1 | Image viewer |
| querencia-dokumente | 0.1.4-1 | PDF viewer |
| querencia-archiv | 0.1.2-1 | Archive manager |
| querencia-rechner | 0.1.6-1 | Calculator |
| querencia-systemmonitor | 0.1.5-1 | System monitor |
| querencia-dateisuche | 0.1.5-1 | Search for files |
| querencia-screenshot | 0.2.10-1 | Screenshot tool, dark |
| querencia-software | 0.1.5-1 | Install programs via PackageKit |
| querencia-anmeldung | 0.1.2-1 | Login screen in German, optional |

Checksum of the package list (SHA256SUMS): `d990d65f791e50d20acd56a8210a91de50d4cbdb13f20cd4541029e43ab7ed50`.

## Upgrading from Alpha 2

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

Then log out and log in again: only then do the panel and the desktop start
in the new version, with the panel under its watchdog. There is no question
about configuration files unless you changed `/etc/querencia/labwc/`
yourself. With recommends, APT also fetches the two Noto font packages,
about 75 MB according to the Ubuntu index.

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`, reboot,
choose "Querencia Desktop" at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Signing key fingerprint:
`63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`. On a server image APT
installs about 389 packages.

## Known limitations

Still valid from Alpha 2: network applet only with NetworkManager, Firefox
as a snap without the GTK theme, shared gsettings values next to GNOME,
greetd stays after removing `querencia-anmeldung`, provisional identifiers
(`org.example…`) for the panel and some programs. New or changed:

- **Files stays light**, as do labwc's window frames. Third-party GTK 3
  programs do not follow the dark style.
- **Panel, desktop and lock screen in German only.** The programs speak
  German and English.
- **The panel takes a few seconds to come back.** Ubuntu writes a crash
  report to `/var/crash` on every crash (about 17 MB for the panel); only
  then does the watchdog restart the panel, after about six seconds in the
  test. The cause of the crash on first opening "Applications" is still
  being investigated.
- **Not tested on real hardware**, only in virtual machines. Also untested:
  printing on a real printer, Windows shares (SMB), logging in through the
  optional login screen from the repository.
- Fixed since Alpha 2: login screen only in English; screenshot tool,
  shortcut overview and terminal bars light in dark style; panel did not
  restart after a crash; "Network settings" led nowhere.

## Reporting bugs

In the project's issue tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>, in German
or English; "Report a problem" in every program's Help menu leads there.
Please include:

- the output of `dpkg -l 'querencia-*' labwc`, `lsb_release -ds` and
  `cat /usr/share/querencia/version`
- what you did, what you expected, what happened
- about 50 lines from the matching log in `~/.local/state/querencia/`
  (panel: `panel.log`, session start: `sitzung-start.log`)

Please black out home paths, host names and IP addresses in the log first.
Do not report security issues publicly; use
<https://github.com/querencia-desktop/querencia/security/advisories/new>.

## Tested

- Every source is a tagged state.
- Static package check 242 passed, Lintian without errors, signed test
  repository, test installation in an isolated copy of the system 88 passed,
  including a forced panel crash with automatic restart.
- **Fresh Ubuntu 26.04** (virtual machine, 22 October 2026, text console):
  installation in about 64 s, session in about 3 s, check script in the session 28/28. Checked: About
  dialogs showing "Alpha 2.1", dragging files into the terminal, dragging out
  of the trash, dark style, and the panel restart after a forced crash.
- **Upgrade from Alpha 2** (virtual machine): Alpha 2 installed from the
  repository, then `apt full-upgrade` to Alpha 2.1 in about 19 s, no
  questions; after logging in again (just under 5 s) the new version runs
  with the panel watchdog.
- Not tested: login through GDM on Ubuntu Desktop with Alpha 2.1, screen lock
  and unlock, real hardware.

## Licences and origin

As in Alpha 2. The name and logo "Querencia" are not free content.

Copyright 2026 Querencia Desktop contributors.
