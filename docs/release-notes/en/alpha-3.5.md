# Querencia Desktop – Alpha 3.5

**As of:** 28 October 2026 · **Status:** in the APT repository since 28 October 2026, 12:07

Alpha 3.5 is a maintenance release with two fixes. The login screen now
also speaks Italian, Spanish and French. The page “Drivers” in the system
settings shows correctly whether the session draws on the graphics card or
in software. There are 24 Debian packages for Ubuntu 26.04 (“resolute”)
from the same signed APT repository; 3 of them are newly built.

> **Alpha.** Meant for test systems, not for daily use. No security or
> data-loss guarantees. Try it in a virtual machine with a snapshot first.
> Querencia Dateien itself carries the stage “beta”.

## New in Alpha 3.5

- **Login screen in Italian, Spanish and French**
  (`querencia-anmeldung` 0.1.5, optional): the optional login screen now
  shows its labels, buttons, tooltips and messages, including the
  expired-password notice, in Italian, Spanish and French as well; before,
  these languages got English. The clock follows the date format of the
  language.
- **Page “Drivers” shows the rendering correctly** (Querencia Einstellungen
  0.2.1). The line “This session:” now follows the measured renderer and
  the loaded kernel module. It shows one of three cases:
  - “OpenGL on the graphics card with the free driver”,
  - “OpenGL on the graphics card with the proprietary NVIDIA driver”,
  - “Software rendering” with the reason: the session switched over at
    login because of a graphics problem with this card, or there is no 3D
    acceleration, for example in a virtual machine without 3D graphics.

  Until now a virtual machine with llvmpipe wrongly showed “OpenGL on the
  graphics card”. “OpenGL renderer:” names what the programs of the session
  get; if the session switched over, the new line “Graphics card OpenGL:”
  names the renderer of the graphics card. With virtual graphics the kernel
  driver reads `virtio_gpu` instead of `virtio-pci`. The note about
  software OpenGL is gone when the NVIDIA driver draws. The page now finds
  the session starter the way the session itself does, not only through
  `PATH`; otherwise the renderer could stay “not measured”.

What Alpha 3.4 brought (page “Drivers”, undo in Querencia Dateien) is
described in the [notes for Alpha 3.4](alpha-3.4.md).

## Versions

Package set of 27 October 2026 (24 packages).

| Package | Version | Content |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.5-1 | Meta package, version file “Alpha 3.5”; dependencies unchanged |
| querencia-einstellungen | 0.2.1-1 | **changed:** line “This session” of the page “Drivers” follows the measured renderer |
| querencia-anmeldung | 0.1.5-1 | **changed:** login screen in German, English, Italian, Spanish, French; optional |
| querencia-dateien | 0.3.0-1 | File manager (unchanged since Alpha 3.4) |
| querencia-shell | 0.1.0~alpha12-1 | Panel, desktop, keyboard shortcuts help, volume control (unchanged since Alpha 3.4) |
| querencia-sitzung | 0.1.10-1 | Session dialog, lock screen (unchanged since Alpha 3.4) |
| querencia-software | 0.1.7-1 | Software center |
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
| querencia-session | 0.1.0~alpha10-1 | Session starter |
| querencia-symbole | 0.8-1 | Program icons and icon theme |
| querencia-hintergruende | 0.2-1 | 16 backgrounds |
| labwc | 0.9.8-0querencia5 | Backport of the window manager |

From Dateien to labwc the packages are byte-identical to Alpha 3.4.

Checksum of the package list (SHA256SUMS): `e19e14215b5d86f8174b7ef06b68e9d8de7f528221304327dd81172c99d6f509`.

