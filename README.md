# Ruffin Manor

**Live site (How to Play): https://troyroberson.github.io/ruffinmanor/**

Ruffin Manor is an interactive Halloween trick-or-treat display: players stay behind a
fence and shoot IR "guns" at 20 animated targets scattered around the yard, competing for
score on a large LED scoreboard. This repo is the **public distribution point** for the
project — firmware binaries and general information. It is not the project's source code
repository; source lives in a private local repo.

## Components

- **IR Targets ("ITC32")** — 20 ESP32-based animated props players shoot at with IR guns.
  Each target has unique firmware (its name/description/behavior are baked in at compile
  time), so there isn't one universal binary — see `binaries/targets/`.
- **Scoreboard** — a 16x64 LED matrix display (built from 16x32 panels) that runs the game
  modes (Free Play, Frenzy, Haunting, Poltergeist) and drives 3 physical control buttons.
- **Mode box** — a standalone physical control panel with 5 arcade buttons, one per game
  mode, for starting a round without the web console. *(Firmware coming soon.)*

## Firmware downloads

| Component  | Binary | Version |
|------------|--------|---------|
| Scoreboard | [`binaries/scoreboard/ITC32.ino.bin`](binaries/scoreboard/ITC32.ino.bin) | see `binaries/scoreboard/version.htm` |
| Targets    | [`binaries/targets/ITC32.ino.bin`](binaries/targets/ITC32.ino.bin) | representative build (bench/test unit) |
| Mode box   | *(not yet published)* | — |

These are backup/reference copies of the binaries used for over-the-air updates on the
live display; they are not served to the hardware directly (the live OTA path runs over
the local network).

## How to play

Players stand behind the yard fence and aim IR "guns" at any of the 20 animated targets.
Hits are free-for-all — no queue or turns, any number of people can play at once. Each
target reacts with its own sound/light/movement effect. A running score is tracked on the
scoreboard, which cycles through timed game modes.
