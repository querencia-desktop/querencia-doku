# Querencia Desktop – Alpha 3.4

**As of:** 27 October 2026 · **Status:** in the APT repository since 27 October 2026, 20:56

Alpha 3.4 adds a page “Drivers” for the graphics card to the system
settings. Querencia Dateien can now undo steps, also search file contents,
restore its tabs at the next start and “Extract Here” for archives. The
login screen explains an expired password. The lock screen, the volume
control and the keyboard shortcuts help now speak all five languages. There
are 24 Debian packages for Ubuntu 26.04 (“resolute”) from the same signed
APT repository; 6 of them are newly built.

> **Alpha.** Meant for test systems, not for daily use. No security or
> data-loss guarantees. Try it in a virtual machine with a snapshot first.
> Querencia Dateien itself carries the stage “beta”.

## New in Alpha 3.4

- **Page “Drivers” (Querencia Einstellungen 0.2.0).** Found under
  System → Administration → “Drivers” or in the System Settings. The page
  shows the graphics card, the loaded kernel driver, the OpenGL renderer
  and whether this session uses software OpenGL. Below are the drivers
  Ubuntu knows for the card, each with its state (“in use”, “installed, in
  use after a restart”, “available”, “not installed”).
  - **The default is the free driver** (“Free driver nouveau (Querencia
    default)”). The NVIDIA driver is a choice, for example “NVIDIA driver
    615 with open kernel modules”.
  - **Changing:** choose a driver → “Apply Changes” → confirmation with the
    list of packages → password. The packages come through PackageKit, as
    in Querencia Software. Going back to the free driver removes the whole
    NVIDIA branch.
  - **Restart afterwards:** the new driver only applies after a restart.
    The page says so and offers “Restart…”; this opens the session's
    restart question.
  - The list comes from the program `ubuntu-drivers` in the package
    `ubuntu-drivers-common`. Querencia Einstellungen now recommends it; the
    upgrade installs it. If it is missing, the page says so and offers
    “Install ubuntu-drivers-common…”.
  - With an NVIDIA card the page explains why the session switches OpenGL
    to software (llvmpipe) with the free driver, and that the NVIDIA driver
    makes this unnecessary.
- **Querencia Dateien 0.3.0:**
  - **Undo and redo** (Ctrl+Z, Shift+Ctrl+Z; the Edit menu says what will
    be undone). This works for moving, renaming, moving to the trash,
    copying, Create Folder and Create Document. Undoing a copy moves the
    copies to the trash, without asking; the menu says “(to the trash)”.
    Deleting permanently and “Empty Trash” cannot be undone. Each window
    has one history for all its tabs, up to 50 steps.
  - **Search in file contents too:** the search bar (Ctrl+F) has the switch
    “Also file contents” (off by default). Then the search also finds text
    files up to 10 MB that contain all the words. The column “Match” shows
    the first matching line, the tooltip its number.
  - **Restore tabs at start** (Edit → Preferences → Behavior, on by
    default): starting without a folder reopens the tabs of the window
    closed last. Places that cannot be reached are skipped.
  - **“Extract Here”** in the context menu of archives, if the Archive
    Manager is installed (it is with the meta package). The Archive Manager
    extracts every selected archive next to itself and shows progress and
    questions itself.
- **Expired passwords explained** (`querencia-anmeldung` 0.1.4, optional):
  the login screen now says in the system language that the password has
  expired and how to set a new one on the text console (Ctrl+Alt+F1, back
  with Ctrl+Alt+F7). Before, it showed `Pam_acct_mgmt: NEW_AUTHTOK_REQD`.
  Changing the password on the login screen itself is not possible with
  greetd 0.10.
- **Remaining language gaps closed:** the lock screen (Querencia Sitzung
  0.1.10), the volume control window (0.1.2) and the keyboard shortcuts
  help with its launcher (0.2.3) are now also available in Italian, Spanish
  and French. So far they were German only.

What Alpha 3.3 brought (five languages, notification area) is described in
the [notes for Alpha 3.3](alpha-3.3.md).

## Versions

Package set of 27 October 2026 (24 packages).

