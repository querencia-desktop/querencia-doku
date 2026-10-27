# Questions and answers

[Back to contents](index.md)

**How do I see all shortcuts?**
Super+? (Windows key, Shift and the key with the question mark). See
[Keyboard shortcuts](tastenkuerzel.md).

**How do I get volume and network into the panel?**
Right-click a free spot in the top panel → “Zum Panel hinzufügen …” (Add to
Panel) → “Lautstärke” (volume) or “Netzwerk” (network). On a fresh user
profile neither is there yet.

**Where are the settings?**
System → Einstellungen → Systemeinstellungen. The background can also be
reached by right-clicking the desktop.

**How do I install programs?**
System → Systemverwaltung → Software. Installing asks for your own password.
See [Software](software.md).

**I logged out – can I log in again right away?**
Yes. When logging out, Querencia ends the programs and services of the
session, so that a new login starts cleanly.

**The screen went dark and locked although I did nothing.**
After 10 minutes without input Querencia locks the screen. Unlock with your
own password.

**The log-out question just waits – is that right?**
Yes. Questions do not count down by themselves. A countdown can be switched
on in `~/.config/querencia/sitzung.ini`, see [Session](sitzung.md).

**Why are some parts German?**
Since Alpha 3.3 the Querencia programs, the panel and the desktop are
available in German, English, Italian, Spanish and French. Still German only
are the lock screen, the volume control window and the keyboard shortcuts
overview. Some dialogs come from system libraries (e.g. GVfs, the GTK file
dialog) and follow their translations; GTK needs the language pack
`language-pack-gnome-<xx>` of the chosen language.

**How do I choose another language?**
In the settings under “Language and Region”, effective from the next login
(see [System Settings](einstellungen.md)). If a language is missing there,
its locale is not installed; the package `locales-all` brings all of them.
To try a single program, start it like this:

```bash
LANGUAGE=en querencia-rechner
```

**Where are screenshots saved?**
In the folder `Screenshots` inside the Pictures folder; existing files are
never overwritten.

**A program hangs or does not respond.**
Applications → System Tools → System Monitor, select the process, “End
Process” (Del) or “Kill Process” (Ctrl+K).

**Where do I find logs for a bug report?**
Under `~/.local/state/querencia/` (one `.log` file per program, the session
start in `sitzung-start.log`).

**The panel or the desktop has disappeared.**
Ctrl+Alt+Del → Log Out and log in again. If the whole session hangs, log in on
a text console (Ctrl+Alt+F3) and type `querencia-session --exit`.

**How do I remove Querencia?**
`sudo apt remove 'querencia-*'`. Your own settings in `~/.config/querencia`
and logs in `~/.local/state/querencia` are kept. Choose your usual session on
the login screen again.
