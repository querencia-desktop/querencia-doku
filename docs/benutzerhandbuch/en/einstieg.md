# Getting started

[Back to contents](index.md)

![Querencia Desktop with the „Orte“ (Places) menu open](../bilder/de-einstieg-orte.png)

The panels and the desktop are German only for now; their labels are quoted
in German with an English translation.

## Logging in

Querencia Desktop is a session of its own. How to start it depends on the
system:

| System | How to log in |
|---|---|
| Ubuntu 26.04 Desktop (GDM login screen) | After installing, **restart once** (GDM reads new sessions only at start-up). On the login screen pick the user, click the gear at the bottom right, choose “Querencia Desktop”, enter the password. |
| Ubuntu 26.04 Server (no login screen) | Log in on the text console (tty1) and type `querencia-session`. |

A Querencia login screen of its own is being packaged (see
[Known limitations](bekannte-einschraenkungen.md)).

After logging in, the desktop with background and icons appears first, then
the two panels.

## The panels

Like GNOME 2, Querencia has two panels.

**Top:** on the left the Q logo with the menus **Anwendungen**
(Applications), **Orte** (Places) and **System**; on the right the
**notification area** for the icons of other programs (see below), the bell
of the notifications and the **clock**. Clicking the clock opens a month
calendar. Volume and network icons can be added at the top right (see
below).

**Bottom:** on the left the **window list** (one button per window), on the
right the **workspace switcher** with four workspaces.

### Menu “Anwendungen” (Applications)

Programs are grouped as in the GNOME 2 menu of Ubuntu 10.04: Zubehör
(Accessories), Bildung (Education), Spiele (Games), Grafik (Graphics),
Internet, Büro (Office), Entwicklung (Programming), Unterhaltungsmedien
(Sound & Video), Systemwerkzeuge (System Tools), Barrierefreiheit (Universal
Access), Sonstige (Other). Empty groups are hidden; each program appears
exactly once. Newly installed programs appear without restarting the panel.

### Menu “Orte” (Places)

Home folder, Desktop, Documents, Music, Pictures, Videos and Downloads (only
those that exist), then Computer, Network and Trash. A click opens the place
in [Querencia Dateien](dateien.md).

### Menu “System”

- **Einstellungen** (Preferences) and **Systemverwaltung** (Administration)
  with the matching programs, among them [System Settings](einstellungen.md)
  and [Software](software.md).
- **Informationen über Querencia** (About Querencia) – versions of the parts.
- **Abmelden …** (Log Out) and **Ausschalten …** (Shut Down) – with a
  question first, see [Session](sitzung.md).

### Notification area

Since Alpha 3.3 (panel 0.4.0). Programs that offer a status icon
(StatusNotifierItem, also through libappindicator, such as Webex, Nextcloud
or Discord) show it here, at the top right, left of the bell. Without icons
the notification area is invisible.

| Input | Effect |
|---|---|
| Pointer on the icon | the program's tooltip |
| Left click | opens the program or brings its window to the front; some programs show their menu instead |
| Right click | the program's menu in the Querencia style |
| Middle button, scroll wheel | go to the program; what they do depends on the program |
| Right click on the narrow edge left of the icons | “Remove From Panel”, “Move” |

If a program asks for attention (e.g. for a new message), its button gets
an orange background.

If you customized the panel before Alpha 3.3, the notification area does not
appear by itself: right-click a free spot of the top panel → “Add to Panel…”
→ “Notification Area”. Limits (no XEmbed for old X11 programs, passive icons
hidden) are listed under
[Known limitations](bekannte-einschraenkungen.md#panel-and-desktop).

### Customising the panels

Right-click a free spot of a panel to open the panel menu:

- **Zum Panel hinzufügen …** (Add to Panel) opens a list with a search field:
  Anwendungen, Orte, System, Fensterliste (window list),
  Arbeitsflächenumschalter (workspace switcher), Uhr (clock),
  Anwendungsstarter … (launcher), Lautstärke (volume), Netzwerk (network),
  Infobereich (Notification Area). The
  new item goes into the area (left, centre, right) that was clicked.
- Right-click an item: **Aus dem Panel entfernen** (Remove from Panel), for
  launchers also **Starten** (Launch).
- **Moving:** drag an item with the middle mouse button, or choose
  “Verschieben” (Move) in its menu and finish with a click on the panel.

The layout is saved and restored at the next login. Moving an item from one
panel to the other is not possible yet.

## The desktop

The desktop shows the icons **Rechner** (Computer), **Persönlicher Ordner**
(Home) and **Papierkorb** (Trash), plus mounted drives (USB sticks, CDs,
network drives – which ones is set in [System Settings](einstellungen.md)
under “Symbole der Arbeitsfläche”, desktop icons).

- **Double-click** opens an icon; **F2** or “Umbenennen …” (Rename) changes
  its label.
- **Selecting:** click, Ctrl+click (add/remove), Shift+click (range), Ctrl+A
  (all), Esc (none), or drag a frame with the mouse.
- Icons can be moved freely; they snap to an invisible grid.
- **Right-click on free space:** create folder, empty file or document, sort
  by name, align icons to the grid, toggle the grid, **change desktop
  background …**
- **Right-click on the trash:** open, empty (with a safety question).
- **Right-click on a drive:** open, unmount or eject.

Several backgrounds are included (“Querencia Blau” and four more motifs, each
with and without logo); choose them in System Settings under
“Hintergrundbild” (background).

## Workspaces

There are four workspaces. The switcher at the bottom right shows them as
small cells; a click or the mouse wheel changes the workspace.

| Shortcut | Effect |
|---|---|
| Ctrl+Alt+← / Ctrl+Alt+→ | workspace to the left / right |
| Ctrl+Alt+Shift+← / → | take the active window along |

Number and names of the workspaces are set in System Settings under
“Arbeitsflächen” (1 to 12).

## Windows

labwc draws the window frames in the “Querencia-Klassisch” theme, with the
program icon in the title bar.

| Shortcut | Effect |
|---|---|
| Alt+Tab / Alt+Shift+Tab | switch windows (with list) |
| Alt+F4 | close window |
| Super+A | maximise / restore |
| Super+←, →, ↑, ↓ | snap to the screen edge |
| Alt+Space | window menu |

In the window list a click activates a window; clicking the active window
minimises it, another click brings it back.

**Super+?** shows all shortcuts (program “Tastenkürzel”), see
[Keyboard shortcuts](tastenkuerzel.md).

## Log out, lock, shut down

- **Lock the screen:** Ctrl+Alt+L. After 10 minutes without input the screen
  locks itself.
- **Log out:** System → Abmelden … or Ctrl+Alt+Del.
- **Shut down or restart:** System → Ausschalten … or Ctrl+Alt+Del.

Details: [Session](sitzung.md).
