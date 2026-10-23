# Known limitations

[Back to contents](index.md)

State of Alpha 1 (20 October 2026), Querencia Dateien as of Alpha 3
(24 October 2026). The identifiers (QD-…) refer to the project's list of
open items; P1 is important, P2 medium.

## Installation and login

| Item | What it means |
|---|---|
| Own login screen not yet packaged (QD-075, P1) | Log in via GDM (choose “Querencia Desktop” at the gear) or on the text console with `querencia-session`. |
| Side by side with an Ubuntu desktop not fully tested (QD-074, P1) | The test on an Ubuntu Desktop system is running. |
| Look on the GDM path (QD-068, P2) | Querencia's font, icon and pointer defaults are still missing there; the session then looks different. In progress. |
| Software offline on server systems (QD-067, P2) | See [Software](software.md#when-software-reports-no-network-connection). |
| Package set behind the development environment | Some packages are one version older than the programs described here (see the release notes). |

## Panel and desktop

| Item | What it means |
|---|---|
| Window list shows all workspaces (QD-013, P2) | A setting “current workspace only” is in progress. |
| Workspace switcher without window thumbnails (QD-012, P2) | The cells show no windows. |
| Panel items cannot be moved between panels (QD-044) | Moving within one panel works. |
| Panel from the package opens the old log-out dialog (QD-069, P2) | Affects the installed packages; in progress. |
| “Panels” area in the settings is display only (QD-046) | Change the panels directly. |
| Display scale 1.5 (QD-028, P2) | Centred or tiled backgrounds appear too small. |
| Fullscreen of X11 programs (QD-065) | Some X11 programs lie under the panels in fullscreen. In progress. |

## Programs

| Item | What it means |
|---|---|
| English not everywhere yet (QD-055, P1) | Panel, desktop, settings, the shortcut overview and the lock screen are German only. |
| Language and region not adjustable (QD-056, P2) | Texts follow the language setting, date and number formats still follow the session's English base setting. |
| Only one keyboard layout (QD-057, P1) | Several layouts with a switch key are missing. |
| System dialogs partly in another language (QD-015, P2) | e.g. the “Message from the system” when connecting to a server in Querencia Dateien. |
| Querencia Dateien: no undo | Ctrl+Z and Shift+Ctrl+Z do not exist yet. Deleted items can be restored from the trash. |
| Querencia Dateien: no column view | The column view of Querencia Files is gone; Ctrl+1, Ctrl+2 and Ctrl+3 are icons, list and compact. |
| Querencia Dateien: no folder tree | The side pane only shows “Places”; the view is not remembered per folder. |
| Querencia Dateien: search by name only | No search in file contents (use [Search for Files](dateisuche.md)); the hits do not update, copying and dragging from the search results does not work yet. |
| Querencia Dateien: thumbnails for PDF | Only appear with an installed PDF thumbnailer and `bubblewrap`; otherwise the icon stays. |
| Querencia Dateien: servers partly untested | Tested with test servers for SFTP, WebDAV and FTP. A successful connection to a Windows share (SMB) and certificate questions with Secure WebDAV are untested. |
| Querencia Dateien: “Remember password” on the second try | After a wrong password a WebDAV server no longer offers to remember it. |
| Querencia Dateien: real devices untested | Drives and network drives are only tested with images and test servers, not with real USB devices. |
| Image Viewer: secondary windows without title bar | A dialog opened for the second time appears without title bar. |
| Terminal: middle-click paste | A selection from another program does not always arrive. |
| Document Viewer: printing | Not yet tested on a real printer. |
| Notifications without notification centre (QD-073) | In progress; until then “do not disturb” via the command line. |
| Faint text remnants when switching pages (QD-070, P2) | A drawing bug in GTK 4.22; the session switches it off, a report to GTK is pending. |

## Hardware and virtual machines

| Item | What it means |
|---|---|
| Wrong resolution after a VM starts (QD-027, P2) | The passed-through graphics sometimes report no monitor data; unplugging and replugging the monitor helps. |
| Sound in VMs | Without a sound card the volume control only shows “Dummy Output”. |
| Alt+Print in VMs | Did not arrive during the test; to be checked on real hardware. |
| Panel and desktop once ended without a trace (QD-025, P1) | Seen once on 18 October, cause unknown. Remedy: Ctrl+Alt+Del → Log Out, then log in again. |
