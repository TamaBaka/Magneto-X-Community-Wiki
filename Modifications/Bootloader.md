---
title: Bootloader Modifications
description: 
published: true
date: 2025-06-03T05:29:50.879Z
tags: mod
editor: markdown
dateCreated: 2025-02-24T23:31:27.629Z
---

# Klipper Firmware Update / Bootloader Related Modifications

Whenever Klipper is updated, the "MCU" boards must also be flashed.  This is not difficult for the toolhead, However, the official instructions for the main MCU requires the electronics cover while the system is running!

Some simple modifications will allow updating everything from the command line.  Only having to open the electronics bay once.

In addition, there is a third board responsible for USB to CAN communication. I also reccommend installing the Katapult bootloader on that board.  Especially if you want to change the CAN bus speed.

## Official Guide
https://wiki.peopoly.net/en/magneto/magneto-x/magneto-linux-mcu-firmware

# Boards

## BTT Octopus Pro V1.1
* Default bootloader requires a TF card to be inserted.
* DFU boot mode is provided if no bootloader exists, and is a much safer method.

DFU boot can be entered one of two ways:
1. Via the command line: https://www.klipper3d.org/Bootloader_Entry.html
2. Bridging the "boot" pins while pressing the reset button for one second.

**IMPORTANT: The first method may not be available while the official bootloader is present.** I recommend setting the bootloader option in Klipper's `make menuconfig` to "No bootloader," and flashing the board.

The original bootloader is [here](/software/btt_octopus_pro_v1.1_stm32h723zet6_bootloader_(dumped_2025-02-23).bin), if you wish to swap back.

You can verify DFU mode using `lsusb`.  Once in DFU mode, Klipper can be updated using `make flash FLASH_DEVICE=0483:df11`.

### Klipper Make Menuconfig Settings
Set these using `make menuconfig` while inside the "/home/pi/klipper/" directory.

* Enable extra low-level configuration options: Selected
* Architecture: STM32
* Processor: STM32H723
* Bootloader offset: No bootloader
* Clock Reference: 25 MHz crystal
* Communication interface: USB on PA11/PA12

### Hardware Modifications
EmperorArthur replaced the WiFi antenna mount with a single boot button.  This is not perfect, since the reset button is not accessable.  However, it allows for entering the bootloader when the main power switch is turned on.  To be used if the software method fails.

## Toolhead
* Default bootloader requires a USB C cable connected to the toolhead.
* [Katapult](https://github.com/Arksine/katapult) presents an alternative method, which can be done without any extra cables.

The original boot loader can be entered by holding the "boot" button while pressing the reset button for one second.

Both Klipper and Katapult can be flashed using `make flash FLASH_DEVICE=2e8a:0003`.

### Klipper Make Menuconfig Settings
Set these using `make menuconfig` while inside the "/home/pi/klipper/" directory.

* Enable extra low-level configuration options: Selected
* Architecture: Rasberry Pi
* Processor: rp20240
* Bootloader offset: 16Kib bootloader \<If using Katapult\>
* Clock Reference: 25 MHz crystal
* Communication interface: CAN bus
  * CAN RX gpio number: 8
  * CAN TX gpio number: 9
  * CAN bus speed: \<Set to same as the adapter board below.  Default 250,000.\>
* Optimize stepper code for 'step on both edges': Selected

### Katapult Specific settings.
GPIO24 (load cell reset) can be abused as a status LED.

## Orange Pi Klipper Adapter Board
This runs Klipper in USB to CAN bridge mode.

Unfortunately, DFU mode does not seem to work.  Katapult needs to be installed using an ST-Link or similar clone.

Confirmed working flash device: https://www.amazon.com/HiLetgo-Emulator-Downloader-Programmer-STM32F103C8T6/dp/B07SQV6VLZ

Regardless of CAN speed selected, do not adjust the Katapult flash speed, as Katapult will be running in USB mode.

### Klipper Make Menuconfig Settings
Set these using `make menuconfig` while inside the "/home/pi/klipper/" directory.

* Architecture: STM32
* Processor: STM32G0B1
* Bootloader offset: 8Kib bootloader \<If using Katapult\>
* Clock Reference: Internal Clock
* Communication interface: USB to CAN bus bridge (USB on PA11/PA12)
* Can bus interface: PB8/PB9
* CAN bus speed: \<see below\>

# CAN Bus Notes

If not using [this patch](https://github.com/Klipper3d/klipper/pull/6866), CAN speed is set by flashing the adapter board.

The Magneto X ships at a default of '250,000', but I reccomend setting it to 1,000,000.
