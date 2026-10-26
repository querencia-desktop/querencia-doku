# Querencia Desktop – Alpha 3.2

**As of:** 26 October 2026 · **Status:** in the APT repository since 26 October 2026, 22:11

Alpha 3.2 is a maintenance update to Alpha 3.1: a fix for the menus in
Querencia Dateien and a new name for the optional program for WhatsApp Web:
Querencia Web Wrapper becomes **Schnatter**. There are 24 Debian packages
for Ubuntu 26.04 (“resolute”) from the same signed APT repository; 20 of
them are unchanged since Alpha 3.

> **Alpha.** Meant for test systems, not for daily use. No security or
> data-loss guarantees. Try it in a virtual machine with a snapshot first.
> Querencia Dateien itself carries the stage “beta”.

## New in Alpha 3.2

- **Querencia Dateien 0.2.2:** an open context menu no longer closes when
  the pointer, on its way to an entry, passes below a menu of the menu bar.
  Before, on the way to “Rename…” for example, “View” opened at the top
  instead. The right arrow key in a context menu no longer jumps into the
  menu bar either. The “Network” window now has its German title
  „Netzwerk“ in the German interface even when the system's network service
  speaks English. The cause was in the menu library shared by the Querencia
  programs; the panel and the desktop get the new version with their next
  release.
- **Schnatter 0.3.0** (formerly Querencia Web Wrapper), optional: WhatsApp
  Web in a window of its own with the classic menu bar, in the menu under
  Applications → Internet → “Schnatter”. It does what the web wrapper did;
  new are the name and the icon (a green speech bubble with a beak).
  - **If you had the web wrapper installed,** the upgrade brings
    Schnatter. The package `querencia-webhuelle` becomes a transitional
    package that pulls in Schnatter. On its first start Schnatter takes over
    the sign-in and the settings: it renames the web wrapper's three
    folders, nothing is copied or deleted. If the web wrapper is still
    running, Schnatter says so and only starts once it is closed.
  - **If you did not have the web wrapper,** nothing new is added.
    Schnatter is not in the meta package and not part of the default
    installation. To install it on its own:

    ```bash
    sudo apt install querencia-schnatter
    ```

  Calls are still not possible (Ubuntu's web engine is built without
  WebRTC). Schnatter is not a product of WhatsApp or Meta and is not
  affiliated with them.

What Alpha 3.1 brought (Dateien also takes over the Querencia Files settings
from `~/.config/strata`; the web wrapper as a new, optional program) is in
the [Alpha 3.1 notes](alpha-3.1.md).

## Versions

Package set of 26 October 2026 (24 packages).

| Package | Version | Content |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.2-1 | meta package, version file “Alpha 3.2” |
| querencia-dateien | 0.2.2-1 | **changed:** context menus stay open, title „Netzwerk“ |
| querencia-schnatter | 0.3.0-1 | **new, optional:** Schnatter, WhatsApp Web in a window of its own (formerly the web wrapper) |
| querencia-webhuelle | 0.3.0-1 | **Transitional package:** pulls in Schnatter, a hidden starter opens Schnatter |
| querencia-files | 0.2.0-1 | transitional package from Alpha 3 (unchanged) |
| querencia-shell | 0.1.0~alpha10-1 | Panel 0.3.2, desktop 0.3.0, keyboard shortcut overview 0.2.2, theme 0.2.2 (unchanged since Alpha 3) |
| querencia-session | 0.1.0~alpha10-1 | Session starter (unchanged since Alpha 3) |
| querencia-sitzung | 0.1.8-1 | Session dialog, lock, password dialog (unchanged since Alpha 3) |
| querencia-symbole | 0.8-1 | Program icons and icon theme (unchanged since Alpha 3) |
| querencia-dateisuche | 0.1.5-2 | Search for Files (unchanged since Alpha 3) |
| querencia-einstellungen | 0.1.6-1 | System settings (unchanged since Alpha 3) |
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
| querencia-anmeldung | 0.1.2-1 | Login screen, German and English, optional (unchanged since Alpha 2.1) |

Checksum of the package list (SHA256SUMS): `fbf26227628c91d94d37faf2f222aaa397b4e475a4dbf24da029b157afed3c7f`.

