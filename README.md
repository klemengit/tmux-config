# tmux config

Personal [tmux](https://github.com/tmux/tmux) configuration, living in
`~/.config/tmux`.

**Superseded by [herdr](https://github.com/klemengit/herdr).** This config is
kept for reference and for machines still on tmux; the herdr config is a direct
port of it, keybinding for keybinding, so the muscle memory carries over. New
changes go there.

Omarchy seeds this file once from `/usr/share/omarchy/config/tmux` and then
leaves it alone.

## Shortcuts

Prefix is `Ctrl+Space` (`Ctrl+B` still works as a secondary).

### Panes

| Keys                       | Action                    |
| -------------------------- | ------------------------- |
| `prefix+h` / `Alt+Enter`   | Split vertically          |
| `prefix+v` / `Alt+Shift+Enter` | Split horizontally    |
| `prefix+x` / `Alt+Esc`     | Kill pane                 |
| `Alt+h/j/k/l`              | Focus left/down/up/right  |
| `Ctrl+Alt+←↓↑→`            | Focus left/down/up/right  |
| `prefix+←↓↑→`              | Resize, and enter resize mode |

Resize mode: after `prefix+arrow` the arrows keep resizing on their own, no
prefix needed. `Esc` or `Enter` leaves; any other key leaves and is handled
normally. The status bar shows `RESIZE` while it's active.

### Windows

| Keys                          | Action        |
| ----------------------------- | ------------- |
| `prefix+c`                    | Create window |
| `prefix+r`                    | Rename window |
| `prefix+k`                    | Kill window   |
| `Alt+←` / `Alt+→`             | Previous / next window |
| `Alt+Shift+←` / `Alt+Shift+→` | Move window left / right |

Windows rename themselves to the basename of the pane's working directory.

### Sessions

| Keys                       | Action                   |
| -------------------------- | ------------------------ |
| `prefix+Shift+C`           | Create session           |
| `prefix+Shift+R`           | Rename session           |
| `prefix+Shift+K`           | Kill session             |
| `prefix+Shift+P` / `Alt+↑` | Previous session         |
| `prefix+Shift+N` / `Alt+↓` | Next session             |

`detach-on-destroy` is off, so killing the last session drops you into another
one instead of back to the shell.

### Other

| Keys       | Action                                   |
| ---------- | ---------------------------------------- |
| `prefix+?` | Show keybindings in a popup              |
| `prefix+q` | Reload configuration                     |
| `prefix+e` | Edit this pane's scrollback in nvim      |
| `prefix+[` | Copy mode (vi keys: `v` select, `y` copy) |

`prefix+e` opens the pane's scrollback in a floating nvim popup, the way
Zellij's "edit scrollback" works. It needs `~/.local/bin/tmux-edit-scrollback`,
which is not in this repo.

## Appearance

Status bar on top, running on the terminal's own palette so transparency still
works. The active pane is marked by heavy border lines and a brighter border
colour, with inactive panes' text dimmed. The right side of the status bar shows
`RESIZE` / `COPY` / `PREFIX` / `ZOOM` state flags and the hostname.

## Install

```sh
git clone git@github.com:klemengit/tmux-config.git ~/.config/tmux
```

Move any existing `~/.config/tmux` aside first.
