# Querencia Desktop – Alpha 3

**As of:** 24 October 2026 · **Status:** in the APT repository since 24 October 2026, 12:18

With Alpha 3 Querencia gets its **own file manager: Querencia Dateien**
0.2.0, a beta. It follows Nautilus 2.30 – menu bar, toolbar, path bar, side
pane “Places”, status bar – and brings tabs, three views, thumbnails, a name
search and “Connect to Server…”. Querencia Dateien is now the program for
folders; the earlier Querencia Files (a fork of Strata) is retired. There
are 22 Debian packages for Ubuntu 26.04 (“resolute”) from the same
signed APT repository.

> **Alpha.** Meant for test systems, not for daily use. No security or
> data-loss guarantees. Try it in a virtual machine with a snapshot first.
> Querencia Dateien itself carries the stage “beta”.

## New in Alpha 3

- **Querencia Dateien 0.2.0 (beta).** Applications → Accessories → “Files”
  (in the German interface „Querencia Dateien“), the Places menu of the
  panel and the folder and drive icons on the desktop open it. It copies,
  moves and deletes with progress, cancel and a question for equal names,
  has a trash with restore, drives with mount and eject, “Open With”, a
  Properties dialog with permissions and preferences in five tabs that apply
  at once. German and English, light and dark. On top of that:
  - **Network:** “Network” shows the computers on the local network, each
    only once. **File → Connect to Server…** opens SFTP servers, Windows
    shares (SMB), FTP and WebDAV, optionally with a bookmark. The password is
    asked for when connecting and only kept in the keyring if you want. For
    an unknown SFTP server Dateien shows the fingerprint of the server key
    before the password; “Connect Anyway” has to be chosen explicitly. A
    message explains errors in one sentence.
  - **Thumbnails and search:** images show thumbnails, from the same cache
    as other programs; adjustable under Preferences → Preview (Always, Local
    files only, Never; size limit). Third-party thumbnailers, for PDF for
    example, only run sandboxed with `bubblewrap`. **Ctrl+F** searches names
    from the folder shown; “Advanced Search…” hands over to Search for Files.
  - **Tabs and compact view:** Ctrl+T opens a tab, the middle mouse button
    opens folders in a tab behind the current one; the tab bar and the
    “Tabs” menu appear with two or more tabs. Besides icons and list there
    is the compact view (Ctrl+3).
- **Querencia Files is retired.** Folders open in Querencia Dateien, also
  through an older own choice in `~/.config/mimeapps.list`. Launchers and
  panel buttons that still point to Files open Querencia Dateien.
  The package `querencia-files` becomes a transitional package: the Files
  program and the command `querencia-files` go away with the upgrade, the
  two hidden starters stay and open Querencia Dateien.
  Both share the bookmarks (`~/.config/gtk-3.0/bookmarks`). Dateien does not
  take over the Files settings after an upgrade from Alpha 2.1 (see Known
  limitations).
- **Shortcuts differ from Files.** In Querencia Dateien:

  | Action | Querencia Files | Querencia Dateien |
  |---|---|---|
  | Icon view | Ctrl+2 | **Ctrl+1** |
  | List view | Ctrl+3 | **Ctrl+2** |
  | Compact view | – | **Ctrl+3** |
  | Column view | Ctrl+1 | dropped (becomes list) |
  | Add bookmark | – | **Ctrl+D** (in Files: duplicate) |
  | Side pane on/off | Ctrl+B | **F9** |
  | Search | Ctrl+K | **Ctrl+F** |
  | Reload | Ctrl+R | Ctrl+R or **F5** |
  | Preferences | Ctrl+, | no shortcut, Edit → Preferences |
  | Undo, redo | Ctrl+Z, Ctrl+Shift+Z | not available yet |
  | Delete permanently | Shift+Del | Shift+Del, called “Delete…”, asks first |

  In the German interface, what Files called „Tab“ is now **„Reiter“**.
  Still valid among others: Ctrl+T new tab, Ctrl+W closes the tab (the last
  one the window), Ctrl+N new window, Ctrl+L enter location, Ctrl+H hidden
  files, Alt+↑ parent folder. Super+? shows all shortcuts.
- **Panel 0.3.2:** the Places menu opens folders with the session's folder
  program and knows Querencia Dateien even without a default set.
- **Keyboard shortcut overview 0.2.2:** Super+? shows the block „Querencia
  Dateien“ with all shortcuts instead of the Files block.
