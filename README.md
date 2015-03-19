# About

This is fork modified to work with the RC power sockets from 
[Conrad](http://www.conrad.ch/ce/de/product/619168/Funk-Schalter-Set-Zwischenstecker-4teilig-Reichweite-max-im-Freifeld-30-m-Einsatzort-Innenbereich/SHOP_AREA_880837#). They  are of type Type B with two rotary/sliding switches. Therefore the compiled send binary takes two integers as arguments, the first defining the group and the second the switch.

rcswitch-pi is for controlling rc remote controlled power sockets 
with the raspberry pi. Kudos to the projects [rc-switch](http://code.google.com/p/rc-switch)
and [wiringpi](https://projects.drogon.net/raspberry-pi/wiringpi).
I just adapted the rc-switch code to use the wiringpi library instead of
the library provided by the arduino.


## Usage

First you have to install the [wiringpi](https://projects.drogon.net/raspberry-pi/wiringpi/download-and-install/) library.
After that you can compile the example program *send* by executing *make*. 
You may want to changet the used GPIO pin before compilation in the send.cpp source file.

# Python bindings

The code comes with Python bindings to call the code from Python:
```python
15:30 # python
Python 2.7.3 (default, Mar 18 2014, 05:13:23) 
[GCC 4.6.3] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import rcswitch
>>> rc = rcswitch.RCSwitch();
>>> rc.enableTransmit(4)
>>> rc.switchOn(2, 1)
>>> 
```