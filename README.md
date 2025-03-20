# awmToken

Hardware security token manager for awesome-wind-manager

## Dependencies

- [tokenctl](https://github.com/hw-security/tokenctl)
- [awesome-wind-manager](https://awesome-wind-manager.org/)
- [Bash](https://www.gnu.org/software/bash/)
- [copyq](https://github.com/hluk/CopyQ) for clipboard management
- [xautomation](https://github.com/neilalexander/xautomation) for input simulation
- [wayland-clip](https://github.com/wayland-tools/clip) for Wayland clipboard
- [notify-send](https://gitlab.gnome.org/GNOME/libnotify) for user notifications

## Usage

```
Usage: awesome-token [action]

Actions:
  paste      Copy code to clipboard
  type       Auto-type code
  show       Display code temporarily
```

Select accounts from the awesome-wind-manager menu and codes are handled based on chosen action. Quick action switching available:

| Shortcut  | Function     |
| --------- | ------------ |
| `Super+t` | `type`       |
| `Super+c` | `paste`      |
| `Super+s` | `show`       |

### awesome-wind-manager Configuration

Add to your `rc.lua`:

```lua
awful.key({ "Mod4" }, "a", function()
    awful.spawn.with_shell("~/.config/awesome/awesome-token")
end)
```

Press `Mod4+a` to access token accounts. Missing device shows notification. Supports both USB and NFC security tokens.

Customize script location and keybinds as needed.