- **Sitzung 0.1.8:** after polkitd restarts, for example during
  an update, the password dialog for administrative tasks registers with the
  new polkitd by itself; until now such requests then failed without a
  dialog.
- **Software OpenGL with zink on nouveau** (session starter 0.1.0~alpha10): when OpenGL runs over zink on an
  NVIDIA card with the free nouveau driver, the session starter gives the
  session's programs software OpenGL (llvmpipe). In testing, Firefox froze
  otherwise; with software OpenGL it runs, at the cost of CPU work. The window manager itself stays
  unchanged. Controlled in `~/.config/querencia/grafik.ini` (`[Grafik]
  Software-OpenGL = automatisch|an|aus`), logged in
  `~/.local/state/querencia/sitzung-start.log`.
- **Desktop 0.3.0:** copying, moving and deleting on the desktop with
  progress, cancel and the same question for equal names as in Querencia
  Dateien; newly plugged-in USB sticks and inserted CDs are mounted without
  opening a window; Computer, Trash and drives open in Dateien.
- **From the Alpha 2.2 state, which was not released on its own:** the cause of the panel crashes when opening „Anwendungen“
  (Applications) is fixed; the dark appearance also switches window borders
  and GTK 3 programs; while locked, the screen turns off after two minutes;
  „Ausschalten …“ (Shut Down) offers „Neu starten“ (Restart); the panel and
  the desktop also speak English; display settings per monitor; the panel
  registers under its final identifier `org.querencia.Panel`.
- **Symbole 0.8:** own program icon for Querencia Dateien.

## Versions

Package set of 24 October 2026 (22 packages).

| Package | Version | Content |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3-1 | Meta package: pulls in Querencia Dateien instead of Files, version file “Alpha 3” |
| querencia-dateien | 0.2.0-1 | **new:** file manager Querencia Dateien 0.2.0 (beta) |
| querencia-files | 0.2.0-1 | **Transitional package:** Files goes away, two hidden starters open Querencia Dateien |
| querencia-shell | 0.1.0~alpha10-1 | Panel 0.3.2, desktop 0.3.0, keyboard shortcut overview 0.2.2, theme 0.2.2 |
| querencia-session | 0.1.0~alpha10-1 | Session starter: folders open in Querencia Dateien, software OpenGL for NVIDIA with nouveau |
| querencia-sitzung | 0.1.8-1 | Session dialog, lock, password dialog; survives a restart of polkitd |
| querencia-symbole | 0.8-1 | Program icons and icon theme, new: the Dateien icon |
| querencia-dateisuche | 0.1.5-2 | Search for Files; recommends Querencia Dateien instead of Files (program unchanged) |
| querencia-einstellungen | 0.1.6-1 | System settings (new since Alpha 2.1) |
| querencia-benachrichtigungen | 0.2.2-1 | Notifications (unchanged since Alpha 2) |
| querencia-hintergruende | 0.2-1 | 16 backgrounds (unchanged since Alpha 2) |
| labwc | 0.9.8-0querencia5 | Backport of the window manager (unchanged since Alpha 2) |
| querencia-terminal | 0.3.2-1 | Terminal (unchanged since Alpha 2.1) |
| querencia-editor | 0.2.4-1 | Text editor (unchanged since Alpha 2.1) |
| querencia-bilder | 0.2.6-1 | Image viewer (unchanged since Alpha 2.1) |
| querencia-dokumente | 0.1.4-1 | PDF viewer (unchanged since Alpha 2.1) |
| querencia-archiv | 0.1.2-1 | Archive manager (unchanged since Alpha 2.1) |
| querencia-rechner | 0.1.6-1 | Calculator (unchanged since Alpha 2.1) |
| querencia-systemmonitor | 0.1.5-1 | System monitor (unchanged since Alpha 2.1) |
| querencia-screenshot | 0.2.10-1 | Screenshot (unchanged since Alpha 2.1) |
| querencia-software | 0.1.5-1 | Installing programs via PackageKit (unchanged since Alpha 2.1) |
| querencia-anmeldung | 0.1.2-1 | German login screen, optional (unchanged since Alpha 2.1) |

Checksum of the package list (SHA256SUMS): `488348b69015ba318e6ec2cf5077d1c532c15a720edf8943d4e2bec8965a2c05`.

