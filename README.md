# Session

Bar glyph that opens a session menu: shut down, reboot, hibernate, or lock.

## What it does

- **Widget** — power icon on the QS Bar; click opens the session panel.
- **Panel** — Shut Down, Restart, Hibernate, Lock screen (labels follow the
  system locale; English + Portuguese ship in `content/I18n.qml`).
  Host dismisses on Escape or click outside the card.
- **Service** — `systemctl poweroff|reboot|hibernate` and `ryoku-shell lock`
  (same lock path as Super+L / native quick settings).

## Panel placement

Ryoku’s `PluginPanel` always anchors the card under the bar glyph. There is no
manifest or host API for a screen-centered modal. This plugin uses a compact
session list inside that host card; dismiss is the host’s full-screen
click-outside layer.

## What it reads and writes

Reads nothing. Writes nothing under the plugin state dir. On action it runs one
of the commands in `dependencies.commands`.

## Settings

None.

## Preview

`assets/preview-widget.png`

## Source

Canonical source: `/home/felix/Work/power-button/`

## Install

```
ryoku plugin validate /home/felix/Work/power-button
ryoku plugin add /home/felix/Work/power-button --bar --yes
```

## Author

Felix <eu@leandrofelix.dev.br>: community plugin (`official` is false).
