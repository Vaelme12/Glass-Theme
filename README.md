# Glass

A fully transparent theme for [BetterDiscord](https://betterdiscord.app) that lets your desktop wallpaper shine through Discord. Window opacity, tint color, sidebar shading and blur strength are all adjustable with a handful of simple variables.

<!-- Add a screenshot of the theme here: ![Preview](preview.png) -->

## Features

- **Adjustable transparency** from barely tinted to fully see-through
- **Custom tint color** to match your wallpaper and setup
- **Sidebar shading** to separate the server list, channel list and chat
- **Blur for floating elements** such as menus, popouts, dialogs and tooltips
- **Readable text** thanks to an optional text shadow on bright wallpapers
- **Single tint layer** so opacity does not stack up across nested elements

## Requirements

- [BetterDiscord](https://betterdiscord.app) installed on Discord desktop
- **Window transparency enabled in BetterDiscord** (see below). A theme cannot make the window itself transparent, so this step is required.

## Installation

1. Download `Glass.theme.css` from this repository.
2. Open Discord and go to **User Settings → BetterDiscord → Themes**, then click **Open Themes Folder**. On Windows this is `%appdata%/BetterDiscord/themes/`.
3. Move `Glass.theme.css` into that folder.
4. Enable **Glass** in the Themes list.
5. Go to **BetterDiscord → Window Preferences** (the exact name may differ slightly between versions) and enable **Transparency**.
6. Fully quit Discord, including the tray icon, and start it again.

## Configuration

All settings are CSS variables at the top of `Glass.theme.css`:

| Variable | Default | Description |
| --- | --- | --- |
| `--glass-rgb` | `12 12 18` | Window tint color as `R G B` (0-255 each) |
| `--glass-opacity` | `0.35` | Overall window opacity. `0` is fully transparent, `1` is fully opaque |
| `--glass-sidebar-shade` | `0.18` | How much darker the server list, channel list and title bar are than the chat. `0` means no difference |
| `--glass-float-opacity` | `0.90` | Opacity of menus, popouts, dialogs and the settings screen. Keep it high for readability |
| `--glass-blur` | `16px` | Blur strength behind menus, popouts and dialogs. `0px` turns it off |
| `--glass-text-shadow` | `0 1px 3px rgb(0 0 0 / 0.55)` | Text shadow for readability on bright wallpapers. `none` turns it off |

### Overriding settings without editing the theme

To keep your settings when updating the theme, put your values in the **Custom CSS** tab of BetterDiscord instead:

```css
:root {
  --glass-opacity: 0.2;
  --glass-blur: 24px;
  --glass-rgb: 20 10 30;
}
```

### Example presets

| Look | `--glass-opacity` | `--glass-sidebar-shade` | `--glass-float-opacity` |
| --- | --- | --- | --- |
| Subtle tint | `0.55` | `0.15` | `0.92` |
| Balanced (default) | `0.35` | `0.18` | `0.90` |
| Very transparent | `0.15` | `0.25` | `0.85` |

## Good to know

- **The blur does not blur your desktop.** CSS can only blur content inside the Discord window, so `--glass-blur` applies to menus, popouts, dialogs and similar floating elements. Your wallpaper stays sharp. A real acrylic or mica effect needs a window-level feature that a theme cannot provide.
- The theme is designed for Discord's **dark** theme.
- Heavy blur can cost performance on older hardware. Set `--glass-blur: 0px` if you notice lag.

## Troubleshooting

**The window is solid and not transparent.**
Make sure Transparency is enabled in BetterDiscord's window settings and that you fully quit and restarted Discord afterwards.

**Some part of the interface is still opaque.**
Discord changes its class names regularly, so a new update can leave an area unthemed. Please open an issue and describe which area is affected.

**Text is hard to read.**
Increase `--glass-opacity`, raise `--glass-float-opacity`, or strengthen `--glass-text-shadow`.

## Author

Made by **glitschyy**.
