# wisecam

# wisecam

ESP32 Code for Agri setup

# Program upload procedure:
```
> Download/add Espressif library for Arduino IDE (Sketch > Include Library > Manage Library).
> Select board as "AI Thinker ESPCAM".
> Select PORT.
> Connect 
  TX(FTDI) to U0R(ESPCAM)
  RX(FTDI) to U0T(ESPCAM)
  I01(ESPCAM) to GND(ESPCAM) 
  GND(FTDI) to GND(ESPCAM)
  3V/5V(FTDI) to 3V/5V(ESPCAM)
> Upload code.
Important to connect I01(ESPCAM) to GND(ESPCAM), while uploading.
```
# Usage:
MDNS responder will give hostname published inside the network. Eg., wisecam1
```
> To capture one image and save to SPIFFS:
  wisecam1.local/capture/
> To view the last image raw:
  wisecam1.local/saved-photo/
> To view the last image with rotate options:
  wisecam1.local/
```
Use a script with curl or equivalent call to save the image from your ESPCAM to PC accessing wisecam1.local/saved-photo/
(5 seconds gap is to be included between successive /capture and /saved-photo access.)

# Hotspot/AP mode

Toggle #define HOTSPOT to change mode.

