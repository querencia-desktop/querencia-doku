# Querencia Desktop – Alpha 1

**As of:** 20 October 2026, 22:30 · **Status:** internal alpha, not
published · Values marked “open” are not yet confirmed or not yet decided;
“in progress” means built or being built, but neither active in the
development environment nor part of the package set.

Querencia Desktop is a classic desktop environment in the style of GNOME 2
(Ubuntu 10.04) for Wayland: the labwc 0.9.8 window manager, two panels, a
desktop with icons and its own programs written in Rust and GTK 4 without
libadwaita. The interface is German; most programs are also available in
English. Alpha 1 is the first test release for Ubuntu 26.04 (“resolute”): 20
Debian packages that can be installed alongside an existing Ubuntu Desktop.

> **Alpha.** Meant for test systems, not for everyday use. No guarantee
> regarding security or data loss. Try it on a virtual machine with a
> snapshot first.

## New in Alpha 1

Compared with the development state of 19 October 2026:

- **Notification center** (Notifications 0.2.0): notifications are kept in a
  history, also across a new login; open it from Applications → Accessories
  → Notification Center.
- **System Settings 0.1.0** in German and English, with the new **Language
  and Region** section and **several keyboard layouts**.
- **Panel:** the window list only shows the windows of the current
  workspace; the System menu has **Bildschirm sperren** (lock screen,
  Ctrl+Alt+L). Log out and shut down go through the session dialog, in the
  packages too.
- **Show the desktop:** a button “Arbeitsfläche anzeigen” at the bottom left
  of the panel minimises all windows of the current workspace, a second click
  restores them; the shortcut is **Super+D**.
- **Notification center bell** at the top right of the panel, with a counter.
- **Full screen** for the active window with **Super+F** or **Alt+F11**.
- **Archive Manager 0.1.0** (Querencia Archiv): open, list, extract and
  create archives.
- **Document Viewer 0.1.0** (Querencia Dokumente), a PDF viewer.
- **Icons 0.6** with a dedicated icon for the Document Viewer. The Image
  Viewer (0.2.2) is listed under “Grafik” (Graphics) in the menu.
- **Login screen as a package** (`querencia-anmeldung` 0.1.1, optional, see
  below).
- Querencia Software 0.1.3 checks the network connection itself and explains
  why PackageKit does not install, instead of silently reporting “offline”.
- Logging in again right after logging out works without a black screen;
  programs started from the menu appear immediately, also alongside GNOME
  (portals fixed).

## Versions

### In the Alpha 1 package set

Package set of 20 October 2026 (20 packages), built from the state that was
active in the development environment the same evening.

| Package | Version | Contents |
|---|---|---|
| querencia-desktop | 0.1.0~alpha2-5 | metapackage: pulls in all components |
| labwc | 0.9.8-0querencia4 | backport of the window manager (Ubuntu 26.04 ships 0.9.3) |
| querencia-session | 0.1.0~alpha6-1 | session starter 2.1, labwc defaults, portal and gsettings defaults |
| querencia-shell | 0.1.0~alpha5-1 | panel, desktop, volume, network, keyboard shortcut overview (Super+?), theme Querencia-Klassisch, backgrounds |
| querencia-sitzung | 0.1.3-2 | Session 0.1.3: lock screen, session dialog, polkit agent |
| querencia-benachrichtigungen | 0.2.0-1 | Notifications 0.2.0 with notification center |
| querencia-einstellungen | 0.1.0-1 | System Settings 0.1.0 |
| querencia-symbole | 0.6-1 | program icons and the “Querencia” icon theme |
| querencia-files | 0.1.0~alpha4-1 | Querencia Files, state QF-0o-3 (file manager, fork of Strata) |
| querencia-terminal | 0.2.0-1 | Querencia Terminal 0.2.0 |
| querencia-editor | 0.2.1-1 | Text Editor 0.2.1 |
| querencia-bilder | 0.2.2-1 | Image Viewer 0.2.2 |
| querencia-dokumente | 0.1.0-2 | PDF viewer 0.1.0 |
| querencia-archiv | 0.1.0-1 | archive manager 0.1.0 |
| querencia-rechner | 0.1.3-1 | calculator 0.1.3 |
| querencia-systemmonitor | 0.1.2-1 | system monitor 0.1.2 |
| querencia-dateisuche | 0.1.3-1 | Search for Files 0.1.3 |
| querencia-screenshot | 0.2.8-2 | Screenshot 0.2.8 with editor and window selection |
| querencia-software | 0.1.3-1 | install programs through PackageKit, 0.1.3 |
| querencia-anmeldung | 0.1.1-2 | login screen (greetd and ReGreet 0.5.0), optional |

From the Ubuntu archive: the DejaVu Sans font and the DMZ-White mouse
pointer.

The “Arbeitsfläche anzeigen” button and the bell (panel, state G2-AL) have
been active in the development environment since 20 October 2026, 22:25;
they are not yet included in the package set above. **Inclusion in
querencia-shell: open.**

### In progress (not in Alpha 1)

