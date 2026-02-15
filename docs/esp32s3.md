# Arduino Nano ESP32 (ESP32-S3)

Guide for building and flashing AWTRIX 3 on [Arduino Nano ESP32](https://docs.arduino.cc/hardware/nano-esp32/) board.

## Prerequisites (Windows)

1. **Git** — download and install from [git-scm.com](https://git-scm.com/download/win) with default settings
2. **Python 3** — download from [python.org](https://www.python.org/downloads/), check **"Add python.exe to PATH"** during install
3. **PlatformIO CLI** — open terminal (PowerShell or cmd) and run:
   ```
   pip install platformio
   ```
   If `pio` is not found after install, use the full path: `%USERPROFILE%\.platformio\penv\Scripts\pio.exe`

## Build

```bash
git clone https://github.com/lawdt/awtrix3.git
cd awtrix3
git checkout feature/esp32-s3-nano-support
pio run -e esp32_s3_nano
```

## Flash

1. Connect Arduino Nano ESP32 via USB-C
2. Enter bootloader mode:
   - Short **GND** and **B1** pins with a jumper wire
   - Press **RESET** button
   - Remove the jumper
3. Flash firmware:
   ```
   pio run -e esp32_s3_nano -t upload
   ```
4. After flashing, press **RESET** to boot normally

## First setup

1. Board creates WiFi access point **"AWTRIX3_XXXX"**
2. Connect to it and configure your WiFi credentials
3. After connecting, open the board IP in a browser to access the web interface

## Matrix layout

Default matrix layout is **1** (tiled progressive). If the display shows wrong pixel order:

1. Open the web interface and go to the file manager
2. Create a file `dev.json` with content:
   ```json
   {"matrix": 0}
   ```
3. Try values `0`, `1`, or `2` and reboot after each change

## Pin mapping

See [Hardware](hardware.md#arduino-nano-esp32-esp32-s3) for the full pin mapping table.

## Online flasher

[filename](esp32s3_flasher/index.html ':include :type=iframe')
