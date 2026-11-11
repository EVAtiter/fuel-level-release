[English](README.md) | [日本語](README.ja.md)

# Fuel Level

<img width="1280" height="340" alt="1280" src="https://github.com/user-attachments/assets/afa717a9-a2ec-4c5e-aa1a-cf456f7e2125" />

**Fuel Level** is a macOS menu bar utility that displays your available
memory as a car fuel gauge. It's a full SwiftUI rewrite of a Classic Mac OS
C app originally released in 1995.

This repository is the **distribution and support channel** for Fuel Level.

---

## Two distributions

| | Fuel Level (Mac App Store) | Fuel Level Plus (this repo) |
|---|---|---|
| Fuel gauge (free memory) | ✅ | ✅ |
| Battery thermometer | — | ✅ |
| Power meter | — | ✅ |
| System Monitor | ✅ CPU only | ✅ CPU + power + GPU / Neural Engine |
| Combination (three gauges in one panel) | — | ✅ |
| Quick Reveal | ✅ | ✅ |
| Style, lighting, window modes | ✅ | ✅ |
| Distribution | Mac App Store | Notarized binary (direct) / Homebrew |

The battery thermometer, the power meter, and the GPU / Neural Engine / power
layers of the System Monitor rely on undocumented APIs (reading the battery's
internal temperature / SMC / IOReport) and cannot be included in the App Store build.
The App Store edition's System Monitor shows **CPU usage over time**, which
public APIs can provide.

The Plus edition is Developer ID signed and notarized by Apple.

## Download (Fuel Level Plus)

### Homebrew

```
brew install --cask EVAtiter/tap/fuel-level-plus
```

### Direct download

Get the latest version from
[Releases](https://github.com/EVAtiter/fuel-level-release/releases/latest).

1. Download `Fuel-Level-Plus-<version>.zip`
2. Unzip and move `Fuel Level Plus.app` to your `Applications` folder
3. On first launch, click "Open" if prompted (the app is notarized, so
   Gatekeeper will allow it)

## Mac App Store edition

Fuel Level (free — fuel gauge and System Monitor) is on the Mac App Store.

https://apps.apple.com/app/fuel-level/id6786531692

---

## Features

### Gauges

- **Fuel gauge**: shows available memory as a car-style fuel gauge (a
  warning lamp lights/blinks under memory pressure)
- **Battery thermometer** (Plus only): shows battery temperature as a
  car-style coolant gauge. The 10–80 °C range uses a **logarithmic scale** so
  that a wide temperature range reads usefully on a single dial: the ticks run
  10, 20, 40, 80 °C, doubling each step. The needle points straight up at the
  geometric midpoint of 20 and 40 °C — √(20×40) ≈ 28.3 °C — not the arithmetic
  mean of 30 °C. A warning lamp lights/blinks past temperature thresholds
- **Power meter** (Plus only): shows the whole Mac's power draw as a car-style fuel gauge,
  relative to the observed maximum (100%), which is remembered indefinitely.
  The warning lamp blinks while a new peak is being set. The remembered peak
  can be reset anytime from the "Reset Power Peak Memory" menu item
- **System Monitor**: a wide panel that plots usage over time as stacked cubes,
  styled after a car instrument panel (hidden by default).
  The Plus edition shows CPU usage (green = user, amber = system) together with
  power draw (three layouts: Overlay, Split or Center), and adds
  GPU (cyan) and Neural Engine (pink) gauges on the
  right; the rows at 0 / 50 / 100% turn off-white and read as a scale.
  Power draw is split into the chip (SoC) in purple and everything else (display,
  SSD, USB devices, Wi-Fi, memory and so on) in dark purple; Macs whose chip power
  can't be read show a single purple.
  The App Store edition plots CPU usage only, so the graph spans the full width
- **Numeric readout**: click the System Monitor to switch between the graph and
  figures. Fixed-width digits show free memory, memory pressure and CPU (broken
  down into user and system time); the Plus edition adds battery temperature,
  power draw and GPU / Neural Engine
- **Combination** (Plus only): shows the fuel gauge, thermometer and power meter
  shrunk side by side in a single black panel (off by default). Choose a horizontal
  layout (fuel, thermometer, power from left to right), a vertical one (same order
  from top to bottom), or Mini Horizontal: a low panel that leaves out the lower part
  of the gauges, while the ticks, needles and warning lamps stay visible (Comfort style
  only; choosing it switches the style to Comfort). The panel holds the fuel gauge plus whichever of "Show
  Thermometer" and "Show Power Meter" are on; while it is on, the individual gauge
  windows are hidden

### Look and handling

- **Style**: Comfort (the original flat-bottomed shape) or Sport (a full circle)
- **Quick Reveal**: rest the pointer at the bottom edge of the screen for a
  moment and any gauges hidden behind other windows come forward together
  (off by default). While they are revealed, hold down Shift to switch the
  System Monitor to its numeric readout (it goes back when you let go)
- **Always on Top**: keeps the gauges in front of every other window
- **Pin to Wallpaper**: pins the gauges to the desktop wallpaper (clicks pass
  through to the window underneath)
- **Lighting**: auto / Day / Night
- Japanese / English UI
- The app never communicates over the network

## Requirements

- macOS 14.0 Sonoma or later
- Apple Silicon only (Intel Macs are not supported)
- The battery thermometer only appears on Macs with a battery (notebooks)
- The power meter reads the whole Mac's power draw via the SMC (Apple Silicon)

## Privacy

Fuel Level **collects no data**. See [PRIVACY.md](PRIVACY.md) for details.

## Support

Questions, feature requests, and bug reports:
[Issues](https://github.com/EVAtiter/fuel-level-release/issues).

Japanese and English are both welcome.