| Package | Version | Contents |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.4-1 | Meta package, version file “Alpha 3.4”; dependencies unchanged |
| querencia-einstellungen | 0.2.0-1 | **changed:** page “Drivers” with its own menu entry; **new:** recommends `ubuntu-drivers-common` |
| querencia-dateien | 0.3.0-1 | **changed:** undo, search in file contents, restore tabs, “Extract Here” |
| querencia-shell | 0.1.0~alpha12-1 | **changed:** keyboard shortcuts help 0.2.3 and volume control 0.1.2 in five languages; panel 0.4.0 and desktop 0.3.1 unchanged |
| querencia-sitzung | 0.1.10-1 | **changed:** lock screen in five languages |
| querencia-anmeldung | 0.1.4-1 | **changed:** login screen, clear message for expired passwords, optional |
| querencia-software | 0.1.7-1 | Software center (unchanged since Alpha 3.3) |
| querencia-editor | 0.2.5-1 | Text editor |
| querencia-terminal | 0.3.3-1 | Terminal |
| querencia-rechner | 0.1.7-1 | Calculator |
| querencia-bilder | 0.2.7-1 | Image viewer |
| querencia-dokumente | 0.1.5-1 | PDF viewer |
| querencia-archiv | 0.1.3-1 | Archive manager |
| querencia-systemmonitor | 0.1.6-1 | System monitor |
| querencia-dateisuche | 0.1.6-1 | Search for files |
| querencia-screenshot | 0.2.11-1 | Screenshot |
| querencia-benachrichtigungen | 0.2.3-1 | Notifications |
| querencia-schnatter | 0.3.1-1 | Schnatter, WhatsApp Web in its own window, optional |
| querencia-webhuelle | 0.3.0-1 | Transitional package to Schnatter (unchanged since Alpha 3.2) |
| querencia-files | 0.2.0-1 | Transitional package from Alpha 3 (unchanged) |
| querencia-session | 0.1.0~alpha10-1 | Session starter (unchanged since Alpha 3) |
| querencia-symbole | 0.8-1 | Program icons and icon theme (unchanged since Alpha 3) |
| querencia-hintergruende | 0.2-1 | 16 backgrounds (unchanged since Alpha 2) |
| labwc | 0.9.8-0querencia5 | Backport of the window manager (unchanged since Alpha 2) |

From Software to labwc the packages are byte-identical to Alpha 3.3.

Checksum of the package list (SHA256SUMS): `97f55df08e102a5b35e3282e0f7f8c4e38e78dbcdab85b2549bffe4698f9a5aa`.

## Upgrading from Alpha 3.3

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` works as well. APT upgrades 5 packages, 6 with the
login screen, and newly installs `ubuntu-drivers-common` (with
`python3-xkit`). It downloads about 29 MB (with the login screen). Nothing
is removed, and there is no question about configuration files. In a
virtual machine the upgrade took about 8 seconds, not counting the
download. Then log out and log in again.

An upgrade from Alpha 3.2 works the same way; what else happens is
described in the [notes for Alpha 3.3](alpha-3.3.md#upgrading-from-alpha-32-or-31).
For older states see there.

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`,
restart, choose “Querencia Desktop” at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Fingerprint of the
signing key: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
`ubuntu-drivers-common` comes along, Schnatter does not. On a fresh
Ubuntu 26.04 server image APT installs 392 packages.

## Known limitations

Still valid from Alpha 3 to 3.3 (see there), unless listed as fixed above.
In particular:

- **Page “Drivers”:**
  - A change needs `ubuntu-drivers-common`, a network connection and the
    password, and it only takes effect after a restart.
  - In a virtual machine with software rendering (llvmpipe) the page
    wrongly shows “OpenGL on the graphics card” for “This session:”. The
    renderer above correctly says llvmpipe. A later version of the settings
    fixes this.
  - The page only shows what `ubuntu-drivers` lists. The change with a
    real NVIDIA card is not tested yet, nor are computers with two graphics
    cards (such as notebooks with Intel and NVIDIA) and Secure Boot. For
    Secure Boot the page installs the module package signed by Canonical;
    there is no prompt for an own MOK key.
  - If there is no picture after the change, log in on the text console
    (Ctrl+Alt+F3) and remove the NVIDIA packages again. So take a snapshot
    of the virtual machine first.