## Upgrading from Alpha 3.4

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` works as well. APT upgrades 2 packages, 3 with
the login screen; nothing new is installed. It downloads about 1.6 MB
(3.6 MB with the login screen). Nothing is removed, and there is no question about
configuration files. In a virtual machine the upgrade took about
53 seconds, not counting the download of the Querencia packages; it included
a Ubuntu kernel that had just come out (221 MB). If Ubuntu updates arrive at
the same time, the download is larger accordingly. Then log out and log in again.

From Alpha 3.3 it works the same way; what else happens
(`ubuntu-drivers-common` is newly installed) is described in the
[notes for Alpha 3.4](alpha-3.4.md#upgrading-from-alpha-33).

## New installation

Unchanged: add the repository, `sudo apt install querencia-desktop`,
restart, choose “Querencia Desktop” at the gear icon (see
[Alpha 1, installation](alpha-1.md#installation)). Fingerprint of the
signing key: `63F6 C499 246E 3699 CA04 726D 342F 12D2 0CE7 1CBD`.
On a fresh Ubuntu 26.04 server image APT installs
392 packages.

## Known limitations

Still valid from Alpha 3.4 (see there). The wrong line “This session:” in
virtual machines is fixed. In particular:

- **Page “Drivers”:** a change needs `ubuntu-drivers-common`, a network
  connection and the password, and it only takes effect after a restart.
  The page is not tested yet with a real NVIDIA, AMD or Intel card, nor on
  computers with two graphics cards or with Secure Boot. Take a snapshot
  before a change; if there is no picture afterwards, log in on the text
  console (Ctrl+Alt+F3) and remove the NVIDIA packages again.
- **Login screen:** an expired password can only be changed on the text
  console. Texts from GTK itself, such as the tooltip at the eye in the
  password field, stay English without the language pack
  `language-pack-gnome-<xx>-base`.
- **Querencia Dateien is a beta**, with the limitations from Alpha 3.4.
- **Not tested on real hardware**, only in virtual machines and in isolated
  copies of the system.

## Reporting bugs

As in Alpha 3, in the project's issue tracker,
<https://github.com/querencia-desktop/querencia/issues/new/choose>.

## Tested

- Every source is a tagged state: the settings from
  `einstellungen/0.2.1-2`, the login screen from `anmeldung/0.1.5`.
- **Page “Drivers”** in isolated runs with seven simulated cases (virtual
  machine with llvmpipe, NVIDIA with the free driver with and without
  switching over, NVIDIA with the NVIDIA driver, AMD, Intel, no card), in
  German and English: 162 checks passed; the 14 other pages pixel-identical
  to 0.2.0; 159 automatic tests; the catalogs of all five languages 532
  checks.
- **Login screen 0.1.5** in isolated probes in Italian, Spanish, French,
  German and English: all its own texts in the language, clock by the
  language, expired password with the notice, a valid password starts the
  session; 102 configuration cases passed.
- Static package check (304 passed), Lintian without errors, test
  installation in an isolated copy of the system (96 checks passed, 103
  with Italian as system language), a control build gave the same
  packages.
- **Upgrade** in an isolated copy of the system: from Alpha 3.4 with
  Schnatter (167 checks passed), without Schnatter (154) and from Alpha 3.3
  with Schnatter (168): nothing removed, nothing held back, no questions.
- **In a virtual machine:** Alpha 3.4 with Schnatter and the login screen
  from the published repository, then the upgrade to 3.5: 3 Querencia
  packages upgraded, nothing new, nothing removed, no questions; check
  script 110 passed (the remaining message is the log of the running
  panel), login screen 4 of 4, session 28 of 28. Checked by eye: page
  “Drivers” with “Software rendering: no 3D acceleration …” and
  `virtio_gpu`; the login screen in Italian with a wrong and an expired
  password, counter-check in German. New installation (392 packages with
  `locales-all` and `ubuntu-drivers-common`, no Schnatter): check script
  109 of 109, session 28 of 28.
- Not tested: a real driver change with restart, real NVIDIA, AMD or Intel
  cards, computers with two graphics cards, Secure Boot, the driver page in
  Italian, Spanish and French with screenshots, texts from GTK and
  Linux-PAM on the login screen in Italian, Spanish and French, the login
  screen in Spanish and French in the virtual machine, real hardware.

## Licences and origin

As Alpha 3.4. Name and logo “Querencia” are not free content.

Copyright 2026 Querencia Desktop contributors.
