# Home Assistant Blueprints — Homelab Italia

Free, tested blueprints for Home Assistant. Each one was run on a real Home Assistant 2026.9 instance with simulated devices before release. Configure everything from the UI, no YAML editing needed.

## 💡 Motion-activated light (day/night)
Turns lights on with motion and off when the room is empty, done properly:
- only when it's dark (optional illuminance sensor);
- dim at night, full brightness during the day;
- motion again restarts the timer, so you're never left in the dark;
- **doesn't turn off a light you switched on manually**;
- multiple sensors and lights per room.

[![Open your Home Assistant instance and show the blueprint import dialog.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fhomelabitalia%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fblueprints%2Fmotion_light.yaml)

## 🪟 Window open → turn off heating/AC (and restore it)
If a window stays open for a few minutes, turns off the room's thermostat or AC. When all windows are closed again, it **restores the exact previous state** (HVAC mode and target temperature) using a scene snapshot. A quick airing doesn't trigger anything. Optional notification.

[![Open your Home Assistant instance and show the blueprint import dialog.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fhomelabitalia%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fblueprints%2Fwindow_open_climate.yaml)

## 🧺 Appliance finished (washer, dishwasher, dryer)
Uses a smart plug with power metering (Shelly, Sonoff, Zigbee…):
- start detection (2 minutes above threshold), so a plug reboot doesn't fire it;
- **ignores mid-cycle pauses**, notifies only when it's really done;
- tells you how long the cycle took;
- with a door sensor, keeps reminding you until you open the door.

[![Open your Home Assistant instance and show the blueprint import dialog.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2Fhomelabitalia%2Fhome-assistant-blueprints%2Fblob%2Fmain%2Fblueprints%2Fappliance_finished.yaml)

| Appliance | Start (W) | End (W) | Minutes below end |
|---|---|---|---|
| Washing machine | 10 | 5 | 4 |
| Dishwasher | 10 | 3 | 15 (long drying pauses) |
| Dryer | 50 | 10 | 3 |

## Manual install
Copy the file into `config/blueprints/automation/homelab_italia/`, then **Settings → Automations & scenes → Blueprints → reload**.

## Need something custom?
I write and test custom Home Assistant automations, packages and blueprints for your setup: describe what you want and get a ready-to-install file with instructions.
👉 **[Custom automation on Ko-fi](https://ko-fi.com/homelabitalia/commissions)**

If these blueprints saved you some time, you can [buy me a coffee ☕](https://ko-fi.com/homelabitalia).

Issues and suggestions are welcome. License: MIT.
