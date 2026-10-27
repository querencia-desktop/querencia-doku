# Querencia Desktop – Alpha 3.3

**As of:** 27 October 2026 · **Status:** in the APT repository since 27 October 2026, 12:05

Alpha 3.3 speaks five languages: German, English, Italian, Spanish and
French. Also new are a notification area in the panel for the icons of other
programs, two fixes in Querencia Dateien and a login screen that now also
translates the session names. There are 24 Debian packages for Ubuntu 26.04
(“resolute”) from the same signed APT repository; 18 of them are newly
built or new in this release.

> **Alpha.** Meant for test systems, not for daily use. No security or
> data-loss guarantees. Try it in a virtual machine with a snapshot first.
> Querencia Dateien itself carries the stage “beta”.

## New in Alpha 3.3

- **Five languages.** All Querencia programs, the panel and the desktop
  are now also available in Italian, Spanish and French: menus, dialogs,
  messages, the launchers in the applications menu and the descriptions in
  the software center. The system language decides (Settings → “Language
  and Region”, effective from the next login). Still German only are the
  lock screen, the volume control window and the keyboard shortcuts
  overview (see [Known limitations](#known-limitations)).
- **Newly recommended: `locales-all`.** The meta package now recommends
  `locales-all`. It makes Italian, Spanish and French selectable in
  “Language and Region”; the page only offers languages for which a locale
  is installed. The upgrade installs the package; it takes about 230 MB.
  Texts from GTK itself (for example in the file dialog) come from the
  system's language pack, `language-pack-gnome-<xx>`; the meta package
  deliberately does not pull it in. If you install Querencia on an existing
  Ubuntu, add it for your language yourself, for example for Italian:

  ```bash
  sudo apt install language-pack-gnome-it
  ```
- **Notification area in the panel (panel 0.4.0).** Programs that offer a
  status icon (StatusNotifierItem, also through libappindicator, such as
  Webex, Nextcloud or Discord) now show it at the top right, left of the
  bell:
  - Pointing at the icon shows the program's tooltip.
  - Left click opens the program or brings its window to the front; some
    programs show their menu instead.
  - Right click opens the program's menu in the Querencia style, with
    check marks and radio items.
  - Middle button and scroll wheel go to the program.
  - If a program asks for attention (e.g. a new message), its button gets
    an orange background.

  Without icons the notification area is invisible. The standard panel has
  it already. **If you have already customized the panel,** add it via
  right click on the panel → “Add to Panel…” → “Notification Area”; the
  panel does not change a saved layout by itself. Remove and move it with a
  right click on the narrow edge left of the icons.
- **Querencia Dateien 0.2.4:** the compact view no longer shortens names
  depending on the zoom level; the columns are as wide as the longest name
  (up to 42 characters), longer names appear in full in the tooltip. After
  closing the search the status bar shows the folder again; during the
  search it shows the number of matches and a selection among them. Both
  were listed as known limitations so far.
- **Login screen** (`querencia-anmeldung` 0.1.3, optional): it follows
  the system language, German or English, for buttons and clock and now
  also for the session names. For other system languages it shows
  English.
- **Software:** Thunderbird and Firefox are listed with a description in
  the software center; they can be installed once their package source is
  set up, otherwise they show “Not available”. Snap wrapper packages are no
  longer offered.
- **Schnatter 0.3.1** (optional) is also available in Italian, Spanish and
  French; otherwise unchanged.

What Alpha 3.2 brought (context menus in Dateien, Schnatter instead of the
web wrapper) is in the [Alpha 3.2 notes](alpha-3.2.md).

## Versions

Package set of 27 October 2026 (24 packages).

| Package | Version | Content |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.3-1 | meta package, version file “Alpha 3.3”, **new:** recommends `locales-all` |
| querencia-shell | 0.1.0~alpha11-1 | **changed:** panel 0.4.0 (notification area), desktop 0.3.1; keyboard shortcuts overview 0.2.2 and theme 0.2.2 unchanged |
| querencia-dateien | 0.2.4-1 | **changed:** compact view, status bar after the search |
| querencia-anmeldung | 0.1.3-1 | **changed:** login screen, session names now translated, optional |
| querencia-software | 0.1.7-1 | **changed:** Thunderbird and Firefox with a description |
| querencia-editor | 0.2.5-1 | text editor |
| querencia-terminal | 0.3.3-1 | terminal |
| querencia-sitzung | 0.1.9-1 | session dialog, lock, password dialog |
| querencia-einstellungen | 0.1.7-1 | system settings |
| querencia-rechner | 0.1.7-1 | calculator |
| querencia-bilder | 0.2.7-1 | image viewer |
| querencia-dokumente | 0.1.5-1 | PDF viewer |
| querencia-archiv | 0.1.3-1 | archive manager |
| querencia-systemmonitor | 0.1.6-1 | system monitor |
| querencia-dateisuche | 0.1.6-1 | search for files |
| querencia-screenshot | 0.2.11-1 | screenshot |
| querencia-benachrichtigungen | 0.2.3-1 | notifications |
| querencia-schnatter | 0.3.1-1 | Schnatter, WhatsApp Web in its own window, optional |
| querencia-webhuelle | 0.3.0-1 | transitional package to Schnatter (unchanged since Alpha 3.2) |
| querencia-files | 0.2.0-1 | transitional package from Alpha 3 (unchanged) |
| querencia-session | 0.1.0~alpha10-1 | session starter (unchanged since Alpha 3) |
| querencia-symbole | 0.8-1 | program icons and icon theme (unchanged since Alpha 3) |
| querencia-hintergruende | 0.2-1 | 16 backgrounds (unchanged since Alpha 2) |
| labwc | 0.9.8-0querencia5 | backport of the window manager (unchanged since Alpha 2) |

From the editor to Schnatter the change is the translation into Italian,
Spanish and French.

Checksum of the package list (SHA256SUMS): `ad018bf1e7808970d9a98a1a9aaa3b57d2b0b3febf6601e80fc632b09b2f1060`.

## Upgrading from Alpha 3.2 or 3.1

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` is enough as well. APT upgrades all packages with a new
version (16 to 18, depending on whether Schnatter and the login screen are
installed) and newly installs `locales-all`. For that it downloads about
45 MB (with Schnatter and the login screen); afterwards `locales-all` takes about 230 MB. Nothing is
removed and there is no question about configuration files. In a virtual
machine the upgrade took a few seconds, not counting the download. Log out and in again
afterwards.

If you never customized the panel, the notification area then appears by
itself. If you did, add it as described [above](#new-in-alpha-33).

Upgrading from Alpha 3 works the same way; what happens to Schnatter and the
web wrapper is in the [Alpha 3.2 notes](alpha-3.2.md#upgrading-from-alpha-3-or-31).
From Alpha 2.1 or 2.2 see [Alpha 3](alpha-3.md#upgrading-from-alpha-21).

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`,
restart, choose “Querencia Desktop” at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Fingerprint of the
signing key: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
`locales-all` comes along, Schnatter does not. On a fresh Ubuntu 26.04
server image APT installs 390 packages.

## Known limitations

Still valid from Alpha 3 to 3.2 (see there), unless listed as fixed above.
In particular:

- **Still German only:** the lock screen, the volume control window and the
  keyboard shortcuts overview (including its launcher). In Italian the key
  name “Return” stays English in menu shortcuts (e.g. “Alt+Return” in the
  image viewer).
- **Texts of GTK itself** (file dialog, some buttons) follow the system's
  language pack. Without `language-pack-gnome-<xx>` for the chosen
  language they stay English.
- **The login screen only knows German and English.** With Italian, Spanish
  or French as the system language it shows English.
- **Message for an expired password still technical:** the login screen
  then shows `Pam_acct_mgmt: NEW_AUTHTOK_REQD` instead of a prompt in the
  system language, also in German.
- **Notification area:**
  - No notification area for old X11 programs that offer their icon
    through the older method (XEmbed); they still show none.
  - Icons that the program itself reports as “passive” stay hidden; there
    is no button to expand them. Many programs have their own setting to
    always show the icon.
  - A program that was already running before the panel does not always
    register; then restart the program.
  - An open menu shows changes only the next time it is opened; animated
    icons are not played.
  - The notification area has not yet been tested with Webex, Nextcloud or
    Discord themselves, but with test programs and with the widely used
    library libayatana-appindicator (see [Tested](#tested)).
- **Schnatter** does not show an icon in the notification area yet; it
  reports new messages only while its window is open.
- **Querencia Dateien is a beta.** There is no undo (Ctrl+Z) yet; there is
  no column view and no folder tree in the sidebar. The search finds names
  only, no file contents; you cannot copy or drag from the search results
  yet.
- **Network partly untested:** a successful connection to a Windows share,
  certificate questions for secure connections and real network drives are
  untested.
- **`locales-all` is large:** it takes about 230 MB, even if you only need
  one language.
- **Software OpenGL** costs CPU time and memory; programs started by the
  window manager itself (e.g. through shortcuts) do not get it.
- **Not tested on real hardware**, only in virtual machines and in isolated
  copies of the system.

## Reporting bugs

As for Alpha 3, in the project's issue tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Tested

- Every source is a tagged state, for example the panel from
  `panel/0.4.0-2`, Querencia Dateien from `dateien/0.2.4`, the login screen
  from `anmeldung/0.1.3`.
- **Languages:** catalogs, launchers and descriptions for Italian, Spanish
  and French in all packages 18 of 18; a test installation with Italian as
  the system language in an isolated copy of the system (98 checks passed,
  with screenshots).
- **Notification area (panel 0.4.0)** in isolated runs: with test programs
  63 of 63 in German and English, two screen sizes, light and dark; with a
  program based on libayatana-appindicator 13 of 13; next to another status
  icon service 19 of 19; 309 automatic tests of the panel.
- **Querencia Dateien 0.2.4** in isolated runs: long names in the compact
  view complete at 50, 100 and 200 %, status bar after search and selection
  in German and English; 21 test runs passed, 684 automatic tests of the
  source tree.
- **Login screen 0.1.3** in an isolated test without a real login check:
  German entirely German, English entirely English, no mixing; 96
  configuration cases passed.
- Static package check (300 passed), Lintian without errors, test
  installation in an isolated copy of the system (95 checks passed), a
  control build produced the same packages.
- **Upgrade** in an isolated copy of the system: from Alpha 3.2 with
  Schnatter (167 checks passed), without Schnatter (154), with Schnatter and
  web wrapper (169) and from Alpha 3.1 with web wrapper (170): nothing
  removed, nothing held back, no questions; own settings of Dateien and
  Schnatter kept.
- **In a virtual machine:** Alpha 3.2 with Schnatter and the login screen
  from the published repository, then the upgrade to 3.3: 18 Querencia
  packages upgraded, `locales-all` added, nothing removed, no questions,
  own settings kept; check script 104 of 104, session 28 of 28. Visual
  checks: login screen in German and English with translated session names
  (the message for an expired password stayed technical, see
  [Known limitations](#known-limitations)), a test program in the
  notification area with its menu, compact view and status bar in Dateien,
  Italian in the menu, Dateien, the image viewer and the settings. New
  installation (390 packages with `locales-all`, no Schnatter): check script
  102 of 102, session 28 of 28.
- Not tested: the notification area with Webex, Nextcloud or Discord,
  Spanish and French in the VM, Schnatter with a real account, real Windows
  shares and network drives, real USB devices, login through GDM, real
  hardware.

## Licences and origin

As for Alpha 3.2. `locales-all` is an Ubuntu package. The name and logo
“Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
