# Known limitations

[Back to contents](index.md)

State of Alpha 1 (20 October 2026), Querencia Dateien as of Alpha 3
(24 October 2026). The identifiers (QD-…) refer to the project's list of
open items; P1 is important, P2 medium.

## Installation and login

| Item | What it means |
|---|---|
| Ubuntu 26.04 only | The packages exist only for Ubuntu 26.04 (“resolute”), amd64. |
| Not tested on real hardware | Testing was done in virtual machines. Real hardware, printing on a real printer and Windows shares (SMB) are not tested yet. |
| Own login screen untested | Since Alpha 2.1 the optional login screen `querencia-anmeldung` uses the system language. Logging in through it with the package from the repository is not tested yet. |
| greetd stays after removing `querencia-anmeldung` | If no login service was set up before (server image), greetd stays with a text login. Next to GDM, GDM comes back. |
| Next to GNOME: shared settings | Querencia and GNOME read the same gsettings values; an icon theme changed in Querencia also applies in GNOME. Next to Ubuntu Desktop, Querencia shows the Yaru icons because Ubuntu sets the icon theme as a user value. GNOME programs also appear in the Querencia menu. |
| Network connections only with NetworkManager | Connecting and disconnecting in the network applet only works when NetworkManager manages the network. Otherwise, on the server image the applet shows no device and Software cannot install anything; see [Software](software.md#when-software-reports-no-network-connection). |

## Dark appearance

| Item | What it means |
|---|---|
| Window frames and Files stay light | labwc draws the frames with its own theme, Querencia Files has a theme of its own. The session dialog, confirmations and the password prompt are dark only when the dark appearance is already on at login. |
| Third-party GTK 3 programs do not follow | GTK 3 ignores “Prefer dark appearance”. The Querencia programs use GTK 4 and follow the setting (except as listed above). |
| Keyboard focus after switching | After switching between light and dark in a running program, the keyboard focus may sit somewhere else than after a start. |
| Changed theme only after a new login | The panel and the desktop take over a changed theme only after logging in again; switching between light and dark takes effect at once. |
| Firefox as a snap | ignores the GTK theme. |

## Panel and desktop

| Item | What it means |
|---|---|
| Panel crash | In test runs the panel crashed the first time the Applications menu was opened. Since Alpha 2.1 it restarts by itself after a crash, after a few seconds and at most three times in ten minutes. If it does not come back: Ctrl+Alt+Del → Log Out, then log in again. The cause of the crash is being investigated. |
| Workspace switcher without window thumbnails | The cells show no windows. |
| Panel items cannot be moved between panels | Moving within one panel works; otherwise remove the item and add it to the other panel again. |
| “Panels” area in the settings is display only | Change the panels directly. |
| Display scale 1.5 | Centred or tiled backgrounds appear too small. |
| Fullscreen of X11 programs | Some X11 programs lie under the panels in fullscreen. Super+F or Alt+F11 switches the active window to real fullscreen, which then covers the panels. |

## Language

| Item | What it means |
|---|---|
| German only | The panel, the desktop, the lock screen and the shortcut overview are German only for now; the programs speak German and English. |
| System dialogs partly in another language | e.g. messages from GVfs when mounting in Files. |
| Placeholder program identifiers | The panel and some programs still use placeholder identifiers (`org.example…`) until Alpha 3. This makes no difference in use. |

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
| Printing not tested | Not yet tested on a real printer (e.g. from the Document Viewer). |
| Faint text remnants when switching pages | A drawing bug in GTK 4.22; the session works around it by having GTK programs redraw their whole window. |

## Hardware and virtual machines

| Item | What it means |
|---|---|
| Alt+Print in VMs | The screenshot of the active window did not arrive in virtual machines; not tested on real hardware. |
| Wrong resolution after a VM starts | The passed-through graphics sometimes report no monitor data; unplugging and replugging the monitor helps. |
| Sound in VMs | Without a sound card the volume control only shows “Dummy Output”. |