| Component | Version | What changes |
|---|---|---|
| Querencia Terminal | 0.3.0 | tabs (Ctrl+Shift+T, tab bar, context menu) |
| Theme | 0.2 | dark variant “Querencia-Klassisch-Dunkel” |
| Querencia Files | state QF-0p | Querencia icon instead of the Strata logo in the About dialog |
| Image Viewer | 0.2.3 | info window keeps its title bar when opened a second time |
| System Settings | 0.1.1 | own backup files with a limit, resetting leaves no traces in the labwc configuration |
| Signed APT repository | – | packages via `dl.querencialinux.org/apt` |

## Installation

Requirements: Ubuntu 26.04 (desktop or server image), a user with sudo
rights, network access to the Ubuntu archive.

> **Not available yet.** The packages will come from a signed APT
> repository. It **follows with the APT repository** at
> `dl.querencialinux.org/apt`; until then the commands for adding the
> repository do not work, and this section describes the planned way.

1. **Add the repository:** follows with the APT repository (signing key
   “Querencia Desktop Archive Signing Key”).

2. **Install:**

   ```bash
   sudo apt update
   ```

   ```bash
   sudo apt install querencia-desktop
   ```

   apt also installs the recommended packages (Recommends): PipeWire for
   sound, NetworkManager, Avahi and wsdd for the network view in Files, the
   GTK portal and more. On a **server image** that is **about 360 packages**
   from the Ubuntu archive, on Ubuntu Desktop only a few. With
   `--no-install-recommends` the installation stays small; then sound,
   connecting through the network applet, the network view in Files and
   `notify-send` are missing.

3. **Restart.** GDM only reads new sessions when it starts: only after a
   restart does “Querencia Desktop” appear under the gear at the bottom right
   of the login screen.

4. **Log in:**
   - with **GDM** (Ubuntu Desktop): choose the user, choose “Querencia
     Desktop” under the gear, log in;
   - **without a graphical login screen** (server image): log in on the text
     console and type `querencia-session`.

### Server image: network through NetworkManager

On Ubuntu Server, netplan manages the network through systemd-networkd.
NetworkManager is then installed but manages nothing. As a result the
network applet only shows the state (“No network device”), and PackageKit
considers the system offline. **Querencia Software cannot install anything
then** and shows a clear message with the remedy.

Remedy: set up NetworkManager as the netplan renderer (`renderer:
NetworkManager` under `network:` in `/etc/netplan/`). On cloud and VM images
with cloud-init and dracut this one line alone is not enough; for those **a
tested switch-over script follows** that keeps the address.

### Alongside GNOME (Ubuntu Desktop)

Querencia **does not replace GNOME**, it sits next to it. Tested on Ubuntu
26.04 Desktop:

- The installation removes nothing from Ubuntu Desktop. **GDM remains the
  login screen** and, after the restart, offers “Ubuntu” and “Querencia
  Desktop”. Switching in both directions by logging out and in works.
- No GNOME session services run in the Querencia session.
- The **session tools** (Screenshot, Settings, Keyboard Shortcuts, Volume,
  session dialog, notification center) appear **only in Querencia**. The
  other Querencia programs are also visible in GNOME.
- **Five file types** for which Ubuntu sets no default (Markdown, JSON, XML,
  Python, shell scripts) then open with Querencia Text Editor in GNOME. This
  can be changed in GNOME under Settings → Apps → Default Apps or with “Open
  With”.
- **Settings are shared:** Querencia and GNOME read the same gsettings
  values. If you change the icon theme in Querencia, it also applies in
  GNOME; the other way round, Querencia shows the Yaru icons on Ubuntu
  Desktop because Ubuntu sets them as a user value. Separate settings for the
  Querencia session are a follow-up item.

### Own login screen (optional)

`querencia-anmeldung` is a login screen in the Querencia look (greetd with
ReGreet). The metapackage only suggests it (Suggests); it is not installed
automatically. **GDM remains the recommendation.**

- Install: `sudo apt install querencia-anmeldung`. Next to GDM, GDM stays the
  default until you switch:

  ```bash
  sudo dpkg-reconfigure querencia-anmeldung
  ```

  The switch takes effect after the next restart; the same question switches
  back.
- By default it shows **only the Querencia session**. Other sessions can be
  enabled in `/etc/querencia/greetd/sitzungen.conf`. **GNOME runs without a
  screen lock under this login screen:** gnome-shell ties the lock to GDM.
  This applies to every other login screen and is not a Querencia bug.
- apt installs `accountsservice`, which ReGreet needs, as a dependency.
- The login screen interface is in English, and so is the clock.

### Removing

```bash
sudo apt purge 'querencia-*' labwc
```

```bash
sudo apt autoremove --purge
```

Only `autoremove --purge` also removes the packages that were installed
along with Querencia. Otherwise, among others, **wsdd-server stays active as
a network service**. On Ubuntu Desktop the installed packages are then the
same as before the installation (tested). Ubuntu's own labwc 0.9.3 can be
installed again if needed.

Known leftovers:

- User data stays, as usual on Debian: `~/.config/querencia/`,
  `~/.local/state/querencia/`, `~/.local/share/strata/`.
