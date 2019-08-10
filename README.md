# LCD\_py for Raspberry Pi

This collection of Python scripts are intended to work on a Raspberry Pi connected to an LCD display through I2C protocol.

Also, an Arduino Nano connected through an USB emulated serial connexion is used to operate and retrieve data from a DHT11 sensor.

## Content of this project

### Requirements

In order to function properly these scripts require:

[I2C\_LCD_driver](https://gist.github.com/DenisFromHR/cc863375a6e19dce359d)

[pytz](https://pypi.org/project/pytz/)

### display\_clocks.py

This simple script using pytz will display local time and selected time zones current time.
It will also display the temperature and humidity of the local where the DHT11 sensor is operating.

### display\_infos.py

This script will retrieve the local wireless LAN adapter IP address and display it.
Also, it will request and display the WAN IP address used by the router behind which the Raspberry is connected using ipify.org API.
In the end it will parse and display the data coming from the serial connexion containing temperature and humidity the DHT11 sensor is returning.

### off.py

This one is the most interesting one as it will use Python subprocess module to get the PID of any script used to display information on the LCD screen, provided it starts with the "display" characters string, terminate it nicely then, clear and turn off the LCD screen.

![Picture of the Pi, the Arduino and the DHT11 in action](https://github.com/t0m-a/LCD_py/raw/master/src/common/images/pi.jpg "Arduino, Pi and DHT11")
