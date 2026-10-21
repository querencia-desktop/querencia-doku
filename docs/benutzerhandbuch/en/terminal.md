# Querencia Terminal

[Back to contents](index.md)

**Start:** Applications → Accessories → Querencia Terminal.

A plain terminal modelled on MATE Terminal and GNOME Terminal 2.x: one window
with a menu bar, tabs and the user's shell, scroll bar on the right.

## What the terminal can do

- Starts the user's shell in the home folder, size 80×24 characters,
  10,000 lines of scrollback.
- **Menu bar** File · Edit · View · Tabs · Help. F10 and Alt+letter do not
  open the menu bar; they stay with the shell (e.g. for Midnight Commander or
  the command line).
- **Copy and paste** as in GNOME Terminal 2: Ctrl+Shift+C copies the
  selection, Ctrl+Shift+V or Shift+Insert pastes. Ctrl+C and Ctrl+V stay
  control characters for the shell.
- Selecting and middle-click paste as usual on Linux.
- **Context menu** (right-click, Menu key or Shift+F10): Copy, Paste, Select
  All, New Tab, Close Tab.
- Each start from the menu opens its own window. When the shell ends
  (`exit`, Ctrl+D), its tab closes; the last tab closes the window.
- Interface in German or English.

## Tabs

| Shortcut | Effect |
|---|---|
| Ctrl+Shift+T | new tab |
| Ctrl+Shift+W | close tab |
| Ctrl+Shift+Q | close window |
| Ctrl+Page Up / Ctrl+Page Down | previous / next tab |
| Ctrl+Shift+Page Up / Ctrl+Shift+Page Down | move tab to the left / right |
| Alt+1 to Alt+9 | switch to tab 1 to 9 |

- The **tab bar** appears from the second tab on. View → “Always Show Tab
  Bar” shows it with a single tab too; the choice is saved.
- A **middle-click** on a tab closes it, a **double-click** on the free part
  of the tab bar opens a new one. Tabs can be moved with the mouse.
- A new tab starts in the working directory of the current one. The tab
  shows the title the shell sets.
- If a program other than the shell is still running in a tab, closing the
  tab or the window asks first (“Close this terminal?” or “Close this
  window?”).
- There is no wrap-around at the first and last tab. If a command is not
  possible at the moment (e.g. Ctrl+Page Down with a single tab), the key
  goes to the shell.
- Help → Keyboard Shortcuts lists all shortcuts of the terminal.

## Not included yet

Search, profiles, font and colour choice, and use as the default terminal
with a command (`-e`/`-x`). Middle-click pasting of a selection made in
another program does not always work yet. In the dark appearance the menu
bar and the tab bar stay light.
