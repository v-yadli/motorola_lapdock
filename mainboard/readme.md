# Main board

Not a sub-project by itself as such..

Link: [Instructions on how to use the HDMI and USB ports of the dock](http://www.instructables.com/id/The-Raspberry-Pi-Lapdock-Connection/?ALLSTEPS)

*(ffc = flexible flat cable)*

- You can power on the machine by connecting a HDMI cable.
- You can disconnect battery connector from the main board and toggle power by connecting and disconnecting wall socket power, or use an extension cord with a switch.  
*For this to work, you must leave HDMI device connected.*
- The main board works even if you disconnect all ffc's. (Though keep the led, so you can see when it's on.)
- The main (mini) USB port provides behind-hub access to the mouse and keyboard when the machine is powered on.


*Running `lspci -v` under Raspberry Pi:*

    Bus 001 Device 005: ID 22b8:9838 Motorola PCS
      Human Interface Device
      Boot Interface Subclass
      Keyboard
      
    Bus 001 Device 005: ID 22b8:093a Motorola PCS
      Human Interface Device
      Boot Interface Subclass
      Mouse


## eof
