# Pico_6502_v4_ehbasic

this version is of the NEO6502 memulator supporting a 320x240 256 color display, dual buffered.
It will boot into Enhanced basic. You do not need to answer the Memory size question

In order to have the board work correctly, connect UEXT.3 to 6502BUS.40

on the 'console' you can use:

^R : reset the 6502 processor.

^L : toggle statistics output, currently the clock-speed is shown.

^D : dumps the 17 VDU registers and Sprite buffer.

^T : toggle trace of the input chars

The basic version has many extra commands to interact with the VDU/SPRITE/SOUND interface. See the docs
Also have a look at the demo basic-programs.
However no LOAD/SAVE available (yet)

For a quick setup: install the UF2-file on the NEO6502 by pressing the little button on the board. Hold it during powerup and release.
The NEO6502 will present itself as a USB-device on your PC. Copy the UF2-file to it.
That's all

BTW no real USB-keyboard yet. You need to use a terminal emulator on your system, like PuTTY, TeraTerm or something and ... you need to connect to the USB-A connector. No connection to the USB-C connector is required. The NEO6502 will be powered through the USB-A connector.

- I added a default 256 color palette according to these definitions: https://www.ditig.com/256-colors-cheat-sheet
- Ehbasic allows for Mixed case programming.
- A simple sprite engine has been added

# For successful compile
1. use Arduino IDE 2.2.1 (downloaded from www.arduino.cc)

2. add the following required Libraries to the IDE ("Tools" -> "Manage Libraries...")

a) PicoDVI - Adafruit Fork by Luke Wren (1.1.0)

b) Queue by SMFSW (1.11)

c) RP2040_PWM by Khoi Hoang (1.7.0)

d) RPI_PICO_TimerInterrupt by Khoi Hoang (1.3.1)

4. change ehbasic.cpp to point the following line to where your basic.mon file is located locally:
#include "C:\cygwin64\home\Rien\pico\ehbasic.neo6502\basic.mon"
