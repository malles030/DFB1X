## David's Falcon Booster (DFB)

#### An attempt to build a low-cost memory expansion and accelerator board for the Atari Falcon.

The primary goals of the project are to:

* Be a plug-in board requiring no soldering on the Falcon;
* Increase available RAM beyond the 14MB the stock Falcon can be expanded to;
* Be low cost;
* Provide some acceleration;
* Allow the PSU to remain in the case;
* Be open source.

Some development narration on this project is provided in the [Wiki](https://github.com/dh219/DFB/wiki).

Firmware source (ISE), board design files (KiCAD) and any source for support programs are published at each release.

#### Capabilities

As of 2024 the published firmware supports 64 (2x32) or 128 (2x64) MB of TT-RAM (see OPTION1 below).

It supports only a PGA128 MC68030. The board has been tested between 32 and 50MHz with the CPU normally being the limiting factor.

The FPU is optional and can be run at half the CPU speed, or with an independent oscillator. This is configured by a resistor placement choice.

The Falcon's on-board FPU, if fitted, should be removed to prevent bus conflicts.

#### Video series

I (David) have recorded a number of videos on the DFB1 development, build and testing process and the use of some of its features. They may been seen at my Youtube channel here:

https://www.youtube.com/playlist?list=PLZBirr2xVnY5Mq7EE_Y8pS-P2WgzqQAjB

#### Jumper settings

The 2024 released firmware employs the following jumper options:

Jumper from left to right.

OPTION2 -- inhibit acceleration. The CPU will not switch up to the installed oscillator speed and will instead follow the motherboard clock (normally 16MHz).
OPTION1 -- this communicates the amount of SDRAM installed on the board to the CPLD. Open for 64MB, closed for 128.
FLASH -- this disables the onboard flash ROM. You will boot and work with the ROM on the motherboard. Can be used if no flash chip is fitted.
DISABLE -- this effectively turns off DFB1. The onboard CPU will be active again and the only interaction one can have with DFB1 is to flash a new ROM.

### Forks

Suavek has made a run of boards with some firmware modifications to support bank switching of the flash ROM in case a 1MB package is fitted: https://github.com/eskwadrat/DFB1_SuavekBuild

---

*Copyright 2020-25 D Henderson, released under GPL2.0*