## Upgrading from Alpha 3 or 3.1

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` is enough as well. APT upgrades Querencia Dateien and the
meta package. If you have the web wrapper installed, you also get Schnatter
as a new package and the web wrapper as a transitional package. Nothing is
removed and there is no question about configuration files. In a virtual
machine the upgrade took a few seconds, not counting the download. Log out
and in again afterwards (or at least close and reopen Dateien). The web
wrapper is then gone from the menu and Schnatter is under Internet; a web
wrapper launcher on the panel opens Schnatter.

After the upgrade APT reports `querencia-webhuelle` as “no longer required”.
That is intended: the transitional package may go once no link points to
the web wrapper any more. APT moves the “manually installed” mark to
Schnatter, so `sudo apt autoremove` only removes the transitional package.
To be on the safe side, mark Schnatter yourself first:

```bash
sudo apt install querencia-schnatter
```

Upgrading from Alpha 2.1 or 2.2 directly to 3.2 works as described in the
[Alpha 3 notes](alpha-3.md#upgrading-from-alpha-21).

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`,
restart, choose “Querencia Desktop” at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Fingerprint of the
signing key: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`. Schnatter
is not installed. On a fresh Ubuntu 26.04 server image APT installs 389
packages; from the published repository that takes about 1.5 to 2 minutes
(depending on the Ubuntu archive).

## Known limitations

Still valid from Alpha 3 and 3.1 (see there), unless listed as fixed above.
In particular:

- **Querencia Dateien is a beta.** Undo (Ctrl+Z) does not exist yet; there
  is no column view and no folder tree in the side pane. Search only finds
  names, not file contents; copying or dragging from the search results
  does not work yet. The view is not remembered per folder, open tabs are
  not restored on the next start.
- **Small things in Dateien, still open:** the compact view shortens long
  names; the status bar is empty after a search.
- **Network partly untested:** a successful connection to a Windows share,
  certificate questions for secure connections and real network drives are
  untested.
- **Takeover of the Files settings only on the first start** of Dateien
  (see [Alpha 3.1](alpha-3.1.md#known-limitations)).
- **No notification area in the panel.** Programs that want to show an icon
  in the panel (notification area, “tray”) show none. Schnatter only
  announces new messages while its window is open; closing it quits it.
- **Schnatter with a real account** has not been tested in the test VM;
  tested are the move of the folders, the sign-in page and the window.
- **Own login screen** (`querencia-anmeldung`, optional): it speaks German
  and English. Still English or untranslated are the session names, the
  messages of the login check (PAM, because greetd sets no language) and some
  texts of GTK itself as long as `language-pack-gnome-de` is not installed
  (the meta package deliberately does not pull it in).
- **Software OpenGL** costs CPU time and memory; programs started by the
  window manager itself (e.g. through shortcuts) do not get it.
- **Not tested on real hardware**, only in virtual machines and in isolated
  copies of the system.

## Reporting bugs

As for Alpha 3, in the project's issue tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Tested

- Every source is a tagged state; Querencia Dateien from `dateien/0.2.2`,
  Schnatter from `schnatter/0.3.0`.
- **Querencia Dateien 0.2.2** in isolated runs: context menu and menu bar
  12 cases, light and dark passed (7 of them failed with 0.2.1); window
  title „Netzwerk“ with a network service speaking English 2 of 2; the
  checks of 0.2.1 repeated (tabs, compact view, search, takeover of the
  Files settings) passed; 659 automatic tests of the source tree.
- **Schnatter 0.3.0** in isolated runs: move from the web wrapper and from
  older versions with test folders (without a real account), 58 of 58 each
  in eight combinations; test page 74 of 74.
- Static package check (290 passed), Lintian without errors, trial
  installation in an isolated copy of the system (95 checks passed), a
  control build gave the same packages.
- **Upgrade** in an isolated copy of the system: from Alpha 3.1 with the web
  wrapper (168 checks passed) and without (149), from Alpha 3 (149) and from
  Alpha 2.1 (148): nothing removed, nothing held back, no questions.
- **In a virtual machine:** Alpha 3.1 with the web wrapper from the
  published repository, web wrapper started once, then the upgrade to 3.2:
  three packages upgraded, Schnatter new, nothing removed, no questions;
  test script 78 of 78, session 28 of 28. On its first start Schnatter took
  over all files of the web wrapper (139 of 139). Visual check: the context
  menu stays open, window title „Netzwerk“. New installation (389 packages,
  no Schnatter): test script 76 of 76, session 28 of 28.
- Not tested: Schnatter with a real account, real Windows shares and network
  drives, real USB devices, login through GDM, real hardware.

## Licences and origin

Like the other Querencia programs, Schnatter is licensed under the
GPL-3.0-or-later. WhatsApp is a trademark of its owner and is only used
descriptively, never in the program name or the icon. Otherwise as Alpha 3.
The name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
