## Motorola Lapdock documentation project

My aim is to re-create the main board of [Motorola Lapdock](http://www.techrepublic.com/pictures/cracking-open-the-motorola-droid-bionic-lapdock/) for the purpose of using it as an input/output device for any hardware I want. (It is not a computer, only input and output devices in a look-alike package.)

Even though the original board could be used with some modifications, I'm going about this the hard way, because I want to learn.

This repository has directories for each sub-project and some common directories like datasheets and images.


## Specs of interest

* 1366 x 768 @ 60Hz screen
* Keyboard, Touchpad
* Internal battery
* 2 Speakers
* Power on led, charging led
* Magnet sensor for detecting lid closure

See [TechRepublic's teardown pictures](http://www.techrepublic.com/pictures/cracking-open-the-motorola-droid-bionic-lapdock/).


## [_] Interfacing touchpad

    Status: Unknown driver chip, initial logic captures.

Link: [Project's Directory](//github.com/gima/motorola_lapdock/tree/master/touchpad)

*The touchpad driver chip is not identified. Unknown protocol (to me), but operates through two wires (clock and data) at 12 kHz. Preliminary logic captures are available.*


## [_] Interfacing screen

    Status: Connector is named "JLVDS1" and it's GND pins are mapped.

Link: [Project's Directory](//github.com/gima/motorola_lapdock/tree/master/screen)

*EDID extracted, confirms resolution, yay..*


## [_] Keyboard

    Status: Assuming keyboard pins to contain keyboard matrix + leds.

Link: [Project's Directory](//github.com/gima/motorola_lapdock/tree/master/keyboard)


## [_] Battery charging, usb power out, toggle power (switch?) etc.

    Status: Not yet started.

Link: No project directory yet.


## [x] Bottom board

    Status: All interfacing pins mapped.

Link: [Project's Directory](//github.com/gima/motorola_lapdock/tree/master/tp_board)

*Acts as a mediator between main board, touchpad driver and battery controller. Has two one "own" function: magnet sensor to main board.*


## [no] Main board

    Status: Not a sub-project by itself.

Link: [Mainboard Directory](//github.com/gima/motorola_lapdock/tree/master/mainboard)


## eof
