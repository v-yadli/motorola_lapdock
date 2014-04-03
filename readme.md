My aim is to re-create the main board of [Motorola Lapdock](http://www.techrepublic.com/pictures/cracking-open-the-motorola-droid-bionic-lapdock/) for the purpose of using it as an input/output device for any hardware I want. (It is not a computer, only input and output devices in a look-alike package.)

Even though the original board could be used with some modifications, I'm going about this the hard way, because I want to learn. I'll also be trying to re-create the panel side of the display panel controller with an FPGA and VHDL. Off-the-shelf chip (or fpga) will be used to interface HDMI / DVI / DisplayPort / USB / Ethernet / whatever custom fun people come up with.

At first the plan is to find out how the touchpad driver chip works, then maybe to re-use the Holtek's keyboard -> USB driver chip.


## Specs of interest

* 1366 x 768 @ 60Hz screen
* Keyboard
* Touchpad
* 2 Speakers
* Power on led, charging led
* Assuming a magnetic switch somewhere to detect lid closure
* Internal battery

See [TechRepublic's teardown pictures](http://www.techrepublic.com/pictures/cracking-open-the-motorola-droid-bionic-lapdock/).


## Bottom board

*touchpad, battery button, battery leds, mouse buttons*

* Relays touchpad data pins to "main" board
* Connects mouse buttons to touchpad
* Connects front battery status button and -leds to battery control board
* "U1" has unknown function. Maybe I missed a connector lead, or maybe it's some kind of "check if board present".

Nearly all pins are known:

![](https://raw.githubusercontent.com/gima/motorola_lapdock/master/tp_board/tpboard_overview.jpg)

### Pinouts:

JP3 (to battery control board):

    1 = Led 1
    2 = Led 2
    3 = Led 3
    4 = Led 4
    5 = Led 5
    6 = Led common
    7 = Battery stats button (to Gnd)
    8 = Gnd

JP1 (to touchpad):

    1 = 5V
    2 = Data
    3 = Data clock
    4 = Mouse button 1
    5 = Mouse button 2
    6 = Gnd

JP2 (to main board):

    1 = 5V
    2 = Data clock
    3 = Data
    4 = ? -/- Connected to "U1"
    5 = ? /
    6 = Gnd

- Link: [overview image](//raw.githubusercontent.com/gima/motorola_lapdock/master/tp_board/bottom%20board%20%28tp,batbtn,batleds,mbtns%29.jpg) of pinouts embedded in an image.
- Link: [picture of "U1" (bottom-right)](https://raw.githubusercontent.com/gima/motorola_lapdock/master/tp_board/tpboard_under.jpg).
- Link: [more stuff](//github.com/gima/motorola_lapdock/tree/master/tp_board) regarding this board.


## Touchpad

Help in identifying the touchpad controller chip. Couldn't even find the manufacturer based on the logo.

- Data and clock line logic capture from moving a finger over the touchpad can be found in the [touchpad directory](//github.com/gima/motorola_lapdock/touchpad/). Clock frequency seems to be 12kHz, but the protocol is unknown. (Though that doesn't prove much at all x).

![](https://raw.githubusercontent.com/gima/motorola_lapdock/master/touchpad/legend.png)


## Screen

Not yet under work.

### "JLVDS1" connector

![](https://gima.github.io/motorola_lapdock/imgs/jlvds1.jpg)

### Pinouts:

2 x 15 pins, 30 pins in total. Couldn't find a connector matching this one.

        0                 1
        1 2 3 4 5 6 7 8 9 0 1 2 3 4 5
      
    1   • • • • • • G G • • G G • • G
    2   • • G • • G • • G • • G • • G

G = Gnd. Dots are as of yet unknown. [LVDS](https://en.wikipedia.org/wiki/Low-voltage_differential_signaling).


### Keyboard

The keyboard should be pretty simple. Not that I know much about it, but the pins coming out of the keyboard are probably some sort of keyboard matrix plus the keyboard leds.

The original main board uses [Holtek HT82K94E (USB Multimedia Keyboard Encoder 8-Bit MCU)](holtek.com/english/docum/computer/82k94x.htm) for presenting the keyboard as a USB keyboard:

![](https://gima.github.io/motorola_lapdock/imgs/holtek.jpg)

- Link: [datasheet](//github.com/gima/lapdock_motorola/datasheets)

## eof