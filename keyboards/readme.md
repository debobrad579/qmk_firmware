# Custom NuPhy Air75 V2 QMK Firmware

Custom QMK firmware for the NuPhy Air75 V2, built on top of the official NuPhy firmware with a vim emulation layer (and additional remaps for productivity).

## Features

- **Vim mode** — Full modal editing via [qmk-vim](https://github.com/andrewjrae/qmk-vim), toggled with `TOG_VIM` (`Esc`) on the Win/Linux layer
- **VIA support** — Fully remappable via the VIA configurator
- **Wireless** — Bluetooth (3 channels) and 2.4GHz RF support preserved from the stock firmware
- **Custom keycodes** — Tab cycling, Windows Super key shortcuts, and more

## Layers

| # | Name | Activated By |
|---|------|-------------|
| 0 | Mac | Hardware switch |
| 1 | Mac Fn | Hold `Fn` |
| 2 | Win/Linux | Hardware switch |
| 3 | Win/Linux Fn | Hold `Fn` |
| 4 | Side LED control | Hold `m` from Fn layer |

## Custom Keycodes

| Keycode | Action |
|---------|--------|
| `TOG_VIM` | Toggle vim mode |
| `CT_TAB` | Ctrl+Tab (next tab) |
| `CT_S_TAB` | Ctrl+Shift+Tab (previous tab) |
| `SUPER_E` | Super+E (toggle i3 split) |
| `SUPER_D` | Super+D (open rofi dmenu) |
| `SUPER_M` | Super+M (toggle mic mute) |
| `SUPER_N` | Super+N (notifications) |

## Vim Mode

Vim mode is powered by qmk-vim and activated with `TOG_VIM`. The left side LEDs indicate the current mode:

| Mode | Colour |
|------|--------|
| Normal | Blue |
| Insert | Green |
| Visual | Orange |
| Visual Line | Purple |

Enabled extensions: `VIM_G_MOTIONS`, `VIM_PASTE_BEFORE`, `VIM_REPLACE`

## Building

```bash
qmk compile -kb nuphy/air75_v2/ansi -km debobrad579
```

## Flashing

Enter the bootloader by holding the top-left key (`Esc`) while plugging in the keyboard, then run:
```bash
qmk flash -kb nuphy/air75_v2/ansi -km debobrad579
```
