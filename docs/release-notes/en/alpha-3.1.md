# Querencia Desktop – Alpha 3.1

**As of:** 24 October 2026 · **Status:** in the APT repository since 24 October 2026, 14:48

Alpha 3.1 is a maintenance update to Alpha 3: a fix in Querencia Dateien and
a new, optional program. There are 23 Debian packages for Ubuntu 26.04
(“resolute”) from the same signed APT repository. It is followed by
[Alpha 3.2](alpha-3.2.md).

> **Alpha.** Meant for test systems, not for daily use. Try it in a virtual
> machine with a snapshot first.

## New in Alpha 3.1

- **Querencia Dateien 0.2.1:** after an upgrade from Alpha 2.1, the first
  start of Dateien now also takes over the Querencia Files settings (view,
  hidden files, sorting, folders first, single or double click, side pane).
  Up to Alpha 2.1 Files kept them in `~/.config/strata`; Dateien 0.2.0 only
  read the later location.
- **Querencia Web Wrapper 0.2.0** (new, optional; German „Querencia
  Webhülle“): shows WhatsApp Web in a window of its own with the classic
  menu bar, announces new messages through the notifications and keeps the
  sign-in. Not part of the default installation:

  ```bash
  sudo apt install querencia-webhuelle
  ```

  Calls are not possible (Ubuntu's web engine is built without WebRTC). The
  program is not a product of WhatsApp or Meta and is not affiliated with
  them. Since Alpha 3.2 it is called **Schnatter** (see
  [Alpha 3.2](alpha-3.2.md)).

## Versions

Changed since Alpha 3; all other packages are unchanged.

| Package | Version | Content |
|---|---|---|
| querencia-desktop | 0.1.0~alpha3.1-1 | meta package, version file “Alpha 3.1” |
| querencia-dateien | 0.2.1-1 | also takes over Files settings from `~/.config/strata` |
| querencia-webhuelle | 0.2.0-1 | **new, optional:** WhatsApp Web in a window of its own |

Checksum of the package list (SHA256SUMS): `f87a4a5ff48c4e20d515716e1f7a44e03065eb9dfba40ccca3acfd69aea4a112`.

## Upgrading

```bash
sudo apt update
```

```bash
sudo apt full-upgrade
```

`sudo apt upgrade` works as well. Dateien and the meta package are upgraded;
nothing is removed. The web wrapper is only added if you ask for it (see
above). Upgrading from Alpha 2.1 or 2.2 directly to 3.1 works as described
in the [Alpha 3 notes](alpha-3.md).

## Known limitations

- **Takeover only on the first start.** Dateien takes over the Files
  settings only while it has no settings of its own
  (`~/.config/querencia/dateien.ini`). If you already started Dateien after
  upgrading to Alpha 3, it keeps its settings and the Files values in
  `~/.config/strata` are not used. To catch up: close Dateien, delete
  `~/.config/querencia/dateien.ini` (Dateien's own settings are lost) and
  start Dateien again.
- Otherwise as Alpha 3.

## Tested

- Static package check, Lintian without errors, the source's tests during
  the build (Dateien: 228 passed, web wrapper: 39).
- Upgrade from Alpha 3, 2.2 and 2.1 to 3.1 in an isolated copy of the
  system: nothing removed, nothing held back; a user with Files settings in
  `~/.config/strata` gets them on the first start of Dateien (list, by date,
  hidden files).
- Web wrapper on its own: installs without the meta package; without
  recommendations only the one package.
- Not tested: the web wrapper with a real account in the test VM.

Copyright 2026 Querencia Desktop contributors.
