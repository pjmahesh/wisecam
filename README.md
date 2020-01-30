# wisecam

ESP32 Code for Agri setup

# Program upload procedure:
```
> Add Espressif boards https://dl.espressif.com/dl/package_esp32_index.json
  File > Preferences > Additional Board Manager URLs
> Add Espressif board. Search Esp32 at Tools > Boards > Board Manager 
> Add https://github.com/me-no-dev/AsyncTCP to User > Documents > Arduono > library folder
> Add https://github.com/me-no-dev/ESPAsyncWebServer/ to User > Documents > Arduono > library folder
> Select board as "AI Thinker ESPCAM".
> Select PORT.
> Connect
  TX(FTDI) to U0R(ESPCAM)
  RX(FTDI) to U0T(ESPCAM)
  I01(ESPCAM) to GND(ESPCAM)
  GND(FTDI) to GND(ESPCAM)
  3V/5V(FTDI) to 3V/5V(ESPCAM)
> Press and release reset button. Upload code.

Important to connect I01(ESPCAM) to GND(ESPCAM)
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

