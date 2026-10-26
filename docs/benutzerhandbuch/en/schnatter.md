# Schnatter (WhatsApp Web in a window of its own)

[Back to contents](index.md)

**Start:** Applications → Internet → Schnatter.

Schnatter shows WhatsApp Web in a window of its own with the classic menu
bar, for everyone who wants to write at the computer without keeping a
browser tab open. Up to Alpha 3.1 the program was called “Querencia Web
Wrapper” (German „Querencia Webhülle“), before that “Querencia Messages”
(„Querencia Nachrichten“). The name is the same in German and English.

Schnatter is **not a product of WhatsApp or Meta** and is not affiliated
with them. WhatsApp is a trademark of its owner.

## Installing

Schnatter is not part of the default installation and does not come with
`querencia-desktop`. To install it on its own:

```bash
sudo apt install querencia-schnatter
```

If you had the Querencia Web Wrapper installed, the next upgrade brings
Schnatter (see [release notes Alpha 3.2](../../release-notes/en/alpha-3.2.md)).

## Signing in

On the first start the window shows the WhatsApp Web sign-in page. The
sign-in is kept, also when the window is closed. **File → Log Out and Delete
Data…** signs out and, after a question, empties the session and the cache.

## What Schnatter does

- **Notifications** of new messages through the
  [notifications](benachrichtigungen.md); a click brings the window to the
  front. The window title counts unread messages (“(3) Schnatter”).
- **Downloads** go to the Downloads folder without a question, never over an
  existing file; then a notification offers “Open” and “Open Folder”.
- **Microphone** (voice messages), **camera** and **reading the
  clipboard:** Schnatter asks once per kind and remembers the answer.
- **Other links** open in the default browser or the mail program; the
  window stays with WhatsApp Web.
- **Spell checking** in the language of the interface and in English, as
  far as the dictionaries are installed.
- **Zoom and window size** are remembered.
- If the web page crashes, the window reloads and says so.

## Menus

| Menu | Entries |
|---|---|
| File | Reload, Log Out and Delete Data…, Quit |
| Edit | Cut, Copy, Paste, Select All, Preferences |
| View | Zoom In, Zoom Out, Normal Size, Full Screen |
| Help | Contents, About |

## Preferences

**Edit → Preferences:**

- **Browser identification:** “Standard of the web engine (WhatsApp sees
  Safari on a Mac)” or “Linux identification without site exceptions”.
- **Sound:** “Play sounds and voice messages”.
- **Software graphics:** Automatic (only where the graphics driver is known
  to fail), On or Off.
- **Remembered permissions:** “Forget Answers” for microphone, camera and
  clipboard.

## Keys

| Key | Effect |
|---|---|
| Ctrl+R, F5 | Reload |
| Ctrl+Q | Quit |
| Ctrl+X, Ctrl+C, Ctrl+V, Ctrl+A | Cut, Copy, Paste, Select All |
| Ctrl+Plus, Ctrl+Minus, Ctrl+0 | Zoom In, Zoom Out, Normal Size |
| F11 | Full screen on/off |
| F1 | Help |

## Moving over from the web wrapper

On its first start Schnatter takes over the sign-in and the settings of the
Querencia Web Wrapper (or, if you skipped the web wrapper, of Querencia
Messages): it renames their three folders to `querencia-schnatter`. Nothing
is copied or deleted. If the old program is still running, Schnatter says so
and only starts once it is closed. If Schnatter folders already exist, the
old ones stay untouched.

Afterwards the data is in `~/.local/share/querencia-schnatter`,
`~/.cache/querencia-schnatter` and `~/.config/querencia-schnatter`.

## Good to know

- **No calls.** Ubuntu's web engine is built without WebRTC.
- **Notifications only while the window is open.** Closing quits
  Schnatter; there is no icon in the panel because the panel has no
  notification area yet.
- Only one account per user.
- Schnatter has not been tested with a real account in the test VM (see
  [Known limitations](bekannte-einschraenkungen.md)).
