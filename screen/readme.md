## Interfacing screen

*This project has not yet started.*

I'll also be trying to re-create the panel side of the display panel controller with an FPGA and VHDL. Off-the-shelf chip (or fpga) will be used to interface HDMI / DVI / DisplayPort / USB / Ethernet / whatever.

### "JLVDS1" connector

![](https://raw.githubusercontent.com/gima/motorola_lapdock/master/display/jlvds1.jpg)

### Pinouts:

2 x 15 pins, 30 pins in total. Couldn't find a connector matching this one.

        0                 1
        1 2 3 4 5 6 7 8 9 0 1 2 3 4 5
      
    1   • • • • • • G G • • G G • • G
    2   • • G • • G • • G • • G • • G

G = Gnd. Dots are as of yet unknown. [LVDS](https://en.wikipedia.org/wiki/Low-voltage_differential_signaling).

---

### eof
