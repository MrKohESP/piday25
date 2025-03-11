![](https://github.com/MrKohESP/piday25/blob/5b20a6e6c4fbf412ede0f5826ad5f6908304fdba/3D_PCB1_2025-03-11.png)
# Pi DAY 2025
For this Pi Day, we have created a development board based on the Raspberry Pi RP2350B microcontroller (MCU).
This MCU is a Dual Cortex-M33 or Hazard3 processors at up to 150MHz and the board has 16MB of Flash memory.
While this board is pretty much Pico 2 compatible there are some differences.  The LED is on GPIO04 and it has a highly stable 3.00V voltage reference which is connected for ADC circuits.
There is also connectivity and space for an addressable RGB LED on GPIO08, it was left off in production because of it's baking requirement.  You may solder your own RGB LED on this board.

# Warning
UPDATE: PLease do not make this board.  There is currently an issue where it will not load programs.  It does present as a USB drive but when files are copied to it, it restarts and comes back in BOOT mode.
