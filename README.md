<p align="center">
  <a href="https://gp2040-ce.info">
    <img alt="GP2040-CE" src="https://raw.githubusercontent.com/OpenStickCommunity/Site/main/docs/assets/images/gp2040-ce-logo.png" />
  </a>
</p>

<p align="center">
  Multi-Platform Gamepad Firmware for RP2040
</p>

<H3 align="center">
 *** THIS FORK DOES NOT CHANGE ANY CORE CODING TO THE GP2040-CE FIRMWARE, IT ONLY EXISTS TO CREATE AN INTEGRATED PICO FIGHTING BOARD SPECIFIC FIRMWARE WITH THE GPIO ASSIGNMENTS SET TO SUPPORT THE INTEGRATED PICO FIGHTING BOARD HARDWARE DESIGN ***
</H3>

<p align="center">
  <img src="https://img.shields.io/github/license/OpenStickCommunity/GP2040-CE" />
  <img src="https://img.shields.io/github/actions/workflow/status/OpenStickCommunity/GP2040-CE/cmake.yml" />
  <br />
  <img src="https://img.shields.io/badge/inputlag.science-0.86%20ms-blue" />
  <img src="https://img.shields.io/badge/MiSTer%20latency-0.765%20ms-blue" />
</p>

<p>
  GP2040-CE (Community Edition) is a gamepad firmware for the Raspberry Pi Pico and other boards based on the RP2040 microcontrollers that combines multi-platform compatibility, low latency and a rich feature set to provide endless customization possibilities without sacrificing performance.
</p>

<p>
  GP2040-CE is compatible with PC, PS3, PS4, PS5, Nintendo Switch, Xbox One, Steam Deck, MiSTer and Android.
</p>

## Links

