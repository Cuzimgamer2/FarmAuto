# FarmAuto

## What it is

FarmAuto is a Minescript farming macro for SkyBlock Garden farms. It loads recorded farm routes from a JSON configuration, moves through waypoints automatically, and can react to pests while farming.

## Main Files

- `FarmAuto.py` — Main runtime script
- `setup.py` — Configuration setup wizard
- `farmauto_config.json` — Farm and macro configuration
- `config_lib.py` — Configuration loading and saving
- `rotation.py` — Camera rotation helpers
- `version_working beacon.py` — Backup or previous working copy

## Main Features

- **F6** — Cycles crop selection between automatic detection and configured crops.
- **F8** — Starts farming from the nearest configured crop start point or the selected crop.
- **F9** — Shows pest information. When the macro is idle, it reads the current pest status from the tab list.
- **F10** — Starts the pest hunter manually.
- **F12** — Pauses or resumes the macro. Movement is stopped safely while paused. and displays a beacon

## How It Works

FarmAuto loads the configuration file and builds a waypoint table for each configured crop. The farm loop then uses these waypoints to move through the farm automatically.

While farming, FarmAuto can check for nearby pests, stop the farming process when necessary, and switch to a vacuum tool to clear them.

In `PestFarming` mode, the macro also monitors the Minecraft log file for pest spawn messages and can react to them automatically.

## Configuration

The `farmauto_config.json` file contains the global settings and farm layouts.

Important configuration values include:

- Hoe slot
- Vacuum slot
- Fishing rod slot
- Pest cooldown
- Pest plot name
- Auto kill on path
- Auto verify tab
- Active crop
- Farms and their waypoint lists

## Setup Tool

`setup.py` is the companion wizard for creating and editing the FarmAuto configuration.

It can record:

- Start points
- Turn points
- End points

The setup tool then writes the recorded farm layout to the JSON configuration file.

## Related Helpers

### `config_lib.py`

Provides the JSON-backed `Config` class used to load and save FarmAuto settings.

### `rotation.py`

Provides smooth camera movement helpers such as `look` and `look_at`.

## Project Structure

```text
FarmAuto/
├── FarmAuto.py
├── setup.py
├── farmauto_config.json
├── config_lib.py
├── rotation.py
└── version_working beacon.py
```

## Short Summary

FarmAuto consists of a main runtime script, a setup wizard, a JSON configuration file, and helper modules.

Its core functionality includes:

- Automated crop farming
- Waypoint-based farm routes
- Pest detection and handling
- Crop selection
- Pause and resume functionality
- Manual pest checking
- Farm route configuration
