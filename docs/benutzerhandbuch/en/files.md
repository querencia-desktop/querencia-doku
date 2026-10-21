# Querencia Files – file manager

[Back to contents](index.md)

**Start:** menu Orte (Places), e.g. “Persönlicher Ordner” (Home); double-click
a folder icon on the desktop; or Applications → Accessories → Querencia
Files.

Querencia Files is Querencia's file manager, a fork of the file manager
Strata, restyled after Nautilus 2.30: menu bar, toolbar, location bar,
sidebar with places and devices.

## What Files can do

- **Views:** icons, list (sortable) and columns; switch in the “View” menu.
- **Working with files:** create folders, rename (F2), cut, copy, paste,
  duplicate, move to trash, delete permanently (Shift+Del, with a question),
  undo; show or hide hidden files; tabs and several windows.
- **Search:** Ctrl+K searches by name in the home folder and on all mounted
  drives.
- **Preview and properties:** preview for text, source code, images, PDF,
  audio and video; Alt+Return shows the properties.
- **Drives:** USB sticks, CDs and other drives appear under “Devices” with
  their own icon, even when not mounted. While Files runs, newly plugged-in
  drives are mounted (can be switched off in the Files preferences). If a
  drive is still busy when unmounting, Files asks.
- **Network:** “Network” in the sidebar shows computers found on the network;
  “Connect to Server …” opens shares via SMB (Windows shares) or SFTP. For an
  unknown SFTP server Files shows the key type and the SHA256 fingerprint so
  that you can check it before connecting. Connected SMB shares can be
  disconnected with a button.
- **Open with:** a double-click opens a file with the default program, e.g.
  text files in the Text Editor, PNG in the Image Viewer, PDF in the Document
  Viewer, archives in the Archive Manager. “Extract here” uses Querencia
  Archiv.
- **Updates** come only through apt; Files does not ask GitHub or the AUR
  for new versions and shows no update notice.

## Shortcuts

See [Keyboard shortcuts](tastenkuerzel.md#programs) or Super+?.

## Good to know

- System dialogs (from GVfs, e.g. when mounting) may appear in English or
  German depending on the system language.
- In the network view the same computer can appear twice because two
  discovery services report it.
- In the dark appearance Files stays light for now; it has a theme of its
  own.

See also [Known limitations](bekannte-einschraenkungen.md).