## Upgrading from Alpha 2.1

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` is enough as well. APT installs Querencia Dateien and
upgrades among others the panel and desktop, Files, the session, the session
dialog, system settings, the icons, file search and the meta package;
nothing is removed and there is no question about configuration files. Log
out and in again afterwards; in a virtual machine the upgrade from the
published repository took about 20 seconds. Folders then open in Querencia Dateien;
“Querencia Files” is no longer in the menu and the command `querencia-files`
is gone. Links to Files on the panel, the desktop or in your own
`~/.config/mimeapps.list` open Querencia Dateien.

After that the package `querencia-files` is only a transitional package with
the two hidden starters; `sudo apt autoremove` leaves it in place. If no link
points to Files any more, you can remove it:

```bash
sudo apt remove querencia-files
```

A panel launcher that still points to Files then no longer starts anything
and can be replaced by “Querencia Dateien”. The Files settings
(`~/.config/strata`, after Alpha 2.2 `~/.config/querencia-files`) stay and
can be deleted.

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`,
restart, choose “Querencia Desktop” at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Fingerprint of the
signing key: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`. Querencia
Files is no longer installed.
On a fresh Ubuntu 26.04 server image APT installs 389 packages in about 1.5
to 2 minutes (depending on the Ubuntu archive).

## Known limitations

Still valid from Alpha 2 and 2.1 (see there), unless listed as fixed above. New or changed:

- **Querencia Dateien is a beta.** Undo (Ctrl+Z) does not exist yet; there
  is no column view and no folder tree in the side pane. Search only finds
  names, not file contents; copying or dragging from the search results
  does not work yet. The view is not remembered per folder, open tabs are
  not restored on the next start.
- **Network partly untested:** tested with test servers for SFTP, WebDAV
  and FTP in an isolated environment. A successful connection to a Windows
  share, certificate questions for secure connections and real network
  drives are untested.
- **Thumbnails for PDF** only appear when a PDF thumbnailer and
  `bubblewrap` are installed.
- **Files settings are not taken over.** After an upgrade from Alpha 2.1,
  Dateien does not take over view, sorting, hidden files, folders first,
  click behaviour and side pane from Files; please set them again under
  Edit → Preferences. Bookmarks are kept. Fixed in
  [Alpha 3.1](alpha-3.1.md).
- **What Files could do and Dateien cannot:** the preview inside the
  window, the column view and extracting inside the program. Archives open
  in the Archive Manager on double-click; an “Extract here” entry in the
  Dateien context menu is still missing.
- **Software OpenGL** costs CPU time and memory; programs started by the
  window manager itself (e.g. through shortcuts) do not get it.
- **Not tested on real hardware**, only in virtual machines and in isolated
  copies of the system.

## Reporting bugs

As for Alpha 2, in the project's bug tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>. For
Querencia Dateien please also include the output from a terminal (start
`querencia-dateien` in a terminal, the lines starting with
“querencia-dateien:”).

## Tested

- Every source is a tagged state; Querencia Dateien from `dateien/0.2.0`.
- Querencia Dateien in isolated runs (own window manager without a screen,
  own profile with test files, network only inside its own namespace), at
  1024×768 and 1920×1080, light and dark, all passed: tabs 20 cases, compact
  view 14, search in tabs 5, takeover of the Files settings 3 each, network
  53, thumbnails and search 26, views 80, file operations 35; plus 656
  automatic tests of the source tree.
- Static package check (266 passed), Lintian without errors, the sources'
  tests during the build (Dateien and its two libraries 227, panel, desktop
  and applets 429, session dialog 85, session starter 106), test
  installation in an isolated copy of the system (91 checks passed).
- **Upgrade from Alpha 2.1 and from Alpha 2.2** (each in an isolated copy of
  the system, 144 checks passed each): old package set installed, a user
  with bookmarks, Files settings and an own folder choice naming the old
  Files ID created, then the new set on top: `apt upgrade` and
  `apt full-upgrade` remove nothing and hold nothing back; folders open in
  Dateien, also through the old choice; the old Files starters open Dateien
  and leave the menu; no starter and no entry of a `mimeapps.list` points to
  nothing.
- **From the published repository** in a virtual machine: new installation
  (389 packages, check script in the session 28 of 28, also through
  Querencia's own login screen) and upgrade from Alpha 2.1 (about 20
  seconds, nothing removed, no questions; own settings such as background,
  shortcuts and panel launchers stay, an old Files launcher on the panel
  opens Dateien); the password dialog after a polkitd restart.
- Not tested: real Windows shares and network drives, real USB devices,
  login through GDM.

## Licenses and origin

Querencia Dateien is licensed GPL-3.0-or-later; some parts taken over from
Querencia Files keep Strata's MIT license (the About dialog says so).
Otherwise as Alpha 2. The name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
