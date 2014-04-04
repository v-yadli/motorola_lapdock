## Interfacing keyboard

This one should be pretty simple. Not that I know much about it, but I'm assuming that the keyboard pins contain some sort of keyboard matrix + keyboard led(s).

The original main board uses [Holtek HT82K94E (USB Multimedia Keyboard Encoder 8-Bit MCU)](holtek.com/english/docum/computer/82k94x.htm) for presenting the keyboard as a USB keyboard, but it seems to be programmable, so the correct pin combinations are known only to the firmware. Read-out possibility? Though is it worth the effort? Will see when the work begins on this one.

![](https://raw.githubusercontent.com/gima/motorola_lapdock/master/keyboard/holtek.jpg)

Link: [Datasheet](//github.com/gima/motorola_lapdock/datasheets)

## Connector

*(ffc = flexible flat cable)*

The TechRepublic's teardown (link in main readme) had a picture of this connector, but that one didn't have this dummy ffc bridge.

![](https://raw.githubusercontent.com/gima/motorola_lapdock/master/keyboard/connector.jpg)

---

## eof
