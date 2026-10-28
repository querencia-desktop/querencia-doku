# Querencia Desktop – Alpha 3.6

**As of:** 28 October 2026 · **Status:** in the APT repository since [date], [time]

Alpha 3.6 is a maintenance release with two fixes. On a fresh install the
panel, the desktop and Querencia Dateien show the Querencia icons instead
of the GNOME-Human icons. Querencia Software no longer lists programs
twice. There are 24 Debian packages for Ubuntu 26.04 (“resolute”) from the
same signed APT repository; 4 of them are newly built.

> **Alpha.** Meant for test systems, not for daily use. No security or
> data-loss guarantees. Try it in a virtual machine with a snapshot first.
> Querencia Dateien itself carries the stage “beta”.

## New in Alpha 3.6

- **Querencia icons on fresh installs** (`querencia-shell` 0.1.0~alpha13
  with panel 0.4.1 and desktop 0.3.2, Querencia Dateien 0.3.1): without an
  icon theme chosen by the user, the panel, the desktop and Querencia
  Dateien used to show the GNOME-Human icons, such as a glossy computer and
  a metal trash can, while the system settings showed “Querencia”. Without
  a choice of your own they now follow the default of the Querencia
  session, that is “Querencia”, with flat icons. If you picked an icon
  theme yourself under “Erscheinungsbild” (appearance), nothing changes.
  Outside the Querencia session it stays GNOME-Human.
- **No duplicate programs in Querencia Software** (`querencia-software`
  0.1.8): programs such as Remmina that Ubuntu lists in two package sources
  under slightly different IDs (once with, once without the ending
  `.desktop`) appear only once in search and categories. Fixed along the
  way: GIMP disappeared from Software as soon as it was installed.

What Alpha 3.5 brought (login screen in five languages, line “This
session” of the page “Drivers”) is described in the
[notes for Alpha 3.5](alpha-3.5.md).

## Versions

Package set of 28 October 2026 (24 packages).

| Package | Version | Content |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.6-1 | Meta package, version file “Alpha 3.6”; requires at least the new versions of shell, Dateien and Software |
| querencia-shell | 0.1.0~alpha13-1 | **changed:** panel 0.4.1, desktop 0.3.2 with the icon default of the session; also keyboard shortcuts help, volume control |
| querencia-dateien | 0.3.1-1 | **changed:** file manager with the icon default of the session |
| querencia-software | 0.1.8-1 | **changed:** software center with catalog 0.1.1, no duplicate programs |
| querencia-einstellungen | 0.2.1-1 | System settings (unchanged since Alpha 3.5) |
| querencia-anmeldung | 0.1.5-1 | Login screen in five languages, optional (unchanged since Alpha 3.5) |
| querencia-sitzung | 0.1.10-1 | Session dialog, lock screen |
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
| querencia-webhuelle | 0.3.0-1 | Transitional package to Schnatter |
| querencia-files | 0.2.0-1 | Transitional package from Alpha 3 |
| querencia-session | 0.1.0~alpha10-1 | Session starter; sets “Querencia” as the default icon theme |
| querencia-symbole | 0.8-1 | Program icons and icon theme |
| querencia-hintergruende | 0.2-1 | 16 backgrounds |
| labwc | 0.9.8-0querencia5 | Backport of the window manager |

From the settings to labwc the packages are byte-identical to Alpha 3.5.

Checksum of the package list (SHA256SUMS): `19dfc9355bbcb45b0d4832dc240c913b7be59444d28affa58bb03676859942fc`.

## Upgrading from Alpha 3.5

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` works as well. APT upgrades 4 packages
(`querencia-shell`, `querencia-dateien`, `querencia-software`,
`querencia-desktop`) and downloads about 26 MB for them. Nothing new is
installed, nothing is removed, and there is no question about configuration
files. Schnatter and the login screen stay as they are. Then log out and
log in again; only then do the panel, the desktop and Querencia Dateien
show the Querencia icons.

From Alpha 3.4 it works the same way; the packages from Alpha 3.5 come
along (the settings, and the login screen if installed), see the
[notes for Alpha 3.5](alpha-3.5.md#upgrading-from-alpha-34).

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`,
restart, choose “Querencia Desktop” at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Fingerprint of the
signing key: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
On a fresh Ubuntu 26.04 server image APT installs
[packages new installation] packages.

## Known limitations

Still valid from Alpha 3.5 (see there). The GNOME-Human icons on fresh
installs and duplicate programs in Software are fixed. In particular:

- **Icon theme:** the default “Querencia” applies only in the Querencia
  session. Next to Ubuntu Desktop, Querencia still shows the Yaru icons,
  because Ubuntu sets the icon theme as a user value. A chosen icon theme
  that is not installed leads to GNOME-Human.
- **Page “Drivers”:** a change needs `ubuntu-drivers-common`, a network
  connection and the password, and it only takes effect after a restart.
  The page is not tested yet with a real NVIDIA, AMD or Intel card, nor on
  computers with two graphics cards or with Secure Boot. Take a snapshot
  before a change.
- **Login screen:** an expired password can only be changed on the text
  console. Texts from GTK itself stay English without the language pack
  `language-pack-gnome-<xx>-base`.
- **Querencia Dateien is a beta**, with the limitations from Alpha 3.4.
- **Not tested on real hardware**, only in virtual machines and in isolated
  copies of the system.

## Reporting bugs

As in Alpha 3, in the project's issue tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Tested

- Every source is a tagged state: panel, desktop and Dateien from
  `panel/0.4.1`, `desktop/0.3.2` and `dateien/0.3.1`, Software from
  `software/0.1.8` with the catalog `katalog/0.1.1`.
- **Icon theme** in isolated sessions with an empty configuration: with
  the default of the Querencia session the panel, the desktop and Dateien
  show “Querencia”, without the default GNOME-Human; a choice of your own
  wins; if the theme “Querencia” is missing, it stays GNOME-Human; if your
  own choice is reset at run time, they switch to “Querencia”. Plus 394
  automatic tests.
- **Software** against the real catalogs of an Ubuntu 26.04: before, 2649
  components with Remmina twice, after, 2647 without duplicates; searching
  “remmina” finds one hit, GIMP is listed again. The catalog has 50
  automatic tests, Software 63; the interface was checked in isolated
  runs.
- Static package check (304 passed), Lintian without errors, test
  installation in an isolated copy of the system (96 checks passed, 103
  with Italian as system language), Italian, Spanish and French complete in
  all 18 packages with texts, a control build gave the same packages.
- **Upgrade** in an isolated copy of the system: from Alpha 3.5 with
  Schnatter (167 checks passed), without Schnatter (154) and from Alpha 3.4
  with Schnatter (167): nothing removed, nothing held back, no questions.
- **In a virtual machine:** [Weg B]
- Not tested: Querencia Software with the new packages against a real
  package manager in the virtual machine [Weg B], and as for Alpha 3.5 a
  real driver change with restart, real NVIDIA, AMD or Intel cards,
  computers with two graphics cards, Secure Boot, the login screen in
  Spanish and French in the virtual machine, real hardware.

## Licences and origin

As Alpha 3.5. Name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
