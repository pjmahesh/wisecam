# WISECAM

ESP32 Code for Agri setup

# Program upload procedure:
```
> Add Espressif board URL: https://dl.espressif.com/dl/package_esp32_index.json
  File > Preferences > Additional Board Manager URLs
> Add Espressif board to IDE. Search Esp32 at Tools > Boards > Board Manager 
> Add https://github.com/me-no-dev/AsyncTCP to User > Documents > Arduino > library folder
> Add https://github.com/me-no-dev/ESPAsyncWebServer/ to User > Documents > Arduino > library folder
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
MDNS responder will publish hostname inside the network. Eg., wisecam1
```
> To capture one image and save to SPIFFS:
  wisecam1.local/capture/
> To view the last image raw:
  wisecam1.local/saved-photo/
> To view the last image with viewer options:
  wisecam1.local/
> To get wifi rssi value
  wisecam1.local/rssi
```
Use a script to access wisecam1.local/saved-photo/ and save the image from your ESPCAM to PC/Linux
(5 seconds gap is adviced in between successive /capture and /saved-photo access.)

# Hotspot/AP mode

Toggle #define HOTSPOT to change AP/WiFi mode.

