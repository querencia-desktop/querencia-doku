# Alpha 1 – short text for the website

Template for the alpha section of querencialinux.org (as of 20 October
2026). In detail: [Alpha 1 release notes](alpha-1.md).

---

## Alpha 1: ready to try on Ubuntu 26.04

Querencia Desktop Alpha 1 is the first test release: 20 Debian packages for
Ubuntu 26.04, as a desktop or server installation. Querencia does not replace
GNOME, it sits next to it. GDM remains the login screen and, after a restart,
offers “Querencia Desktop” under the gear.

**New in Alpha 1:** a notification center with history and a bell in the
panel, System Settings in German and English with Language and Region and
several keyboard layouts, a window list per workspace, screen locking from
the panel, a button “Arbeitsfläche anzeigen” (show desktop, Super+D), full
screen with Super+F, an archive manager and a PDF viewer. An own login screen
comes as an optional package.

**Tested:** the packages pass the mandatory test on a fresh Ubuntu 26.04,
with login on the text console and through GDM. Alongside Ubuntu Desktop they
can be installed and removed again; afterwards Querencia is removed completely
and on Ubuntu Desktop the package list is as before.

**Installation:** from the signed APT repository at `dl.querencialinux.org/apt`;
add the repository as described on the Alpha page, then `sudo apt install
querencia-desktop`. Tested on 21 October 2026 on a fresh Ubuntu 26.04.

**Known limitations:** on Ubuntu Server, Querencia Software needs
NetworkManager as the netplan renderer, otherwise it cannot install
anything. The login screen is in English. The terminal has no tabs yet, and
a dark appearance is missing; both are in progress.

> **Alpha:** for test systems only, ideally a virtual machine with a
> snapshot. No guarantee regarding security or data.
