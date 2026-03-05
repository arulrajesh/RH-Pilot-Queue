# Pilot Queue

A ZippyQ-style pilot self-service queue plugin for [RotorHazard](https://github.com/RotorHazard/RotorHazard).

Pilots queue themselves at a shared kiosk (tablet/phone), and heats are automatically generated in RotorHazard when all slots are filled.

## Features

- **Kiosk mode** - Touchscreen-friendly interface for pilots to add themselves to slots
- **Spotlight search** - Quick pilot lookup with real-time filtering
- **Auto-generate heats** - Heats are created in RotorHazard automatically when slots fill up
- **FIFO heat ordering** - The oldest unraced heat is always set as the active heat
- **Pack tracking** - Track how many packs each pilot has flown and queued
- **Rest periods** - Configurable cooldown between races for each pilot
- **Admin panel** - Configure slots, max packs, rest periods, and manage the queue
- **Pilot replacement** - Admins can swap pilots in both the queue and generated heats

## Installation

1. Copy the `custom_plugins/pilot_queue` folder into your RotorHazard `custom_plugins` directory
2. Restart RotorHazard

## Usage

### Kiosk Page
Navigate to `http://<your-rh-server>/pilot_queue/` on a tablet or phone placed at the race venue.

Pilots tap **Add Pilot** on their preferred slot, search for their name, and tap to join the queue.

### Admin Page
Navigate to `http://<your-rh-server>/pilot_queue/admin` to configure the queue and manage pilots.

**Settings:**
- **Number of slots** - How many frequency slots per heat (default: 4)
- **Max packs** - Maximum packs a pilot can fly in a session (default: 10)
- **Rest rounds** - Minimum heats between consecutive races for a pilot (default: 0)
- **Race class** - Which RotorHazard class to assign generated heats to
- **Auto-generate** - Automatically create heats when all slots are filled

## Requirements

- RotorHazard 4.0+ (RHAPI version 1.2+)

## License

[MIT](LICENSE)