- **Querencia Dateien is a beta.**
  - Undo only covers operations of this window and only until Querencia
    Dateien is closed. Deleting permanently and “Empty Trash” cannot be
    undone; what was replaced while pasting does not come back. “Extract
    Here” is not in the undo history.
  - The content search has no index (large folders take time), does not
    read network places and no documents such as odt or pdf.
  - Restored tabs only keep their folder, not view, zoom or history.
  - There is no column view and no folder tree in the sidebar; copying or
    dragging from the search results is not possible yet.
- **Login screen:** an expired password can only be changed on the text
  console, not on the login screen. It still only knows German and
  English; with Italian, Spanish or French as the system language it shows
  English.
- **Languages:** in Italian the key name “Return” stays English in menu
  shortcuts (e.g. “Alt+Return” in the image viewer). Texts from GTK itself
  (file dialog, some buttons) follow the system's language pack,
  `language-pack-gnome-<xx>`.
- **Notification area:** as in Alpha 3.3 (no XEmbed, passive icons hidden,
  not yet tested with Webex, Nextcloud or Discord themselves).
- **Schnatter** does not show an icon in the notification area yet.
- **Network partly untested:** Windows shares, certificate questions for
  secure connections and real network drives are untested.
- **Software OpenGL** with the free driver costs CPU time and memory;
  programs started by the window manager itself (e.g. through keyboard
  shortcuts) do not get it.
- **Not tested on real hardware**, only in virtual machines and in isolated
  copies of the system.

## Reporting bugs

As for Alpha 3, in the project's issue tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Tested

- Every source is a tagged state: the settings from `einstellungen/0.2.0`,
  Querencia Dateien from `dateien/0.3.0`, the login screen from
  `anmeldung/0.1.4`, the session from `sitzung/0.1.10`.
- **Page “Drivers”** in isolated runs with simulated graphics cards
  (NVIDIA with the free and with the NVIDIA driver, AMD, Intel, no card,
  without `ubuntu-drivers`) and a stand-in for PackageKit: 256 checks
  passed, in German and English, two screen sizes, light and dark; change
  there and back, rejected password and locked package management; the 14
  other pages as before; 155 automatic tests.
- **Querencia Dateien 0.3.0** in isolated runs: undo for each kind,
  content search, tabs and “Extract Here” in their own scenarios, all
  passed; 701 automatic tests of the source tree.
- **Login screen 0.1.4** in an isolated probe with real greetd and a real
  password check: expired password in German and English with the new
  message, wrong and valid password as before; 96 configuration cases
  passed.
- **Languages:** lock screen, volume control and keyboard shortcuts help
  in isolated runs in five languages with screenshots; catalogs, launchers
  and descriptions in all packages 18 of 18.
- Static package check (304 passed), Lintian without errors, trial
  installation in an isolated copy of the system (96 checks passed, with
  Italian as the system language 103, with screenshots), a control build
  gave the same packages.
- **Upgrade** in an isolated copy of the system: from Alpha 3.3 with
  Schnatter (168 checks passed), without Schnatter (155) and from Alpha 3.2
  with Schnatter (169): nothing removed, nothing held back, no questions;
  `ubuntu-drivers-common` new.
- **In a virtual machine:** Alpha 3.3 with Schnatter and the login screen
  from the published repository, then the upgrade to 3.4: 6 Querencia
  packages upgraded, `ubuntu-drivers-common` new, nothing removed, no
  questions, own settings kept; session 28 of 28, login screen 3 of 3,
  check script 107 passed (the other three messages are not about the
  upgrade: two compared with a state before the login screen was
  installed, one is the log of the running panel). Visual checks: the page
  “Drivers”, undo, content search, tabs and “Extract Here” in Dateien, the
  expired password in German and English including the change on the text
  console and logging in with the new password, lock screen, volume control
  and keyboard shortcuts help in Italian. New installation (392 packages
  with `locales-all` and `ubuntu-drivers-common`, no Schnatter): check
  script 108 of 108, session 28 of 28.
- Not tested: a real driver change with restart, real NVIDIA, AMD or Intel
  cards, Secure Boot, the notification area
  with Webex, Nextcloud or Discord, Schnatter with a real account, real
  Windows shares and network drives, login through GDM, real hardware.

## Licences and origin

As for Alpha 3.3. `ubuntu-drivers-common` and the NVIDIA drivers are
Ubuntu packages; the NVIDIA driver is proprietary and is only installed on
request. The name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