- If `querencia-anmeldung` was installed and no login service was set up
  before (server image), **greetd with a text login** remains the login
  service after removal. Next to GDM, GDM comes back. The clean-up comes with
  `querencia-anmeldung` 0.1.2.

## Known limitations

The full list is in the user guide under
[Known limitations](../../benutzerhandbuch/en/bekannte-einschraenkungen.md).
The most important ones in Alpha 1:

- **Login screen in English:** ReGreet shows buttons and clock in English.
- **Alt+Print in VMs:** the screenshot of the active window did not arrive in
  virtual machines; untested on real hardware.
- **Secondary windows without a title bar:** a window that a program only
  hides when closed appears without a title bar the second time it is opened
  (for example the image information in the Image Viewer). The cause lies in
  the interplay of GTK 4.22 and labwc; the fix in Image Viewer 0.2.3 is in
  progress.
- **Terminal without tabs** until Querencia Terminal 0.3.0.
- **Settings and rc.xml:** changing and resetting values in the Keyboard,
  Mouse, Window Design and Workspaces sections leaves the default values
  written out in `~/.config/querencia/labwc/rc.xml`, and every apply creates
  a backup file `rc.xml.vorher-…`. The effect is correct; the clean-up comes
  with Settings 0.1.1.
- **Network:** connecting and disconnecting in the network applet only works
  when NetworkManager manages the network; otherwise it only shows the state
  (see server image).
- **Firefox as a snap** does not pick up the GTK theme.
- **No dark appearance:** it comes with theme 0.2.
- **Alongside GNOME:** shared gsettings values and Querencia Text Editor for
  five file types in GNOME (see above); on Ubuntu Desktop the Querencia menu
  also lists the GNOME programs, some with the same name.
- **Files:** the About dialog still shows the Strata logo (fix in progress);
  computers can appear twice in the network view.
- The panel and the desktop once (18 October) quit without a recognisable
  cause. Remedy: Ctrl+Alt+Del → Log Out, log in again.

## Tested

- **Mandatory test on a fresh Ubuntu 26.04** with the Alpha 1 package set,
  passed on 20 October 2026 at 22:18: installation, session, all programs,
  logging out and logging in again immediately, locking, polkit, portals and
  language.
  - Login on the **text console (tty1)**: passed;
  - login through **GDM**: passed;
  - login through **querencia-anmeldung**: passed. The `accountsservice`
    dependency (0.1.1-2) comes from this test. After removal greetd stays
    (see above).
  - Measurements: the settings portal answers in 9–11 ms, Terminal from the
    menu in at most 2.2 s, a new login after logging out in under 10 s.
  - Not tested: Alt+Print, copy and paste in Terminal, copying in Files,
    saving in the editor, real hardware, SMB shares.
- **Alongside Ubuntu Desktop** (Ubuntu 26.04.1 with GNOME 50): passed. The
  installation removes nothing, GDM starts both sessions, switching twice in
  each direction, after removal the installed packages are the same as
  before. The findings (shared gsettings, editor for five file types, GNOME
  programs in the Querencia menu, wsdd-server after removal) are described
  above and in progress.
- **Test run QREL-06, part A** (workshop, all programs in the running
  development session): **63 PASS, 3 FAIL, 8 NOT TESTED**. The three FAILs:
  - Image Viewer 0.2.1: image information without a title bar when opened a
    second time (see Known limitations; fix in Image Viewer 0.2.3);
  - Terminal 0.2.0: no tabs – a missing feature, not a regression (Terminal
    0.3.0);
  - Settings 0.0.9: resetting does not restore the labwc configuration byte
    for byte and creates backup files (Settings 0.1.1).

  Six of the eight NOT TESTED concern programs that were replaced by newer
  versions during the run (panel, image viewer, Software, notifications,
  icons); they move to part B. The tester skipped two steps out of caution or
  because of a missed click. **Part B: open.**
- Every program has unit tests and isolated GUI runs (own compositor, own
  profile, German and English, several resolutions). The package set passes
  the static package check and Lintian without errors.

## Licences and origin

- **Programs:** GPL-3.0-or-later, Querencia Screenshot included.
- **Querencia Files:** MIT like its origin Strata; the PDF preview links
  against Poppler (GPL).
- **Libraries of Querencia Software:** MIT or Apache-2.0.
- **Documentation, icons and icon theme:** CC-BY-SA-4.0; the tools of the
  icon repository GPL-3.0-or-later.
- **Login screen:** ReGreet 0.5.0 from the upstream source, GPL-3.0.
- **Backgrounds:** own images without the logo under CC-BY-SA-4.0. The four
  motifs are AI-generated; they will only be published once the generator's
  terms of use allow distribution under CC-BY-SA. Purely AI-generated images
  may not be protected by copyright in some jurisdictions; the licence notice
  is then a note only.
- **The name and logo “Querencia”** are not free content; the project's
  trademark rule applies, also to the logo part of the backgrounds.
- **Signing key of the package repository:** “Querencia Desktop Archive
  Signing Key <archive@querencialinux.org>”.

Copyright 2026 Querencia Desktop contributors.

