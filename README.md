# raspy2c
Comprehensive support for I2C devices on the Raspberry Pi

uses:
  - smbus (raspy2c)
  - time (raspy2c(example))

This project originated from the need of measuring and correlating multiple 
(slow) signals in a quantum optics lab at the University of Toronto, Canada.

I2C in combination with a Raspberry Pi was chosen as the way to go, since it
provides a simple and easily expandable architecture. Further inclusion of 
GPIO pins allows for triggered measurements, e.g. to measure the intensity of a
laser pulse whenever it is turned on.

The architecture of the classes supporting different devices is built to easily
add new devices with help of the respective datasheet, while (hopefully) maintaining 
a common syntax.

Do not choose this repository if you need fast ADC reading or real-time DAQ.
The effective data rate for repeated measurements of a single 12-bit ADS1015
channel on a RPi 2B+ is limited to about 1000 SPS -- useful enough to do basic
monitoring tasks, but far too slow for e.g. accoustig measurements.
