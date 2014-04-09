# Bottom board

*touchpad, battery button, battery leds, mouse buttons, magnetic sensor*

* Relays touchpad data pins to "main" board
* Connects mouse buttons to touchpad
* Connects front battery status button and -leds to battery control board
* Provides magnetic sensor to main board for detecting lid closure

![](https://raw.githubusercontent.com/gima/motorola_lapdock/master/tp_board/tpboard_overview.jpg)


## Pinouts:

*(ffc = flexible flat cable)*

JP3 (ffc to battery control board):

    1 = Led 1
    2 = Led 2
    3 = Led 3
    4 = Led 4
    5 = Led 5
    6 = Led common
    7 = Battery stats button (to Gnd)
    8 = Gnd

JP1 (ffc to touchpad):

    1 = 5V
    2 = Data
    3 = Data clock
    4 = Mouse button 1
    5 = Mouse button 2
    6 = Gnd

JP2 (ffc main board):

    1 = 5V from main board
    2 = Data clock
    3 = Data
    4 = 3.3V from main board to U1
    5 = From U1
        3.3V  No magnet present (lid open)
        0V    Magnet present (lid closed)
    6 = Gnd

Link: [Pinouts embedded in an image](//raw.githubusercontent.com/gima/motorola_lapdock/master/tp_board/bottom%20board%20%28tp,batbtn,batleds,mbtns%29.jpg).


## eof
