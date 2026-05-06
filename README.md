# ViCare — fork with error sensors

This is a fork of the official [Home Assistant ViCare integration](https://www.home-assistant.io/integrations/vicare/)
with three additional diagnostic sensor entities for device error reporting.

## Added sensors (disabled by default)

| Entity | Description |
|--------|-------------|
| `sensor.X_error_count` | Number of active device errors |
| `sensor.X_latest_error_code` | Error code of the most recent error (e.g. `F4`) |
| `sensor.X_latest_error_message` | Human-readable description of the most recent error |

All three sensors are disabled by default and categorised as **Diagnostic**.
Enable them under **Settings → Devices & Services → ViCare → Entities**.

## Purpose

This fork exists to test the error sensor additions before submitting them
as a pull request to the official Home Assistant core repository.

## Installation via HACS

1. HACS → Custom repositories → add this repo as **Integration**
2. Install "ViCare (fork with error sensors)"
3. Restart Home Assistant
4. The existing ViCare config entry continues to work — no reconfiguration needed

## Differences from upstream

- `sensor.py`: three new `GLOBAL_SENSORS` entries for `error_count`, `latest_error_code`, `latest_error_message`
- `strings.json`: three new translation keys (alphabetically sorted)
- `manifest.json`: `version` field added (required for HACS custom components)
