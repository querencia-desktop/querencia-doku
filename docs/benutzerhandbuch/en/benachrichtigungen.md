# Notifications (Querencia Benachrichtigungen)

[Back to contents](index.md)

The service starts with the session and shows messages from programs
(standard `org.freedesktop.Notifications`, e.g. `notify-send`).

![Notification with urgency “critical”](../bilder/en-benachrichtigungen.png)

## What notifications look like

- They appear at the **top right** below the top panel and stack downwards;
  at most five are visible at a time, more wait.
- **Display time** by urgency: low 3 s, normal 5 s; **critical** messages have
  an orange border and stay until closed.
- While the mouse pointer rests on a message, its time does not run out.
- A click triggers the program's main action; action buttons appear when the
  program offers some. The “Close” button removes the message.
- Pictures in messages are scaled down to at most 48 pixels.

## Do not disturb and history

Until there is a panel icon for it, both work in the terminal:

```bash
querencia-benachrichtigungen --nicht-stoeren an
```

```bash
querencia-benachrichtigungen --nicht-stoeren aus
```

```bash
querencia-benachrichtigungen --verlauf
```

(`an` = on, `aus` = off, `--verlauf` = history.) A **notification centre**
with a stored history and a panel icon are in progress.
