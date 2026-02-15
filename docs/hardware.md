# DIY Hardware

if you want to build your own AWTRIX 3, here are the pinout of the Ulanzi clock  
  

|ESP32 PIN | GPIO  | Usage or part                          |
|---|-------|-----------------------------------------------|
|6  | ADC6 / GPIO34    | Battery sensor (optional)                     |
|7  | ADC7 / GPIO35   | LDR (light) sensor (GL5516) (optional)          |
|8  | GPIO32    | Matrix                                      |
|11 | GPIO26    | Left button (optional)                               |
|12 | GPIO27    | Middle button (optional) NC/Inverted                  |
|13 | GPIO14    | Right button  (optional)                              |
|23 | GPIO15    | Buzzer  (optional)                                    |
|33/36| 21 (SDA) /22(SCL)  | Temperature and Humidity Sensors (optional)     |
|37/30| 23(RX)/18(TX) | DFplayer (optional)     |

Supported Sensors:
BME280
BMP280
HTU21df
SHT31

---

## Arduino Nano ESP32 (ESP32-S3)

Pin mapping for [Arduino Nano ESP32](https://docs.arduino.cc/hardware/nano-esp32/) board:

| Function | Ulanzi ESP32 PIN | Ulanzi GPIO | Nano ESP32 Pin | Nano ESP32 GPIO |
|----------|------------------|-------------|----------------|-----------------|
| Matrix | 8 | 32 | D2 | 5 |
| Battery sensor (optional) | 6 | 34 (ADC6) | A1 | 2 |
| LDR sensor (optional) | 7 | 35 (ADC7) | A0 | 1 |
| Left button (optional) | 11 | 26 | D3 | 6 |
| Middle button (optional) | 12 | 27 | D5 | 8 |
| Right button (optional) | 13 | 14 | D4 | 7 |
| Buzzer (optional) | 23 | 15 | D6 | 9 |
| I2C SDA (sensors) | 33 | 21 | A4 | 11 |
| I2C SCL (sensors) | 36 | 22 | A5 | 12 |
| DFPlayer RX | 37 | 23 | D0 | 44 |
| DFPlayer TX | 30 | 18 | D1 | 43 |
| Reset | — | 13 | D7 | 10 |

Notes:
- Use `esp32_s3_nano` build environment in PlatformIO
- Default matrix layout is 1 (tiled progressive). If display is wrong, create `dev.json` with `{"matrix": 0}` or `{"matrix": 2}`
- Flash via USB-C. To enter bootloader mode: short GND and B1 pins, press RESET, then remove the jumper before flashing

---

If the matrix displays meaningless characters, the matrix type must be changed.

Create a dev.json in your filemanager with the following content:

```json
{
  "matrix": 2
}
```

Change the matrix layout to 0,1 or 2

