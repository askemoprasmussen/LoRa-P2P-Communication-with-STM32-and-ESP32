# ESP32 LoRa Project Files

This folder contains the project-specific files used with the [nopnop2002/esp-idf-sx127x](https://github.com/nopnop2002/esp-idf-sx127x) `basic` example, configured for use with the Ra-01 (SX1278) module as described in the main guide.

## Files

- **`main.c`** — the application code, modified from the library's example to add a 10 dBm transmit power override for EU compliance (see the guide, Part 3)
- **`sdkconfig`** — the saved menuconfig settings, including:
  - Frequency: 433 MHz
  - NSS GPIO: 5, RST GPIO: 4 (matching the ESP32 wiring in Part 2)
  - Communication polarity: sender or receiver (this file reflects whichever mode was last configured; see the guide for how to change it)

## Setting Up From Scratch

1. Clone the library and navigate to the `basic` example:
```bash
   git clone https://github.com/nopnop2002/esp-idf-sx127x
   cd esp-idf-sx127x/basic
```
2. Replace `main/main.c` with the `main.c` from this folder
3. Replace `sdkconfig` with the `sdkconfig` from this folder (or run `idf.py menuconfig` manually and set the values listed above)
4. Build and flash as described in the main guide, Part 3

See the full PDF guide in the repo root for complete step-by-step instructions.
