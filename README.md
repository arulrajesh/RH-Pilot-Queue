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

## User Guide

### 1. Configure the Admin Page

Navigate to `http://<your-rh-server>/q/admin` and configure the following settings:

1. **Race Class** - Select the class that heats will be generated in
2. **Number of Slots** - Frequency slots per heat, match your node count (e.g. `4`)
3. **Max Packs per Pilot** - Total races a pilot can fly in a session (e.g. `10`)
4. **Max Queue Entries** - Times a pilot can be in the queue simultaneously (e.g. `5`)
5. **Rest Rounds** - Heats to skip between a pilot's races, set to `0` for no rest
6. **Auto-Generate Heats** - Check this to automatically create heats when all slots are filled
7. Click **Save Settings**

### 2. Sync Existing Heats (if applicable)

If there are already heats in the selected class (from a previous session or manual setup):

1. Scroll down to the **Queue Overview** section on the admin page
2. Click **Reset Queue**
3. The plugin will scan the class and pick up any existing heats — both completed and upcoming heats will appear on the kiosk

### 3. Open the Kiosk

Navigate to `http://<your-rh-server>/q/` on a tablet or phone placed at the race venue.

- Pilots tap **Add Pilot** on their preferred slot, search for their name, and tap to join the queue
- When all slots in a row are filled, a heat is automatically generated in RotorHazard (if auto-generate is enabled)
- The kiosk shows three sections:
  - **Running / Up Next** - Heats that are currently racing or about to race
  - **Queue Grid** - Upcoming pilot assignments by slot
  - **Completed Heats** - Previously run heats with results

### Admin Controls

On the admin page (`/q/admin`) you can also:

- **Generate Heat** - Manually create the next heat from the queue
- **Replace Pilot** - Swap a pilot in the queue or in a generated heat
- **Reset Queue** - Clear all queue entries and pilot stats, then sync existing heats from the class

## Requirements

- RotorHazard 4.0+ (RHAPI version 1.2+)

## License

[MIT](LICENSE)
