# Interfacing screen

I'll also be trying to re-create the panel side of the display panel controller with an FPGA and VHDL. Off-the-shelf chip (or fpga) will be used to interface HDMI / DVI / DisplayPort / USB / Ethernet / whatever.

* Resolution: 1366x768 @ 60Hz (EDID says so)  
(Native? Quite likely :)


## "JLVDS1" connector

![](https://raw.githubusercontent.com/gima/motorola_lapdock/master/screen/jlvds1.jpg)


## Pinouts:

2 x 15 pins, 30 pins in total. Couldn't find a connector matching this one.

        0                 1
        1 2 3 4 5 6 7 8 9 0 1 2 3 4 5
      
    1   • • • • • • G G • • G G • • G
    2   • • G • • G • • G • • G • • G

G = Gnd. Dots are as of yet unknown. [LVDS](https://en.wikipedia.org/wiki/Low-voltage_differential_signaling).


## EDID

@See `w25x10.bin`, `edid.bin`, and `edid.txt`

* Extracted from 128KB SPI memory (Winbond W25X10).
* EDID structure decoded using [Extron EDID Manager](http://www.extron.com/download/software.aspx?material=2&id=E). (Thanks [blogger](http://aricsblog.blogspot.fi/2011/08/edid-reader-for-windows-that-works.html)).


## eof
