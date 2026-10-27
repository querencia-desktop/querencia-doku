# Known limitations

[Back to contents](index.md)

State of Alpha 1 (20 October 2026); notification area and Schnatter as of
Alpha 3.3, languages, login screen, drivers and Querencia Dateien as of
Alpha 3.4 (27 October 2026). The identifiers (QD-…) refer to the project's
list of open items; P1 is important, P2 medium.

## Installation and login

| Item | What it means |
|---|---|
| Own login screen German and English only | The optional login screen (`querencia-anmeldung`) follows the system language for German and English; for Italian, Spanish or French it shows English. Since Alpha 3.4 it reports an expired password clearly, but it can only be changed on the text console (see [Getting started](einstieg.md#logging-in)). Without it, log in via GDM (choose “Querencia Desktop” at the gear) or on the text console with `querencia-session`. |
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
| Notification area: no XEmbed | Old X11 programs that offer their icon through the older XEmbed method show none. Programs with StatusNotifierItem (also libappindicator) are shown. |
| Notification area: passive icons hidden | Icons that a program reports as “passive” stay hidden; there is no button to expand them. Many programs can always show their icon themselves. |
| Notification area: program started before the panel | It does not always register; then restart the program. |
| Notification area with real programs | Tested with test programs and the libayatana-appindicator library, not yet with Webex, Nextcloud or Discord themselves. |

## Programs

| Item | What it means |
|---|---|
| Small language gaps | Since Alpha 3.4 all programs, the panel, the desktop, the lock screen, the volume control and the keyboard shortcuts overview are available in German, English, Italian, Spanish and French. In Italian the key name “Return” stays English in menu shortcuts. |
| Language and Region: only languages with a locale | The page only offers languages for which a locale is installed. The recommended package `locales-all` (about 230 MB) brings all of them. A change takes effect from the next login. |
| Only one keyboard layout (QD-057, P1) | Several layouts with a switch key are missing. |
| System dialogs partly in another language (QD-015, P2) | e.g. the “Message from the system” when connecting to a server in Querencia Dateien. |
| Querencia Dateien: undo with limits | Undo only works within its own window and until Querencia Dateien is closed. Deleting permanently and “Empty Trash” cannot be undone; replaced items do not come back; “Extract Here” is not in the history. See [Undo and redo](dateien.md#undo-and-redo). |
| Querencia Dateien: Files settings only on the first start | Since Alpha 3.1 Dateien takes over the Files settings on its first start. If you already started Dateien under Alpha 3, it keeps its own settings; to catch up: close Dateien, delete `~/.config/querencia/dateien.ini` (Dateien's own settings are lost), start Dateien again. Bookmarks are kept. |
| Querencia Dateien: no column view | The column view of Querencia Files is gone; Ctrl+1, Ctrl+2 and Ctrl+3 are icons, list and compact. |
| Querencia Dateien: no folder tree | The side pane only shows “Places”; the view is not remembered per folder. |
| Querencia Dateien: content search without index | “Also file contents” only reads text files up to 10 MB, no network places and no documents such as odt or pdf; large folders take time. The hits do not update, copying and dragging from the search results does not work yet. |
| Querencia Dateien: tabs keep only the folder | Restored tabs only keep the folder, not view, zoom or history. |
| Querencia Dateien: thumbnails for PDF | Only appear with an installed PDF thumbnailer and `bubblewrap`; otherwise the icon stays. |
| Querencia Dateien: servers partly untested | Tested with test servers for SFTP, WebDAV and FTP. A successful connection to a Windows share (SMB) and certificate questions with Secure WebDAV are untested. |
| Querencia Dateien: “Remember password” on the second try | After a wrong password a WebDAV server no longer offers to remember it. |
| Querencia Dateien: real devices untested | Drives and network drives are only tested with images and test servers, not with real USB devices. |
| Schnatter: no calls | Ubuntu's web engine is built without WebRTC. |
| Schnatter: notifications only while the window is open | Closing quits Schnatter; Schnatter does not show an icon in the notification area yet. |
| Schnatter: untested with a real account | Tested are the move of the folders, the sign-in page and the window, not working with a real account. |
| Image Viewer: secondary windows without title bar | A dialog opened for the second time appears without title bar. |
| Terminal: middle-click paste | A selection from another program does not always arrive. |
| Printing not tested | Not yet tested on a real printer (e.g. from the Document Viewer). |
| Faint text remnants when switching pages | A drawing bug in GTK 4.22; the session works around it by having GTK programs redraw their whole window. |

## Hardware and virtual machines

| Item | What it means |
|---|---|
| Driver change untested | The page “Drivers” is only tested with simulated cards. A real change to the NVIDIA driver, computers with two graphics cards and Secure Boot are untested. A change needs `ubuntu-drivers-common`, network and password and only takes effect after a restart. Take a snapshot first. |
| Drivers: “This session” wrong in VMs | In a virtual machine with software rendering (llvmpipe) the page “Drivers” shows “OpenGL on the graphics card” for “This session:”; the renderer above correctly says llvmpipe. To be fixed in a later version. |
| Wrong resolution after a VM starts (QD-027, P2) | The passed-through graphics sometimes report no monitor data; unplugging and replugging the monitor helps. |
| Sound in VMs | Without a sound card the volume control only shows “Dummy Output”. |
