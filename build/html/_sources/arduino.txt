=======
Arduino
=======

Migrating Libraries to 1.0
==========================

Case 1
   Change from
        #include "wiring.h"
        #include "WProgram.h"
        #include "WConstants.h"
        #include "pins_arduino.h"
    to
        #include "Arduino.h"

Case 2
   Change from
        #include "WProgram.h"
   to
        #if ARDUINO >= 100
            #include "Arduino.h"
        #else
            #include "WProgram.h"
        #endif

Arduino Pins
============

I2C bus (RTC, EEPROM)       18, 19
SPI bus (Ethernet shield)   12, 13
Button Up                   5
Button Down/Ethernet CS     10
Button Left                 11
Button Right/SD card CS     4
Button B                    14
Button A                    15
LCD RS                      8
LCD EN                      9
LCD D4                      7
LCD D5                      6
LCD D6                      2
LCD D7                      3