[Downloads](https://gp2040-ce.info/downloads) | [Installation](https://gp2040-ce.info/installation) | [Wiring](https://gp2040-ce.info/controller-build/wiring) | [Usage](https://gp2040-ce.info/usage) | [FAQ](https://gp2040-ce.info/faq/faq-general) | [GitHub](https://github.com/OpenStickCommunity/GP2040-CE)

Full documentation can be found at [https://gp2040-ce.info](https://gp2040-ce.info)

## Features

- Select from 13 input modes including X-Input, Nintendo Switch, Playstation 4/5, Xbox One, D-Input, and Keyboard
- Input latency average of 0.76ms in Xinput and 0.91ms for Playstation 5.
- Multiple SOCD cleaning modes - Up Priority (a.k.a. Stickless), Neutral, and Second Input Priority.
- Left and Right stick emulation via D-pad inputs as well as dedicated toggle switches.
- Dual direction via D-pad + LS/RS.
- Reversed input via a button.
- [Turbo and Turbo LED](https://gp2040-ce.info/add-ons/turbo) with selectable speed
- Per-button RGB LED support.
- PWM Player indicator LED support (XInput only).
- Multiple LED profiles support.
- Support for 128x64 monochrome I2C displays - SSD1306, SH1106, and SH1107 compatible.
- Custom startup splash screen and easy image upload via web configuration.
- Support for passive buzzer speaker (3v or 5v).
- [Built-in, embedded web configuration](https://gp2040-ce.info/web-configurator) - No download required!

Visit the [GP2040-CE Usage](https://gp2040-ce.info/usage) page for more details.

## Performance

Input latency is tested using the methodology outlined at [WydD's inputlag.science website](https://inputlag.science/controller/methodology), using the default 1000 Hz (1 ms) polling rate in the firmware. You can read more about the setup we use to conduct latency testing [HERE](https://github.com/OpenStickCommunity/Site/blob/main/latency_testing/README.md) if you are interested in testing for yourself or would just like to know more about the devices used to do the testing.

| Version | Mode         | Poll Rate | Min     | Max     | Avg     | Stdev   | % on time | %1f skip | %2f skip |
| ------- | ------------ | --------- | ------- | ------- | ------- | ------- | --------- | -------- | -------- |
| v0.7.9  | Xinput       | 1 ms      | 0.45 ms | 1.28 ms | 0.76 ms | 0.24 ms | 98.48%    | 1.52%    | 0%       |
| v0.7.9  | Switch       | 1 ms      | 0.41 ms | 1.23 ms | 0.72 ms | 0.24 ms | 98.53%    | 1.47%    | 0%       |
| v0.7.9  | Dinput (PS3) | 1 ms      | 0.44 ms | 1.27 ms | 0.75 ms | 0.24 ms | 98.49%    | 1.51%    | 0%       |
| v0.7.9  | PS4          | 1 ms      | 0.55 ms | 2.26 ms | 0.90 ms | 0.32 ms | 98.21%    | 1.79%    | 0%       |
| v0.7.9  | PS5          | 1 ms      | 0.55 ms | 2.33 ms | 0.91 ms | 0.33 ms | 98.18%    | 1.82%    | 0%       |

Full results can be found in the [GP2040-CE v0.7.9 Firmware Latency Test Results](https://github.com/OpenStickCommunity/Site/raw/main/latency_testing/GP2040-CE_Firmware_Latency_Test_Results_v0.7.9.xlsx) .xlsx Sheet.

Results from v0.7.8 can be found [HERE](https://github.com/OpenStickCommunity/Site/raw/main/latency_testing/GP2040-CE_Firmware_Latency_Test_Results_v0.7.8.xlsx).  Previous results can be found in the `latency_testing` folder.

## Integrated Pico Fighting Board GPIO Settings

Main Buttons and Directions:

- GPIO 0: Left
- GPIO 1: Up
- GPIO 2: Down
- GPIO 3: Right
- GPIO 4: HOME (PS)
- GPIO 5: SELECT (SHARE)
- GPIO 6: START
- GPIO 7: Punch 1
- GPIO 8: Punch 2
- GPIO 9: Punch 3
- GPIO 10: Punch 4
- GPIO 11: Kick 1
- GPIO 12: Kick 2
- GPIO 13: Kick 3
- GPIO 14: Kick 4

RGB Data Channel

- GPIO 15: RGB Data

Player LEDS (Version 2.0+ PCB can designate these as other functions as the resistor on the line has been removed)

- GPIO 16: Player 1 LED
- GPIO 17: Player 2 LED
- GPIO 18: Player 3 LED
- GPIO 19: Player 4 LED

Modern Controller Buttons, Turbo Functions

- GPIO 20: Touch Pad Click
- GPIO 21: L3
- GPIO 22: R3
- GPIO 23: TURBO LED (Version 2.0+ PCB can designate this as another function as the resistor on the line has been removed)
- GPIO 28: TURBO KEY

I2C Lines both have been pulled high via resistor (3.3V)

- GPIO 26: SDA
- GPIO 27: SCL

USB Passthrough GPIO

- GPIO 24: DATA PLUS
- GPIO 25: DATA MINUS



## Support

If you would like to discuss features, issues or anything else related to GP2040-CE please [create an issue](https://github.com/OpenStickCommunity/GP2040-CE/issues/new) or join the [OpenStick GP2040-CE Discord](https://discord.gg/k2pxhke7q8) support channel.

## Contributing

Want to help improve GP2040-CE? There are a bunch of ways to contribute!

### Community Participation

Have an idea for a cool new feature, or just want to discuss some technical details with the developers? Join the [OpenStick GP2040-CE Discord](https://discord.gg/k2pxhke7q8) server to participate in our active and ever-growing community!

### Pull Requests

Pull requests are welcome and encouraged for enhancements, bug fixes and documentation updates.

Please respect the coding style of the file(s) you are working in, and enforce the use of the `.editorconfig` file when present.

## Acknowledgements

- [FeralAI](https://github.com/FeralAI) for building [GP2040](https://github.com/FeralAI/GP2040) and laying the foundation for this community project
- Ha Thach's excellent [TinyUSB library](https://github.com/hathach/tinyusb) examples
- fluffymadness's [tinyusb-xinput](https://github.com/fluffymadness/tinyusb-xinput) sample
- Kevin Boone's [blog post on using RP2040 flash memory as emulated EEPROM](https://kevinboone.me/picoflash.html)
- [bitbank2](https://github.com/bitbank2) for the [OneBitDisplay](https://github.com/bitbank2/OneBitDisplay) and [BitBang_I2C](https://github.com/bitbank2/BitBang_I2C) libraries, which were ported for use with the Pico SDK
- [arntsonl](https://github.com/arntsonl) for the amazing cleanup and feature additions that brought us to v0.5.0
- [alirin222](https://github.com/alirin222) for the awesome turbo code ([@alirin222](https://twitter.com/alirin222) on Twitter)
- [deeebug](https://github.com/deeebug) for improvements to the web-UI and fixing the PS3 home button issue
- [TheTrain](https://github.com/TheTrainGoes/GP2040-Projects) and [Fortinbra](https://github.com/Fortinbra) for helping keep our community chugging along
- [PassingLink](https://github.com/passinglink/passinglink) for the technical details and code for PS4 implementation
- [Youssef Habchi](https://youssef-habchi.com/) for allowing us to purchase a license to use Road Rage font for the project
- [tamanegitaro](https://github.com/tamanegitaro/) and [alirin222](https://github.com/alirin222) for the basis of the mini/classic controller work
- [Ryzee119](https://github.com/Ryzee119) for the wonderful [ogx360_t4](https://github.com/Ryzee119/ogx360_t4/) and xid_driver library for Original Xbox support
- [Santroller](https://github.com/Santroller/Santroller) and [GIMX](https://github.com/matlo/GIMX) for technical examples of Xbox One authentication using pass-through
