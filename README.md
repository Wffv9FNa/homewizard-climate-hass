# HomeWizard Climate — HEATERFAN Fork

Fork of [giuseppe99barchetta/homewizard-climate-hass](https://github.com/giuseppe99barchetta/homewizard-climate-hass) with added support for the **HEATERFAN** device type.

## What this fork adds

The upstream integration supports Fan, IR Panel, Glass Panel Heater, and other HomeWizard Climate devices — but the HEATERFAN (combined heater + fan) device type was not handled correctly. This fork was created to support the **Princess 347000 Smart Heating and Cooling Tower** and adds proper HEATERFAN support:

- **Temperature control** — current temperature reading and target temperature setting
- **Integer fan speeds** — speeds 1–10 (cool mode) or 1–4 (heat mode), sent as integers via WebSocket
- **Swing mode** — oscillation control
- **Preset modes** — normal, sleep, natural
- **HVAC modes** — heat, cool, off

### Technical details

The HEATERFAN differs from other device types in a few ways:

| Feature | Other devices | HEATERFAN |
|---------|--------------|-----------|
| Fan speed key | `speed` (low/med/high) | `fan_speed` (integer 1–10) |
| Oscillation key | `oscillation` | `oscillate` |
| HVAC modes | Device-specific | Generic heat/cool/off |
| Fan speed range | 3 levels | 1–4 (heat) or 1–10 (cool) |

All changes are backwards-compatible — existing device types are unaffected.

## Installation

1. Install [HACS](https://hacs.xyz/) if you haven't already.
2. In HACS, go to **Integrations** → **Custom repositories**.
3. Add this repository URL and install.
4. Restart Home Assistant.
5. Add the integration from **Settings → Devices & Services** with your HomeWizard credentials.

## Credits

Based on the fork by [giuseppe99barchetta](https://github.com/giuseppe99barchetta/homewizard-climate-hass), which is itself a fork of the original integration by [dennis1804](https://github.com/dennis1804/homewizard-climate-hass). All credit for the core integration, WebSocket protocol implementation, and support for other device types belongs to the original authors.
