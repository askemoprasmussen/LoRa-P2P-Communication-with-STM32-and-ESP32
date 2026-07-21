
# LoRa P2P Communication: STM32 and ESP32

STM32F302 implementation of LoRa Point-to-Point (P2P) communication with an ESP32, using a Ra-01 (SX1278) module over SPI. Built for a special course at DTU.

This repository contains the STM32 side of the project. It receives LoRa packets sent from an ESP32 running the [nopnop2002/esp-idf-sx127x](https://github.com/nopnop2002/esp-idf-sx127x) example.

## Full Guide

The complete step-by-step how-to guide, covering both the ESP32 and STM32 setup, wiring, and testing, is available here: `LoRa_P2P_Guide.pdf` (or link to wherever you host the PDF).

## Hardware

- STM32F302R8 Nucleo-64

- Ra-01 (SX1278) LoRa module, 433 MHz

- ESP32 DevKit (for the transmitting side, see guide)

## Pin Configuration

| Ra-01 Pin | STM32 Pin | Function |

|-----------|-----------|----------|

| 3.3V | 3V3 | Power |

| GND | GND | Ground |

| NSS | PB0 | SPI Chip Select |

| SCK | PC10 | SPI Clock |

| MISO | PC11 | SPI Data Out |

| MOSI | PC12 | SPI Data In |

| RST | PB1 | Reset |

| DIO0 | PA5 | Interrupt (TX/RX done) |

## Building

Requires STM32CubeIDE. Open the project via **File → Open Projects from File System** and build normally.

**Note:** SPI3 must be configured with **Data Size: 8 Bits** in CubeMX (this project's `.ioc` already has this set correctly).

## Credits

- LoRa driver: [wdomski/SX1278](https://github.com/wdomski/SX1278) (STM32 HAL-based SX1278 driver)

- ESP32-side implementation: [nopnop2002/esp-idf-sx127x](https://github.com/nopnop2002/esp-idf-sx127x)

## Results

Achieved 0% packet loss over ~15-20m indoors through multiple concrete floors and walls, at SF7/125kHz/CR4-5. See the full guide for detailed test results and LoRa parameter explanations.

