# Querencia Desktop – Alpha 3

**As of:** `<date>` · **Status:** in the APT repository since `<date>`, `<time>`

With Alpha 3 Querencia gets its **own file manager: Querencia Dateien**
0.2.0, a beta. It follows Nautilus 2.30 – menu bar, toolbar, path bar, side
pane “Places”, status bar – and brings tabs, three views, thumbnails, a name
search and “Connect to Server…”. Querencia Dateien is now the program for
folders; the earlier Querencia Files (a fork of Strata) is retired. There
are `<number>` Debian packages for Ubuntu 26.04 (“resolute”) from the same
signed APT repository.

> **Alpha.** Meant for test systems, not for daily use. No security or
> data-loss guarantees. Try it in a virtual machine with a snapshot first.

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
  two hidden starters stay and open Querencia Dateien. The transitional
  package can be removed once no link points to Files any more.
  `<according to the packaging draft of 24 October, check against the final set>`
  On its first start Dateien takes over six Files settings once (hidden
  files, view, sorting, folders first, single or double click, side pane);
  both share the bookmarks (`~/.config/gtk-3.0/bookmarks`). The Files
  settings in `~/.config/querencia-files` stay untouched.
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
- `<only if querencia-sitzung 0.1.8 is in the set; as of 24 October: 0.1.7>`
  **Sitzung 0.1.8:** after polkitd restarts, for example during
  an update, the password dialog for administrative tasks registers with the
  new polkitd by itself; until now such requests then failed without a
  dialog.
- `<only if the querencia-session package contains the session starter's graphics check; as of 24 October: development build only>`
  **Software OpenGL with zink on nouveau:** when OpenGL runs over zink on an
  NVIDIA card with the free nouveau driver, the session starter gives the
  session's programs software OpenGL (llvmpipe). In testing, the web content
  of Querencia Nachrichten crashed and Firefox froze otherwise; with software
  OpenGL both run, at the cost of CPU work. The window manager itself stays
  unchanged. Controlled in `~/.config/querencia/grafik.ini` (`[Grafik]
  Software-OpenGL = automatisch|an|aus`), logged in
  `~/.local/state/querencia/sitzung-start.log`.
- `<only if querencia-nachrichten is in the set:>` **Querencia Nachrichten
  0.1.1:** the same graphics fallback (setting “Software-Grafik”, from the
  next start); links with schemes other than http, https and mailto only
  open after a question. Calls still do not work.
- **Desktop 0.3.0:** copying, moving and deleting on the desktop with
  progress, cancel and the same question for equal names as in Querencia
  Dateien; newly plugged-in USB sticks and inserted CDs are mounted without
  opening a window; Computer, Trash and drives open in Dateien.
- `<only if Alpha 2.2 is not published first:>` **From the Alpha 2.2
  state:** the cause of the panel crashes when opening „Anwendungen“
  (Applications) is fixed; the dark appearance also switches window borders
  and GTK 3 programs; while locked, the screen turns off after two minutes;
  „Ausschalten …“ (Shut Down) offers „Neu starten“ (Restart); the panel and
  the desktop also speak English; display settings per monitor.
- **Symbole 0.8:** own program icon for Querencia Dateien.

## Versions

Package set of `<date>` (`<number>` packages).

| Package | Version | Content |
|---|---|---|
| querencia-desktop | `<0.1.0~alpha3-n>` | Meta package: pulls in Querencia Dateien instead of Files, version file “Alpha 3” |
| querencia-dateien | `<0.2.0-n>` | **new:** file manager Querencia Dateien 0.2.0 (beta) |
| querencia-files | `<0.2.0-1>` | Transitional package: Files goes away, the hidden starters open Querencia Dateien |
| querencia-shell | `<0.1.0~alpha10-n>` | Panel 0.3.2, desktop 0.3.0, keyboard shortcut overview 0.2.2, theme `<version>` |
| querencia-session | `<0.1.0~alpha9-n>` | Session starter: folders open in Querencia Dateien |
| querencia-sitzung | `<0.1.7-1 or 0.1.8-1>` | Session dialog, lock, password dialog |
| querencia-symbole | `<0.8-1>` | Program icons and icon theme, new: the Dateien icon |
| querencia-dateisuche | `<0.1.5-2>` | Search for Files; recommends Querencia Dateien instead of Files |
| `<other packages>` | `<version>` | `<unchanged since the predecessor, list according to the final set>` |

Checksum of the package list (SHA256SUMS): `<SHA256SUMS>`.

## Upgrading from `<Alpha 2.1 or 2.2>`

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`<What APT installs, upgrades and removes, according to the upgrade test of the final set>`
Log out and in again afterwards. Folders then open in Querencia Dateien;
“Querencia Files” is no longer in the menu.

`<Fallback note according to the final set, e.g. whether and how Files can still be installed>`

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`,
restart, choose “Querencia Desktop” at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Fingerprint of the
signing key: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`. Querencia
Files is no longer installed.
`<New installation: package count and time>`

## Known limitations

Still valid from Alpha 2 (see there). New or changed:

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
- **What Files could do and Dateien cannot:** the preview inside the
  window, the column view and extracting inside the program. Archives open
  in the Archive Manager on double-click; an “Extract here” entry in the
  Dateien context menu is still missing.
- `<only if software OpenGL is in the set:>` **Software OpenGL** costs CPU time and memory; programs started by the
  window manager itself (e.g. through shortcuts) do not get it.
- `<only if querencia-nachrichten is in the set:>` **Querencia Nachrichten:**
  no calls.
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
- `<Package check, Lintian, test installation and upgrade test of the final set>`
- Not tested: real Windows shares and network drives, real USB devices,
  login through GDM.

## Licenses and origin

Querencia Dateien is licensed GPL-3.0-or-later; some parts taken over from
Querencia Files keep Strata's MIT license (the About dialog says so).
Otherwise as Alpha 2. The name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
