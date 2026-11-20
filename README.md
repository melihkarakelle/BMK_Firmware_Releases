# BMK Firmware Releases

Firmware files for BMK hand units and receivers. The **BMK FlyMate** app (App Store / Google Play) reads the
list in [`bmk_finder_firmwares.json`](bmk_finder_firmwares.json) and installs these files over Bluetooth, so most
users never need to download anything from here by hand.

## Latest firmware

All three hand units share one version number since v3.6.

| Device | Version | File | Update over |
|---|---|---|---|
| FlexiDisplay YELLO (nRF52832) | **v4.13** | [FlexiDisplay_YELLO_v4.13.zip](https://github.com/melihkarakelle/BMK_Firmware_Releases/raw/main/FlexiDisplay_YELLO_v4.13.zip) | Bluetooth (DFU) |
| SkyLink 434 MHz | **v4.11** | [SkyLink_434_v4.11.zip](https://github.com/melihkarakelle/BMK_Firmware_Releases/raw/main/SkyLink_434_v4.11.zip) | Bluetooth (DFU) |
| FlexiDisplay (original, ESP32) | **v4.11** | in [FlexiDisplay-Firmware-Releases](https://github.com/melihkarakelle/FlexiDisplay-Firmware-Releases) | Bluetooth or WiFi |
| ThermalHunter | v1.5 | [ThermalHunter_v1.5.zip](https://github.com/melihkarakelle/BMK_Firmware_Releases/raw/main/ThermalHunter_v1.5.zip) | Bluetooth (DFU) |

FlexiTimer firmware and settings forms live in [FlexiTimer_Files](https://github.com/melihkarakelle/FlexiTimer_Files).

## How to update

1. Open **BMK FlyMate**, connect to the unit and hold the phone next to it (within 1–2 m).
2. Open **Device Update** and pick the firmware for your unit.
3. Put the unit into update mode:

**FlexiDisplay YELLO**
- From v4.0 on: the app asks the unit; press the **RED** button when the unit asks to confirm.
- Older firmware: on Display 1 or 2 hold the joystick centre for 4–10 seconds and release, choose
  **FW UPDATE(DFU)** in the Quick Menu and confirm with RED. The screen shows *FIRMWARE UPDATE MODE / BLE OTA READY*.
- If the menu cannot be reached: power the unit off, then hold the joystick centre and press RED together to switch it on.
- Before the update starts, RED cancels. With no update the unit restarts normally after about 2 minutes.

**SkyLink 434 MHz**
- From v4.0 on: the app asks the unit; press the **RED** button to confirm.
- Older firmware: power the unit off, press and hold the side button, then also hold RED. Keep both pressed for
  5 seconds until the LED blinks fast (DFU mode). With no update it returns to normal mode after about 6 minutes.

**FlexiDisplay (original)**: see the instructions in
[FlexiDisplay-Firmware-Releases](https://github.com/melihkarakelle/FlexiDisplay-Firmware-Releases).

Nearby units in update mode appear in the app's list; tap the upload button next to yours.

## Version history

### v4.13 — FlexiDisplay YELLO (November 2026)
- **Spoken alerts** from the unit's buzzer: signal lost / back, GPS fixed / lost, beacon GPS fixed / lost, battery
  low / critical, beacon battery low, and "Yello on / off" at switch on and off. Settings → DEVICE → **ALERTS** chooses
  VOICE (default) or MELODY (the tones of older firmware).
- **CONTRAST** setting back in Settings → DEVICE (−5 to +5, default 0).
- **Flight recorder:** up to 100 flights, newest first; when the memory is full the oldest flight is overwritten.
  Switching off while recording saves the flight; after a flat battery the flight is closed at the next switch-on.
  Flights saved with older firmware are not kept by this update: download them first.
- **Settings** are kept on the flash chip in two copies (safe if the power fails while saving); your current settings
  are carried over by the update.
- **The clock keeps running while the unit is off**, so flight dates are right before the GPS has a fix.
- FACTORY RESET now also erases the flights. SEARCH MODE OFF message no longer wraps.
- Manual: FlexiDisplay YELLO manual for v4.13 (English, Español, Français, Deutsch) on bmks.co.uk.

### v4.12 — FlexiDisplay YELLO (November 2026)
- Settings are saved again: changes made in the menus or from the app (RDT code, channel, names, last beacon and
  position at power off) could be lost after switching the unit off. Please update if you use v4.11.

### v4.11 — all three hand units (November 2026)
- **RDT code B1xxxx or B2xxxx:** the RDT CODE menu (YELLO, original FlexiDisplay) now lets you choose 1 or 2 after the
  B, then the last 4 digits. In BMK FlyMate's Device Settings you type the whole 6-digit code (B1xxxx or B2xxxx).
- The full RDT code set in the app is now saved on the unit (v4.0 / v4.1 kept their own first two digits).
- Everything from v4.1 below.

### v4.1 — all three hand units (November 2026)
- **Beacon selection shared with BMK FlyMate:** pick a beacon on the app's map and the FlexiDisplay follows it
  (SELECTED screen); pick one on the unit (BEACON SELECT, QR page, antenna kiss) and the app follows. When the app
  connects it selects the unit's last beacon, so it is ready at once.
- **SkyLink 434:** remembers the beacon selected in the app and sends its 2Way / FlexiTimer return link only to that
  beacon (and to the 2Way beacon set up from it) — it no longer answers every FlexiTimer on the channel.
- **FlexiDisplay YELLO and original:** GPS accuracy (Q) from the receiver's own error estimate, no position drift in
  GPS low power, steadier GPS reception (YELLO).
- Use together with the latest AltiLoc 2Way beacon and FlexiTimer firmware, which accept a return-link message only
  with their own RDT code: another flyer's hand unit can no longer turn your beacon's power down.

### v4.0 — FlexiDisplay YELLO
- Compass: tilt compensation, three-turn calibration (flat, upright, on its side); the arrow also works with the unit held upright.
- FIND devices from the app.
- GPS aiding from the phone: faster first fix.
- Step counter with automatic low-power mode while you walk.
- Firmware update requested from the app and confirmed with the RED button.
- 2Way beacon setup from the app; FSK / LoRa radio mode in Device Settings.
- Bluetooth output power raised to +4 dBm (nRF52832 maximum).
- Firmware version readable by the app (Device Information Service): the app tells you when an update is available.

### v4.0 — SkyLink 434 MHz
- Receives LoRa beacons (AltiLoc LoRa and AltiLoc 2Way) as well as FSK.
- 2Way beacon setup from the app; FSK / LoRa radio mode in Device Settings.
- RDT (remote dethermaliser) transmit power raised to 22 dBm (was 10 dBm).
- Firmware update requested from the app and confirmed with the RED button.
- Same version number as the FlexiDisplay units from now on.

### Earlier releases
| Device | Version | Date | File |
|---|---|---|---|
| FlexiDisplay YELLO | v4.12 | 2026-11 | replaced by v4.13 |
| FlexiDisplay YELLO | v4.11 | 2026-11 | replaced by v4.12 |
| FlexiDisplay YELLO / SkyLink 434 | v4.1 | 2026-11 | replaced by v4.11 |
| FlexiDisplay YELLO / SkyLink 434 | v4.0 | 2026-11 | replaced by v4.1 |
| FlexiDisplay YELLO | v3.3 | 2026-10 | FlexiDisplay_YELLO_v3.3.zip |
| FlexiDisplay YELLO | v3.2 | 2026-09 | FlexiDisplay_YELLO_v3.2.zip |
| FlexiDisplay YELLO | v3.1 | 2026-07 | FlexiDisplay_YELLO_v3.1.zip |
| FlexiDisplay YELLO | v3.0 | 2026-06 | FlexiDisplay_YELLO_v3.0.zip |
| SkyLink 434 MHz | v1.7.0 | 2026-10 | GPS_BLE_Dongle_1_7.zip |
| SkyLink 434 MHz | v1.6.0 | 2026-10 | GPS_BLE_Dongle_1_6.zip |
| SkyLink 434 MHz | v1.5.0 | 2026-07 | GPS_BLE_Dongle_1_5.zip |

YELLO v3.3 and SkyLink v1.7.0 stay in the list for older app versions (`legacy_only`); the new app hides them.

## Files in this repository

- `bmk_finder_firmwares.json` — firmware list read by BMK FlyMate (also mirrored to `api.bmks.app`).
- `firmwares.json` — list for the old BMK Firmware Loader app, kept unchanged for old installs.
- `base_ota.zip` — Bluetooth recovery image. **Do not install** unless asked to by BMKs support.
- `FlexiDisplay_test.bin`, `FlexiDisplay_ST7567_Display_2_0.bin`, `flexitimer_f1a.zip` — older builds kept for old app versions.

Installing firmware made for another device can leave the unit unusable. Always pick the entry that matches your unit.
